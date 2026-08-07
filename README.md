# imgli for LazyCat

[imgli](https://github.com/yixian-huang/imgli) is a self-hosted image hosting service.

## Deployment

- **Public Base URL** is optional. Leave it empty to use the LazyCat-assigned
  application domain. To use a custom domain, bind it in LazyCat first and
  enter the exact HTTPS origin (for example, `https://img.example.com`).
- imgli stores its SQLite database and local image objects under
  `/lzcapp/var/data`.
- The first account registered in imgli becomes its administrator.

This package routes its full public path (`/`) to imgli.

## Automation

The scheduled GitHub Actions workflow tracks stable upstream image versions
through `ghcr.1ms.run`, builds a versioned GitHub Release asset, and publishes
only to the MiaoMiao private store.

Required GitHub Secrets: `APPSTORE_URL` and `APPSTORE_TOKEN`. Optional secrets:
`APP_ID` and `PRIVATE_STORE_GROUP_CODES`.
