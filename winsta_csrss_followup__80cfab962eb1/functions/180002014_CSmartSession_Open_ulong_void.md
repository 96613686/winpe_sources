# CSmartSession::Open(ulong,void *)

- ea: `0x180002014`
- end: `0x18000210d`
- name: `?Open@CSmartSession@@QEAAJKPEAX@Z`
- size: `249`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, unsigned int, void *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180001524`
- `0x180002114`
- `0x1800049a0`
- `0x180009dec`
- `0x180021fa4`
- `0x180029610`
- `0x180029ff0`

## callees

- `0x180001694`
- `0x180002014`
- `0x180005b40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002029`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002029`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020da`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032de1`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032de1`
- `RPCRT4!NdrClientCall3` at `0x180002078`
- `RPCRT4!NdrClientCall3` at `0x180002078`

## string_xrefs

- `0x1800020eb`: `RpcOpenSession() takes %d`
- `0x18000203e`: `Open session on %d`
- `0x1800020c5`: `RpcOpenSession threw an exception: 0x%x`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a3, v10, this).Pointer;
  }
  v8 = GetTickCount();
  _DbgPrintMessage(1, "RpcOpenSession() takes %d", v8 - TickCount);
  return Pointer;
}

```

## disassembly

```asm
0x180002014  mov     [rsp+arg_10], rbx
0x180002019  push    rsi
0x18000201a  push    rdi
0x18000201b  push    r14
0x18000201d  sub     rsp, 40h
0x180002021  mov     r14, r8
0x180002024  mov     ebx, edx
0x180002026  mov     rsi, rcx
0x180002029  call    cs:__imp_GetTickCount
0x180002030  nop     dword ptr [rax+rax+00h]
0x180002035  mov     edi, eax
0x180002037  mov     [rsp+58h+arg_8], eax
0x18000203b  mov     r8d, ebx
0x18000203e  lea     rdx, aOpenSessionOnD; "Open session on %d"
0x180002045  mov     ecx, 1; int
0x18000204a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000204f  mov     [rsi+8], ebx
0x180002052  cmp     ebx, 0FFFFFFFFh
0x180002055  jz      short loc_18000208E
0x180002057  mov     [rsp+58h+arg_0], 0
0x180002060  mov     [rsp+58h+var_30], rsi
0x180002065  mov     [rsp+58h+var_38], ebx
0x180002069  mov     r9, r14
0x18000206c  xor     r8d, r8d; pReturnValue
0x18000206f  xor     edx, edx; nProcNum
0x180002071  lea     rcx, pProxyInfo; pProxyInfo
0x180002078  call    cs:__imp_NdrClientCall3
0x18000207f  nop     dword ptr [rax+rax+00h]
0x180002084  mov     rbx, rax
0x180002087  mov     [rsp+58h+arg_0], rax
0x18000208c  jmp     short loc_1800020AA
0x18000208e  mov     rdx, gs:60h
0x180002097  mov     r8, rsi
0x18000209a  mov     edx, [rdx+2C0h]
0x1800020a0  mov     rcx, r14
0x1800020a3  call    RpcOpenSession
0x1800020a8  mov     ebx, eax
0x1800020aa  mov     [rsp+58h+var_28], eax
0x1800020ae  jmp     short loc_1800020DA
0x1800020b0  test    eax, eax
0x1800020b2  jle     short loc_1800020BC
0x1800020b4  movzx   eax, ax
0x1800020b7  or      eax, 80070000h
0x1800020bc  mov     ebx, eax
0x1800020be  mov     [rsp+58h+var_28], eax
0x1800020c2  mov     r8d, eax
0x1800020c5  lea     rdx, aRpcopensession_0; "RpcOpenSession threw an exception: 0x%x"
0x1800020cc  mov     ecx, 8; int
0x1800020d1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800020d6  mov     edi, [rsp+58h+arg_8]
0x1800020da  call    cs:__imp_GetTickCount
0x1800020e1  nop     dword ptr [rax+rax+00h]
0x1800020e6  sub     eax, edi
0x1800020e8  mov     r8d, eax
0x1800020eb  lea     rdx, aRpcopensession; "RpcOpenSession() takes %d"
0x1800020f2  mov     ecx, 1; int
0x1800020f7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800020fc  mov     eax, ebx
0x1800020fe  mov     rbx, [rsp+58h+arg_10]
0x180002103  add     rsp, 40h
0x180002107  pop     r14
0x180002109  pop     rdi
0x18000210a  pop     rsi
0x18000210b  retn
0x180032dd3  push    rbp
0x180032dd5  sub     rsp, 30h
0x180032dd9  mov     rbp, rdx
0x180032ddc  mov     rcx, [rcx]
0x180032ddf  mov     ecx, [rcx]; ExceptionCode
0x180032de1  call    cs:__imp_I_RpcExceptionFilter
0x180032de8  nop     dword ptr [rax+rax+00h]
0x180032ded  nop
0x180032dee  add     rsp, 30h
0x180032df2  pop     rbp
0x180032df3  retn
```
