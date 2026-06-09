# CVolumeManager::Initialize(CTrkWksSvc *,CTrkWksConfiguration const *,SERVICE_STATUS_HANDLE__ *)

- ea: `0x18000a880`
- end: `0x18000a9c7`
- name: `?Initialize@CVolumeManager@@QEAAXPEAVCTrkWksSvc@@PEBVCTrkWksConfiguration@@PEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `327`
- prototype: `void __fastcall(CVolumeManager *__hidden this, struct CTrkWksSvc *, const struct CTrkWksConfiguration *, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000a524`

## callees

- `0x1800090c8`
- `0x18000a038`
- `0x18000a27c`
- `0x18000a880`
- `0x18000ad70`
- `0x18000ada0`
- `0x18000af38`
- `0x18000d020`
- `0x18000d038`
- `0x18000d1a0`
- `0x18000d228`
- `0x18000feb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a8f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a8f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a981`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a931`

## pseudocode

```c
void __fastcall CVolumeManager::Initialize(
        CVolumeManager *this,
        struct CTrkWksSvc *a2,
        const struct CTrkWksConfiguration *a3,
        struct SERVICE_STATUS_HANDLE__ *a4)
{
  __int64 v6; // rdx
  struct _FILETIME v7; // r8
  __int64 v8; // r9
  HANDLE EventW; // rdx
  unsigned int v10; // r9d
  signed int LastError; // eax
  DWORD v12; // eax
  void *v13; // rax
  const struct CTrkWksConfiguration *v14; // rdx
  __int64 v15; // [rsp+28h] [rbp-80h]
  _BYTE v16[48]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v17[16]; // [rsp+80h] [rbp-28h] BYREF
  _BYTE v18[24]; // [rsp+90h] [rbp-18h] BYREF

  CSystemSD::CSystemSD((CSystemSD *)v16);
  *((_DWORD *)this + 5) |= 1u;
  *((_QWORD *)this + 24) = v6;
  *((struct _FILETIME *)this + 23) = v7;
  *((_QWORD *)this + 25) = 0;
  CNewTimer::Initialize(
    (__int64)this + 24,
    (__int64)this,
    v7,
    v8,
    dword_18001B24C,
    v15,
    dword_18001B27C,
    dword_18001B264,
    dword_18001B294);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 21) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    TrkReportInternalError(0x71u, 0x49u, LastError, 0);
    v12 = GetLastError();
    TrkRaiseWin32Error(v12);
  }
  v13 = TrkRegisterWaitForSingleObjectEx(
          EventW,
          (void (*)(void *, unsigned __int8))EventW,
          (void *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          v10,
          0x11u);
  *((_QWORD *)this + 22) = v13;
  if ( !v13 )
    TrkRaiseLastError();
  CVolumeManager::InitializeVolumeList((const struct CTrkWksConfiguration **)this, v14, a4);
  SetEvent(*((HANDLE *)this + 21));
  CSID::UnInitialize((CSID *)v17);
  CSID::UnInitialize((CSID *)v18);
  CSecDescriptor::UnInitialize((CSecDescriptor *)v16);
  CSystemSD::~CSystemSD((CSystemSD *)v16);
}

```

## disassembly

```asm
0x18000a880  mov     [rsp+arg_0], rbx
0x18000a885  push    rdi
0x18000a886  sub     rsp, 0A0h
0x18000a88d  mov     rdi, r9
0x18000a890  mov     rbx, rcx
0x18000a893  lea     rcx, [rsp+0A8h+var_58]; this
0x18000a898  call    ??0CSystemSD@@QEAA@XZ; CSystemSD::CSystemSD(void)
0x18000a89d  or      dword ptr [rbx+14h], 1
0x18000a8a1  mov     [rbx+0C0h], rdx
0x18000a8a8  mov     [rbx+0B8h], r8
0x18000a8af  mov     qword ptr [rbx+0C8h], 0
0x18000a8ba  lea     rcx, [rbx+18h]
0x18000a8be  mov     eax, cs:dword_18001B294
0x18000a8c4  mov     [rsp+0A8h+var_68], eax
0x18000a8c8  mov     eax, cs:dword_18001B264
0x18000a8ce  mov     [rsp+0A8h+var_70], eax
0x18000a8d2  mov     eax, cs:dword_18001B27C
0x18000a8d8  mov     [rsp+0A8h+var_78], eax
0x18000a8dc  mov     eax, cs:dword_18001B24C
0x18000a8e2  mov     [rsp+0A8h+var_88], eax
0x18000a8e6  mov     rdx, rbx
0x18000a8e9  call    ?Initialize@CNewTimer@@QEAAXPEAVPTimerCallback@@PEBGKKW4TimerRetryType@1@KKK@Z; CNewTimer::Initialize(PTimerCallback *,ushort const *,ulong,ulong,CNewTimer::TimerRetryType,ulong,ulong,ulong)
0x18000a8ee  xor     r9d, r9d; lpName
0x18000a8f1  xor     r8d, r8d; bInitialState
0x18000a8f4  xor     edx, edx; bManualReset
0x18000a8f6  xor     ecx, ecx; lpEventAttributes
0x18000a8f8  call    cs:__imp_CreateEventW
0x18000a8fe  mov     rdx, rax; void (*)(void *, unsigned __int8)
0x18000a901  mov     [rbx+0A8h], rax
0x18000a908  test    rax, rax
0x18000a90b  jnz     short loc_18000A93E
0x18000a90d  call    cs:__imp_GetLastError
0x18000a913  test    eax, eax
0x18000a915  jle     short loc_18000A91F
0x18000a917  movzx   eax, ax
0x18000a91a  or      eax, 80070000h
0x18000a91f  xor     r9d, r9d; unsigned __int16 *
0x18000a922  mov     r8d, eax; int
0x18000a925  lea     edx, [r9+49h]; unsigned int
0x18000a929  lea     ecx, [rdx+28h]; unsigned int
0x18000a92c  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000a931  call    cs:__imp_GetLastError
0x18000a937  mov     ecx, eax; int
0x18000a939  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000a93e  mov     rax, rbx
0x18000a941  lea     rcx, [rbx+8]
0x18000a945  neg     rax
0x18000a948  sbb     r8, r8
0x18000a94b  and     r8, rcx; void *
0x18000a94e  mov     [rsp+0A8h+var_88], 11h; unsigned int
0x18000a956  mov     rcx, rdx; hObject
0x18000a959  call    ?TrkRegisterWaitForSingleObjectEx@@YAPEAXPEAXP6AX0E@Z0KK@Z; TrkRegisterWaitForSingleObjectEx(void *,void (*)(void *,uchar),void *,ulong,ulong)
0x18000a95e  mov     [rbx+0B0h], rax
0x18000a965  test    rax, rax
0x18000a968  jnz     short loc_18000A96F
0x18000a96a  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x18000a96f  mov     r8, rdi; struct SERVICE_STATUS_HANDLE__ *
0x18000a972  mov     rcx, rbx; this
0x18000a975  call    ?InitializeVolumeList@CVolumeManager@@AEAAXPEBVCTrkWksConfiguration@@PEAUSERVICE_STATUS_HANDLE__@@@Z; CVolumeManager::InitializeVolumeList(CTrkWksConfiguration const *,SERVICE_STATUS_HANDLE__ *)
0x18000a97a  mov     rcx, [rbx+0A8h]; hEvent
0x18000a981  call    cs:__imp_SetEvent
0x18000a987  nop
0x18000a988  lea     rcx, [rsp+0A8h+var_28]; this
0x18000a990  call    ?UnInitialize@CSID@@QEAAXXZ; CSID::UnInitialize(void)
0x18000a995  lea     rcx, [rsp+0A8h+var_18]; this
0x18000a99d  call    ?UnInitialize@CSID@@QEAAXXZ; CSID::UnInitialize(void)
0x18000a9a2  lea     rcx, [rsp+0A8h+var_58]; this
0x18000a9a7  call    ?UnInitialize@CSecDescriptor@@QEAAXXZ; CSecDescriptor::UnInitialize(void)
0x18000a9ac  lea     rcx, [rsp+0A8h+var_58]; this
0x18000a9b1  call    ??1CSystemSD@@QEAA@XZ; CSystemSD::~CSystemSD(void)
0x18000a9b6  mov     rbx, [rsp+0A8h+arg_0]
0x18000a9be  add     rsp, 0A0h
0x18000a9c5  pop     rdi
0x18000a9c6  retn
0x180011737  push    rbp
0x180011739  sub     rsp, 50h
0x18001173d  mov     rbp, rdx
0x180011740  lea     rcx, [rbp+50h]; this
0x180011744  call    ?UnInitialize@CSystemSD@@QEAAXXZ; CSystemSD::UnInitialize(void)
0x180011749  nop
0x18001174a  add     rsp, 50h
0x18001174e  pop     rbp
0x18001174f  retn
```
