# CVdsPnPNotificationManager::RegisterForCustomVolumeEventAll(void)

- ea: `0x14000d2d8`
- end: `0x14000d470`
- name: `?RegisterForCustomVolumeEventAll@CVdsPnPNotificationManager@@AEAAXXZ`
- size: `408`
- prototype: `void __fastcall(CVdsPnPNotificationManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140050270`

## callees

- `0x14000d2d8`
- `0x14000d478`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d3f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d389`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14000d42c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14000d42c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14000d328`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14000d328`
- `DEVOBJ!DevObjGetClassDevs` at `0x14000d37f`
- `DEVOBJ!DevObjGetClassDevs` at `0x14000d37f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14000d43e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14000d43e`
- `vdsutil!VdsHeapFree` at `0x14000d404`
- `vdsutil!VdsHeapFree` at `0x14000d404`
- `vdsutil!VdsTraceEx` at `0x14000d34f`
- `vdsutil!VdsTraceEx` at `0x14000d3da`
- `vdsutil!VdsTraceEx` at `0x14000d34f`
- `vdsutil!VdsTraceEx` at `0x14000d3da`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d30e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d30e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d449`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d449`
- `vdsutil!GetInterfaceDetailData` at `0x14000d3c1`
- `vdsutil!GetInterfaceDetailData` at `0x14000d3c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsPnPNotificationManager::RegisterForCustomVolumeEventAll(CVdsPnPNotificationManager *this)
{
  __int64 DeviceInfoList; // rax
  __int64 v3; // rdi
  DWORD LastError; // eax
  DWORD v5; // eax
  unsigned int v6; // esi
  __int64 i; // r9
  int InterfaceDetailData; // eax
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v11; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v13[2]; // [rsp+48h] [rbp-28h] BYREF

  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v12,
    0x5Eu,
    "CVdsPnPNotificationManager::RegisterForCustomVolumeEventAll");
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    VdsTraceEx(94, 1, "VDS(0X02040008): failed to initialize device info list: %X", LastError);
  }
  else if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_VOLUME, 0, 18, 0, 0) )
  {
    memset(v13, 0, sizeof(v13));
    v11 = 0;
    LODWORD(v13[0]) = 32;
    v6 = 0;
    for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v3, 0, &GUID_DEVINTERFACE_VOLUME, i, v13) == 1; i = v6 )
    {
      InterfaceDetailData = GetInterfaceDetailData(v3, v13, &v11);
      if ( InterfaceDetailData )
      {
        VdsTraceEx(
          94,
          0,
          "CVdsPnPNotificationManager::RegisterForCustomVolumeEventAll, 1, error=%ld",
          InterfaceDetailData);
      }
      else
      {
        CVdsPnPNotificationManager::RegisterForCustomVolumeEvent(this, (unsigned __int16 *)(v11 + 4));
        v9 = v11;
        ProcessHeap = GetProcessHeap();
        VdsHeapFree(ProcessHeap, 0, v9);
        v11 = 0;
      }
      ++v6;
    }
    DevObjDestroyDeviceInfoList(v3);
  }
  else
  {
    v5 = GetLastError();
    VdsTraceEx(94, 1, "VDS(0X02040008): failed to get volume device info set: %X", v5);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v12);
}

```

## disassembly

```asm
0x14000d2d8  mov     [rsp-18h+arg_8], rbx
0x14000d2dd  mov     [rsp-18h+arg_10], rsi
0x14000d2e2  push    rbp
0x14000d2e3  push    rdi
0x14000d2e4  push    r14
0x14000d2e6  mov     rbp, rsp
0x14000d2e9  sub     rsp, 70h
0x14000d2ed  mov     rax, cs:__security_cookie
0x14000d2f4  xor     rax, rsp
0x14000d2f7  mov     [rbp+var_8], rax
0x14000d2fb  mov     r14, rcx
0x14000d2fe  lea     r8, aCvdspnpnotific_21; "CVdsPnPNotificationManager::RegisterFor"...
0x14000d305  mov     edx, 5Eh ; '^'
0x14000d30a  lea     rcx, [rbp+var_38]
0x14000d30e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000d314  nop
0x14000d315  mov     [rsp+70h+var_50], 0
0x14000d31e  xor     r9d, r9d
0x14000d321  xor     r8d, r8d
0x14000d324  xor     edx, edx
0x14000d326  xor     ecx, ecx
0x14000d328  call    cs:__imp_DevObjCreateDeviceInfoList
0x14000d32e  mov     rdi, rax
0x14000d331  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d335  jnz     short loc_14000D35A
0x14000d337  call    cs:__imp_GetLastError
0x14000d33d  lea     r8, aVds0x02040008F; "VDS(0X02040008): failed to initialize d"...
0x14000d344  mov     r9d, eax
0x14000d347  mov     edx, 1
0x14000d34c  lea     ecx, [rdx+5Dh]
0x14000d34f  call    cs:__imp_VdsTraceEx
0x14000d355  jmp     loc_14000D445
0x14000d35a  mov     [rsp+70h+var_48], 0
0x14000d363  mov     [rsp+70h+var_50], 0
0x14000d36c  mov     r9d, 12h
0x14000d372  xor     r8d, r8d
0x14000d375  lea     rdx, GUID_DEVINTERFACE_VOLUME
0x14000d37c  mov     rcx, rdi
0x14000d37f  call    cs:__imp_DevObjGetClassDevs
0x14000d385  test    eax, eax
0x14000d387  jnz     short loc_14000D398
0x14000d389  call    cs:__imp_GetLastError
0x14000d38f  lea     r8, aVds0x02040008F_0; "VDS(0X02040008): failed to get volume d"...
0x14000d396  jmp     short loc_14000D344
0x14000d398  xorps   xmm0, xmm0
0x14000d39b  movups  [rbp+var_28], xmm0
0x14000d39f  movups  [rbp+var_18], xmm0
0x14000d3a3  mov     [rbp+var_40], 0
0x14000d3ab  mov     dword ptr [rbp+var_28], 20h ; ' '
0x14000d3b2  xor     esi, esi
0x14000d3b4  xor     r9d, r9d
0x14000d3b7  jmp     short loc_14000D417
0x14000d3b9  lea     r8, [rbp+var_40]
0x14000d3bd  lea     rdx, [rbp+var_28]
0x14000d3c1  call    cs:__imp_GetInterfaceDetailData
0x14000d3c7  test    eax, eax
0x14000d3c9  jz      short loc_14000D3E2
0x14000d3cb  mov     r9d, eax
0x14000d3ce  lea     r8, aCvdspnpnotific_29; "CVdsPnPNotificationManager::RegisterFor"...
0x14000d3d5  xor     edx, edx
0x14000d3d7  lea     ecx, [rdx+5Eh]
0x14000d3da  call    cs:__imp_VdsTraceEx
0x14000d3e0  jmp     short loc_14000D412
0x14000d3e2  mov     rdx, [rbp+var_40]
0x14000d3e6  add     rdx, 4; unsigned __int16 *
0x14000d3ea  mov     rcx, r14; this
0x14000d3ed  call    ?RegisterForCustomVolumeEvent@CVdsPnPNotificationManager@@AEAAXPEAG@Z; CVdsPnPNotificationManager::RegisterForCustomVolumeEvent(ushort *)
0x14000d3f2  mov     rbx, [rbp+var_40]
0x14000d3f6  call    cs:__imp_GetProcessHeap
0x14000d3fc  mov     r8, rbx
0x14000d3ff  xor     edx, edx
0x14000d401  mov     rcx, rax
0x14000d404  call    cs:__imp_VdsHeapFree
0x14000d40a  mov     [rbp+var_40], 0
0x14000d412  inc     esi
0x14000d414  mov     r9d, esi
0x14000d417  lea     rax, [rbp+var_28]
0x14000d41b  mov     [rsp+70h+var_50], rax
0x14000d420  lea     r8, GUID_DEVINTERFACE_VOLUME
0x14000d427  xor     edx, edx
0x14000d429  mov     rcx, rdi
0x14000d42c  call    cs:__imp_DevObjEnumDeviceInterfaces
0x14000d432  mov     rcx, rdi
0x14000d435  cmp     eax, 1
0x14000d438  jz      loc_14000D3B9
0x14000d43e  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14000d444  nop
0x14000d445  lea     rcx, [rbp+var_38]
0x14000d449  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000d44f  mov     rcx, [rbp+var_8]
0x14000d453  xor     rcx, rsp; StackCookie
0x14000d456  call    __security_check_cookie
0x14000d45b  lea     r11, [rsp+70h+var_s0]
0x14000d460  mov     rbx, [r11+28h]
0x14000d464  mov     rsi, [r11+30h]
0x14000d468  mov     rsp, r11
0x14000d46b  pop     r14
0x14000d46d  pop     rdi
0x14000d46e  pop     rbp
0x14000d46f  retn
```
