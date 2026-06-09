# WinStationIsBoundToCacheTerminal

- ea: `0x18002b8c0`
- end: `0x18002b9d1`
- name: `WinStationIsBoundToCacheTerminal`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002b8c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b8f6`
- `RPCRT4!NdrClientCall3` at `0x18002b943`
- `RPCRT4!NdrClientCall3` at `0x18002b943`

## string_xrefs

- `0x18002b8e7`: `Failed to open binding`
- `0x18002b962`: `RpcIsBoundToCacheTerminal threw an exception: 0x%x`
- `0x18002b988`: `WinStationIsBoundToCacheTerminal`
- `0x18002b992`: `WinStationIsBoundToCacheTerminal failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall WinStationIsBoundToCacheTerminal(__int64 a1)
{
  signed int LastError; // eax
  signed int Pointer; // ebx
  __int64 v4; // rax
  unsigned int v5; // ebx
  unsigned __int16 v7[16]; // [rsp+38h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 0);
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    v4 = CSmartPublicBinding::operator void *(v7);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x13u, 0, v4, a1).Pointer;
    if ( Pointer >= 0 )
      goto LABEL_8;
    _DbgPrintMessage(
      8,
      "WinStationIsBoundToCacheTerminal failed: 0x%x in %s",
      Pointer,
      "WinStationIsBoundToCacheTerminal");
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Pointer < 0 )
  {
    v5 = ConvertHRESULT2WIN32(Pointer);
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
    return v5;
  }
LABEL_8:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return 0;
}

```

## disassembly

```asm
0x18002b8c0  push    rbx
0x18002b8c2  sub     rsp, 50h
0x18002b8c6  mov     rbx, rcx
0x18002b8c9  xor     r8d, r8d; int
0x18002b8cc  xor     edx, edx; void *
0x18002b8ce  lea     rcx, [rsp+58h+var_20]; this
0x18002b8d3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002b8d8  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002b8dd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b8e2  test    rax, rax
0x18002b8e5  jnz     short loc_18002B91A
0x18002b8e7  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002b8ee  lea     ecx, [rax+8]; int
0x18002b8f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b8f6  call    cs:__imp_GetLastError
0x18002b8fd  nop     dword ptr [rax+rax+00h]
0x18002b902  mov     ebx, eax
0x18002b904  test    eax, eax
0x18002b906  jle     loc_18002B9A3
0x18002b90c  movzx   ebx, ax
0x18002b90f  or      ebx, 80070000h
0x18002b915  jmp     loc_18002B9A3
0x18002b91a  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002b91f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b924  mov     [rsp+58h+arg_8], 0
0x18002b92d  mov     [rsp+58h+var_38], rbx
0x18002b932  mov     r9, rax
0x18002b935  xor     r8d, r8d; pReturnValue
0x18002b938  lea     edx, [r8+13h]; nProcNum
0x18002b93c  lea     rcx, pProxyInfo; pProxyInfo
0x18002b943  call    cs:__imp_NdrClientCall3
0x18002b94a  nop     dword ptr [rax+rax+00h]
0x18002b94f  mov     rbx, rax
0x18002b952  mov     [rsp+58h+arg_8], rax
0x18002b957  mov     [rsp+58h+var_28], eax
0x18002b95b  jmp     short loc_18002B984
0x18002b95d  mov     ebx, eax
0x18002b95f  mov     r8d, eax
0x18002b962  lea     rdx, aRpcisboundtoca; "RpcIsBoundToCacheTerminal threw an exce"...
0x18002b969  mov     ecx, 8; int
0x18002b96e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b973  test    ebx, ebx
0x18002b975  jle     short loc_18002B980
0x18002b977  movzx   ebx, bx
0x18002b97a  or      ebx, 80070000h
0x18002b980  mov     [rsp+58h+var_28], ebx
0x18002b984  test    ebx, ebx
0x18002b986  jns     short loc_18002B9BE
0x18002b988  lea     r9, aWinstationisbo_1; "WinStationIsBoundToCacheTerminal"
0x18002b98f  mov     r8d, ebx
0x18002b992  lea     rdx, aWinstationisbo_0; "WinStationIsBoundToCacheTerminal failed"...
0x18002b999  mov     ecx, 8; int
0x18002b99e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b9a3  test    ebx, ebx
0x18002b9a5  jns     short loc_18002B9BE
0x18002b9a7  mov     ecx, ebx; int
0x18002b9a9  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002b9ae  mov     ebx, eax
0x18002b9b0  lea     rcx, [rsp+58h+var_20]; this
0x18002b9b5  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b9ba  mov     eax, ebx
0x18002b9bc  jmp     short loc_18002B9CA
0x18002b9be  lea     rcx, [rsp+58h+var_20]; this
0x18002b9c3  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b9c8  xor     eax, eax
0x18002b9ca  add     rsp, 50h
0x18002b9ce  pop     rbx
0x18002b9cf  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```
