# WinStationPreCreateGlassReplacementSessionEx

- ea: `0x180010d90`
- end: `0x180011160`
- name: `WinStationPreCreateGlassReplacementSessionEx`
- size: `976`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010d70`

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180010d90`
- `0x1800230b8`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011132`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ec6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110f1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010ea7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800110d0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010ea7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800110d0`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030661`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030661`
- `RPCRT4!NdrClientCall3` at `0x180011029`
- `RPCRT4!NdrClientCall3` at `0x180011029`

## string_xrefs

- `0x180010ef1`: `WinStationPreCreateGlassReplacementSessionEx`
- `0x18001103f`: `WinStationPreCreateGlassReplacementSessionEx`
- `0x180010ee7`: `LocalAlloc on pszInitialCommand failed: 0x%x in %s`
- `0x180010fbf`: `Calling WinStationPreCreateGlassReplacementSession()`
- `0x180011049`: `RpcCreateSession failed: 0x%x in %s`
- `0x180010f69`: `ExpandEnvironmentStrings on initial command failed: 0x%x in %s`
- `0x180011076`: `RpcCreateSession threw an exception: 0x%x`
- `0x1800110a1`: `WinStationPreCreateGlassReplacementSession() return 0x%08x, Session id %d`

## pseudocode

```c
bool __fastcall WinStationPreCreateGlassReplacementSessionEx(LPCWSTR lpSrc, int a2, int a3, _DWORD *a4)
{
  _DWORD *Simple; // r13
  signed int Pointer; // ebx
  WCHAR *v7; // r12
  CPublicBinding *v8; // rax
  CPublicBinding *v9; // rax
  DWORD v10; // esi
  DWORD v11; // eax
  signed int v13; // eax
  int v14; // esi
  BOOL v15; // ebx
  __int64 v16; // rax
  CLIENT_CALL_RETURN v17; // rax
  signed int LastError; // eax
  __int64 v19; // [rsp+50h] [rbp-E8h] BYREF
  int v20; // [rsp+58h] [rbp-E0h]
  int v21; // [rsp+5Ch] [rbp-DCh]
  CLIENT_CALL_RETURN v22; // [rsp+60h] [rbp-D8h]
  unsigned __int16 v23[4]; // [rsp+68h] [rbp-D0h] BYREF
  CPublicBinding *v24; // [rsp+70h] [rbp-C8h]
  WCHAR *v25; // [rsp+78h] [rbp-C0h]
  LPCWSTR lpSrca; // [rsp+80h] [rbp-B8h]
  _DWORD *v27; // [rsp+88h] [rbp-B0h]
  __int128 v28; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v29[40]; // [rsp+A0h] [rbp-98h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-70h] BYREF
  WCHAR Dst[12]; // [rsp+D8h] [rbp-60h] BYREF

  Simple = a4;
  v22.Simple = (LONG_PTR)a4;
  HIDWORD(v19) = a3;
  v20 = a2;
  lpSrca = lpSrc;
  v27 = a4;
  Pointer = 0;
  v28 = 0;
  memset(v29, 0, sizeof(v29));
  v7 = 0;
  v25 = 0;
  v30 = 0;
  *(_QWORD *)v23 = 0;
  LODWORD(v19) = 0;
  v8 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
    v9 = CPublicBinding::CPublicBinding(v8, 0, 0, (unsigned int *)&v19);
  else
    v9 = 0;
  v24 = v9;
  if ( v9 )
  {
    *(_DWORD *)&v23[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( !CSmartPublicBinding::operator void *(v23) )
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    if ( Pointer < 0 )
    {
      _DbgPrintMessage(
        8,
        "Bind( NULL ) failed: 0x%x in %s",
        (unsigned int)Pointer,
        "WinStationPreCreateGlassReplacementSessionEx");
      goto LABEL_12;
    }
  }
  v28 = 0;
  memset(v29, 0, sizeof(v29));
  if ( !lpSrc )
  {
    LOWORD(v10) = 0;
LABEL_20:
    LODWORD(v28) = 1;
    if ( v7 )
      WORD4(v28) = 2 * (v10 + 1);
    else
      WORD4(v28) = 0;
    *(_QWORD *)v29 = v7;
    *(_OWORD *)&v29[8] = TERMINAL_TYPE_REGULAR_DESKTOP;
    *(_OWORD *)&v29[24] = LICENSE_TYPE_BUILTIN;
    _DbgPrintMessage(1, "Calling WinStationPreCreateGlassReplacementSession()");
    v14 = HIDWORD(v19);
    v15 = HIDWORD(v19) != 0;
    v16 = CSmartPublicBinding::operator void *(v23);
    v22.Simple = 0;
    v17.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_180032260,
                    2u,
                    0,
                    v16,
                    &v28,
                    v15,
                    v14,
                    v20,
                    Simple,
                    &v30,
                    v19).Pointer;
    Pointer = (signed int)v17.Pointer;
    v22.Pointer = v17.Pointer;
    v21 = (int)v17.Pointer;
    if ( SLODWORD(v17.Simple) >= 0 )
      _DbgPrintMessage(
        1,
        "WinStationPreCreateGlassReplacementSession() return 0x%08x, Session id %d",
        LODWORD(v17.Pointer),
        *Simple);
    else
      _DbgPrintMessage(
        8,
        "RpcCreateSession failed: 0x%x in %s",
        LODWORD(v17.Pointer),
        "WinStationPreCreateGlassReplacementSessionEx");
    goto LABEL_12;
  }
  v10 = ExpandEnvironmentStringsW(lpSrc, Dst, 0xAu);
  if ( !v10 )
  {
    v13 = GetLastError();
    Pointer = v13;
    if ( v13 > 0 )
      Pointer = (unsigned __int16)v13 | 0x80070000;
    if ( Pointer < 0 )
    {
      _DbgPrintMessage(
        8,
        "ExpandEnvironmentStrings on initial command failed: 0x%x in %s",
        (unsigned int)Pointer,
        "WinStationPreCreateGlassReplacementSessionEx");
      goto LABEL_12;
    }
  }
  v7 = (WCHAR *)LocalAlloc(0x40u, 2LL * (v10 + 1));
  v25 = v7;
  if ( !v7 )
    Pointer = -2147024882;
  if ( Pointer < 0 )
  {
    _DbgPrintMessage(
      8,
      "LocalAlloc on pszInitialCommand failed: 0x%x in %s",
      (unsigned int)Pointer,
      "WinStationPreCreateGlassReplacementSessionEx");
    goto LABEL_12;
  }
  if ( !ExpandEnvironmentStringsW(lpSrca, v7, v10 + 1) )
    Pointer = -2147023537;
  if ( Pointer >= 0 )
  {
    Simple = (_DWORD *)v22.Simple;
    goto LABEL_20;
  }
  _DbgPrintMessage(
    8,
    "2nd ExpandEnvironmentStrings failed failed: 0x%x in %s",
    (unsigned int)Pointer,
    "WinStationPreCreateGlassReplacementSessionEx");
LABEL_12:
  if ( v7 )
    LocalFree(v7);
  v11 = ConvertHRESULT2WIN32(Pointer);
  SetLastError(v11);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v23);
  return Pointer >= 0;
}

```

## disassembly

```asm
0x180010d90  mov     r11, rsp
0x180010d93  push    rbx
0x180010d94  push    rsi
0x180010d95  push    rdi
0x180010d96  push    r12
0x180010d98  push    r13
0x180010d9a  push    r14
0x180010d9c  sub     rsp, 108h
0x180010da3  mov     rax, cs:__security_cookie
0x180010daa  xor     rax, rsp
0x180010dad  mov     [rsp+138h+var_48], rax
0x180010db5  mov     r13, r9
0x180010db8  mov     [rsp+138h+var_D8], r9
0x180010dbd  mov     [rsp+138h+var_E4], r8d
0x180010dc2  mov     [rsp+138h+var_E0], edx
0x180010dc6  mov     rsi, rcx
0x180010dc9  mov     [rsp+138h+lpSrc], rcx
0x180010dd1  mov     [rsp+138h+var_B0], r9
0x180010dd9  xor     edi, edi
0x180010ddb  mov     ebx, edi
0x180010ddd  xorps   xmm0, xmm0
0x180010de0  xor     eax, eax
0x180010de2  movups  [rsp+138h+var_A8], xmm0
0x180010dea  movups  [rsp+138h+var_98], xmm0
0x180010df2  movups  [rsp+138h+var_88], xmm0
0x180010dfa  mov     [r11-78h], rax
0x180010dfe  mov     r12d, edi
0x180010e01  mov     [rsp+138h+var_C0], rdi
0x180010e06  movups  xmmword ptr [r11-70h], xmm0
0x180010e0b  mov     qword ptr [rsp+138h+var_D0], rdi
0x180010e10  mov     [rsp+138h+var_E8], edi
0x180010e14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010e1b  lea     ecx, [rdi+40h]; unsigned __int64
0x180010e1e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010e23  test    rax, rax
0x180010e26  jz      loc_180011125
0x180010e2c  lea     r9, [rsp+138h+var_E8]; unsigned int *
0x180010e31  xor     r8d, r8d; int
0x180010e34  xor     edx, edx; unsigned __int16 *
0x180010e36  mov     rcx, rax; this
0x180010e39  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180010e3e  mov     [rsp+138h+var_C8], rax
0x180010e43  test    rax, rax
0x180010e46  jz      loc_18001112D
0x180010e4c  mov     r14d, 1
0x180010e52  mov     dword ptr [rsp+138h+var_D0+4], r14d
0x180010e57  lea     rcx, [rsp+138h+var_D0]; unsigned __int16 *
0x180010e5c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180010e61  test    rax, rax
0x180010e64  jz      loc_1800110FC
0x180010e6a  xorps   xmm0, xmm0
0x180010e6d  xor     eax, eax
0x180010e6f  movups  [rsp+138h+var_A8], xmm0
0x180010e77  movups  [rsp+138h+var_98], xmm0
0x180010e7f  movups  [rsp+138h+var_88], xmm0
0x180010e87  mov     [rsp+138h+var_78], rax
0x180010e8f  test    rsi, rsi
0x180010e92  jz      loc_180010F75
0x180010e98  lea     r8d, [rax+0Ah]; nSize
0x180010e9c  lea     rdx, [rsp+138h+Dst]; lpDst
0x180010ea4  mov     rcx, rsi; lpSrc
0x180010ea7  call    cs:__imp_ExpandEnvironmentStringsW
0x180010ead  mov     esi, eax
0x180010eaf  test    eax, eax
0x180010eb1  jz      loc_180010F4C
0x180010eb7  lea     r13d, [rsi+1]
0x180010ebb  mov     edx, r13d
0x180010ebe  add     rdx, rdx; uBytes
0x180010ec1  mov     ecx, 40h ; '@'; uFlags
0x180010ec6  call    cs:__imp_LocalAlloc
0x180010ecc  mov     r12, rax
0x180010ecf  mov     [rsp+138h+var_C0], rax
0x180010ed4  mov     eax, 8007000Eh
0x180010ed9  test    r12, r12
0x180010edc  cmovz   ebx, eax
0x180010edf  test    ebx, ebx
0x180010ee1  jns     loc_1800110C2
0x180010ee7  lea     rdx, aLocalallocOnPs; "LocalAlloc on pszInitialCommand failed:"...
0x180010eee  mov     r8d, ebx
0x180010ef1  lea     r9, aWinstationprec_1; "WinStationPreCreateGlassReplacementSess"...
0x180010ef8  mov     ecx, 8; int
0x180010efd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010f02  test    r12, r12
0x180010f05  jnz     loc_1800110EE
0x180010f0b  mov     ecx, ebx; int
0x180010f0d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180010f12  mov     ecx, eax; dwErrCode
0x180010f14  call    cs:__imp_SetLastError
0x180010f1a  test    ebx, ebx
0x180010f1c  setns   bl
0x180010f1f  lea     rcx, [rsp+138h+var_D0]; this
0x180010f24  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180010f29  mov     al, bl
0x180010f2b  mov     rcx, [rsp+138h+var_48]
0x180010f33  xor     rcx, rsp; StackCookie
0x180010f36  call    __security_check_cookie
0x180010f3b  add     rsp, 108h
0x180010f42  pop     r14
0x180010f44  pop     r13
0x180010f46  pop     r12
0x180010f48  pop     rdi
0x180010f49  pop     rsi
0x180010f4a  pop     rbx
0x180010f4b  retn
0x180010f4c  call    cs:__imp_GetLastError
0x180010f52  mov     ebx, eax
0x180010f54  test    eax, eax
0x180010f56  jle     short loc_180010F61
0x180010f58  movzx   ebx, ax
0x180010f5b  or      ebx, 80070000h
0x180010f61  test    ebx, ebx
0x180010f63  jns     loc_180010EB7
0x180010f69  lea     rdx, aExpandenvironm; "ExpandEnvironmentStrings on initial com"...
0x180010f70  jmp     loc_180010EEE
0x180010f75  mov     esi, edi
0x180010f77  mov     dword ptr [rsp+138h+var_A8], r14d
0x180010f7f  test    r12, r12
0x180010f82  jz      loc_1800110B5
0x180010f88  add     si, r14w
0x180010f8c  add     si, si
0x180010f8f  mov     word ptr [rsp+138h+var_A8+8], si
0x180010f97  mov     qword ptr [rsp+138h+var_98], r12
0x180010f9f  movups  xmm0, cs:TERMINAL_TYPE_REGULAR_DESKTOP
0x180010fa6  movdqu  [rsp+138h+var_98+8], xmm0
0x180010faf  movups  xmm1, cs:LICENSE_TYPE_BUILTIN
0x180010fb6  movdqu  [rsp+138h+var_88+8], xmm1
0x180010fbf  lea     rdx, aCallingWinstat; "Calling WinStationPreCreateGlassReplace"...
0x180010fc6  mov     ecx, r14d; int
0x180010fc9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010fce  nop
0x180010fcf  mov     ebx, edi
0x180010fd1  mov     esi, [rsp+138h+var_E4]
0x180010fd5  test    esi, esi
0x180010fd7  setnz   bl
0x180010fda  lea     rcx, [rsp+138h+var_D0]; unsigned __int16 *
0x180010fdf  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180010fe4  mov     [rsp+138h+var_D8], rdi
0x180010fe9  lea     rcx, [rsp+138h+var_70]
0x180010ff1  mov     [rsp+138h+var_F0], rcx
0x180010ff6  mov     [rsp+138h+var_F8], r13
0x180010ffb  mov     ecx, [rsp+138h+var_E0]
0x180010fff  mov     [rsp+138h+var_100], ecx
0x180011003  mov     [rsp+138h+var_108], esi
0x180011007  mov     [rsp+138h+var_110], ebx
0x18001100b  lea     rcx, [rsp+138h+var_A8]
0x180011013  mov     [rsp+138h+var_118], rcx
0x180011018  mov     r9, rax
0x18001101b  xor     r8d, r8d; pReturnValue
0x18001101e  lea     edx, [r8+2]; nProcNum
0x180011022  lea     rcx, stru_180032260; pProxyInfo
0x180011029  call    cs:__imp_NdrClientCall3
0x18001102f  mov     rbx, rax
0x180011032  mov     [rsp+138h+var_D8], rax
0x180011037  mov     [rsp+138h+var_DC], eax
0x18001103b  test    eax, eax
0x18001103d  jns     short loc_18001105F
0x18001103f  lea     r9, aWinstationprec_1; "WinStationPreCreateGlassReplacementSess"...
0x180011046  mov     r8d, eax
0x180011049  lea     rdx, aRpccreatesessi; "RpcCreateSession failed: 0x%x in %s"
0x180011050  mov     ecx, 8; int
0x180011055  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001105a  jmp     loc_180010F02
0x18001105f  jmp     short loc_18001109A
0x180011061  test    eax, eax
0x180011063  jle     short loc_18001106D
0x180011065  movzx   eax, ax
0x180011068  or      eax, 80070000h
0x18001106d  mov     ebx, eax
0x18001106f  mov     [rsp+138h+var_DC], eax
0x180011073  mov     r8d, eax
0x180011076  lea     rdx, aRpccreatesessi_0; "RpcCreateSession threw an exception: 0x"...
0x18001107d  mov     ecx, 8; int
0x180011082  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011087  mov     r14d, 1
0x18001108d  mov     r12, [rsp+138h+var_C0]
0x180011092  mov     r13, [rsp+138h+var_B0]
0x18001109a  mov     r9d, [r13+0]
0x18001109e  mov     r8d, ebx
0x1800110a1  lea     rdx, aWinstationprec_2; "WinStationPreCreateGlassReplacementSess"...
0x1800110a8  mov     ecx, r14d; int
0x1800110ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800110b0  jmp     loc_180010F02
0x1800110b5  mov     word ptr [rsp+138h+var_A8+8], di
0x1800110bd  jmp     loc_180010F97
0x1800110c2  mov     r8d, r13d; nSize
0x1800110c5  mov     rdx, r12; lpDst
0x1800110c8  mov     rcx, [rsp+138h+lpSrc]; lpSrc
0x1800110d0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800110d6  mov     ecx, 8007054Fh
0x1800110db  test    eax, eax
0x1800110dd  cmovz   ebx, ecx
0x1800110e0  test    ebx, ebx
0x1800110e2  js      short loc_180011154
0x1800110e4  mov     r13, [rsp+138h+var_D8]
0x1800110e9  jmp     loc_180010F77
0x1800110ee  mov     rcx, r12; hMem
0x1800110f1  call    cs:__imp_LocalFree
0x1800110f7  jmp     loc_180010F0B
0x1800110fc  call    cs:__imp_GetLastError
0x180011102  mov     ebx, eax
0x180011104  test    eax, eax
0x180011106  jle     short loc_180011111
0x180011108  movzx   ebx, ax
0x18001110b  or      ebx, 80070000h
0x180011111  test    ebx, ebx
0x180011113  jns     loc_180010E6A
0x180011119  lea     rdx, aBindNullFailed; "Bind( NULL ) failed: 0x%x in %s"
0x180011120  jmp     loc_180010EEE
0x180011125  mov     rax, rdi
0x180011128  jmp     loc_180010E3E
0x18001112d  mov     ecx, 0Eh; dwErrCode
0x180011132  call    cs:__imp_SetLastError
0x180011138  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18001113f  mov     ecx, 8; int
0x180011144  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011149  mov     r14d, 1
0x18001114f  jmp     loc_180010E57
0x180011154  lea     rdx, a2ndExpandenvir; "2nd ExpandEnvironmentStrings failed fai"...
0x18001115b  jmp     loc_180010EEE
0x180030653  push    rbp
0x180030655  sub     rsp, 50h
0x180030659  mov     rbp, rdx
0x18003065c  mov     rcx, [rcx]
0x18003065f  mov     ecx, [rcx]; ExceptionCode
0x180030661  call    cs:__imp_I_RpcExceptionFilter
0x180030667  nop
0x180030668  add     rsp, 50h
0x18003066c  pop     rbp
0x18003066d  retn
```
