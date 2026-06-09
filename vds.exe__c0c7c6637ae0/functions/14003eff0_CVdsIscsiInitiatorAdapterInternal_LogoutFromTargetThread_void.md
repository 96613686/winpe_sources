# CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread(void *)

- ea: `0x14003eff0`
- end: `0x14003f203`
- name: `?LogoutFromTargetThread@CVdsIscsiInitiatorAdapterInternal@@SAKPEAX@Z`
- size: `531`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14003eff0`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f1a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f1c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f1a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f1c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f062`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f062`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f0e2`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f10f`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f133`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f16a`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f0e2`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f10f`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f133`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14003f16a`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x14003f173`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x14003f173`
- `vdsutil!VdsHeapFree` at `0x14003f1b4`
- `vdsutil!VdsHeapFree` at `0x14003f1d0`
- `vdsutil!VdsHeapFree` at `0x14003f1b4`
- `vdsutil!VdsHeapFree` at `0x14003f1d0`
- `vdsutil!VdsTraceEx` at `0x14003f03b`
- `vdsutil!VdsTraceEx` at `0x14003f148`
- `vdsutil!VdsTraceEx` at `0x14003f03b`
- `vdsutil!VdsTraceEx` at `0x14003f148`
- `vdsutil!AcquireRundownProtection` at `0x14003f01f`
- `vdsutil!AcquireRundownProtection` at `0x14003f01f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003f011`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003f011`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003f1ee`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003f1ee`
- `vdsutil!VdsTraceW` at `0x14003f0c1`
- `vdsutil!VdsTraceW` at `0x14003f159`
- `vdsutil!VdsTraceW` at `0x14003f0c1`
- `vdsutil!VdsTraceW` at `0x14003f159`
- `vdsutil!ReleaseRundownProtection` at `0x14003f1e2`
- `vdsutil!ReleaseRundownProtection` at `0x14003f1e2`

## string_xrefs

- `0x14003f000`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread()`
- `0x14003f02c`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread exiting due to shutdown`
- `0x14003f150`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread: Could not access necessary function in iSCSI library.`
- `0x14003f0b8`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread: LogoutIScsiTarget failed: %X, session ID: %X:%X`
- `0x14003f139`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread, 1, hr=%lX`
- `0x14003f115`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread, 2, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread(CVdsAsyncObjectBase **Parameter)
{
  char v2; // r15
  int v3; // edx
  FARPROC ProcAddress; // rbp
  unsigned int v5; // ebx
  CVdsAsyncObjectBase *v6; // rsi
  unsigned int v7; // eax
  CVdsAsyncObjectBase *v8; // rcx
  unsigned int v9; // r8d
  CVdsAsyncObjectBase *v10; // rsi
  CVdsAsyncObjectBase *v11; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  _BYTE v15[72]; // [rsp+30h] [rbp-48h] BYREF

  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v15,
    0x5Eu,
    "CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread()");
  v2 = AcquireRundownProtection(&g_RundownRef);
  if ( !v2 )
  {
    VdsTraceEx(94, 3, "CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread exiting due to shutdown");
    v3 = -2146959352;
LABEL_19:
    v9 = 0;
    v8 = *Parameter;
LABEL_20:
    CVdsAsyncObjectBase::SetCompletionStatus(v8, v3, v9);
    goto LABEL_21;
  }
  if ( !CVdsService::m_hIscsidscModule
    || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "LogoutIScsiTarget")) == 0 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread: Could not access necessary function in iSCSI library.");
    v3 = -2147418113;
    goto LABEL_19;
  }
  v5 = 0;
  v6 = Parameter[2];
  if ( v6 )
  {
    do
    {
      v7 = ((__int64 (__fastcall *)(CVdsAsyncObjectBase *))ProcAddress)(v6);
      if ( v7 && ((v7 & 0xFFF0000) == 0 || (v7 & 0xC0000000) == 0xC0000000) )
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread: LogoutIScsiTarget failed: %X, session ID: %X:%X",
          v7,
          *(_QWORD *)v6,
          *((_QWORD *)v6 + 1));
      else
        ++v5;
      CVdsAsyncObjectBase::SetCompletionStatus(*Parameter, -2147212279, 100 * v5 / *((_DWORD *)Parameter + 2));
      v6 = (CVdsAsyncObjectBase *)*((_QWORD *)v6 + 2);
    }
    while ( v6 );
    if ( v5 )
    {
      v8 = *Parameter;
      if ( v5 < *((_DWORD *)Parameter + 2) )
      {
        CVdsAsyncObjectBase::SetCompletionStatus(v8, -2147211504, 100 * v5 / *((_DWORD *)Parameter + 2));
        VdsTraceEx(94, 0, "CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread, 2, hr=%lX", 2147755792LL);
        goto LABEL_21;
      }
      v3 = 0;
      v9 = 100;
      goto LABEL_20;
    }
  }
  CVdsAsyncObjectBase::SetCompletionStatus(*Parameter, -2147211511, 0);
  VdsTraceEx(94, 0, "CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread, 1, hr=%lX", 2147755785LL);
LABEL_21:
  CVdsAsyncObjectBase::Signal(*Parameter);
  if ( Parameter )
  {
    if ( *Parameter )
    {
      (*(void (__fastcall **)(CVdsAsyncObjectBase *))(*(_QWORD *)*Parameter + 16LL))(*Parameter);
      *Parameter = 0;
    }
    v10 = Parameter[2];
    if ( v10 )
    {
      do
      {
        v11 = (CVdsAsyncObjectBase *)*((_QWORD *)v10 + 2);
        ProcessHeap = GetProcessHeap();
        VdsHeapFree(ProcessHeap, 0, v10);
        v10 = v11;
      }
      while ( v11 );
    }
    v13 = GetProcessHeap();
    VdsHeapFree(v13, 0, Parameter);
  }
  if ( v2 )
    ReleaseRundownProtection(&g_RundownRef);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v15);
  return 0;
}

```

## disassembly

```asm
0x14003eff0  push    rbx
0x14003eff2  push    rbp
0x14003eff3  push    rsi
0x14003eff4  push    rdi
0x14003eff5  push    r14
0x14003eff7  push    r15
0x14003eff9  sub     rsp, 48h
0x14003effd  mov     rdi, rcx
0x14003f000  lea     r8, aCvdsiscsiiniti_103; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14003f007  mov     edx, 5Eh ; '^'
0x14003f00c  lea     rcx, [rsp+78h+var_48]
0x14003f011  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003f017  nop
0x14003f018  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14003f01f  call    cs:__imp_AcquireRundownProtection
0x14003f025  mov     r15b, al
0x14003f028  test    al, al
0x14003f02a  jnz     short loc_14003F04B
0x14003f02c  lea     r8, aCvdsiscsiiniti_32; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14003f033  mov     edx, 3
0x14003f038  lea     ecx, [rdx+5Bh]
0x14003f03b  call    cs:__imp_VdsTraceEx
0x14003f041  mov     edx, 80080008h
0x14003f046  jmp     loc_14003F164
0x14003f04b  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14003f052  test    rcx, rcx
0x14003f055  jz      loc_14003F150
0x14003f05b  lea     rdx, aLogoutiscsitar; "LogoutIScsiTarget"
0x14003f062  call    cs:__imp_GetProcAddress
0x14003f068  mov     rbp, rax
0x14003f06b  test    rax, rax
0x14003f06e  jz      loc_14003F150
0x14003f074  xor     ebx, ebx
0x14003f076  mov     rsi, [rdi+10h]
0x14003f07a  test    rsi, rsi
0x14003f07d  jz      loc_14003F126
0x14003f083  mov     rcx, rsi
0x14003f086  mov     rax, rbp
0x14003f089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f08e  test    eax, eax
0x14003f090  jz      short loc_14003F0C9
0x14003f092  test    eax, 0FFF0000h
0x14003f097  jz      short loc_14003F0A9
0x14003f099  mov     ecx, eax
0x14003f09b  and     ecx, 0C0000000h
0x14003f0a1  cmp     ecx, 0C0000000h
0x14003f0a7  jnz     short loc_14003F0C9
0x14003f0a9  mov     rcx, [rsi+8]
0x14003f0ad  mov     [rsp+78h+var_58], rcx
0x14003f0b2  mov     r9, [rsi]
0x14003f0b5  mov     r8d, eax
0x14003f0b8  lea     rdx, aCvdsiscsiiniti_65; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14003f0bf  xor     ecx, ecx
0x14003f0c1  call    cs:__imp_VdsTraceW
0x14003f0c7  jmp     short loc_14003F0CB
0x14003f0c9  inc     ebx
0x14003f0cb  imul    r14d, ebx, 64h ; 'd'
0x14003f0cf  xor     edx, edx
0x14003f0d1  mov     eax, r14d
0x14003f0d4  div     dword ptr [rdi+8]
0x14003f0d7  mov     r8d, eax
0x14003f0da  mov     edx, 80042409h
0x14003f0df  mov     rcx, [rdi]
0x14003f0e2  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14003f0e8  mov     rsi, [rsi+10h]
0x14003f0ec  test    rsi, rsi
0x14003f0ef  jnz     short loc_14003F083
0x14003f0f1  test    ebx, ebx
0x14003f0f3  jz      short loc_14003F126
0x14003f0f5  mov     rcx, [rdi]
0x14003f0f8  cmp     ebx, [rdi+8]
0x14003f0fb  jnb     short loc_14003F11E
0x14003f0fd  xor     edx, edx
0x14003f0ff  mov     eax, r14d
0x14003f102  div     dword ptr [rdi+8]
0x14003f105  mov     r8d, eax
0x14003f108  mov     ebx, 80042710h
0x14003f10d  mov     edx, ebx
0x14003f10f  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14003f115  lea     r8, aCvdsiscsiiniti_99; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14003f11c  jmp     short loc_14003F140
0x14003f11e  xor     edx, edx
0x14003f120  lea     r8d, [rdx+64h]
0x14003f124  jmp     short loc_14003F16A
0x14003f126  xor     r8d, r8d
0x14003f129  mov     ebx, 80042709h
0x14003f12e  mov     edx, ebx
0x14003f130  mov     rcx, [rdi]
0x14003f133  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14003f139  lea     r8, aCvdsiscsiiniti_16; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14003f140  mov     r9d, ebx
0x14003f143  xor     edx, edx
0x14003f145  lea     ecx, [rdx+5Eh]
0x14003f148  call    cs:__imp_VdsTraceEx
0x14003f14e  jmp     short loc_14003F170
0x14003f150  lea     rdx, aCvdsiscsiiniti_63; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14003f157  xor     ecx, ecx
0x14003f159  call    cs:__imp_VdsTraceW
0x14003f15f  mov     edx, 8000FFFFh
0x14003f164  xor     r8d, r8d
0x14003f167  mov     rcx, [rdi]
0x14003f16a  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14003f170  mov     rcx, [rdi]
0x14003f173  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x14003f179  test    rdi, rdi
0x14003f17c  jz      short loc_14003F1D6
0x14003f17e  mov     rcx, [rdi]
0x14003f181  test    rcx, rcx
0x14003f184  jz      short loc_14003F199
0x14003f186  mov     rax, [rcx]
0x14003f189  mov     rax, [rax+10h]
0x14003f18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f192  mov     qword ptr [rdi], 0
0x14003f199  mov     rsi, [rdi+10h]
0x14003f19d  test    rsi, rsi
0x14003f1a0  jz      short loc_14003F1C2
0x14003f1a2  mov     rbx, [rsi+10h]
0x14003f1a6  call    cs:__imp_GetProcessHeap
0x14003f1ac  mov     rcx, rax
0x14003f1af  mov     r8, rsi
0x14003f1b2  xor     edx, edx
0x14003f1b4  call    cs:__imp_VdsHeapFree
0x14003f1ba  mov     rsi, rbx
0x14003f1bd  test    rbx, rbx
0x14003f1c0  jnz     short loc_14003F1A2
0x14003f1c2  call    cs:__imp_GetProcessHeap
0x14003f1c8  mov     rcx, rax
0x14003f1cb  mov     r8, rdi
0x14003f1ce  xor     edx, edx
0x14003f1d0  call    cs:__imp_VdsHeapFree
0x14003f1d6  test    r15b, r15b
0x14003f1d9  jz      short loc_14003F1E9
0x14003f1db  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14003f1e2  call    cs:__imp_ReleaseRundownProtection
0x14003f1e8  nop
0x14003f1e9  lea     rcx, [rsp+78h+var_48]
0x14003f1ee  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003f1f4  xor     eax, eax
0x14003f1f6  add     rsp, 48h
0x14003f1fa  pop     r15
0x14003f1fc  pop     r14
0x14003f1fe  pop     rdi
0x14003f1ff  pop     rsi
0x14003f200  pop     rbp
0x14003f201  pop     rbx
0x14003f202  retn
```
