# WinStationIsBoundToCacheTerminal

- ea: `0x180029c50`
- end: `0x180029d54`
- name: `WinStationIsBoundToCacheTerminal`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180029c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c86`
- `RPCRT4!NdrClientCall3` at `0x180029ccd`
- `RPCRT4!NdrClientCall3` at `0x180029ccd`

## string_xrefs

- `0x180029c77`: `Failed to open binding`
- `0x180029ce6`: `RpcIsBoundToCacheTerminal threw an exception: 0x%x`
- `0x180029d0c`: `WinStationIsBoundToCacheTerminal`
- `0x180029d16`: `WinStationIsBoundToCacheTerminal failed: 0x%x in %s`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032200, 0x13u, 0, v4, a1).Pointer;
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
0x180029c50  push    rbx
0x180029c52  sub     rsp, 50h
0x180029c56  mov     rbx, rcx
0x180029c59  xor     r8d, r8d; int
0x180029c5c  xor     edx, edx; void *
0x180029c5e  lea     rcx, [rsp+58h+var_20]; this
0x180029c63  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029c68  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029c6d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029c72  test    rax, rax
0x180029c75  jnz     short loc_180029CA4
0x180029c77  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180029c7e  lea     ecx, [rax+8]; int
0x180029c81  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029c86  call    cs:__imp_GetLastError
0x180029c8c  mov     ebx, eax
0x180029c8e  test    eax, eax
0x180029c90  jle     loc_180029D27
0x180029c96  movzx   ebx, ax
0x180029c99  or      ebx, 80070000h
0x180029c9f  jmp     loc_180029D27
0x180029ca4  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029ca9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029cae  mov     [rsp+58h+arg_8], 0
0x180029cb7  mov     [rsp+58h+var_38], rbx
0x180029cbc  mov     r9, rax
0x180029cbf  xor     r8d, r8d; pReturnValue
0x180029cc2  lea     edx, [r8+13h]; nProcNum
0x180029cc6  lea     rcx, stru_180032200; pProxyInfo
0x180029ccd  call    cs:__imp_NdrClientCall3
0x180029cd3  mov     rbx, rax
0x180029cd6  mov     [rsp+58h+arg_8], rax
0x180029cdb  mov     [rsp+58h+var_28], eax
0x180029cdf  jmp     short loc_180029D08
0x180029ce1  mov     ebx, eax
0x180029ce3  mov     r8d, eax
0x180029ce6  lea     rdx, aRpcisboundtoca; "RpcIsBoundToCacheTerminal threw an exce"...
0x180029ced  mov     ecx, 8; int
0x180029cf2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029cf7  test    ebx, ebx
0x180029cf9  jle     short loc_180029D04
0x180029cfb  movzx   ebx, bx
0x180029cfe  or      ebx, 80070000h
0x180029d04  mov     [rsp+58h+var_28], ebx
0x180029d08  test    ebx, ebx
0x180029d0a  jns     short loc_180029D42
0x180029d0c  lea     r9, aWinstationisbo_1; "WinStationIsBoundToCacheTerminal"
0x180029d13  mov     r8d, ebx
0x180029d16  lea     rdx, aWinstationisbo_0; "WinStationIsBoundToCacheTerminal failed"...
0x180029d1d  mov     ecx, 8; int
0x180029d22  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029d27  test    ebx, ebx
0x180029d29  jns     short loc_180029D42
0x180029d2b  mov     ecx, ebx; int
0x180029d2d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180029d32  mov     ebx, eax
0x180029d34  lea     rcx, [rsp+58h+var_20]; this
0x180029d39  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029d3e  mov     eax, ebx
0x180029d40  jmp     short loc_180029D4E
0x180029d42  lea     rcx, [rsp+58h+var_20]; this
0x180029d47  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029d4c  xor     eax, eax
0x180029d4e  add     rsp, 50h
0x180029d52  pop     rbx
0x180029d53  retn
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
