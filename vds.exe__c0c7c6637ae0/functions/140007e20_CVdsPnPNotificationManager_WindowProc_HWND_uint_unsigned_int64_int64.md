# CVdsPnPNotificationManager::WindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140007e20`
- end: `0x14000835d`
- name: `?WindowProc@CVdsPnPNotificationManager@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1341`
- prototype: `__int64(CVdsPnPNotificationManager *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140007e20`
- `0x140016f9c`
- `0x14004feac`
- `0x14004ff94`
- `0x140050078`
- `0x14005014c`
- `0x1400504f4`

## import_xrefs

- `USER32!DefWindowProcW` at `0x140008356`
- `USER32!PostThreadMessageW` at `0x140008074`
- `USER32!PostThreadMessageW` at `0x140008074`
- `vdsutil!VdsTraceEx` at `0x140007e62`
- `vdsutil!VdsTraceEx` at `0x140007ea4`
- `vdsutil!VdsTraceEx` at `0x140007f88`
- `vdsutil!VdsTraceEx` at `0x140007fd1`
- `vdsutil!VdsTraceEx` at `0x140008022`
- `vdsutil!VdsTraceEx` at `0x1400080bf`
- `vdsutil!VdsTraceEx` at `0x140008100`
- `vdsutil!VdsTraceEx` at `0x140008260`
- `vdsutil!VdsTraceEx` at `0x14000833b`
- `vdsutil!VdsTraceEx` at `0x140007e62`
- `vdsutil!VdsTraceEx` at `0x140007ea4`
- `vdsutil!VdsTraceEx` at `0x140007f88`
- `vdsutil!VdsTraceEx` at `0x140007fd1`
- `vdsutil!VdsTraceEx` at `0x140008022`
- `vdsutil!VdsTraceEx` at `0x1400080bf`
- `vdsutil!VdsTraceEx` at `0x140008100`
- `vdsutil!VdsTraceEx` at `0x140008260`
- `vdsutil!VdsTraceEx` at `0x14000833b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140008039`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140008039`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008080`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008080`

## string_xrefs

- `0x140008130`: `TMP: GUID_IO_VOLUME_DISMOUNT event received.`
- `0x1400080ef`: `VDS(0X0204000D: mount points change notification received.`
- `0x140008182`: `TMP: GUID_IO_VOLUME_MOUNT event received.`
- `0x140008159`: `TMP: GUID_IO_VOLUME_DISMOUNT_FAILED event received.`
- `0x140008028`: `CVdsPnPNotificationManager::LabelMountPointsNotificationHandler()`
- `0x1400082b9`: `TMP: GUID_IO_DEVICE_BECOMING_READY event received.`
- `0x140008226`: `TMP: GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE event received.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LRESULT __fastcall CVdsPnPNotificationManager::WindowProc(
        CVdsPnPNotificationManager *this,
        HWND a2,
        UINT a3,
        unsigned __int64 a4,
        struct _DEV_BROADCAST_HANDLE *a5)
{
  DWORD dbch_devicetype; // eax
  CVdsPnPNotificationManager *v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  const char *v15; // rax
  CVdsPnPNotificationManager *v16; // rcx
  const char *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  UINT v20; // edx
  __int64 v21; // rax
  CVdsPnPNotificationManager *v22; // rcx
  __int64 v23; // rax
  CVdsPnPNotificationManager *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  CVdsPnPNotificationManager *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  const char *v39; // r8
  _BYTE v41[56]; // [rsp+30h] [rbp-38h] BYREF

  if ( a3 == 537 )
  {
    VdsTraceEx(94, 3, "VDS(0X02040002): WM_DEVICECHANGE: wParam=%lX lParam=%ld", a4, (_DWORD)a5);
    if ( a4 == 32774 )
    {
      if ( a5->dbch_devicetype == 6 )
      {
        v18 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_CHANGE.Data1;
        if ( !v18 )
          v18 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_CHANGE.Data4;
        if ( v18 )
        {
          v21 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_DISK_LAYOUT_CHANGE.Data1;
          if ( !v21 )
            v21 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_DISK_LAYOUT_CHANGE.Data4;
          if ( v21 )
          {
            v23 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_NAME_CHANGE.Data1;
            if ( !v23 )
              v23 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_NAME_CHANGE.Data4;
            if ( v23 )
            {
              v25 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1;
              if ( !v25 )
                v25 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4;
              if ( v25 )
              {
                v26 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1;
                if ( !v26 )
                  v26 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT_FAILED.Data4;
                if ( v26 )
                {
                  v27 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
                  if ( !v27 )
                    v27 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
                  if ( v27 )
                  {
                    v28 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1;
                    if ( !v28 )
                      v28 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4;
                    if ( v28 )
                    {
                      v29 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1;
                      if ( !v29 )
                        v29 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_LOCK_FAILED.Data4;
                      if ( v29 )
                      {
                        v30 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1;
                        if ( !v30 )
                          v30 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_UNLOCK.Data4;
                        if ( v30 )
                        {
                          v31 = *(_QWORD *)&a5->dbch_eventguid.Data1
                              - *(_QWORD *)&GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1;
                          if ( !v31 )
                            v31 = *(_QWORD *)a5->dbch_eventguid.Data4
                                - *(_QWORD *)GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data4;
                          if ( v31 )
                          {
                            v32 = *(_QWORD *)&a5->dbch_eventguid.Data1
                                - *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1;
                            if ( !v32 )
                              v32 = *(_QWORD *)a5->dbch_eventguid.Data4
                                  - *(_QWORD *)GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4;
                            if ( v32 )
                            {
                              v34 = *(_QWORD *)&a5->dbch_eventguid.Data1
                                  - *(_QWORD *)&GUID_IO_VOLUME_DEVICE_INTERFACE.Data1;
                              if ( !v34 )
                                v34 = *(_QWORD *)a5->dbch_eventguid.Data4
                                    - *(_QWORD *)GUID_IO_VOLUME_DEVICE_INTERFACE.Data4;
                              if ( v34 )
                              {
                                v35 = *(_QWORD *)&a5->dbch_eventguid.Data1
                                    - *(_QWORD *)&GUID_IO_DEVICE_BECOMING_READY.Data1;
                                if ( !v35 )
                                  v35 = *(_QWORD *)a5->dbch_eventguid.Data4
                                      - *(_QWORD *)GUID_IO_DEVICE_BECOMING_READY.Data4;
                                if ( v35 )
                                {
                                  v36 = *(_QWORD *)&a5->dbch_eventguid.Data1
                                      - *(_QWORD *)&GUID_IO_DEVICE_EXTERNAL_REQUEST.Data1;
                                  if ( !v36 )
                                    v36 = *(_QWORD *)a5->dbch_eventguid.Data4
                                        - *(_QWORD *)GUID_IO_DEVICE_EXTERNAL_REQUEST.Data4;
                                  if ( v36 )
                                  {
                                    v37 = *(_QWORD *)&a5->dbch_eventguid.Data1
                                        - *(_QWORD *)&GUID_IO_MEDIA_EJECT_REQUEST.Data1;
                                    if ( !v37 )
                                      v37 = *(_QWORD *)a5->dbch_eventguid.Data4
                                          - *(_QWORD *)GUID_IO_MEDIA_EJECT_REQUEST.Data4;
                                    if ( v37 )
                                    {
                                      v38 = *(_QWORD *)&a5->dbch_eventguid.Data1
                                          - *(_QWORD *)&GUID_IO_DISK_LAYOUT_CHANGE.Data1;
                                      if ( !v38 )
                                        v38 = *(_QWORD *)a5->dbch_eventguid.Data4
                                            - *(_QWORD *)GUID_IO_DISK_LAYOUT_CHANGE.Data4;
                                      v39 = "TMP: GUID_IO_DISK_LAYOUT_CHANGE event received.";
                                      if ( v38 )
                                        v39 = "TMP: CUSTOM event received.";
                                      VdsTraceEx(94, 2, v39);
                                    }
                                    else
                                    {
                                      VdsTraceEx(94, 2, "TMP: GUID_IO_MEDIA_EJECT_REQUEST event received.");
                                    }
                                  }
                                  else
                                  {
                                    VdsTraceEx(94, 2, "TMP: GUID_IO_DEVICE_EXTERNAL_REQUEST event received.");
                                  }
                                }
                                else
                                {
                                  VdsTraceEx(94, 2, "TMP: GUID_IO_DEVICE_BECOMING_READY event received.");
                                }
                              }
                              else
                              {
                                VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_DEVICE_INTERFACE event received.");
                              }
                            }
                            else
                            {
                              VdsTraceEx(
                                94,
                                2,
                                "VDS(0X02040014: BitLocker full-volume encryption status change notification received.");
                              CVdsPnPNotificationManager::ForwardVolumeChangeNotification(v33, a5);
                            }
                          }
                          else
                          {
                            VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE event received.");
                          }
                        }
                        else
                        {
                          VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_UNLOCK event received.");
                        }
                      }
                      else
                      {
                        VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_LOCK_FAILED event received.");
                      }
                    }
                    else
                    {
                      VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_LOCK event received.");
                    }
                  }
                  else
                  {
                    VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_MOUNT event received.");
                  }
                }
                else
                {
                  VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_DISMOUNT_FAILED event received.");
                }
              }
              else
              {
                VdsTraceEx(94, 2, "TMP: GUID_IO_VOLUME_DISMOUNT event received.");
              }
            }
            else
            {
              VdsTraceEx(94, 2, "VDS(0X0204000D: mount points change notification received.");
              CVdsPnPNotificationManager::ForwardLabelMountPointsNotification(v24, a5);
            }
          }
          else
          {
            VdsTraceEx(94, 2, "VDS(0X02040007): Disk layout change notification received");
            CVdsPnPNotificationManager::ForwardLayoutChangeNotification(v22, a5);
          }
        }
        else
        {
          VdsTraceEx(94, 2, "VDS(0X02040006): Label Change notification received");
          CVdsCallTracer::CVdsCallTracer(
            (CVdsCallTracer *)v41,
            0x5Eu,
            "CVdsPnPNotificationManager::LabelMountPointsNotificationHandler()");
          v19 = *(_QWORD *)&a5->dbch_eventguid.Data1 - *(_QWORD *)&GUID_IO_VOLUME_CHANGE.Data1;
          if ( !v19 )
            v19 = *(_QWORD *)a5->dbch_eventguid.Data4 - *(_QWORD *)GUID_IO_VOLUME_CHANGE.Data4;
          v20 = 1026;
          if ( v19 )
            v20 = 1027;
          PostThreadMessageW(CVdsPnPNotificationManager::m_dwAuxThreadId, v20, 0, (LPARAM)a5->dbch_hdevnotify);
          CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v41);
        }
      }
    }
    else if ( a4 == 0x8000 || a4 == 32772 )
    {
      dbch_devicetype = a5->dbch_devicetype;
      if ( dbch_devicetype == 2 )
      {
        VdsTraceEx(94, 2, "VDS(0X02040003): Drive letter notification received: mask: %X", *(&a5->dbch_reserved + 1));
        if ( ((__int64)a5->dbch_handle & 1) != 0 )
          VdsTraceEx(94, 2, "VDS(0X02040003): Drive letter notification received, DBTF_MEDIA");
        else
          CVdsPnPNotificationManager::DriveLetterNotificationHandler(v10, a4, (struct _DEV_BROADCAST_VOLUME *)a5);
      }
      else if ( dbch_devicetype == 5 )
      {
        v11 = *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1 - *(_QWORD *)(&a5->dbch_reserved + 1);
        if ( *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1 == *(_QWORD *)(&a5->dbch_reserved + 1) )
          v11 = *(_QWORD *)GUID_DEVINTERFACE_VOLUME.Data4 - *(unsigned __int64 *)((char *)&a5->dbch_handle + 4);
        if ( !v11 )
          goto LABEL_25;
        v12 = *(_QWORD *)&GUID_DEVINTERFACE_HIDDEN_VOLUME.Data1 - *(_QWORD *)(&a5->dbch_reserved + 1);
        if ( *(_QWORD *)&GUID_DEVINTERFACE_HIDDEN_VOLUME.Data1 == *(_QWORD *)(&a5->dbch_reserved + 1) )
          v12 = *(_QWORD *)GUID_DEVINTERFACE_HIDDEN_VOLUME.Data4 - *(unsigned __int64 *)((char *)&a5->dbch_handle + 4);
        if ( v12 )
        {
          v13 = *(_QWORD *)&GUID_DEVINTERFACE_DISK.Data1 - *(_QWORD *)(&a5->dbch_reserved + 1);
          if ( *(_QWORD *)&GUID_DEVINTERFACE_DISK.Data1 == *(_QWORD *)(&a5->dbch_reserved + 1) )
            v13 = *(_QWORD *)GUID_DEVINTERFACE_DISK.Data4 - *(unsigned __int64 *)((char *)&a5->dbch_handle + 4);
          if ( !v13 )
            goto LABEL_22;
          v14 = *(_QWORD *)&GUID_DEVINTERFACE_CDROM.Data1 - *(_QWORD *)(&a5->dbch_reserved + 1);
          if ( *(_QWORD *)&GUID_DEVINTERFACE_CDROM.Data1 == *(_QWORD *)(&a5->dbch_reserved + 1) )
            v14 = *(_QWORD *)GUID_DEVINTERFACE_CDROM.Data4 - *(unsigned __int64 *)((char *)&a5->dbch_handle + 4);
          if ( !v14 )
          {
LABEL_22:
            v15 = "arrival";
            if ( a4 != 0x8000 )
              v15 = "removal";
            VdsTraceEx(
              94,
              2,
              "VDS(0X02040005): Disk Notification: %S %s.",
              (const wchar_t *)&a5->dbch_hdevnotify + 2,
              v15);
            CVdsPnPNotificationManager::ForwardDiskNotification(v16, a4, (struct _DEV_BROADCAST_DEVICEINTERFACE_W *)a5);
          }
        }
        else
        {
LABEL_25:
          v17 = "arrival";
          if ( a4 != 0x8000 )
            v17 = "removal";
          VdsTraceEx(
            94,
            2,
            "VDS(0X02040004): Volume Notification: %S %s.",
            (const wchar_t *)&a5->dbch_hdevnotify + 2,
            v17);
          CVdsPnPNotificationManager::VolumeNotificationHandler(this, a4, (struct _DEV_BROADCAST_DEVICEINTERFACE_W *)a5);
        }
      }
    }
  }
  return DefWindowProcW(a2, a3, a4, (LPARAM)a5);
}

```

## disassembly

```asm
0x140007e20  push    rbx
0x140007e22  push    rbp
0x140007e23  push    rsi
0x140007e24  push    rdi
0x140007e25  push    r14
0x140007e27  sub     rsp, 40h
0x140007e2b  mov     rdi, r9
0x140007e2e  mov     esi, r8d
0x140007e31  mov     rbp, rdx
0x140007e34  mov     r14, rcx
0x140007e37  mov     rbx, [rsp+68h+arg_20]
0x140007e3f  cmp     r8d, 219h
0x140007e46  jnz     loc_140008341
0x140007e4c  mov     [rsp+68h+var_48], rbx
0x140007e51  lea     r8, aVds0x02040002W; "VDS(0X02040002): WM_DEVICECHANGE: wPara"...
0x140007e58  mov     edx, 3
0x140007e5d  mov     ecx, 5Eh ; '^'
0x140007e62  call    cs:__imp_VdsTraceEx
0x140007e68  cmp     rdi, 8006h
0x140007e6f  jz      loc_140007FEA
0x140007e75  mov     rax, rdi
0x140007e78  sub     rax, 8000h
0x140007e7e  jz      short loc_140007E8A
0x140007e80  cmp     rax, 4
0x140007e84  jnz     loc_140008341
0x140007e8a  mov     eax, [rbx+4]
0x140007e8d  cmp     eax, 2
0x140007e90  jnz     short loc_140007ECC
0x140007e92  mov     r9d, [rbx+0Ch]
0x140007e96  lea     r8, aVds0x02040003D; "VDS(0X02040003): Drive letter notificat"...
0x140007e9d  mov     edx, eax
0x140007e9f  mov     ecx, 5Eh ; '^'
0x140007ea4  call    cs:__imp_VdsTraceEx
0x140007eaa  test    byte ptr [rbx+10h], 1
0x140007eae  jz      short loc_140007EBC
0x140007eb0  lea     r8, aVds0x02040003D_0; "VDS(0X02040003): Drive letter notificat"...
0x140007eb7  jmp     loc_140008331
0x140007ebc  mov     r8, rbx; struct _DEV_BROADCAST_VOLUME *
0x140007ebf  mov     rdx, rdi; unsigned __int64
0x140007ec2  call    ?DriveLetterNotificationHandler@CVdsPnPNotificationManager@@AEAAX_KPEAU_DEV_BROADCAST_VOLUME@@@Z; CVdsPnPNotificationManager::DriveLetterNotificationHandler(unsigned __int64,_DEV_BROADCAST_VOLUME *)
0x140007ec7  jmp     loc_140008341
0x140007ecc  cmp     eax, 5
0x140007ecf  jnz     loc_140008341
0x140007ed5  mov     rax, qword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x140007edc  sub     rax, [rbx+0Ch]
0x140007ee0  jnz     short loc_140007EED
0x140007ee2  mov     rax, qword ptr cs:GUID_DEVINTERFACE_VOLUME.Data4
0x140007ee9  sub     rax, [rbx+14h]
0x140007eed  test    rax, rax
0x140007ef0  jz      loc_140007F9E
0x140007ef6  mov     rax, qword ptr cs:GUID_DEVINTERFACE_HIDDEN_VOLUME.Data1
0x140007efd  sub     rax, [rbx+0Ch]
0x140007f01  jnz     short loc_140007F0E
0x140007f03  mov     rax, qword ptr cs:GUID_DEVINTERFACE_HIDDEN_VOLUME.Data4
0x140007f0a  sub     rax, [rbx+14h]
0x140007f0e  test    rax, rax
0x140007f11  jz      loc_140007F9E
0x140007f17  mov     rax, qword ptr cs:GUID_DEVINTERFACE_DISK.Data1
0x140007f1e  sub     rax, [rbx+0Ch]
0x140007f22  jnz     short loc_140007F2F
0x140007f24  mov     rax, qword ptr cs:GUID_DEVINTERFACE_DISK.Data4
0x140007f2b  sub     rax, [rbx+14h]
0x140007f2f  test    rax, rax
0x140007f32  jz      short loc_140007F55
0x140007f34  mov     rax, qword ptr cs:GUID_DEVINTERFACE_CDROM.Data1
0x140007f3b  sub     rax, [rbx+0Ch]
0x140007f3f  jnz     short loc_140007F4C
0x140007f41  mov     rax, qword ptr cs:GUID_DEVINTERFACE_CDROM.Data4
0x140007f48  sub     rax, [rbx+14h]
0x140007f4c  test    rax, rax
0x140007f4f  jnz     loc_140008341
0x140007f55  lea     rcx, aRemoval; "removal"
0x140007f5c  lea     rax, aArrival; "arrival"
0x140007f63  cmp     rdi, 8000h
0x140007f6a  cmovnz  rax, rcx
0x140007f6e  lea     r9, [rbx+1Ch]
0x140007f72  mov     [rsp+68h+var_48], rax
0x140007f77  lea     r8, aVds0x02040005D; "VDS(0X02040005): Disk Notification: %S "...
0x140007f7e  mov     edx, 2
0x140007f83  mov     ecx, 5Eh ; '^'
0x140007f88  call    cs:__imp_VdsTraceEx
0x140007f8e  mov     r8, rbx; struct _DEV_BROADCAST_DEVICEINTERFACE_W *
0x140007f91  mov     rdx, rdi; unsigned __int64
0x140007f94  call    ?ForwardDiskNotification@CVdsPnPNotificationManager@@AEAAX_KPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z; CVdsPnPNotificationManager::ForwardDiskNotification(unsigned __int64,_DEV_BROADCAST_DEVICEINTERFACE_W *)
0x140007f99  jmp     loc_140008341
0x140007f9e  lea     rcx, aRemoval; "removal"
0x140007fa5  lea     rax, aArrival; "arrival"
0x140007fac  cmp     rdi, 8000h
0x140007fb3  cmovnz  rax, rcx
0x140007fb7  lea     r9, [rbx+1Ch]
0x140007fbb  mov     [rsp+68h+var_48], rax
0x140007fc0  lea     r8, aVds0x02040004V; "VDS(0X02040004): Volume Notification: %"...
0x140007fc7  mov     edx, 2
0x140007fcc  mov     ecx, 5Eh ; '^'
0x140007fd1  call    cs:__imp_VdsTraceEx
0x140007fd7  mov     r8, rbx; struct _DEV_BROADCAST_DEVICEINTERFACE_W *
0x140007fda  mov     rdx, rdi; unsigned __int64
0x140007fdd  mov     rcx, r14; this
0x140007fe0  call    ?VolumeNotificationHandler@CVdsPnPNotificationManager@@AEAAX_KPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z; CVdsPnPNotificationManager::VolumeNotificationHandler(unsigned __int64,_DEV_BROADCAST_DEVICEINTERFACE_W *)
0x140007fe5  jmp     loc_140008341
0x140007fea  cmp     dword ptr [rbx+4], 6
0x140007fee  jnz     loc_140008341
0x140007ff4  mov     rax, [rbx+20h]
0x140007ff8  sub     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data1
0x140007fff  jnz     short loc_14000800C
0x140008001  mov     rax, [rbx+28h]
0x140008005  sub     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data4
0x14000800c  test    rax, rax
0x14000800f  jnz     short loc_14000808B
0x140008011  lea     r8, aVds0x02040006L; "VDS(0X02040006): Label Change notificat"...
0x140008018  mov     edx, 2
0x14000801d  mov     ecx, 5Eh ; '^'
0x140008022  call    cs:__imp_VdsTraceEx
0x140008028  lea     r8, aCvdspnpnotific_6; "CVdsPnPNotificationManager::LabelMountP"...
0x14000802f  mov     edx, 5Eh ; '^'
0x140008034  lea     rcx, [rsp+68h+var_38]
0x140008039  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000803f  nop
0x140008040  mov     rax, [rbx+20h]
0x140008044  sub     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data1
0x14000804b  jnz     short loc_140008058
0x14000804d  mov     rax, [rbx+28h]
0x140008051  sub     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data4
0x140008058  mov     r9, [rbx+18h]; lParam
0x14000805c  xor     r8d, r8d; wParam
0x14000805f  mov     ecx, cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; idThread
0x140008065  test    rax, rax
0x140008068  mov     edx, 402h
0x14000806d  jz      short loc_140008074
0x14000806f  mov     edx, 403h; Msg
0x140008074  call    cs:__imp_PostThreadMessageW
0x14000807a  nop
0x14000807b  lea     rcx, [rsp+68h+var_38]
0x140008080  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140008086  jmp     loc_140008341
0x14000808b  mov     rax, [rbx+20h]
0x14000808f  mov     rdx, qword ptr cs:GUID_IO_DISK_LAYOUT_CHANGE.Data1
0x140008096  mov     rcx, qword ptr cs:GUID_IO_DISK_LAYOUT_CHANGE.Data4
0x14000809d  sub     rax, rdx
0x1400080a0  jnz     short loc_1400080A9
0x1400080a2  mov     rax, [rbx+28h]
0x1400080a6  sub     rax, rcx
0x1400080a9  test    rax, rax
0x1400080ac  jnz     short loc_1400080D2
0x1400080ae  lea     r8, aVds0x02040007D; "VDS(0X02040007): Disk layout change not"...
0x1400080b5  mov     edx, 2
0x1400080ba  mov     ecx, 5Eh ; '^'
0x1400080bf  call    cs:__imp_VdsTraceEx
0x1400080c5  mov     rdx, rbx; struct _DEV_BROADCAST_HANDLE *
0x1400080c8  call    ?ForwardLayoutChangeNotification@CVdsPnPNotificationManager@@AEAAXPEAU_DEV_BROADCAST_HANDLE@@@Z; CVdsPnPNotificationManager::ForwardLayoutChangeNotification(_DEV_BROADCAST_HANDLE *)
0x1400080cd  jmp     loc_140008341
0x1400080d2  mov     rax, [rbx+20h]
0x1400080d6  sub     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x1400080dd  jnz     short loc_1400080EA
0x1400080df  mov     rax, [rbx+28h]
0x1400080e3  sub     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data4
0x1400080ea  test    rax, rax
0x1400080ed  jnz     short loc_140008113
0x1400080ef  lea     r8, aVds0x0204000dM; "VDS(0X0204000D: mount points change not"...
0x1400080f6  mov     edx, 2
0x1400080fb  mov     ecx, 5Eh ; '^'
0x140008100  call    cs:__imp_VdsTraceEx
0x140008106  mov     rdx, rbx; struct _DEV_BROADCAST_HANDLE *
0x140008109  call    ?ForwardLabelMountPointsNotification@CVdsPnPNotificationManager@@AEAAXPEAU_DEV_BROADCAST_HANDLE@@@Z; CVdsPnPNotificationManager::ForwardLabelMountPointsNotification(_DEV_BROADCAST_HANDLE *)
0x14000810e  jmp     loc_140008341
0x140008113  mov     rax, [rbx+20h]
0x140008117  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x14000811e  jnz     short loc_14000812B
0x140008120  mov     rax, [rbx+28h]
0x140008124  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x14000812b  test    rax, rax
0x14000812e  jnz     short loc_14000813C
0x140008130  lea     r8, aTmpGuidIoVolum_0; "TMP: GUID_IO_VOLUME_DISMOUNT event rece"...
0x140008137  jmp     loc_140008331
0x14000813c  mov     rax, [rbx+20h]
0x140008140  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data1
0x140008147  jnz     short loc_140008154
0x140008149  mov     rax, [rbx+28h]
0x14000814d  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data4
0x140008154  test    rax, rax
0x140008157  jnz     short loc_140008165
0x140008159  lea     r8, aTmpGuidIoVolum_6; "TMP: GUID_IO_VOLUME_DISMOUNT_FAILED eve"...
0x140008160  jmp     loc_140008331
0x140008165  mov     rax, [rbx+20h]
0x140008169  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x140008170  jnz     short loc_14000817D
0x140008172  mov     rax, [rbx+28h]
0x140008176  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x14000817d  test    rax, rax
0x140008180  jnz     short loc_14000818E
0x140008182  lea     r8, aTmpGuidIoVolum; "TMP: GUID_IO_VOLUME_MOUNT event receive"...
0x140008189  jmp     loc_140008331
0x14000818e  mov     rax, [rbx+20h]
0x140008192  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data1
0x140008199  jnz     short loc_1400081A6
0x14000819b  mov     rax, [rbx+28h]
0x14000819f  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data4
0x1400081a6  test    rax, rax
0x1400081a9  jnz     short loc_1400081B7
0x1400081ab  lea     r8, aTmpGuidIoVolum_4; "TMP: GUID_IO_VOLUME_LOCK event received"...
0x1400081b2  jmp     loc_140008331
0x1400081b7  mov     rax, [rbx+20h]
0x1400081bb  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data1
0x1400081c2  jnz     short loc_1400081CF
0x1400081c4  mov     rax, [rbx+28h]
0x1400081c8  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data4
0x1400081cf  test    rax, rax
0x1400081d2  jnz     short loc_1400081E0
0x1400081d4  lea     r8, aTmpGuidIoVolum_2; "TMP: GUID_IO_VOLUME_LOCK_FAILED event r"...
0x1400081db  jmp     loc_140008331
0x1400081e0  mov     rax, [rbx+20h]
0x1400081e4  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data1
0x1400081eb  jnz     short loc_1400081F8
0x1400081ed  mov     rax, [rbx+28h]
0x1400081f1  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data4
0x1400081f8  test    rax, rax
0x1400081fb  jnz     short loc_140008209
0x1400081fd  lea     r8, aTmpGuidIoVolum_3; "TMP: GUID_IO_VOLUME_UNLOCK event receiv"...
0x140008204  jmp     loc_140008331
0x140008209  mov     rax, [rbx+20h]
0x14000820d  sub     rax, qword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1
0x140008214  jnz     short loc_140008221
0x140008216  mov     rax, [rbx+28h]
0x14000821a  sub     rax, qword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data4
0x140008221  test    rax, rax
0x140008224  jnz     short loc_140008232
0x140008226  lea     r8, aTmpGuidIoVolum_5; "TMP: GUID_IO_VOLUME_PHYSICAL_CONFIGURAT"...
0x14000822d  jmp     loc_140008331
0x140008232  mov     rax, [rbx+20h]
0x140008236  sub     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1
0x14000823d  jnz     short loc_14000824A
0x14000823f  mov     rax, [rbx+28h]
0x140008243  sub     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4
0x14000824a  test    rax, rax
0x14000824d  jnz     short loc_140008273
0x14000824f  lea     r8, aVds0x02040014B; "VDS(0X02040014: BitLocker full-volume e"...
0x140008256  mov     edx, 2
0x14000825b  mov     ecx, 5Eh ; '^'
0x140008260  call    cs:__imp_VdsTraceEx
0x140008266  mov     rdx, rbx; struct _DEV_BROADCAST_HANDLE *
0x140008269  call    ?ForwardVolumeChangeNotification@CVdsPnPNotificationManager@@AEAAXPEAU_DEV_BROADCAST_HANDLE@@@Z; CVdsPnPNotificationManager::ForwardVolumeChangeNotification(_DEV_BROADCAST_HANDLE *)
0x14000826e  jmp     loc_140008341
0x140008273  mov     rax, [rbx+20h]
0x140008277  sub     rax, qword ptr cs:GUID_IO_VOLUME_DEVICE_INTERFACE.Data1
0x14000827e  jnz     short loc_14000828B
0x140008280  mov     rax, [rbx+28h]
0x140008284  sub     rax, qword ptr cs:GUID_IO_VOLUME_DEVICE_INTERFACE.Data4
0x14000828b  test    rax, rax
0x14000828e  jnz     short loc_14000829C
0x140008290  lea     r8, aTmpGuidIoVolum_1; "TMP: GUID_IO_VOLUME_DEVICE_INTERFACE ev"...
0x140008297  jmp     loc_140008331
0x14000829c  mov     rax, [rbx+20h]
0x1400082a0  sub     rax, qword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data1
0x1400082a7  jnz     short loc_1400082B4
0x1400082a9  mov     rax, [rbx+28h]
0x1400082ad  sub     rax, qword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data4
0x1400082b4  test    rax, rax
0x1400082b7  jnz     short loc_1400082C2
0x1400082b9  lea     r8, aTmpGuidIoDevic_0; "TMP: GUID_IO_DEVICE_BECOMING_READY even"...
0x1400082c0  jmp     short loc_140008331
0x1400082c2  mov     rax, [rbx+20h]
0x1400082c6  sub     rax, qword ptr cs:GUID_IO_DEVICE_EXTERNAL_REQUEST.Data1
0x1400082cd  jnz     short loc_1400082DA
0x1400082cf  mov     rax, [rbx+28h]
0x1400082d3  sub     rax, qword ptr cs:GUID_IO_DEVICE_EXTERNAL_REQUEST.Data4
0x1400082da  test    rax, rax
0x1400082dd  jnz     short loc_1400082E8
0x1400082df  lea     r8, aTmpGuidIoDevic; "TMP: GUID_IO_DEVICE_EXTERNAL_REQUEST ev"...
0x1400082e6  jmp     short loc_140008331
0x1400082e8  mov     rax, [rbx+20h]
0x1400082ec  sub     rax, qword ptr cs:GUID_IO_MEDIA_EJECT_REQUEST.Data1
0x1400082f3  jnz     short loc_140008300
0x1400082f5  mov     rax, [rbx+28h]
0x1400082f9  sub     rax, qword ptr cs:GUID_IO_MEDIA_EJECT_REQUEST.Data4
0x140008300  test    rax, rax
0x140008303  jnz     short loc_14000830E
0x140008305  lea     r8, aTmpGuidIoMedia; "TMP: GUID_IO_MEDIA_EJECT_REQUEST event "...
0x14000830c  jmp     short loc_140008331
0x14000830e  mov     rax, [rbx+20h]
0x140008312  sub     rax, rdx
0x140008315  jnz     short loc_14000831E
0x140008317  mov     rax, [rbx+28h]
0x14000831b  sub     rax, rcx
0x14000831e  test    rax, rax
0x140008321  lea     r8, aTmpGuidIoDiskL; "TMP: GUID_IO_DISK_LAYOUT_CHANGE event r"...
0x140008328  jz      short loc_140008331
0x14000832a  lea     r8, aTmpCustomEvent; "TMP: CUSTOM event received."
0x140008331  mov     edx, 2
0x140008336  mov     ecx, 5Eh ; '^'
0x14000833b  call    cs:__imp_VdsTraceEx
0x140008341  mov     r9, rbx
0x140008344  mov     r8, rdi
0x140008347  mov     edx, esi
0x140008349  mov     rcx, rbp
0x14000834c  add     rsp, 40h
0x140008350  pop     r14
0x140008352  pop     rdi
0x140008353  pop     rsi
0x140008354  pop     rbp
0x140008355  pop     rbx
  ... truncated ...
```
