# CSmartSession::Open(ulong,void *)

- ea: `0x1800039e8`
- end: `0x180003ace`
- name: `?Open@CSmartSession@@QEAAJKPEAX@Z`
- size: `230`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, unsigned int, void *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800046ec`
- `0x1800067b0`
- `0x18000ce54`
- `0x180011458`
- `0x1800207f4`
- `0x180027b30`
- `0x180028470`

## callees

- `0x1800039e8`
- `0x180007890`
- `0x180011368`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800039fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003aa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800039fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003aa2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030066`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030066`
- `RPCRT4!NdrClientCall3` at `0x180003a46`
- `RPCRT4!NdrClientCall3` at `0x180003a46`

## string_xrefs

- `0x180003aad`: `RpcOpenSession() takes %d`
- `0x180003a0c`: `Open session on %d`
- `0x180003a8d`: `RpcOpenSession threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CSmartSession::Open(CSmartSession *this, int a2, void *a3)
{
  DWORD TickCount; // edi
  unsigned int Pointer; // ebx
  DWORD v8; // eax
  int v10; // [rsp+20h] [rbp-38h]

  TickCount = GetTickCount();
  _DbgPrintMessage(1, "Open session on %d", a2);
  *((_DWORD *)this + 2) = a2;
  if ( a2 == -1 )
  {
    Pointer = RpcOpenSession(a3, NtCurrentPeb()->SessionId, this);
  }
  else
  {
    v10 = a2;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032200, 0, 0, a3, v10, this).Pointer;
  }
  v8 = GetTickCount();
  _DbgPrintMessage(1, "RpcOpenSession() takes %d", v8 - TickCount);
  return Pointer;
}

```

## disassembly

```asm
0x1800039e8  mov     [rsp+arg_10], rbx
0x1800039ed  push    rsi
0x1800039ee  push    rdi
0x1800039ef  push    r14
0x1800039f1  sub     rsp, 40h
0x1800039f5  mov     r14, r8
0x1800039f8  mov     ebx, edx
0x1800039fa  mov     rsi, rcx
0x1800039fd  call    cs:__imp_GetTickCount
0x180003a03  mov     edi, eax
0x180003a05  mov     [rsp+58h+arg_8], eax
0x180003a09  mov     r8d, ebx
0x180003a0c  lea     rdx, aOpenSessionOnD; "Open session on %d"
0x180003a13  mov     ecx, 1; int
0x180003a18  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003a1d  mov     [rsi+8], ebx
0x180003a20  cmp     ebx, 0FFFFFFFFh
0x180003a23  jz      short loc_180003A56
0x180003a25  mov     [rsp+58h+arg_0], 0
0x180003a2e  mov     [rsp+58h+var_30], rsi
0x180003a33  mov     [rsp+58h+var_38], ebx
0x180003a37  mov     r9, r14
0x180003a3a  xor     r8d, r8d; pReturnValue
0x180003a3d  xor     edx, edx; nProcNum
0x180003a3f  lea     rcx, stru_180032200; pProxyInfo
0x180003a46  call    cs:__imp_NdrClientCall3
0x180003a4c  mov     rbx, rax
0x180003a4f  mov     [rsp+58h+arg_0], rax
0x180003a54  jmp     short loc_180003A72
0x180003a56  mov     rdx, gs:60h
0x180003a5f  mov     r8, rsi
0x180003a62  mov     edx, [rdx+2C0h]
0x180003a68  mov     rcx, r14
0x180003a6b  call    RpcOpenSession
0x180003a70  mov     ebx, eax
0x180003a72  mov     [rsp+58h+var_28], eax
0x180003a76  jmp     short loc_180003AA2
0x180003a78  test    eax, eax
0x180003a7a  jle     short loc_180003A84
0x180003a7c  movzx   eax, ax
0x180003a7f  or      eax, 80070000h
0x180003a84  mov     ebx, eax
0x180003a86  mov     [rsp+58h+var_28], eax
0x180003a8a  mov     r8d, eax
0x180003a8d  lea     rdx, aRpcopensession_0; "RpcOpenSession threw an exception: 0x%x"
0x180003a94  mov     ecx, 8; int
0x180003a99  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003a9e  mov     edi, [rsp+58h+arg_8]
0x180003aa2  call    cs:__imp_GetTickCount
0x180003aa8  sub     eax, edi
0x180003aaa  mov     r8d, eax
0x180003aad  lea     rdx, aRpcopensession; "RpcOpenSession() takes %d"
0x180003ab4  mov     ecx, 1; int
0x180003ab9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003abe  mov     eax, ebx
0x180003ac0  mov     rbx, [rsp+58h+arg_10]
0x180003ac5  add     rsp, 40h
0x180003ac9  pop     r14
0x180003acb  pop     rdi
0x180003acc  pop     rsi
0x180003acd  retn
0x180030058  push    rbp
0x18003005a  sub     rsp, 30h
0x18003005e  mov     rbp, rdx
0x180030061  mov     rcx, [rcx]
0x180030064  mov     ecx, [rcx]; ExceptionCode
0x180030066  call    cs:__imp_I_RpcExceptionFilter
0x18003006c  nop
0x18003006d  add     rsp, 30h
0x180030071  pop     rbp
0x180030072  retn
```
