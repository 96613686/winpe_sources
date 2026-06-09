# GetEventIdString(ulong)

- ea: `0x180154bc0`
- end: `0x180155245`
- name: `?GetEventIdString@@YAPEB_WK@Z`
- size: `1669`
- prototype: `const wchar_t *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180087174`
- `0x1801687dc`

## callees

- `0x180154bc0`

## string_xrefs

- `0x180154e8a`: `AGENT_INSTALL_POSTREBOOT_SUCCEEDED`
- `0x180154c58`: `AGENT_DETECTION_FINISHED`
- `0x180154cad`: `AGENT_DETECTION_FAILED`
- `0x180154c95`: `AGENT_INVALID_PID`
- `0x180154c8d`: `AGENT_UPDATE_DETECTED`
- `0x180154c9d`: `AGENT_STATUS`
- `0x180154cb5`: `AGENT_DOWNLOAD_FAILED`
- `0x180154d15`: `AGENT_DOWNLOAD_SUCCEEDED`
- `0x180154c85`: `AGENT_STATUS_30`
- `0x180154ced`: `AGENT_DOWNLOAD_STARTED`
- `0x180154cf5`: `AGENT_DOWNLOAD_RESUMED`
- `0x180154d05`: `AGENT_DOWNLOAD_SUCCEEDED_FROM_PEER`
- `0x180154d0d`: `AGENT_DOWNLOAD_CANCELED`
- `0x180154cfd`: `AGENT_DOWNLOAD_SUSPENDED`
- `0x180154d6a`: `AGENT_PREDOWNLOAD_FAILED`
- `0x180154d62`: `AGENT_PREDOWNLOAD_SUCCEEDED`
- `0x180154d1d`: `AGENT_DOWNLOAD_PROGRESS`
- `0x180154d72`: `AGENT_PREDOWNLOAD_STARTED`
- `0x180154d4a`: `AGENT_INSTALLING_FAILED`
- `0x180154d7a`: `AGENT_INSTALLING_SUCCEEDED`
- `0x180154d5a`: `AGENT_PREDOWNLOAD_CANCELED`
- `0x180154d52`: `AGENT_INSTALLING_STARTED`
- `0x180154ddd`: `AGENT_INSTALL_CANCEL`
- `0x180154dd5`: `AGENT_INSTALL_KILLED`
- `0x180154ded`: `AGENT_INSTALL_COMPLETE_WITH_REBOOT`
- `0x180154de5`: `AGENT_INSTALL_HIDE`
- `0x180154df5`: `AU_SCHEDULED_INSTALL_SUCCESS`
- `0x180154e4a`: `AU_SCHEDULED_INSTALL_COMPLETE_WITH_REBOOT`
- `0x180154dcd`: `AU_SCHEDULED_INSTALL_READY`
- `0x180154dc5`: `AU_UNSCHEDULED_INSTALL_READY`
- `0x180154e32`: `AU_SCHEDULED_REBOOT_REQUIRED`
- `0x180154e2a`: `AU_SCHEDULED_INSTALL_FAILED`
- `0x180154e42`: `AU_SCHEDULED_INSTALL_KILLED`
- `0x180154e3a`: `AU_UNSCHEDULED_REBOOT_REQUIRED`
- `0x180154eb2`: `AU_SHUTDOWN_INSTALL_FAILED`
- `0x180154eaa`: `AU_SHUTDOWN_INSTALL_COMPLETE_WITH_REBOOT`
- `0x180154e22`: `AGENT_INSTALL_UNHIDE`
- `0x180154e52`: `AU_SHUTDOWN_INSTALL_SUCCESS`
- `0x180154e92`: `AU_REBOOT_COMPLETED`
- `0x180154eba`: `AGENT_INSTALLING_FAILED_POST_REBOOT`
- `0x180154ea2`: `AU_SHUTDOWN_INSTALL_KILLED`
- `0x180154e9a`: `AGENT_INSTALLING_PENDING`
- `0x180154efa`: `AGENT_UNINSTALLING_SUCCEEDED`
- `0x180154ef2`: `AGENT_UNINSTALL_CANCEL`
- `0x180154f0a`: `AGENT_UNINSTALL_STARTED`
- `0x180154f02`: `AGENT_UNINSTALLING_FAILED`
- `0x18015521d`: `AGENT_REVERT_STARTED`
- `0x1801551f9`: `AGENT_REVERT_FAILED`
- `0x180154eea`: `AGENT_UNINSTALL_COMPLETE_WITH_REBOOT`
- `0x180154ee2`: `AGENT_UNINSTALL_KILLED`
- `0x18015522d`: `AGENT_REVERT_COMPLETE_WITH_REBOOT`
- `0x180155225`: `AGENT_REVERT_KILLED`
- `0x18015523d`: `AGENT_REVERT_SUCCEEDED`
- `0x180155235`: `AGENT_REVERT_CANCEL`
- `0x1801551d9`: `AGENT_COMMIT_SUCCEEDED`
- `0x1801551d1`: `AGENT_COMMIT_CANCEL`
- `0x1801551e9`: `AGENT_COMMIT_STARTED`
- `0x1801551e1`: `AGENT_COMMIT_FAILED`
- `0x1801551c9`: `AGENT_COMMIT_KILLED`
- `0x180154ff5`: `WindowsUpdate_Engine_ScanStart`
- `0x180155055`: `WindowsUpdate_Engine_ScanStop_Success`
- `0x18015503d`: `WindowsUpdate_Engine_InstallStart`
- `0x180155035`: `WindowsUpdate_Engine_InstallStop_Success`
- `0x18015504d`: `WindowsUpdate_Engine_DownloadStart`
- `0x180155045`: `WindowsUpdate_Engine_DownloadStop_Success`
- `0x1801550b2`: `WindowsUpdate_Engine_DownloadStop_Failure`
- `0x1801550aa`: `WindowsUpdate_Engine_DownloadStop_Cancel`
- `0x18015502d`: `WindowsUpdate_Engine_ScanStop_Failure`
- `0x18015505d`: `WindowsUpdate_Engine_ScanStop_Cancel`
- `0x180155092`: `WindowsUpdate_Engine_ServiceStartupStart`
- `0x18015508a`: `WindowsUpdate_Engine_ServiceStartupStop`
- `0x1801550a2`: `WindowsUpdate_Engine_InstallStop_Failure`
- `0x18015509a`: `WindowsUpdate_Engine_InstallStop_Cancel`
- `0x180155128`: `WindowsUpdate_Engine_DownloadStop_Invalid`
- `0x180155120`: `WindowsUpdate_Engine_DriverScanStart`
- `0x1801550ba`: `WindowsUpdate_Engine_ServiceShutdownStart`
- `0x180155130`: `WindowsUpdate_Engine_ServiceShutdownStop`
- `0x180155108`: `WindowsUpdate_Engine_DriverInstallStart`
- `0x180155138`: `WindowsUpdate_Engine_DriverInstallStop_Success`
- `0x180155118`: `WindowsUpdate_Engine_DriverScanStop_Success`
- `0x180155110`: `WindowsUpdate_Engine_DriverScanStop_Failure`
- `0x18015517d`: `WindowsUpdate_Engine_QueueScanEnd`
- `0x180155175`: `WindowsUpdate_Engine_SyncUpdatesStart`
- `0x18015518d`: `WindowsUpdate_Engine_DriverInstallStop_Failure`
- `0x180155185`: `WindowsUpdate_Engine_QueueScanStart`
- `0x180155195`: `WindowsUpdate_Engine_AppScanStop_Success`
- `0x1801551f1`: `WindowsUpdate_Engine_AppScanStop_Failure`
- `0x18015516d`: `WindowsUpdate_Engine_SyncUpdatesEnd`
- `0x180155165`: `WindowsUpdate_Engine_AppScanStart`
- `0x180154fed`: `AGENT_SERVICE_STOP`
- `0x180154fe5`: `AGENT_SERVICE_SHUTDOWN`
- `0x180154f68`: `AGENT_CONNECTIVITY_LOST`
- `0x180154f98`: `AGENT_CONNECTIVITY_GAINED`
- `0x180154fcd`: `SELFUPDATE_CORE_SUCCEEDED`
- `0x180154fc5`: `SELFUPDATE_AUX_SUCCEEDED`
- `0x180154fdd`: `SELFUPDATE_CORE_FAILED`
- `0x180154fd5`: `SELFUPDATE_AUX_FAILED`

## pseudocode

```c
const wchar_t *__fastcall GetEventIdString(unsigned int a1)
{
  const wchar_t *result; // rax
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx

  result = 0;
  if ( a1 > 0xE2 )
  {
    if ( a1 > 0x127 )
    {
      if ( a1 > 0x1FF )
      {
        if ( a1 > 0x21D )
        {
          v76 = a1 - 542;
          if ( v76 )
          {
            v77 = v76 - 1;
            if ( v77 )
            {
              v78 = v77 - 1;
              if ( v78 )
              {
                v79 = v78 - 1;
                if ( v79 )
                {
                  if ( v79 == 1 )
                    return L"AGENT_REVERT_STARTED";
                }
                else
                {
                  return L"AGENT_REVERT_KILLED";
                }
              }
              else
              {
                return L"AGENT_REVERT_COMPLETE_WITH_REBOOT";
              }
            }
            else
            {
              return L"AGENT_REVERT_CANCEL";
            }
          }
          else
          {
            return L"AGENT_REVERT_SUCCEEDED";
          }
        }
        else if ( a1 == 541 )
        {
          return L"AGENT_REVERT_FAILED";
        }
        else
        {
          v71 = a1 - 512;
          if ( v71 )
          {
            v72 = v71 - 9;
            if ( v72 )
            {
              v73 = v72 - 1;
              if ( v73 )
              {
                v74 = v73 - 1;
                if ( v74 )
                {
                  v75 = v74 - 1;
                  if ( v75 )
                  {
                    if ( v75 == 1 )
                      return L"AGENT_COMMIT_KILLED";
                  }
                  else
                  {
                    return L"AGENT_COMMIT_CANCEL";
                  }
                }
                else
                {
                  return L"AGENT_COMMIT_SUCCEEDED";
                }
              }
              else
              {
                return L"AGENT_COMMIT_FAILED";
              }
            }
            else
            {
              return L"AGENT_COMMIT_STARTED";
            }
          }
          else
          {
            return L"WindowsUpdate_Engine_AppScanStop_Failure";
          }
        }
      }
      else if ( a1 == 511 )
      {
        return L"WindowsUpdate_Engine_AppScanStop_Success";
      }
      else if ( a1 > 0x1F8 )
      {
        v66 = a1 - 505;
        if ( v66 )
        {
          v67 = v66 - 1;
          if ( v67 )
          {
            v68 = v67 - 1;
            if ( v68 )
            {
              v69 = v68 - 1;
              if ( v69 )
              {
                v70 = v69 - 1;
                if ( v70 )
                {
                  if ( v70 == 1 )
                    return L"WindowsUpdate_Engine_AppScanStart";
                }
                else
                {
                  return L"WindowsUpdate_Engine_SyncUpdatesEnd";
                }
              }
              else
              {
                return L"WindowsUpdate_Engine_SyncUpdatesStart";
              }
            }
            else
            {
              return L"WindowsUpdate_Engine_QueueScanEnd";
            }
          }
          else
          {
            return L"WindowsUpdate_Engine_QueueScanStart";
          }
        }
        else
        {
          return L"WindowsUpdate_Engine_DriverInstallStop_Failure";
        }
      }
      else if ( a1 == 504 )
      {
        return L"WindowsUpdate_Engine_DriverInstallStop_Success";
      }
      else
      {
        v61 = a1 - 296;
        if ( v61 )
        {
          v62 = v61 - 2;
          if ( v62 )
          {
            v63 = v62 - 1;
            if ( v63 )
            {
              v64 = v63 - 202;
              if ( v64 )
              {
                v65 = v64 - 1;
                if ( v65 )
                {
                  if ( v65 == 1 )
                    return L"WindowsUpdate_Engine_DriverInstallStart";
                }
                else
                {
                  return L"WindowsUpdate_Engine_DriverScanStop_Failure";
                }
              }
              else
              {
                return L"WindowsUpdate_Engine_DriverScanStop_Success";
              }
            }
            else
            {
              return L"WindowsUpdate_Engine_DriverScanStart";
            }
          }
          else
          {
            return L"WindowsUpdate_Engine_DownloadStop_Invalid";
          }
        }
        else
        {
          return L"WindowsUpdate_Engine_ServiceShutdownStop";
        }
      }
    }
    else if ( a1 == 295 )
    {
      return L"WindowsUpdate_Engine_ServiceShutdownStart";
    }
    else if ( a1 > 0x119 )
    {
      if ( a1 > 0x120 )
      {
        v56 = a1 - 289;
        if ( v56 )
        {
          v57 = v56 - 1;
          if ( v57 )
          {
            v58 = v57 - 1;
            if ( v58 )
            {
              v59 = v58 - 1;
              if ( v59 )
              {
                v60 = v59 - 1;
                if ( v60 )
                {
                  if ( v60 == 1 )
                    return L"WindowsUpdate_Engine_ServiceStartupStop";
                }
                else
                {
                  return L"WindowsUpdate_Engine_ServiceStartupStart";
                }
              }
              else
              {
                return L"WindowsUpdate_Engine_InstallStop_Cancel";
              }
            }
            else
            {
              return L"WindowsUpdate_Engine_InstallStop_Failure";
            }
          }
          else
          {
            return L"WindowsUpdate_Engine_DownloadStop_Cancel";
          }
        }
        else
        {
          return L"WindowsUpdate_Engine_DownloadStop_Failure";
        }
      }
      else if ( a1 == 288 )
      {
        return L"WindowsUpdate_Engine_ScanStop_Cancel";
      }
      else
      {
        v51 = a1 - 282;
        if ( v51 )
        {
          v52 = v51 - 1;
          if ( v52 )
          {
            v53 = v52 - 1;
            if ( v53 )
            {
              v54 = v53 - 1;
              if ( v54 )
              {
                v55 = v54 - 1;
                if ( v55 )
                {
                  if ( v55 == 1 )
                    return L"WindowsUpdate_Engine_ScanStop_Failure";
                }
                else
                {
                  return L"WindowsUpdate_Engine_InstallStop_Success";
                }
              }
              else
              {
                return L"WindowsUpdate_Engine_InstallStart";
              }
            }
            else
            {
              return L"WindowsUpdate_Engine_DownloadStop_Success";
            }
          }
          else
          {
            return L"WindowsUpdate_Engine_DownloadStart";
          }
        }
        else
        {
          return L"WindowsUpdate_Engine_ScanStop_Success";
        }
      }
    }
    else if ( a1 == 281 )
    {
      return L"WindowsUpdate_Engine_ScanStart";
    }
    else if ( a1 > 0xFC )
    {
      v46 = a1 - 253;
      if ( v46 )
      {
        v47 = v46 - 1;
        if ( v47 )
        {
          v48 = v47 - 17;
          if ( v48 )
          {
            v49 = v48 - 1;
            if ( v49 )
            {
              v50 = v49 - 1;
              if ( v50 )
              {
                if ( v50 == 1 )
                  return L"SELFUPDATE_AUX_SUCCEEDED";
              }
              else
              {
                return L"SELFUPDATE_CORE_SUCCEEDED";
              }
            }
            else
            {
              return L"SELFUPDATE_AUX_FAILED";
            }
          }
          else
          {
            return L"SELFUPDATE_CORE_FAILED";
          }
        }
        else
        {
          return L"AGENT_SERVICE_SHUTDOWN";
        }
      }
      else
      {
        return L"AGENT_SERVICE_STOP";
      }
    }
    else if ( a1 == 252 )
    {
      return L"AGENT_CONNECTIVITY_GAINED";
    }
    else
    {
      v41 = a1 - 241;
      if ( v41 )
      {
        v42 = v41 - 1;
        if ( v42 )
        {
          v43 = v42 - 1;
          if ( v43 )
          {
            v44 = v43 - 1;
            if ( v44 )
            {
              v45 = v44 - 1;
              if ( v45 )
              {
                if ( v45 == 6 )
                  return L"AGENT_CONNECTIVITY_LOST";
              }
              else
              {
                return L"AU_HEALTH_CHANGED";
              }
            }
            else
            {
              return L"PROXY_AUTH_REQUIRED";
            }
          }
          else
          {
            return L"CHECK_CONNECTION";
          }
        }
        else
        {
          return L"AU_RESUMED";
        }
      }
      else
      {
        return L"AU_PAUSED";
      }
    }
  }
  else if ( a1 == 226 )
  {
    return L"AGENT_UNINSTALL_STARTED";
  }
  else if ( a1 > 0xB7 )
  {
    if ( a1 > 0xC5 )
    {
      if ( a1 > 0xCC )
      {
        v37 = a1 - 221;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( v39 )
            {
              v40 = v39 - 1;
              if ( v40 )
              {
                if ( v40 == 1 )
                  return L"AGENT_UNINSTALL_KILLED";
              }
              else
              {
                return L"AGENT_UNINSTALL_COMPLETE_WITH_REBOOT";
              }
            }
            else
            {
              return L"AGENT_UNINSTALL_CANCEL";
            }
          }
          else
          {
            return L"AGENT_UNINSTALLING_SUCCEEDED";
          }
        }
        else
        {
          return L"AGENT_UNINSTALLING_FAILED";
        }
      }
      else if ( a1 == 204 )
      {
        return L"AGENT_INSTALLING_FAILED_POST_REBOOT";
      }
      else
      {
        v32 = a1 - 198;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            v34 = v33 - 1;
            if ( v34 )
            {
              v35 = v34 - 1;
              if ( v35 )
              {
                v36 = v35 - 1;
                if ( v36 )
                {
                  if ( v36 == 1 )
                    return L"AGENT_INSTALL_POSTREBOOT_SUCCEEDED";
                }
                else
                {
                  return L"AU_REBOOT_COMPLETED";
                }
              }
              else
              {
                return L"AGENT_INSTALLING_PENDING";
              }
            }
            else
            {
              return L"AU_SHUTDOWN_INSTALL_KILLED";
            }
          }
          else
          {
            return L"AU_SHUTDOWN_INSTALL_COMPLETE_WITH_REBOOT";
          }
        }
        else
        {
          return L"AU_SHUTDOWN_INSTALL_FAILED";
        }
      }
    }
    else if ( a1 == 197 )
    {
      return L"AU_SHUTDOWN_INSTALL_SUCCESS";
    }
    else if ( a1 > 0xBE )
    {
      v27 = a1 - 191;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                if ( v31 == 1 )
                  return L"AGENT_INSTALL_UNHIDE";
              }
              else
              {
                return L"AU_SCHEDULED_INSTALL_FAILED";
              }
            }
            else
            {
              return L"AU_SCHEDULED_REBOOT_REQUIRED";
            }
          }
          else
          {
            return L"AU_UNSCHEDULED_REBOOT_REQUIRED";
          }
        }
        else
        {
          return L"AU_SCHEDULED_INSTALL_KILLED";
        }
      }
      else
      {
        return L"AU_SCHEDULED_INSTALL_COMPLETE_WITH_REBOOT";
      }
    }
    else if ( a1 == 190 )
    {
      return L"AU_SCHEDULED_INSTALL_SUCCESS";
    }
    else
    {
      v22 = a1 - 184;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                if ( v26 == 1 )
                  return L"AU_UNSCHEDULED_INSTALL_READY";
              }
              else
              {
                return L"AU_SCHEDULED_INSTALL_READY";
              }
            }
            else
            {
              return L"AGENT_INSTALL_KILLED";
            }
          }
          else
          {
            return L"AGENT_INSTALL_CANCEL";
          }
        }
        else
        {
          return L"AGENT_INSTALL_HIDE";
        }
      }
      else
      {
        return L"AGENT_INSTALL_COMPLETE_WITH_REBOOT";
      }
    }
  }
  else if ( a1 == 183 )
  {
    return L"AGENT_INSTALLING_SUCCEEDED";
  }
  else if ( a1 > 0xA1 )
  {
    if ( a1 > 0xAA )
    {
      v17 = a1 - 171;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              v21 = v20 - 7;
              if ( v21 )
              {
                if ( v21 == 1 )
                  return L"AGENT_INSTALLING_FAILED";
              }
              else
              {
                return L"AGENT_INSTALLING_STARTED";
              }
            }
            else
            {
              return L"AGENT_PREDOWNLOAD_CANCELED";
            }
          }
          else
          {
            return L"AGENT_PREDOWNLOAD_SUCCEEDED";
          }
        }
        else
        {
          return L"AGENT_PREDOWNLOAD_FAILED";
        }
      }
      else
      {
        return L"AGENT_PREDOWNLOAD_STARTED";
      }
    }
    else if ( a1 == 170 )
    {
      return L"AGENT_DOWNLOAD_PROGRESS";
    }
    else
    {
      v12 = a1 - 162;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 == 1 )
                  return L"AGENT_DOWNLOAD_STARTED";
              }
              else
              {
                return L"AGENT_DOWNLOAD_RESUMED";
              }
            }
            else
            {
              return L"AGENT_DOWNLOAD_SUSPENDED";
            }
          }
          else
          {
            return L"AGENT_DOWNLOAD_SUCCEEDED_FROM_PEER";
          }
        }
        else
        {
          return L"AGENT_DOWNLOAD_CANCELED";
        }
      }
      else
      {
        return L"AGENT_DOWNLOAD_SUCCEEDED";
      }
    }
  }
  else if ( a1 == 161 )
  {
    return L"AGENT_DOWNLOAD_FAILED";
  }
  else if ( a1 > 0x93 )
  {
    v7 = a1 - 148;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 4;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 1 )
                return L"AGENT_STATUS_30";
            }
            else
            {
              return L"AGENT_UPDATE_DETECTED";
            }
          }
          else
          {
            return L"AGENT_INVALID_PID";
          }
        }
        else
        {
          return L"AGENT_STATUS";
        }
      }
      else
      {
        return L"AU_UNABLE_TO_CONNECT";
      }
    }
    else
    {
      return L"AGENT_DETECTION_FAILED";
    }
  }
  else if ( a1 == 147 )
  {
    return L"AGENT_DETECTION_FINISHED";
  }
  else
  {
    v2 = a1 - 121;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              if ( v6 == 1 )
                return L"INVENTORY_COLLECTION_SUCCESS";
            }
            else
            {
              return L"INVENTORY_OPERATIONAL_FAILURE";
            }
          }
          else
          {
            return L"INVENTORY_UPLOAD_FAILED";
          }
        }
        else
        {
          return L"INVENTORY_COLLECTION_FAILED";
        }
      }
      else
      {
        return L"INVENTORY_RULES_PROCESSING_FAILED";
      }
    }
    else
    {
      return L"INVENTORY_RULES_DOWNLOAD_FAILED";
    }
  }
  return result;
}

```

## disassembly

```asm
0x180154bc0  xor     eax, eax
0x180154bc2  mov     edx, 0E2h
0x180154bc7  cmp     ecx, edx
0x180154bc9  ja      loc_180154F12
0x180154bcf  jz      loc_180154F0A
0x180154bd5  mov     edx, 0B7h
0x180154bda  cmp     ecx, edx
0x180154bdc  ja      loc_180154D82
0x180154be2  jz      loc_180154D7A
0x180154be8  mov     edx, 0A1h
0x180154bed  cmp     ecx, edx
0x180154bef  ja      loc_180154CBD
0x180154bf5  jz      loc_180154CB5
0x180154bfb  mov     edx, 93h
0x180154c00  cmp     ecx, edx
0x180154c02  ja      short loc_180154C60
0x180154c04  jz      short loc_180154C58
0x180154c06  sub     ecx, 79h ; 'y'
0x180154c09  jz      short loc_180154C50
0x180154c0b  sub     ecx, 1
0x180154c0e  jz      short loc_180154C48
0x180154c10  sub     ecx, 1
0x180154c13  jz      short loc_180154C40
0x180154c15  sub     ecx, 1
0x180154c18  jz      short loc_180154C38
0x180154c1a  sub     ecx, 1
0x180154c1d  jz      short loc_180154C30
0x180154c1f  cmp     ecx, 1
0x180154c22  jnz     locret_180155244
0x180154c28  lea     rax, aInventoryColle; "INVENTORY_COLLECTION_SUCCESS"
0x180154c2f  retn
0x180154c30  lea     rax, aInventoryOpera; "INVENTORY_OPERATIONAL_FAILURE"
0x180154c37  retn
0x180154c38  lea     rax, aInventoryUploa; "INVENTORY_UPLOAD_FAILED"
0x180154c3f  retn
0x180154c40  lea     rax, aInventoryColle_1; "INVENTORY_COLLECTION_FAILED"
0x180154c47  retn
0x180154c48  lea     rax, aInventoryRules; "INVENTORY_RULES_PROCESSING_FAILED"
0x180154c4f  retn
0x180154c50  lea     rax, aInventoryRules_0; "INVENTORY_RULES_DOWNLOAD_FAILED"
0x180154c57  retn
0x180154c58  lea     rax, aAgentDetection; "AGENT_DETECTION_FINISHED"
0x180154c5f  retn
0x180154c60  sub     ecx, 94h
0x180154c66  jz      short loc_180154CAD
0x180154c68  sub     ecx, 1
0x180154c6b  jz      short loc_180154CA5
0x180154c6d  sub     ecx, 4
0x180154c70  jz      short loc_180154C9D
0x180154c72  sub     ecx, 1
0x180154c75  jz      short loc_180154C95
0x180154c77  sub     ecx, 1
0x180154c7a  jz      short loc_180154C8D
0x180154c7c  cmp     ecx, 1
0x180154c7f  jnz     locret_180155244
0x180154c85  lea     rax, aAgentStatus30; "AGENT_STATUS_30"
0x180154c8c  retn
0x180154c8d  lea     rax, aAgentUpdateDet; "AGENT_UPDATE_DETECTED"
0x180154c94  retn
0x180154c95  lea     rax, aAgentInvalidPi; "AGENT_INVALID_PID"
0x180154c9c  retn
0x180154c9d  lea     rax, aAgentStatus; "AGENT_STATUS"
0x180154ca4  retn
0x180154ca5  lea     rax, aAuUnableToConn; "AU_UNABLE_TO_CONNECT"
0x180154cac  retn
0x180154cad  lea     rax, aAgentDetection_0; "AGENT_DETECTION_FAILED"
0x180154cb4  retn
0x180154cb5  lea     rax, aAgentDownloadF; "AGENT_DOWNLOAD_FAILED"
0x180154cbc  retn
0x180154cbd  mov     edx, 0AAh
0x180154cc2  cmp     ecx, edx
0x180154cc4  ja      short loc_180154D25
0x180154cc6  jz      short loc_180154D1D
0x180154cc8  sub     ecx, 0A2h
0x180154cce  jz      short loc_180154D15
0x180154cd0  sub     ecx, 1
0x180154cd3  jz      short loc_180154D0D
0x180154cd5  sub     ecx, 1
0x180154cd8  jz      short loc_180154D05
0x180154cda  sub     ecx, 1
0x180154cdd  jz      short loc_180154CFD
0x180154cdf  sub     ecx, 1
0x180154ce2  jz      short loc_180154CF5
0x180154ce4  cmp     ecx, 1
0x180154ce7  jnz     locret_180155244
0x180154ced  lea     rax, aAgentDownloadS_1; "AGENT_DOWNLOAD_STARTED"
0x180154cf4  retn
0x180154cf5  lea     rax, aAgentDownloadR; "AGENT_DOWNLOAD_RESUMED"
0x180154cfc  retn
0x180154cfd  lea     rax, aAgentDownloadS_2; "AGENT_DOWNLOAD_SUSPENDED"
0x180154d04  retn
0x180154d05  lea     rax, aAgentDownloadS; "AGENT_DOWNLOAD_SUCCEEDED_FROM_PEER"
0x180154d0c  retn
0x180154d0d  lea     rax, aAgentDownloadC; "AGENT_DOWNLOAD_CANCELED"
0x180154d14  retn
0x180154d15  lea     rax, aAgentDownloadS_0; "AGENT_DOWNLOAD_SUCCEEDED"
0x180154d1c  retn
0x180154d1d  lea     rax, aAgentDownloadP; "AGENT_DOWNLOAD_PROGRESS"
0x180154d24  retn
0x180154d25  sub     ecx, 0ABh
0x180154d2b  jz      short loc_180154D72
0x180154d2d  sub     ecx, 1
0x180154d30  jz      short loc_180154D6A
0x180154d32  sub     ecx, 1
0x180154d35  jz      short loc_180154D62
0x180154d37  sub     ecx, 1
0x180154d3a  jz      short loc_180154D5A
0x180154d3c  sub     ecx, 7
0x180154d3f  jz      short loc_180154D52
0x180154d41  cmp     ecx, 1
0x180154d44  jnz     locret_180155244
0x180154d4a  lea     rax, aAgentInstallin_1; "AGENT_INSTALLING_FAILED"
0x180154d51  retn
0x180154d52  lea     rax, aAgentInstallin_0; "AGENT_INSTALLING_STARTED"
0x180154d59  retn
0x180154d5a  lea     rax, aAgentPredownlo_0; "AGENT_PREDOWNLOAD_CANCELED"
0x180154d61  retn
0x180154d62  lea     rax, aAgentPredownlo_1; "AGENT_PREDOWNLOAD_SUCCEEDED"
0x180154d69  retn
0x180154d6a  lea     rax, aAgentPredownlo; "AGENT_PREDOWNLOAD_FAILED"
0x180154d71  retn
0x180154d72  lea     rax, aAgentPredownlo_2; "AGENT_PREDOWNLOAD_STARTED"
0x180154d79  retn
0x180154d7a  lea     rax, aAgentInstallin_3; "AGENT_INSTALLING_SUCCEEDED"
0x180154d81  retn
0x180154d82  mov     edx, 0C5h
0x180154d87  cmp     ecx, edx
0x180154d89  ja      loc_180154E5A
0x180154d8f  jz      loc_180154E52
0x180154d95  mov     edx, 0BEh
0x180154d9a  cmp     ecx, edx
0x180154d9c  ja      short loc_180154DFD
0x180154d9e  jz      short loc_180154DF5
0x180154da0  sub     ecx, 0B8h
0x180154da6  jz      short loc_180154DED
0x180154da8  sub     ecx, 1
0x180154dab  jz      short loc_180154DE5
0x180154dad  sub     ecx, 1
0x180154db0  jz      short loc_180154DDD
0x180154db2  sub     ecx, 1
0x180154db5  jz      short loc_180154DD5
0x180154db7  sub     ecx, 1
0x180154dba  jz      short loc_180154DCD
0x180154dbc  cmp     ecx, 1
0x180154dbf  jnz     locret_180155244
0x180154dc5  lea     rax, aAuUnscheduledI; "AU_UNSCHEDULED_INSTALL_READY"
0x180154dcc  retn
0x180154dcd  lea     rax, aAuScheduledIns_0; "AU_SCHEDULED_INSTALL_READY"
0x180154dd4  retn
0x180154dd5  lea     rax, aAgentInstallKi; "AGENT_INSTALL_KILLED"
0x180154ddc  retn
0x180154ddd  lea     rax, aAgentInstallCa; "AGENT_INSTALL_CANCEL"
0x180154de4  retn
0x180154de5  lea     rax, aAgentInstallHi; "AGENT_INSTALL_HIDE"
0x180154dec  retn
0x180154ded  lea     rax, aAgentInstallCo; "AGENT_INSTALL_COMPLETE_WITH_REBOOT"
0x180154df4  retn
0x180154df5  lea     rax, aAuScheduledIns_1; "AU_SCHEDULED_INSTALL_SUCCESS"
0x180154dfc  retn
0x180154dfd  sub     ecx, 0BFh
0x180154e03  jz      short loc_180154E4A
0x180154e05  sub     ecx, 1
0x180154e08  jz      short loc_180154E42
0x180154e0a  sub     ecx, 1
0x180154e0d  jz      short loc_180154E3A
0x180154e0f  sub     ecx, 1
0x180154e12  jz      short loc_180154E32
0x180154e14  sub     ecx, 1
0x180154e17  jz      short loc_180154E2A
0x180154e19  cmp     ecx, 1
0x180154e1c  jnz     locret_180155244
0x180154e22  lea     rax, aAgentInstallUn; "AGENT_INSTALL_UNHIDE"
0x180154e29  retn
0x180154e2a  lea     rax, aAuScheduledIns; "AU_SCHEDULED_INSTALL_FAILED"
0x180154e31  retn
0x180154e32  lea     rax, aAuScheduledReb; "AU_SCHEDULED_REBOOT_REQUIRED"
0x180154e39  retn
0x180154e3a  lea     rax, aAuUnscheduledR; "AU_UNSCHEDULED_REBOOT_REQUIRED"
0x180154e41  retn
0x180154e42  lea     rax, aAuScheduledIns_3; "AU_SCHEDULED_INSTALL_KILLED"
0x180154e49  retn
0x180154e4a  lea     rax, aAuScheduledIns_2; "AU_SCHEDULED_INSTALL_COMPLETE_WITH_REBO"...
0x180154e51  retn
0x180154e52  lea     rax, aAuShutdownInst_1; "AU_SHUTDOWN_INSTALL_SUCCESS"
0x180154e59  retn
0x180154e5a  mov     edx, 0CCh
0x180154e5f  cmp     ecx, edx
0x180154e61  ja      short loc_180154EC2
0x180154e63  jz      short loc_180154EBA
0x180154e65  sub     ecx, 0C6h
0x180154e6b  jz      short loc_180154EB2
0x180154e6d  sub     ecx, 1
0x180154e70  jz      short loc_180154EAA
0x180154e72  sub     ecx, 1
0x180154e75  jz      short loc_180154EA2
0x180154e77  sub     ecx, 1
0x180154e7a  jz      short loc_180154E9A
0x180154e7c  sub     ecx, 1
0x180154e7f  jz      short loc_180154E92
0x180154e81  cmp     ecx, 1
0x180154e84  jnz     locret_180155244
0x180154e8a  lea     rax, aAgentInstallPo; "AGENT_INSTALL_POSTREBOOT_SUCCEEDED"
0x180154e91  retn
0x180154e92  lea     rax, aAuRebootComple; "AU_REBOOT_COMPLETED"
0x180154e99  retn
0x180154e9a  lea     rax, aAgentInstallin; "AGENT_INSTALLING_PENDING"
0x180154ea1  retn
0x180154ea2  lea     rax, aAuShutdownInst_0; "AU_SHUTDOWN_INSTALL_KILLED"
0x180154ea9  retn
0x180154eaa  lea     rax, aAuShutdownInst_2; "AU_SHUTDOWN_INSTALL_COMPLETE_WITH_REBOO"...
0x180154eb1  retn
0x180154eb2  lea     rax, aAuShutdownInst; "AU_SHUTDOWN_INSTALL_FAILED"
0x180154eb9  retn
0x180154eba  lea     rax, aAgentInstallin_2; "AGENT_INSTALLING_FAILED_POST_REBOOT"
0x180154ec1  retn
0x180154ec2  sub     ecx, 0DDh
0x180154ec8  jz      short loc_180154F02
0x180154eca  sub     ecx, 1
0x180154ecd  jz      short loc_180154EFA
0x180154ecf  sub     ecx, 1
0x180154ed2  jz      short loc_180154EF2
0x180154ed4  sub     ecx, 1
0x180154ed7  jz      short loc_180154EEA
0x180154ed9  cmp     ecx, 1
0x180154edc  jnz     locret_180155244
0x180154ee2  lea     rax, aAgentUninstall_1; "AGENT_UNINSTALL_KILLED"
0x180154ee9  retn
0x180154eea  lea     rax, aAgentUninstall; "AGENT_UNINSTALL_COMPLETE_WITH_REBOOT"
0x180154ef1  retn
0x180154ef2  lea     rax, aAgentUninstall_3; "AGENT_UNINSTALL_CANCEL"
0x180154ef9  retn
0x180154efa  lea     rax, aAgentUninstall_0; "AGENT_UNINSTALLING_SUCCEEDED"
0x180154f01  retn
0x180154f02  lea     rax, aAgentUninstall_2; "AGENT_UNINSTALLING_FAILED"
0x180154f09  retn
0x180154f0a  lea     rax, aAgentUninstall_4; "AGENT_UNINSTALL_STARTED"
0x180154f11  retn
0x180154f12  mov     edx, 127h
0x180154f17  cmp     ecx, edx
0x180154f19  ja      loc_1801550C2
0x180154f1f  jz      loc_1801550BA
0x180154f25  mov     edx, 119h
0x180154f2a  cmp     ecx, edx
0x180154f2c  ja      loc_180154FFD
0x180154f32  jz      loc_180154FF5
0x180154f38  mov     edx, 0FCh
0x180154f3d  cmp     ecx, edx
0x180154f3f  ja      short loc_180154FA0
0x180154f41  jz      short loc_180154F98
0x180154f43  sub     ecx, 0F1h
0x180154f49  jz      short loc_180154F90
0x180154f4b  sub     ecx, 1
0x180154f4e  jz      short loc_180154F88
0x180154f50  sub     ecx, 1
0x180154f53  jz      short loc_180154F80
0x180154f55  sub     ecx, 1
0x180154f58  jz      short loc_180154F78
0x180154f5a  sub     ecx, 1
0x180154f5d  jz      short loc_180154F70
0x180154f5f  cmp     ecx, 6
0x180154f62  jnz     locret_180155244
0x180154f68  lea     rax, aAgentConnectiv_0; "AGENT_CONNECTIVITY_LOST"
0x180154f6f  retn
0x180154f70  lea     rax, aAuHealthChange; "AU_HEALTH_CHANGED"
0x180154f77  retn
0x180154f78  lea     rax, aProxyAuthRequi; "PROXY_AUTH_REQUIRED"
0x180154f7f  retn
0x180154f80  lea     rax, aCheckConnectio; "CHECK_CONNECTION"
0x180154f87  retn
0x180154f88  lea     rax, aAuResumed; "AU_RESUMED"
0x180154f8f  retn
0x180154f90  lea     rax, aAuPaused; "AU_PAUSED"
0x180154f97  retn
0x180154f98  lea     rax, aAgentConnectiv; "AGENT_CONNECTIVITY_GAINED"
0x180154f9f  retn
0x180154fa0  sub     ecx, 0FDh
0x180154fa6  jz      short loc_180154FED
0x180154fa8  sub     ecx, 1
0x180154fab  jz      short loc_180154FE5
0x180154fad  sub     ecx, 11h
0x180154fb0  jz      short loc_180154FDD
0x180154fb2  sub     ecx, 1
0x180154fb5  jz      short loc_180154FD5
0x180154fb7  sub     ecx, 1
0x180154fba  jz      short loc_180154FCD
0x180154fbc  cmp     ecx, 1
0x180154fbf  jnz     locret_180155244
0x180154fc5  lea     rax, aSelfupdateAuxS; "SELFUPDATE_AUX_SUCCEEDED"
0x180154fcc  retn
0x180154fcd  lea     rax, aSelfupdateCore_0; "SELFUPDATE_CORE_SUCCEEDED"
0x180154fd4  retn
0x180154fd5  lea     rax, aSelfupdateAuxF; "SELFUPDATE_AUX_FAILED"
0x180154fdc  retn
0x180154fdd  lea     rax, aSelfupdateCore; "SELFUPDATE_CORE_FAILED"
0x180154fe4  retn
0x180154fe5  lea     rax, aAgentServiceSh; "AGENT_SERVICE_SHUTDOWN"
0x180154fec  retn
0x180154fed  lea     rax, aAgentServiceSt; "AGENT_SERVICE_STOP"
0x180154ff4  retn
0x180154ff5  lea     rax, aWindowsupdateE_11; "WindowsUpdate_Engine_ScanStart"
  ... truncated ...
```
