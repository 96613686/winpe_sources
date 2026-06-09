# CSrmFileSafe::SafeOpenForRead(void)

- ea: `0x180079724`
- end: `0x180079b93`
- name: `?SafeOpenForRead@CSrmFileSafe@@QEAAXXZ`
- size: `1135`
- prototype: `void __fastcall(CSrmFileSafe *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18000fd74`

## callees

- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073d04`
- `0x180074048`
- `0x180074a04`
- `0x18007945c`
- `0x180079724`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18007987c`
- `KERNEL32!CreateFileW` at `0x18007987c`
- `KERNEL32!CloseHandle` at `0x180079892`
- `KERNEL32!CloseHandle` at `0x180079892`
- `KERNEL32!GetLastError` at `0x1800798a9`
- `KERNEL32!GetLastError` at `0x1800798a9`

## string_xrefs

- `0x180079a27`: `Access denied to SRM store file %s`
- `0x180079b76`: `Volume not ready for SRM store file %s`
- `0x180079764`: `CSrmFileSafe::SafeOpenForRead`
- `0x180079905`: `CreateFileW for SRM store file %s failed with %lu`
- `0x180079a84`: `CreateFileW(%s, GENERIC_READ)`
- `0x180079acb`: `file already opened read=%d write=%d`
- `0x180079830`: `Opening file '%s' for read ...`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSrmFileSafe::SafeOpenForRead(CSrmFileSafe *this)
{
  DWORD v2; // edi
  const WCHAR **v3; // rdi
  char *v4; // rsi
  const WCHAR *v5; // rcx
  HANDLE FileW; // rsi
  void *v7; // rcx
  unsigned __int64 LastError; // rbx
  const WCHAR *v9; // rsi
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  struct CSrmDebugInfo *v12; // r9
  CSrmDebugInfo *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rax
  int v18; // ebx
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  struct CSrmDebugInfo *v21; // r9
  CSrmDebugInfo *v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v29; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  int v33; // [rsp+68h] [rbp-98h]
  _BYTE v34[96]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+D0h] [rbp-30h]
  _QWORD v36[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F4h] [rbp-Ch]
  int v39; // [rsp+F8h] [rbp-8h]
  _BYTE v40[96]; // [rsp+100h] [rbp+0h] BYREF
  int v41; // [rsp+160h] [rbp+60h]
  _BYTE v42[152]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v43[22]; // [rsp+200h] [rbp+100h] BYREF

  v36[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v36[1] = L"CSrmFileSafe::SafeOpenForRead";
  v36[2] = L"FILESF_C";
  v37 = 243;
  v38 = 17;
  v39 = 255;
  v41 = 0x1000000;
  memset_0(v40, 0, sizeof(v40));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v43, (const struct CSrmDebugInfo *)v36, 0);
  v2 = *((unsigned __int8 *)this + 200);
  if ( *((_WORD *)this + 100) )
  {
    v18 = *((unsigned __int8 *)this + 201);
    v19 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v42,
            (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            (__int64)L"FILESF_C",
            (__int64)L"CSrmFileSafe::SafeOpenForRead",
            249,
            17);
    LODWORD(dwFlagsAndAttributes) = v18;
    dwCreationDispositiona[0] = v2;
    CSrmFunctionTracer::TranslateGenericError(
      v43,
      v19,
      2147767062LL,
      L"file already opened read=%d write=%d",
      *(_QWORD *)dwCreationDispositiona,
      dwFlagsAndAttributes);
  }
  CSrmFileSafe::RecoverSafeFile(this);
  v3 = (const WCHAR **)((char *)this + 80);
  if ( *((_QWORD *)this + 13) < 8u )
    v4 = (char *)this + 80;
  else
    v4 = (char *)*v3;
  v28 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v29 = L"CSrmFileSafe::SafeOpenForRead";
  v30 = L"FILESF_C";
  v31 = 255;
  v32 = 17;
  v33 = 255;
  v35 = 0x1000000;
  memset_0(v34, 0, sizeof(v34));
  CSrmFunctionTracer::Trace(v43, &v28, L"Opening file '%s' for read ...", v4);
  if ( *((_QWORD *)this + 13) < 8u )
    v5 = (const WCHAR *)((char *)this + 80);
  else
    v5 = *v3;
  FileW = CreateFileW(v5, 0x80000000, 1u, 0, 3u, 0x2000080u, 0);
  v7 = (void *)*((_QWORD *)this + 27);
  if ( v7 != (void *)-1LL )
    CloseHandle(v7);
  *((_QWORD *)this + 27) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( (unsigned __int64)v3[3] < 8 )
      v9 = (const WCHAR *)v3;
    else
      v9 = *v3;
    v28 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v29 = L"CSrmFileSafe::SafeOpenForRead";
    v30 = L"FILESF_C";
    v31 = 269;
    v32 = 17;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(v34, 0, sizeof(v34));
    dwCreationDisposition[0] = LastError;
    CSrmFunctionTracer::Trace(
      v43,
      &v28,
      L"CreateFileW for SRM store file %s failed with %lu",
      v9,
      *(_QWORD *)dwCreationDisposition);
    if ( (_DWORD)LastError != 5 )
    {
      if ( (unsigned int)LastError <= 0x37 && (v10 = 0x80000000280000LL, _bittest64(&v10, LastError))
        || (_DWORD)LastError == 1167 )
      {
        CSrmDebugInfo::CSrmDebugInfo(
          (__int64)v42,
          (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
          (__int64)L"FILESF_C",
          (__int64)L"CSrmFileSafe::SafeOpenForRead",
          288,
          17);
        v20 = (unsigned __int16 *)std::wstring::c_str(v3);
        v22 = CSrmDebugInfo::operator<<(v21, (CSrmDebugInfo *)&v28, v20);
        CSrmFunctionTracer::LogError((__int64)v43, 0x80042039, (__int64)v22, 2u);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v42);
        v23 = std::wstring::c_str(v3);
        v24 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v42,
                (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                (__int64)L"FILESF_C",
                (__int64)L"CSrmFileSafe::SafeOpenForRead",
                291,
                17);
        CSrmFunctionTracer::Throw(v43, v24, 2147767142LL, L"Volume not ready for SRM store file %s", v23);
      }
      v16 = std::wstring::c_str(v3);
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
      v17 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v28,
              (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              (__int64)L"FILESF_C",
              (__int64)L"CSrmFileSafe::SafeOpenForRead",
              296,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v43,
        v17,
        (unsigned int)LastError,
        L"CreateFileW(%s, GENERIC_READ)",
        v16);
    }
    CSrmDebugInfo::CSrmDebugInfo(
      (__int64)&v28,
      (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      (__int64)L"FILESF_C",
      (__int64)L"CSrmFileSafe::SafeOpenForRead",
      275,
      17);
    v11 = (unsigned __int16 *)std::wstring::c_str(v3);
    v13 = CSrmDebugInfo::operator<<(v12, (CSrmDebugInfo *)v42, v11);
    CSrmFunctionTracer::LogError((__int64)v43, 0x80042024, (__int64)v13, 2u);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v28);
    v14 = std::wstring::c_str(v3);
    v15 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v42,
            (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            (__int64)L"FILESF_C",
            (__int64)L"CSrmFileSafe::SafeOpenForRead",
            278,
            17);
    CSrmFunctionTracer::Throw(v43, v15, 2147942405LL, L"Access denied to SRM store file %s", v14);
  }
  *((_BYTE *)this + 200) = 1;
  v43[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v43);
}

```

## disassembly

```asm
0x180079724  mov     [rsp-8+arg_8], rbx
0x180079729  mov     [rsp-8+arg_10], rsi
0x18007972e  push    rbp
0x18007972f  push    rdi
0x180079730  push    r12
0x180079732  push    r13
0x180079734  push    r15
0x180079736  lea     rbp, [rsp-1C0h]
0x18007973e  sub     rsp, 2C0h
0x180079745  mov     rax, cs:__security_cookie
0x18007974c  xor     rax, rsp
0x18007974f  mov     [rbp+1E0h+var_30], rax
0x180079756  mov     rbx, rcx
0x180079759  lea     r15, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180079760  mov     [rbp+1E0h+var_208], r15
0x180079764  lea     r12, aCsrmfilesafeSa_1; "CSrmFileSafe::SafeOpenForRead"
0x18007976b  mov     [rbp+1E0h+var_200], r12
0x18007976f  lea     r13, aFilesfC; "FILESF_C"
0x180079776  mov     [rbp+1E0h+var_1F8], r13
0x18007977a  mov     [rbp+1E0h+var_1F0], 0F3h
0x180079781  mov     esi, 11h
0x180079786  mov     [rbp+1E0h+var_1EC], esi
0x180079789  mov     [rbp+1E0h+var_1E8], 0FFh
0x180079790  mov     [rbp+1E0h+var_180], 1000000h
0x180079797  xor     edx, edx; Val
0x180079799  lea     r8d, [rsi+4Fh]; Size
0x18007979d  lea     rcx, [rbp+1E0h+var_1E0]; void *
0x1800797a1  call    memset_0
0x1800797a6  xor     r8d, r8d
0x1800797a9  lea     rdx, [rbp+1E0h+var_208]
0x1800797ad  lea     rcx, [rbp+1E0h+var_E0]
0x1800797b4  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800797b9  nop
0x1800797ba  movzx   edi, byte ptr [rbx+0C8h]
0x1800797c1  test    dil, dil
0x1800797c4  jnz     loc_180079A9E
0x1800797ca  cmp     [rbx+0C9h], dil
0x1800797d1  jnz     loc_180079A9E
0x1800797d7  mov     rcx, rbx; this
0x1800797da  call    ?RecoverSafeFile@CSrmFileSafe@@QEAAXXZ; CSrmFileSafe::RecoverSafeFile(void)
0x1800797df  lea     rdi, [rbx+50h]
0x1800797e3  cmp     qword ptr [rdi+18h], 8
0x1800797e8  jb      short loc_1800797EF
0x1800797ea  mov     rsi, [rdi]
0x1800797ed  jmp     short loc_1800797F2
0x1800797ef  mov     rsi, rdi
0x1800797f2  mov     [rsp+2E0h+var_298], r15
0x1800797f7  mov     [rsp+2E0h+var_290], r12
0x1800797fc  mov     [rsp+2E0h+var_288], r13
0x180079801  mov     eax, 0FFh
0x180079806  mov     [rsp+2E0h+var_280], eax
0x18007980a  mov     [rsp+2E0h+var_27C], 11h
0x180079812  mov     [rsp+2E0h+var_278], eax
0x180079816  mov     [rbp+1E0h+var_210], 1000000h
0x18007981d  xor     edx, edx; Val
0x18007981f  lea     r8d, [rdx+60h]; Size
0x180079823  lea     rcx, [rsp+2E0h+var_270]; void *
0x180079828  call    memset_0
0x18007982d  mov     r9, rsi
0x180079830  lea     r8, aOpeningFileSFo; "Opening file '%s' for read ..."
0x180079837  lea     rdx, [rsp+2E0h+var_298]
0x18007983c  lea     rcx, [rbp+1E0h+var_E0]
0x180079843  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180079848  cmp     qword ptr [rdi+18h], 8
0x18007984d  jb      short loc_180079854
0x18007984f  mov     rcx, [rdi]
0x180079852  jmp     short loc_180079857
0x180079854  mov     rcx, rdi; lpFileName
0x180079857  mov     [rsp+2E0h+hTemplateFile], 0; hTemplateFile
0x180079860  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180079868  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180079870  xor     r9d, r9d; lpSecurityAttributes
0x180079873  mov     edx, 80000000h; dwDesiredAccess
0x180079878  lea     r8d, [r9+1]; dwShareMode
0x18007987c  call    cs:__imp_CreateFileW
0x180079882  mov     rsi, rax
0x180079885  mov     rcx, [rbx+0D8h]; hObject
0x18007988c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180079890  jz      short loc_180079898
0x180079892  call    cs:__imp_CloseHandle
0x180079898  mov     [rbx+0D8h], rsi
0x18007989f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800798a3  jnz     loc_18007994C
0x1800798a9  call    cs:__imp_GetLastError
0x1800798af  mov     ebx, eax
0x1800798b1  cmp     qword ptr [rdi+18h], 8
0x1800798b6  jb      short loc_1800798BD
0x1800798b8  mov     rsi, [rdi]
0x1800798bb  jmp     short loc_1800798C0
0x1800798bd  mov     rsi, rdi
0x1800798c0  mov     [rsp+2E0h+var_298], r15
0x1800798c5  mov     [rsp+2E0h+var_290], r12
0x1800798ca  mov     [rsp+2E0h+var_288], r13
0x1800798cf  mov     [rsp+2E0h+var_280], 10Dh
0x1800798d7  mov     [rsp+2E0h+var_27C], 11h
0x1800798df  mov     [rsp+2E0h+var_278], 0FFh
0x1800798e7  mov     [rbp+1E0h+var_210], 1000000h
0x1800798ee  xor     edx, edx; Val
0x1800798f0  lea     r8d, [rdx+60h]; Size
0x1800798f4  lea     rcx, [rsp+2E0h+var_270]; void *
0x1800798f9  call    memset_0
0x1800798fe  mov     [rsp+2E0h+dwCreationDisposition], ebx
0x180079902  mov     r9, rsi
0x180079905  lea     r8, aCreatefilewFor; "CreateFileW for SRM store file %s faile"...
0x18007990c  lea     rdx, [rsp+2E0h+var_298]
0x180079911  lea     rcx, [rbp+1E0h+var_E0]
0x180079918  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007991d  cmp     ebx, 5
0x180079920  jz      short loc_180079998
0x180079922  cmp     ebx, 37h ; '7'
0x180079925  ja      short loc_18007993B
0x180079927  mov     rcx, 80000000280000h
0x180079931  bt      rcx, rbx
0x180079935  jb      loc_180079AE8
0x18007993b  cmp     ebx, 48Fh
0x180079941  jnz     loc_180079A44
0x180079947  jmp     loc_180079AE8
0x18007994c  mov     byte ptr [rbx+0C8h], 1
0x180079953  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007995a  mov     [rbp+1E0h+var_E0], rax
0x180079961  lea     rcx, [rbp+1E0h+var_E0]; this
0x180079968  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007996d  mov     rcx, [rbp+1E0h+var_30]
0x180079974  xor     rcx, rsp; StackCookie
0x180079977  call    __security_check_cookie
0x18007997c  lea     r11, [rsp+2E0h+var_20]
0x180079984  mov     rbx, [r11+38h]
0x180079988  mov     rsi, [r11+40h]
0x18007998c  mov     rsp, r11
0x18007998f  pop     r15
0x180079991  pop     r13
0x180079993  pop     r12
0x180079995  pop     rdi
0x180079996  pop     rbp
0x180079997  retn
0x180079998  mov     esi, 11h
0x18007999d  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], esi
0x1800799a1  mov     [rsp+2E0h+dwCreationDisposition], 113h
0x1800799a9  mov     r9, r12
0x1800799ac  mov     r8, r13
0x1800799af  mov     rdx, r15
0x1800799b2  lea     rcx, [rsp+2E0h+var_298]
0x1800799b7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800799bc  mov     r9, rax
0x1800799bf  mov     rcx, rdi
0x1800799c2  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800799c7  mov     r8, rax; unsigned __int16 *
0x1800799ca  lea     rdx, [rbp+1E0h+var_178]; this
0x1800799ce  mov     rcx, r9; struct CSrmDebugInfo *
0x1800799d1  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x1800799d6  lea     r9d, [rsi-0Fh]
0x1800799da  mov     r8, rax
0x1800799dd  mov     edx, 80042024h
0x1800799e2  lea     rcx, [rbp+1E0h+var_E0]
0x1800799e9  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x1800799ee  nop
0x1800799ef  lea     rcx, [rsp+2E0h+var_298]; this
0x1800799f4  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x1800799f9  mov     rcx, rdi
0x1800799fc  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079a01  mov     rbx, rax
0x180079a04  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], esi
0x180079a08  mov     [rsp+2E0h+dwCreationDisposition], 116h
0x180079a10  mov     r9, r12
0x180079a13  mov     r8, r13
0x180079a16  mov     rdx, r15
0x180079a19  lea     rcx, [rbp+1E0h+var_178]
0x180079a1d  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180079a22  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rbx
0x180079a27  lea     r9, aAccessDeniedTo; "Access denied to SRM store file %s"
0x180079a2e  mov     r8d, 80070005h
0x180079a34  mov     rdx, rax
0x180079a37  lea     rcx, [rbp+1E0h+var_E0]
0x180079a3e  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180079a44  mov     rcx, rdi
0x180079a47  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079a4c  mov     rdi, rax
0x180079a4f  test    ebx, ebx
0x180079a51  jle     short loc_180079A5C
0x180079a53  movzx   ebx, bx
0x180079a56  or      ebx, 80070000h
0x180079a5c  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], 11h
0x180079a64  mov     [rsp+2E0h+dwCreationDisposition], 128h
0x180079a6c  mov     r9, r12
0x180079a6f  mov     r8, r13
0x180079a72  mov     rdx, r15
0x180079a75  lea     rcx, [rsp+2E0h+var_298]
0x180079a7a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180079a7f  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rdi
0x180079a84  lea     r9, aCreatefilewSGe_0; "CreateFileW(%s, GENERIC_READ)"
0x180079a8b  mov     r8d, ebx
0x180079a8e  mov     rdx, rax
0x180079a91  lea     rcx, [rbp+1E0h+var_E0]
0x180079a98  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180079a9e  movzx   ebx, byte ptr [rbx+0C9h]
0x180079aa5  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], esi
0x180079aa9  mov     [rsp+2E0h+dwCreationDisposition], 0F9h
0x180079ab1  mov     r9, r12
0x180079ab4  mov     r8, r13
0x180079ab7  mov     rdx, r15
0x180079aba  lea     rcx, [rbp+1E0h+var_178]
0x180079abe  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180079ac3  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], ebx
0x180079ac7  mov     [rsp+2E0h+dwCreationDisposition], edi
0x180079acb  lea     r9, aFileAlreadyOpe_0; "file already opened read=%d write=%d"
0x180079ad2  mov     r8d, 80045316h
0x180079ad8  mov     rdx, rax
0x180079adb  lea     rcx, [rbp+1E0h+var_E0]
0x180079ae2  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180079ae8  mov     esi, 11h
0x180079aed  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], esi
0x180079af1  mov     [rsp+2E0h+dwCreationDisposition], 120h
0x180079af9  mov     r9, r12
0x180079afc  mov     r8, r13
0x180079aff  mov     rdx, r15
0x180079b02  lea     rcx, [rbp+1E0h+var_178]
0x180079b06  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180079b0b  mov     r9, rax
0x180079b0e  mov     rcx, rdi
0x180079b11  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079b16  mov     r8, rax; unsigned __int16 *
0x180079b19  lea     rdx, [rsp+2E0h+var_298]; this
0x180079b1e  mov     rcx, r9; struct CSrmDebugInfo *
0x180079b21  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180079b26  lea     r9d, [rsi-0Fh]
0x180079b2a  mov     r8, rax
0x180079b2d  mov     edx, 80042039h
0x180079b32  lea     rcx, [rbp+1E0h+var_E0]
0x180079b39  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180079b3e  nop
0x180079b3f  lea     rcx, [rbp+1E0h+var_178]; this
0x180079b43  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180079b48  mov     rcx, rdi
0x180079b4b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079b50  mov     rbx, rax
0x180079b53  mov     dword ptr [rsp+2E0h+dwFlagsAndAttributes], esi
0x180079b57  mov     [rsp+2E0h+dwCreationDisposition], 123h
0x180079b5f  mov     r9, r12
0x180079b62  mov     r8, r13
0x180079b65  mov     rdx, r15
0x180079b68  lea     rcx, [rbp+1E0h+var_178]
0x180079b6c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180079b71  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rbx
0x180079b76  lea     r9, aVolumeNotReady; "Volume not ready for SRM store file %s"
0x180079b7d  mov     r8d, 80045366h
0x180079b83  mov     rdx, rax
0x180079b86  lea     rcx, [rbp+1E0h+var_E0]
0x180079b8d  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
