# CSrmFileSafe::SafeOpenForWrite(int,ulong,void *)

- ea: `0x180079b9c`
- end: `0x18007a3af`
- name: `?SafeOpenForWrite@CSrmFileSafe@@QEAAXHKPEAX@Z`
- size: `2067`
- prototype: `void __fastcall(CSrmFileSafe *this, __int64, __int64, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800106e0`

## callees

- `0x1800031d0`
- `0x180006a1c`
- `0x18000af10`
- `0x18000ee10`
- `0x18000eef4`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073d04`
- `0x180074048`
- `0x180074a04`
- `0x180075034`
- `0x180077c54`
- `0x180078128`
- `0x18007945c`
- `0x180079b9c`
- `0x18007aa14`
- `0x18007f650`
- `0x18007f760`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007a1b3`
- `ole32!CoTaskMemFree` at `0x18007a1b3`
- `KERNEL32!SetEndOfFile` at `0x180079f3c`
- `KERNEL32!SetEndOfFile` at `0x180079f3c`
- `KERNEL32!CreateFileW` at `0x180079d64`
- `KERNEL32!CreateFileW` at `0x180079d64`
- `KERNEL32!CloseHandle` at `0x180079d7a`
- `KERNEL32!CloseHandle` at `0x180079d7a`
- `KERNEL32!GetLastError` at `0x180079d91`
- `KERNEL32!GetLastError` at `0x180079d91`

## string_xrefs

- `0x18007a2b5`: `Access denied to SRM store file %s`
- `0x18007a0d6`: `Volume not ready for SRM store file %s`
- `0x180079e0f`: `CreateFileW for SRM store file %s failed with %lu`
- `0x180079cf0`: `Opening file '%s' for write ...`
- `0x180079ed4`: `SRM metadata directory was created on %s, will retry the create-store-file`
- `0x180079bdf`: `CSrmFileSafe::SafeOpenForWrite`
- `0x180079f82`: `CSrmFileSafe::SafeOpenForWrite`
- `0x18007a01a`: `File already opened?`
- `0x18007a1fc`: `CreateFileW(%s, GENERIC_WRITE)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CSrmFileSafe::SafeOpenForWrite(CSrmFileSafe *this, __int64 a2, __int64 a3, void *a4)
{
  CSrmFileSafe *v4; // r14
  const WCHAR **v5; // rbx
  const WCHAR *v6; // rsi
  const WCHAR *v7; // rcx
  HANDLE v8; // rsi
  void *v9; // rcx
  unsigned __int64 LastError; // rsi
  const WCHAR *v11; // rcx
  CSrmFileSafe *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int16 *v15; // r8
  struct CSrmDebugInfo *v16; // r9
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  const unsigned __int16 *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  unsigned __int16 *v24; // rax
  struct CSrmDebugInfo *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  unsigned int Hr; // eax
  __int64 v32; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-358h]
  unsigned __int8 v34[16]; // [rsp+40h] [rbp-338h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-328h] BYREF
  CSrmFileSafe *v36; // [rsp+60h] [rbp-318h]
  const WCHAR *v37; // [rsp+70h] [rbp-308h]
  _BYTE *v38; // [rsp+78h] [rbp-300h]
  const unsigned __int16 *v39; // [rsp+80h] [rbp-2F8h] BYREF
  const unsigned __int16 *v40; // [rsp+88h] [rbp-2F0h]
  const unsigned __int16 *v41; // [rsp+90h] [rbp-2E8h]
  int v42; // [rsp+98h] [rbp-2E0h]
  int v43; // [rsp+9Ch] [rbp-2DCh]
  int v44; // [rsp+A0h] [rbp-2D8h]
  _BYTE v45[96]; // [rsp+A8h] [rbp-2D0h] BYREF
  int v46; // [rsp+108h] [rbp-270h]
  int v47; // [rsp+110h] [rbp-268h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+118h] [rbp-260h] BYREF
  _com_error *v49; // [rsp+130h] [rbp-248h] BYREF
  const exception *v50; // [rsp+138h] [rbp-240h] BYREF
  _QWORD v51[3]; // [rsp+140h] [rbp-238h] BYREF
  int v52; // [rsp+158h] [rbp-220h]
  int v53; // [rsp+15Ch] [rbp-21Ch]
  int v54; // [rsp+160h] [rbp-218h]
  _DWORD v55[26]; // [rsp+168h] [rbp-210h] BYREF
  void **v56; // [rsp+1D0h] [rbp-1A8h] BYREF
  int v57; // [rsp+1D8h] [rbp-1A0h]
  unsigned int v58; // [rsp+1FCh] [rbp-17Ch]
  WCHAR FileName[24]; // [rsp+280h] [rbp-F8h] BYREF
  WCHAR szVolumeName[4]; // [rsp+2B0h] [rbp-C8h] BYREF
  const unsigned __int16 *v61; // [rsp+2B8h] [rbp-C0h]
  const unsigned __int16 *v62; // [rsp+2C0h] [rbp-B8h]
  int v63; // [rsp+2C8h] [rbp-B0h]
  int v64; // [rsp+2CCh] [rbp-ACh]
  int v65; // [rsp+2D0h] [rbp-A8h]
  _BYTE v66[96]; // [rsp+2D8h] [rbp-A0h] BYREF
  int v67; // [rsp+338h] [rbp-40h]

  v4 = this;
  v36 = this;
  v51[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v51[1] = L"CSrmFileSafe::SafeOpenForWrite";
  v51[2] = L"FILESF_C";
  v52 = 312;
  v53 = 17;
  v54 = 255;
  v55[24] = 0x1000000;
  memset_0(v55, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v56, v51, 0);
  if ( *((_BYTE *)v4 + 200) || (v38 = (char *)v4 + 201, *((_BYTE *)v4 + 201)) )
  {
    v14 = CSrmDebugInfo::CSrmDebugInfo(
            &v39,
            L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            L"FILESF_C",
            L"CSrmFileSafe::SafeOpenForWrite",
            316,
            17);
    CSrmFunctionTracer::Throw(&v56, v14, 2147549183LL, L"File already opened?");
  }
  CSrmFileSafe::RecoverSafeFile(v4);
  v5 = (const WCHAR **)((char *)v4 + 120);
  pv = (char *)v4 + 120;
  if ( *((_QWORD *)v4 + 18) < 8u )
    v6 = (const WCHAR *)((char *)v4 + 120);
  else
    v6 = *v5;
  *(_QWORD *)szVolumeName = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v61 = L"CSrmFileSafe::SafeOpenForWrite";
  v62 = L"FILESF_C";
  v63 = 321;
  v64 = 17;
  v65 = 255;
  v67 = 0x1000000;
  memset_0(v66, 0, sizeof(v66));
  CSrmFunctionTracer::Trace(&v56, szVolumeName, L"Opening file '%s' for write ...", v6);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  for ( *(_DWORD *)v34 = 1; ; *(_DWORD *)v34 = 0 )
  {
    if ( *((_QWORD *)v4 + 18) < 8u )
      v7 = (const WCHAR *)((char *)v4 + 120);
    else
      v7 = *v5;
    v8 = CreateFileW(v7, 0x40000000u, 0, &SecurityAttributes, 2u, 0x2000006u, 0);
    v9 = (void *)*((_QWORD *)v4 + 27);
    if ( v9 != (void *)-1LL )
      CloseHandle(v9);
    *((_QWORD *)v4 + 27) = v8;
    if ( v8 != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    if ( *((_QWORD *)v4 + 18) < 8u )
      v37 = (const WCHAR *)((char *)v4 + 120);
    else
      v37 = *v5;
    *(_QWORD *)szVolumeName = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v61 = L"CSrmFileSafe::SafeOpenForWrite";
    v62 = L"FILESF_C";
    v63 = 349;
    v64 = 17;
    v65 = 255;
    v67 = 0x1000000;
    memset_0(v66, 0, sizeof(v66));
    dwCreationDisposition[0] = LastError;
    CSrmFunctionTracer::Trace(
      &v56,
      szVolumeName,
      L"CreateFileW for SRM store file %s failed with %lu",
      v37,
      *(_QWORD *)dwCreationDisposition);
    if ( (_DWORD)LastError != 3 )
    {
      if ( (_DWORD)LastError == 5 )
      {
        CSrmDebugInfo::CSrmDebugInfo(
          szVolumeName,
          L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
          L"FILESF_C",
          L"CSrmFileSafe::SafeOpenForWrite",
          388,
          17);
        v24 = (unsigned __int16 *)std::wstring::c_str((char *)v4 + 120);
        v26 = CSrmDebugInfo::operator<<(v25, (CSrmDebugInfo *)&v39, v24);
        CSrmFunctionTracer::LogError(&v56, 2147754020LL, v26, 2);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)szVolumeName);
        v27 = std::wstring::c_str((char *)v4 + 120);
        v28 = CSrmDebugInfo::CSrmDebugInfo(
                &v39,
                L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                L"FILESF_C",
                L"CSrmFileSafe::SafeOpenForWrite",
                391,
                17);
        CSrmFunctionTracer::Throw(&v56, v28, 2147942405LL, L"Access denied to SRM store file %s", v27);
      }
      if ( (unsigned int)LastError > 0x37 || (v13 = 0x80000000280000LL, !_bittest64(&v13, LastError)) )
      {
        if ( (_DWORD)LastError == 112 )
        {
          pv = 0;
          if ( *((_QWORD *)v4 + 18) < 8u )
            v20 = (const unsigned __int16 *)((char *)v4 + 120);
          else
            v20 = *v5;
          SrmGetVolumeDisplayNameForPath(v20, (unsigned __int16 **)&pv);
          v39 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
          v40 = L"CSrmFileSafe::SafeOpenForWrite";
          v41 = L"FILESF_C";
          v42 = 379;
          v43 = 17;
          v44 = 255;
          v46 = 0x1000000;
          memset_0(v45, 0, sizeof(v45));
          v21 = CSrmDebugInfo::operator<<(
                  (struct CSrmDebugInfo *)&v39,
                  (CSrmDebugInfo *)szVolumeName,
                  (unsigned __int16 *)pv);
          CSrmFunctionTracer::LogError(&v56, 2147758110LL, v21, 1);
          CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v39);
          CoTaskMemFree(pv);
        }
        else if ( (_DWORD)LastError == 1167 )
        {
          goto LABEL_33;
        }
LABEL_38:
        v22 = std::wstring::c_str((char *)v4 + 120);
        if ( (int)LastError > 0 )
          LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
        v23 = CSrmDebugInfo::CSrmDebugInfo(
                &v39,
                L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                L"FILESF_C",
                L"CSrmFileSafe::SafeOpenForWrite",
                418,
                17);
        CSrmFunctionTracer::TranslateGenericError(
          &v56,
          v23,
          (unsigned int)LastError,
          L"CreateFileW(%s, GENERIC_WRITE)",
          v22);
      }
LABEL_33:
      CSrmDebugInfo::CSrmDebugInfo(
        szVolumeName,
        L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
        L"FILESF_C",
        L"CSrmFileSafe::SafeOpenForWrite",
        401,
        17);
      v15 = (unsigned __int16 *)std::wstring::c_str((char *)v4 + 120);
      v17 = CSrmDebugInfo::operator<<(v16, (CSrmDebugInfo *)&v39, v15);
      CSrmFunctionTracer::LogError(&v56, 2147754041LL, v17, 2);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)szVolumeName);
      v18 = std::wstring::c_str((char *)v4 + 120);
      v19 = CSrmDebugInfo::CSrmDebugInfo(
              &v39,
              L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              L"FILESF_C",
              L"CSrmFileSafe::SafeOpenForWrite",
              404,
              17);
      CSrmFunctionTracer::Throw(&v56, v19, 2147767142LL, L"Volume not ready for SRM store file %s", v18);
    }
    if ( !*(_DWORD *)v34 )
      goto LABEL_38;
    if ( *((_QWORD *)v4 + 18) < 8u )
      v11 = (const WCHAR *)((char *)v4 + 120);
    else
      v11 = *v5;
    SrmGetVolumeNameForPathName(v11, szVolumeName, 0x32u, 1, 0);
    CSrmFileSafe::CreateMetadataFolder(v12, szVolumeName);
    v39 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v40 = L"CSrmFileSafe::SafeOpenForWrite";
    v41 = L"FILESF_C";
    v42 = 367;
    v43 = 17;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CSrmFunctionTracer::Trace(
      &v56,
      &v39,
      L"SRM metadata directory was created on %s, will retry the create-store-file",
      szVolumeName);
  }
  try
  {
    if ( !SetEndOfFile(*((HANDLE *)v4 + 27)) )
    {
      v29 = std::wstring::c_str((char *)v4 + 120);
      v30 = CSrmDebugInfo::CSrmDebugInfo(
              &v39,
              L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              L"FILESF_C",
              L"CSrmFileSafe::SafeOpenForWrite",
              431,
              17);
      CSrmFunctionTracer::TranslateWin32Error(&v56, v30, L"SetEndOfFile('%s')", v29);
    }
    *(_WORD *)v34 = -257;
    CSrmFileSafe::WriteToFile(v4, (struct CSrmFunctionTracer *)&v56, v34, 2u);
  }
  catch ( long v47 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v56,
      v47,
      L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      L"FILESF_C",
      L"CSrmFileSafe::SafeOpenForWrite",
      0x1B5u,
      v58);
    v5 = (const WCHAR **)pv;
    v4 = v36;
  }
  catch ( _com_error *v49 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v56,
      v49,
      L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      L"FILESF_C",
      L"CSrmFileSafe::SafeOpenForWrite",
      0x1B5u,
      v58);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v56,
      L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      L"FILESF_C",
      L"CSrmFileSafe::SafeOpenForWrite",
      0x1B5u,
      v58);
    v5 = (const WCHAR **)pv;
    v4 = v36;
  }
  catch ( const exception *v50 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v56,
      v50,
      L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      L"FILESF_C",
      L"CSrmFileSafe::SafeOpenForWrite",
      0x1B5u,
      v58);
  }
  if ( !SetEndOfFile(*((HANDLE *)v4 + 27)) )
  {
    v29 = std::wstring::c_str((char *)v4 + 120);
    v30 = CSrmDebugInfo::CSrmDebugInfo(
            &v39,
            L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            L"FILESF_C",
            L"CSrmFileSafe::SafeOpenForWrite",
            431,
            17);
    CSrmFunctionTracer::TranslateWin32Error(&v56, v30, L"SetEndOfFile('%s')", v29);
  }
  *(_WORD *)v34 = -257;
  CSrmFileSafe::WriteToFile(v4, (struct CSrmFunctionTracer *)&v56, v34, 2u);
  CSrmFunctionTracer::HandleHresultException(
    (CSrmFunctionTracer *)&v56,
    v47,
    L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
    L"FILESF_C",
    L"CSrmFileSafe::SafeOpenForWrite",
    0x1B5u,
    v58);
}

```

## disassembly

```asm
0x180079b9c  mov     r11, rsp
0x180079b9f  mov     [r11+10h], rbx
0x180079ba3  mov     [r11+18h], rsi
0x180079ba7  push    rdi
0x180079ba8  push    r12
0x180079baa  push    r13
0x180079bac  push    r14
0x180079bae  push    r15
0x180079bb0  sub     rsp, 350h
0x180079bb7  mov     rax, cs:__security_cookie
0x180079bbe  xor     rax, rsp
0x180079bc1  mov     [rsp+378h+var_38], rax
0x180079bc9  mov     r14, rcx
0x180079bcc  mov     [rsp+378h+var_318], rcx
0x180079bd1  lea     r15, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180079bd8  mov     [r11-238h], r15
0x180079bdf  lea     r12, aCsrmfilesafeSa; "CSrmFileSafe::SafeOpenForWrite"
0x180079be6  mov     [r11-230h], r12
0x180079bed  lea     r13, aFilesfC; "FILESF_C"
0x180079bf4  mov     [r11-228h], r13
0x180079bfb  mov     [rsp+378h+var_220], 138h
0x180079c06  mov     [rsp+378h+var_21C], 11h
0x180079c11  mov     [rsp+378h+var_218], 0FFh
0x180079c1c  xor     edi, edi
0x180079c1e  mov     [rsp+378h+var_1B0], 1000000h
0x180079c29  xor     edx, edx; Val
0x180079c2b  lea     r8d, [rdi+60h]; Size
0x180079c2f  lea     rcx, [r11-210h]; void *
0x180079c36  call    memset_0
0x180079c3b  xor     r8d, r8d
0x180079c3e  lea     rdx, [rsp+378h+var_238]
0x180079c46  lea     rcx, [rsp+378h+var_1A8]
0x180079c4e  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180079c53  nop
0x180079c54  cmp     [r14+0C8h], dil
0x180079c5b  jnz     loc_180079FF4
0x180079c61  lea     rax, [r14+0C9h]
0x180079c68  mov     [rsp+378h+var_300], rax
0x180079c6d  cmp     [rax], dil
0x180079c70  jnz     loc_180079FF4
0x180079c76  mov     rcx, r14; this
0x180079c79  call    ?RecoverSafeFile@CSrmFileSafe@@QEAAXXZ; CSrmFileSafe::RecoverSafeFile(void)
0x180079c7e  lea     rbx, [r14+78h]
0x180079c82  mov     [rsp+378h+pv], rbx
0x180079c87  cmp     qword ptr [rbx+18h], 8
0x180079c8c  jb      short loc_180079C93
0x180079c8e  mov     rsi, [rbx]
0x180079c91  jmp     short loc_180079C96
0x180079c93  mov     rsi, rbx
0x180079c96  mov     qword ptr [rsp+378h+szVolumeName], r15
0x180079c9e  mov     [rsp+378h+var_C0], r12
0x180079ca6  mov     [rsp+378h+var_B8], r13
0x180079cae  mov     [rsp+378h+var_B0], 141h
0x180079cb9  mov     [rsp+378h+var_AC], 11h
0x180079cc4  mov     [rsp+378h+var_A8], 0FFh
0x180079ccf  mov     [rsp+378h+var_40], 1000000h
0x180079cda  xor     edx, edx; Val
0x180079cdc  lea     r8d, [rdx+60h]; Size
0x180079ce0  lea     rcx, [rsp+378h+var_A0]; void *
0x180079ce8  call    memset_0
0x180079ced  mov     r9, rsi
0x180079cf0  lea     r8, aOpeningFileSFo_0; "Opening file '%s' for write ..."
0x180079cf7  lea     rdx, [rsp+378h+szVolumeName]
0x180079cff  lea     rcx, [rsp+378h+var_1A8]
0x180079d07  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180079d0c  mov     qword ptr [rsp+378h+SecurityAttributes.nLength], 18h
0x180079d18  mov     qword ptr [rsp+378h+SecurityAttributes.bInheritHandle], rdi
0x180079d20  mov     [rsp+378h+SecurityAttributes.lpSecurityDescriptor], rdi
0x180079d28  mov     dword ptr [rsp+378h+var_338], 1
0x180079d30  cmp     qword ptr [rbx+18h], 8
0x180079d35  jb      short loc_180079D3C
0x180079d37  mov     rcx, [rbx]
0x180079d3a  jmp     short loc_180079D3F
0x180079d3c  mov     rcx, rbx; lpFileName
0x180079d3f  mov     [rsp+378h+hTemplateFile], rdi; hTemplateFile
0x180079d44  mov     [rsp+378h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x180079d4c  mov     [rsp+378h+dwCreationDisposition], 2; dwCreationDisposition
0x180079d54  lea     r9, [rsp+378h+SecurityAttributes]; lpSecurityAttributes
0x180079d5c  xor     r8d, r8d; dwShareMode
0x180079d5f  mov     edx, 40000000h; dwDesiredAccess
0x180079d64  call    cs:__imp_CreateFileW
0x180079d6a  mov     rsi, rax
0x180079d6d  mov     rcx, [r14+0D8h]; hObject
0x180079d74  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180079d78  jz      short loc_180079D80
0x180079d7a  call    cs:__imp_CloseHandle
0x180079d80  mov     [r14+0D8h], rsi
0x180079d87  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180079d8b  jnz     loc_180079F35
0x180079d91  call    cs:__imp_GetLastError
0x180079d97  mov     esi, eax
0x180079d99  cmp     qword ptr [rbx+18h], 8
0x180079d9e  jb      short loc_180079DAA
0x180079da0  mov     rax, [rbx]
0x180079da3  mov     [rsp+378h+var_308], rax
0x180079da8  jmp     short loc_180079DAF
0x180079daa  mov     [rsp+378h+var_308], rbx
0x180079daf  mov     qword ptr [rsp+378h+szVolumeName], r15
0x180079db7  mov     [rsp+378h+var_C0], r12
0x180079dbf  mov     [rsp+378h+var_B8], r13
0x180079dc7  mov     [rsp+378h+var_B0], 15Dh
0x180079dd2  mov     [rsp+378h+var_AC], 11h
0x180079ddd  mov     [rsp+378h+var_A8], 0FFh
0x180079de8  mov     [rsp+378h+var_40], 1000000h
0x180079df3  xor     edx, edx; Val
0x180079df5  lea     r8d, [rdx+60h]; Size
0x180079df9  lea     rcx, [rsp+378h+var_A0]; void *
0x180079e01  call    memset_0
0x180079e06  mov     [rsp+378h+dwCreationDisposition], esi
0x180079e0a  mov     r9, [rsp+378h+var_308]
0x180079e0f  lea     r8, aCreatefilewFor; "CreateFileW for SRM store file %s faile"...
0x180079e16  lea     rdx, [rsp+378h+szVolumeName]
0x180079e1e  lea     rcx, [rsp+378h+var_1A8]
0x180079e26  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180079e2b  cmp     esi, 3
0x180079e2e  jnz     loc_180079EF9
0x180079e34  cmp     dword ptr [rsp+378h+var_338], edi
0x180079e38  jz      loc_18007A1B9
0x180079e3e  cmp     qword ptr [rbx+18h], 8
0x180079e43  jb      short loc_180079E4A
0x180079e45  mov     rcx, [rbx]
0x180079e48  jmp     short loc_180079E4D
0x180079e4a  mov     rcx, rbx; lpszFileName
0x180079e4d  mov     qword ptr [rsp+378h+dwCreationDisposition], rdi; unsigned __int16 **
0x180079e52  mov     r9b, 1; bool
0x180079e55  mov     r8d, 32h ; '2'; unsigned int
0x180079e5b  lea     rdx, [rsp+378h+szVolumeName]; lpszVolumeName
0x180079e63  call    ?SrmGetVolumeNameForPathName@@YAXPEBGPEAGK_NPEAPEAG@Z; SrmGetVolumeNameForPathName(ushort const *,ushort *,ulong,bool,ushort * *)
0x180079e68  lea     rdx, [rsp+378h+szVolumeName]; unsigned __int16 *
0x180079e70  call    ?CreateMetadataFolder@CSrmFileSafe@@AEAAXPEBG@Z; CSrmFileSafe::CreateMetadataFolder(ushort const *)
0x180079e75  mov     [rsp+378h+var_2F8], r15
0x180079e7d  mov     [rsp+378h+var_2F0], r12
0x180079e85  mov     [rsp+378h+var_2E8], r13
0x180079e8d  mov     [rsp+378h+var_2E0], 16Fh
0x180079e98  mov     [rsp+378h+var_2DC], 11h
0x180079ea3  mov     [rsp+378h+var_2D8], 0FFh
0x180079eae  mov     [rsp+378h+var_270], 1000000h
0x180079eb9  xor     edx, edx; Val
0x180079ebb  lea     r8d, [rdx+60h]; Size
0x180079ebf  lea     rcx, [rsp+378h+var_2D0]; void *
0x180079ec7  call    memset_0
0x180079ecc  lea     r9, [rsp+378h+szVolumeName]
0x180079ed4  lea     r8, aSrmMetadataDir; "SRM metadata directory was created on %"...
0x180079edb  lea     rdx, [rsp+378h+var_2F8]
0x180079ee3  lea     rcx, [rsp+378h+var_1A8]
0x180079eeb  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180079ef0  mov     dword ptr [rsp+378h+var_338], edi
0x180079ef4  jmp     loc_180079D30
0x180079ef9  cmp     esi, 5
0x180079efc  jz      loc_18007A217
0x180079f02  cmp     esi, 37h ; '7'
0x180079f05  ja      short loc_180079F1B
0x180079f07  mov     rcx, 80000000280000h
0x180079f11  bt      rcx, rsi
0x180079f15  jb      loc_18007A038
0x180079f1b  cmp     esi, 70h ; 'p'
0x180079f1e  jz      loc_18007A0F4
0x180079f24  cmp     esi, 48Fh
0x180079f2a  jnz     loc_18007A1B9
0x180079f30  jmp     loc_18007A038
0x180079f35  mov     rcx, [r14+0D8h]; hFile
0x180079f3c  call    cs:__imp_SetEndOfFile
0x180079f42  test    eax, eax
0x180079f44  jz      loc_18007A2D3
0x180079f4a  mov     word ptr [rsp+378h+var_338], 0FEFFh
0x180079f51  mov     r9d, 2; unsigned int
0x180079f57  lea     r8, [rsp+378h+var_338]; unsigned __int8 *
0x180079f5c  lea     rdx, [rsp+378h+var_1A8]; struct CSrmFunctionTracer *
0x180079f64  mov     rcx, r14; this
0x180079f67  call    ?WriteToFile@CSrmFileSafe@@AEAAXAEAVCSrmFunctionTracer@@PEAEK@Z; CSrmFileSafe::WriteToFile(CSrmFunctionTracer &,uchar *,ulong)
0x180079f6c  nop
0x180079f6d  jmp     short loc_180079F90
0x180079f6f  mov     rbx, [rsp+378h+pv]
0x180079f74  mov     r14, [rsp+378h+var_318]
0x180079f79  xor     edi, edi
0x180079f7b  lea     r13, aFilesfC; "FILESF_C"
0x180079f82  lea     r12, aCsrmfilesafeSa; "CSrmFileSafe::SafeOpenForWrite"
0x180079f89  lea     r15, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180079f90  cmp     [rsp+378h+var_1A0], edi
0x180079f97  jl      loc_18007A31F
0x180079f9d  jmp     short loc_180079FA3
0x180079f9f  jmp     short loc_180079F6F
0x180079fa1  jmp     short loc_180079F6F
0x180079fa3  mov     rax, [rsp+378h+var_300]
0x180079fa8  mov     byte ptr [rax], 1
0x180079fab  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180079fb2  mov     [rsp+378h+var_1A8], rax
0x180079fba  lea     rcx, [rsp+378h+var_1A8]; this
0x180079fc2  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180079fc7  mov     rcx, [rsp+378h+var_38]
0x180079fcf  xor     rcx, rsp; StackCookie
0x180079fd2  call    __security_check_cookie
0x180079fd7  lea     r11, [rsp+378h+var_28]
0x180079fdf  mov     rbx, [r11+38h]
0x180079fe3  mov     rsi, [r11+40h]
0x180079fe7  mov     rsp, r11
0x180079fea  pop     r15
0x180079fec  pop     r14
0x180079fee  pop     r13
0x180079ff0  pop     r12
0x180079ff2  pop     rdi
0x180079ff3  retn
0x180079ff4  mov     [rsp+378h+dwFlagsAndAttributes], 11h
0x180079ffc  mov     [rsp+378h+dwCreationDisposition], 13Ch
0x18007a004  mov     r9, r12
0x18007a007  mov     r8, r13
0x18007a00a  mov     rdx, r15
0x18007a00d  lea     rcx, [rsp+378h+var_2F8]
0x18007a015  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a01a  lea     r9, aFileAlreadyOpe; "File already opened?"
0x18007a021  mov     r8d, 8000FFFFh
0x18007a027  mov     rdx, rax
0x18007a02a  lea     rcx, [rsp+378h+var_1A8]
0x18007a032  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007a038  mov     edi, 11h
0x18007a03d  mov     [rsp+378h+dwFlagsAndAttributes], edi
0x18007a041  mov     [rsp+378h+dwCreationDisposition], 191h
0x18007a049  mov     r9, r12
0x18007a04c  mov     r8, r13
0x18007a04f  mov     rdx, r15
0x18007a052  lea     rcx, [rsp+378h+szVolumeName]
0x18007a05a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a05f  mov     r9, rax
0x18007a062  mov     rcx, rbx
0x18007a065  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007a06a  mov     r8, rax; unsigned __int16 *
0x18007a06d  lea     rdx, [rsp+378h+var_2F8]; this
0x18007a075  mov     rcx, r9; struct CSrmDebugInfo *
0x18007a078  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18007a07d  lea     r9d, [rdi-0Fh]
0x18007a081  mov     r8, rax
0x18007a084  mov     edx, 80042039h
0x18007a089  lea     rcx, [rsp+378h+var_1A8]
0x18007a091  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x18007a096  nop
0x18007a097  lea     rcx, [rsp+378h+szVolumeName]; this
0x18007a09f  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18007a0a4  mov     rcx, rbx
0x18007a0a7  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007a0ac  mov     rbx, rax
0x18007a0af  mov     [rsp+378h+dwFlagsAndAttributes], edi
0x18007a0b3  mov     [rsp+378h+dwCreationDisposition], 194h
0x18007a0bb  mov     r9, r12
0x18007a0be  mov     r8, r13
0x18007a0c1  mov     rdx, r15
0x18007a0c4  lea     rcx, [rsp+378h+var_2F8]
0x18007a0cc  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a0d1  mov     qword ptr [rsp+378h+dwCreationDisposition], rbx
0x18007a0d6  lea     r9, aVolumeNotReady; "Volume not ready for SRM store file %s"
0x18007a0dd  mov     r8d, 80045366h
0x18007a0e3  mov     rdx, rax
0x18007a0e6  lea     rcx, [rsp+378h+var_1A8]
0x18007a0ee  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007a0f4  mov     [rsp+378h+pv], rdi
0x18007a0f9  cmp     qword ptr [rbx+18h], 8
0x18007a0fe  jb      short loc_18007A105
0x18007a100  mov     rcx, [rbx]
0x18007a103  jmp     short loc_18007A108
0x18007a105  mov     rcx, rbx; unsigned __int16 *
0x18007a108  lea     rdx, [rsp+378h+pv]; unsigned __int16 **
0x18007a10d  call    ?SrmGetVolumeDisplayNameForPath@@YAXPEBGPEAPEAG@Z; SrmGetVolumeDisplayNameForPath(ushort const *,ushort * *)
0x18007a112  mov     [rsp+378h+var_2F8], r15
0x18007a11a  mov     [rsp+378h+var_2F0], r12
0x18007a122  mov     [rsp+378h+var_2E8], r13
0x18007a12a  mov     [rsp+378h+var_2E0], 17Bh
0x18007a135  mov     [rsp+378h+var_2DC], 11h
0x18007a140  mov     [rsp+378h+var_2D8], 0FFh
0x18007a14b  mov     [rsp+378h+var_270], 1000000h
0x18007a156  xor     edx, edx; Val
0x18007a158  lea     r8d, [rdx+60h]; Size
0x18007a15c  lea     rcx, [rsp+378h+var_2D0]; void *
0x18007a164  call    memset_0
0x18007a169  nop
0x18007a16a  mov     r8, [rsp+378h+pv]; unsigned __int16 *
0x18007a16f  lea     rdx, [rsp+378h+szVolumeName]; this
0x18007a177  lea     rcx, [rsp+378h+var_2F8]; struct CSrmDebugInfo *
0x18007a17f  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18007a184  mov     r9d, 1
0x18007a18a  mov     r8, rax
0x18007a18d  mov     edx, 8004301Eh
0x18007a192  lea     rcx, [rsp+378h+var_1A8]
0x18007a19a  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x18007a19f  nop
0x18007a1a0  lea     rcx, [rsp+378h+var_2F8]; this
0x18007a1a8  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18007a1ad  nop
0x18007a1ae  mov     rcx, [rsp+378h+pv]; pv
0x18007a1b3  call    cs:__imp_CoTaskMemFree
0x18007a1b9  mov     rcx, rbx
0x18007a1bc  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007a1c1  mov     rbx, rax
0x18007a1c4  test    esi, esi
0x18007a1c6  jle     short loc_18007A1D1
0x18007a1c8  movzx   esi, si
0x18007a1cb  or      esi, 80070000h
0x18007a1d1  mov     [rsp+378h+dwFlagsAndAttributes], 11h
0x18007a1d9  mov     [rsp+378h+dwCreationDisposition], 1A2h
0x18007a1e1  mov     r9, r12
0x18007a1e4  mov     r8, r13
0x18007a1e7  mov     rdx, r15
  ... truncated ...
```
