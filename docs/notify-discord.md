### Notify Discord

Example: Notify on success or error
```yml
  notify-on-error:
    needs:
      - pull-request
      - validation
    if: ${{ always() && (contains(needs.*.result, 'failure') || contains(needs.*.result, 'cancelled')) }}
    uses: codingones/github-actions-workflows/.github/workflows/notify-discord.yml@main
    with:
      bot-username: CI Failure Bot
      notification-content: Some validation checks have failed for branch ${{ github.ref_name }}
      embed-title: Go to the workflow
      embed-url: https://github.com/${{ github.repository }}/actions/runs/${{ github.run_id }}
    secrets:
      DISCORD_WEBHOOK: ${{ secrets.DISCORD_FAILURES_WEBHOOK }}

  notify-on-success:
    needs:
      - pull-request
      - validation
    if: ${{ always() && needs.pull-request.result == 'success' && needs.validation.result == 'success' }}
    uses: codingones/github-actions-workflows/.github/workflows/notify-discord.yml@main
    with:
      bot-username: CI Success Bot
      notification-content: All checks have passed for branch ${{ github.ref_name }} !
      embed-title: Go to the ${{ github.ref_name }} pull request
      embed-url: ${{ needs.pull-request.outputs.pull-request-url }}
    secrets:
      DISCORD_WEBHOOK: ${{ secrets.DISCORD_SUCCESSES_WEBHOOK }}
```