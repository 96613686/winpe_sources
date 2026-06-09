# CVdsPnPNotificationManager::LabelMountPointsNotificationHandler(uint,void *)

- ea: `0x14000fd1c`
- end: `0x14000ff04`
- name: `?LabelMountPointsNotificationHandler@CVdsPnPNotificationManager@@AEAAXIPEAX@Z`
- size: `488`
- prototype: `void __fastcall(CVdsPnPNotificationManager *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x1400066a0`

## callees

- `0x140006a80`
- `0x14000cf60`
- `0x14000d0f0`
- `0x14000e6bc`
- `0x14000f930`
- `0x14000f9b0`
- `0x14000fd1c`
- `0x14003c084`
- `0x14003cba8`
- `0x14004fd20`
- `0x140052e46`
- `0x140052e80`

## import_xrefs

- `vdsutil!OpenDevice` at `0x14000fdb8`
- `vdsutil!OpenDevice` at `0x14000fdb8`
- `vdsutil!GetDeviceName` at `0x14000fdda`
- `vdsutil!GetDeviceName` at `0x14000fdda`
- `vdsutil!VdsTraceEx` at `0x14000fdf5`
- `vdsutil!VdsTraceEx` at `0x14000fe2e`
- `vdsutil!VdsTraceEx` at `0x14000fe92`
- `vdsutil!VdsTraceEx` at `0x14000feb5`
- `vdsutil!VdsTraceEx` at `0x14000fdf5`
- `vdsutil!VdsTraceEx` at `0x14000fe2e`
- `vdsutil!VdsTraceEx` at `0x14000fe92`
- `vdsutil!VdsTraceEx` at `0x14000feb5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000fd67`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000fd67`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000fed7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000fed7`

## string_xrefs

- `0x14000fd52`: `CVdsPnPNotificationManager::LabelMountPointsNotificationHandler`
- `0x14000fde9`: `CVdsPnPNotificationManager::LabelMountPointsNotificationHandler, 1, error=%ld`
- `0x14000fe22`: `CVdsPnPNotificationManager::LabelMountPointsNotificationHandler, 2, hr=%lX`
- `0x14000fea6`: `CVdsPnPNotificationManager::LabelMountPointsNotificationHandler, 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVdsPnPNotificationManager::LabelMountPointsNotificationHandler(
        CVdsPnPNotificationManager *this,
        int a2,
        void *a3)
{
  unsigned __int16 *VolumeInMap; // rax
  const wchar_t *v7; // rbx
  int v8; // edi
  int DeviceName; // eax
  int VolumeId; // eax
  unsigned int v11; // ecx
  int v12; // eax
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v14; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v17[280]; // [rsp+60h] [rbp-A0h] BYREF

  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v15,
    0x5Eu,
    "CVdsPnPNotificationManager::LabelMountPointsNotificationHandler");
  v14 = 0;
  VolumeInMap = CVdsPnPNotificationManager::FindVolumeInMap(this, a3);
  CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&v14, (__int64)VolumeInMap);
  v7 = v14;
  if ( v14 )
  {
    v13 = -1;
    Buf1 = 0;
    v8 = OpenDevice(v14, 0, &v13);
    if ( v8 )
      goto LABEL_12;
    DeviceName = GetDeviceName(v13, 0, 274, v17);
    v8 = DeviceName;
    if ( DeviceName )
      VdsTraceEx(94, 0, "CVdsPnPNotificationManager::LabelMountPointsNotificationHandler, 1, error=%ld", DeviceName);
    CVdsHandleImpl<-1>::Close(&v13);
    if ( v8 )
    {
LABEL_12:
      if ( v8 == 2 )
      {
        v12 = CVdsService::RemoveObsoleteDevNodes();
        if ( v12 < 0 )
          VdsTraceEx(94, 1, "CVdsPnPNotificationManager::LabelMountPointsNotificationHandler, 3, hr=%lX", v12);
      }
      else
      {
        VdsTraceEx(94, 1, "VDS(0X0204000C): failed to send volume label change notification(%S): %X", v7, v8);
      }
    }
    else
    {
      VolumeId = CVdsService::GetVolumeId(v17, &Buf1, 0);
      if ( VolumeId >= 0 )
      {
        if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        {
          if ( a2 == 1026 )
            CVdsService::SendFileSystemNotification(0xCBu, &Buf1, 0);
          else
            CVdsService::SendMountPointsNotification(v11, &Buf1);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsPnPNotificationManager::LabelMountPointsNotificationHandler, 2, hr=%lX", VolumeId);
      }
    }
    CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v13);
  }
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v14);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v15);
}

```

## disassembly

```asm
0x14000fd1c  mov     [rsp-8+arg_8], rbx
0x14000fd21  mov     [rsp-8+arg_18], rsi
0x14000fd26  push    rbp
0x14000fd27  push    rdi
0x14000fd28  push    r14
0x14000fd2a  lea     rbp, [rsp-1A0h]
0x14000fd32  sub     rsp, 2A0h
0x14000fd39  mov     rax, cs:__security_cookie
0x14000fd40  xor     rax, rsp
0x14000fd43  mov     [rbp+1B0h+var_20], rax
0x14000fd4a  mov     rdi, r8
0x14000fd4d  mov     esi, edx
0x14000fd4f  mov     rbx, rcx
0x14000fd52  lea     r8, aCvdspnpnotific_2; "CVdsPnPNotificationManager::LabelMountP"...
0x14000fd59  mov     r14d, 5Eh ; '^'
0x14000fd5f  mov     edx, r14d
0x14000fd62  lea     rcx, [rsp+2B0h+var_270]
0x14000fd67  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000fd6d  nop
0x14000fd6e  mov     [rsp+2B0h+var_278], 0
0x14000fd77  mov     rdx, rdi; void *
0x14000fd7a  mov     rcx, rbx; this
0x14000fd7d  call    ?FindVolumeInMap@CVdsPnPNotificationManager@@AEAAPEAGPEAX@Z; CVdsPnPNotificationManager::FindVolumeInMap(void *)
0x14000fd82  mov     rdx, rax
0x14000fd85  lea     rcx, [rsp+2B0h+var_278]
0x14000fd8a  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x14000fd8f  mov     rbx, [rsp+2B0h+var_278]
0x14000fd94  test    rbx, rbx
0x14000fd97  jz      loc_14000FEC7
0x14000fd9d  mov     [rsp+2B0h+var_280], 0FFFFFFFFFFFFFFFFh
0x14000fda6  xorps   xmm0, xmm0
0x14000fda9  movups  [rsp+2B0h+Buf1], xmm0
0x14000fdae  lea     r8, [rsp+2B0h+var_280]
0x14000fdb3  xor     edx, edx
0x14000fdb5  mov     rcx, rbx
0x14000fdb8  call    cs:__imp_OpenDevice
0x14000fdbe  mov     edi, eax
0x14000fdc0  test    eax, eax
0x14000fdc2  jnz     loc_14000FE77
0x14000fdc8  lea     r9, [rsp+2B0h+var_250]
0x14000fdcd  xor     edx, edx
0x14000fdcf  mov     r8d, 112h
0x14000fdd5  mov     rcx, [rsp+2B0h+var_280]
0x14000fdda  call    cs:__imp_GetDeviceName
0x14000fde0  mov     edi, eax
0x14000fde2  test    eax, eax
0x14000fde4  jz      short loc_14000FDFB
0x14000fde6  mov     r9d, eax
0x14000fde9  lea     r8, aCvdspnpnotific_1; "CVdsPnPNotificationManager::LabelMountP"...
0x14000fdf0  xor     edx, edx
0x14000fdf2  mov     ecx, r14d
0x14000fdf5  call    cs:__imp_VdsTraceEx
0x14000fdfb  lea     rcx, [rsp+2B0h+var_280]
0x14000fe00  call    ?Close@?$CVdsHandleImpl@$0?0@@QEAAXXZ; CVdsHandleImpl<-1>::Close(void)
0x14000fe05  test    edi, edi
0x14000fe07  jnz     short loc_14000FE77
0x14000fe09  xor     r8d, r8d; int *
0x14000fe0c  lea     rdx, [rsp+2B0h+Buf1]; struct _GUID *
0x14000fe11  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x14000fe16  call    ?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z; CVdsService::GetVolumeId(ushort *,_GUID *,int *)
0x14000fe1b  test    eax, eax
0x14000fe1d  jns     short loc_14000FE39
0x14000fe1f  mov     r9d, eax
0x14000fe22  lea     r8, aCvdspnpnotific_26; "CVdsPnPNotificationManager::LabelMountP"...
0x14000fe29  xor     edx, edx
0x14000fe2b  mov     ecx, r14d
0x14000fe2e  call    cs:__imp_VdsTraceEx
0x14000fe34  jmp     loc_14000FEBC
0x14000fe39  mov     r8d, 10h; Size
0x14000fe3f  lea     rdx, GUID_NULL; Buf2
0x14000fe46  lea     rcx, [rsp+2B0h+Buf1]; Buf1
0x14000fe4b  call    memcmp_0
0x14000fe50  test    eax, eax
0x14000fe52  jz      short loc_14000FEBC
0x14000fe54  lea     rdx, [rsp+2B0h+Buf1]; struct _GUID *
0x14000fe59  cmp     esi, 402h
0x14000fe5f  jnz     short loc_14000FE70
0x14000fe61  xor     r8d, r8d; unsigned int
0x14000fe64  mov     ecx, 0CBh; unsigned int
0x14000fe69  call    ?SendFileSystemNotification@CVdsService@@SAXKAEAU_GUID@@K@Z; CVdsService::SendFileSystemNotification(ulong,_GUID &,ulong)
0x14000fe6e  jmp     short loc_14000FEBC
0x14000fe70  call    ?SendMountPointsNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendMountPointsNotification(ulong,_GUID &)
0x14000fe75  jmp     short loc_14000FEBC
0x14000fe77  cmp     edi, 2
0x14000fe7a  jz      short loc_14000FE9A
0x14000fe7c  mov     [rsp+2B0h+var_290], edi
0x14000fe80  mov     r9, rbx
0x14000fe83  lea     r8, aVds0x0204000cF; "VDS(0X0204000C): failed to send volume "...
0x14000fe8a  mov     edx, 1
0x14000fe8f  mov     ecx, r14d
0x14000fe92  call    cs:__imp_VdsTraceEx
0x14000fe98  jmp     short loc_14000FEBC
0x14000fe9a  call    ?RemoveObsoleteDevNodes@CVdsService@@SAJXZ; CVdsService::RemoveObsoleteDevNodes(void)
0x14000fe9f  test    eax, eax
0x14000fea1  jns     short loc_14000FEBC
0x14000fea3  mov     r9d, eax
0x14000fea6  lea     r8, aCvdspnpnotific_3; "CVdsPnPNotificationManager::LabelMountP"...
0x14000fead  mov     edx, 1
0x14000feb2  mov     ecx, r14d
0x14000feb5  call    cs:__imp_VdsTraceEx
0x14000febb  nop
0x14000febc  lea     rcx, [rsp+2B0h+var_280]
0x14000fec1  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14000fec6  nop
0x14000fec7  lea     rcx, [rsp+2B0h+var_278]
0x14000fecc  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000fed1  nop
0x14000fed2  lea     rcx, [rsp+2B0h+var_270]
0x14000fed7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000fedd  mov     rcx, [rbp+1B0h+var_20]
0x14000fee4  xor     rcx, rsp; StackCookie
0x14000fee7  call    __security_check_cookie
0x14000feec  lea     r11, [rsp+2B0h+var_10]
0x14000fef4  mov     rbx, [r11+28h]
0x14000fef8  mov     rsi, [r11+38h]
0x14000fefc  mov     rsp, r11
0x14000feff  pop     r14
0x14000ff01  pop     rdi
0x14000ff02  pop     rbp
0x14000ff03  retn
```
