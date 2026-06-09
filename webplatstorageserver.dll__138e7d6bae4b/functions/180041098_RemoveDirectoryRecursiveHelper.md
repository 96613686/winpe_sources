# RemoveDirectoryRecursiveHelper

- ea: `0x180041098`
- end: `0x1800412bc`
- name: `RemoveDirectoryRecursiveHelper`
- size: `548`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180041098`
- `0x1800415d4`

## callees

- `0x1800169b0`
- `0x18001c800`
- `0x180041098`
- `0x1800412c4`
- `0x180042310`
- `0x180064ec8`
- `0x180080fb0`
- `0x180081b40`
- `0x180081f31`
- `0x180081f3d`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180041114`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180041114`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800411af`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800411af`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800411cc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800411cc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004129a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004129a`

## pseudocode

```c
int __fastcall RemoveDirectoryRecursiveHelper(_QWORD *a1)
{
  _QWORD *v1; // rdi
  const WCHAR *v2; // rcx
  char *FirstFile; // rbx
  int result; // eax
  const WCHAR *v5; // rcx
  int v6; // edx
  int v7; // edx
  _QWORD *v8; // rax
  const WCHAR *v9; // rcx
  LPCWSTR Src[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v11; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpFileName[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v13; // [rsp+70h] [rbp-90h]
  WCHAR PathName[20]; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v1 = a1;
  std::operator+<unsigned short>(lpFileName, a1, (void *)L"*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = (const WCHAR *)lpFileName;
  if ( v13 > 7 )
    v2 = lpFileName[0];
  FirstFile = (char *)FindFirstFileExW(v2, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      std::operator+<unsigned short>(Src, v1, FindFileData.cFileName);
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v6 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v6 = FindFileData.cFileName[1];
        if ( v6 )
        {
          v7 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v7 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v7 = FindFileData.cFileName[2];
          }
          if ( v7 )
          {
            v8 = (_QWORD *)std::wstring::append(Src, L"\\");
            if ( v8[3] > 7u )
              v8 = (_QWORD *)*v8;
            std::wstring::wstring(PathName, v8);
            RemoveDirectoryRecursiveHelper(PathName);
            std::wstring::~wstring(PathName);
          }
        }
      }
      else
      {
        if ( (FindFileData.dwFileAttributes & 1) != 0 )
        {
          v9 = (const WCHAR *)Src;
          if ( v11 > 7 )
            v9 = Src[0];
          SetFileAttributesW_0(v9, FindFileData.dwFileAttributes & 0xFFFFFFFE);
        }
        v5 = (const WCHAR *)Src;
        if ( v11 > 7 )
          v5 = Src[0];
        DeleteFileW(v5);
      }
      if ( v11 > 7 )
        std::_Deallocate<16>(Src[0], 2 * v11 + 2);
    }
    while ( FindNextFileW(FirstFile, &FindFileData) );
  }
  if ( v1[3] > 7u )
    v1 = (_QWORD *)*v1;
  RemoveDirectoryW_0((LPCWSTR)v1);
  result = (_DWORD)FirstFile - 1;
  if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    result = FindClose(FirstFile);
  if ( v13 > 7 )
    return std::_Deallocate<16>(lpFileName[0], 2 * v13 + 2);
  return result;
}

```

## disassembly

```asm
0x180041098  push    rbp
0x18004109a  push    rbx
0x18004109b  push    rdi
0x18004109c  push    r14
0x18004109e  lea     rbp, [rsp-208h]
0x1800410a6  sub     rsp, 308h
0x1800410ad  mov     rax, cs:__security_cookie
0x1800410b4  xor     rax, rsp
0x1800410b7  mov     [rbp+220h+var_30], rax
0x1800410be  mov     rdi, rcx
0x1800410c1  lea     r8, pszMore; "*"
0x1800410c8  mov     rdx, rcx; Src
0x1800410cb  lea     rcx, [rsp+320h+lpFileName]; void *
0x1800410d0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800410d5  nop
0x1800410d6  xor     edx, edx; Val
0x1800410d8  mov     r8d, 250h; Size
0x1800410de  lea     rcx, [rbp+220h+FindFileData]; void *
0x1800410e2  call    memset_0
0x1800410e7  lea     rcx, [rsp+320h+lpFileName]
0x1800410ec  cmp     [rsp+320h+var_2B0], 7
0x1800410f2  cmova   rcx, [rsp+320h+lpFileName]; lpFileName
0x1800410f8  mov     [rsp+320h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180041100  mov     [rsp+320h+lpSearchFilter], 0; lpSearchFilter
0x180041109  xor     r9d, r9d; fSearchOp
0x18004110c  lea     r8, [rbp+220h+FindFileData]; lpFindFileData
0x180041110  lea     edx, [r9+1]; fInfoLevelId
0x180041114  call    cs:__imp_FindFirstFileExW
0x18004111a  mov     rbx, rax
0x18004111d  mov     [rsp+320h+var_2F0], rax
0x180041122  dec     rax
0x180041125  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041129  jbe     loc_180041257
0x18004112f  cmp     qword ptr [rdi+18h], 7
0x180041134  jbe     short loc_180041139
0x180041136  mov     rdi, [rdi]
0x180041139  mov     rcx, rdi; lpPathName
0x18004113c  call    RemoveDirectoryW_0
0x180041141  nop
0x180041142  lea     rax, [rbx-1]
0x180041146  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004114a  jbe     loc_180041297
0x180041150  mov     rdx, [rsp+320h+var_2B0]
0x180041155  cmp     rdx, 7
0x180041159  ja      loc_1800412A5
0x18004115f  mov     rcx, [rbp+220h+var_30]
0x180041166  xor     rcx, rsp; StackCookie
0x180041169  call    __security_check_cookie
0x18004116e  add     rsp, 308h
0x180041175  pop     r14
0x180041177  pop     rdi
0x180041178  pop     rbx
0x180041179  pop     rbp
0x18004117a  retn
0x18004117b  lea     r8, [rbp+220h+var_254]; void *
0x18004117f  mov     rdx, rdi; Src
0x180041182  lea     rcx, [rsp+320h+Src]; void *
0x180041187  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004118c  nop
0x18004118d  mov     edx, [rbp+220h+FindFileData]
0x180041190  test    dl, 10h
0x180041193  jnz     short loc_1800411DB
0x180041195  test    dl, 1
0x180041198  jnz     loc_180041262
0x18004119e  lea     rcx, [rsp+320h+Src]
0x1800411a3  cmp     [rsp+320h+var_2D0], 7
0x1800411a9  cmova   rcx, [rsp+320h+Src]; lpFileName
0x1800411af  call    cs:__imp_DeleteFileW
0x1800411b5  nop
0x1800411b6  mov     rdx, [rsp+320h+var_2D0]
0x1800411bb  cmp     rdx, 7
0x1800411bf  ja      loc_180041280
0x1800411c5  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x1800411c9  mov     rcx, rbx; hFindFile
0x1800411cc  call    cs:__imp_FindNextFileW
0x1800411d2  test    eax, eax
0x1800411d4  jnz     short loc_18004117B
0x1800411d6  jmp     loc_18004112F
0x1800411db  movzx   edx, [rbp+220h+var_254]
0x1800411df  sub     edx, r14d
0x1800411e2  jnz     short loc_1800411EF
0x1800411e4  movzx   edx, [rbp+220h+var_252]
0x1800411e8  xor     eax, eax
0x1800411ea  movzx   ecx, ax
0x1800411ed  sub     edx, ecx
0x1800411ef  test    edx, edx
0x1800411f1  jz      short loc_1800411B6
0x1800411f3  movzx   edx, [rbp+220h+var_254]
0x1800411f7  sub     edx, r14d
0x1800411fa  jnz     short loc_180041210
0x1800411fc  movzx   edx, [rbp+220h+var_252]
0x180041200  sub     edx, r14d
0x180041203  jnz     short loc_180041210
0x180041205  movzx   edx, [rbp+220h+var_250]
0x180041209  xor     eax, eax
0x18004120b  movzx   ecx, ax
0x18004120e  sub     edx, ecx
0x180041210  test    edx, edx
0x180041212  jz      short loc_1800411B6
0x180041214  lea     rdx, asc_1800D6E04; "\\"
0x18004121b  lea     rcx, [rsp+320h+Src]; Src
0x180041220  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041225  cmp     qword ptr [rax+18h], 7
0x18004122a  jbe     short loc_18004122F
0x18004122c  mov     rax, [rax]
0x18004122f  mov     rdx, rax
0x180041232  lea     rcx, [rsp+320h+PathName]
0x180041237  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004123c  nop
0x18004123d  lea     rcx, [rsp+320h+PathName]
0x180041242  call    RemoveDirectoryRecursiveHelper
0x180041247  nop
0x180041248  lea     rcx, [rsp+320h+PathName]; void *
0x18004124d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041252  jmp     loc_1800411B6
0x180041257  mov     r14d, 2Eh ; '.'
0x18004125d  jmp     loc_18004117B
0x180041262  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180041265  lea     rcx, [rsp+320h+Src]
0x18004126a  cmp     [rsp+320h+var_2D0], 7
0x180041270  cmova   rcx, [rsp+320h+Src]; lpFileName
0x180041276  call    SetFileAttributesW_0
0x18004127b  jmp     loc_18004119E
0x180041280  lea     rdx, ds:2[rdx*2]
0x180041288  mov     rcx, [rsp+320h+Src]
0x18004128d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041292  jmp     loc_1800411C5
0x180041297  mov     rcx, rbx; hFindFile
0x18004129a  call    cs:__imp_FindClose
0x1800412a0  jmp     loc_180041150
0x1800412a5  lea     rdx, ds:2[rdx*2]
0x1800412ad  mov     rcx, [rsp+320h+lpFileName]
0x1800412b2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800412b7  jmp     loc_18004115F
```
