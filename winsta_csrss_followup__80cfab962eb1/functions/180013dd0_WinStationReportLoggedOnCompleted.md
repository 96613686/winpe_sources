# WinStationReportLoggedOnCompleted

- ea: `0x180013dd0`
- end: `0x180013f4f`
- name: `WinStationReportLoggedOnCompleted`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180013dd0`
- `0x1800249e8`
- `0x180032a14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e52`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003364d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003364d`
- `RPCRT4!NdrClientCall3` at `0x180013eb5`
- `RPCRT4!NdrClientCall3` at `0x180013eb5`

## string_xrefs

- `0x180013f05`: `WinStationReportLoggedOnCompleted threw an exception: 0x%x`
- `0x180013e71`: `WinStationReportLoggedOnCompleted`
- `0x180013ed1`: `WinStationReportLoggedOnCompleted`
- `0x180013edb`: `WinStationReportLoggedOnCompleted failed: 0x%x in %s`

## pseudocode

```c
bool WinStationReportLoggedOnCompleted()
{
  CPublicBinding *v0; // rax
  signed int LastError; // eax
  signed int Pointer; // ebx
  __int64 v3; // rcx
  __int64 v4; // rax
  CLIENT_CALL_RETURN v5; // rax
  DWORD v6; // eax
  unsigned __int16 v8[4]; // [rsp+28h] [rbp-20h] BYREF
  CPublicBinding *v9; // [rsp+30h] [rbp-18h]
  CLIENT_CALL_RETURN v10; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)v8 = 0;
  LODWORD(v10.Pointer) = 0;
  v0 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v0 )
    v0 = CPublicBinding::CPublicBinding(v0, 0, 0, (unsigned int *)&v10);
  v9 = v0;
  if ( v0 )
  {
    *(_DWORD *)&v8[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v8) )
    goto LABEL_11;
  LastError = GetLastError();
  Pointer = LastError;
  if ( LastError > 0 )
    Pointer = (unsigned __int16)LastError | 0x80070000;
  if ( Pointer >= 0 )
  {
LABEL_11:
    v4 = CSmartPublicBinding::operator void *(v8);
    v10.Simple = 0;
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 0xBu, 0, v4).Pointer;
    Pointer = (signed int)v5.Pointer;
    v10.Pointer = v5.Pointer;
    if ( SLODWORD(v5.Simple) < 0 )
      _DbgPrintMessage(
        8,
        "WinStationReportLoggedOnCompleted failed: 0x%x in %s",
        LODWORD(v5.Pointer),
        "WinStationReportLoggedOnCompleted");
  }
  else
  {
    _DbgPrintMessage(8, "Bind( NULL ) failed: 0x%x in %s", Pointer, "WinStationReportLoggedOnCompleted");
  }
  if ( Pointer < 0 )
    MicrosoftTelemetryAssertTriggeredArgs(v3, (unsigned int)Pointer);
  v6 = ConvertHRESULT2WIN32(Pointer);
  SetLastError(v6);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
  return Pointer >= 0;
}

```

## disassembly

```asm
0x180013dd0  push    rbx
0x180013dd2  sub     rsp, 40h
0x180013dd6  mov     qword ptr [rsp+48h+var_20], 0
0x180013ddf  mov     dword ptr [rsp+48h+arg_0], 0
0x180013de7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013dee  mov     ecx, 40h ; '@'; unsigned __int64
0x180013df3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013df8  test    rax, rax
0x180013dfb  jz      short loc_180013E0F
0x180013dfd  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x180013e02  xor     r8d, r8d; int
0x180013e05  xor     edx, edx; unsigned __int16 *
0x180013e07  mov     rcx, rax; this
0x180013e0a  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180013e0f  mov     [rsp+48h+var_18], rax
0x180013e14  test    rax, rax
0x180013e17  jnz     short loc_180013E3B
0x180013e19  lea     ecx, [rax+0Eh]; dwErrCode
0x180013e1c  call    cs:__imp_SetLastError
0x180013e23  nop     dword ptr [rax+rax+00h]
0x180013e28  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180013e2f  mov     ecx, 8; int
0x180013e34  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013e39  jmp     short loc_180013E43
0x180013e3b  mov     dword ptr [rsp+48h+var_20+4], 1
0x180013e43  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180013e48  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013e4d  test    rax, rax
0x180013e50  jnz     short loc_180013E91
0x180013e52  call    cs:__imp_GetLastError
0x180013e59  nop     dword ptr [rax+rax+00h]
0x180013e5e  mov     ebx, eax
0x180013e60  test    eax, eax
0x180013e62  jle     short loc_180013E6D
0x180013e64  movzx   ebx, ax
0x180013e67  or      ebx, 80070000h
0x180013e6d  test    ebx, ebx
0x180013e6f  jns     short loc_180013E91
0x180013e71  lea     r9, aWinstationrepo_2; "WinStationReportLoggedOnCompleted"
0x180013e78  mov     r8d, ebx
0x180013e7b  lea     rdx, aBindNullFailed; "Bind( NULL ) failed: 0x%x in %s"
0x180013e82  mov     ecx, 8; int
0x180013e87  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013e8c  jmp     loc_180013F17
0x180013e91  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180013e96  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013e9b  mov     [rsp+48h+arg_0], 0
0x180013ea4  mov     r9, rax
0x180013ea7  xor     r8d, r8d; pReturnValue
0x180013eaa  lea     edx, [r8+0Bh]; nProcNum
0x180013eae  lea     rcx, stru_1800351D0; pProxyInfo
0x180013eb5  call    cs:__imp_NdrClientCall3
0x180013ebc  nop     dword ptr [rax+rax+00h]
0x180013ec1  mov     rbx, rax
0x180013ec4  mov     [rsp+48h+arg_0], rax
0x180013ec9  mov     [rsp+48h+var_28], eax
0x180013ecd  test    eax, eax
0x180013ecf  jns     short loc_180013EEE
0x180013ed1  lea     r9, aWinstationrepo_2; "WinStationReportLoggedOnCompleted"
0x180013ed8  mov     r8d, eax
0x180013edb  lea     rdx, aWinstationrepo_3; "WinStationReportLoggedOnCompleted faile"...
0x180013ee2  mov     ecx, 8; int
0x180013ee7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013eec  jmp     short loc_180013F17
0x180013eee  jmp     short loc_180013F17
0x180013ef0  test    eax, eax
0x180013ef2  jle     short loc_180013EFC
0x180013ef4  movzx   eax, ax
0x180013ef7  or      eax, 80070000h
0x180013efc  mov     ebx, eax
0x180013efe  mov     [rsp+48h+var_28], eax
0x180013f02  mov     r8d, eax
0x180013f05  lea     rdx, aWinstationrepo_1; "WinStationReportLoggedOnCompleted threw"...
0x180013f0c  mov     ecx, 8; int
0x180013f11  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013f16  nop
0x180013f17  test    ebx, ebx
0x180013f19  jns     short loc_180013F22
0x180013f1b  mov     edx, ebx
0x180013f1d  call    MicrosoftTelemetryAssertTriggeredArgs
0x180013f22  mov     ecx, ebx; int
0x180013f24  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180013f29  mov     ecx, eax; dwErrCode
0x180013f2b  call    cs:__imp_SetLastError
0x180013f32  nop     dword ptr [rax+rax+00h]
0x180013f37  test    ebx, ebx
0x180013f39  setns   bl
0x180013f3c  lea     rcx, [rsp+48h+var_20]; this
0x180013f41  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180013f46  mov     al, bl
0x180013f48  add     rsp, 40h
0x180013f4c  pop     rbx
0x180013f4d  retn
0x18003363f  push    rbp
0x180033641  sub     rsp, 20h
0x180033645  mov     rbp, rdx
0x180033648  mov     rcx, [rcx]
0x18003364b  mov     ecx, [rcx]; ExceptionCode
0x18003364d  call    cs:__imp_I_RpcExceptionFilter
0x180033654  nop     dword ptr [rax+rax+00h]
0x180033659  nop
0x18003365a  add     rsp, 20h
0x18003365e  pop     rbp
0x18003365f  retn
```
