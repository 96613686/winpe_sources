# _WinStationWaitForConnect

- ea: `0x18000c420`
- end: `0x18000c55d`
- name: `_WinStationWaitForConnect`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000c420`
- `0x18000c6b0`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c53a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c53a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003054c`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003054c`
- `RPCRT4!NdrClientCall3` at `0x18000c4d6`
- `RPCRT4!NdrClientCall3` at `0x18000c4d6`

## string_xrefs

- `0x18000c4a2`: `Failed to open binding`

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
    v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 1u, 0, v3).Pointer;
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
0x18000c420  mov     [rsp+arg_8], rbx
0x18000c425  push    rdi
0x18000c426  sub     rsp, 40h
0x18000c42a  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18000c42f  xor     edi, edi
0x18000c431  mov     qword ptr [rsp+48h+var_20], rdi
0x18000c436  mov     dword ptr [rsp+48h+arg_0], edi
0x18000c43a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c441  lea     ecx, [rdi+40h]; unsigned __int64
0x18000c444  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c449  test    rax, rax
0x18000c44c  jz      short loc_18000C462
0x18000c44e  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x18000c453  xor     r8d, r8d; int
0x18000c456  xor     edx, edx; unsigned __int16 *
0x18000c458  mov     rcx, rax; this
0x18000c45b  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18000c460  jmp     short loc_18000C465
0x18000c462  mov     rax, rdi
0x18000c465  mov     [rsp+48h+var_18], rax
0x18000c46a  test    rax, rax
0x18000c46d  jnz     short loc_18000C48B
0x18000c46f  lea     ecx, [rax+0Eh]; dwErrCode
0x18000c472  call    cs:__imp_SetLastError
0x18000c478  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000c47f  mov     ecx, 8; int
0x18000c484  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c489  jmp     short loc_18000C493
0x18000c48b  mov     dword ptr [rsp+48h+var_20+4], 1
0x18000c493  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000c498  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000c49d  test    rax, rax
0x18000c4a0  jnz     short loc_18000C4B6
0x18000c4a2  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000c4a9  lea     ecx, [rax+8]; int
0x18000c4ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c4b1  jmp     loc_18000C545
0x18000c4b6  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000c4bb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000c4c0  mov     [rsp+48h+arg_0], rdi
0x18000c4c5  mov     r9, rax
0x18000c4c8  xor     r8d, r8d; pReturnValue
0x18000c4cb  lea     edx, [r8+1]; nProcNum
0x18000c4cf  lea     rcx, stru_1800321A0; pProxyInfo
0x18000c4d6  call    cs:__imp_NdrClientCall3
0x18000c4dc  mov     rbx, rax
0x18000c4df  mov     [rsp+48h+arg_0], rax
0x18000c4e4  mov     [rsp+48h+var_28], eax
0x18000c4e8  jmp     short loc_18000C512
0x18000c4ea  test    eax, eax
0x18000c4ec  jle     short loc_18000C4F6
0x18000c4ee  movzx   eax, ax
0x18000c4f1  or      eax, 80070000h
0x18000c4f6  mov     ebx, eax
0x18000c4f8  mov     [rsp+48h+var_28], eax
0x18000c4fc  mov     r8d, eax
0x18000c4ff  lea     rdx, aRpcconnectterm_0; "RpcConnectTerminal threw an exception: "...
0x18000c506  mov     ecx, 8; int
0x18000c50b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c510  xor     edi, edi
0x18000c512  test    ebx, ebx
0x18000c514  jns     short loc_18000C542
0x18000c516  lea     r9, aWinstationwait_2; "_WinStationWaitForConnect"
0x18000c51d  mov     r8d, ebx
0x18000c520  lea     rdx, aRpcconnectterm; "RpcConnectTerminal failed: 0x%x in %s"
0x18000c527  mov     ecx, 8; int
0x18000c52c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c531  mov     ecx, ebx; int
0x18000c533  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000c538  mov     ecx, eax; dwErrCode
0x18000c53a  call    cs:__imp_SetLastError
0x18000c540  jmp     short loc_18000C545
0x18000c542  mov     dil, 1
0x18000c545  lea     rcx, [rsp+48h+var_20]; this
0x18000c54a  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000c54f  mov     al, dil
0x18000c552  mov     rbx, [rsp+48h+arg_8]
0x18000c557  add     rsp, 40h
0x18000c55b  pop     rdi
0x18000c55c  retn
0x18003053e  push    rbp
0x180030540  sub     rsp, 20h
0x180030544  mov     rbp, rdx
0x180030547  mov     rcx, [rcx]
0x18003054a  mov     ecx, [rcx]; ExceptionCode
0x18003054c  call    cs:__imp_I_RpcExceptionFilter
0x180030552  nop
0x180030553  add     rsp, 20h
0x180030557  pop     rbp
0x180030558  retn
```
