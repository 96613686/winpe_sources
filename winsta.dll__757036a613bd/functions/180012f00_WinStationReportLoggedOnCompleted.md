# WinStationReportLoggedOnCompleted

- ea: `0x180012f00`
- end: `0x180013066`
- name: `WinStationReportLoggedOnCompleted`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180012f00`
- `0x1800230b8`
- `0x18002fc44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013049`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f7c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030771`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030771`
- `RPCRT4!NdrClientCall3` at `0x180012fd9`
- `RPCRT4!NdrClientCall3` at `0x180012fd9`

## string_xrefs

- `0x180013023`: `WinStationReportLoggedOnCompleted threw an exception: 0x%x`
- `0x180012f95`: `WinStationReportLoggedOnCompleted`
- `0x180012fef`: `WinStationReportLoggedOnCompleted`
- `0x180012ff9`: `WinStationReportLoggedOnCompleted failed: 0x%x in %s`

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
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 0xBu, 0, v4).Pointer;
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
0x180012f00  push    rbx
0x180012f02  sub     rsp, 40h
0x180012f06  mov     qword ptr [rsp+48h+var_20], 0
0x180012f0f  mov     dword ptr [rsp+48h+arg_0], 0
0x180012f17  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012f1e  mov     ecx, 40h ; '@'; unsigned __int64
0x180012f23  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012f28  test    rax, rax
0x180012f2b  jz      short loc_180012F3F
0x180012f2d  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x180012f32  xor     r8d, r8d; int
0x180012f35  xor     edx, edx; unsigned __int16 *
0x180012f37  mov     rcx, rax; this
0x180012f3a  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180012f3f  mov     [rsp+48h+var_18], rax
0x180012f44  test    rax, rax
0x180012f47  jnz     short loc_180012F65
0x180012f49  lea     ecx, [rax+0Eh]; dwErrCode
0x180012f4c  call    cs:__imp_SetLastError
0x180012f52  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180012f59  mov     ecx, 8; int
0x180012f5e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012f63  jmp     short loc_180012F6D
0x180012f65  mov     dword ptr [rsp+48h+var_20+4], 1
0x180012f6d  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180012f72  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180012f77  test    rax, rax
0x180012f7a  jnz     short loc_180012FB5
0x180012f7c  call    cs:__imp_GetLastError
0x180012f82  mov     ebx, eax
0x180012f84  test    eax, eax
0x180012f86  jle     short loc_180012F91
0x180012f88  movzx   ebx, ax
0x180012f8b  or      ebx, 80070000h
0x180012f91  test    ebx, ebx
0x180012f93  jns     short loc_180012FB5
0x180012f95  lea     r9, aWinstationrepo_2; "WinStationReportLoggedOnCompleted"
0x180012f9c  mov     r8d, ebx
0x180012f9f  lea     rdx, aBindNullFailed; "Bind( NULL ) failed: 0x%x in %s"
0x180012fa6  mov     ecx, 8; int
0x180012fab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012fb0  jmp     loc_180013035
0x180012fb5  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180012fba  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180012fbf  mov     [rsp+48h+arg_0], 0
0x180012fc8  mov     r9, rax
0x180012fcb  xor     r8d, r8d; pReturnValue
0x180012fce  lea     edx, [r8+0Bh]; nProcNum
0x180012fd2  lea     rcx, stru_1800321A0; pProxyInfo
0x180012fd9  call    cs:__imp_NdrClientCall3
0x180012fdf  mov     rbx, rax
0x180012fe2  mov     [rsp+48h+arg_0], rax
0x180012fe7  mov     [rsp+48h+var_28], eax
0x180012feb  test    eax, eax
0x180012fed  jns     short loc_18001300C
0x180012fef  lea     r9, aWinstationrepo_2; "WinStationReportLoggedOnCompleted"
0x180012ff6  mov     r8d, eax
0x180012ff9  lea     rdx, aWinstationrepo_3; "WinStationReportLoggedOnCompleted faile"...
0x180013000  mov     ecx, 8; int
0x180013005  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001300a  jmp     short loc_180013035
0x18001300c  jmp     short loc_180013035
0x18001300e  test    eax, eax
0x180013010  jle     short loc_18001301A
0x180013012  movzx   eax, ax
0x180013015  or      eax, 80070000h
0x18001301a  mov     ebx, eax
0x18001301c  mov     [rsp+48h+var_28], eax
0x180013020  mov     r8d, eax
0x180013023  lea     rdx, aWinstationrepo_1; "WinStationReportLoggedOnCompleted threw"...
0x18001302a  mov     ecx, 8; int
0x18001302f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013034  nop
0x180013035  test    ebx, ebx
0x180013037  jns     short loc_180013040
0x180013039  mov     edx, ebx
0x18001303b  call    MicrosoftTelemetryAssertTriggeredArgs
0x180013040  mov     ecx, ebx; int
0x180013042  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180013047  mov     ecx, eax; dwErrCode
0x180013049  call    cs:__imp_SetLastError
0x18001304f  test    ebx, ebx
0x180013051  setns   bl
0x180013054  lea     rcx, [rsp+48h+var_20]; this
0x180013059  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001305e  mov     al, bl
0x180013060  add     rsp, 40h
0x180013064  pop     rbx
0x180013065  retn
0x180030763  push    rbp
0x180030765  sub     rsp, 20h
0x180030769  mov     rbp, rdx
0x18003076c  mov     rcx, [rcx]
0x18003076f  mov     ecx, [rcx]; ExceptionCode
0x180030771  call    cs:__imp_I_RpcExceptionFilter
0x180030777  nop
0x180030778  add     rsp, 20h
0x18003077c  pop     rbp
0x18003077d  retn
```
