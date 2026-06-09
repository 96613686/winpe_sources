# CPicturePasswordDUIHost::_CheckRoamingImageAvailable(bool *)

- ea: `0x180011534`
- end: `0x180011773`
- name: `?_CheckRoamingImageAvailable@CPicturePasswordDUIHost@@IEAAJPEA_N@Z`
- size: `575`
- prototype: `__int64 __fastcall(CPicturePasswordDUIHost *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800104d0`
- `0x180012d7c`

## callees

- `0x180002610`
- `0x180002f94`
- `0x180010fa0`
- `0x180011534`
- `0x180011b00`
- `0x180013860`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001168a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011695`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001172c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001168a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011695`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001172c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800115d5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180011649`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001170e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800115d5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180011649`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001170e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001167a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001167a`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::_CheckRoamingImageAvailable(CPicturePasswordDUIHost *this, bool *a2)
{
  int FilePath; // ebx
  HANDLE FirstFileW; // rax
  HANDLE v5; // rsi
  HANDLE v6; // rax
  HANDLE hFindFile; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR v9; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+30h] [rbp-D0h]
  __int64 v11; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h]
  __int64 v14; // [rsp+50h] [rbp-B0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  struct _WIN32_FIND_DATAW v16; // [rsp+2B0h] [rbp+1B0h] BYREF

  *a2 = 1;
  lpFileName = 0;
  v13 = 0;
  v14 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFileName);
  v13 = -1;
  v14 = -1;
  FilePath = CPicturePasswordDUIHost::s_GetFilePath(L"Cloud.jpg", (unsigned __int16 **)&lpFileName);
  if ( FilePath >= 0 )
  {
    hFindFile = 0;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    FilePath = ResultFromWin32Handle(FirstFileW, &hFindFile);
    if ( FilePath >= 0 )
    {
      v9 = 0;
      v10 = 0;
      v11 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9);
      v10 = -1;
      v11 = -1;
      FilePath = CPicturePasswordDUIHost::s_GetFilePath(L"Local.jpg", (unsigned __int16 **)&v9);
      if ( FilePath >= 0 )
      {
        memset_0(&v16, 0, sizeof(v16));
        v5 = FindFirstFileW(v9, &v16);
        if ( v5 != (HANDLE)-1LL )
        {
          if ( FindFileData.nFileSizeHigh == v16.nFileSizeHigh
            && FindFileData.nFileSizeLow == v16.nFileSizeLow
            && !CompareFileTime(&FindFileData.ftLastWriteTime, &v16.ftLastWriteTime) )
          {
            *a2 = 0;
          }
          FindClose(v5);
        }
      }
      FindClose(hFindFile);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9);
      if ( FilePath >= 0 && *a2 )
      {
        v9 = 0;
        v10 = 0;
        v11 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9);
        v10 = -1;
        v11 = -1;
        FilePath = CPicturePasswordDUIHost::s_GetFilePath(L"Sanitized.jpg", (unsigned __int16 **)&v9);
        if ( FilePath >= 0 )
        {
          hFindFile = 0;
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          v6 = FindFirstFileW(v9, &FindFileData);
          FilePath = ResultFromWin32Handle(v6, &hFindFile);
          if ( FilePath >= 0 )
            FindClose(hFindFile);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9);
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFileName);
  return (unsigned int)FilePath;
}

```

## disassembly

```asm
0x180011534  mov     [rsp-8+arg_0], rbx
0x180011539  mov     [rsp-8+arg_10], rsi
0x18001153e  push    rbp
0x18001153f  push    rdi
0x180011540  push    r12
0x180011542  push    r14
0x180011544  push    r15
0x180011546  lea     rbp, [rsp-410h]
0x18001154e  sub     rsp, 510h
0x180011555  mov     rax, cs:__security_cookie
0x18001155c  xor     rax, rsp
0x18001155f  mov     [rbp+430h+var_30], rax
0x180011566  xor     r14d, r14d
0x180011569  mov     byte ptr [rdx], 1
0x18001156c  lea     rcx, [rsp+530h+lpFileName]
0x180011571  mov     [rsp+530h+lpFileName], r14
0x180011576  mov     [rsp+530h+var_4E8], r14
0x18001157b  mov     rdi, rdx
0x18001157e  mov     [rsp+530h+var_4E0], r14
0x180011583  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180011588  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001158c  lea     rdx, [rsp+530h+lpFileName]; unsigned __int16 **
0x180011591  lea     rcx, aCloudJpg; "Cloud.jpg"
0x180011598  mov     [rsp+530h+var_4E8], r15
0x18001159d  mov     [rsp+530h+var_4E0], r15
0x1800115a2  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x1800115a7  mov     ebx, eax
0x1800115a9  test    eax, eax
0x1800115ab  js      loc_18001173C
0x1800115b1  mov     r12d, 250h
0x1800115b7  mov     [rsp+530h+hFindFile], r14
0x1800115bc  mov     r8d, r12d; Size
0x1800115bf  lea     rcx, [rsp+530h+FindFileData]; void *
0x1800115c4  xor     edx, edx; Val
0x1800115c6  call    memset_0
0x1800115cb  mov     rcx, [rsp+530h+lpFileName]; lpFileName
0x1800115d0  lea     rdx, [rsp+530h+FindFileData]; lpFindFileData
0x1800115d5  call    cs:__imp_FindFirstFileW
0x1800115db  mov     rcx, rax; void *
0x1800115de  lea     rdx, [rsp+530h+hFindFile]; void **
0x1800115e3  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1800115e8  mov     ebx, eax
0x1800115ea  test    eax, eax
0x1800115ec  js      loc_18001173C
0x1800115f2  lea     rcx, [rsp+530h+var_508]
0x1800115f7  mov     [rsp+530h+var_508], r14
0x1800115fc  mov     [rsp+530h+var_500], r14
0x180011601  mov     [rsp+530h+var_4F8], r14
0x180011606  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001160b  lea     rdx, [rsp+530h+var_508]; unsigned __int16 **
0x180011610  mov     [rsp+530h+var_500], r15
0x180011615  lea     rcx, aLocalJpg; "Local.jpg"
0x18001161c  mov     [rsp+530h+var_4F8], r15
0x180011621  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x180011626  mov     ebx, eax
0x180011628  test    eax, eax
0x18001162a  js      short loc_180011690
0x18001162c  mov     r8d, r12d; Size
0x18001162f  lea     rcx, [rbp+430h+var_280]; void *
0x180011636  xor     edx, edx; Val
0x180011638  call    memset_0
0x18001163d  mov     rcx, [rsp+530h+var_508]; lpFileName
0x180011642  lea     rdx, [rbp+430h+var_280]; lpFindFileData
0x180011649  call    cs:__imp_FindFirstFileW
0x18001164f  mov     rsi, rax
0x180011652  cmp     rax, r15
0x180011655  jz      short loc_180011690
0x180011657  mov     ecx, [rbp+430h+var_280.nFileSizeHigh]
0x18001165d  cmp     [rsp+530h+FindFileData.nFileSizeHigh], ecx
0x180011661  jnz     short loc_180011687
0x180011663  mov     ecx, [rbp+430h+var_280.nFileSizeLow]
0x180011669  cmp     [rbp+430h+FindFileData.nFileSizeLow], ecx
0x18001166c  jnz     short loc_180011687
0x18001166e  lea     rdx, [rbp+430h+var_280.ftLastWriteTime]; lpFileTime2
0x180011675  lea     rcx, [rsp+530h+FindFileData.ftLastWriteTime]; lpFileTime1
0x18001167a  call    cs:__imp_CompareFileTime
0x180011680  test    eax, eax
0x180011682  jnz     short loc_180011687
0x180011684  mov     [rdi], r14b
0x180011687  mov     rcx, rsi; hFindFile
0x18001168a  call    cs:__imp_FindClose
0x180011690  mov     rcx, [rsp+530h+hFindFile]; hFindFile
0x180011695  call    cs:__imp_FindClose
0x18001169b  lea     rcx, [rsp+530h+var_508]
0x1800116a0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800116a5  test    ebx, ebx
0x1800116a7  js      loc_18001173C
0x1800116ad  cmp     byte ptr [rdi], 1
0x1800116b0  jnz     loc_18001173C
0x1800116b6  lea     rcx, [rsp+530h+var_508]
0x1800116bb  mov     [rsp+530h+var_508], r14
0x1800116c0  mov     [rsp+530h+var_500], r14
0x1800116c5  mov     [rsp+530h+var_4F8], r14
0x1800116ca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800116cf  lea     rdx, [rsp+530h+var_508]; unsigned __int16 **
0x1800116d4  mov     [rsp+530h+var_500], r15
0x1800116d9  lea     rcx, aSanitizedJpg; "Sanitized.jpg"
0x1800116e0  mov     [rsp+530h+var_4F8], r15
0x1800116e5  call    ?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z; CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)
0x1800116ea  mov     ebx, eax
0x1800116ec  test    eax, eax
0x1800116ee  js      short loc_180011732
0x1800116f0  mov     r8, r12; Size
0x1800116f3  mov     [rsp+530h+hFindFile], r14
0x1800116f8  xor     edx, edx; Val
0x1800116fa  lea     rcx, [rsp+530h+FindFileData]; void *
0x1800116ff  call    memset_0
0x180011704  mov     rcx, [rsp+530h+var_508]; lpFileName
0x180011709  lea     rdx, [rsp+530h+FindFileData]; lpFindFileData
0x18001170e  call    cs:__imp_FindFirstFileW
0x180011714  mov     rcx, rax; void *
0x180011717  lea     rdx, [rsp+530h+hFindFile]; void **
0x18001171c  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180011721  mov     ebx, eax
0x180011723  test    eax, eax
0x180011725  js      short loc_180011732
0x180011727  mov     rcx, [rsp+530h+hFindFile]; hFindFile
0x18001172c  call    cs:__imp_FindClose
0x180011732  lea     rcx, [rsp+530h+var_508]
0x180011737  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001173c  lea     rcx, [rsp+530h+lpFileName]
0x180011741  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180011746  mov     eax, ebx
0x180011748  mov     rcx, [rbp+430h+var_30]
0x18001174f  xor     rcx, rsp; StackCookie
0x180011752  call    __security_check_cookie
0x180011757  lea     r11, [rsp+530h+var_20]
0x18001175f  mov     rbx, [r11+30h]
0x180011763  mov     rsi, [r11+40h]
0x180011767  mov     rsp, r11
0x18001176a  pop     r15
0x18001176c  pop     r14
0x18001176e  pop     r12
0x180011770  pop     rdi
0x180011771  pop     rbp
0x180011772  retn
```
