# CSrmFileSafe::CreateDirectoryInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007791c`
- end: `0x180077c4c`
- name: `?CreateDirectoryInternal@CSrmFileSafe@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `816`
- prototype: `char __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18000d560`
- `0x180077c54`

## callees

- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180074048`
- `0x18007424c`
- `0x180075034`
- `0x18007791c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800779d0`
- `KERNEL32!GetLastError` at `0x1800779db`
- `KERNEL32!GetLastError` at `0x180077bfb`
- `KERNEL32!GetLastError` at `0x1800779d0`
- `KERNEL32!GetLastError` at `0x1800779db`
- `KERNEL32!GetLastError` at `0x180077bfb`
- `KERNEL32!GetFileAttributesW` at `0x1800779c1`
- `KERNEL32!GetFileAttributesW` at `0x1800779c1`
- `KERNEL32!CreateDirectoryW` at `0x180077a60`
- `KERNEL32!CreateDirectoryW` at `0x180077a60`

## string_xrefs

- `0x18007795c`: `CSrmFileSafe::CreateDirectoryInternal`
- `0x180077aeb`: `Directory already exists '%s' ...`
- `0x180077a3a`: `CreateDirectory('%s') ...`
- `0x180077b9e`: `CreateDirectory('%s')`
- `0x180077be1`: `- A file exists with the same name '%s'. Installation cannot continue.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CSrmFileSafe::CreateDirectoryInternal(LPCWSTR lpPathName)
{
  char v2; // si
  const WCHAR *v3; // rcx
  DWORD FileAttributesW; // eax
  LPCWSTR v5; // rdi
  const WCHAR *v6; // rcx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  DWORD LastError; // edi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v16; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v17; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[96]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+D0h] [rbp-30h]
  _QWORD v24[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v25; // [rsp+F0h] [rbp-10h]
  int v26; // [rsp+F4h] [rbp-Ch]
  int v27; // [rsp+F8h] [rbp-8h]
  _BYTE v28[96]; // [rsp+100h] [rbp+0h] BYREF
  int v29; // [rsp+160h] [rbp+60h]
  _QWORD v30[22]; // [rsp+170h] [rbp+70h] BYREF

  v24[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v24[1] = L"CSrmFileSafe::CreateDirectoryInternal";
  v24[2] = L"FILESF_C";
  v25 = 999;
  v26 = 17;
  v27 = 255;
  v29 = 0x1000000;
  v2 = 1;
  memset_0(v28, 0, sizeof(v28));
  CSrmFunctionTracer::CSrmFunctionTracer(v30, v24, L"CSrmFileSafe::CreateDirectoryInternal");
  if ( *((_QWORD *)lpPathName + 3) < 8u )
    v3 = lpPathName;
  else
    v3 = *(const WCHAR **)lpPathName;
  FileAttributesW = GetFileAttributesW(v3);
  if ( FileAttributesW == -1 )
  {
    if ( GetLastError() != 2 && GetLastError() != 3 )
    {
      LastError = GetLastError();
      v13 = std::wstring::c_str(lpPathName);
      v14 = CSrmDebugInfo::CSrmDebugInfo(
              &v16,
              L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              L"FILESF_C",
              L"CSrmFileSafe::CreateDirectoryInternal",
              1016,
              17);
      LODWORD(v15) = LastError;
      CSrmFunctionTracer::TranslateWin32Error(v30, v14, L"GetFileAttributes('%s') [%d]", v13, v15);
    }
    if ( *((_QWORD *)lpPathName + 3) < 8u )
      v5 = lpPathName;
    else
      v5 = *(LPCWSTR *)lpPathName;
    v16 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v17 = L"CSrmFileSafe::CreateDirectoryInternal";
    v18 = L"FILESF_C";
    v19 = 1009;
    v20 = 17;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CSrmFunctionTracer::Trace(v30, &v16, L"CreateDirectory('%s') ...", v5);
    if ( *((_QWORD *)lpPathName + 3) < 8u )
      v6 = lpPathName;
    else
      v6 = *(const WCHAR **)lpPathName;
    if ( !CreateDirectoryW(v6, 0) )
    {
      v8 = std::wstring::c_str(lpPathName);
      v9 = CSrmDebugInfo::CSrmDebugInfo(
             &v16,
             L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
             L"FILESF_C",
             L"CSrmFileSafe::CreateDirectoryInternal",
             1012,
             17);
      CSrmFunctionTracer::TranslateWin32Error(v30, v9, L"CreateDirectory('%s')", v8);
    }
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v30,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
  }
  else
  {
    if ( (FileAttributesW & 0x10) == 0 )
    {
      v10 = std::wstring::c_str(lpPathName);
      v11 = CSrmDebugInfo::CSrmDebugInfo(
              &v16,
              L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              L"FILESF_C",
              L"CSrmFileSafe::CreateDirectoryInternal",
              1028,
              17);
      CSrmFunctionTracer::Throw(
        v30,
        v11,
        2147767062LL,
        L"- A file exists with the same name '%s'. Installation cannot continue.",
        v10);
    }
    if ( *((_QWORD *)lpPathName + 3) >= 8u )
      lpPathName = *(LPCWSTR *)lpPathName;
    v16 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v17 = L"CSrmFileSafe::CreateDirectoryInternal";
    v18 = L"FILESF_C";
    v19 = 1022;
    v20 = 17;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CSrmFunctionTracer::Trace(v30, &v16, L"Directory already exists '%s' ...", lpPathName);
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v30,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v2 = 0;
  }
  v30[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v30);
  return v2;
}

```

## disassembly

```asm
0x18007791c  mov     [rsp-8+arg_8], rbx
0x180077921  mov     [rsp-8+arg_10], rsi
0x180077926  push    rbp
0x180077927  push    rdi
0x180077928  push    r12
0x18007792a  push    r13
0x18007792c  push    r15
0x18007792e  lea     rbp, [rsp-130h]
0x180077936  sub     rsp, 230h
0x18007793d  mov     rax, cs:__security_cookie
0x180077944  xor     rax, rsp
0x180077947  mov     [rbp+150h+var_30], rax
0x18007794e  mov     rbx, rcx
0x180077951  lea     r12, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180077958  mov     [rbp+150h+var_178], r12
0x18007795c  lea     r15, aCsrmfilesafeCr; "CSrmFileSafe::CreateDirectoryInternal"
0x180077963  mov     [rbp+150h+var_170], r15
0x180077967  lea     r13, aFilesfC; "FILESF_C"
0x18007796e  mov     [rbp+150h+var_168], r13
0x180077972  mov     [rbp+150h+var_160], 3E7h
0x180077979  mov     edi, 11h
0x18007797e  mov     [rbp+150h+var_15C], edi
0x180077981  mov     [rbp+150h+var_158], 0FFh
0x180077988  mov     [rbp+150h+var_F0], 1000000h
0x18007798f  mov     sil, 1
0x180077992  xor     edx, edx; Val
0x180077994  lea     r8d, [rdi+4Fh]; Size
0x180077998  lea     rcx, [rbp+150h+var_150]; void *
0x18007799c  call    memset_0
0x1800779a1  mov     r8, r15
0x1800779a4  lea     rdx, [rbp+150h+var_178]
0x1800779a8  lea     rcx, [rbp+150h+var_E0]
0x1800779ac  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800779b1  nop
0x1800779b2  cmp     qword ptr [rbx+18h], 8
0x1800779b7  jb      short loc_1800779BE
0x1800779b9  mov     rcx, [rbx]
0x1800779bc  jmp     short loc_1800779C1
0x1800779be  mov     rcx, rbx; lpFileName
0x1800779c1  call    cs:__imp_GetFileAttributesW
0x1800779c7  cmp     eax, 0FFFFFFFFh
0x1800779ca  jnz     loc_180077A9C
0x1800779d0  call    cs:__imp_GetLastError
0x1800779d6  cmp     eax, 2
0x1800779d9  jz      short loc_1800779EA
0x1800779db  call    cs:__imp_GetLastError
0x1800779e1  cmp     eax, 3
0x1800779e4  jnz     loc_180077BFB
0x1800779ea  cmp     qword ptr [rbx+18h], 8
0x1800779ef  jb      short loc_1800779F6
0x1800779f1  mov     rdi, [rbx]
0x1800779f4  jmp     short loc_1800779F9
0x1800779f6  mov     rdi, rbx
0x1800779f9  mov     [rsp+250h+var_208], r12
0x1800779fe  mov     [rsp+250h+var_200], r15
0x180077a03  mov     [rsp+250h+var_1F8], r13
0x180077a08  mov     [rsp+250h+var_1F0], 3F1h
0x180077a10  mov     [rsp+250h+var_1EC], 11h
0x180077a18  mov     [rsp+250h+var_1E8], 0FFh
0x180077a20  mov     [rbp+150h+var_180], 1000000h
0x180077a27  xor     edx, edx; Val
0x180077a29  lea     r8d, [rdx+60h]; Size
0x180077a2d  lea     rcx, [rsp+250h+var_1E0]; void *
0x180077a32  call    memset_0
0x180077a37  mov     r9, rdi
0x180077a3a  lea     r8, aCreatedirector_0; "CreateDirectory('%s') ..."
0x180077a41  lea     rdx, [rsp+250h+var_208]
0x180077a46  lea     rcx, [rbp+150h+var_E0]
0x180077a4a  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180077a4f  cmp     qword ptr [rbx+18h], 8
0x180077a54  jb      short loc_180077A5B
0x180077a56  mov     rcx, [rbx]
0x180077a59  jmp     short loc_180077A5E
0x180077a5b  mov     rcx, rbx; lpPathName
0x180077a5e  xor     edx, edx; lpSecurityAttributes
0x180077a60  call    cs:__imp_CreateDirectoryW
0x180077a66  test    eax, eax
0x180077a68  jz      loc_180077B6D
0x180077a6e  lea     rax, aTrue_0; "TRUE"
0x180077a75  mov     [rsp+250h+var_230], rax
0x180077a7a  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180077a81  mov     r8d, 0AAh; unsigned int
0x180077a87  lea     rdx, aReturn; "RETURN"
0x180077a8e  lea     rcx, [rbp+150h+var_E0]; this
0x180077a92  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180077a97  jmp     loc_180077B2B
0x180077a9c  test    al, 10h
0x180077a9e  jz      loc_180077BB2
0x180077aa4  cmp     qword ptr [rbx+18h], 8
0x180077aa9  jb      short loc_180077AAE
0x180077aab  mov     rbx, [rbx]
0x180077aae  mov     [rsp+250h+var_208], r12
0x180077ab3  mov     [rsp+250h+var_200], r15
0x180077ab8  mov     [rsp+250h+var_1F8], r13
0x180077abd  mov     [rsp+250h+var_1F0], 3FEh
0x180077ac5  mov     [rsp+250h+var_1EC], edi
0x180077ac9  mov     [rsp+250h+var_1E8], 0FFh
0x180077ad1  mov     [rbp+150h+var_180], 1000000h
0x180077ad8  xor     edx, edx; Val
0x180077ada  lea     r8d, [rdx+60h]; Size
0x180077ade  lea     rcx, [rsp+250h+var_1E0]; void *
0x180077ae3  call    memset_0
0x180077ae8  mov     r9, rbx
0x180077aeb  lea     r8, aDirectoryAlrea; "Directory already exists '%s' ..."
0x180077af2  lea     rdx, [rsp+250h+var_208]
0x180077af7  lea     rcx, [rbp+150h+var_E0]
0x180077afb  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180077b00  lea     rax, aFalse; "FALSE"
0x180077b07  mov     [rsp+250h+var_230], rax
0x180077b0c  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180077b13  mov     r8d, 0AAh; unsigned int
0x180077b19  lea     rdx, aReturn; "RETURN"
0x180077b20  lea     rcx, [rbp+150h+var_E0]; this
0x180077b24  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180077b29  xor     esi, esi
0x180077b2b  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180077b32  mov     [rbp+150h+var_E0], rax
0x180077b36  lea     rcx, [rbp+150h+var_E0]; this
0x180077b3a  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180077b3f  mov     al, sil
0x180077b42  mov     rcx, [rbp+150h+var_30]
0x180077b49  xor     rcx, rsp; StackCookie
0x180077b4c  call    __security_check_cookie
0x180077b51  lea     r11, [rsp+250h+var_20]
0x180077b59  mov     rbx, [r11+38h]
0x180077b5d  mov     rsi, [r11+40h]
0x180077b61  mov     rsp, r11
0x180077b64  pop     r15
0x180077b66  pop     r13
0x180077b68  pop     r12
0x180077b6a  pop     rdi
0x180077b6b  pop     rbp
0x180077b6c  retn
0x180077b6d  mov     rcx, rbx
0x180077b70  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180077b75  mov     rbx, rax
0x180077b78  mov     [rsp+250h+var_228], 11h
0x180077b80  mov     dword ptr [rsp+250h+var_230], 3F4h
0x180077b88  mov     r9, r15
0x180077b8b  mov     r8, r13
0x180077b8e  mov     rdx, r12
0x180077b91  lea     rcx, [rsp+250h+var_208]
0x180077b96  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180077b9b  mov     r9, rbx
0x180077b9e  lea     r8, aCreatedirector; "CreateDirectory('%s')"
0x180077ba5  mov     rdx, rax
0x180077ba8  lea     rcx, [rbp+150h+var_E0]
0x180077bac  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x180077bb2  mov     rcx, rbx
0x180077bb5  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180077bba  mov     rbx, rax
0x180077bbd  mov     [rsp+250h+var_228], edi
0x180077bc1  mov     dword ptr [rsp+250h+var_230], 404h
0x180077bc9  mov     r9, r15
0x180077bcc  mov     r8, r13
0x180077bcf  mov     rdx, r12
0x180077bd2  lea     rcx, [rsp+250h+var_208]
0x180077bd7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180077bdc  mov     [rsp+250h+var_230], rbx
0x180077be1  lea     r9, aAFileExistsWit; "- A file exists with the same name '%s'"...
0x180077be8  mov     r8d, 80045316h
0x180077bee  mov     rdx, rax
0x180077bf1  lea     rcx, [rbp+150h+var_E0]
0x180077bf5  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180077bfb  call    cs:__imp_GetLastError
0x180077c01  mov     edi, eax
0x180077c03  mov     rcx, rbx
0x180077c06  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180077c0b  mov     rbx, rax
0x180077c0e  mov     [rsp+250h+var_228], 11h
0x180077c16  mov     dword ptr [rsp+250h+var_230], 3F8h
0x180077c1e  mov     r9, r15
0x180077c21  mov     r8, r13
0x180077c24  mov     rdx, r12
0x180077c27  lea     rcx, [rsp+250h+var_208]
0x180077c2c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180077c31  mov     dword ptr [rsp+250h+var_230], edi
0x180077c35  mov     r9, rbx
0x180077c38  lea     r8, aGetfileattribu; "GetFileAttributes('%s') [%d]"
0x180077c3f  mov     rdx, rax
0x180077c42  lea     rcx, [rbp+150h+var_E0]
0x180077c46  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```
