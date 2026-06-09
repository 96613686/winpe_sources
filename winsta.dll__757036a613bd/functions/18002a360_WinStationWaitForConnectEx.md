# _WinStationWaitForConnectEx

- ea: `0x18002a360`
- end: `0x18002a452`
- name: `_WinStationWaitForConnectEx`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000c6b0`
- `0x18002a360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a42f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a42f`
- `RPCRT4!NdrClientCall3` at `0x18002a3cb`
- `RPCRT4!NdrClientCall3` at `0x18002a3cb`

## string_xrefs

- `0x18002a392`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationWaitForConnectEx(__int64 a1)
{
  char v2; // di
  void *v3; // rax
  int Pointer; // ebx
  DWORD v5; // eax
  unsigned __int16 v7[12]; // [rsp+40h] [rbp-18h] BYREF

  WaitForLsmStart();
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 0);
  v2 = 0;
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    v3 = CSmartPublicBinding::operator void *(v7);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 2u, 0, v3, a1).Pointer;
    if ( Pointer >= 0 )
    {
      v2 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcConnectTerminal failed: 0x%x in %s", Pointer, "_WinStationWaitForConnectEx");
      v5 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v5);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v2;
}

```

## disassembly

```asm
0x18002a360  mov     [rsp+arg_8], rbx
0x18002a365  push    rdi
0x18002a366  sub     rsp, 50h
0x18002a36a  mov     rbx, rcx
0x18002a36d  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18002a372  xor     r8d, r8d; int
0x18002a375  xor     edx, edx; void *
0x18002a377  lea     rcx, [rsp+58h+var_18]; this
0x18002a37c  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002a381  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002a386  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a38b  xor     edi, edi
0x18002a38d  test    rax, rax
0x18002a390  jnz     short loc_18002A3A6
0x18002a392  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002a399  lea     ecx, [rdi+8]; int
0x18002a39c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a3a1  jmp     loc_18002A43A
0x18002a3a6  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002a3ab  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a3b0  mov     [rsp+58h+var_20], rdi
0x18002a3b5  mov     [rsp+58h+var_38], rbx
0x18002a3ba  mov     r9, rax
0x18002a3bd  xor     r8d, r8d; pReturnValue
0x18002a3c0  lea     edx, [r8+2]; nProcNum
0x18002a3c4  lea     rcx, stru_1800321A0; pProxyInfo
0x18002a3cb  call    cs:__imp_NdrClientCall3
0x18002a3d1  mov     rbx, rax
0x18002a3d4  mov     [rsp+58h+var_20], rax
0x18002a3d9  mov     [rsp+58h+var_28], eax
0x18002a3dd  jmp     short loc_18002A407
0x18002a3df  test    eax, eax
0x18002a3e1  jle     short loc_18002A3EB
0x18002a3e3  movzx   eax, ax
0x18002a3e6  or      eax, 80070000h
0x18002a3eb  mov     ebx, eax
0x18002a3ed  mov     [rsp+58h+var_28], eax
0x18002a3f1  mov     r8d, eax
0x18002a3f4  lea     rdx, aRpcconnectterm_0; "RpcConnectTerminal threw an exception: "...
0x18002a3fb  mov     ecx, 8; int
0x18002a400  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a405  xor     edi, edi
0x18002a407  test    ebx, ebx
0x18002a409  jns     short loc_18002A437
0x18002a40b  lea     r9, aWinstationwait_3; "_WinStationWaitForConnectEx"
0x18002a412  mov     r8d, ebx
0x18002a415  lea     rdx, aRpcconnectterm; "RpcConnectTerminal failed: 0x%x in %s"
0x18002a41c  mov     ecx, 8; int
0x18002a421  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a426  mov     ecx, ebx; int
0x18002a428  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002a42d  mov     ecx, eax; dwErrCode
0x18002a42f  call    cs:__imp_SetLastError
0x18002a435  jmp     short loc_18002A43A
0x18002a437  mov     dil, 1
0x18002a43a  lea     rcx, [rsp+58h+var_18]; this
0x18002a43f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002a444  mov     al, dil
0x18002a447  mov     rbx, [rsp+58h+arg_8]
0x18002a44c  add     rsp, 50h
0x18002a450  pop     rdi
0x18002a451  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
