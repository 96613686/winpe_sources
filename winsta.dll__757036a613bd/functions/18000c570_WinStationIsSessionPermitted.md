# WinStationIsSessionPermitted

- ea: `0x18000c570`
- end: `0x18000c6a6`
- name: `WinStationIsSessionPermitted`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005db0`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000c570`
- `0x18000c6b0`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c68a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c673`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003056e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003056e`
- `RPCRT4!NdrClientCall3` at `0x18000c61a`
- `RPCRT4!NdrClientCall3` at `0x18000c61a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000c584`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000c584`

## string_xrefs

- `0x18000c662`: `Failed to open binding`

## pseudocode

```c
__int64 WinStationIsSessionPermitted()
{
  DWORD Pointer; // ebx
  CPublicBinding *v2; // rax
  CPublicBinding *v3; // rax
  void *v4; // rax
  CLIENT_CALL_RETURN v5; // rax
  unsigned __int16 v6[4]; // [rsp+28h] [rbp-20h] BYREF
  CPublicBinding *v7; // [rsp+30h] [rbp-18h]
  CLIENT_CALL_RETURN v8; // [rsp+50h] [rbp+8h] BYREF

  WaitForLsmStart();
  if ( GetSystemMetrics(4096) )
  {
    *(_QWORD *)v6 = 1;
    LODWORD(v8.Pointer) = 0;
    v2 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v2 )
      v3 = CPublicBinding::CPublicBinding(v2, 0, 0, (unsigned int *)&v8);
    else
      v3 = 0;
    v7 = v3;
    if ( v3 )
    {
      *(_DWORD *)&v6[2] = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
    if ( CSmartPublicBinding::operator void *(v6) )
    {
      v4 = CSmartPublicBinding::operator void *(v6);
      v8.Simple = 0;
      v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 0, 0, v4).Pointer;
      Pointer = (DWORD)v5.Pointer;
      v8.Pointer = v5.Pointer;
      if ( LODWORD(v5.Pointer) == 1722 )
        Pointer = 0;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding");
      Pointer = GetLastError();
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v6);
  }
  else
  {
    return 0;
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000c570  mov     [rsp+arg_8], rbx
0x18000c575  push    rdi
0x18000c576  sub     rsp, 40h
0x18000c57a  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18000c57f  mov     ecx, 1000h; nIndex
0x18000c584  call    cs:__imp_GetSystemMetrics
0x18000c58a  xor     edi, edi
0x18000c58c  test    eax, eax
0x18000c58e  jnz     short loc_18000C59F
0x18000c590  mov     ebx, edi
0x18000c592  mov     eax, ebx
0x18000c594  mov     rbx, [rsp+48h+arg_8]
0x18000c599  add     rsp, 40h
0x18000c59d  pop     rdi
0x18000c59e  retn
0x18000c59f  mov     qword ptr [rsp+48h+var_20], 1
0x18000c5a8  mov     dword ptr [rsp+48h+arg_0], edi
0x18000c5ac  mov     ebx, 1
0x18000c5b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c5b8  lea     ecx, [rbx+3Fh]; unsigned __int64
0x18000c5bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c5c0  test    rax, rax
0x18000c5c3  jz      loc_18000C67D
0x18000c5c9  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x18000c5ce  xor     r8d, r8d; int
0x18000c5d1  xor     edx, edx; unsigned __int16 *
0x18000c5d3  mov     rcx, rax; this
0x18000c5d6  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18000c5db  mov     [rsp+48h+var_18], rax
0x18000c5e0  test    rax, rax
0x18000c5e3  jz      loc_18000C685
0x18000c5e9  mov     dword ptr [rsp+48h+var_20+4], ebx
0x18000c5ed  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000c5f2  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000c5f7  test    rax, rax
0x18000c5fa  jz      short loc_18000C662
0x18000c5fc  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000c601  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000c606  mov     [rsp+48h+arg_0], rdi
0x18000c60b  mov     r9, rax
0x18000c60e  xor     r8d, r8d; pReturnValue
0x18000c611  xor     edx, edx; nProcNum
0x18000c613  lea     rcx, stru_180032170; pProxyInfo
0x18000c61a  call    cs:__imp_NdrClientCall3
0x18000c620  mov     rbx, rax
0x18000c623  mov     [rsp+48h+arg_0], rax
0x18000c628  mov     [rsp+48h+var_28], eax
0x18000c62c  jmp     short loc_18000C64A
0x18000c62e  mov     ebx, eax
0x18000c630  mov     [rsp+48h+var_28], eax
0x18000c634  mov     r8d, eax
0x18000c637  lea     rdx, aRpcissessionpe; "RpcIsSessionPermitted threw an exceptio"...
0x18000c63e  mov     ecx, 8; int
0x18000c643  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c648  xor     edi, edi
0x18000c64a  cmp     ebx, 6BAh
0x18000c650  cmovz   ebx, edi
0x18000c653  lea     rcx, [rsp+48h+var_20]; this
0x18000c658  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000c65d  jmp     loc_18000C592
0x18000c662  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000c669  mov     ecx, 8; int
0x18000c66e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c673  call    cs:__imp_GetLastError
0x18000c679  mov     ebx, eax
0x18000c67b  jmp     short loc_18000C653
0x18000c67d  mov     rax, rdi
0x18000c680  jmp     loc_18000C5DB
0x18000c685  mov     ecx, 0Eh; dwErrCode
0x18000c68a  call    cs:__imp_SetLastError
0x18000c690  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000c697  mov     ecx, 8; int
0x18000c69c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c6a1  jmp     loc_18000C5ED
0x180030560  push    rbp
0x180030562  sub     rsp, 20h
0x180030566  mov     rbp, rdx
0x180030569  mov     rcx, [rcx]
0x18003056c  mov     ecx, [rcx]; ExceptionCode
0x18003056e  call    cs:__imp_I_RpcExceptionFilter
0x180030574  nop
0x180030575  add     rsp, 20h
0x180030579  pop     rbp
0x18003057a  retn
```
