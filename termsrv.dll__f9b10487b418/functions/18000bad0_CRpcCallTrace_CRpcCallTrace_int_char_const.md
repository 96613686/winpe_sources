# CRpcCallTrace::CRpcCallTrace(int,char const *)

- ea: `0x18000bad0`
- end: `0x18000bdf6`
- name: `??0CRpcCallTrace@@QEAA@HPEBD@Z`
- size: `806`
- prototype: `CRpcCallTrace *__fastcall(CRpcCallTrace *__hidden this, int, const char *)`
- caller_count: `104`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010060`
- `0x180027100`
- `0x1800274e0`
- `0x180027b90`
- `0x180029740`
- `0x180029e40`
- `0x18002a700`
- `0x18002af60`
- `0x18002bb90`
- `0x18002bdc0`
- `0x18002cd30`
- `0x18002cfc0`
- `0x18002d3f0`
- `0x18002d5d0`
- `0x18002e920`
- `0x18002ee20`
- `0x180030d80`
- `0x180030f30`
- `0x1800310f0`
- `0x1800312b0`
- `0x180031490`
- `0x18005acd0`
- `0x18005b120`
- `0x18005b650`
- `0x18005ba40`
- `0x18005d110`
- `0x18005d530`
- `0x18005d970`
- `0x18005df80`
- `0x18005e710`
- `0x18005e8c0`
- `0x18005eaf0`
- `0x18005ed60`
- `0x18005efe0`
- `0x18005f310`
- `0x18005f550`
- `0x18005f670`
- `0x18005f8d0`
- `0x18005fab0`
- `0x18005fff0`
- `0x180060ac0`
- `0x180060b30`
- `0x180060ba0`
- `0x180060c10`
- `0x180060c80`
- `0x180060cf0`
- `0x180060d60`
- `0x180060dd0`
- `0x180060e40`
- `0x180060eb0`

## callees

- `0x18000a210`
- `0x18000bad0`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bd6b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bd6b`
- `ntdll!NtQueryInformationProcess` at `0x18000bd51`
- `ntdll!NtQueryInformationProcess` at `0x18000bd51`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000bbc4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000bbc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd94`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000bb9c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000bb9c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bd27`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bd27`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bb32`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bb32`

## string_xrefs

- `0x18000bc6a`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000bdb4`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRpcCallTrace *__fastcall CRpcCallTrace::CRpcCallTrace(CRpcCallTrace *this, int a2, const char *a3)
{
  _DWORD *v6; // r15
  char v7; // bp
  int v8; // ebp
  RPC_STATUS v9; // eax
  int v10; // edi
  const char *v12; // rax
  __int64 v13; // rcx
  HANDLE v14; // rax
  void *v15; // rbp
  NTSTATUS InformationProcess; // eax
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  struct CTraceBase *v19; // [rsp+30h] [rbp-168h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+40h] [rbp-158h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-150h]

  *(_QWORD *)this = &CTraceBase::`vftable';
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 7) = 1;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
    {
      v12 = a3;
      if ( !a3 )
        v12 = "null";
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", this, 1, v12);
    }
    v19 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v19) >= 0 && v19 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace((struct CTraceBase **)this + 4) >= 0 )
    {
      v13 = *((_QWORD *)this + 4);
      if ( v13 )
      {
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 32LL))(v13, (char *)this + 8);
        v6 = (_DWORD *)((char *)this + 24);
        *((_DWORD *)this + 6) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4));
        *((_DWORD *)this + 10) = 1;
        goto LABEL_4;
      }
    }
    CTraceBase::ResetThreadCurrentOperationTrace(this, a3);
    v6 = (_DWORD *)((char *)this + 24);
    CTraceBase::GenerateTraceID((struct _GUID *)((char *)this + 8), (unsigned int *)this + 6);
  }
  else
  {
    CoCreateGuid((GUID *)((char *)this + 8));
    v6 = (_DWORD *)((char *)this + 24);
    *((_DWORD *)this + 6) = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  *((_DWORD *)this + 10) = 0;
LABEL_4:
  *((_DWORD *)this + 16) = a2;
  *(_QWORD *)this = &CRpcCallTrace::`vftable';
  *((_QWORD *)this + 6) = a3;
  *((_QWORD *)this + 7) = -1;
  memset_0((char *)this + 68, 0, 0x208u);
  if ( *((_DWORD *)this + 16) && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", *((const char **)this + 6), *v6);
  v7 = g_DebugTraceComponent;
  *((_QWORD *)this + 7) = -1;
  v8 = v7 & 1;
  v9 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)this + 15);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    ProcessIdToSessionId(*((_DWORD *)this + 15), (DWORD *)this + 14);
    if ( v8 )
    {
      if ( this != (CRpcCallTrace *)-68LL )
      {
        v14 = OpenProcess(0x400u, 0, *((_DWORD *)this + 15));
        v15 = v14;
        if ( v14 )
        {
          InformationProcess = NtQueryInformationProcess(v14, ProcessImageFileName, ProcessInformation, 0x110u, 0);
          v10 = InformationProcess | 0x10000000;
          if ( InformationProcess >= 0 )
          {
            v17 = wcsrchr(Str, 0x5Cu);
            if ( v17 )
              v18 = v17 + 1;
            else
              v18 = Str;
            StringCchCopyW((unsigned __int16 *)this + 34, 0x104u, v18);
          }
          CloseHandle(v15);
        }
      }
    }
  }
  if ( *((_DWORD *)this + 16) )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(
        2,
        "RPC Caller: PID %d, SessID %d, Process Name: <%S>",
        *((_DWORD *)this + 15),
        *((_DWORD *)this + 14),
        (const wchar_t *)this + 34);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000bad0  mov     r11, rsp
0x18000bad3  push    rbx
0x18000bad4  push    rsi
0x18000bad5  push    rdi
0x18000bad6  push    r12
0x18000bad8  push    r14
0x18000bada  sub     rsp, 170h
0x18000bae1  mov     rax, cs:__security_cookie
0x18000bae8  xor     rax, rsp
0x18000baeb  mov     [rsp+198h+var_48], rax
0x18000baf3  mov     [r11+10h], rbp
0x18000baf7  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000bafe  mov     [r11-30h], r13
0x18000bb02  mov     edi, 1
0x18000bb07  xor     r13d, r13d
0x18000bb0a  mov     [rcx], rax
0x18000bb0d  mov     [rcx+20h], r13
0x18000bb11  mov     rbp, r8
0x18000bb14  mov     [rcx+1Ch], edi
0x18000bb17  mov     r12d, edx
0x18000bb1a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000bb21  mov     rbx, rcx
0x18000bb24  mov     [r11-38h], r15
0x18000bb28  jnz     loc_18000BC0E
0x18000bb2e  add     rcx, 8; pguid
0x18000bb32  call    cs:__imp_CoCreateGuid
0x18000bb38  lea     r15, [rbx+18h]
0x18000bb3c  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, edi; ulong CTraceBase::g_NextShortActivityID
0x18000bb44  inc     edi
0x18000bb46  mov     [r15], edi
0x18000bb49  mov     [rbx+28h], r13d
0x18000bb4d  mov     [rbx+40h], r12d
0x18000bb51  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000bb58  lea     r12, [rbx+44h]
0x18000bb5c  mov     [rbx], rax
0x18000bb5f  mov     rcx, r12; void *
0x18000bb62  mov     [rbx+30h], rbp
0x18000bb66  xor     edx, edx; Val
0x18000bb68  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x18000bb70  mov     r8d, 208h; Size
0x18000bb76  call    memset_0
0x18000bb7b  cmp     [rbx+40h], r13d
0x18000bb7f  jnz     loc_18000BCE9
0x18000bb85  mov     ebp, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000bb8b  lea     rdx, [rbx+3Ch]; Pid
0x18000bb8f  xor     ecx, ecx; Binding
0x18000bb91  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x18000bb99  and     ebp, 1
0x18000bb9c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000bba2  mov     r15, [rsp+198h+var_38]
0x18000bbaa  mov     edi, eax
0x18000bbac  test    eax, eax
0x18000bbae  jle     short loc_18000BBB9
0x18000bbb0  movzx   edi, ax
0x18000bbb3  or      edi, 80070000h
0x18000bbb9  test    edi, edi
0x18000bbbb  js      short loc_18000BBD2
0x18000bbbd  mov     ecx, [rbx+3Ch]; dwProcessId
0x18000bbc0  lea     rdx, [rbx+38h]; pSessionId
0x18000bbc4  call    cs:__imp_ProcessIdToSessionId
0x18000bbca  test    ebp, ebp
0x18000bbcc  jnz     loc_18000BD13
0x18000bbd2  cmp     dword ptr [rbx+40h], 0
0x18000bbd6  mov     r13, [rsp+198h+var_30]
0x18000bbde  mov     rbp, [rsp+198h+arg_8]
0x18000bbe6  jnz     loc_18000BD9F
0x18000bbec  mov     rax, rbx
0x18000bbef  mov     rcx, [rsp+198h+var_48]
0x18000bbf7  xor     rcx, rsp; StackCookie
0x18000bbfa  call    __security_check_cookie
0x18000bbff  add     rsp, 170h
0x18000bc06  pop     r14
0x18000bc08  pop     r12
0x18000bc0a  pop     rdi
0x18000bc0b  pop     rsi
0x18000bc0c  pop     rbx
0x18000bc0d  retn
0x18000bc0e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000bc15  jz      short loc_18000BC44
0x18000bc17  lea     rcx, aNull_0; "null"
0x18000bc1e  test    rbp, rbp
0x18000bc21  mov     rax, rbp
0x18000bc24  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000bc2b  cmovz   rax, rcx
0x18000bc2f  mov     r9d, edi
0x18000bc32  mov     ecx, 2; int
0x18000bc37  mov     [rsp+198h+ReturnLength], rax
0x18000bc3c  mov     r8, rbx
0x18000bc3f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bc44  lea     rcx, [rsp+198h+var_168]; struct CTraceBase **
0x18000bc49  mov     [rsp+198h+var_168], r13
0x18000bc4e  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000bc53  test    eax, eax
0x18000bc55  js      short loc_18000BC7B
0x18000bc57  cmp     [rsp+198h+var_168], r13
0x18000bc5c  jz      short loc_18000BC7B
0x18000bc5e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000bc65  jz      short loc_18000BC7B
0x18000bc67  mov     r8d, edi
0x18000bc6a  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000bc71  mov     ecx, 2; int
0x18000bc76  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bc7b  xor     edx, edx; char *
0x18000bc7d  xor     ecx, ecx; lpTlsValue
0x18000bc7f  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000bc84  lea     rcx, [rbx+20h]; struct CTraceBase **
0x18000bc88  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000bc8d  test    eax, eax
0x18000bc8f  js      short loc_18000BCC9
0x18000bc91  mov     rcx, [rbx+20h]
0x18000bc95  test    rcx, rcx
0x18000bc98  jz      short loc_18000BCC9
0x18000bc9a  mov     rax, [rcx]
0x18000bc9d  lea     rdx, [rbx+8]
0x18000bca1  mov     rax, [rax+20h]
0x18000bca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcaa  mov     rcx, [rbx+20h]
0x18000bcae  lea     r15, [rbx+18h]
0x18000bcb2  mov     rax, [rcx]
0x18000bcb5  mov     rax, [rax+18h]
0x18000bcb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcbe  mov     [r15], eax
0x18000bcc1  mov     [rbx+28h], edi
0x18000bcc4  jmp     loc_18000BB4D
0x18000bcc9  mov     rdx, rbp; char *
0x18000bccc  mov     rcx, rbx; lpTlsValue
0x18000bccf  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000bcd4  lea     r15, [rbx+18h]
0x18000bcd8  mov     rdx, r15; unsigned int *
0x18000bcdb  lea     rcx, [rbx+8]; struct _GUID *
0x18000bcdf  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000bce4  jmp     loc_18000BB49
0x18000bce9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bcf0  jz      loc_18000BB85
0x18000bcf6  mov     r9d, [r15]
0x18000bcf9  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000bd00  mov     r8, [rbx+30h]
0x18000bd04  mov     ecx, 2; int
0x18000bd09  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bd0e  jmp     loc_18000BB85
0x18000bd13  test    r12, r12
0x18000bd16  jz      loc_18000BBD2
0x18000bd1c  mov     r8d, [rbx+3Ch]; dwProcessId
0x18000bd20  xor     edx, edx; bInheritHandle
0x18000bd22  mov     ecx, 400h; dwDesiredAccess
0x18000bd27  call    cs:__imp_OpenProcess
0x18000bd2d  mov     rbp, rax
0x18000bd30  test    rax, rax
0x18000bd33  jz      loc_18000BBD2
0x18000bd39  mov     r9d, 110h; ProcessInformationLength
0x18000bd3f  mov     [rsp+198h+ReturnLength], r13; ReturnLength
0x18000bd44  lea     r8, [rsp+198h+ProcessInformation]; ProcessInformation
0x18000bd49  mov     edx, 1Bh; ProcessInformationClass
0x18000bd4e  mov     rcx, rax; ProcessHandle
0x18000bd51  call    cs:__imp_NtQueryInformationProcess
0x18000bd57  mov     edi, eax
0x18000bd59  or      edi, 10000000h
0x18000bd5f  jl      short loc_18000BD91
0x18000bd61  mov     rcx, [rsp+198h+Str]; Str
0x18000bd66  mov     edx, 5Ch ; '\'; Ch
0x18000bd6b  call    cs:__imp_wcsrchr
0x18000bd71  test    rax, rax
0x18000bd74  jnz     short loc_18000BD7D
0x18000bd76  mov     rax, [rsp+198h+Str]
0x18000bd7b  jmp     short loc_18000BD81
0x18000bd7d  add     rax, 2
0x18000bd81  mov     r8, rax; unsigned __int16 *
0x18000bd84  mov     edx, 104h; unsigned __int64
0x18000bd89  mov     rcx, r12; unsigned __int16 *
0x18000bd8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bd91  mov     rcx, rbp; hObject
0x18000bd94  call    cs:__imp_CloseHandle
0x18000bd9a  jmp     loc_18000BBD2
0x18000bd9f  test    edi, edi
0x18000bda1  js      short loc_18000BDD3
0x18000bda3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bdaa  jz      loc_18000BBEC
0x18000bdb0  mov     r9d, [rbx+38h]
0x18000bdb4  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000bdbb  mov     r8d, [rbx+3Ch]
0x18000bdbf  mov     ecx, 2; int
0x18000bdc4  mov     [rsp+198h+ReturnLength], r12
0x18000bdc9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bdce  jmp     loc_18000BBEC
0x18000bdd3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bdda  jz      loc_18000BBEC
0x18000bde0  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000bde7  mov     ecx, 2; int
0x18000bdec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bdf1  jmp     loc_18000BBEC
```
