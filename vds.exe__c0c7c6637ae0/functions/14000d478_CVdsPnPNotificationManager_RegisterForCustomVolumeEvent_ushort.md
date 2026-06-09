# CVdsPnPNotificationManager::RegisterForCustomVolumeEvent(ushort *)

- ea: `0x14000d478`
- end: `0x14000d69f`
- name: `?RegisterForCustomVolumeEvent@CVdsPnPNotificationManager@@AEAAXPEAG@Z`
- size: `551`
- prototype: `void __fastcall(CVdsPnPNotificationManager *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000d2d8`
- `0x1400504f4`

## callees

- `0x14000d478`
- `0x14000e794`
- `0x140013298`
- `0x14003c084`
- `0x140052e80`

## import_xrefs

- `USER32!UnregisterDeviceNotification` at `0x14000d5b6`
- `USER32!UnregisterDeviceNotification` at `0x14000d5b6`
- `USER32!RegisterDeviceNotificationW` at `0x14000d541`
- `USER32!RegisterDeviceNotificationW` at `0x14000d541`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d649`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d649`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d4eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d4eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d669`
- `vdsutil!OpenDevice` at `0x14000d4fb`
- `vdsutil!OpenDevice` at `0x14000d4fb`
- `vdsutil!VdsTraceEx` at `0x14000d576`
- `vdsutil!VdsTraceEx` at `0x14000d5a4`
- `vdsutil!VdsTraceEx` at `0x14000d5da`
- `vdsutil!VdsTraceEx` at `0x14000d5f4`
- `vdsutil!VdsTraceEx` at `0x14000d63f`
- `vdsutil!VdsTraceEx` at `0x14000d576`
- `vdsutil!VdsTraceEx` at `0x14000d5a4`
- `vdsutil!VdsTraceEx` at `0x14000d5da`
- `vdsutil!VdsTraceEx` at `0x14000d5f4`
- `vdsutil!VdsTraceEx` at `0x14000d63f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d4d9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d4d9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d654`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d654`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVdsPnPNotificationManager::RegisterForCustomVolumeEvent(
        CVdsPnPNotificationManager *this,
        unsigned __int16 *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  HDEVNOTIFY v6; // rax
  void *v7; // rdi
  unsigned int inserted; // eax
  DWORD LastError; // ebx
  int v10; // eax
  HANDLE hObject[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v12[16]; // [rsp+50h] [rbp-19h] BYREF
  __int128 NotificationFilter; // [rsp+60h] [rbp-9h] BYREF
  __int128 v14; // [rsp+70h] [rbp+7h]
  __int128 v15; // [rsp+80h] [rbp+17h]
  __int64 v16; // [rsp+90h] [rbp+27h]

  hObject[0] = (HANDLE)-1LL;
  NotificationFilter = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v12,
    0x5Eu,
    "CVdsPnPNotificationManager::RegisterForCustomVolumeEvent");
  hObject[1] = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v4 = OpenDevice(a2, 0, hObject);
  v5 = v4;
  if ( v4 )
  {
    VdsTraceEx(94, v4 == 2, "VDS(0X0204000A): failed to get volume handle(%S): %X", a2, v4);
    if ( v5 == 2 )
    {
      v10 = CVdsService::RemoveObsoleteDevNodes();
      if ( v10 < 0 )
        VdsTraceEx(94, 1, "CVdsPnPNotificationManager::RegisterForCustomVolumeEvent, 3, hr=%lX", v10);
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsPnPNotificationManager::RegisterForCustomVolumeEvent, 2, error=%ld", v5);
      VdsLogError(0xC2000008, 0, 0, v5, 0x2000001u, a2, 0);
    }
  }
  else
  {
    v15 = 0;
    v16 = 0;
    NotificationFilter = 0x600000038uLL;
    v14 = (unsigned __int64)hObject[0];
    v6 = RegisterDeviceNotificationW(*((HANDLE *)this + 14), &NotificationFilter, 0);
    v7 = v6;
    if ( v6 )
    {
      inserted = CVdsPnPNotificationManager::InsertVolumeToMap(this, v6, a2);
      LastError = inserted;
      if ( !inserted )
        goto LABEL_12;
      VdsTraceEx(94, 0, "CVdsPnPNotificationManager::RegisterForCustomVolumeEvent, 1, error=%ld", inserted);
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_12;
    }
    VdsTraceEx(94, 1, "VDS(0X02040009): failed to register for volume device notification(%S): %X", a2, LastError);
    if ( v7 )
      UnregisterDeviceNotification(v7);
  }
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v12);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
}

```

## disassembly

```asm
0x14000d478  mov     [rsp-8+arg_10], rbx
0x14000d47d  mov     [rsp-8+arg_18], rsi
0x14000d482  push    rbp
0x14000d483  push    rdi
0x14000d484  push    r12
0x14000d486  push    r14
0x14000d488  push    r15
0x14000d48a  lea     rbp, [rsp-37h]
0x14000d48f  sub     rsp, 0A0h
0x14000d496  mov     rax, cs:__security_cookie
0x14000d49d  xor     rax, rsp
0x14000d4a0  mov     [rbp+57h+var_28], rax
0x14000d4a4  mov     rsi, rdx
0x14000d4a7  mov     r14, rcx
0x14000d4aa  mov     [rbp+57h+hObject], 0FFFFFFFFFFFFFFFFh
0x14000d4b2  xorps   xmm0, xmm0
0x14000d4b5  xor     eax, eax
0x14000d4b7  movups  [rbp+57h+NotificationFilter], xmm0
0x14000d4bb  movups  [rbp+57h+var_50], xmm0
0x14000d4bf  movups  [rbp+57h+var_40], xmm0
0x14000d4c3  mov     [rbp+57h+var_30], rax
0x14000d4c7  lea     r8, aCvdspnpnotific_5; "CVdsPnPNotificationManager::RegisterFor"...
0x14000d4ce  lea     r12d, [rax+5Eh]
0x14000d4d2  mov     edx, r12d
0x14000d4d5  lea     rcx, [rbp+57h+var_70]
0x14000d4d9  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000d4df  nop
0x14000d4e0  lea     r15, [r14+8]
0x14000d4e4  mov     [rbp+57h+var_78], r15
0x14000d4e8  mov     rcx, r15; lpCriticalSection
0x14000d4eb  call    cs:__imp_EnterCriticalSection
0x14000d4f1  nop
0x14000d4f2  lea     r8, [rbp+57h+hObject]
0x14000d4f6  xor     edx, edx
0x14000d4f8  mov     rcx, rsi
0x14000d4fb  call    cs:__imp_OpenDevice
0x14000d501  mov     ebx, eax
0x14000d503  test    eax, eax
0x14000d505  jnz     loc_14000D5C1
0x14000d50b  xorps   xmm0, xmm0
0x14000d50e  xor     eax, eax
0x14000d510  movups  [rbp+57h+NotificationFilter], xmm0
0x14000d514  movups  [rbp+57h+var_50], xmm0
0x14000d518  movups  [rbp+57h+var_40], xmm0
0x14000d51c  mov     [rbp+57h+var_30], rax
0x14000d520  mov     dword ptr [rbp+57h+NotificationFilter], 38h ; '8'
0x14000d527  mov     dword ptr [rbp+57h+NotificationFilter+4], 6
0x14000d52e  mov     rax, [rbp+57h+hObject]
0x14000d532  mov     qword ptr [rbp+57h+var_50], rax
0x14000d536  xor     r8d, r8d; Flags
0x14000d539  lea     rdx, [rbp+57h+NotificationFilter]; NotificationFilter
0x14000d53d  mov     rcx, [r14+70h]; hRecipient
0x14000d541  call    cs:__imp_RegisterDeviceNotificationW
0x14000d547  mov     rdi, rax
0x14000d54a  test    rax, rax
0x14000d54d  jz      short loc_14000D57E
0x14000d54f  mov     r8, rsi; unsigned __int16 *
0x14000d552  mov     rdx, rax; void *
0x14000d555  mov     rcx, r14; this
0x14000d558  call    ?InsertVolumeToMap@CVdsPnPNotificationManager@@AEAAKPEAXPEAG@Z; CVdsPnPNotificationManager::InsertVolumeToMap(void *,ushort *)
0x14000d55d  mov     ebx, eax
0x14000d55f  test    eax, eax
0x14000d561  jz      loc_14000D646
0x14000d567  mov     r9d, eax
0x14000d56a  lea     r8, aCvdspnpnotific_30; "CVdsPnPNotificationManager::RegisterFor"...
0x14000d571  xor     edx, edx
0x14000d573  mov     ecx, r12d
0x14000d576  call    cs:__imp_VdsTraceEx
0x14000d57c  jmp     short loc_14000D58E
0x14000d57e  call    cs:__imp_GetLastError
0x14000d584  mov     ebx, eax
0x14000d586  test    eax, eax
0x14000d588  jz      loc_14000D646
0x14000d58e  mov     [rsp+0C0h+var_A0], ebx
0x14000d592  mov     r9, rsi
0x14000d595  lea     r8, aVds0x02040009F; "VDS(0X02040009): failed to register for"...
0x14000d59c  mov     edx, 1
0x14000d5a1  mov     ecx, r12d
0x14000d5a4  call    cs:__imp_VdsTraceEx
0x14000d5aa  test    rdi, rdi
0x14000d5ad  jz      loc_14000D646
0x14000d5b3  mov     rcx, rdi; Handle
0x14000d5b6  call    cs:__imp_UnregisterDeviceNotification
0x14000d5bc  jmp     loc_14000D646
0x14000d5c1  xor     edx, edx
0x14000d5c3  cmp     ebx, 2
0x14000d5c6  setz    dl
0x14000d5c9  mov     [rsp+0C0h+var_A0], ebx
0x14000d5cd  mov     r9, rsi
0x14000d5d0  lea     r8, aVds0x0204000aF; "VDS(0X0204000A): failed to get volume h"...
0x14000d5d7  mov     ecx, r12d
0x14000d5da  call    cs:__imp_VdsTraceEx
0x14000d5e0  cmp     ebx, 2
0x14000d5e3  jz      short loc_14000D624
0x14000d5e5  mov     r9d, ebx
0x14000d5e8  lea     r8, aCvdspnpnotific_38; "CVdsPnPNotificationManager::RegisterFor"...
0x14000d5ef  xor     edx, edx
0x14000d5f1  mov     ecx, r12d
0x14000d5f4  call    cs:__imp_VdsTraceEx
0x14000d5fa  mov     [rsp+0C0h+var_90], 0
0x14000d603  mov     [rsp+0C0h+var_98], rsi; unsigned __int16 *
0x14000d608  mov     [rsp+0C0h+var_A0], 2000001h; unsigned int
0x14000d610  mov     r9d, ebx; unsigned int
0x14000d613  xor     r8d, r8d; void *
0x14000d616  xor     edx, edx; unsigned int
0x14000d618  mov     ecx, 0C2000008h; unsigned int
0x14000d61d  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000d622  jmp     short loc_14000D646
0x14000d624  call    ?RemoveObsoleteDevNodes@CVdsService@@SAJXZ; CVdsService::RemoveObsoleteDevNodes(void)
0x14000d629  test    eax, eax
0x14000d62b  jns     short loc_14000D646
0x14000d62d  mov     r9d, eax
0x14000d630  lea     r8, aCvdspnpnotific_7; "CVdsPnPNotificationManager::RegisterFor"...
0x14000d637  mov     edx, 1
0x14000d63c  mov     ecx, r12d
0x14000d63f  call    cs:__imp_VdsTraceEx
0x14000d645  nop
0x14000d646  mov     rcx, r15; lpCriticalSection
0x14000d649  call    cs:__imp_LeaveCriticalSection
0x14000d64f  nop
0x14000d650  lea     rcx, [rbp+57h+var_70]
0x14000d654  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000d65a  nop
0x14000d65b  mov     rcx, [rbp+57h+hObject]; hObject
0x14000d65f  lea     rax, [rcx-1]
0x14000d663  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d667  ja      short loc_14000D677
0x14000d669  call    cs:__imp_CloseHandle
0x14000d66f  mov     [rbp+57h+hObject], 0FFFFFFFFFFFFFFFFh
0x14000d677  mov     rcx, [rbp+57h+var_28]
0x14000d67b  xor     rcx, rsp; StackCookie
0x14000d67e  call    __security_check_cookie
0x14000d683  lea     r11, [rsp+0C0h+var_20]
0x14000d68b  mov     rbx, [r11+40h]
0x14000d68f  mov     rsi, [r11+48h]
0x14000d693  mov     rsp, r11
0x14000d696  pop     r15
0x14000d698  pop     r14
0x14000d69a  pop     r12
0x14000d69c  pop     rdi
0x14000d69d  pop     rbp
0x14000d69e  retn
```
