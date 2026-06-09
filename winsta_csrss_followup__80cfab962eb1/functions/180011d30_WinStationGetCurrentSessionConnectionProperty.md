# WinStationGetCurrentSessionConnectionProperty

- ea: `0x180011d30`
- end: `0x180011ebd`
- name: `WinStationGetCurrentSessionConnectionProperty`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a9e0`

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180011d30`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011eaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e3e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033535`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033535`
- `RPCRT4!NdrClientCall3` at `0x180011dde`
- `RPCRT4!NdrClientCall3` at `0x180011dde`

## string_xrefs

- `0x180011e59`: `Failed to open binding`

## pseudocode

```c
bool __fastcall WinStationGetCurrentSessionConnectionProperty(__int64 a1, _QWORD *a2)
{
  CPublicBinding *v4; // rax
  void *v5; // rax
  CLIENT_CALL_RETURN v6; // rax
  signed int Pointer; // ebx
  bool v8; // sf
  bool v9; // bl
  signed int LastError; // eax
  DWORD v12; // eax
  unsigned __int16 v13[4]; // [rsp+38h] [rbp-20h] BYREF
  CPublicBinding *v14; // [rsp+40h] [rbp-18h]
  CLIENT_CALL_RETURN v15; // [rsp+70h] [rbp+18h] BYREF

  *(_QWORD *)v13 = 1;
  LODWORD(v15.Pointer) = 0;
  v4 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v4 = CPublicBinding::CPublicBinding(v4, 0, 0, (unsigned int *)&v15);
  v14 = v4;
  if ( v4 )
  {
    *(_DWORD *)&v13[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v13) )
  {
    if ( a2 )
    {
      *a2 = 0;
      v5 = CSmartPublicBinding::operator void *(v13);
      v15.Simple = 0;
      v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035018, 0, 0, v5, a1, a2).Pointer;
      Pointer = (signed int)v6.Pointer;
      v15.Pointer = v6.Pointer;
    }
    else
    {
      Pointer = -2147024809;
      _DbgPrintMessage(8, "ppProperyValue is NULL");
    }
  }
  else
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  v8 = Pointer < 0;
  if ( Pointer < 0 )
  {
    v12 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v12);
    v8 = Pointer < 0;
  }
  v9 = !v8;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v13);
  return v9;
}

```

## disassembly

```asm
0x180011d30  mov     [rsp+arg_0], rbx
0x180011d35  push    rdi
0x180011d36  sub     rsp, 50h
0x180011d3a  mov     rbx, rdx
0x180011d3d  mov     rdi, rcx
0x180011d40  mov     qword ptr [rsp+58h+var_20], 1
0x180011d49  mov     dword ptr [rsp+58h+arg_10], 0
0x180011d51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d58  mov     ecx, 40h ; '@'; unsigned __int64
0x180011d5d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011d62  test    rax, rax
0x180011d65  jz      short loc_180011D79
0x180011d67  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x180011d6c  xor     r8d, r8d; int
0x180011d6f  xor     edx, edx; unsigned __int16 *
0x180011d71  mov     rcx, rax; this
0x180011d74  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180011d79  mov     [rsp+58h+var_18], rax
0x180011d7e  test    rax, rax
0x180011d81  jz      loc_180011E6C
0x180011d87  mov     dword ptr [rsp+58h+var_20+4], 1
0x180011d8f  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180011d94  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011d99  test    rax, rax
0x180011d9c  jz      loc_180011E3E
0x180011da2  test    rbx, rbx
0x180011da5  jz      loc_180011E93
0x180011dab  mov     qword ptr [rbx], 0
0x180011db2  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180011db7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011dbc  mov     [rsp+58h+arg_10], 0
0x180011dc5  mov     [rsp+58h+var_30], rbx
0x180011dca  mov     [rsp+58h+var_38], rdi
0x180011dcf  mov     r9, rax
0x180011dd2  xor     r8d, r8d; pReturnValue
0x180011dd5  xor     edx, edx; nProcNum
0x180011dd7  lea     rcx, stru_180035018; pProxyInfo
0x180011dde  call    cs:__imp_NdrClientCall3
0x180011de5  nop     dword ptr [rax+rax+00h]
0x180011dea  mov     rbx, rax
0x180011ded  mov     [rsp+58h+arg_10], rax
0x180011df2  mov     [rsp+58h+var_28], eax
0x180011df6  jmp     short loc_180011E1F
0x180011df8  test    eax, eax
0x180011dfa  jle     short loc_180011E04
0x180011dfc  movzx   eax, ax
0x180011dff  or      eax, 80070000h
0x180011e04  mov     ebx, eax
0x180011e06  mov     [rsp+58h+var_28], eax
0x180011e0a  mov     r8d, eax
0x180011e0d  lea     rdx, aRpcgetcurrents_1; "RpcGetCurrentSessionConnectionProperty "...
0x180011e14  mov     ecx, 8; int
0x180011e19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011e1e  nop
0x180011e1f  test    ebx, ebx
0x180011e21  js      short loc_180011EA1
0x180011e23  setns   bl
0x180011e26  lea     rcx, [rsp+58h+var_20]; this
0x180011e2b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180011e30  mov     al, bl
0x180011e32  mov     rbx, [rsp+58h+arg_0]
0x180011e37  add     rsp, 50h
0x180011e3b  pop     rdi
0x180011e3c  retn
0x180011e3e  call    cs:__imp_GetLastError
0x180011e45  nop     dword ptr [rax+rax+00h]
0x180011e4a  mov     ebx, eax
0x180011e4c  test    eax, eax
0x180011e4e  jle     short loc_180011E59
0x180011e50  movzx   ebx, ax
0x180011e53  or      ebx, 80070000h
0x180011e59  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180011e60  mov     ecx, 8; int
0x180011e65  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011e6a  jmp     short loc_180011E1F
0x180011e6c  mov     ecx, 0Eh; dwErrCode
0x180011e71  call    cs:__imp_SetLastError
0x180011e78  nop     dword ptr [rax+rax+00h]
0x180011e7d  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180011e84  mov     ecx, 8; int
0x180011e89  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011e8e  jmp     loc_180011D8F
0x180011e93  mov     ebx, 80070057h
0x180011e98  lea     rdx, aPpproperyvalue; "ppProperyValue is NULL"
0x180011e9f  jmp     short loc_180011E60
0x180011ea1  mov     ecx, ebx; int
0x180011ea3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180011ea8  mov     ecx, eax; dwErrCode
0x180011eaa  call    cs:__imp_SetLastError
0x180011eb1  nop     dword ptr [rax+rax+00h]
0x180011eb6  test    ebx, ebx
0x180011eb8  jmp     loc_180011E23
0x180033527  push    rbp
0x180033529  sub     rsp, 30h
0x18003352d  mov     rbp, rdx
0x180033530  mov     rcx, [rcx]
0x180033533  mov     ecx, [rcx]; ExceptionCode
0x180033535  call    cs:__imp_I_RpcExceptionFilter
0x18003353c  nop     dword ptr [rax+rax+00h]
0x180033541  nop
0x180033542  add     rsp, 30h
0x180033546  pop     rbp
0x180033547  retn
```
