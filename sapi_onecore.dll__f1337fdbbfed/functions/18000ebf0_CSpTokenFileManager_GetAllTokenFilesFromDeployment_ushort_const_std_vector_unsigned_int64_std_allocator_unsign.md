# CSpTokenFileManager::GetAllTokenFilesFromDeployment(ushort const *,std::vector<unsigned __int64,std::allocator<unsigned __int64>> &)

- ea: `0x18000ebf0`
- end: `0x18000f070`
- name: `?GetAllTokenFilesFromDeployment@CSpTokenFileManager@@AEAAJPEBGAEAV?$vector@_KV?$allocator@_K@std@@@std@@@Z`
- size: `1152`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f96c`

## callees

- `0x18000d6d8`
- `0x18000d75c`
- `0x18000ebf0`
- `0x18000f080`
- `0x18000f310`
- `0x180026508`
- `0x180079e30`
- `0x18007aae4`
- `0x1800fe45c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__waccess` at `0x18000ed1a`
- `api-ms-win-crt-private-l1-1-0!_o__waccess` at `0x18000eea7`
- `api-ms-win-crt-private-l1-1-0!_o__waccess` at `0x18000ed1a`
- `api-ms-win-crt-private-l1-1-0!_o__waccess` at `0x18000eea7`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000ee90`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000ee90`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000efe0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000efe0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000ec6c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000ed76`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000ec6c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000ed76`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f02a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f065`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f02a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f065`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000edfe`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000ef62`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000edfe`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000ef62`

## string_xrefs

- `0x18000eef3`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x18000ef09`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x18000ef34`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x18000ef7f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x18000efed`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x18000f03f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x18000ec8a`: `Tokens*.xml`
- `0x18000edcc`: `Tokens*.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSpTokenFileManager::GetAllTokenFilesFromDeployment(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  char *FirstFileW; // r14
  __int64 v10; // r9
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  char *v16; // rsi
  int v18; // eax
  unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rcx
  unsigned int v21; // ebx
  unsigned __int16 *v22; // rdx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD); // rbx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r9
  wil::details::in1diag3 *v28; // rcx
  __time64_t *v29; // rdx
  _DWORD *v30; // rax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v34; // [rsp+34h] [rbp-CCh] BYREF
  char *v35; // [rsp+38h] [rbp-C8h] BYREF
  __time64_t st_mtime; // [rsp+40h] [rbp-C0h] BYREF
  char *v37; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  struct _WIN32_FIND_DATAW v40; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v41[264]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR FileName[264]; // [rsp+720h] [rbp+620h] BYREF
  WCHAR v43[264]; // [rsp+930h] [rbp+830h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B88h] [rbp+A88h]

  v6 = StringCchPrintfW(FileName, 0x105u, L"%s\\*.*", a2);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
      (const char *)(unsigned int)v6,
      v31);
    return v7;
  }
  else
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
    v35 = FirstFileW;
    v34 = 0;
    if ( FirstFileW == (char *)-1LL )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
      return 2147766317LL;
    }
    else
    {
      while ( 1 )
      {
        v10 = 46;
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          v8 = FindFileData.cFileName[0];
          v11 = 46 - FindFileData.cFileName[0];
          if ( FindFileData.cFileName[0] == 46 )
            v11 = -FindFileData.cFileName[1];
          if ( v11 )
          {
            v12 = 46 - FindFileData.cFileName[0];
            if ( FindFileData.cFileName[0] == 46 )
            {
              v12 = 46 - FindFileData.cFileName[1];
              if ( FindFileData.cFileName[1] == 46 )
                v12 = -FindFileData.cFileName[2];
            }
            if ( v12 )
              break;
          }
        }
LABEL_19:
        if ( (*(int (__fastcall **)(_QWORD, unsigned int *, __int64, __int64))(**(_QWORD **)(a1 + 16) + 56LL))(
               *(_QWORD *)(a1 + 16),
               &v34,
               v8,
               v10) < 0
          || v34 >= 0x1F4
          || !FindNextFileW(FirstFileW, &FindFileData) )
        {
          if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            FindClose(FirstFileW);
          return 0;
        }
      }
      v13 = StringCchPrintfW(v41, 0x105u, L"%s\\%s", a2);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( (unsigned int)_o__waccess(v41, 0) )
          goto LABEL_19;
        v15 = StringCchPrintfW(v43, 0x105u, L"%s\\%s", v41);
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC6,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
            (const char *)(unsigned int)v15,
            (int)L"Tokens*.xml");
          goto LABEL_19;
        }
        memset_0(&v40, 0, sizeof(v40));
        v16 = (char *)FindFirstFileW(v43, &v40);
        v37 = v16;
        v33 = 0;
        if ( v16 == (char *)-1LL )
          goto LABEL_19;
        while ( 1 )
        {
          if ( (v40.dwFileAttributes & 0x10) == 0 )
          {
            v18 = StringCchPrintfW(&FullPath, 0x105u, L"%s\\%s", v41);
            v21 = v18;
            if ( v18 < 0 )
            {
              v26 = 273;
LABEL_31:
              v27 = (unsigned int)v18;
              v28 = retaddr;
LABEL_32:
              wil::details::in1diag3::Return_Hr(
                v28,
                (void *)v26,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
                (const char *)v27,
                (int)v40.cFileName);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD2,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
                (const char *)v21,
                v32);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
              goto LABEL_19;
            }
            CModelDownloadComponent::GetLatestVersionForThisEngine(v20, v19);
            if ( _wstat64i32(&::FileName, &Stat) )
            {
              v30 = (_DWORD *)_o__errno();
              v28 = retaddr;
              if ( *v30 == 2 )
              {
                v21 = -2147023728;
                v26 = 278;
                v27 = 2147943568LL;
              }
              else
              {
                v21 = -2147418113;
                v26 = 279;
                v27 = 2147549183LL;
              }
              goto LABEL_32;
            }
            if ( !(unsigned int)_o__waccess(&::FileName, 0) )
            {
              v23 = *(_QWORD *)(a1 + 16);
              v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 104LL);
              v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (unsigned __int16 (*)[261])v22);
              v18 = v24(v23, *(_QWORD *)(v25 + 24));
              v21 = v18;
              if ( v18 < 0 )
              {
                v26 = 285;
                goto LABEL_31;
              }
              st_mtime = Stat.st_mtime;
              v29 = *(__time64_t **)(a3 + 8);
              if ( v29 == *(__time64_t **)(a3 + 16) )
              {
                std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(
                  a3,
                  v29,
                  &st_mtime);
              }
              else
              {
                *v29 = Stat.st_mtime;
                *(_QWORD *)(a3 + 8) += 8LL;
              }
            }
          }
          if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 16) + 56LL))(
                 *(_QWORD *)(a1 + 16),
                 &v33) < 0
            || v33 >= 0x1F4
            || !FindNextFileW(v16, &v40) )
          {
            if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              FindClose(v16);
            goto LABEL_19;
          }
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
        (const char *)(unsigned int)v13,
        (int)FindFileData.cFileName);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
      return v14;
    }
  }
}

```

## disassembly

```asm
0x18000ebf0  mov     [rsp-8+arg_18], rbx
0x18000ebf5  push    rbp
0x18000ebf6  push    rsi
0x18000ebf7  push    rdi
0x18000ebf8  push    r12
0x18000ebfa  push    r13
0x18000ebfc  push    r14
0x18000ebfe  push    r15
0x18000ec00  lea     rbp, [rsp-0A50h]
0x18000ec08  sub     rsp, 0B50h
0x18000ec0f  mov     rax, cs:__security_cookie
0x18000ec16  xor     rax, rsp
0x18000ec19  mov     [rbp+0A80h+var_40], rax
0x18000ec20  mov     r13, r8
0x18000ec23  mov     r12, rdx
0x18000ec26  mov     r15, rcx
0x18000ec29  mov     r9, rdx
0x18000ec2c  lea     r8, aS; "%s\\*.*"
0x18000ec33  mov     edx, 105h; unsigned __int64
0x18000ec38  lea     rcx, [rbp+0A80h+FileName]; unsigned __int16 *
0x18000ec3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ec44  mov     ebx, eax
0x18000ec46  test    eax, eax
0x18000ec48  js      loc_18000EF75
0x18000ec4e  xor     edx, edx; Val
0x18000ec50  mov     r8d, 250h; Size
0x18000ec56  lea     rcx, [rsp+0B80h+FindFileData]; void *
0x18000ec5b  call    memset_0
0x18000ec60  lea     rdx, [rsp+0B80h+FindFileData]; lpFindFileData
0x18000ec65  lea     rcx, [rbp+0A80h+FileName]; lpFileName
0x18000ec6c  call    cs:__imp_FindFirstFileW
0x18000ec72  mov     r14, rax
0x18000ec75  mov     [rsp+0B80h+var_B48], rax
0x18000ec7a  xor     edi, edi
0x18000ec7c  mov     [rsp+0B80h+var_B4C], edi
0x18000ec80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ec84  jz      loc_18000EF97
0x18000ec8a  lea     rsi, aTokensXml; "Tokens*.xml"
0x18000ec91  mov     r9d, 2Eh ; '.'
0x18000ec97  test    byte ptr [rsp+0B80h+FindFileData.dwFileAttributes], 10h
0x18000ec9c  jz      loc_18000EDD3
0x18000eca2  movzx   ecx, r9w
0x18000eca6  movzx   r8d, [rbp+0A80h+FindFileData.cFileName]
0x18000ecab  movzx   edx, [rbp+0A80h+FindFileData.cFileName+2]
0x18000ecaf  sub     ecx, r8d
0x18000ecb2  jnz     short loc_18000ECB9
0x18000ecb4  movzx   ecx, di
0x18000ecb7  sub     ecx, edx
0x18000ecb9  test    ecx, ecx
0x18000ecbb  jz      loc_18000EDD3
0x18000ecc1  movzx   eax, r9w
0x18000ecc5  sub     eax, r8d
0x18000ecc8  jnz     short loc_18000ECDB
0x18000ecca  movzx   eax, r9w
0x18000ecce  sub     eax, edx
0x18000ecd0  jnz     short loc_18000ECDB
0x18000ecd2  movzx   eax, di
0x18000ecd5  movzx   ecx, [rbp+0A80h+FindFileData.cFileName+4]
0x18000ecd9  sub     eax, ecx
0x18000ecdb  test    eax, eax
0x18000ecdd  jz      loc_18000EDD3
0x18000ece3  lea     rax, [rbp+0A80h+FindFileData.cFileName]
0x18000ece7  mov     qword ptr [rsp+0B80h+var_B60], rax; int
0x18000ecec  mov     r9, r12
0x18000ecef  lea     r8, aSS; "%s\\%s"
0x18000ecf6  mov     edx, 105h; unsigned __int64
0x18000ecfb  lea     rcx, [rbp+0A80h+var_670]; unsigned __int16 *
0x18000ed02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ed07  mov     ebx, eax
0x18000ed09  test    eax, eax
0x18000ed0b  js      loc_18000F035
0x18000ed11  xor     edx, edx
0x18000ed13  lea     rcx, [rbp+0A80h+var_670]
0x18000ed1a  call    cs:__imp__o__waccess
0x18000ed20  test    eax, eax
0x18000ed22  jnz     loc_18000EDD3
0x18000ed28  mov     qword ptr [rsp+0B80h+var_B60], rsi; int
0x18000ed2d  lea     r9, [rbp+0A80h+var_670]
0x18000ed34  lea     r8, aSS; "%s\\%s"
0x18000ed3b  mov     edx, 105h; unsigned __int64
0x18000ed40  lea     rcx, [rbp+0A80h+var_250]; unsigned __int16 *
0x18000ed47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ed4c  test    eax, eax
0x18000ed4e  js      loc_18000EF2A
0x18000ed54  xor     edx, edx; Val
0x18000ed56  mov     r8d, 250h; Size
0x18000ed5c  lea     rcx, [rbp+0A80h+var_8C0]; void *
0x18000ed63  call    memset_0
0x18000ed68  lea     rdx, [rbp+0A80h+var_8C0]; lpFindFileData
0x18000ed6f  lea     rcx, [rbp+0A80h+var_250]; lpFileName
0x18000ed76  call    cs:__imp_FindFirstFileW
0x18000ed7c  mov     rsi, rax
0x18000ed7f  mov     [rsp+0B80h+var_B38], rax
0x18000ed84  mov     [rsp+0B80h+var_B50], edi
0x18000ed88  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ed8c  jz      loc_18000EE46
0x18000ed92  test    byte ptr [rbp+0A80h+var_8C0.dwFileAttributes], 10h
0x18000ed99  jz      loc_18000EE48
0x18000ed9f  mov     rcx, [r15+10h]
0x18000eda3  mov     rax, [rcx]
0x18000eda6  lea     rdx, [rsp+0B80h+var_B50]
0x18000edab  mov     rax, [rax+38h]
0x18000edaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edb4  test    eax, eax
0x18000edb6  jns     loc_18000EF4A
0x18000edbc  lea     rax, [rsi-1]
0x18000edc0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000edc4  jbe     loc_18000F027
0x18000edca  xor     edi, edi
0x18000edcc  lea     rsi, aTokensXml; "Tokens*.xml"
0x18000edd3  mov     rcx, [r15+10h]
0x18000edd7  mov     rax, [rcx]
0x18000edda  lea     rdx, [rsp+0B80h+var_B4C]
0x18000eddf  mov     rax, [rax+38h]
0x18000ede3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ede8  test    eax, eax
0x18000edea  js      short loc_18000EE0C
0x18000edec  cmp     [rsp+0B80h+var_B4C], 1F4h
0x18000edf4  jnb     short loc_18000EE0C
0x18000edf6  lea     rdx, [rsp+0B80h+FindFileData]; lpFindFileData
0x18000edfb  mov     rcx, r14; hFindFile
0x18000edfe  call    cs:__imp_FindNextFileW
0x18000ee04  test    eax, eax
0x18000ee06  jnz     loc_18000EC91
0x18000ee0c  lea     rax, [r14-1]
0x18000ee10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ee14  jbe     loc_18000F062
0x18000ee1a  xor     eax, eax
0x18000ee1c  mov     rcx, [rbp+0A80h+var_40]
0x18000ee23  xor     rcx, rsp; StackCookie
0x18000ee26  call    __security_check_cookie
0x18000ee2b  mov     rbx, [rsp+0B80h+arg_18]
0x18000ee33  add     rsp, 0B50h
0x18000ee3a  pop     r15
0x18000ee3c  pop     r14
0x18000ee3e  pop     r13
0x18000ee40  pop     r12
0x18000ee42  pop     rdi
0x18000ee43  pop     rsi
0x18000ee44  pop     rbp
0x18000ee45  retn
0x18000ee46  jmp     short loc_18000EDCC
0x18000ee48  lea     rax, [rbp+0A80h+var_8C0.cFileName]
0x18000ee4f  mov     qword ptr [rsp+0B80h+var_B60], rax; int
0x18000ee54  lea     r9, [rbp+0A80h+var_670]
0x18000ee5b  lea     r8, aSS; "%s\\%s"
0x18000ee62  mov     edx, 105h; unsigned __int64
0x18000ee67  lea     rcx, FullPath; unsigned __int16 *
0x18000ee6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ee73  mov     ebx, eax
0x18000ee75  test    eax, eax
0x18000ee77  js      loc_18000F01D
0x18000ee7d  call    ?GetLatestVersionForThisEngine@CModelDownloadComponent@@SAJPEBGPEAG@Z; CModelDownloadComponent::GetLatestVersionForThisEngine(ushort const *,ushort *)
0x18000ee82  lea     rdx, Stat; Stat
0x18000ee89  lea     rcx, FileName; FileName
0x18000ee90  call    cs:__imp__wstat64i32
0x18000ee96  test    eax, eax
0x18000ee98  jnz     loc_18000EFE0
0x18000ee9e  xor     edx, edx
0x18000eea0  lea     rcx, FileName
0x18000eea7  call    cs:__imp__o__waccess
0x18000eead  test    eax, eax
0x18000eeaf  jnz     loc_18000ED9F
0x18000eeb5  mov     rdi, [r15+10h]
0x18000eeb9  mov     rax, [rdi]
0x18000eebc  mov     rbx, [rax+68h]
0x18000eec0  lea     rcx, [rsp+0B80h+hstringHeader]; hstringHeader
0x18000eec5  call    ??$?0$0BAF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[261])
0x18000eeca  nop
0x18000eecb  mov     rdx, [rax+18h]
0x18000eecf  mov     rcx, rdi
0x18000eed2  mov     rax, rbx
0x18000eed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeda  mov     ebx, eax
0x18000eedc  test    eax, eax
0x18000eede  jns     loc_18000EFAB
0x18000eee4  mov     edx, 11Dh; void *
0x18000eee9  mov     r9d, eax; char *
0x18000eeec  mov     rcx, [rbp+0A88h]; this
0x18000eef3  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000eefa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eeff  mov     rcx, [rbp+0A88h]; this
0x18000ef06  mov     r9d, ebx; char *
0x18000ef09  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000ef10  mov     edx, 0D2h; void *
0x18000ef15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef1a  nop
0x18000ef1b  lea     rcx, [rsp+0B80h+var_B38]
0x18000ef20  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18000ef25  jmp     loc_18000EDCA
0x18000ef2a  mov     rcx, [rbp+0A88h]; this
0x18000ef31  mov     r9d, eax; char *
0x18000ef34  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000ef3b  mov     edx, 0C6h; void *
0x18000ef40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef45  jmp     loc_18000EDD3
0x18000ef4a  cmp     [rsp+0B80h+var_B50], 1F4h
0x18000ef52  jnb     loc_18000EDBC
0x18000ef58  lea     rdx, [rbp+0A80h+var_8C0]; lpFindFileData
0x18000ef5f  mov     rcx, rsi; hFindFile
0x18000ef62  call    cs:__imp_FindNextFileW
0x18000ef68  test    eax, eax
0x18000ef6a  jnz     loc_18000ED92
0x18000ef70  jmp     loc_18000EDBC
0x18000ef75  mov     rcx, [rbp+0A88h]; this
0x18000ef7c  mov     r9d, ebx; char *
0x18000ef7f  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000ef86  mov     edx, 9Eh; void *
0x18000ef8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef90  mov     eax, ebx
0x18000ef92  jmp     loc_18000EE1C
0x18000ef97  lea     rcx, [rsp+0B80h+var_B48]
0x18000ef9c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18000efa1  mov     eax, 8004502Dh
0x18000efa6  jmp     loc_18000EE1C
0x18000efab  mov     rax, cs:Stat.st_mtime
0x18000efb2  mov     [rsp+0B80h+var_B40], rax
0x18000efb7  mov     rdx, [r13+8]
0x18000efbb  cmp     rdx, [r13+10h]
0x18000efbf  jz      short loc_18000EFCE
0x18000efc1  mov     [rdx], rax
0x18000efc4  add     qword ptr [r13+8], 8
0x18000efc9  jmp     loc_18000ED9F
0x18000efce  lea     r8, [rsp+0B80h+var_B40]
0x18000efd3  mov     rcx, r13
0x18000efd6  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18000efdb  jmp     loc_18000ED9F
0x18000efe0  call    cs:__imp__o__errno
0x18000efe6  mov     rcx, [rbp+0A88h]
0x18000efed  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000eff4  cmp     dword ptr [rax], 2
0x18000eff7  jnz     short loc_18000F00B
0x18000eff9  mov     ebx, 80070490h
0x18000effe  mov     edx, 116h
0x18000f003  mov     r9d, ebx
0x18000f006  jmp     loc_18000EEFA
0x18000f00b  mov     ebx, 8000FFFFh
0x18000f010  mov     edx, 117h
0x18000f015  mov     r9d, ebx
0x18000f018  jmp     loc_18000EEFA
0x18000f01d  mov     edx, 111h
0x18000f022  jmp     loc_18000EEE9
0x18000f027  mov     rcx, rsi; hFindFile
0x18000f02a  call    cs:__imp_FindClose
0x18000f030  jmp     loc_18000EDCA
0x18000f035  mov     rcx, [rbp+0A88h]; this
0x18000f03c  mov     r9d, ebx; char *
0x18000f03f  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000f046  mov     edx, 0AEh; void *
0x18000f04b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f050  nop
0x18000f051  lea     rcx, [rsp+0B80h+var_B48]
0x18000f056  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18000f05b  mov     eax, ebx
0x18000f05d  jmp     loc_18000EE1C
0x18000f062  mov     rcx, r14; hFindFile
0x18000f065  call    cs:__imp_FindClose
0x18000f06b  jmp     loc_18000EE1A
```
