## Uninstall exisinting installed packages from aem cloud through curl
```
curl -H "Authorization: Bearer <your_ims_access_token>" -X POST https://author-p<prog-name>-e<env-name>.adobeaemcloud.com/crx/packmgr/service/.json/etc/packages/techiearchive.aem/techiearchive-aem.ui.content-0.0.1-SNAPSHOT-cp2fm-converted.zip?cmd=uninstall --ssl-no-revoke
```
