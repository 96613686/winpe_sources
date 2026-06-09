# CEnumHandlers::Init(ushort const *)

- ea: `0x1801db24c`
- end: `0x1801db5e3`
- name: `?Init@CEnumHandlers@@QEAAHPEBG@Z`
- size: `919`
- prototype: `int(CEnumHandlers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801dada0`

## callees

- `0x18003e390`
- `0x180094c70`
- `0x1801db24c`
- `0x1801db5ec`
- `0x1801db9f8`
- `0x1801dbaa8`
- `0x1801dbb78`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801db29c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801db29c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801db288`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801db288`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801db4f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801db4f6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1801db2c0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1801db2c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db35c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db3cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db439`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db465`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db578`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db5cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db35c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db3cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db439`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db465`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db578`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801db5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801db5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801db5d8`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1801db37a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1801db37a`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocGetPerceivedType` at `0x1801db401`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocGetPerceivedType` at `0x1801db401`

## string_xrefs

- `0x1801db32c`: `%s\OpenWithProgids`
- `0x1801db39f`: `%s\OpenWithList`
- `0x1801db42f`: `*\OpenWithProgids`
- `0x1801db57e`: `OpenWithList`
- `0x1801db54a`: `SystemFileAssociations\%s\OpenWithList`

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
0x1801db24c  mov     [rsp-8+arg_10], rbx
0x1801db251  push    rbp
0x1801db252  push    rsi
0x1801db253  push    rdi
0x1801db254  push    r12
0x1801db256  push    r13
0x1801db258  push    r14
0x1801db25a  push    r15
0x1801db25c  lea     rbp, [rsp-190h]
0x1801db264  sub     rsp, 290h
0x1801db26b  mov     rax, cs:__security_cookie
0x1801db272  xor     rax, rsp
0x1801db275  mov     [rbp+1C0h+var_40], rax
0x1801db27c  xor     r15d, r15d
0x1801db27f  mov     rsi, rdx
0x1801db282  mov     r14d, r15d
0x1801db285  mov     rdi, rcx
0x1801db288  call    cs:__imp_GetProcessHeap
0x1801db28e  mov     rcx, rax; hHeap
0x1801db291  lea     edx, [r15+8]; dwFlags
0x1801db295  lea     r8d, [r15+20h]; dwBytes
0x1801db299  mov     rbx, rax
0x1801db29c  call    cs:__imp_HeapAlloc
0x1801db2a2  test    rax, rax
0x1801db2a5  jz      loc_1801DB53C
0x1801db2ab  mov     dword ptr [rax+1Ch], 8
0x1801db2b2  mov     rcx, rsi; pszSrch
0x1801db2b5  mov     [rax+10h], rbx
0x1801db2b9  mov     [rdi+330h], rax
0x1801db2c0  call    cs:__imp_StrDupW
0x1801db2c6  mov     rcx, [rdi+10h]; void *
0x1801db2ca  mov     rbx, rax
0x1801db2cd  mov     [rdi+10h], r15
0x1801db2d1  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x1801db2d6  mov     [rdi+10h], rbx
0x1801db2da  test    rbx, rbx
0x1801db2dd  jz      loc_1801DB50F
0x1801db2e3  mov     rcx, rsi; pszSubKey
0x1801db2e6  call    ?_AddProgidForExt@@YAXPEBG@Z; _AddProgidForExt(ushort const *)
0x1801db2eb  lea     rcx, [rdi+18h]; this
0x1801db2ef  mov     r8, rsi; unsigned __int16 *
0x1801db2f2  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1801db2f9  call    ?Init@CDefaultProgramsMatches@@QEAAJPEAUHKEY__@@PEBG@Z; CDefaultProgramsMatches::Init(HKEY__ *,ushort const *)
0x1801db2fe  lea     rcx, [rdi+58h]; this
0x1801db302  mov     r8, rsi; unsigned __int16 *
0x1801db305  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x1801db30c  call    ?Init@CDefaultProgramsMatches@@QEAAJPEAUHKEY__@@PEBG@Z; CDefaultProgramsMatches::Init(HKEY__ *,ushort const *)
0x1801db311  mov     r13d, 104h
0x1801db317  lea     rbx, [rdi+98h]
0x1801db31e  lea     r14d, [r15+40h]
0x1801db322  mov     edx, r13d; unsigned __int64
0x1801db325  mov     r9, rsi
0x1801db328  mov     [rbx+0Ch], r14d
0x1801db32c  lea     r8, aSOpenwithprogi; "%s\\OpenWithProgids"
0x1801db333  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801db338  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801db33d  mov     [rsp+2C0h+phkResult], rbx; phkResult
0x1801db342  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801db347  mov     ebx, 20019h
0x1801db34c  mov     r12, 0FFFFFFFF80000000h
0x1801db353  mov     r9d, ebx; samDesired
0x1801db356  xor     r8d, r8d; ulOptions
0x1801db359  mov     rcx, r12; hKey
0x1801db35c  call    cs:__imp_RegOpenKeyExW
0x1801db362  lea     r9d, [r15+9]
0x1801db366  mov     [rdi+0B4h], r14d
0x1801db36d  xor     r8d, r8d
0x1801db370  lea     rdx, [rsp+2C0h+SubKey]
0x1801db375  mov     ecx, 6001h
0x1801db37a  call    cs:__imp_SHGetShellKeyEx
0x1801db380  lea     rcx, [rdi+0B8h]; this
0x1801db387  mov     rdx, rsi; unsigned __int16 *
0x1801db38a  mov     [rdi+0A8h], rax
0x1801db391  call    ?Init@CMRUEnumHandlers@@QEAAHPEBG@Z; CMRUEnumHandlers::Init(ushort const *)
0x1801db396  mov     r9, rsi
0x1801db399  mov     [rdi+2D0h], eax
0x1801db39f  lea     r8, aSOpenwithlist; "%s\\OpenWithList"
0x1801db3a6  mov     edx, r13d; unsigned __int64
0x1801db3a9  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801db3ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801db3b3  lea     rax, [rdi+2D8h]
0x1801db3ba  mov     r9d, ebx; samDesired
0x1801db3bd  xor     r8d, r8d; ulOptions
0x1801db3c0  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801db3c5  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801db3ca  mov     rcx, r12; hKey
0x1801db3cd  call    cs:__imp_RegOpenKeyExW
0x1801db3d3  mov     r14d, 80h
0x1801db3d9  mov     [rsp+2C0h+ptype], r15d
0x1801db3de  lea     r9, [rsp+2C0h+ppszType]; ppszType
0x1801db3e3  mov     [rdi+2E4h], r14d
0x1801db3ea  lea     r8, [rsp+2C0h+pflag]; pflag
0x1801db3ef  mov     [rsp+2C0h+pflag], r15d
0x1801db3f4  lea     rdx, [rsp+2C0h+ptype]; ptype
0x1801db3f9  mov     [rsp+2C0h+ppszType], r15
0x1801db3fe  mov     rcx, rsi; pszExt
0x1801db401  call    cs:__imp_AssocGetPerceivedType
0x1801db407  test    eax, eax
0x1801db409  jns     loc_1801DB545
0x1801db40f  lea     rax, [rdi+308h]
0x1801db416  mov     [rdi+2F4h], r14d
0x1801db41d  mov     r9d, ebx; samDesired
0x1801db420  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801db425  xor     r8d, r8d; ulOptions
0x1801db428  mov     [rdi+304h], r14d
0x1801db42f  lea     rdx, aOpenwithprogid; "*\\OpenWithProgids"
0x1801db436  mov     rcx, r12; hKey
0x1801db439  call    cs:__imp_RegOpenKeyExW
0x1801db43f  lea     rax, [rdi+318h]
0x1801db446  mov     dword ptr [rdi+314h], 200h
0x1801db450  mov     r9d, ebx; samDesired
0x1801db453  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801db458  xor     r8d, r8d; ulOptions
0x1801db45b  lea     rdx, aApplications; "Applications"
0x1801db462  mov     rcx, r12; hKey
0x1801db465  call    cs:__imp_RegOpenKeyExW
0x1801db46b  mov     dword ptr [rdi+324h], 10h
0x1801db475  mov     r14d, 1
0x1801db47b  call    ?IsBrowserReplacementFeaturePresent@@YA_NXZ; IsBrowserReplacementFeaturePresent(void)
0x1801db480  test    al, al
0x1801db482  jz      loc_1801DB50F
0x1801db488  lea     rax, aEpub; ".epub"
0x1801db48f  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801db493  mov     [rsp+2C0h+var_290], rax
0x1801db498  mov     rdi, r12
0x1801db49b  lea     rax, aHtm; ".htm"
0x1801db4a2  mov     [rsp+2C0h+var_288], rax
0x1801db4a7  lea     rax, aHtml; ".html"
0x1801db4ae  mov     [rsp+2C0h+var_280], rax
0x1801db4b3  lea     rax, aPdf; ".pdf"
0x1801db4ba  mov     [rsp+2C0h+var_278], rax
0x1801db4bf  lea     rax, aSvg; ".svg"
0x1801db4c6  mov     [rsp+2C0h+var_270], rax
0x1801db4cb  lea     rax, aXml_0; ".xml"
0x1801db4d2  mov     [rsp+2C0h+var_268], rax
0x1801db4d7  inc     rdi
0x1801db4da  cmp     [rsi+rdi*2], r15w
0x1801db4df  jnz     short loc_1801DB4D7
0x1801db4e1  lea     rbx, [rsp+2C0h+var_290]
0x1801db4e6  mov     r8, [rbx]; lpString2
0x1801db4e9  mov     r9d, r12d; cchCount2
0x1801db4ec  mov     edx, edi; cchCount1
0x1801db4ee  mov     dword ptr [rsp+2C0h+phkResult], r14d; bIgnoreCase
0x1801db4f3  mov     rcx, rsi; lpString1
0x1801db4f6  call    cs:__imp_CompareStringOrdinal
0x1801db4fc  cmp     eax, 2
0x1801db4ff  jz      short loc_1801DB50F
0x1801db501  add     rbx, 8
0x1801db505  lea     rax, [rsp+2C0h+ppszType]
0x1801db50a  cmp     rbx, rax
0x1801db50d  jnz     short loc_1801DB4E6
0x1801db50f  mov     eax, r14d
0x1801db512  mov     rcx, [rbp+1C0h+var_40]
0x1801db519  xor     rcx, rsp; StackCookie
0x1801db51c  call    __security_check_cookie
0x1801db521  mov     rbx, [rsp+2C0h+arg_10]
0x1801db529  add     rsp, 290h
0x1801db530  pop     r15
0x1801db532  pop     r14
0x1801db534  pop     r13
0x1801db536  pop     r12
0x1801db538  pop     rdi
0x1801db539  pop     rsi
0x1801db53a  pop     rbp
0x1801db53b  retn
0x1801db53c  mov     [rdi+330h], r15
0x1801db543  jmp     short loc_1801DB50F
0x1801db545  mov     r9, [rsp+2C0h+ppszType]
0x1801db54a  lea     r8, aSystemfileasso; "SystemFileAssociations\\%s\\OpenWithLis"...
0x1801db551  mov     rdx, r13; unsigned __int64
0x1801db554  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801db559  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801db55e  lea     rax, [rdi+2E8h]
0x1801db565  mov     r9d, ebx; samDesired
0x1801db568  xor     r8d, r8d; ulOptions
0x1801db56b  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801db570  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801db575  mov     rcx, r12; hKey
0x1801db578  call    cs:__imp_RegOpenKeyExW
0x1801db57e  lea     rax, aOpenwithlist; "OpenWithList"
0x1801db585  mov     rdx, r13; unsigned __int64
0x1801db588  mov     [rsp+2C0h+var_298], rax
0x1801db58d  lea     r9, aSoftwareMicros_90; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801db594  mov     rax, [rsp+2C0h+ppszType]
0x1801db599  lea     r8, aSSS; "%s\\%s\\%s"
0x1801db5a0  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1801db5a5  mov     [rsp+2C0h+phkResult], rax
0x1801db5aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801db5af  lea     rax, [rdi+2F8h]
0x1801db5b6  mov     r9d, ebx; samDesired
0x1801db5b9  xor     r8d, r8d; ulOptions
0x1801db5bc  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801db5c1  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1801db5c6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801db5cd  call    cs:__imp_RegOpenKeyExW
0x1801db5d3  mov     rcx, [rsp+2C0h+ppszType]; pv
0x1801db5d8  call    cs:__imp_CoTaskMemFree
0x1801db5de  jmp     loc_1801DB40F
```
