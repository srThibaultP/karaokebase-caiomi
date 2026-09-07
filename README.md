# karaokebase-caiomi

Dedicated Karaoke Mugen repository for home-made karaoke. It is the primary
online repository (`Repositories[0]`) served by the self-hosted KM Server at
**kara.caiomi.moe**, so its name matches that hostname and heavy KM apps that
add `kara.caiomi.moe` get this repo. The kara.moe base is loaded on the same
server as a second, local repository.

## Layout

| dir | contents |
|-----|----------|
| `karaokes/` | `<kid>.kara.json` — KaraFileV4 metadata |
| `lyrics/`   | `<kid>.ass` — timed subtitles |
| `tags/`     | `<name>.<tid8>.tag.json` — tags owned by this repo (`repository: kara.caiomi.moe`) |
| `medias/`   | **git-ignored** — media files live only on the KM Server (`repos/caiomi/medias/<kid>.mp4`) and in personal backups; GitHub's 100 MB/file limit rules them out anyway |

Karas here may reference tags from the kara.moe base by TID (both repos are
loaded into one DB).

## Adding a kara

1. Drop `<kid>.kara.json` + `<kid>.ass` here, push.
2. Put `<kid>.<ext>` in the server's `repos/caiomi/medias/`.
3. On the server: `git -C repos/caiomi/git pull` then `POST /api/generate`,
   then `POST /api/hardsubs/generate`.

## Contents

- `f19ee59a-…` — **Mermaid festa vol.1**, fan cover by Eimi Isami & Runie Ruse
  (original by µ's / Love Live!). Collection: Caiomi.
