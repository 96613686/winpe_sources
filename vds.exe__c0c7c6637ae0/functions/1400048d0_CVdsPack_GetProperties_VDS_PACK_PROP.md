# CVdsPack::GetProperties(_VDS_PACK_PROP *)

- ea: `0x1400048d0`
- end: `0x140004a78`
- name: `?GetProperties@CVdsPack@@UEAAJPEAU_VDS_PACK_PROP@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(CVdsPack *__hidden this, struct _VDS_PACK_PROP *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003710`
- `0x1400048d0`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400049fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400049fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1400049b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1400049b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004978`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400049c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004a0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004978`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400049c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004a0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004955`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004999`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004955`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000493a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000493a`
- `vdsutil!AcquireRundownProtection` at `0x140004923`
- `vdsutil!AcquireRundownProtection` at `0x140004923`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400048f9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400048f9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400049d3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400049d3`
- `vdsutil!ReleaseRundownProtection` at `0x140004a36`
- `vdsutil!ReleaseRundownProtection` at `0x140004a36`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsPack::GetProperties(CVdsPack *this, struct _VDS_PACK_PROP *a2)
{
  int v4; // esi
  int v5; // edi
  int v6; // eax
  signed int v7; // ebx
  signed int LastError; // eax
  __int64 v10; // [rsp+20h] [rbp-38h] BYREF
  int v11; // [rsp+28h] [rbp-30h]
  _BYTE v12[40]; // [rsp+30h] [rbp-28h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v12, 0x5Eu, "CVdsPack::GetProperties()");
  a2->id = 0;
  *(_OWORD *)&a2->pwszName = 0;
  v10 = 0;
  v4 = 0;
  v5 = 0;
  v11 = 0;
  if ( (unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    v5 = 1;
    v11 = 1;
    if ( g_dwThreadIdExclusiveLock == GetCurrentThreadId() )
    {
LABEL_16:
      v7 = (*(__int64 (__fastcall **)(_QWORD, struct _VDS_PACK_PROP *))(**((_QWORD **)this + 11) + 24LL))(
             *((_QWORD *)this + 11),
             a2);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v10);
      goto LABEL_12;
    }
    EnterCriticalSection(&g_OpsInFlight);
    v6 = g_lOperationsInFly;
    if ( g_lOperationsInFly )
      goto LABEL_4;
    if ( !WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF) )
    {
      v6 = g_lOperationsInFly;
LABEL_4:
      g_lOperationsInFly = v6 + 1;
      LeaveCriticalSection(&g_OpsInFlight);
      v7 = 0;
      v4 = 1;
      HIDWORD(v10) = 1;
      goto LABEL_5;
    }
    LeaveCriticalSection(&g_OpsInFlight);
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = -2146959352;
  }
LABEL_5:
  if ( v7 >= 0 )
    goto LABEL_16;
  if ( v4 )
  {
    EnterCriticalSection(&g_OpsInFlight);
    if ( !--g_lOperationsInFly )
      ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
    LeaveCriticalSection(&g_OpsInFlight);
  }
  if ( v5 )
    ReleaseRundownProtection(&g_RundownRef);
LABEL_12:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400048d0  mov     [rsp+arg_0], rbx
0x1400048d5  mov     [rsp+arg_8], rbp
0x1400048da  push    rsi
0x1400048db  push    rdi
0x1400048dc  push    r14
0x1400048de  sub     rsp, 40h
0x1400048e2  mov     rbp, rdx
0x1400048e5  mov     r14, rcx
0x1400048e8  lea     r8, aCvdspackGetpro; "CVdsPack::GetProperties()"
0x1400048ef  mov     edx, 5Eh ; '^'
0x1400048f4  lea     rcx, [rsp+58h+var_28]
0x1400048f9  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400048ff  nop
0x140004900  xorps   xmm0, xmm0
0x140004903  movups  xmmword ptr [rbp+0], xmm0
0x140004907  movups  xmmword ptr [rbp+10h], xmm0
0x14000490b  mov     [rsp+58h+var_38], 0
0x140004914  xor     esi, esi
0x140004916  xor     edi, edi
0x140004918  mov     [rsp+58h+var_30], edi
0x14000491c  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140004923  call    cs:__imp_AcquireRundownProtection
0x140004929  test    al, al
0x14000492b  jz      loc_140004A6D
0x140004931  mov     edi, 1
0x140004936  mov     [rsp+58h+var_30], edi
0x14000493a  call    cs:__imp_GetCurrentThreadId
0x140004940  mov     ecx, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x140004946  cmp     ecx, eax
0x140004948  jz      loc_140004A3E
0x14000494e  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004955  call    cs:__imp_EnterCriticalSection
0x14000495b  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140004961  test    eax, eax
0x140004963  jz      loc_1400049EE
0x140004969  inc     eax
0x14000496b  mov     cs:?g_lOperationsInFly@@3JA, eax; long g_lOperationsInFly
0x140004971  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004978  call    cs:__imp_LeaveCriticalSection
0x14000497e  xor     ebx, ebx
0x140004980  mov     esi, edi
0x140004982  mov     dword ptr [rsp+58h+var_38+4], edi
0x140004986  test    ebx, ebx
0x140004988  jns     loc_140004A3E
0x14000498e  test    esi, esi
0x140004990  jz      short loc_1400049CA
0x140004992  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004999  call    cs:__imp_EnterCriticalSection
0x14000499f  sub     cs:?g_lOperationsInFly@@3JA, 1; long g_lOperationsInFly
0x1400049a6  jnz     short loc_1400049BD
0x1400049a8  xor     r8d, r8d; lpPreviousCount
0x1400049ab  mov     edx, 1; lReleaseCount
0x1400049b0  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x1400049b7  call    cs:__imp_ReleaseSemaphore
0x1400049bd  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400049c4  call    cs:__imp_LeaveCriticalSection
0x1400049ca  test    edi, edi
0x1400049cc  jnz     short loc_140004A2F
0x1400049ce  lea     rcx, [rsp+58h+var_28]
0x1400049d3  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400049d9  mov     eax, ebx
0x1400049db  mov     rbx, [rsp+58h+arg_0]
0x1400049e0  mov     rbp, [rsp+58h+arg_8]
0x1400049e5  add     rsp, 40h
0x1400049e9  pop     r14
0x1400049eb  pop     rdi
0x1400049ec  pop     rsi
0x1400049ed  retn
0x1400049ee  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1400049f3  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x1400049fa  call    cs:__imp_WaitForSingleObject
0x140004a00  test    eax, eax
0x140004a02  jz      short loc_140004A62
0x140004a04  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004a0b  call    cs:__imp_LeaveCriticalSection
0x140004a11  call    cs:__imp_GetLastError
0x140004a17  mov     ebx, eax
0x140004a19  test    eax, eax
0x140004a1b  jle     loc_140004986
0x140004a21  movzx   ebx, ax
0x140004a24  or      ebx, 80070000h
0x140004a2a  jmp     loc_140004986
0x140004a2f  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140004a36  call    cs:__imp_ReleaseRundownProtection
0x140004a3c  jmp     short loc_1400049CE
0x140004a3e  mov     rcx, [r14+58h]
0x140004a42  mov     rax, [rcx]
0x140004a45  mov     rdx, rbp
0x140004a48  mov     rax, [rax+18h]
0x140004a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a51  mov     ebx, eax
0x140004a53  lea     rcx, [rsp+58h+var_38]; this
0x140004a58  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140004a5d  jmp     loc_1400049CE
0x140004a62  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140004a68  jmp     loc_140004969
0x140004a6d  mov     ebx, 80080008h
0x140004a72  jmp     loc_140004986
```
