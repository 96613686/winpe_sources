# DeviceInfoSet::Refresh(void)

- ea: `0x180008cac`
- end: `0x180008ed8`
- name: `?Refresh@DeviceInfoSet@@QEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(DeviceInfoSet *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008930`

## callees

- `0x18000813c`
- `0x180008cac`
- `0x180009438`
- `0x18000a0d8`
- `0x18000ac34`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x1800129fc`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008d6b`
- `KERNEL32!LeaveCriticalSection` at `0x180008d6b`
- `KERNEL32!GetLastError` at `0x180008cff`
- `KERNEL32!GetLastError` at `0x180008e44`
- `KERNEL32!GetLastError` at `0x180008e83`
- `KERNEL32!GetLastError` at `0x180008cff`
- `KERNEL32!GetLastError` at `0x180008e44`
- `KERNEL32!GetLastError` at `0x180008e83`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180008da7`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180008de1`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180008da7`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180008de1`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180008e31`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180008e31`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180008ceb`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180008ceb`

## string_xrefs

- `0x180008d07`: `SetupDiCreateDeviceInfoList failed with 0x%X, we will not be able to enumerate installed devices`
- `0x180008d31`: `SetupDiCreateDeviceInfoList failed with 0x%X, we will not be able to enumerate installed devices`

## pseudocode

```c
__int64 __fastcall DeviceInfoSet::Refresh(HDEVINFO *this)
{
  int v2; // r14d
  HDEVINFO v3; // rcx
  char *DeviceInfoSet; // rax
  DWORD LastError; // esi
  char *v6; // rbx
  void *v7; // rdx
  void **v8; // rax
  void *v9; // rdx
  __int64 v10; // rcx
  int v11; // r9d
  char *v13; // rbx
  void *v14; // rdx
  char *v15; // rbx
  void *v16; // rdx

  v2 = CRIT_SECT::Lock((CRIT_SECT *)(this + 7));
  if ( this[2] )
  {
    DeviceInfoSet::Close((DeviceInfoSet *)this);
    this[2] = 0;
  }
  CSimpleLinkedList<DeviceInfoSet::DeviceCacheEntry>::Destroy((__int64)(this + 3));
  v3 = this[2];
  if ( v3 )
  {
    if ( v3 != (HDEVINFO)-1LL )
      SetupDiDestroyDeviceInfoList(v3);
    this[2] = 0;
  }
  DeviceInfoSet = (char *)SetupDiCreateDeviceInfoList(0, 0);
  this[2] = DeviceInfoSet;
  if ( (unsigned __int64)(DeviceInfoSet - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( SetupDiGetClassDevsExW(&GUID_DEVCLASS_IMAGE, 0, 0, 0x10u, DeviceInfoSet, 0, 0) == (HDEVINFO)-1LL )
    {
      LastError = GetLastError();
      v13 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "SetupDiGetClassDevsEx(IMAGE, DIGCF_DEVICEINTERFACE) failed with 0x%X",
                      LastError);
      WriteDbgTraceWarningWI("DeviceInfoSet::Refresh", v13);
      WiaTrcLib::Free((WiaTrcLib *)v13, v14);
      v8 = (void **)WiaTrace_TraceWithSubComp(
                      1,
                      "SetupDiGetClassDevsEx(IMAGE, DIGCF_DEVICEINTERFACE) failed with 0x%X",
                      LastError);
    }
    else
    {
      if ( SetupDiGetClassDevsExW(&GUID_DEVCLASS_IMAGE, 0, 0, 0, this[2], 0, 0) != (HDEVINFO)-1LL )
      {
LABEL_13:
        LastError = 0;
        DeviceInfoSet::AddDevNodeDevices((DeviceInfoSet *)this);
        DeviceInfoSet::AddInterfaceDevices((DeviceInfoSet *)this);
        goto LABEL_8;
      }
      LastError = GetLastError();
      v15 = (char *)WiaTrace_TraceLogWithSubComp(1, "SetupDiGetClassDevsEx(IMAGE, 0) failed with 0x%X", LastError);
      WriteDbgTraceWarningWI("DeviceInfoSet::Refresh", v15);
      WiaTrcLib::Free((WiaTrcLib *)v15, v16);
      v8 = (void **)WiaTrace_TraceWithSubComp(1, "SetupDiGetClassDevsEx(IMAGE, 0) failed with 0x%X", LastError);
    }
    v11 = 2;
  }
  else
  {
    LastError = GetLastError();
    v6 = (char *)WiaTrace_TraceLog("SetupDiCreateDeviceInfoList failed with 0x%X, we will not be able to enumerate installed devices");
    WriteDbgTraceErrorWI("DeviceInfoSet::Refresh", v6);
    WiaTrcLib::Free((WiaTrcLib *)v6, v7);
    v8 = (void **)WiaTrace_Trace(
                    "SetupDiCreateDeviceInfoList failed with 0x%X, we will not be able to enumerate installed devices",
                    LastError);
    v11 = 1;
  }
  WiaTrace_ProcessTrace_Ex(v10, v9, (void *)"DeviceInfoSet::Refresh", v11, v8);
  if ( (int)LastError <= 0 )
  {
    if ( LastError )
      goto LABEL_8;
    goto LABEL_13;
  }
  LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_8:
  if ( v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(this + 7));
  return LastError;
}

```

## disassembly

```asm
0x180008cac  push    rbx
0x180008cae  push    rbp
0x180008caf  push    rsi
0x180008cb0  push    rdi
0x180008cb1  push    r14
0x180008cb3  sub     rsp, 40h
0x180008cb7  mov     rdi, rcx
0x180008cba  add     rcx, 38h ; '8'; this
0x180008cbe  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x180008cc3  cmp     qword ptr [rdi+10h], 0
0x180008cc8  mov     r14d, eax
0x180008ccb  jnz     loc_180008E16
0x180008cd1  lea     rcx, [rdi+18h]
0x180008cd5  call    ?Destroy@?$CSimpleLinkedList@VDeviceCacheEntry@DeviceInfoSet@@@@QEAAXXZ; CSimpleLinkedList<DeviceInfoSet::DeviceCacheEntry>::Destroy(void)
0x180008cda  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180008cde  test    rcx, rcx
0x180008ce1  jnz     loc_180008E2B
0x180008ce7  xor     edx, edx; hwndParent
0x180008ce9  xor     ecx, ecx; ClassGuid
0x180008ceb  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180008cf1  mov     [rdi+10h], rax
0x180008cf5  lea     rcx, [rax-1]
0x180008cf9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180008cfd  jbe     short loc_180008D7E
0x180008cff  call    cs:__imp_GetLastError
0x180008d05  mov     edx, eax
0x180008d07  lea     rcx, aSetupdicreated_0; "SetupDiCreateDeviceInfoList failed with"...
0x180008d0e  mov     esi, eax
0x180008d10  call    WiaTrace_TraceLog
0x180008d15  mov     rdx, rax; char *
0x180008d18  lea     rcx, aDeviceinfosetR; "DeviceInfoSet::Refresh"
0x180008d1f  mov     rbx, rax
0x180008d22  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180008d27  mov     rcx, rbx; this
0x180008d2a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180008d2f  mov     edx, esi
0x180008d31  lea     rcx, aSetupdicreated_0; "SetupDiCreateDeviceInfoList failed with"...
0x180008d38  call    WiaTrace_Trace
0x180008d3d  mov     r9d, 1; int
0x180008d43  lea     r8, aDeviceinfosetR; "DeviceInfoSet::Refresh"
0x180008d4a  mov     [rsp+68h+DeviceInfoSet], rax; lpMem
0x180008d4f  call    WiaTrace_ProcessTrace_Ex
0x180008d54  test    esi, esi
0x180008d56  jg      loc_180008E08
0x180008d5c  jz      loc_180008DF1
0x180008d62  test    r14d, r14d
0x180008d65  jz      short loc_180008D71
0x180008d67  lea     rcx, [rdi+38h]; lpCriticalSection
0x180008d6b  call    cs:__imp_LeaveCriticalSection
0x180008d71  mov     eax, esi
0x180008d73  add     rsp, 40h
0x180008d77  pop     r14
0x180008d79  pop     rdi
0x180008d7a  pop     rsi
0x180008d7b  pop     rbp
0x180008d7c  pop     rbx
0x180008d7d  retn
0x180008d7e  mov     [rsp+68h+Reserved], 0; Reserved
0x180008d87  lea     rcx, GUID_DEVCLASS_IMAGE; ClassGuid
0x180008d8e  mov     [rsp+68h+MachineName], 0; MachineName
0x180008d97  mov     r9d, 10h; Flags
0x180008d9d  xor     r8d, r8d; hwndParent
0x180008da0  mov     [rsp+68h+DeviceInfoSet], rax; DeviceInfoSet
0x180008da5  xor     edx, edx; Enumerator
0x180008da7  call    cs:__imp_SetupDiGetClassDevsExW
0x180008dad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008db1  jz      loc_180008E44
0x180008db7  mov     rax, [rdi+10h]
0x180008dbb  lea     rcx, GUID_DEVCLASS_IMAGE; ClassGuid
0x180008dc2  mov     [rsp+68h+Reserved], 0; Reserved
0x180008dcb  xor     r9d, r9d; Flags
0x180008dce  mov     [rsp+68h+MachineName], 0; MachineName
0x180008dd7  xor     r8d, r8d; hwndParent
0x180008dda  xor     edx, edx; Enumerator
0x180008ddc  mov     [rsp+68h+DeviceInfoSet], rax; DeviceInfoSet
0x180008de1  call    cs:__imp_SetupDiGetClassDevsExW
0x180008de7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008deb  jz      loc_180008E83
0x180008df1  mov     rcx, rdi; this
0x180008df4  xor     esi, esi
0x180008df6  call    ?AddDevNodeDevices@DeviceInfoSet@@AEAAXXZ; DeviceInfoSet::AddDevNodeDevices(void)
0x180008dfb  mov     rcx, rdi; this
0x180008dfe  call    ?AddInterfaceDevices@DeviceInfoSet@@AEAAXXZ; DeviceInfoSet::AddInterfaceDevices(void)
0x180008e03  jmp     loc_180008D62
0x180008e08  movzx   esi, si
0x180008e0b  or      esi, 80070000h
0x180008e11  jmp     loc_180008D62
0x180008e16  mov     rcx, rdi; this
0x180008e19  call    ?Close@DeviceInfoSet@@AEAAXXZ; DeviceInfoSet::Close(void)
0x180008e1e  mov     qword ptr [rdi+10h], 0
0x180008e26  jmp     loc_180008CD1
0x180008e2b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008e2f  jz      short loc_180008E37
0x180008e31  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180008e37  mov     qword ptr [rdi+10h], 0
0x180008e3f  jmp     loc_180008CE7
0x180008e44  call    cs:__imp_GetLastError
0x180008e4a  lea     rdx, aSetupdigetclas_1; "SetupDiGetClassDevsEx(IMAGE, DIGCF_DEVI"...
0x180008e51  mov     ecx, 1
0x180008e56  mov     r8d, eax
0x180008e59  mov     esi, eax
0x180008e5b  call    WiaTrace_TraceLogWithSubComp
0x180008e60  mov     rdx, rax; char *
0x180008e63  lea     rcx, aDeviceinfosetR; "DeviceInfoSet::Refresh"
0x180008e6a  mov     rbx, rax
0x180008e6d  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180008e72  mov     rcx, rbx; this
0x180008e75  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180008e7a  lea     rdx, aSetupdigetclas_1; "SetupDiGetClassDevsEx(IMAGE, DIGCF_DEVI"...
0x180008e81  jmp     short loc_180008EC0
0x180008e83  call    cs:__imp_GetLastError
0x180008e89  lea     rdx, aSetupdigetclas_2; "SetupDiGetClassDevsEx(IMAGE, 0) failed "...
0x180008e90  mov     ecx, 1
0x180008e95  mov     r8d, eax
0x180008e98  mov     esi, eax
0x180008e9a  call    WiaTrace_TraceLogWithSubComp
0x180008e9f  mov     rdx, rax; char *
0x180008ea2  lea     rcx, aDeviceinfosetR; "DeviceInfoSet::Refresh"
0x180008ea9  mov     rbx, rax
0x180008eac  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180008eb1  mov     rcx, rbx; this
0x180008eb4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180008eb9  lea     rdx, aSetupdigetclas_2; "SetupDiGetClassDevsEx(IMAGE, 0) failed "...
0x180008ec0  mov     r8d, esi
0x180008ec3  mov     ecx, 1
0x180008ec8  call    WiaTrace_TraceWithSubComp
0x180008ecd  mov     r9d, 2
0x180008ed3  jmp     loc_180008D43
```
