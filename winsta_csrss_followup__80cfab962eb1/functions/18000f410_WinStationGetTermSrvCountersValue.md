# WinStationGetTermSrvCountersValue

- ea: `0x18000f410`
- end: `0x18000f571`
- name: `WinStationGetTermSrvCountersValue`
- size: `353`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000eda4`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000f410`
- `0x18002ede0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f55e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f52c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033446`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033446`
- `RPCRT4!NdrClientCall3` at `0x18000f483`
- `RPCRT4!NdrClientCall3` at `0x18000f483`

## string_xrefs

- `0x18000f505`: `Failed to open binding`

## pseudocode

```c
unsigned __int8 __fastcall WinStationGetTermSrvCountersValue(CPublicBinding *this, unsigned int a2, void *a3)
{
  void *v6; // rax
  int Pointer; // ebx
  unsigned __int8 TermSrvCountersValue; // bl
  DWORD v10; // eax
  unsigned __int16 v11[32]; // [rsp+38h] [rbp-40h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v11, this, 0);
  if ( CSmartPublicBinding::operator void *(v11) )
  {
    v6 = CSmartPublicBinding::operator void *(v11);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0, v6, a3, a2).Pointer;
    if ( Pointer == -2147023174 )
    {
      TermSrvCountersValue = Legacy_WinStationGetTermSrvCountersValue(this, a2, a3);
      if ( !TermSrvCountersValue )
        GetLastError();
    }
    else if ( Pointer < 0 )
    {
      _DbgPrintMessage(8, "RpcGetSessionCounters failed: 0x%x in %s", Pointer, "WinStationGetTermSrvCountersValue");
      v10 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v10);
      TermSrvCountersValue = 0;
    }
    else
    {
      TermSrvCountersValue = 1;
    }
  }
  else
  {
    TermSrvCountersValue = 0;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v11);
  return TermSrvCountersValue;
}

```

## disassembly

```asm
0x18000f410  mov     rax, rsp
0x18000f413  mov     [rax+18h], r8
0x18000f417  mov     [rax+10h], edx
0x18000f41a  mov     [rax+8], rcx
0x18000f41e  push    rbx
0x18000f41f  push    rsi
0x18000f420  push    rdi
0x18000f421  push    r14
0x18000f423  sub     rsp, 58h
0x18000f427  mov     rsi, r8
0x18000f42a  mov     r14d, edx
0x18000f42d  mov     rdi, rcx
0x18000f430  xor     r8d, r8d; int
0x18000f433  mov     rdx, rcx; void *
0x18000f436  lea     rcx, [rax-40h]; this
0x18000f43a  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000f43f  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000f444  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000f449  test    rax, rax
0x18000f44c  jz      loc_18000F503
0x18000f452  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000f457  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000f45c  mov     [rsp+78h+arg_18], 0
0x18000f468  mov     [rsp+78h+var_50], r14d
0x18000f46d  mov     [rsp+78h+var_58], rsi
0x18000f472  mov     r9, rax
0x18000f475  xor     r8d, r8d; pReturnValue
0x18000f478  lea     edx, [r8+0Bh]; nProcNum
0x18000f47c  lea     rcx, pProxyInfo; pProxyInfo
0x18000f483  call    cs:__imp_NdrClientCall3
0x18000f48a  nop     dword ptr [rax+rax+00h]
0x18000f48f  mov     rbx, rax
0x18000f492  mov     [rsp+78h+arg_18], rax
0x18000f49a  mov     [rsp+78h+var_48], eax
0x18000f49e  jmp     short loc_18000F4DE
0x18000f4a0  test    eax, eax
0x18000f4a2  jle     short loc_18000F4AC
0x18000f4a4  movzx   eax, ax
0x18000f4a7  or      eax, 80070000h
0x18000f4ac  mov     ebx, eax
0x18000f4ae  mov     [rsp+78h+var_48], eax
0x18000f4b2  mov     r8d, eax
0x18000f4b5  lea     rdx, aRpcgetsessionc_0; "RpcGetSessionCounters threw an exceptio"...
0x18000f4bc  mov     ecx, 8; int
0x18000f4c1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f4c6  mov     rsi, [rsp+78h+arg_10]
0x18000f4ce  mov     r14d, [rsp+78h+arg_8]
0x18000f4d6  mov     rdi, [rsp+78h+arg_0]
0x18000f4de  cmp     ebx, 800706BAh
0x18000f4e4  jz      short loc_18000F518
0x18000f4e6  test    ebx, ebx
0x18000f4e8  js      short loc_18000F53A
0x18000f4ea  mov     bl, 1
0x18000f4ec  lea     rcx, [rsp+78h+var_40]; this
0x18000f4f1  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000f4f6  mov     al, bl
0x18000f4f8  add     rsp, 58h
0x18000f4fc  pop     r14
0x18000f4fe  pop     rdi
0x18000f4ff  pop     rsi
0x18000f500  pop     rbx
0x18000f501  retn
0x18000f503  xor     bl, bl
0x18000f505  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000f50c  mov     ecx, 8; int
0x18000f511  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f516  jmp     short loc_18000F4EC
0x18000f518  mov     r8, rsi; void *
0x18000f51b  mov     edx, r14d; unsigned int
0x18000f51e  mov     rcx, rdi; this
0x18000f521  call    ?Legacy_WinStationGetTermSrvCountersValue@@YAEPEAXK0@Z; Legacy_WinStationGetTermSrvCountersValue(void *,ulong,void *)
0x18000f526  mov     bl, al
0x18000f528  test    al, al
0x18000f52a  jnz     short loc_18000F4EC
0x18000f52c  call    cs:__imp_GetLastError
0x18000f533  nop     dword ptr [rax+rax+00h]
0x18000f538  jmp     short loc_18000F4EC
0x18000f53a  lea     r9, aWinstationgett_0; "WinStationGetTermSrvCountersValue"
0x18000f541  mov     r8d, ebx
0x18000f544  lea     rdx, aRpcgetsessionc; "RpcGetSessionCounters failed: 0x%x in %"...
0x18000f54b  mov     ecx, 8; int
0x18000f550  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f555  mov     ecx, ebx; int
0x18000f557  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000f55c  mov     ecx, eax; dwErrCode
0x18000f55e  call    cs:__imp_SetLastError
0x18000f565  nop     dword ptr [rax+rax+00h]
0x18000f56a  xor     bl, bl
0x18000f56c  jmp     loc_18000F4EC
0x180033438  push    rbp
0x18003343a  sub     rsp, 30h
0x18003343e  mov     rbp, rdx
0x180033441  mov     rcx, [rcx]
0x180033444  mov     ecx, [rcx]; ExceptionCode
0x180033446  call    cs:__imp_I_RpcExceptionFilter
0x18003344d  nop     dword ptr [rax+rax+00h]
0x180033452  nop
0x180033453  add     rsp, 30h
0x180033457  pop     rbp
0x180033458  retn
```
