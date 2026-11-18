# Check the email used for coauthor attribution

When investigating a contribution that has not appeared in achievement history,
record the exact author email from the original commit. Compare it with an
account-associated address rather than guessing from the display name.

For a controlled comparison:

1. Ask the account owner which address they want in the commit history.
2. If using the authenticated email API, require that the selected address is
   marked verified. The account's token must have permission to read emails.
3. Put that address in the `Co-authored-by: Name <email>` trailer after an
   empty line in the original commit message.
4. Before merging, inspect both the literal email and the GitHub account linked
   to that author. These are different checks.
5. Preserve the original commit during the merge and retain its SHA as evidence.
6. Observe the achievement separately; a linked author does not expose the
   achievement service's internal eligibility decision or processing status.

GitHub-provided noreply addresses are also documented for commit attribution.
An address missing from the email-list API response is not, by itself, proof
that a noreply address is invalid. A comparison with a verified public address
can remove that uncertainty from a specific test.

References:
- https://docs.github.com/en/pull-requests/how-tos/commit-changes/creating-a-commit-with-multiple-authors
- https://docs.github.com/en/rest/users/emails

Keep email API responses local. Never publish tokens or private addresses as
part of the diagnostic record.
