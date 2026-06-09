# WinStationSystemShutdownStarted

- ea: `0x180014d40`
- end: `0x180014ead`
- name: `WinStationSystemShutdownStarted`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180014d40`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dd3`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800336ed`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800336ed`
- `RPCRT4!NdrClientCall3` at `0x180014e1f`
- `RPCRT4!NdrClientCall3` at `0x180014e1f`

## string_xrefs

- `0x180014dc4`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationSystemShutdownStarted(int a1)
{
  CPublicBinding *v2; // rax
  signed int LastError; // eax
  CLIENT_CALL_RETURN v4; // rbx
  void *v5; // rax
  unsigned int v6; // ebx
  unsigned __int16 v8[4]; // [rsp+38h] [rbp-20h] BYREF
  CPublicBinding *v9; // [rsp+40h] [rbp-18h]
  CLIENT_CALL_RETURN v10; // [rsp+68h] [rbp+10h] BYREF

  *(_QWORD *)v8 = 0;
  LODWORD(v10.Pointer) = 0;
  v2 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    v2 = CPublicBinding::CPublicBinding(v2, 0, 0, (unsigned int *)&v10);
  v9 = v2;
  if ( v2 )
  {
    *(_DWORD *)&v8[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v8) )
  {
    v5 = CSmartPublicBinding::operator void *(v8);
    v10.Simple = 0;
    v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 3u, 0, v5, a1).Pointer;
    v10.Pointer = v4.Pointer;
    if ( SLODWORD(v4.Simple) >= 0 )
      goto LABEL_13;
    _DbgPrintMessage(
      8,
      "RpcSystemShutdownStarted failed: 0x%x in %s",
      LODWORD(v4.Pointer),
      "WinStationSystemShutdownStarted");
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    LODWORD(v4.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v4.Pointer) = (unsigned __int16)LastError | 0x80070000;
  }
  if ( SLODWORD(v4.Simple) < 0 )
  {
    v6 = ConvertHRESULT2WIN32(v4.Simple);
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
    return v6;
  }
LABEL_13:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
  return 0;
}

```

## disassembly

```asm
0x180014d40  push    rbx
0x180014d42  sub     rsp, 50h
0x180014d46  mov     ebx, ecx
0x180014d48  mov     qword ptr [rsp+58h+var_20], 0
0x180014d51  mov     dword ptr [rsp+58h+arg_8], 0
0x180014d59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d60  mov     ecx, 40h ; '@'; unsigned __int64
0x180014d65  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014d6a  test    rax, rax
0x180014d6d  jz      short loc_180014D81
0x180014d6f  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x180014d74  xor     r8d, r8d; int
0x180014d77  xor     edx, edx; unsigned __int16 *
0x180014d79  mov     rcx, rax; this
0x180014d7c  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180014d81  mov     [rsp+58h+var_18], rax
0x180014d86  test    rax, rax
0x180014d89  jnz     short loc_180014DAD
0x180014d8b  lea     ecx, [rax+0Eh]; dwErrCode
0x180014d8e  call    cs:__imp_SetLastError
0x180014d95  nop     dword ptr [rax+rax+00h]
0x180014d9a  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180014da1  mov     ecx, 8; int
0x180014da6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014dab  jmp     short loc_180014DB5
0x180014dad  mov     dword ptr [rsp+58h+var_20+4], 1
0x180014db5  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180014dba  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180014dbf  test    rax, rax
0x180014dc2  jnz     short loc_180014DF7
0x180014dc4  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180014dcb  lea     ecx, [rax+8]; int
0x180014dce  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014dd3  call    cs:__imp_GetLastError
0x180014dda  nop     dword ptr [rax+rax+00h]
0x180014ddf  mov     ebx, eax
0x180014de1  test    eax, eax
0x180014de3  jle     loc_180014E7F
0x180014de9  movzx   ebx, ax
0x180014dec  or      ebx, 80070000h
0x180014df2  jmp     loc_180014E7F
0x180014df7  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180014dfc  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180014e01  mov     [rsp+58h+arg_8], 0
0x180014e0a  mov     [rsp+58h+var_38], ebx
0x180014e0e  mov     r9, rax
0x180014e11  xor     r8d, r8d; pReturnValue
0x180014e14  lea     edx, [r8+3]; nProcNum
0x180014e18  lea     rcx, stru_1800351D0; pProxyInfo
0x180014e1f  call    cs:__imp_NdrClientCall3
0x180014e26  nop     dword ptr [rax+rax+00h]
0x180014e2b  mov     rbx, rax
0x180014e2e  mov     [rsp+58h+arg_8], rax
0x180014e33  mov     [rsp+58h+var_28], eax
0x180014e37  jmp     short loc_180014E60
0x180014e39  mov     ebx, eax
0x180014e3b  mov     r8d, eax
0x180014e3e  lea     rdx, aRpcsystemshutd; "RpcSystemShutdownStarted threw an excep"...
0x180014e45  mov     ecx, 8; int
0x180014e4a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014e4f  test    ebx, ebx
0x180014e51  jle     short loc_180014E5C
0x180014e53  movzx   ebx, bx
0x180014e56  or      ebx, 80070000h
0x180014e5c  mov     [rsp+58h+var_28], ebx
0x180014e60  test    ebx, ebx
0x180014e62  jns     short loc_180014E9A
0x180014e64  lea     r9, aWinstationsyst_2; "WinStationSystemShutdownStarted"
0x180014e6b  mov     r8d, ebx
0x180014e6e  lea     rdx, aRpcsystemshutd_0; "RpcSystemShutdownStarted failed: 0x%x i"...
0x180014e75  mov     ecx, 8; int
0x180014e7a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014e7f  test    ebx, ebx
0x180014e81  jns     short loc_180014E9A
0x180014e83  mov     ecx, ebx; int
0x180014e85  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180014e8a  mov     ebx, eax
0x180014e8c  lea     rcx, [rsp+58h+var_20]; this
0x180014e91  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180014e96  mov     eax, ebx
0x180014e98  jmp     short loc_180014EA6
0x180014e9a  lea     rcx, [rsp+58h+var_20]; this
0x180014e9f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180014ea4  xor     eax, eax
0x180014ea6  add     rsp, 50h
0x180014eaa  pop     rbx
0x180014eab  retn
0x1800336df  push    rbp
0x1800336e1  sub     rsp, 30h
0x1800336e5  mov     rbp, rdx
0x1800336e8  mov     rcx, [rcx]
0x1800336eb  mov     ecx, [rcx]; ExceptionCode
0x1800336ed  call    cs:__imp_I_RpcExceptionFilter
0x1800336f4  nop     dword ptr [rax+rax+00h]
0x1800336f9  nop
0x1800336fa  add     rsp, 30h
0x1800336fe  pop     rbp
0x1800336ff  retn
```
