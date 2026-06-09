# WinStationPreCreateGlassReplacementSessionEx

- ea: `0x180011ef0`
- end: `0x1800122fb`
- name: `WinStationPreCreateGlassReplacementSessionEx`
- size: `1035`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011ed0`

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180011ef0`
- `0x1800249e8`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800122c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800122c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001228b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001228b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001202c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001202c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001227a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001227a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012007`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001224f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012007`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001224f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003355d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003355d`
- `RPCRT4!NdrClientCall3` at `0x1800121a2`
- `RPCRT4!NdrClientCall3` at `0x1800121a2`

## string_xrefs

- `0x18001205d`: `WinStationPreCreateGlassReplacementSessionEx`
- `0x1800121be`: `WinStationPreCreateGlassReplacementSessionEx`
- `0x180012053`: `LocalAlloc on pszInitialCommand failed: 0x%x in %s`
- `0x180012138`: `Calling WinStationPreCreateGlassReplacementSession()`
- `0x1800121c8`: `RpcCreateSession failed: 0x%x in %s`
- `0x1800120e2`: `ExpandEnvironmentStrings on initial command failed: 0x%x in %s`
- `0x1800121f5`: `RpcCreateSession threw an exception: 0x%x`
- `0x180012220`: `WinStationPreCreateGlassReplacementSession() return 0x%08x, Session id %d`

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
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_180035260,
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
0x180011ef0  mov     r11, rsp
0x180011ef3  push    rbx
0x180011ef4  push    rsi
0x180011ef5  push    rdi
0x180011ef6  push    r12
0x180011ef8  push    r13
0x180011efa  push    r14
0x180011efc  sub     rsp, 108h
0x180011f03  mov     rax, cs:__security_cookie
0x180011f0a  xor     rax, rsp
0x180011f0d  mov     [rsp+138h+var_48], rax
0x180011f15  mov     r13, r9
0x180011f18  mov     [rsp+138h+var_D8], r9
0x180011f1d  mov     [rsp+138h+var_E4], r8d
0x180011f22  mov     [rsp+138h+var_E0], edx
0x180011f26  mov     rsi, rcx
0x180011f29  mov     [rsp+138h+lpSrc], rcx
0x180011f31  mov     [rsp+138h+var_B0], r9
0x180011f39  xor     edi, edi
0x180011f3b  mov     ebx, edi
0x180011f3d  xorps   xmm0, xmm0
0x180011f40  xor     eax, eax
0x180011f42  movups  [rsp+138h+var_A8], xmm0
0x180011f4a  movups  [rsp+138h+var_98], xmm0
0x180011f52  movups  [rsp+138h+var_88], xmm0
0x180011f5a  mov     [r11-78h], rax
0x180011f5e  mov     r12d, edi
0x180011f61  mov     [rsp+138h+var_C0], rdi
0x180011f66  movups  xmmword ptr [r11-70h], xmm0
0x180011f6b  mov     qword ptr [rsp+138h+var_D0], rdi
0x180011f70  mov     [rsp+138h+var_E8], edi
0x180011f74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011f7b  lea     ecx, [rdi+40h]; unsigned __int64
0x180011f7e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011f83  test    rax, rax
0x180011f86  jz      loc_1800122BA
0x180011f8c  lea     r9, [rsp+138h+var_E8]; unsigned int *
0x180011f91  xor     r8d, r8d; int
0x180011f94  xor     edx, edx; unsigned __int16 *
0x180011f96  mov     rcx, rax; this
0x180011f99  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180011f9e  mov     [rsp+138h+var_C8], rax
0x180011fa3  test    rax, rax
0x180011fa6  jz      loc_1800122C2
0x180011fac  mov     r14d, 1
0x180011fb2  mov     dword ptr [rsp+138h+var_D0+4], r14d
0x180011fb7  lea     rcx, [rsp+138h+var_D0]; unsigned __int16 *
0x180011fbc  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011fc1  test    rax, rax
0x180011fc4  jz      loc_18001228B
0x180011fca  xorps   xmm0, xmm0
0x180011fcd  xor     eax, eax
0x180011fcf  movups  [rsp+138h+var_A8], xmm0
0x180011fd7  movups  [rsp+138h+var_98], xmm0
0x180011fdf  movups  [rsp+138h+var_88], xmm0
0x180011fe7  mov     [rsp+138h+var_78], rax
0x180011fef  test    rsi, rsi
0x180011ff2  jz      loc_1800120EE
0x180011ff8  lea     r8d, [rax+0Ah]; nSize
0x180011ffc  lea     rdx, [rsp+138h+Dst]; lpDst
0x180012004  mov     rcx, rsi; lpSrc
0x180012007  call    cs:__imp_ExpandEnvironmentStringsW
0x18001200e  nop     dword ptr [rax+rax+00h]
0x180012013  mov     esi, eax
0x180012015  test    eax, eax
0x180012017  jz      loc_1800120BF
0x18001201d  lea     r13d, [rsi+1]
0x180012021  mov     edx, r13d
0x180012024  add     rdx, rdx; uBytes
0x180012027  mov     ecx, 40h ; '@'; uFlags
0x18001202c  call    cs:__imp_LocalAlloc
0x180012033  nop     dword ptr [rax+rax+00h]
0x180012038  mov     r12, rax
0x18001203b  mov     [rsp+138h+var_C0], rax
0x180012040  mov     eax, 8007000Eh
0x180012045  test    r12, r12
0x180012048  cmovz   ebx, eax
0x18001204b  test    ebx, ebx
0x18001204d  jns     loc_180012241
0x180012053  lea     rdx, aLocalallocOnPs; "LocalAlloc on pszInitialCommand failed:"...
0x18001205a  mov     r8d, ebx
0x18001205d  lea     r9, aWinstationprec_1; "WinStationPreCreateGlassReplacementSess"...
0x180012064  mov     ecx, 8; int
0x180012069  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001206e  test    r12, r12
0x180012071  jnz     loc_180012277
0x180012077  mov     ecx, ebx; int
0x180012079  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18001207e  mov     ecx, eax; dwErrCode
0x180012080  call    cs:__imp_SetLastError
0x180012087  nop     dword ptr [rax+rax+00h]
0x18001208c  test    ebx, ebx
0x18001208e  setns   bl
0x180012091  lea     rcx, [rsp+138h+var_D0]; this
0x180012096  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001209b  mov     al, bl
0x18001209d  mov     rcx, [rsp+138h+var_48]
0x1800120a5  xor     rcx, rsp; StackCookie
0x1800120a8  call    __security_check_cookie
0x1800120ad  add     rsp, 108h
0x1800120b4  pop     r14
0x1800120b6  pop     r13
0x1800120b8  pop     r12
0x1800120ba  pop     rdi
0x1800120bb  pop     rsi
0x1800120bc  pop     rbx
0x1800120bd  retn
0x1800120bf  call    cs:__imp_GetLastError
0x1800120c6  nop     dword ptr [rax+rax+00h]
0x1800120cb  mov     ebx, eax
0x1800120cd  test    eax, eax
0x1800120cf  jle     short loc_1800120DA
0x1800120d1  movzx   ebx, ax
0x1800120d4  or      ebx, 80070000h
0x1800120da  test    ebx, ebx
0x1800120dc  jns     loc_18001201D
0x1800120e2  lea     rdx, aExpandenvironm; "ExpandEnvironmentStrings on initial com"...
0x1800120e9  jmp     loc_18001205A
0x1800120ee  mov     esi, edi
0x1800120f0  mov     dword ptr [rsp+138h+var_A8], r14d
0x1800120f8  test    r12, r12
0x1800120fb  jz      loc_180012234
0x180012101  add     si, r14w
0x180012105  add     si, si
0x180012108  mov     word ptr [rsp+138h+var_A8+8], si
0x180012110  mov     qword ptr [rsp+138h+var_98], r12
0x180012118  movups  xmm0, cs:TERMINAL_TYPE_REGULAR_DESKTOP
0x18001211f  movdqu  [rsp+138h+var_98+8], xmm0
0x180012128  movups  xmm1, cs:LICENSE_TYPE_BUILTIN
0x18001212f  movdqu  [rsp+138h+var_88+8], xmm1
0x180012138  lea     rdx, aCallingWinstat; "Calling WinStationPreCreateGlassReplace"...
0x18001213f  mov     ecx, r14d; int
0x180012142  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012147  nop
0x180012148  mov     ebx, edi
0x18001214a  mov     esi, [rsp+138h+var_E4]
0x18001214e  test    esi, esi
0x180012150  setnz   bl
0x180012153  lea     rcx, [rsp+138h+var_D0]; unsigned __int16 *
0x180012158  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001215d  mov     [rsp+138h+var_D8], rdi
0x180012162  lea     rcx, [rsp+138h+var_70]
0x18001216a  mov     [rsp+138h+var_F0], rcx
0x18001216f  mov     [rsp+138h+var_F8], r13
0x180012174  mov     ecx, [rsp+138h+var_E0]
0x180012178  mov     [rsp+138h+var_100], ecx
0x18001217c  mov     [rsp+138h+var_108], esi
0x180012180  mov     [rsp+138h+var_110], ebx
0x180012184  lea     rcx, [rsp+138h+var_A8]
0x18001218c  mov     [rsp+138h+var_118], rcx
0x180012191  mov     r9, rax
0x180012194  xor     r8d, r8d; pReturnValue
0x180012197  lea     edx, [r8+2]; nProcNum
0x18001219b  lea     rcx, stru_180035260; pProxyInfo
0x1800121a2  call    cs:__imp_NdrClientCall3
0x1800121a9  nop     dword ptr [rax+rax+00h]
0x1800121ae  mov     rbx, rax
0x1800121b1  mov     [rsp+138h+var_D8], rax
0x1800121b6  mov     [rsp+138h+var_DC], eax
0x1800121ba  test    eax, eax
0x1800121bc  jns     short loc_1800121DE
0x1800121be  lea     r9, aWinstationprec_1; "WinStationPreCreateGlassReplacementSess"...
0x1800121c5  mov     r8d, eax
0x1800121c8  lea     rdx, aRpccreatesessi; "RpcCreateSession failed: 0x%x in %s"
0x1800121cf  mov     ecx, 8; int
0x1800121d4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800121d9  jmp     loc_18001206E
0x1800121de  jmp     short loc_180012219
0x1800121e0  test    eax, eax
0x1800121e2  jle     short loc_1800121EC
0x1800121e4  movzx   eax, ax
0x1800121e7  or      eax, 80070000h
0x1800121ec  mov     ebx, eax
0x1800121ee  mov     [rsp+138h+var_DC], eax
0x1800121f2  mov     r8d, eax
0x1800121f5  lea     rdx, aRpccreatesessi_0; "RpcCreateSession threw an exception: 0x"...
0x1800121fc  mov     ecx, 8; int
0x180012201  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012206  mov     r14d, 1
0x18001220c  mov     r12, [rsp+138h+var_C0]
0x180012211  mov     r13, [rsp+138h+var_B0]
0x180012219  mov     r9d, [r13+0]
0x18001221d  mov     r8d, ebx
0x180012220  lea     rdx, aWinstationprec_2; "WinStationPreCreateGlassReplacementSess"...
0x180012227  mov     ecx, r14d; int
0x18001222a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001222f  jmp     loc_18001206E
0x180012234  mov     word ptr [rsp+138h+var_A8+8], di
0x18001223c  jmp     loc_180012110
0x180012241  mov     r8d, r13d; nSize
0x180012244  mov     rdx, r12; lpDst
0x180012247  mov     rcx, [rsp+138h+lpSrc]; lpSrc
0x18001224f  call    cs:__imp_ExpandEnvironmentStringsW
0x180012256  nop     dword ptr [rax+rax+00h]
0x18001225b  mov     ecx, 8007054Fh
0x180012260  test    eax, eax
0x180012262  cmovz   ebx, ecx
0x180012265  test    ebx, ebx
0x180012267  js      loc_1800122EF
0x18001226d  mov     r13, [rsp+138h+var_D8]
0x180012272  jmp     loc_1800120F0
0x180012277  mov     rcx, r12; hMem
0x18001227a  call    cs:__imp_LocalFree
0x180012281  nop     dword ptr [rax+rax+00h]
0x180012286  jmp     loc_180012077
0x18001228b  call    cs:__imp_GetLastError
0x180012292  nop     dword ptr [rax+rax+00h]
0x180012297  mov     ebx, eax
0x180012299  test    eax, eax
0x18001229b  jle     short loc_1800122A6
0x18001229d  movzx   ebx, ax
0x1800122a0  or      ebx, 80070000h
0x1800122a6  test    ebx, ebx
0x1800122a8  jns     loc_180011FCA
0x1800122ae  lea     rdx, aBindNullFailed; "Bind( NULL ) failed: 0x%x in %s"
0x1800122b5  jmp     loc_18001205A
0x1800122ba  mov     rax, rdi
0x1800122bd  jmp     loc_180011F9E
0x1800122c2  mov     ecx, 0Eh; dwErrCode
0x1800122c7  call    cs:__imp_SetLastError
0x1800122ce  nop     dword ptr [rax+rax+00h]
0x1800122d3  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800122da  mov     ecx, 8; int
0x1800122df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800122e4  mov     r14d, 1
0x1800122ea  jmp     loc_180011FB7
0x1800122ef  lea     rdx, a2ndExpandenvir; "2nd ExpandEnvironmentStrings failed fai"...
0x1800122f6  jmp     loc_18001205A
0x18003354f  push    rbp
0x180033551  sub     rsp, 50h
0x180033555  mov     rbp, rdx
0x180033558  mov     rcx, [rcx]
0x18003355b  mov     ecx, [rcx]; ExceptionCode
0x18003355d  call    cs:__imp_I_RpcExceptionFilter
0x180033564  nop     dword ptr [rax+rax+00h]
0x180033569  nop
0x18003356a  add     rsp, 50h
0x18003356e  pop     rbp
0x18003356f  retn
```
