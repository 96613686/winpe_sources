# SrmGetVolumeNameForPathName(ushort const *,ushort *,ulong,bool,ushort * *)

- ea: `0x18007f760`
- end: `0x18007fbcf`
- name: `?SrmGetVolumeNameForPathName@@YAXPEBGPEAGK_NPEAPEAG@Z`
- size: `1135`
- prototype: `void __usercall(LPCWSTR lpszFileName@<rcx>, LPWSTR lpszVolumeName@<rdx>, unsigned int@<r8d>, bool@<r9b>, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `14`
- tags: `reparse_path, service_task`

## callers

- `0x18005162c`
- `0x180059008`
- `0x180079b9c`
- `0x18007b5f4`
- `0x18007cfe0`
- `0x18007f150`
- `0x18007f2bc`
- `0x18007f650`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x180016ee0`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180070bd8`
- `0x180073d04`
- `0x180074048`
- `0x180074d00`
- `0x18007f760`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007f9c1`
- `ole32!CoTaskMemFree` at `0x18007f9c1`
- `KERNEL32!GetLastError` at `0x18007f8b9`
- `KERNEL32!GetLastError` at `0x18007fa0f`
- `KERNEL32!GetLastError` at `0x18007fadd`
- `KERNEL32!GetLastError` at `0x18007fb56`
- `KERNEL32!GetLastError` at `0x18007f8b9`
- `KERNEL32!GetLastError` at `0x18007fa0f`
- `KERNEL32!GetLastError` at `0x18007fadd`
- `KERNEL32!GetLastError` at `0x18007fb56`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18007f942`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18007f95f`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18007f942`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18007f95f`
- `KERNEL32!GetVolumePathNameW` at `0x18007f8fc`
- `KERNEL32!GetVolumePathNameW` at `0x18007f8fc`

## string_xrefs

- `0x18007fbb8`: `GetVolumePathName`
- `0x18007f7bd`: `SrmGetVolumeNameForPathName`
- `0x18007f854`: `SrmGetVolumeNameForPathName`
- `0x18007fa52`: `SrmGetVolumeNameForPathName`
- `0x18007faa3`: `SrmGetVolumeNameForPathName`
- `0x18007fb1f`: `SrmGetVolumeNameForPathName`
- `0x18007fb98`: `SrmGetVolumeNameForPathName`
- `0x18007fa72`: `GetVolumeNameForVolumeMountPoint`
- `0x18007fb3f`: `GetVolumeNameForVolumeMountPoint`
- `0x18007fac3`: `GetVolumePathName: Filename is empty`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SrmGetVolumeNameForPathName(
        LPCWSTR lpszFileName,
        LPWSTR lpszVolumeName,
        DWORD a3,
        char a4,
        unsigned __int16 **a5)
{
  __int64 v7; // rdi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  DWORD LastError; // eax
  unsigned __int64 v11; // rax
  WCHAR *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  signed int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rax
  signed int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rax
  signed int v23; // eax
  unsigned int Hr; // ebx
  __int64 v25; // rax
  LPWSTR lpszVolumePathName; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 **v28; // [rsp+50h] [rbp-B0h]
  DWORD cchBufferLength; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v30; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v31; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  int v35; // [rsp+80h] [rbp-80h]
  _BYTE v36[96]; // [rsp+88h] [rbp-78h] BYREF
  int v37; // [rsp+E8h] [rbp-18h]
  _QWORD v38[22]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR szVolumeName[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  cchBufferLength = a3;
  v28 = &v30;
  v30 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
  v31 = L"SrmGetVolumeNameForPathName";
  v32 = L"SRMVOLMC";
  v33 = 75;
  v34 = 17;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v38, (const struct CSrmDebugInfo *)&v30, 0);
  lpszVolumePathName = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( lpszFileName[v8] );
  v9 = v8 + 1;
  CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumePathName, v8 + 1);
  v28 = &v30;
  v30 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
  v31 = L"SrmGetVolumeNameForPathName";
  v32 = L"SRMVOLMC";
  v33 = 88;
  v34 = 17;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CSrmFunctionTracer::Trace(v38, &v30, L"<%s>", lpszFileName);
  while ( 1 )
  {
    v12 = lpszVolumePathName;
    if ( GetVolumePathNameW(lpszFileName, lpszVolumePathName, v9 + 1) )
      break;
    LastError = GetLastError();
    if ( LastError != 206 )
    {
      if ( !LastError )
      {
        v28 = &v30;
        v19 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)&v30,
                (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
                (__int64)L"SRMVOLMC",
                (__int64)L"SrmGetVolumeNameForPathName",
                107,
                17);
        CSrmFunctionTracer::Throw(v38, v19, 2147942487LL, L"GetVolumePathName: Filename is empty");
      }
LABEL_36:
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v38, v23);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v38);
      v28 = &v30;
      v25 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v30,
              (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
              (__int64)L"SRMVOLMC",
              (__int64)L"SrmGetVolumeNameForPathName",
              114,
              17);
      CSrmFunctionTracer::TranslatePathError(v38, v25, Hr, L"GetVolumePathName");
    }
    if ( v9 > 0x104 )
      goto LABEL_36;
    v11 = 2 * v9;
    v9 = 260;
    if ( v11 <= 0x104 )
      v9 = v11;
    CSrmAutoPWSZ::Reallocate((CSrmAutoPWSZ *)&lpszVolumePathName, v9);
  }
  v13 = -1;
  do
    ++v13;
  while ( v12[v13] );
  if ( v12[v13 - 1] != 92 )
  {
    CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&lpszVolumePathName, L"\\");
    v12 = lpszVolumePathName;
  }
  if ( !GetVolumeNameForVolumeMountPointW(v12, szVolumeName, 0x100u) )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v38, v20);
    v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v38);
    v28 = &v30;
    v22 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v30,
            (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
            (__int64)L"SRMVOLMC",
            (__int64)L"SrmGetVolumeNameForPathName",
            131,
            17);
    CSrmFunctionTracer::TranslatePathError(v38, v22, v21, L"GetVolumeNameForVolumeMountPoint");
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, cchBufferLength) )
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v38, v16);
    v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v38);
    v28 = &v30;
    v18 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v30,
            (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
            (__int64)L"SRMVOLMC",
            (__int64)L"SrmGetVolumeNameForPathName",
            139,
            17);
    CSrmFunctionTracer::TranslatePathError(v38, v18, v17, L"GetVolumeNameForVolumeMountPoint");
  }
  if ( a4 )
  {
    v14 = -1;
    do
      ++v14;
    while ( lpszVolumeName[v14] );
    lpszVolumeName[v14 - 1] = 0;
  }
  if ( a5 )
  {
    do
      ++v7;
    while ( v12[v7] );
    if ( v7 - 1 > v8 )
      v15 = (unsigned __int16 *)&lpszFileName[v8];
    else
      v15 = (unsigned __int16 *)&lpszFileName[v7 - 1];
    *a5 = v15;
  }
  CoTaskMemFree(v12);
  lpszVolumePathName = 0;
  v38[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v38);
}

```

## disassembly

```asm
0x18007f760  mov     [rsp-8+arg_18], rbx
0x18007f765  push    rbp
0x18007f766  push    rsi
0x18007f767  push    rdi
0x18007f768  push    r12
0x18007f76a  push    r13
0x18007f76c  push    r14
0x18007f76e  push    r15
0x18007f770  lea     rbp, [rsp-2B0h]
0x18007f778  sub     rsp, 3B0h
0x18007f77f  mov     rax, cs:__security_cookie
0x18007f786  xor     rax, rsp
0x18007f789  mov     [rbp+2E0h+var_40], rax
0x18007f790  mov     [rsp+3E0h+var_3A0], r9b
0x18007f795  mov     [rsp+3E0h+cchBufferLength], r8d
0x18007f79a  mov     r13, rdx
0x18007f79d  mov     r15, rcx
0x18007f7a0  mov     r12, [rbp+2E0h+arg_20]
0x18007f7a7  lea     rax, [rsp+3E0h+var_380]
0x18007f7ac  mov     [rsp+3E0h+var_390], rax
0x18007f7b1  lea     rax, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007f7b8  mov     [rsp+3E0h+var_380], rax
0x18007f7bd  lea     rax, aSrmgetvolumena; "SrmGetVolumeNameForPathName"
0x18007f7c4  mov     [rsp+3E0h+var_378], rax
0x18007f7c9  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007f7d0  mov     [rsp+3E0h+var_370], rax
0x18007f7d5  mov     [rsp+3E0h+var_368], 4Bh ; 'K'
0x18007f7dd  mov     [rsp+3E0h+var_364], 11h
0x18007f7e5  mov     [rbp+2E0h+var_360], 0FFh
0x18007f7ec  xor     ebx, ebx
0x18007f7ee  mov     [rbp+2E0h+var_2F8], 1000000h
0x18007f7f5  xor     edx, edx; Val
0x18007f7f7  lea     r8d, [rbx+60h]; Size
0x18007f7fb  lea     rcx, [rbp+2E0h+var_358]; void *
0x18007f7ff  call    memset_0
0x18007f804  nop
0x18007f805  xor     r8d, r8d
0x18007f808  lea     rdx, [rsp+3E0h+var_380]
0x18007f80d  lea     rcx, [rbp+2E0h+var_2F0]
0x18007f811  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007f816  nop
0x18007f817  mov     [rsp+3E0h+lpszVolumePathName], rbx
0x18007f81c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007f820  mov     r14, rdi
0x18007f823  inc     r14
0x18007f826  cmp     [r15+r14*2], bx
0x18007f82b  jnz     short loc_18007F823
0x18007f82d  lea     rsi, [r14+1]
0x18007f831  mov     rdx, rsi; unsigned __int64
0x18007f834  lea     rcx, [rsp+3E0h+lpszVolumePathName]; this
0x18007f839  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007f83e  lea     rax, [rsp+3E0h+var_380]
0x18007f843  mov     [rsp+3E0h+var_390], rax
0x18007f848  lea     rax, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007f84f  mov     [rsp+3E0h+var_380], rax
0x18007f854  lea     rax, aSrmgetvolumena; "SrmGetVolumeNameForPathName"
0x18007f85b  mov     [rsp+3E0h+var_378], rax
0x18007f860  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007f867  mov     [rsp+3E0h+var_370], rax
0x18007f86c  mov     [rsp+3E0h+var_368], 58h ; 'X'
0x18007f874  mov     [rsp+3E0h+var_364], 11h
0x18007f87c  mov     [rbp+2E0h+var_360], 0FFh
0x18007f883  mov     [rbp+2E0h+var_2F8], 1000000h
0x18007f88a  xor     edx, edx; Val
0x18007f88c  lea     r8d, [rdx+60h]; Size
0x18007f890  lea     rcx, [rbp+2E0h+var_358]; void *
0x18007f894  call    memset_0
0x18007f899  nop
0x18007f89a  mov     r9, r15
0x18007f89d  lea     r8, aS_0; "<%s>"
0x18007f8a4  lea     rdx, [rsp+3E0h+var_380]
0x18007f8a9  lea     rcx, [rbp+2E0h+var_2F0]
0x18007f8ad  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007f8b2  jmp     short loc_18007F8ED
0x18007f8b4  mov     ebx, 104h
0x18007f8b9  call    cs:__imp_GetLastError
0x18007f8bf  cmp     eax, 0CEh
0x18007f8c4  jnz     loc_18007F9A9
0x18007f8ca  cmp     rsi, rbx
0x18007f8cd  ja      loc_18007FB56
0x18007f8d3  lea     rax, [rsi+rsi]
0x18007f8d7  mov     esi, ebx
0x18007f8d9  cmp     rax, rbx
0x18007f8dc  cmovbe  rsi, rax
0x18007f8e0  mov     rdx, rsi; unsigned __int64
0x18007f8e3  lea     rcx, [rsp+3E0h+lpszVolumePathName]; this
0x18007f8e8  call    ?Reallocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Reallocate(unsigned __int64)
0x18007f8ed  mov     rbx, [rsp+3E0h+lpszVolumePathName]
0x18007f8f2  lea     r8d, [rsi+1]; cchBufferLength
0x18007f8f6  mov     rdx, rbx; lpszVolumePathName
0x18007f8f9  mov     rcx, r15; lpszFileName
0x18007f8fc  call    cs:__imp_GetVolumePathNameW
0x18007f902  test    eax, eax
0x18007f904  jz      short loc_18007F8B4
0x18007f906  mov     rax, rdi
0x18007f909  xor     esi, esi
0x18007f90b  inc     rax
0x18007f90e  cmp     [rbx+rax*2], si
0x18007f912  jnz     short loc_18007F90B
0x18007f914  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x18007f91a  jz      short loc_18007F932
0x18007f91c  lea     rdx, psz; "\\"
0x18007f923  lea     rcx, [rsp+3E0h+lpszVolumePathName]; this
0x18007f928  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x18007f92d  mov     rbx, [rsp+3E0h+lpszVolumePathName]
0x18007f932  mov     r8d, 100h; cchBufferLength
0x18007f938  lea     rdx, [rbp+2E0h+szVolumeName]; lpszVolumeName
0x18007f93f  mov     rcx, rbx; lpszVolumeMountPoint
0x18007f942  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18007f948  test    eax, eax
0x18007f94a  jz      loc_18007FADD
0x18007f950  mov     r8d, [rsp+3E0h+cchBufferLength]; cchBufferLength
0x18007f955  mov     rdx, r13; lpszVolumeName
0x18007f958  lea     rcx, [rbp+2E0h+szVolumeName]; lpszVolumeMountPoint
0x18007f95f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18007f965  test    eax, eax
0x18007f967  jz      loc_18007FA0F
0x18007f96d  cmp     [rsp+3E0h+var_3A0], sil
0x18007f972  jz      short loc_18007F988
0x18007f974  mov     rcx, rdi
0x18007f977  inc     rcx
0x18007f97a  cmp     [r13+rcx*2+0], si
0x18007f980  jnz     short loc_18007F977
0x18007f982  mov     [r13+rcx*2-2], si
0x18007f988  test    r12, r12
0x18007f98b  jz      short loc_18007F9BE
0x18007f98d  inc     rdi
0x18007f990  cmp     [rbx+rdi*2], si
0x18007f994  jnz     short loc_18007F98D
0x18007f996  lea     rax, [rdi-1]
0x18007f99a  cmp     rax, r14
0x18007f99d  ja      short loc_18007F9B6
0x18007f99f  lea     rax, [r15-2]
0x18007f9a3  lea     rax, [rax+rdi*2]
0x18007f9a7  jmp     short loc_18007F9BA
0x18007f9a9  test    eax, eax
0x18007f9ab  jz      loc_18007FA89
0x18007f9b1  jmp     loc_18007FB56
0x18007f9b6  lea     rax, [r15+r14*2]
0x18007f9ba  mov     [r12], rax
0x18007f9be  mov     rcx, rbx; pv
0x18007f9c1  call    cs:__imp_CoTaskMemFree
0x18007f9c7  mov     [rsp+3E0h+lpszVolumePathName], rsi
0x18007f9cc  mov     [rsp+3E0h+lpszVolumePathName], rsi
0x18007f9d1  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007f9d8  mov     [rbp+2E0h+var_2F0], rax
0x18007f9dc  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007f9e0  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007f9e5  mov     rcx, [rbp+2E0h+var_40]
0x18007f9ec  xor     rcx, rsp; StackCookie
0x18007f9ef  call    __security_check_cookie
0x18007f9f4  mov     rbx, [rsp+3E0h+arg_18]
0x18007f9fc  add     rsp, 3B0h
0x18007fa03  pop     r15
0x18007fa05  pop     r14
0x18007fa07  pop     r13
0x18007fa09  pop     r12
0x18007fa0b  pop     rdi
0x18007fa0c  pop     rsi
0x18007fa0d  pop     rbp
0x18007fa0e  retn
0x18007fa0f  call    cs:__imp_GetLastError
0x18007fa15  nop
0x18007fa16  test    eax, eax
0x18007fa18  jle     short loc_18007FA22
0x18007fa1a  movzx   eax, ax
0x18007fa1d  or      eax, 80070000h
0x18007fa22  mov     edx, eax; int
0x18007fa24  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007fa28  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007fa2d  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007fa31  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007fa36  mov     ebx, eax
0x18007fa38  lea     rax, [rsp+3E0h+var_380]
0x18007fa3d  mov     [rsp+3E0h+var_390], rax
0x18007fa42  mov     [rsp+3E0h+var_3B8], 11h
0x18007fa4a  mov     [rsp+3E0h+var_3C0], 8Bh
0x18007fa52  lea     r9, aSrmgetvolumena; "SrmGetVolumeNameForPathName"
0x18007fa59  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007fa60  lea     rdx, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007fa67  lea     rcx, [rsp+3E0h+var_380]
0x18007fa6c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007fa71  nop
0x18007fa72  lea     r9, aGetvolumenamef; "GetVolumeNameForVolumeMountPoint"
0x18007fa79  mov     r8d, ebx
0x18007fa7c  mov     rdx, rax
0x18007fa7f  lea     rcx, [rbp+2E0h+var_2F0]
0x18007fa83  call    ?TranslatePathError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslatePathError(CSrmDebugInfo,long,ushort const *,...)
0x18007fa89  lea     rax, [rsp+3E0h+var_380]
0x18007fa8e  mov     [rsp+3E0h+var_390], rax
0x18007fa93  mov     [rsp+3E0h+var_3B8], 11h
0x18007fa9b  mov     [rsp+3E0h+var_3C0], 6Bh ; 'k'
0x18007faa3  lea     r9, aSrmgetvolumena; "SrmGetVolumeNameForPathName"
0x18007faaa  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007fab1  lea     rdx, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007fab8  lea     rcx, [rsp+3E0h+var_380]
0x18007fabd  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007fac2  nop
0x18007fac3  lea     r9, aGetvolumepathn; "GetVolumePathName: Filename is empty"
0x18007faca  mov     r8d, 80070057h
0x18007fad0  mov     rdx, rax
0x18007fad3  lea     rcx, [rbp+2E0h+var_2F0]
0x18007fad7  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007fadd  call    cs:__imp_GetLastError
0x18007fae3  test    eax, eax
0x18007fae5  jle     short loc_18007FAEF
0x18007fae7  movzx   eax, ax
0x18007faea  or      eax, 80070000h
0x18007faef  mov     edx, eax; int
0x18007faf1  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007faf5  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007fafa  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007fafe  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007fb03  mov     ebx, eax
0x18007fb05  lea     rax, [rsp+3E0h+var_380]
0x18007fb0a  mov     [rsp+3E0h+var_390], rax
0x18007fb0f  mov     [rsp+3E0h+var_3B8], 11h
0x18007fb17  mov     [rsp+3E0h+var_3C0], 83h
0x18007fb1f  lea     r9, aSrmgetvolumena; "SrmGetVolumeNameForPathName"
0x18007fb26  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007fb2d  lea     rdx, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007fb34  lea     rcx, [rsp+3E0h+var_380]
0x18007fb39  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007fb3e  nop
0x18007fb3f  lea     r9, aGetvolumenamef; "GetVolumeNameForVolumeMountPoint"
0x18007fb46  mov     r8d, ebx
0x18007fb49  mov     rdx, rax
0x18007fb4c  lea     rcx, [rbp+2E0h+var_2F0]
0x18007fb50  call    ?TranslatePathError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslatePathError(CSrmDebugInfo,long,ushort const *,...)
0x18007fb56  call    cs:__imp_GetLastError
0x18007fb5c  test    eax, eax
0x18007fb5e  jle     short loc_18007FB68
0x18007fb60  movzx   eax, ax
0x18007fb63  or      eax, 80070000h
0x18007fb68  mov     edx, eax; int
0x18007fb6a  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007fb6e  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007fb73  lea     rcx, [rbp+2E0h+var_2F0]; this
0x18007fb77  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007fb7c  mov     ebx, eax
0x18007fb7e  lea     rax, [rsp+3E0h+var_380]
0x18007fb83  mov     [rsp+3E0h+var_390], rax
0x18007fb88  mov     [rsp+3E0h+var_3B8], 11h
0x18007fb90  mov     [rsp+3E0h+var_3C0], 72h ; 'r'
0x18007fb98  lea     r9, aSrmgetvolumena; "SrmGetVolumeNameForPathName"
0x18007fb9f  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007fba6  lea     rdx, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007fbad  lea     rcx, [rsp+3E0h+var_380]
0x18007fbb2  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007fbb7  nop
0x18007fbb8  lea     r9, aGetvolumepathn_1; "GetVolumePathName"
0x18007fbbf  mov     r8d, ebx
0x18007fbc2  mov     rdx, rax
0x18007fbc5  lea     rcx, [rbp+2E0h+var_2F0]
0x18007fbc9  call    ?TranslatePathError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslatePathError(CSrmDebugInfo,long,ushort const *,...)
```
