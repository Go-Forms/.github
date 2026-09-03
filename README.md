# Go-Forms organisation profile

`profile/README.md` is what GitHub renders at the top of
<https://github.com/Go-Forms>.

GitHub only looks for it in a repository named exactly `.github`, owned by the
organisation. Nothing else about the repository matters — not its description,
not its default branch's name — but that one name does, so if this repository
is still called `org-profile`, the profile page is not being served from it
yet. Renaming it is enough; see below.

## Renaming this repository to `.github`

1. <https://github.com/Go-Forms/org-profile/settings> → **General** → the
   **Repository name** field at the top.
2. Replace `org-profile` with `.github` and press **Rename**.
3. The repository must be **public**. A private one is valid, but GitHub
   will not render a profile from it.

GitHub redirects the old name, so an existing clone keeps working. Point it at
the new name anyway, so the remote says what it is:

    git remote set-url origin git@github.com:Go-Forms/.github.git

## Editing the profile

Edit `profile/README.md` and push. GitHub picks the change up on its own —
there is no build step and nothing to enable.

Relative links do not resolve on a profile page the way they do in a normal
README, so every link in it is absolute.

## What else can live here

A `.github` repository is also where organisation-wide defaults go, if you
ever want them: `.github/ISSUE_TEMPLATE/`, `.github/PULL_REQUEST_TEMPLATE.md`,
`CONTRIBUTING.md`, `SECURITY.md` and `CODE_OF_CONDUCT.md` here apply to every
repository in the organisation that does not define its own.
