# AreTestKeysAllowedInternal(int &)

- ea: `0x18000b9d0`
- end: `0x18000bd63`
- name: `?AreTestKeysAllowedInternal@@YAJAEAH@Z`
- size: `915`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000bd6c`
- `0x180010f54`

## callees

- `0x1800029a0`
- `0x180003950`
- `0x180009c1c`
- `0x18000b67c`
- `0x18000b8a4`
- `0x18000b9d0`
- `0x18000bf00`
- `0x18000c080`
- `0x18000c0b4`
- `0x18000c0e4`
- `0x18000d158`
- `0x180012480`
- `0x180015dfc`
- `0x1800165a4`
- `0x180032250`
- `0x180042630`
- `0x180042a24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000baa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000baa5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bb42`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bb42`

## string_xrefs

- `0x18000bab4`: `AlternateTestCabPath`
- `0x18000ba97`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18000bc88`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AreTestKeysAllowedInternal(int *a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  int SusBaseDirectoryW; // ebx
  __int64 v6; // rdx
  wchar_t **v8; // r9
  wchar_t **v9; // r9
  int LastErrorFailHr; // esi
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  wil::details *v13; // rcx
  int FileSize; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  COutputMemoryFile *v20; // rbx
  int v21; // eax
  COutputMemoryFile *v22; // rdi
  int phkResult; // [rsp+28h] [rbp-E0h]
  int *phkResulta; // [rsp+28h] [rbp-E0h]
  unsigned __int64 *phkResultb; // [rsp+28h] [rbp-E0h]
  int phkResultc; // [rsp+28h] [rbp-E0h]
  int phkResultd; // [rsp+28h] [rbp-E0h]
  int *v28; // [rsp+30h] [rbp-D8h]
  __int64 v29; // [rsp+48h] [rbp-C0h]
  __int64 v30; // [rsp+58h] [rbp-B0h]
  COutputMemoryFile *v31; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  WCHAR FileName[264]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v34[264]; // [rsp+288h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C0h] [rbp+3B8h]

  SusBaseDirectoryW = GetSusBaseDirectoryW(v34, a2, L"\\", a4);
  if ( SusBaseDirectoryW < 0 )
  {
    v6 = 115;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
      (const char *)(unsigned int)SusBaseDirectoryW,
      phkResult);
    return (unsigned int)SusBaseDirectoryW;
  }
  SusBaseDirectoryW = StringCchCopyExW(FileName, 0x104u, v34, 0, 0, 0x100u);
  if ( SusBaseDirectoryW < 0 )
  {
    v6 = 117;
    goto LABEL_3;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
          0,
          0x20019u,
          &hKey) )
  {
    if ( (int)SafeRegQueryStringValueCch(hKey, L"AlternateTestCabPath", FileName, (int)v8, phkResulta, v28) < 0 )
      StringCchCopyExW(FileName, 0x104u, v34, 0, 0, 0x100u);
    LastErrorFailHr = StringCchCatExW(FileName, 0x104u, L"\\", v9, phkResultb, 0x100u);
    if ( LastErrorFailHr < 0 )
    {
      v11 = 133;
LABEL_13:
      v12 = (unsigned int)LastErrorFailHr;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
        (const char *)v12,
        (int)phkResulta);
      goto LABEL_19;
    }
  }
  LastErrorFailHr = StringCchCatExW(FileName, 0x104u, L"autest.cab", v8, (unsigned __int64 *)phkResulta, 0x100u);
  if ( LastErrorFailHr < 0 )
  {
    v11 = 137;
    goto LABEL_13;
  }
  if ( GetFileAttributesW(FileName) != -1
    || (LastErrorFailHr = wil::details::GetLastErrorFailHr(v13), LastErrorFailHr >= 0) )
  {
    v31 = 0;
    FileSize = SusGetFileSize(FileName, (unsigned __int64 *)&v31);
    if ( FileSize >= 0 )
    {
      if ( (unsigned __int64)v31 <= 0x4E20 )
      {
        LODWORD(phkResulta) = 0;
        v16 = VerifyFileTrustImp(FileName, v15, 0);
        LastErrorFailHr = v16;
        if ( v16 >= 0 )
        {
          v31 = 0;
          v19 = DecompressCabFileInternal(v18, v17, (__int64)FileName, 0, 0, &off_180075140, 1u, 0, v29, 0, v30, &v31);
          LastErrorFailHr = v19;
          v20 = v31;
          if ( v19 >= 0 )
          {
            if ( v31 && *((_DWORD *)v31 + 6) == 1 )
            {
              *((_QWORD *)v31 + 4) = *((_QWORD *)v31 + 1);
              v31 = 0;
              v21 = CSusListIterator<COutputMemoryFile>::Remove(v20, &v31);
              LastErrorFailHr = v21;
              v22 = v31;
              if ( v21 >= 0 )
              {
                *a1 = IsValidAUTestCabFileText(
                        *(_DWORD *)(*((_QWORD *)v31 + 2) + 20LL),
                        *(const char **)(*((_QWORD *)v31 + 2) + 8LL));
                LastErrorFailHr = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB0,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
                  (const char *)(unsigned int)v21,
                  phkResultc);
              }
              if ( v22 )
              {
                COutputMemoryFile::~COutputMemoryFile(v22);
                operator delete(v22, (const struct std::nothrow_t *)0x120);
              }
            }
            else
            {
              LastErrorFailHr = -2145120257;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x608,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
              (const char *)(unsigned int)v19,
              phkResultc);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA6,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
              (const char *)(unsigned int)LastErrorFailHr,
              phkResultd);
          }
          if ( v20 )
          {
            CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v20);
            operator delete(v20, (const struct std::nothrow_t *)0x28);
          }
          goto LABEL_19;
        }
        v12 = (unsigned int)v16;
        v11 = 157;
        goto LABEL_25;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
        (const char *)(unsigned int)FileSize,
        (int)phkResulta);
    }
    LastErrorFailHr = -2145120257;
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)LastErrorFailHr;
}

```

## disassembly

```asm
0x18000b9d0  mov     rax, rsp
0x18000b9d3  mov     [rax+10h], rbx
0x18000b9d7  mov     [rax+18h], rsi
0x18000b9db  mov     [rax+20h], rdi
0x18000b9df  push    rbp
0x18000b9e0  push    r12
0x18000b9e2  push    r14
0x18000b9e4  lea     rbp, [rax-3B8h]
0x18000b9eb  sub     rsp, 4A0h
0x18000b9f2  mov     rax, cs:__security_cookie
0x18000b9f9  xor     rax, rsp
0x18000b9fc  mov     [rbp+3B0h+var_20], rax
0x18000ba03  mov     r14, rcx
0x18000ba06  lea     r8, SubBlock; "\\"
0x18000ba0d  lea     rcx, [rbp+3B0h+var_230]; wchar_t *
0x18000ba14  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x18000ba19  mov     ebx, eax
0x18000ba1b  test    eax, eax
0x18000ba1d  jns     short loc_18000BA41
0x18000ba1f  mov     edx, 73h ; 's'; void *
0x18000ba24  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000ba2b  mov     r9d, ebx; char *
0x18000ba2e  mov     rcx, [rbp+3B8h]; this
0x18000ba35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba3a  mov     eax, ebx
0x18000ba3c  jmp     loc_18000BBA6
0x18000ba41  mov     edi, 100h
0x18000ba46  mov     dword ptr [rsp+4B0h+var_488], edi; int *
0x18000ba4a  mov     [rsp+4B0h+phkResult], 0; unsigned __int64 *
0x18000ba53  xor     r9d, r9d; wchar_t **
0x18000ba56  lea     r8, [rbp+3B0h+var_230]; wchar_t *
0x18000ba5d  lea     r12d, [rdi+4]
0x18000ba61  mov     edx, r12d; unsigned __int64
0x18000ba64  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x18000ba69  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000ba6e  mov     ebx, eax
0x18000ba70  test    eax, eax
0x18000ba72  jns     short loc_18000BA7B
0x18000ba74  mov     edx, 75h ; 'u'
0x18000ba79  jmp     short loc_18000BA24
0x18000ba7b  mov     [rsp+4B0h+hKey], 0
0x18000ba84  lea     rax, [rsp+4B0h+hKey]
0x18000ba89  mov     [rsp+4B0h+phkResult], rax; int
0x18000ba8e  mov     r9d, 20019h; samDesired
0x18000ba94  xor     r8d, r8d; ulOptions
0x18000ba97  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ba9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000baa5  call    cs:__imp_RegOpenKeyExW
0x18000baab  test    eax, eax
0x18000baad  jnz     short loc_18000BB12
0x18000baaf  lea     r8, [rsp+4B0h+FileName]; wchar_t *
0x18000bab4  lea     rdx, aAlternatetestc; "AlternateTestCabPath"
0x18000babb  mov     rcx, [rsp+4B0h+hKey]; HKEY
0x18000bac0  call    ?SafeRegQueryStringValueCch@@YAJPEAUHKEY__@@PEB_WPEA_WHPEAH3@Z; SafeRegQueryStringValueCch(HKEY__ *,wchar_t const *,wchar_t *,int,int *,int *)
0x18000bac5  test    eax, eax
0x18000bac7  jns     short loc_18000BAED
0x18000bac9  mov     dword ptr [rsp+4B0h+var_488], edi; unsigned int
0x18000bacd  mov     [rsp+4B0h+phkResult], 0; unsigned __int64 *
0x18000bad6  xor     r9d, r9d; wchar_t **
0x18000bad9  lea     r8, [rbp+3B0h+var_230]; wchar_t *
0x18000bae0  mov     rdx, r12; unsigned __int64
0x18000bae3  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x18000bae8  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000baed  mov     dword ptr [rsp+4B0h+var_488], edi; unsigned int
0x18000baf1  lea     r8, SubBlock; "\\"
0x18000baf8  mov     rdx, r12; unsigned __int64
0x18000bafb  lea     rcx, [rsp+4B0h+FileName]; wchar_t *
0x18000bb00  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000bb05  mov     esi, eax
0x18000bb07  test    eax, eax
0x18000bb09  jns     short loc_18000BB12
0x18000bb0b  mov     edx, 85h
0x18000bb10  jmp     short loc_18000BB35
0x18000bb12  mov     dword ptr [rsp+4B0h+var_488], edi; unsigned int
0x18000bb16  lea     r8, aAutestCab; "autest.cab"
0x18000bb1d  mov     rdx, r12; unsigned __int64
0x18000bb20  lea     rcx, [rsp+4B0h+FileName]; wchar_t *
0x18000bb25  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000bb2a  mov     esi, eax
0x18000bb2c  test    eax, eax
0x18000bb2e  jns     short loc_18000BB3D
0x18000bb30  mov     edx, 89h
0x18000bb35  mov     r9d, esi
0x18000bb38  jmp     loc_18000BC12
0x18000bb3d  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x18000bb42  call    cs:__imp_GetFileAttributesW
0x18000bb48  cmp     eax, 0FFFFFFFFh
0x18000bb4b  jnz     short loc_18000BB58
0x18000bb4d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bb52  mov     esi, eax
0x18000bb54  test    eax, eax
0x18000bb56  js      short loc_18000BB94
0x18000bb58  mov     [rsp+4B0h+var_450], 0
0x18000bb61  lea     rdx, [rsp+4B0h+var_450]; unsigned __int64 *
0x18000bb66  lea     rcx, [rsp+4B0h+FileName]; wchar_t *
0x18000bb6b  call    ?SusGetFileSize@@YAJPEB_WPEA_K@Z; SusGetFileSize(wchar_t const *,unsigned __int64 *)
0x18000bb70  mov     rcx, [rbp+3B8h]; this
0x18000bb77  test    eax, eax
0x18000bb79  jns     short loc_18000BBD2
0x18000bb7b  mov     r9d, eax; char *
0x18000bb7e  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000bb85  mov     edx, 91h; void *
0x18000bb8a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bb8f  mov     esi, 80240FFFh
0x18000bb94  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000bb99  test    rcx, rcx
0x18000bb9c  jz      short loc_18000BBA4
0x18000bb9e  call    cs:__imp_RegCloseKey
0x18000bba4  mov     eax, esi
0x18000bba6  mov     rcx, [rbp+3B0h+var_20]
0x18000bbad  xor     rcx, rsp; StackCookie
0x18000bbb0  call    __security_check_cookie
0x18000bbb5  lea     r11, [rsp+4B0h+var_10]
0x18000bbbd  mov     rbx, [r11+28h]
0x18000bbc1  mov     rsi, [r11+30h]
0x18000bbc5  mov     rdi, [r11+38h]
0x18000bbc9  mov     rsp, r11
0x18000bbcc  pop     r14
0x18000bbce  pop     r12
0x18000bbd0  pop     rbp
0x18000bbd1  retn
0x18000bbd2  cmp     [rsp+4B0h+var_450], 4E20h
0x18000bbdb  ja      short loc_18000BB8F
0x18000bbdd  mov     [rsp+4B0h+var_480], 3
0x18000bbe5  mov     edi, 1
0x18000bbea  mov     dword ptr [rsp+4B0h+var_488], edi
0x18000bbee  mov     [rsp+4B0h+phkResult], 0; int
0x18000bbf7  xor     r8d, r8d
0x18000bbfa  lea     rcx, [rsp+4B0h+FileName]
0x18000bbff  call    ?VerifyFileTrustImp@@YAJPEB_WW4_AcceptTrustedPublishersAction@@HPEAUCERT_HASH_BLOB@@0HW4_SignatureStrengthPolicy@@PEAUDualSubCAIdentity@@@Z; VerifyFileTrustImp(wchar_t const *,_AcceptTrustedPublishersAction,int,CERT_HASH_BLOB *,wchar_t const *,int,_SignatureStrengthPolicy,DualSubCAIdentity *)
0x18000bc04  mov     esi, eax
0x18000bc06  test    eax, eax
0x18000bc08  jns     short loc_18000BC2A
0x18000bc0a  mov     r9d, eax; char *
0x18000bc0d  mov     edx, 9Dh; void *
0x18000bc12  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000bc19  mov     rcx, [rbp+3B8h]; this
0x18000bc20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc25  jmp     loc_18000BB94
0x18000bc2a  mov     [rsp+4B0h+var_450], 0
0x18000bc33  lea     rax, [rsp+4B0h+var_450]
0x18000bc38  mov     [rsp+4B0h+var_458], rax
0x18000bc3d  mov     [rsp+4B0h+var_468], 0
0x18000bc45  mov     [rsp+4B0h+var_478], 0
0x18000bc4d  mov     [rsp+4B0h+var_480], edi
0x18000bc51  lea     rax, off_180075140; "autest.txt"
0x18000bc58  mov     [rsp+4B0h+var_488], rax
0x18000bc5d  mov     [rsp+4B0h+phkResult], 0; int
0x18000bc66  xor     r9d, r9d
0x18000bc69  lea     r8, [rsp+4B0h+FileName]
0x18000bc6e  call    DecompressCabFileInternal
0x18000bc73  mov     esi, eax
0x18000bc75  mov     rbx, [rsp+4B0h+var_450]
0x18000bc7a  test    eax, eax
0x18000bc7c  jns     short loc_18000BCB9
0x18000bc7e  mov     rcx, [rbp+3B8h]; this
0x18000bc85  mov     r9d, eax; char *
0x18000bc88  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x18000bc8f  mov     edx, 608h; void *
0x18000bc94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc99  mov     rcx, [rbp+3B8h]; this
0x18000bca0  mov     r9d, esi; char *
0x18000bca3  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000bcaa  mov     edx, 0A6h; void *
0x18000bcaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcb4  jmp     loc_18000BD3F
0x18000bcb9  test    rbx, rbx
0x18000bcbc  jz      short loc_18000BD3A
0x18000bcbe  cmp     [rbx+18h], edi
0x18000bcc1  jnz     short loc_18000BD3A
0x18000bcc3  mov     rax, [rbx+8]
0x18000bcc7  mov     [rbx+20h], rax
0x18000bccb  mov     [rsp+4B0h+var_450], 0
0x18000bcd4  lea     rdx, [rsp+4B0h+var_450]
0x18000bcd9  mov     rcx, rbx
0x18000bcdc  call    ?Remove@?$CSusListIterator@VCOutputMemoryFile@@@@QEAAJPEAPEAVCOutputMemoryFile@@@Z; CSusListIterator<COutputMemoryFile>::Remove(COutputMemoryFile * *)
0x18000bce1  mov     esi, eax
0x18000bce3  mov     rdi, [rsp+4B0h+var_450]
0x18000bce8  test    eax, eax
0x18000bcea  jns     short loc_18000BD09
0x18000bcec  mov     rcx, [rbp+3B8h]; this
0x18000bcf3  mov     r9d, eax; char *
0x18000bcf6  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000bcfd  mov     edx, 0B0h; void *
0x18000bd02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd07  jmp     short loc_18000BD1E
0x18000bd09  mov     rcx, [rdi+10h]
0x18000bd0d  mov     rdx, [rcx+8]; char *
0x18000bd11  mov     ecx, [rcx+14h]; unsigned int
0x18000bd14  call    ?IsValidAUTestCabFileText@@YAHKPEBD@Z; IsValidAUTestCabFileText(ulong,char const *)
0x18000bd19  mov     [r14], eax
0x18000bd1c  xor     esi, esi
0x18000bd1e  test    rdi, rdi
0x18000bd21  jz      short loc_18000BD3F
0x18000bd23  mov     rcx, rdi; this
0x18000bd26  call    ??1COutputMemoryFile@@QEAA@XZ; COutputMemoryFile::~COutputMemoryFile(void)
0x18000bd2b  mov     edx, 120h; struct std::nothrow_t *
0x18000bd30  mov     rcx, rdi; void *
0x18000bd33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bd38  jmp     short loc_18000BD3F
0x18000bd3a  mov     esi, 80240FFFh
0x18000bd3f  test    rbx, rbx
0x18000bd42  jz      loc_18000BB94
0x18000bd48  mov     rcx, rbx
0x18000bd4b  call    ??1?$CSusListIterator@VCOutputMemoryFile@@@@QEAA@XZ; CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(void)
0x18000bd50  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000bd55  mov     rcx, rbx; void *
0x18000bd58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bd5d  jmp     loc_18000BB94
```
