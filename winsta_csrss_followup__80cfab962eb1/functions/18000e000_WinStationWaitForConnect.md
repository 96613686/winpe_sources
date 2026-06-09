# _WinStationWaitForConnect

- ea: `0x18000e000`
- end: `0x18000e150`
- name: `_WinStationWaitForConnect`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000e000`
- `0x18000e2c0`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e052`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e126`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e052`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e126`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800333f6`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800333f6`
- `RPCRT4!NdrClientCall3` at `0x18000e0bc`
- `RPCRT4!NdrClientCall3` at `0x18000e0bc`

## string_xrefs

- `0x18000e088`: `Failed to open binding`

## pseudocode

```c
char WinStationWaitForConnect()
{
  char v0; // di
  CPublicBinding *v1; // rax
  CPublicBinding *v2; // rax
  void *v3; // rax
  CLIENT_CALL_RETURN v4; // rbx
  DWORD v5; // eax
  unsigned __int16 v7[4]; // [rsp+28h] [rbp-20h] BYREF
  CPublicBinding *v8; // [rsp+30h] [rbp-18h]
  CLIENT_CALL_RETURN v9; // [rsp+50h] [rbp+8h] BYREF

  WaitForLsmStart();
  v0 = 0;
  *(_QWORD *)v7 = 0;
  LODWORD(v9.Pointer) = 0;
  v1 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v1 )
    v2 = CPublicBinding::CPublicBinding(v1, 0, 0, (unsigned int *)&v9);
  else
    v2 = 0;
  v8 = v2;
  if ( v2 )
  {
    *(_DWORD *)&v7[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    v3 = CSmartPublicBinding::operator void *(v7);
    v9.Simple = 0;
    v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 1u, 0, v3).Pointer;
    v9.Pointer = v4.Pointer;
    if ( SLODWORD(v4.Simple) >= 0 )
    {
      v0 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcConnectTerminal failed: 0x%x in %s", LODWORD(v4.Pointer), "_WinStationWaitForConnect");
      v5 = ConvertHRESULT2WIN32(v4.Simple);
      SetLastError(v5);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v0;
}

```

## disassembly

```asm
0x18000e000  mov     [rsp+arg_8], rbx
0x18000e005  push    rdi
0x18000e006  sub     rsp, 40h
0x18000e00a  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18000e00f  xor     edi, edi
0x18000e011  mov     qword ptr [rsp+48h+var_20], rdi
0x18000e016  mov     dword ptr [rsp+48h+arg_0], edi
0x18000e01a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e021  lea     ecx, [rdi+40h]; unsigned __int64
0x18000e024  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e029  test    rax, rax
0x18000e02c  jz      short loc_18000E042
0x18000e02e  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x18000e033  xor     r8d, r8d; int
0x18000e036  xor     edx, edx; unsigned __int16 *
0x18000e038  mov     rcx, rax; this
0x18000e03b  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18000e040  jmp     short loc_18000E045
0x18000e042  mov     rax, rdi
0x18000e045  mov     [rsp+48h+var_18], rax
0x18000e04a  test    rax, rax
0x18000e04d  jnz     short loc_18000E071
0x18000e04f  lea     ecx, [rax+0Eh]; dwErrCode
0x18000e052  call    cs:__imp_SetLastError
0x18000e059  nop     dword ptr [rax+rax+00h]
0x18000e05e  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000e065  mov     ecx, 8; int
0x18000e06a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e06f  jmp     short loc_18000E079
0x18000e071  mov     dword ptr [rsp+48h+var_20+4], 1
0x18000e079  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000e07e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000e083  test    rax, rax
0x18000e086  jnz     short loc_18000E09C
0x18000e088  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000e08f  lea     ecx, [rax+8]; int
0x18000e092  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e097  jmp     loc_18000E137
0x18000e09c  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000e0a1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000e0a6  mov     [rsp+48h+arg_0], rdi
0x18000e0ab  mov     r9, rax
0x18000e0ae  xor     r8d, r8d; pReturnValue
0x18000e0b1  lea     edx, [r8+1]; nProcNum
0x18000e0b5  lea     rcx, stru_1800351D0; pProxyInfo
0x18000e0bc  call    cs:__imp_NdrClientCall3
0x18000e0c3  nop     dword ptr [rax+rax+00h]
0x18000e0c8  mov     rbx, rax
0x18000e0cb  mov     [rsp+48h+arg_0], rax
0x18000e0d0  mov     [rsp+48h+var_28], eax
0x18000e0d4  jmp     short loc_18000E0FE
0x18000e0d6  test    eax, eax
0x18000e0d8  jle     short loc_18000E0E2
0x18000e0da  movzx   eax, ax
0x18000e0dd  or      eax, 80070000h
0x18000e0e2  mov     ebx, eax
0x18000e0e4  mov     [rsp+48h+var_28], eax
0x18000e0e8  mov     r8d, eax
0x18000e0eb  lea     rdx, aRpcconnectterm_0; "RpcConnectTerminal threw an exception: "...
0x18000e0f2  mov     ecx, 8; int
0x18000e0f7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e0fc  xor     edi, edi
0x18000e0fe  test    ebx, ebx
0x18000e100  jns     short loc_18000E134
0x18000e102  lea     r9, aWinstationwait_2; "_WinStationWaitForConnect"
0x18000e109  mov     r8d, ebx
0x18000e10c  lea     rdx, aRpcconnectterm; "RpcConnectTerminal failed: 0x%x in %s"
0x18000e113  mov     ecx, 8; int
0x18000e118  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e11d  mov     ecx, ebx; int
0x18000e11f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000e124  mov     ecx, eax; dwErrCode
0x18000e126  call    cs:__imp_SetLastError
0x18000e12d  nop     dword ptr [rax+rax+00h]
0x18000e132  jmp     short loc_18000E137
0x18000e134  mov     dil, 1
0x18000e137  lea     rcx, [rsp+48h+var_20]; this
0x18000e13c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000e141  mov     al, dil
0x18000e144  mov     rbx, [rsp+48h+arg_8]
0x18000e149  add     rsp, 40h
0x18000e14d  pop     rdi
0x18000e14e  retn
0x1800333e8  push    rbp
0x1800333ea  sub     rsp, 20h
0x1800333ee  mov     rbp, rdx
0x1800333f1  mov     rcx, [rcx]
0x1800333f4  mov     ecx, [rcx]; ExceptionCode
0x1800333f6  call    cs:__imp_I_RpcExceptionFilter
0x1800333fd  nop     dword ptr [rax+rax+00h]
0x180033402  nop
0x180033403  add     rsp, 20h
0x180033407  pop     rbp
0x180033408  retn
```
