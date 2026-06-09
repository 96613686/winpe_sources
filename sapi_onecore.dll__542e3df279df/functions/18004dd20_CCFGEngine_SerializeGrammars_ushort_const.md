# CCFGEngine::SerializeGrammars(ushort const *)

- ea: `0x18004dd20`
- end: `0x18004e3a5`
- name: `?SerializeGrammars@CCFGEngine@@UEAAJPEBG@Z`
- size: `1669`
- prototype: `int(CCFGEngine *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a590`
- `0x180011cb0`
- `0x180019a50`
- `0x180021944`
- `0x180021970`
- `0x180026508`
- `0x180026ae4`
- `0x180029860`
- `0x18002b750`
- `0x18004dd20`
- `0x180079e30`
- `0x18007aae4`
- `0x1800a2880`
- `0x180133710`
- `0x180138e00`
- `0x18013a614`
- `0x18013a658`
- `0x18013a6a8`
- `0x18016c488`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004dfab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004dfab`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004de66`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004de66`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004deb4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004deb4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004df2c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004df2c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004df1b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004df1b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004e18f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004e18f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCFGEngine::SerializeGrammars(CCFGEngine *this, const unsigned __int16 *a2)
{
  unsigned int RegistryKey; // ebx
  __int64 v5; // rdx
  __int64 v6; // rax
  char v7; // bl
  HANDLE FirstFileW; // rdi
  __int64 v9; // rax
  __int64 v10; // rax
  BOOL v11; // ebx
  const char *v12; // r9
  unsigned int LastError; // ebx
  unsigned int v15; // r15d
  unsigned int v16; // r12d
  __int64 v17; // r14
  HRESULT v18; // eax
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, _QWORD); // rbx
  __int64 v21; // rax
  unsigned int i; // edi
  char v23; // dl
  __int64 v24; // r8
  __int64 v25; // rcx
  const unsigned __int16 *v26; // rdx
  const WCHAR *v28; // rcx
  const unsigned __int16 *FileNameW; // rax
  unsigned __int16 *v30; // rdx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  unsigned __int64 v34; // r9
  __int64 v35; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-758h]
  int ppva; // [rsp+20h] [rbp-758h]
  int ppvb; // [rsp+20h] [rbp-758h]
  struct _SECURITY_ATTRIBUTES *v39; // [rsp+30h] [rbp-748h]
  unsigned int v40; // [rsp+38h] [rbp-740h]
  void *v41; // [rsp+40h] [rbp-738h]
  LPVOID v42; // [rsp+50h] [rbp-728h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-720h] BYREF
  __int64 v44; // [rsp+60h] [rbp-718h] BYREF
  char *v45; // [rsp+68h] [rbp-710h] BYREF
  __int64 v46; // [rsp+70h] [rbp-708h] BYREF
  int v47; // [rsp+78h] [rbp-700h] BYREF
  int v48; // [rsp+7Ch] [rbp-6FCh] BYREF
  __int64 v49; // [rsp+80h] [rbp-6F8h] BYREF
  _BYTE v50[32]; // [rsp+88h] [rbp-6F0h] BYREF
  _BYTE v51[40]; // [rsp+A8h] [rbp-6D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-6A8h] BYREF
  unsigned __int16 Src[264]; // [rsp+320h] [rbp-458h] BYREF
  unsigned __int16 v54[264]; // [rsp+530h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+0h]

  if ( !a2 )
  {
    RegistryKey = -2147024809;
    v5 = 79;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\cfgengine.cpp",
      (const char *)RegistryKey,
      (int)ppv);
    return RegistryKey;
  }
  RegistryKey = RemoteControlHelpers::QueryRegistryKey(
                  L"GrammarDumpOutDir",
                  (unsigned __int16 *)1,
                  (unsigned int)Src,
                  (unsigned __int8 *)0x208,
                  (unsigned __int64)ppv);
  if ( (RegistryKey & 0x80000000) != 0 )
  {
    v5 = 82;
    goto LABEL_3;
  }
  v6 = std::wstring::wstring(v50, Src);
  v7 = RemoteControlHelpers::DirectoryExists(v6);
  std::wstring::_Tidy_deallocate(v50);
  if ( !v7 )
  {
    RegistryKey = -2147467260;
    v5 = 84;
    goto LABEL_3;
  }
  v46 = 0;
  CSpDynamicString::AppendHR((CSpDynamicString *)&v46, Src);
  CSpDynamicString::AppendHR((CSpDynamicString *)&v46, a2);
  CSpDynamicString::AppendHR((CSpDynamicString *)&v46, L"__");
  lpFileName = 0;
  CSpDynamicString::operator=(&lpFileName, &v46);
  CSpDynamicString::AppendHR((CSpDynamicString *)&lpFileName, L"*MemoryGrammar*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      try
      {
        v9 = std::wstring::wstring(v51, Src);
        v10 = std::operator+<unsigned short>(v50, v9, FindFileData.cFileName);
        if ( *(_QWORD *)(v10 + 24) > 7u )
          v10 = *(_QWORD *)v10;
        v11 = DeleteFileW((LPCWSTR)v10);
        std::wstring::_Tidy_deallocate(v50);
        std::wstring::_Tidy_deallocate(v51);
      }
      catch ( ... )
      {
        LODWORD(v45) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x68,
                         (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\cfgengine.cpp",
                         v12);
        SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
        RegistryKey = (unsigned int)v45;
        goto LABEL_69;
      }
      if ( !v11 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x66,
                      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\cfgengine.cpp",
                      v12);
        SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
        SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v46);
        return LastError;
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    FindClose(FirstFileW);
  }
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
  v15 = 0;
  v16 = 0;
  while ( v15 < *((_DWORD *)this + 2056) )
  {
    v17 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * v15);
    if ( ((v17 - 128) & -(__int64)(v17 != 0)) != 0 )
    {
      v42 = 0;
      v44 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v18 = CoCreateInstance(&CLSID_SpGramCompBackend, 0, 3u, &GUID_b423f56f_1221_46fa_ade9_cdf19f06658d, &v42);
      RegistryKey = v18;
      if ( v18 < 0 )
      {
        v33 = 119;
      }
      else
      {
        v18 = Microsoft::WRL::ComPtr<ISpGramCompBackendPrivate>::As<ISpGrammarBuilderPrivate>(&v42, &v44);
        RegistryKey = v18;
        if ( v18 < 0 )
        {
          v33 = 120;
        }
        else
        {
          v19 = v42;
          v20 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v42 + 96LL);
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
          v18 = v20(v19, *(_QWORD *)(v21 + 224));
          RegistryKey = v18;
          if ( v18 < 0 )
          {
            v33 = 121;
          }
          else
          {
            v47 = 0;
            v18 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v42 + 104LL))(v42, &v47);
            RegistryKey = v18;
            if ( v18 >= 0 )
            {
              for ( i = 0; (int)i < v47; ++i )
              {
                v48 = 0;
                v49 = 0;
                v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v42 + 112LL))(v42, i, &v49);
                RegistryKey = v18;
                if ( v18 < 0 )
                {
                  v33 = 131;
                  goto LABEL_66;
                }
                v18 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v44 + 88LL))(v44, v49, &v48);
                RegistryKey = v18;
                if ( v18 < 0 )
                {
                  v33 = 132;
                  goto LABEL_66;
                }
                if ( !(unsigned int)CRecoInstGrammar::RulesShouldCount(*(CRecoInstGrammar **)(((v17 - 128)
                                                                                             & -(__int64)(v17 != 0))
                                                                                            + 0x308))
                  || (v23 = 1,
                      !*(_DWORD *)(96LL * (int)i + *(_QWORD *)(((v17 - 128) & -(__int64)(v17 != 0)) + 0xA8) + 36)) )
                {
                  v23 = 0;
                }
                if ( (v48 & 1) != 0 )
                {
                  v24 = v48 & 0xFFFFFFBD | 2;
                  if ( !v23 )
                    v24 = v48 & 0xFFFFFFBD;
                  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v44 + 80LL))(v44, v49, v24);
                  RegistryKey = v18;
                  if ( v18 < 0 )
                  {
                    v33 = 147;
                    goto LABEL_66;
                  }
                }
              }
              lpFileName = 0;
              CSpDynamicString::operator=(&lpFileName, &v46);
              v25 = *(_QWORD *)(*(_QWORD *)(((v17 - 128) & -(__int64)(v17 != 0)) + 0x308) + 16LL);
              if ( v25 )
              {
                v26 = (const unsigned __int16 *)(v25 + 56);
                if ( *(_QWORD *)(v25 + 80) <= 7u ? v25 + 56 : *(_QWORD *)v26 )
                {
                  if ( *(_QWORD *)(v25 + 80) > 7u )
                    v26 = *(const unsigned __int16 **)v26;
                  CSpDynamicString::AppendHR((CSpDynamicString *)&lpFileName, v26);
                  CSpDynamicString::AppendHR((CSpDynamicString *)&lpFileName, L"__");
                }
              }
              v28 = *(const WCHAR **)(((v17 - 128) & -(__int64)(v17 != 0)) + 0x58);
              if ( v28 )
              {
                FileNameW = PathFindFileNameW(v28);
                CSpDynamicString::AppendHR((CSpDynamicString *)&lpFileName, FileNameW);
                v30 = L".cfg";
                goto LABEL_48;
              }
              if ( (int)swprintf_s<260>(v54, L"MemoryGrammar_%d.cfg", v16) < 0 )
              {
                RegistryKey = -2147467259;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\cfgengine.cpp",
                  (const char *)0x80004005LL,
                  ppva);
              }
              else
              {
                ++v16;
                v30 = v54;
LABEL_48:
                CSpDynamicString::AppendHR((CSpDynamicString *)&lpFileName, v30);
                LODWORD(v45) = 0;
                CSpFileStream::CSpFileStream(
                  (CSpFileStream *)v50,
                  (int *)&v45,
                  lpFileName,
                  0x40000000u,
                  0,
                  2u,
                  v39,
                  v40,
                  v41);
                RegistryKey = (unsigned int)v45;
                if ( (int)v45 < 0 )
                {
                  v34 = (unsigned int)v45;
                  v35 = 176;
                }
                else
                {
                  v31 = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, _QWORD))(*(_QWORD *)v42 + 88LL))(v42, v50, 0);
                  RegistryKey = v31;
                  if ( v31 < 0 )
                  {
                    v34 = (unsigned int)v31;
                    v35 = 177;
                  }
                  else
                  {
                    v32 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v42 + 80LL))(v42, 1);
                    RegistryKey = v32;
                    if ( v32 >= 0 )
                    {
                      CSpFileStream::~CSpFileStream((CSpFileStream *)v50);
                      SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                      goto LABEL_52;
                    }
                    v34 = (unsigned int)v32;
                    v35 = 178;
                  }
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v35,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\cfgengine.cpp",
                  (const char *)v34,
                  ppvb);
                CSpFileStream::~CSpFileStream((CSpFileStream *)v50);
              }
              SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
LABEL_67:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              goto LABEL_69;
            }
            v33 = 124;
          }
        }
      }
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\cfgengine.cpp",
        (const char *)(unsigned int)v18,
        ppva);
      goto LABEL_67;
    }
LABEL_52:
    ++v15;
  }
  RegistryKey = 0;
LABEL_69:
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v46);
  return RegistryKey;
}

```

## disassembly

```asm
0x18004dd20  mov     [rsp+arg_10], rbx
0x18004dd25  mov     [rsp+arg_18], rsi
0x18004dd2a  push    rdi
0x18004dd2b  push    r12
0x18004dd2d  push    r13
0x18004dd2f  push    r14
0x18004dd31  push    r15
0x18004dd33  sub     rsp, 750h
0x18004dd3a  mov     rax, cs:__security_cookie
0x18004dd41  xor     rax, rsp
0x18004dd44  mov     [rsp+778h+var_38], rax
0x18004dd4c  mov     rdi, rdx
0x18004dd4f  mov     r13, rcx
0x18004dd52  xor     r14d, r14d
0x18004dd55  test    rdx, rdx
0x18004dd58  jnz     short loc_18004DD7E
0x18004dd5a  mov     ebx, 80070057h
0x18004dd5f  lea     edx, [rdi+4Fh]; void *
0x18004dd62  mov     rcx, [rsp+778h]; this
0x18004dd6a  mov     r9d, ebx; char *
0x18004dd6d  lea     r8, aOnecoreuapEndu_334; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004dd74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dd79  jmp     loc_18004E376
0x18004dd7e  mov     r9d, 208h; unsigned __int8 *
0x18004dd84  lea     r8, [rsp+778h+Src]; unsigned int
0x18004dd8c  mov     edx, 1; unsigned __int16 *
0x18004dd91  lea     rcx, aGrammardumpout; "GrammarDumpOutDir"
0x18004dd98  call    ?QueryRegistryKey@RemoteControlHelpers@@YAJPEAGKPEAE_K@Z; RemoteControlHelpers::QueryRegistryKey(ushort *,ulong,uchar *,unsigned __int64)
0x18004dd9d  mov     ebx, eax
0x18004dd9f  test    eax, eax
0x18004dda1  jns     short loc_18004DDAA
0x18004dda3  mov     edx, 52h ; 'R'
0x18004dda8  jmp     short loc_18004DD62
0x18004ddaa  lea     rdx, [rsp+778h+Src]
0x18004ddb2  lea     rcx, [rsp+778h+var_6F0]
0x18004ddba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ddbf  mov     rcx, rax
0x18004ddc2  call    ?DirectoryExists@RemoteControlHelpers@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RemoteControlHelpers::DirectoryExists(std::wstring const &)
0x18004ddc7  mov     bl, al
0x18004ddc9  lea     rcx, [rsp+778h+var_6F0]
0x18004ddd1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ddd6  test    bl, bl
0x18004ddd8  jnz     short loc_18004DDE9
0x18004ddda  mov     ebx, 80004004h
0x18004dddf  mov     edx, 54h ; 'T'
0x18004dde4  jmp     loc_18004DD62
0x18004dde9  mov     [rsp+778h+var_708], r14
0x18004ddee  lea     rdx, [rsp+778h+Src]; Src
0x18004ddf6  lea     rcx, [rsp+778h+var_708]; this
0x18004ddfb  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004de00  mov     rdx, rdi; Src
0x18004de03  lea     rcx, [rsp+778h+var_708]; this
0x18004de08  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004de0d  lea     rdx, asc_1802AEB80; "__"
0x18004de14  lea     rcx, [rsp+778h+var_708]; this
0x18004de19  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004de1e  mov     [rsp+778h+lpFileName], r14
0x18004de23  lea     rdx, [rsp+778h+var_708]
0x18004de28  lea     rcx, [rsp+778h+lpFileName]
0x18004de2d  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x18004de32  nop
0x18004de33  lea     rdx, aMemorygrammar; "*MemoryGrammar*"
0x18004de3a  lea     rcx, [rsp+778h+lpFileName]; this
0x18004de3f  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004de44  xor     edx, edx; Val
0x18004de46  mov     r8d, 250h; Size
0x18004de4c  lea     rcx, [rsp+778h+FindFileData]; void *
0x18004de54  call    memset_0
0x18004de59  lea     rdx, [rsp+778h+FindFileData]; lpFindFileData
0x18004de61  mov     rcx, [rsp+778h+lpFileName]; lpFileName
0x18004de66  call    cs:__imp_FindFirstFileW
0x18004de6c  mov     rdi, rax
0x18004de6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004de73  jz      loc_18004DF33
0x18004de79  lea     rdx, [rsp+778h+Src]
0x18004de81  lea     rcx, [rsp+778h+var_6D0]
0x18004de89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004de8e  nop
0x18004de8f  lea     r8, [rsp+778h+FindFileData.cFileName]
0x18004de97  mov     rdx, rax
0x18004de9a  lea     rcx, [rsp+778h+var_6F0]
0x18004dea2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004dea7  cmp     qword ptr [rax+18h], 7
0x18004deac  jbe     short loc_18004DEB1
0x18004deae  mov     rax, [rax]
0x18004deb1  mov     rcx, rax; lpFileName
0x18004deb4  call    cs:__imp_DeleteFileW
0x18004deba  mov     ebx, eax
0x18004debc  lea     rcx, [rsp+778h+var_6F0]
0x18004dec4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dec9  nop
0x18004deca  lea     rcx, [rsp+778h+var_6D0]
0x18004ded2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ded7  test    ebx, ebx
0x18004ded9  jnz     short loc_18004DF10
0x18004dedb  mov     rcx, [rsp+778h]; this
0x18004dee3  lea     r8, aOnecoreuapEndu_334; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004deea  lea     edx, [rbx+66h]; void *
0x18004deed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004def2  mov     ebx, eax
0x18004def4  lea     rcx, [rsp+778h+lpFileName]; this
0x18004def9  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18004defe  nop
0x18004deff  lea     rcx, [rsp+778h+var_708]; this
0x18004df04  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18004df09  mov     eax, ebx
0x18004df0b  jmp     loc_18004E378
0x18004df10  lea     rdx, [rsp+778h+FindFileData]; lpFindFileData
0x18004df18  mov     rcx, rdi; hFindFile
0x18004df1b  call    cs:__imp_FindNextFileW
0x18004df21  test    eax, eax
0x18004df23  jnz     loc_18004DE79
0x18004df29  mov     rcx, rdi; hFindFile
0x18004df2c  call    cs:__imp_FindClose
0x18004df32  nop
0x18004df33  lea     rcx, [rsp+778h+lpFileName]; this
0x18004df38  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18004df3d  mov     r15d, r14d
0x18004df40  mov     r12d, r14d
0x18004df43  cmp     r15d, [r13+2020h]
0x18004df4a  jnb     loc_18004E369
0x18004df50  mov     ecx, r15d
0x18004df53  mov     rax, [r13+18h]
0x18004df57  mov     r14, [rax+rcx*8]
0x18004df5b  mov     rax, r14
0x18004df5e  lea     rcx, [r14-80h]
0x18004df62  neg     rax
0x18004df65  sbb     rsi, rsi
0x18004df68  and     rsi, rcx
0x18004df6b  jz      loc_18004E289
0x18004df71  mov     [rsp+778h+var_728], 0
0x18004df7a  mov     [rsp+778h+var_718], 0
0x18004df83  lea     rcx, [rsp+778h+var_728]
0x18004df88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004df8d  lea     rax, [rsp+778h+var_728]
0x18004df92  mov     [rsp+778h+ppv], rax; int
0x18004df97  lea     r9, _GUID_b423f56f_1221_46fa_ade9_cdf19f06658d; riid
0x18004df9e  xor     edx, edx; pUnkOuter
0x18004dfa0  lea     r8d, [rdx+3]; dwClsContext
0x18004dfa4  lea     rcx, CLSID_SpGramCompBackend; rclsid
0x18004dfab  call    cs:__imp_CoCreateInstance
0x18004dfb1  mov     ebx, eax
0x18004dfb3  test    eax, eax
0x18004dfb5  js      loc_18004E335
0x18004dfbb  lea     rdx, [rsp+778h+var_718]
0x18004dfc0  lea     rcx, [rsp+778h+var_728]
0x18004dfc5  call    ??$As@UISpGrammarBuilderPrivate@@@?$ComPtr@UISpGramCompBackendPrivate@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISpGrammarBuilderPrivate@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ISpGramCompBackendPrivate>::As<ISpGrammarBuilderPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISpGrammarBuilderPrivate>>)
0x18004dfca  mov     ebx, eax
0x18004dfcc  test    eax, eax
0x18004dfce  js      loc_18004E32E
0x18004dfd4  mov     rdi, [rsp+778h+var_728]
0x18004dfd9  mov     rax, [rdi]
0x18004dfdc  mov     rbx, [rax+60h]
0x18004dfe0  mov     rdx, [r14]
0x18004dfe3  mov     rcx, r14
0x18004dfe6  mov     rax, [rdx+28h]
0x18004dfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfef  mov     rdx, [rax+0E0h]
0x18004dff6  mov     rcx, rdi
0x18004dff9  mov     rax, rbx
0x18004dffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e001  mov     ebx, eax
0x18004e003  xor     r14d, r14d
0x18004e006  test    eax, eax
0x18004e008  js      loc_18004E327
0x18004e00e  mov     [rsp+778h+var_700], r14d
0x18004e013  mov     rcx, [rsp+778h+var_728]
0x18004e018  mov     rax, [rcx]
0x18004e01b  lea     rdx, [rsp+778h+var_700]
0x18004e020  mov     rax, [rax+68h]
0x18004e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e029  mov     ebx, eax
0x18004e02b  test    eax, eax
0x18004e02d  js      loc_18004E320
0x18004e033  mov     edi, r14d
0x18004e036  cmp     edi, [rsp+778h+var_700]
0x18004e03a  jge     loc_18004E124
0x18004e040  mov     [rsp+778h+var_6FC], r14d
0x18004e045  mov     [rsp+778h+var_6F8], r14
0x18004e04d  mov     rcx, [rsp+778h+var_728]
0x18004e052  mov     rax, [rcx]
0x18004e055  lea     r8, [rsp+778h+var_6F8]
0x18004e05d  mov     edx, edi
0x18004e05f  mov     rax, [rax+70h]
0x18004e063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e068  mov     ebx, eax
0x18004e06a  test    eax, eax
0x18004e06c  js      loc_18004E2A8
0x18004e072  mov     rcx, [rsp+778h+var_718]
0x18004e077  mov     rax, [rcx]
0x18004e07a  lea     r8, [rsp+778h+var_6FC]
0x18004e07f  mov     rdx, [rsp+778h+var_6F8]
0x18004e087  mov     rax, [rax+58h]
0x18004e08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e090  mov     ebx, eax
0x18004e092  test    eax, eax
0x18004e094  js      loc_18004E29E
0x18004e09a  mov     rcx, [rsi+308h]; this
0x18004e0a1  call    ?RulesShouldCount@CRecoInstGrammar@@QEAAHXZ; CRecoInstGrammar::RulesShouldCount(void)
0x18004e0a6  test    eax, eax
0x18004e0a8  jz      short loc_18004E0C5
0x18004e0aa  movsxd  rax, edi
0x18004e0ad  lea     rcx, [rax+rax*2]
0x18004e0b1  shl     rcx, 5
0x18004e0b5  mov     rax, [rsi+0A8h]
0x18004e0bc  cmp     [rcx+rax+24h], r14d
0x18004e0c1  mov     dl, 1
0x18004e0c3  jnz     short loc_18004E0C8
0x18004e0c5  mov     dl, r14b
0x18004e0c8  mov     r8d, [rsp+778h+var_6FC]
0x18004e0cd  test    r8b, 1
0x18004e0d1  jz      short loc_18004E10A
0x18004e0d3  and     r8d, 0FFFFFFBFh
0x18004e0d7  mov     rcx, [rsp+778h+var_718]
0x18004e0dc  mov     r9, [rcx]
0x18004e0df  mov     eax, r8d
0x18004e0e2  and     eax, 0FFFFFFFDh
0x18004e0e5  or      r8d, 2
0x18004e0e9  test    dl, dl
0x18004e0eb  cmovz   r8d, eax
0x18004e0ef  mov     rdx, [rsp+778h+var_6F8]
0x18004e0f7  mov     rax, [r9+50h]
0x18004e0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e100  mov     ebx, eax
0x18004e102  test    eax, eax
0x18004e104  js      loc_18004E294
0x18004e10a  inc     edi
0x18004e10c  jmp     loc_18004E036
0x18004e111  lea     rcx, [rsp+778h+lpFileName]; this
0x18004e116  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18004e11b  mov     ebx, dword ptr [rsp+778h+var_710]
0x18004e11f  jmp     loc_18004E36C
0x18004e124  mov     [rsp+778h+lpFileName], r14
0x18004e129  lea     rdx, [rsp+778h+var_708]
0x18004e12e  lea     rcx, [rsp+778h+lpFileName]
0x18004e133  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x18004e138  nop
0x18004e139  mov     rax, [rsi+308h]
0x18004e140  mov     rcx, [rax+10h]
0x18004e144  test    rcx, rcx
0x18004e147  jz      short loc_18004E186
0x18004e149  lea     rdx, [rcx+38h]
0x18004e14d  cmp     qword ptr [rcx+50h], 7
0x18004e152  jbe     short loc_18004E159
0x18004e154  mov     rax, [rdx]
0x18004e157  jmp     short loc_18004E15C
0x18004e159  mov     rax, rdx
0x18004e15c  test    rax, rax
0x18004e15f  jz      short loc_18004E186
0x18004e161  cmp     qword ptr [rcx+50h], 7
0x18004e166  jbe     short loc_18004E16B
0x18004e168  mov     rdx, [rdx]; Src
0x18004e16b  lea     rcx, [rsp+778h+lpFileName]; this
0x18004e170  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004e175  lea     rdx, asc_1802AEB80; "__"
0x18004e17c  lea     rcx, [rsp+778h+lpFileName]; this
0x18004e181  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004e186  mov     rcx, [rsi+58h]; pszPath
0x18004e18a  test    rcx, rcx
0x18004e18d  jz      short loc_18004E1AB
0x18004e18f  call    cs:__imp_PathFindFileNameW
0x18004e195  mov     rdx, rax; Src
0x18004e198  lea     rcx, [rsp+778h+lpFileName]; this
0x18004e19d  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004e1a2  lea     rdx, aCfg; ".cfg"
0x18004e1a9  jmp     short loc_18004E1D5
0x18004e1ab  mov     r8d, r12d
0x18004e1ae  lea     rdx, aMemorygrammarD; "MemoryGrammar_%d.cfg"
0x18004e1b5  lea     rcx, [rsp+778h+var_248]
0x18004e1bd  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x18004e1c2  test    eax, eax
0x18004e1c4  js      loc_18004E2F2
0x18004e1ca  inc     r12d
0x18004e1cd  lea     rdx, [rsp+778h+var_248]; Src
0x18004e1d5  lea     rcx, [rsp+778h+lpFileName]; this
0x18004e1da  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x18004e1df  mov     dword ptr [rsp+778h+var_710], r14d
0x18004e1e4  mov     [rsp+778h+var_750], 2; unsigned int
0x18004e1ec  mov     dword ptr [rsp+778h+ppv], r14d; int
0x18004e1f1  mov     r9d, 40000000h; unsigned int
0x18004e1f7  mov     r8, [rsp+778h+lpFileName]; unsigned __int16 *
0x18004e1fc  lea     rdx, [rsp+778h+var_710]; int *
0x18004e201  lea     rcx, [rsp+778h+var_6F0]; this
0x18004e209  call    ??0CSpFileStream@@QEAA@PEAJPEBGKKKPEAU_SECURITY_ATTRIBUTES@@KPEAX@Z; CSpFileStream::CSpFileStream(long *,ushort const *,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,void *)
0x18004e20e  nop
0x18004e20f  mov     ebx, dword ptr [rsp+778h+var_710]
0x18004e213  test    ebx, ebx
0x18004e215  js      loc_18004E2C6
0x18004e21b  mov     rcx, [rsp+778h+var_728]
0x18004e220  mov     rax, [rcx]
0x18004e223  xor     r8d, r8d
0x18004e226  lea     rdx, [rsp+778h+var_6F0]
0x18004e22e  mov     rax, [rax+58h]
0x18004e232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e237  mov     ebx, eax
0x18004e239  test    eax, eax
0x18004e23b  js      short loc_18004E2BC
0x18004e23d  mov     rcx, [rsp+778h+var_728]
0x18004e242  mov     rax, [rcx]
0x18004e245  mov     edx, 1
  ... truncated ...
```
