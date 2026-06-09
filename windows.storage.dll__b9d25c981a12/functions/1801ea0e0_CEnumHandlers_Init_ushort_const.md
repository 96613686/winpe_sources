# CEnumHandlers::Init(ushort const *)

- ea: `0x1801ea0e0`
- end: `0x1801ea4c6`
- name: `?Init@CEnumHandlers@@QEAAHPEBG@Z`
- size: `998`
- prototype: `int(CEnumHandlers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801e9e50`

## callees

- `0x180033d90`
- `0x180045bd0`
- `0x1801ea0e0`
- `0x1801ea4cc`
- `0x1801eb38c`
- `0x1801ebc64`
- `0x1801ebd40`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ea136`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ea136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ea11c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ea11c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ea3c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ea3c0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1801ea160`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1801ea160`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea202`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea27f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea2f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea329`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea449`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea4a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea202`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea27f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea2f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea329`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea449`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ea4a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ea4b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ea4b5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1801ea226`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1801ea226`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocGetPerceivedType` at `0x1801ea2b9`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocGetPerceivedType` at `0x1801ea2b9`

## string_xrefs

- `0x1801ea1d2`: `%s\OpenWithProgids`
- `0x1801ea251`: `%s\OpenWithList`
- `0x1801ea2ed`: `*\OpenWithProgids`
- `0x1801ea455`: `OpenWithList`
- `0x1801ea41b`: `SystemFileAssociations\%s\OpenWithList`

## pseudocode

```c
__int64 __fastcall CEnumHandlers::Init(CEnumHandlers *this, const unsigned __int16 *a2)
{
  unsigned int v3; // r14d
  HANDLE ProcessHeap; // rbx
  _DWORD *v6; // rax
  PWSTR v7; // rax
  void *v8; // rcx
  PWSTR v9; // rbx
  __int64 v10; // rdi
  LPCWCH *v11; // rbx
  _QWORD v13[6]; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszType; // [rsp+60h] [rbp-A0h] BYREF
  PERCEIVEDFLAG pflag; // [rsp+68h] [rbp-98h] BYREF
  PERCEIVED ptype; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v3 = 0;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( v6 )
  {
    v6[7] = 8;
    *((_QWORD *)v6 + 2) = ProcessHeap;
    *((_QWORD *)this + 102) = v6;
    v7 = StrDupW(a2);
    v8 = (void *)*((_QWORD *)this + 2);
    v9 = v7;
    *((_QWORD *)this + 2) = 0;
    CTContainer_PolicyLocalMem::DestroyMem(v8);
    *((_QWORD *)this + 2) = v9;
    if ( v9 )
    {
      _AddProgidForExt(a2);
      CDefaultProgramsMatches::Init((CEnumHandlers *)((char *)this + 24), HKEY_LOCAL_MACHINE, a2);
      CDefaultProgramsMatches::Init((CEnumHandlers *)((char *)this + 88), HKEY_CURRENT_USER, a2);
      *((_DWORD *)this + 41) = 64;
      StringCchPrintfW(SubKey, 0x104u, L"%s\\OpenWithProgids", a2);
      RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, (PHKEY)this + 19);
      *((_DWORD *)this + 45) = 64;
      *((_QWORD *)this + 21) = SHGetShellKeyEx(24577, SubKey);
      *((_DWORD *)this + 180) = CMRUEnumHandlers::Init((CEnumHandlers *)((char *)this + 184), a2);
      StringCchPrintfW(SubKey, 0x104u, L"%s\\OpenWithList", a2);
      RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, (PHKEY)this + 91);
      ptype = PERCEIVED_TYPE_UNKNOWN;
      *((_DWORD *)this + 185) = 128;
      pflag = 0;
      ppszType = 0;
      if ( AssocGetPerceivedType(a2, &ptype, &pflag, &ppszType) >= 0 )
      {
        StringCchPrintfW(SubKey, 0x104u, L"SystemFileAssociations\\%s\\OpenWithList", ppszType);
        RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, (PHKEY)this + 93);
        StringCchPrintfW(
          SubKey,
          0x104u,
          L"%s\\%s\\%s",
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FileExts",
          ppszType,
          L"OpenWithList");
        RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)this + 95);
        CoTaskMemFree(ppszType);
      }
      *((_DWORD *)this + 189) = 128;
      *((_DWORD *)this + 193) = 128;
      RegOpenKeyExW(HKEY_CLASSES_ROOT, L"*\\OpenWithProgids", 0, 0x20019u, (PHKEY)this + 97);
      *((_DWORD *)this + 197) = 512;
      RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Applications", 0, 0x20019u, (PHKEY)this + 99);
      *((_DWORD *)this + 201) = 16;
      v3 = 1;
      if ( IsBrowserReplacementFeaturePresent() )
      {
        v13[0] = L".epub";
        v10 = -1;
        v13[1] = L".htm";
        v13[2] = L".html";
        v13[3] = L".pdf";
        v13[4] = L".svg";
        v13[5] = L".xml";
        do
          ++v10;
        while ( a2[v10] );
        v11 = (LPCWCH *)v13;
        do
        {
          if ( CompareStringOrdinal(a2, v10, *v11, -1, 1) == 2 )
            break;
          ++v11;
        }
        while ( v11 != (LPCWCH *)&ppszType );
      }
    }
  }
  else
  {
    *((_QWORD *)this + 102) = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1801ea0e0  mov     [rsp-8+arg_10], rbx
0x1801ea0e5  push    rbp
0x1801ea0e6  push    rsi
0x1801ea0e7  push    rdi
0x1801ea0e8  push    r12
0x1801ea0ea  push    r13
0x1801ea0ec  push    r14
0x1801ea0ee  push    r15
0x1801ea0f0  lea     rbp, [rsp-190h]
0x1801ea0f8  sub     rsp, 290h
0x1801ea0ff  mov     rax, cs:__security_cookie
0x1801ea106  xor     rax, rsp
0x1801ea109  mov     [rbp+1C0h+var_40], rax
0x1801ea110  xor     r15d, r15d
0x1801ea113  mov     rsi, rdx
0x1801ea116  mov     r14d, r15d
0x1801ea119  mov     rdi, rcx
0x1801ea11c  call    cs:__imp_GetProcessHeap
0x1801ea123  nop     dword ptr [rax+rax+00h]
0x1801ea128  mov     rcx, rax; hHeap
0x1801ea12b  lea     edx, [r15+8]; dwFlags
0x1801ea12f  lea     r8d, [r15+20h]; dwBytes
0x1801ea133  mov     rbx, rax
0x1801ea136  call    cs:__imp_HeapAlloc
0x1801ea13d  nop     dword ptr [rax+rax+00h]
0x1801ea142  test    rax, rax
0x1801ea145  jz      loc_1801EA40D
0x1801ea14b  mov     dword ptr [rax+1Ch], 8
0x1801ea152  mov     rcx, rsi; pszSrch
0x1801ea155  mov     [rax+10h], rbx
0x1801ea159  mov     [rdi+330h], rax
0x1801ea160  call    cs:__imp_StrDupW
0x1801ea167  nop     dword ptr [rax+rax+00h]
0x1801ea16c  mov     rcx, [rdi+10h]; void *
0x1801ea170  mov     rbx, rax
0x1801ea173  mov     [rdi+10h], r15
0x1801ea177  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x1801ea17c  mov     [rdi+10h], rbx
0x1801ea180  test    rbx, rbx
0x1801ea183  jz      loc_1801EA3DF
0x1801ea189  mov     rcx, rsi; pszSubKey
0x1801ea18c  call    ?_AddProgidForExt@@YAXPEBG@Z; _AddProgidForExt(ushort const *)
0x1801ea191  lea     rcx, [rdi+18h]; this
0x1801ea195  mov     r8, rsi; unsigned __int16 *
0x1801ea198  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1801ea19f  call    ?Init@CDefaultProgramsMatches@@QEAAJPEAUHKEY__@@PEBG@Z; CDefaultProgramsMatches::Init(HKEY__ *,ushort const *)
0x1801ea1a4  lea     rcx, [rdi+58h]; this
0x1801ea1a8  mov     r8, rsi; unsigned __int16 *
0x1801ea1ab  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x1801ea1b2  call    ?Init@CDefaultProgramsMatches@@QEAAJPEAUHKEY__@@PEBG@Z; CDefaultProgramsMatches::Init(HKEY__ *,ushort const *)
0x1801ea1b7  mov     r13d, 104h
0x1801ea1bd  lea     rbx, [rdi+98h]
0x1801ea1c4  lea     r14d, [r15+40h]
0x1801ea1c8  mov     edx, r13d; unsigned __int64
0x1801ea1cb  mov     r9, rsi
0x1801ea1ce  mov     [rbx+0Ch], r14d
0x1801ea1d2  lea     r8, aSOpenwithprogi; "%s\\OpenWithProgids"
0x1801ea1d9  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801ea1de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ea1e3  mov     [rsp+2C0h+phkResult], rbx; phkResult
0x1801ea1e8  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801ea1ed  mov     ebx, 20019h
0x1801ea1f2  mov     r12, 0FFFFFFFF80000000h
0x1801ea1f9  mov     r9d, ebx; samDesired
0x1801ea1fc  xor     r8d, r8d; ulOptions
0x1801ea1ff  mov     rcx, r12; hKey
0x1801ea202  call    cs:__imp_RegOpenKeyExW
0x1801ea209  nop     dword ptr [rax+rax+00h]
0x1801ea20e  lea     r9d, [r15+9]
0x1801ea212  mov     [rdi+0B4h], r14d
0x1801ea219  xor     r8d, r8d
0x1801ea21c  lea     rdx, [rsp+2C0h+SubKey]
0x1801ea221  mov     ecx, 6001h
0x1801ea226  call    cs:__imp_SHGetShellKeyEx
0x1801ea22d  nop     dword ptr [rax+rax+00h]
0x1801ea232  lea     rcx, [rdi+0B8h]; this
0x1801ea239  mov     rdx, rsi; unsigned __int16 *
0x1801ea23c  mov     [rdi+0A8h], rax
0x1801ea243  call    ?Init@CMRUEnumHandlers@@QEAAHPEBG@Z; CMRUEnumHandlers::Init(ushort const *)
0x1801ea248  mov     r9, rsi
0x1801ea24b  mov     [rdi+2D0h], eax
0x1801ea251  lea     r8, aSOpenwithlist; "%s\\OpenWithList"
0x1801ea258  mov     edx, r13d; unsigned __int64
0x1801ea25b  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801ea260  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ea265  lea     rax, [rdi+2D8h]
0x1801ea26c  mov     r9d, ebx; samDesired
0x1801ea26f  xor     r8d, r8d; ulOptions
0x1801ea272  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801ea277  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801ea27c  mov     rcx, r12; hKey
0x1801ea27f  call    cs:__imp_RegOpenKeyExW
0x1801ea286  nop     dword ptr [rax+rax+00h]
0x1801ea28b  mov     r14d, 80h
0x1801ea291  mov     [rsp+2C0h+ptype], r15d
0x1801ea296  lea     r9, [rsp+2C0h+ppszType]; ppszType
0x1801ea29b  mov     [rdi+2E4h], r14d
0x1801ea2a2  lea     r8, [rsp+2C0h+pflag]; pflag
0x1801ea2a7  mov     [rsp+2C0h+pflag], r15d
0x1801ea2ac  lea     rdx, [rsp+2C0h+ptype]; ptype
0x1801ea2b1  mov     [rsp+2C0h+ppszType], r15
0x1801ea2b6  mov     rcx, rsi; pszExt
0x1801ea2b9  call    cs:__imp_AssocGetPerceivedType
0x1801ea2c0  nop     dword ptr [rax+rax+00h]
0x1801ea2c5  test    eax, eax
0x1801ea2c7  jns     loc_1801EA416
0x1801ea2cd  lea     rax, [rdi+308h]
0x1801ea2d4  mov     [rdi+2F4h], r14d
0x1801ea2db  mov     r9d, ebx; samDesired
0x1801ea2de  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801ea2e3  xor     r8d, r8d; ulOptions
0x1801ea2e6  mov     [rdi+304h], r14d
0x1801ea2ed  lea     rdx, aOpenwithprogid; "*\\OpenWithProgids"
0x1801ea2f4  mov     rcx, r12; hKey
0x1801ea2f7  call    cs:__imp_RegOpenKeyExW
0x1801ea2fe  nop     dword ptr [rax+rax+00h]
0x1801ea303  lea     rax, [rdi+318h]
0x1801ea30a  mov     dword ptr [rdi+314h], 200h
0x1801ea314  mov     r9d, ebx; samDesired
0x1801ea317  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801ea31c  xor     r8d, r8d; ulOptions
0x1801ea31f  lea     rdx, aApplications; "Applications"
0x1801ea326  mov     rcx, r12; hKey
0x1801ea329  call    cs:__imp_RegOpenKeyExW
0x1801ea330  nop     dword ptr [rax+rax+00h]
0x1801ea335  mov     dword ptr [rdi+324h], 10h
0x1801ea33f  mov     r14d, 1
0x1801ea345  call    ?IsBrowserReplacementFeaturePresent@@YA_NXZ; IsBrowserReplacementFeaturePresent(void)
0x1801ea34a  test    al, al
0x1801ea34c  jz      loc_1801EA3DF
0x1801ea352  lea     rax, aEpub; ".epub"
0x1801ea359  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801ea35d  mov     [rsp+2C0h+var_290], rax
0x1801ea362  mov     rdi, r12
0x1801ea365  lea     rax, aHtm; ".htm"
0x1801ea36c  mov     [rsp+2C0h+var_288], rax
0x1801ea371  lea     rax, aHtml; ".html"
0x1801ea378  mov     [rsp+2C0h+var_280], rax
0x1801ea37d  lea     rax, aPdf; ".pdf"
0x1801ea384  mov     [rsp+2C0h+var_278], rax
0x1801ea389  lea     rax, aSvg; ".svg"
0x1801ea390  mov     [rsp+2C0h+var_270], rax
0x1801ea395  lea     rax, aXml_0; ".xml"
0x1801ea39c  mov     [rsp+2C0h+var_268], rax
0x1801ea3a1  inc     rdi
0x1801ea3a4  cmp     [rsi+rdi*2], r15w
0x1801ea3a9  jnz     short loc_1801EA3A1
0x1801ea3ab  lea     rbx, [rsp+2C0h+var_290]
0x1801ea3b0  mov     r8, [rbx]; lpString2
0x1801ea3b3  mov     r9d, r12d; cchCount2
0x1801ea3b6  mov     edx, edi; cchCount1
0x1801ea3b8  mov     dword ptr [rsp+2C0h+phkResult], r14d; bIgnoreCase
0x1801ea3bd  mov     rcx, rsi; lpString1
0x1801ea3c0  call    cs:__imp_CompareStringOrdinal
0x1801ea3c7  nop     dword ptr [rax+rax+00h]
0x1801ea3cc  cmp     eax, 2
0x1801ea3cf  jz      short loc_1801EA3DF
0x1801ea3d1  add     rbx, 8
0x1801ea3d5  lea     rax, [rsp+2C0h+ppszType]
0x1801ea3da  cmp     rbx, rax
0x1801ea3dd  jnz     short loc_1801EA3B0
0x1801ea3df  mov     eax, r14d
0x1801ea3e2  mov     rcx, [rbp+1C0h+var_40]
0x1801ea3e9  xor     rcx, rsp; StackCookie
0x1801ea3ec  call    __security_check_cookie
0x1801ea3f1  mov     rbx, [rsp+2C0h+arg_10]
0x1801ea3f9  add     rsp, 290h
0x1801ea400  pop     r15
0x1801ea402  pop     r14
0x1801ea404  pop     r13
0x1801ea406  pop     r12
0x1801ea408  pop     rdi
0x1801ea409  pop     rsi
0x1801ea40a  pop     rbp
0x1801ea40b  retn
0x1801ea40d  mov     [rdi+330h], r15
0x1801ea414  jmp     short loc_1801EA3DF
0x1801ea416  mov     r9, [rsp+2C0h+ppszType]
0x1801ea41b  lea     r8, aSystemfileasso; "SystemFileAssociations\\%s\\OpenWithLis"...
0x1801ea422  mov     rdx, r13; unsigned __int64
0x1801ea425  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801ea42a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ea42f  lea     rax, [rdi+2E8h]
0x1801ea436  mov     r9d, ebx; samDesired
0x1801ea439  xor     r8d, r8d; ulOptions
0x1801ea43c  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801ea441  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801ea446  mov     rcx, r12; hKey
0x1801ea449  call    cs:__imp_RegOpenKeyExW
0x1801ea450  nop     dword ptr [rax+rax+00h]
0x1801ea455  lea     rax, aOpenwithlist; "OpenWithList"
0x1801ea45c  mov     rdx, r13; unsigned __int64
0x1801ea45f  mov     [rsp+2C0h+var_298], rax
0x1801ea464  lea     r9, aSoftwareMicros_90; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801ea46b  mov     rax, [rsp+2C0h+ppszType]
0x1801ea470  lea     r8, aSSS; "%s\\%s\\%s"
0x1801ea477  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801ea47c  mov     [rsp+2C0h+phkResult], rax
0x1801ea481  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ea486  lea     rax, [rdi+2F8h]
0x1801ea48d  mov     r9d, ebx; samDesired
0x1801ea490  xor     r8d, r8d; ulOptions
0x1801ea493  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801ea498  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801ea49d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801ea4a4  call    cs:__imp_RegOpenKeyExW
0x1801ea4ab  nop     dword ptr [rax+rax+00h]
0x1801ea4b0  mov     rcx, [rsp+2C0h+ppszType]; pv
0x1801ea4b5  call    cs:__imp_CoTaskMemFree
0x1801ea4bc  nop     dword ptr [rax+rax+00h]
0x1801ea4c1  jmp     loc_1801EA2CD
```
