# CRpcCallTrace::CRpcCallTrace(int,char const *)

- ea: `0x18000ba50`
- end: `0x18000bda1`
- name: `??0CRpcCallTrace@@QEAA@HPEBD@Z`
- size: `849`
- prototype: `CRpcCallTrace *__fastcall(CRpcCallTrace *__hidden this, int, const char *)`
- caller_count: `104`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010780`
- `0x180028520`
- `0x180028900`
- `0x180028fd0`
- `0x18002ad60`
- `0x18002b4b0`
- `0x18002be00`
- `0x18002c6c0`
- `0x18002d3a0`
- `0x18002d5f0`
- `0x18002e6d0`
- `0x18002e970`
- `0x18002ede0`
- `0x18002efd0`
- `0x180030440`
- `0x180030950`
- `0x180032a00`
- `0x180032bc0`
- `0x180032d90`
- `0x180032f60`
- `0x180033140`
- `0x18005da00`
- `0x18005de80`
- `0x18005e3f0`
- `0x18005e7f0`
- `0x18005ffe0`
- `0x180060420`
- `0x180060880`
- `0x180060ee0`
- `0x1800616a0`
- `0x180061860`
- `0x180061ab0`
- `0x180061d30`
- `0x180061fd0`
- `0x180062310`
- `0x180062560`
- `0x180062690`
- `0x1800628f0`
- `0x180062ae0`
- `0x180063030`
- `0x180063b80`
- `0x180063bf0`
- `0x180063c60`
- `0x180063cd0`
- `0x180063d40`
- `0x180063db0`
- `0x180063e20`
- `0x180063e90`
- `0x180063f00`
- `0x180063f70`

## callees

- `0x180009940`
- `0x18000ba50`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bd0a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bd0a`
- `ntdll!NtQueryInformationProcess` at `0x18000bcea`
- `ntdll!NtQueryInformationProcess` at `0x18000bcea`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000bb50`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000bb50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd39`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000bb22`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000bb22`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bcba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bcba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bab2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bab2`

## string_xrefs

- `0x18000bbfd`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000bd5f`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
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
0x18000ba50  mov     r11, rsp
0x18000ba53  push    rbx
0x18000ba54  push    rsi
0x18000ba55  push    rdi
0x18000ba56  push    r12
0x18000ba58  push    r14
0x18000ba5a  sub     rsp, 170h
0x18000ba61  mov     rax, cs:__security_cookie
0x18000ba68  xor     rax, rsp
0x18000ba6b  mov     [rsp+198h+var_48], rax
0x18000ba73  mov     [r11+10h], rbp
0x18000ba77  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000ba7e  mov     [r11-30h], r13
0x18000ba82  mov     edi, 1
0x18000ba87  xor     r13d, r13d
0x18000ba8a  mov     [rcx], rax
0x18000ba8d  mov     [rcx+20h], r13
0x18000ba91  mov     rbp, r8
0x18000ba94  mov     [rcx+1Ch], edi
0x18000ba97  mov     r12d, edx
0x18000ba9a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000baa1  mov     rbx, rcx
0x18000baa4  mov     [r11-38h], r15
0x18000baa8  jnz     loc_18000BBA1
0x18000baae  add     rcx, 8; pguid
0x18000bab2  call    cs:__imp_CoCreateGuid
0x18000bab9  nop     dword ptr [rax+rax+00h]
0x18000babe  lea     r15, [rbx+18h]
0x18000bac2  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, edi; ulong CTraceBase::g_NextShortActivityID
0x18000baca  inc     edi
0x18000bacc  mov     [r15], edi
0x18000bacf  mov     [rbx+28h], r13d
0x18000bad3  mov     [rbx+40h], r12d
0x18000bad7  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000bade  lea     r12, [rbx+44h]
0x18000bae2  mov     [rbx], rax
0x18000bae5  mov     rcx, r12; void *
0x18000bae8  mov     [rbx+30h], rbp
0x18000baec  xor     edx, edx; Val
0x18000baee  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x18000baf6  mov     r8d, 208h; Size
0x18000bafc  call    memset_0
0x18000bb01  cmp     [rbx+40h], r13d
0x18000bb05  jnz     loc_18000BC7C
0x18000bb0b  mov     ebp, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000bb11  lea     rdx, [rbx+3Ch]; Pid
0x18000bb15  xor     ecx, ecx; Binding
0x18000bb17  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x18000bb1f  and     ebp, 1
0x18000bb22  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000bb29  nop     dword ptr [rax+rax+00h]
0x18000bb2e  mov     r15, [rsp+198h+var_38]
0x18000bb36  mov     edi, eax
0x18000bb38  test    eax, eax
0x18000bb3a  jle     short loc_18000BB45
0x18000bb3c  movzx   edi, ax
0x18000bb3f  or      edi, 80070000h
0x18000bb45  test    edi, edi
0x18000bb47  js      short loc_18000BB64
0x18000bb49  mov     ecx, [rbx+3Ch]; dwProcessId
0x18000bb4c  lea     rdx, [rbx+38h]; pSessionId
0x18000bb50  call    cs:__imp_ProcessIdToSessionId
0x18000bb57  nop     dword ptr [rax+rax+00h]
0x18000bb5c  test    ebp, ebp
0x18000bb5e  jnz     loc_18000BCA6
0x18000bb64  cmp     dword ptr [rbx+40h], 0
0x18000bb68  mov     r13, [rsp+198h+var_30]
0x18000bb70  mov     rbp, [rsp+198h+arg_8]
0x18000bb78  jnz     loc_18000BD4A
0x18000bb7e  mov     rax, rbx
0x18000bb81  mov     rcx, [rsp+198h+var_48]
0x18000bb89  xor     rcx, rsp; StackCookie
0x18000bb8c  call    __security_check_cookie
0x18000bb91  add     rsp, 170h
0x18000bb98  pop     r14
0x18000bb9a  pop     r12
0x18000bb9c  pop     rdi
0x18000bb9d  pop     rsi
0x18000bb9e  pop     rbx
0x18000bb9f  retn
0x18000bba1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000bba8  jz      short loc_18000BBD7
0x18000bbaa  lea     rcx, aNull_0; "null"
0x18000bbb1  test    rbp, rbp
0x18000bbb4  mov     rax, rbp
0x18000bbb7  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000bbbe  cmovz   rax, rcx
0x18000bbc2  mov     r9d, edi
0x18000bbc5  mov     ecx, 2; int
0x18000bbca  mov     [rsp+198h+ReturnLength], rax
0x18000bbcf  mov     r8, rbx
0x18000bbd2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bbd7  lea     rcx, [rsp+198h+var_168]; struct CTraceBase **
0x18000bbdc  mov     [rsp+198h+var_168], r13
0x18000bbe1  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000bbe6  test    eax, eax
0x18000bbe8  js      short loc_18000BC0E
0x18000bbea  cmp     [rsp+198h+var_168], r13
0x18000bbef  jz      short loc_18000BC0E
0x18000bbf1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18000bbf8  jz      short loc_18000BC0E
0x18000bbfa  mov     r8d, edi
0x18000bbfd  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000bc04  mov     ecx, 2; int
0x18000bc09  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bc0e  xor     edx, edx; char *
0x18000bc10  xor     ecx, ecx; lpTlsValue
0x18000bc12  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000bc17  lea     rcx, [rbx+20h]; struct CTraceBase **
0x18000bc1b  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000bc20  test    eax, eax
0x18000bc22  js      short loc_18000BC5C
0x18000bc24  mov     rcx, [rbx+20h]
0x18000bc28  test    rcx, rcx
0x18000bc2b  jz      short loc_18000BC5C
0x18000bc2d  mov     rax, [rcx]
0x18000bc30  lea     rdx, [rbx+8]
0x18000bc34  mov     rax, [rax+20h]
0x18000bc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc3d  mov     rcx, [rbx+20h]
0x18000bc41  lea     r15, [rbx+18h]
0x18000bc45  mov     rax, [rcx]
0x18000bc48  mov     rax, [rax+18h]
0x18000bc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc51  mov     [r15], eax
0x18000bc54  mov     [rbx+28h], edi
0x18000bc57  jmp     loc_18000BAD3
0x18000bc5c  mov     rdx, rbp; char *
0x18000bc5f  mov     rcx, rbx; lpTlsValue
0x18000bc62  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000bc67  lea     r15, [rbx+18h]
0x18000bc6b  mov     rdx, r15; unsigned int *
0x18000bc6e  lea     rcx, [rbx+8]; struct _GUID *
0x18000bc72  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000bc77  jmp     loc_18000BACF
0x18000bc7c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bc83  jz      loc_18000BB0B
0x18000bc89  mov     r9d, [r15]
0x18000bc8c  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000bc93  mov     r8, [rbx+30h]
0x18000bc97  mov     ecx, 2; int
0x18000bc9c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bca1  jmp     loc_18000BB0B
0x18000bca6  test    r12, r12
0x18000bca9  jz      loc_18000BB64
0x18000bcaf  mov     r8d, [rbx+3Ch]; dwProcessId
0x18000bcb3  xor     edx, edx; bInheritHandle
0x18000bcb5  mov     ecx, 400h; dwDesiredAccess
0x18000bcba  call    cs:__imp_OpenProcess
0x18000bcc1  nop     dword ptr [rax+rax+00h]
0x18000bcc6  mov     rbp, rax
0x18000bcc9  test    rax, rax
0x18000bccc  jz      loc_18000BB64
0x18000bcd2  mov     r9d, 110h; ProcessInformationLength
0x18000bcd8  mov     [rsp+198h+ReturnLength], r13; ReturnLength
0x18000bcdd  lea     r8, [rsp+198h+ProcessInformation]; ProcessInformation
0x18000bce2  mov     edx, 1Bh; ProcessInformationClass
0x18000bce7  mov     rcx, rax; ProcessHandle
0x18000bcea  call    cs:__imp_NtQueryInformationProcess
0x18000bcf1  nop     dword ptr [rax+rax+00h]
0x18000bcf6  mov     edi, eax
0x18000bcf8  or      edi, 10000000h
0x18000bcfe  jl      short loc_18000BD36
0x18000bd00  mov     rcx, [rsp+198h+Str]; Str
0x18000bd05  mov     edx, 5Ch ; '\'; Ch
0x18000bd0a  call    cs:__imp_wcsrchr
0x18000bd11  nop     dword ptr [rax+rax+00h]
0x18000bd16  test    rax, rax
0x18000bd19  jnz     short loc_18000BD22
0x18000bd1b  mov     rax, [rsp+198h+Str]
0x18000bd20  jmp     short loc_18000BD26
0x18000bd22  add     rax, 2
0x18000bd26  mov     r8, rax; unsigned __int16 *
0x18000bd29  mov     edx, 104h; unsigned __int64
0x18000bd2e  mov     rcx, r12; unsigned __int16 *
0x18000bd31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bd36  mov     rcx, rbp; hObject
0x18000bd39  call    cs:__imp_CloseHandle
0x18000bd40  nop     dword ptr [rax+rax+00h]
0x18000bd45  jmp     loc_18000BB64
0x18000bd4a  test    edi, edi
0x18000bd4c  js      short loc_18000BD7E
0x18000bd4e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bd55  jz      loc_18000BB7E
0x18000bd5b  mov     r9d, [rbx+38h]
0x18000bd5f  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000bd66  mov     r8d, [rbx+3Ch]
0x18000bd6a  mov     ecx, 2; int
0x18000bd6f  mov     [rsp+198h+ReturnLength], r12
0x18000bd74  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bd79  jmp     loc_18000BB7E
0x18000bd7e  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000bd85  jz      loc_18000BB7E
0x18000bd8b  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000bd92  mov     ecx, 2; int
0x18000bd97  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bd9c  jmp     loc_18000BB7E
```
