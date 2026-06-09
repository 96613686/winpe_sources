# WinStationSystemShutdownStarted

- ea: `0x180013d80`
- end: `0x180013eda`
- name: `WinStationSystemShutdownStarted`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180013d80`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013dce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e0d`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800307f9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800307f9`
- `RPCRT4!NdrClientCall3` at `0x180013e53`
- `RPCRT4!NdrClientCall3` at `0x180013e53`

## string_xrefs

- `0x180013dfe`: `Failed to open binding`

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
    v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 3u, 0, v5, a1).Pointer;
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
0x180013d80  push    rbx
0x180013d82  sub     rsp, 50h
0x180013d86  mov     ebx, ecx
0x180013d88  mov     qword ptr [rsp+58h+var_20], 0
0x180013d91  mov     dword ptr [rsp+58h+arg_8], 0
0x180013d99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013da0  mov     ecx, 40h ; '@'; unsigned __int64
0x180013da5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013daa  test    rax, rax
0x180013dad  jz      short loc_180013DC1
0x180013daf  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x180013db4  xor     r8d, r8d; int
0x180013db7  xor     edx, edx; unsigned __int16 *
0x180013db9  mov     rcx, rax; this
0x180013dbc  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180013dc1  mov     [rsp+58h+var_18], rax
0x180013dc6  test    rax, rax
0x180013dc9  jnz     short loc_180013DE7
0x180013dcb  lea     ecx, [rax+0Eh]; dwErrCode
0x180013dce  call    cs:__imp_SetLastError
0x180013dd4  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180013ddb  mov     ecx, 8; int
0x180013de0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013de5  jmp     short loc_180013DEF
0x180013de7  mov     dword ptr [rsp+58h+var_20+4], 1
0x180013def  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180013df4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013df9  test    rax, rax
0x180013dfc  jnz     short loc_180013E2B
0x180013dfe  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180013e05  lea     ecx, [rax+8]; int
0x180013e08  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013e0d  call    cs:__imp_GetLastError
0x180013e13  mov     ebx, eax
0x180013e15  test    eax, eax
0x180013e17  jle     loc_180013EAD
0x180013e1d  movzx   ebx, ax
0x180013e20  or      ebx, 80070000h
0x180013e26  jmp     loc_180013EAD
0x180013e2b  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180013e30  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180013e35  mov     [rsp+58h+arg_8], 0
0x180013e3e  mov     [rsp+58h+var_38], ebx
0x180013e42  mov     r9, rax
0x180013e45  xor     r8d, r8d; pReturnValue
0x180013e48  lea     edx, [r8+3]; nProcNum
0x180013e4c  lea     rcx, stru_1800321A0; pProxyInfo
0x180013e53  call    cs:__imp_NdrClientCall3
0x180013e59  mov     rbx, rax
0x180013e5c  mov     [rsp+58h+arg_8], rax
0x180013e61  mov     [rsp+58h+var_28], eax
0x180013e65  jmp     short loc_180013E8E
0x180013e67  mov     ebx, eax
0x180013e69  mov     r8d, eax
0x180013e6c  lea     rdx, aRpcsystemshutd; "RpcSystemShutdownStarted threw an excep"...
0x180013e73  mov     ecx, 8; int
0x180013e78  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013e7d  test    ebx, ebx
0x180013e7f  jle     short loc_180013E8A
0x180013e81  movzx   ebx, bx
0x180013e84  or      ebx, 80070000h
0x180013e8a  mov     [rsp+58h+var_28], ebx
0x180013e8e  test    ebx, ebx
0x180013e90  jns     short loc_180013EC8
0x180013e92  lea     r9, aWinstationsyst_2; "WinStationSystemShutdownStarted"
0x180013e99  mov     r8d, ebx
0x180013e9c  lea     rdx, aRpcsystemshutd_0; "RpcSystemShutdownStarted failed: 0x%x i"...
0x180013ea3  mov     ecx, 8; int
0x180013ea8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013ead  test    ebx, ebx
0x180013eaf  jns     short loc_180013EC8
0x180013eb1  mov     ecx, ebx; int
0x180013eb3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180013eb8  mov     ebx, eax
0x180013eba  lea     rcx, [rsp+58h+var_20]; this
0x180013ebf  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180013ec4  mov     eax, ebx
0x180013ec6  jmp     short loc_180013ED4
0x180013ec8  lea     rcx, [rsp+58h+var_20]; this
0x180013ecd  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180013ed2  xor     eax, eax
0x180013ed4  add     rsp, 50h
0x180013ed8  pop     rbx
0x180013ed9  retn
0x1800307eb  push    rbp
0x1800307ed  sub     rsp, 30h
0x1800307f1  mov     rbp, rdx
0x1800307f4  mov     rcx, [rcx]
0x1800307f7  mov     ecx, [rcx]; ExceptionCode
0x1800307f9  call    cs:__imp_I_RpcExceptionFilter
0x1800307ff  nop
0x180030800  add     rsp, 30h
0x180030804  pop     rbp
0x180030805  retn
```
