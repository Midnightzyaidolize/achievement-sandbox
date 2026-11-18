# Verify a coauthored pull request

This sandbox records controlled tests of GitHub collaboration mechanics.
The API's author attribution and the profile's achievement tier are separate
observations; a local operation count does not certify an achievement award.

## Contributor workflow

1. Create a branch in the contributor's fork of the upstream repository.
2. Include a `Co-authored-by: Name <email>` trailer in the original commit,
   separated from the description by an empty line. Use an email associated
   with the coauthor's GitHub account.
3. Open a pull request from that branch to the upstream default branch.
4. Before merging, inspect the original commit and confirm GitHub links both
   intended author accounts. Record the commit SHA and pull request URL.
5. Merge upstream using a regular merge when testing preservation of the
   original commit. Verify that the source SHA is a parent of the merge commit.
6. Inspect the profile achievement separately. Record the displayed tier and
   observation time without treating attribution as proof of eligibility.

GitHub's documentation describes the commit trailer format:
https://docs.github.com/en/pull-requests/how-tos/commit-changes/creating-a-commit-with-multiple-authors

Do not include access tokens, proxy credentials, or private email addresses in
public diagnostic records. A GitHub-provided noreply address can be used for
commit attribution.
