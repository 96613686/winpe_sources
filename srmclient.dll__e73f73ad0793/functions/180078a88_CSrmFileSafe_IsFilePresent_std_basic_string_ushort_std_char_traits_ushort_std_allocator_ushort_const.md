# CSrmFileSafe::IsFilePresent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180078a88`
- end: `0x180078f56`
- name: `?IsFilePresent@CSrmFileSafe@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1230`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800101e8`
- `0x18007945c`
- `0x18007a3b8`

## callees

- `0x18000ab88`
- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073d04`
- `0x180074048`
- `0x18007424c`
- `0x180074a04`
- `0x180078a88`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180078bac`
- `KERNEL32!CreateFileW` at `0x180078bac`
- `KERNEL32!GetLastError` at `0x180078bcd`
- `KERNEL32!GetLastError` at `0x180078bcd`
- `KERNEL32!GetFileType` at `0x180078cce`
- `KERNEL32!GetFileType` at `0x180078cce`

## string_xrefs

- `0x180078de4`: `CreateFileW(%s, n--access)`
- `0x180078f39`: `Access denied to SRM store file %s`
- `0x180078e8d`: `Volume not ready for SRM store file %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CSrmFileSafe::IsFilePresent(LPCWSTR lpFileName)
{
  LPCWSTR v2; // rdi
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  signed int LastError; // edi
  DWORD FileType; // edi
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned __int16 *v12; // rax
  struct CSrmDebugInfo *v13; // r10
  CSrmDebugInfo *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int16 *v17; // rax
  struct CSrmDebugInfo *v18; // r9
  CSrmDebugInfo *v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  _QWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v24; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v25; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  int v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[96]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+E0h] [rbp-20h]
  _QWORD v32[3]; // [rsp+E8h] [rbp-18h] BYREF
  int v33; // [rsp+100h] [rbp+0h]
  int v34; // [rsp+104h] [rbp+4h]
  int v35; // [rsp+108h] [rbp+8h]
  _BYTE v36[96]; // [rsp+110h] [rbp+10h] BYREF
  int v37; // [rsp+170h] [rbp+70h]
  _QWORD v38[22]; // [rsp+180h] [rbp+80h] BYREF

  v32[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v32[1] = L"CSrmFileSafe::IsFilePresent";
  v32[2] = L"FILESF_C";
  v33 = 123;
  v34 = 17;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v38, (const struct CSrmDebugInfo *)v32, 0);
  if ( *((_QWORD *)lpFileName + 3) < 8u )
    v2 = lpFileName;
  else
    v2 = *(LPCWSTR *)lpFileName;
  v24 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v25 = L"CSrmFileSafe::IsFilePresent";
  v26 = L"FILESF_C";
  v27 = 125;
  v28 = 17;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  CSrmFunctionTracer::Trace(v38, &v24, L"- Verifying if the file '%s' is valid", v2);
  if ( *((_QWORD *)lpFileName + 3) < 8u )
    v3 = lpFileName;
  else
    v3 = *(const WCHAR **)lpFileName;
  FileW = CreateFileW(v3, 0, 3u, 0, 3u, 0x80u, 0);
  v23[0] = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v23[1] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError != 2 && LastError != 3 )
    {
      if ( LastError != 5 )
      {
        if ( LastError == 19 || LastError == 21 || LastError == 55 || LastError == 1167 )
        {
          CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v32,
            (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            (__int64)L"FILESF_C",
            (__int64)L"CSrmFileSafe::IsFilePresent",
            164,
            17);
          v12 = (unsigned __int16 *)std::wstring::c_str(lpFileName);
          v14 = CSrmDebugInfo::operator<<(v13, (CSrmDebugInfo *)&v24, v12);
          CSrmFunctionTracer::LogError((__int64)v38, 0x80042039, (__int64)v14, 2u);
          CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v32);
          v15 = std::wstring::c_str(lpFileName);
          v16 = CSrmDebugInfo::CSrmDebugInfo(
                  (__int64)&v24,
                  (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                  (__int64)L"FILESF_C",
                  (__int64)L"CSrmFileSafe::IsFilePresent",
                  167,
                  17);
          CSrmFunctionTracer::Throw(v38, v16, 2147767142LL, L"Volume not ready for SRM store file %s", v15);
        }
        v10 = std::wstring::c_str(lpFileName);
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)&v24,
                (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                (__int64)L"FILESF_C",
                (__int64)L"CSrmFileSafe::IsFilePresent",
                172,
                17);
        CSrmFunctionTracer::TranslateGenericError(v38, v11, (unsigned int)LastError, L"CreateFileW(%s, n--access)", v10);
      }
      CSrmDebugInfo::CSrmDebugInfo(
        (__int64)v32,
        (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
        (__int64)L"FILESF_C",
        (__int64)L"CSrmFileSafe::IsFilePresent",
        152,
        17);
      v17 = (unsigned __int16 *)std::wstring::c_str(lpFileName);
      v19 = CSrmDebugInfo::operator<<(v18, (CSrmDebugInfo *)&v24, v17);
      CSrmFunctionTracer::LogError((__int64)v38, 0x80042024, (__int64)v19, 2u);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v32);
      v20 = std::wstring::c_str(lpFileName);
      v21 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v24,
              (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              (__int64)L"FILESF_C",
              (__int64)L"CSrmFileSafe::IsFilePresent",
              155,
              17);
      CSrmFunctionTracer::Throw(v38, v21, 2147942405LL, L"Access denied to SRM store file %s", v20);
    }
    if ( *((_QWORD *)lpFileName + 3) >= 8u )
      lpFileName = *(LPCWSTR *)lpFileName;
    v24 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v25 = L"CSrmFileSafe::IsFilePresent";
    v26 = L"FILESF_C";
    v27 = 145;
    v28 = 17;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CSrmFunctionTracer::Trace(v38, &v24, L"File '%s' not found ... ", lpFileName);
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v38,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v23);
    v38[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v38);
    return 0;
  }
  else
  {
    FileType = GetFileType(FileW);
    if ( FileType != 1 )
    {
      v8 = std::wstring::c_str(lpFileName);
      v9 = CSrmDebugInfo::CSrmDebugInfo(
             (__int64)&v24,
             (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
             (__int64)L"FILESF_C",
             (__int64)L"CSrmFileSafe::IsFilePresent",
             182,
             17);
      LODWORD(dwFlagsAndAttributes) = FileType;
      CSrmFunctionTracer::TranslateGenericError(
        v38,
        v9,
        2147767062LL,
        L"%s type is %u - not a file !!",
        v8,
        dwFlagsAndAttributes);
    }
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v38,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v23);
    v38[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v38);
    return 1;
  }
}

```

## disassembly

```asm
0x180078a88  push    rbp
0x180078a8a  push    rbx
0x180078a8b  push    rdi
0x180078a8c  push    r12
0x180078a8e  push    r13
0x180078a90  push    r15
0x180078a92  lea     rbp, [rsp-148h]
0x180078a9a  sub     rsp, 248h
0x180078aa1  mov     rax, cs:__security_cookie
0x180078aa8  xor     rax, rsp
0x180078aab  mov     [rbp+170h+var_40], rax
0x180078ab2  mov     rbx, rcx
0x180078ab5  lea     r15, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180078abc  mov     [rbp+170h+var_188], r15
0x180078ac0  lea     r12, aCsrmfilesafeIs; "CSrmFileSafe::IsFilePresent"
0x180078ac7  mov     [rbp+170h+var_180], r12
0x180078acb  lea     r13, aFilesfC; "FILESF_C"
0x180078ad2  mov     [rbp+170h+var_178], r13
0x180078ad6  mov     [rbp+170h+var_170], 7Bh ; '{'
0x180078add  mov     [rbp+170h+var_16C], 11h
0x180078ae4  mov     [rbp+170h+var_168], 0FFh
0x180078aeb  mov     [rbp+170h+var_100], 1000000h
0x180078af2  xor     edx, edx; Val
0x180078af4  lea     r8d, [rdx+60h]; Size
0x180078af8  lea     rcx, [rbp+170h+var_160]; void *
0x180078afc  call    memset_0
0x180078b01  xor     r8d, r8d
0x180078b04  lea     rdx, [rbp+170h+var_188]
0x180078b08  lea     rcx, [rbp+170h+var_F0]
0x180078b0f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180078b14  nop
0x180078b15  cmp     qword ptr [rbx+18h], 8
0x180078b1a  jb      short loc_180078B21
0x180078b1c  mov     rdi, [rbx]
0x180078b1f  jmp     short loc_180078B24
0x180078b21  mov     rdi, rbx
0x180078b24  mov     [rsp+270h+var_218], r15
0x180078b29  mov     [rsp+270h+var_210], r12
0x180078b2e  mov     [rsp+270h+var_208], r13
0x180078b33  mov     [rsp+270h+var_200], 7Dh ; '}'
0x180078b3b  mov     [rsp+270h+var_1FC], 11h
0x180078b43  mov     [rsp+270h+var_1F8], 0FFh
0x180078b4b  mov     [rbp+170h+var_190], 1000000h
0x180078b52  xor     edx, edx; Val
0x180078b54  lea     r8d, [rdx+60h]; Size
0x180078b58  lea     rcx, [rbp+170h+var_1F0]; void *
0x180078b5c  call    memset_0
0x180078b61  mov     r9, rdi
0x180078b64  lea     r8, aVerifyingIfThe; "- Verifying if the file '%s' is valid"
0x180078b6b  lea     rdx, [rsp+270h+var_218]
0x180078b70  lea     rcx, [rbp+170h+var_F0]
0x180078b77  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180078b7c  cmp     qword ptr [rbx+18h], 8
0x180078b81  jb      short loc_180078B88
0x180078b83  mov     rcx, [rbx]
0x180078b86  jmp     short loc_180078B8B
0x180078b88  mov     rcx, rbx; lpFileName
0x180078b8b  mov     [rsp+270h+hTemplateFile], 0; hTemplateFile
0x180078b94  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180078b9c  mov     r8d, 3; dwShareMode
0x180078ba2  mov     [rsp+270h+dwCreationDisposition], r8d; dwCreationDisposition
0x180078ba7  xor     r9d, r9d; lpSecurityAttributes
0x180078baa  xor     edx, edx; dwDesiredAccess
0x180078bac  call    cs:__imp_CreateFileW
0x180078bb2  lea     rcx, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180078bb9  mov     [rsp+270h+var_228], rcx
0x180078bbe  mov     [rsp+270h+var_220], rax
0x180078bc3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180078bc7  jnz     loc_180078CCB
0x180078bcd  call    cs:__imp_GetLastError
0x180078bd3  mov     edi, eax
0x180078bd5  sub     eax, 2
0x180078bd8  jz      short loc_180078C13
0x180078bda  sub     eax, 1
0x180078bdd  jz      short loc_180078C13
0x180078bdf  sub     eax, 2
0x180078be2  jz      loc_180078EAA
0x180078be8  sub     eax, 0Eh
0x180078beb  jz      loc_180078DFE
0x180078bf1  sub     eax, 2
0x180078bf4  jz      loc_180078DFE
0x180078bfa  sub     eax, 22h ; '"'
0x180078bfd  jz      loc_180078DFE
0x180078c03  cmp     eax, 458h
0x180078c08  jnz     loc_180078DA4
0x180078c0e  jmp     loc_180078DFE
0x180078c13  cmp     qword ptr [rbx+18h], 8
0x180078c18  jb      short loc_180078C1D
0x180078c1a  mov     rbx, [rbx]
0x180078c1d  mov     [rsp+270h+var_218], r15
0x180078c22  mov     [rsp+270h+var_210], r12
0x180078c27  mov     [rsp+270h+var_208], r13
0x180078c2c  mov     [rsp+270h+var_200], 91h
0x180078c34  mov     [rsp+270h+var_1FC], 11h
0x180078c3c  mov     [rsp+270h+var_1F8], 0FFh
0x180078c44  mov     [rbp+170h+var_190], 1000000h
0x180078c4b  xor     edx, edx; Val
0x180078c4d  lea     r8d, [rdx+60h]; Size
0x180078c51  lea     rcx, [rbp+170h+var_1F0]; void *
0x180078c55  call    memset_0
0x180078c5a  mov     r9, rbx
0x180078c5d  lea     r8, aFileSNotFound; "File '%s' not found ... "
0x180078c64  lea     rdx, [rsp+270h+var_218]
0x180078c69  lea     rcx, [rbp+170h+var_F0]
0x180078c70  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180078c75  lea     rax, aFalse; "FALSE"
0x180078c7c  mov     qword ptr [rsp+270h+dwCreationDisposition], rax
0x180078c81  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180078c88  mov     r8d, 0AAh; unsigned int
0x180078c8e  lea     rdx, aReturn; "RETURN"
0x180078c95  lea     rcx, [rbp+170h+var_F0]; this
0x180078c9c  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180078ca1  nop
0x180078ca2  lea     rcx, [rsp+270h+var_228]
0x180078ca7  call    ??1?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x180078cac  nop
0x180078cad  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180078cb4  mov     [rbp+170h+var_F0], rax
0x180078cbb  lea     rcx, [rbp+170h+var_F0]; this
0x180078cc2  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180078cc7  xor     al, al
0x180078cc9  jmp     short loc_180078D30
0x180078ccb  mov     rcx, rax; hFile
0x180078cce  call    cs:__imp_GetFileType
0x180078cd4  mov     edi, eax
0x180078cd6  cmp     eax, 1
0x180078cd9  jnz     short loc_180078D50
0x180078cdb  lea     rax, aTrue_0; "TRUE"
0x180078ce2  mov     qword ptr [rsp+270h+dwCreationDisposition], rax
0x180078ce7  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180078cee  mov     r8d, 0AAh; unsigned int
0x180078cf4  lea     rdx, aReturn; "RETURN"
0x180078cfb  lea     rcx, [rbp+170h+var_F0]; this
0x180078d02  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180078d07  nop
0x180078d08  lea     rcx, [rsp+270h+var_228]
0x180078d0d  call    ??1?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x180078d12  nop
0x180078d13  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180078d1a  mov     [rbp+170h+var_F0], rax
0x180078d21  lea     rcx, [rbp+170h+var_F0]; this
0x180078d28  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180078d2d  mov     al, dil
0x180078d30  mov     rcx, [rbp+170h+var_40]
0x180078d37  xor     rcx, rsp; StackCookie
0x180078d3a  call    __security_check_cookie
0x180078d3f  add     rsp, 248h
0x180078d46  pop     r15
0x180078d48  pop     r13
0x180078d4a  pop     r12
0x180078d4c  pop     rdi
0x180078d4d  pop     rbx
0x180078d4e  pop     rbp
0x180078d4f  retn
0x180078d50  mov     rcx, rbx
0x180078d53  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180078d58  mov     rbx, rax
0x180078d5b  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], 11h
0x180078d63  mov     [rsp+270h+dwCreationDisposition], 0B6h
0x180078d6b  mov     r9, r12
0x180078d6e  mov     r8, r13
0x180078d71  mov     rdx, r15
0x180078d74  lea     rcx, [rsp+270h+var_218]
0x180078d79  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078d7e  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], edi
0x180078d82  mov     qword ptr [rsp+270h+dwCreationDisposition], rbx
0x180078d87  lea     r9, aSTypeIsUNotAFi; "%s type is %u - not a file !!"
0x180078d8e  mov     r8d, 80045316h
0x180078d94  mov     rdx, rax
0x180078d97  lea     rcx, [rbp+170h+var_F0]
0x180078d9e  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180078da4  mov     rcx, rbx
0x180078da7  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180078dac  mov     rbx, rax
0x180078daf  test    edi, edi
0x180078db1  jle     short loc_180078DBC
0x180078db3  movzx   edi, di
0x180078db6  or      edi, 80070000h
0x180078dbc  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], 11h
0x180078dc4  mov     [rsp+270h+dwCreationDisposition], 0ACh
0x180078dcc  mov     r9, r12
0x180078dcf  mov     r8, r13
0x180078dd2  mov     rdx, r15
0x180078dd5  lea     rcx, [rsp+270h+var_218]
0x180078dda  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078ddf  mov     qword ptr [rsp+270h+dwCreationDisposition], rbx
0x180078de4  lea     r9, aCreatefilewSNA; "CreateFileW(%s, n--access)"
0x180078deb  mov     r8d, edi
0x180078dee  mov     rdx, rax
0x180078df1  lea     rcx, [rbp+170h+var_F0]
0x180078df8  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180078dfe  mov     edi, 11h
0x180078e03  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], edi
0x180078e07  mov     [rsp+270h+dwCreationDisposition], 0A4h
0x180078e0f  mov     r9, r12
0x180078e12  mov     r8, r13
0x180078e15  mov     rdx, r15
0x180078e18  lea     rcx, [rbp+170h+var_188]
0x180078e1c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078e21  mov     r10, rax
0x180078e24  mov     rcx, rbx
0x180078e27  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180078e2c  mov     r8, rax; unsigned __int16 *
0x180078e2f  lea     rdx, [rsp+270h+var_218]; this
0x180078e34  mov     rcx, r10; struct CSrmDebugInfo *
0x180078e37  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180078e3c  lea     r9d, [rdi-0Fh]
0x180078e40  mov     r8, rax
0x180078e43  mov     edx, 80042039h
0x180078e48  lea     rcx, [rbp+170h+var_F0]
0x180078e4f  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180078e54  nop
0x180078e55  lea     rcx, [rbp+170h+var_188]; this
0x180078e59  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180078e5e  mov     rcx, rbx
0x180078e61  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180078e66  mov     rbx, rax
0x180078e69  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], edi
0x180078e6d  mov     [rsp+270h+dwCreationDisposition], 0A7h
0x180078e75  mov     r9, r12
0x180078e78  mov     r8, r13
0x180078e7b  mov     rdx, r15
0x180078e7e  lea     rcx, [rsp+270h+var_218]
0x180078e83  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078e88  mov     qword ptr [rsp+270h+dwCreationDisposition], rbx
0x180078e8d  lea     r9, aVolumeNotReady; "Volume not ready for SRM store file %s"
0x180078e94  mov     r8d, 80045366h
0x180078e9a  mov     rdx, rax
0x180078e9d  lea     rcx, [rbp+170h+var_F0]
0x180078ea4  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180078eaa  mov     edi, 11h
0x180078eaf  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], edi
0x180078eb3  mov     [rsp+270h+dwCreationDisposition], 98h
0x180078ebb  mov     r9, r12
0x180078ebe  mov     r8, r13
0x180078ec1  mov     rdx, r15
0x180078ec4  lea     rcx, [rbp+170h+var_188]
0x180078ec8  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078ecd  mov     r9, rax
0x180078ed0  mov     rcx, rbx
0x180078ed3  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180078ed8  mov     r8, rax; unsigned __int16 *
0x180078edb  lea     rdx, [rsp+270h+var_218]; this
0x180078ee0  mov     rcx, r9; struct CSrmDebugInfo *
0x180078ee3  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180078ee8  lea     r9d, [rdi-0Fh]
0x180078eec  mov     r8, rax
0x180078eef  mov     edx, 80042024h
0x180078ef4  lea     rcx, [rbp+170h+var_F0]
0x180078efb  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180078f00  nop
0x180078f01  lea     rcx, [rbp+170h+var_188]; this
0x180078f05  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180078f0a  mov     rcx, rbx
0x180078f0d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180078f12  mov     rbx, rax
0x180078f15  mov     dword ptr [rsp+270h+dwFlagsAndAttributes], edi
0x180078f19  mov     [rsp+270h+dwCreationDisposition], 9Bh
0x180078f21  mov     r9, r12
0x180078f24  mov     r8, r13
0x180078f27  mov     rdx, r15
0x180078f2a  lea     rcx, [rsp+270h+var_218]
0x180078f2f  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078f34  mov     qword ptr [rsp+270h+dwCreationDisposition], rbx
0x180078f39  lea     r9, aAccessDeniedTo; "Access denied to SRM store file %s"
0x180078f40  mov     r8d, 80070005h
0x180078f46  mov     rdx, rax
0x180078f49  lea     rcx, [rbp+170h+var_F0]
0x180078f50  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
