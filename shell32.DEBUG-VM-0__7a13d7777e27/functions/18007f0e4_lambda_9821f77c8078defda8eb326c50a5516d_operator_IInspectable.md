# _lambda_9821f77c8078defda8eb326c50a5516d_::operator()(IInspectable *)

- ea: `0x18007f0e4`
- end: `0x18007f518`
- name: `??R_lambda_9821f77c8078defda8eb326c50a5516d_@@QEBA@PEAUIInspectable@@@Z`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007f520`

## callees

- `0x18000f05c`
- `0x18003cd64`
- `0x18007eb78`
- `0x18007f0e4`
- `0x18007fd9c`
- `0x18007fdc8`
- `0x1800803e4`
- `0x180080b90`
- `0x180080c24`
- `0x1801a1ecc`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007f46f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007f489`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007f46f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007f489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f4ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f2e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f4ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f2e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f4ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f1c4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f313`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f313`

## string_xrefs

- `0x18007f3c8`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f3fe`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f41d`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f450`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f498`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f4bb`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f1bd`: `@ShellNewCommandParameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_9821f77c8078defda8eb326c50a5516d_::operator()(__int64 a1, StateRepoHelpers *a2)
{
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v3; // r15
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(StateRepoHelpers *, GUID *, HSTRING *); // rbx
  int v6; // eax
  unsigned int InfoForShellNewEntry; // ebx
  HSTRING v8; // rbx
  __int64 v9; // rsi
  signed int v10; // eax
  int v11; // eax
  HSTRING v12; // rbx
  __int64 v13; // rsi
  signed int v14; // eax
  char v15; // bl
  HSTRING v16; // rcx
  HSTRING *v18; // r9
  int v19; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int Reserved1; // edx
  NewMenuEntry *v22; // rcx
  __int64 v23; // rcx
  const WCHAR *v24; // rax
  unsigned int v25; // edx
  NewMenuEntry *v26; // rcx
  __int64 v27; // rax
  NewMenuEntry *v28; // rbx
  const unsigned __int16 *v29; // rax
  StateRepoNewMenuCache *v30; // rcx
  unsigned int v31; // edx
  NewMenuEntry *v32; // rcx
  HSTRING v33; // rcx
  __int64 v34; // rdx
  int v35; // [rsp+20h] [rbp-60h]
  int v36; // [rsp+20h] [rbp-60h]
  int v37; // [rsp+20h] [rbp-60h]
  int v38; // [rsp+20h] [rbp-60h]
  void *v39; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  LPWSTR ppwsz; // [rsp+58h] [rbp-28h] BYREF
  char v43; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v44[7]; // [rsp+61h] [rbp-1Fh] BYREF
  HSTRING v45; // [rsp+68h] [rbp-18h] BYREF
  NewMenuEntry *v46; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v3 = **(struct Windows::Internal::StateRepository::IFileTypeAssociation ***)(a1 + 16);
  v4 = *(_QWORD *)(a1 + 8);
  v45 = 0;
  v5 = **(__int64 (__fastcall ***)(StateRepoHelpers *, GUID *, HSTRING *))a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  v6 = v5(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v45);
  InfoForShellNewEntry = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v6,
      v35);
    v33 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_36;
  }
  v43 = 0;
  v8 = v45;
  v9 = *(_QWORD *)v45;
  string = 0;
  v10 = WindowsCreateStringReference(L"@ShellNewFileName", 0x11u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    RaiseException(v10, 1u, 0, 0);
    __debugbreak();
  }
  v11 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, char *))(v9 + 64))(v8, string, &v43);
  InfoForShellNewEntry = v11;
  if ( v11 < 0 )
  {
    v34 = 213;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v11,
      v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)InfoForShellNewEntry,
      v38);
    goto LABEL_33;
  }
  v44[0] = 0;
  v12 = v45;
  v13 = *(_QWORD *)v45;
  string = 0;
  v14 = WindowsCreateStringReference(L"@ShellNewCommandParameters", 0x1Au, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  v11 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, _BYTE *))(v13 + 64))(v12, string, v44);
  InfoForShellNewEntry = v11;
  if ( v11 < 0 )
  {
    v34 = 215;
    goto LABEL_41;
  }
  if ( v43 || (v15 = 0, v44[0]) )
    v15 = 1;
  v16 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( !v15 )
    return 0;
  v45 = 0;
  WindowsDeleteString(0);
  v45 = 0;
  v19 = StateRepoHelpers::LookupStringInPropertySet(
          a2,
          (struct IInspectable *)&stru_1805D8078,
          (const unsigned __int16 *)&v45,
          v18);
  InfoForShellNewEntry = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)(unsigned int)v19,
      v35);
  }
  else
  {
    v46 = 0;
    hstringHeader.Reserved.Reserved1 = &v46;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    StringRawBuffer = WindowsGetStringRawBuffer(v45, 0);
    InfoForShellNewEntry = StateRepoNewMenuCache::GetInfoForShellNewEntry(
                             (StateRepoNewMenuCache *)&hstringHeader.Reserved.Reserved2[8],
                             StringRawBuffer,
                             v3,
                             (struct IInspectable *)a2,
                             (struct NewMenuEntry **)&hstringHeader.Reserved.Reserved2[8]);
    if ( hstringHeader.Reserved.Reserved2[16] )
    {
      Reserved1 = (unsigned int)hstringHeader.Reserved.Reserved1;
      v22 = *(NewMenuEntry **)hstringHeader.Reserved.Reserved1;
      *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
      if ( v22 )
        NewMenuEntry::`scalar deleting destructor'(v22, Reserved1);
    }
    if ( (InfoForShellNewEntry & 0x80000000) == 0 )
    {
      ppwsz = (LPWSTR)WindowsGetStringRawBuffer(v45, 0);
      v23 = *(_QWORD *)(v4 + 16);
      if ( v23
        && (v27 = CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                    v23,
                    *(unsigned int *)(v4 + 4),
                    &ppwsz),
            *(_DWORD *)v27 == 1) )
      {
        v28 = *(NewMenuEntry **)(v27 + 16);
        v29 = WindowsGetStringRawBuffer(v45, 0);
        if ( StateRepoNewMenuCache::IsDefaultHandler(v30, v29, v3) )
        {
          ppwsz = (LPWSTR)v46;
          v39 = (void *)WindowsGetStringRawBuffer(v45, 0);
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v4,
                      0,
                      &v39,
                      &ppwsz) >= 0 )
          {
            if ( v28 )
              NewMenuEntry::`scalar deleting destructor'(v28, v25);
            goto LABEL_29;
          }
        }
      }
      else
      {
        v39 = v46;
        v24 = WindowsGetStringRawBuffer(v45, 0);
        ppwsz = 0;
        if ( SHStrDupW(v24, &ppwsz) >= 0 )
        {
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v4,
                      1,
                      &ppwsz,
                      &v39) >= 0 )
          {
            v39 = (void *)WindowsGetStringRawBuffer(v45, 0);
            FileExplorerTelemetry::ShellNew_CentennialExtCached<unsigned short const *>(&v39);
LABEL_29:
            v26 = 0;
            goto LABEL_20;
          }
          CoTaskMemFree(ppwsz);
        }
      }
      v26 = v46;
LABEL_20:
      v46 = 0;
      if ( v26 )
        NewMenuEntry::`scalar deleting destructor'(v26, v25);
      WindowsDeleteString(v45);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)InfoForShellNewEntry,
      v36);
    v32 = v46;
    v46 = 0;
    if ( v32 )
      NewMenuEntry::`scalar deleting destructor'(v32, v31);
  }
  WindowsDeleteString(v45);
LABEL_33:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x205,
    (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
    (const char *)InfoForShellNewEntry,
    v37);
  return InfoForShellNewEntry;
}

```

## disassembly

```asm
0x18007f0e4  mov     [rsp-28h+arg_10], rbx
0x18007f0e9  mov     [rsp-28h+arg_18], rsi
0x18007f0ee  push    rbp
0x18007f0ef  push    rdi
0x18007f0f0  push    r12
0x18007f0f2  push    r14
0x18007f0f4  push    r15
0x18007f0f6  mov     rbp, rsp
0x18007f0f9  sub     rsp, 80h
0x18007f100  mov     rax, cs:__security_cookie
0x18007f107  xor     rax, rsp
0x18007f10a  mov     [rbp+var_8], rax
0x18007f10e  mov     r14, rdx
0x18007f111  mov     rax, [rcx+10h]
0x18007f115  mov     r15, [rax]
0x18007f118  mov     rdi, [rcx+8]
0x18007f11c  xor     r12d, r12d
0x18007f11f  mov     [rbp+var_18], r12
0x18007f123  mov     rax, [rdx]
0x18007f126  mov     rbx, [rax]
0x18007f129  lea     rcx, [rbp+var_18]
0x18007f12d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f132  lea     r8, [rbp+var_18]
0x18007f136  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007f13d  mov     rcx, r14
0x18007f140  mov     rax, rbx
0x18007f143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f148  mov     ebx, eax
0x18007f14a  test    eax, eax
0x18007f14c  js      loc_18007F416
0x18007f152  mov     [rbp+var_20], r12b
0x18007f156  mov     rbx, [rbp+var_18]
0x18007f15a  mov     rsi, [rbx]
0x18007f15d  mov     [rbp+string], r12
0x18007f161  lea     r9, [rbp+string]; string
0x18007f165  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007f169  lea     edx, [r12+11h]; length
0x18007f16e  lea     rcx, sourceString; "@ShellNewFileName"
0x18007f175  call    cs:__imp_WindowsCreateStringReference
0x18007f17b  test    eax, eax
0x18007f17d  js      loc_18007F463
0x18007f183  lea     r8, [rbp+var_20]
0x18007f187  mov     rdx, [rbp+string]
0x18007f18b  mov     rcx, rbx
0x18007f18e  mov     rax, [rsi+40h]
0x18007f192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f197  mov     ebx, eax
0x18007f199  test    eax, eax
0x18007f19b  js      loc_18007F476
0x18007f1a1  mov     [rbp+var_1F], r12b
0x18007f1a5  mov     rbx, [rbp+var_18]
0x18007f1a9  mov     rsi, [rbx]
0x18007f1ac  mov     [rbp+string], r12
0x18007f1b0  lea     r9, [rbp+string]; string
0x18007f1b4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007f1b8  lea     edx, [r12+1Ah]; length
0x18007f1bd  lea     rcx, aShellnewcomman; "@ShellNewCommandParameters"
0x18007f1c4  call    cs:__imp_WindowsCreateStringReference
0x18007f1ca  test    eax, eax
0x18007f1cc  js      loc_18007F47D
0x18007f1d2  lea     r8, [rbp+var_1F]
0x18007f1d6  mov     rdx, [rbp+string]
0x18007f1da  mov     rcx, rbx
0x18007f1dd  mov     rax, [rsi+40h]
0x18007f1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1e6  mov     ebx, eax
0x18007f1e8  test    eax, eax
0x18007f1ea  js      loc_18007F490
0x18007f1f0  cmp     [rbp+var_20], r12b
0x18007f1f4  jnz     loc_18007F343
0x18007f1fa  cmp     [rbp+var_1F], r12b
0x18007f1fe  mov     bl, r12b
0x18007f201  jnz     loc_18007F343
0x18007f207  mov     rcx, [rbp+var_18]
0x18007f20b  test    rcx, rcx
0x18007f20e  jz      short loc_18007F221
0x18007f210  mov     [rbp+var_18], r12
0x18007f214  mov     rax, [rcx]
0x18007f217  mov     rax, [rax+10h]
0x18007f21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f220  nop
0x18007f221  test    bl, bl
0x18007f223  jnz     short loc_18007F24F
0x18007f225  xor     eax, eax
0x18007f227  mov     rcx, [rbp+var_8]
0x18007f22b  xor     rcx, rsp; StackCookie
0x18007f22e  call    __security_check_cookie
0x18007f233  lea     r11, [rsp+80h+var_s0]
0x18007f23b  mov     rbx, [r11+40h]
0x18007f23f  mov     rsi, [r11+48h]
0x18007f243  mov     rsp, r11
0x18007f246  pop     r15
0x18007f248  pop     r14
0x18007f24a  pop     r12
0x18007f24c  pop     rdi
0x18007f24d  pop     rbp
0x18007f24e  retn
0x18007f24f  mov     [rbp+var_18], r12
0x18007f253  xor     ecx, ecx; string
0x18007f255  call    cs:__imp_WindowsDeleteString
0x18007f25b  mov     [rbp+var_18], r12
0x18007f25f  lea     r8, [rbp+var_18]; unsigned __int16 *
0x18007f263  lea     rdx, stru_1805D8078; struct IInspectable *
0x18007f26a  mov     rcx, r14; this
0x18007f26d  call    ?LookupStringInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; StateRepoHelpers::LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x18007f272  mov     ebx, eax
0x18007f274  test    eax, eax
0x18007f276  js      loc_18007F4B4
0x18007f27c  mov     [rbp+var_10], r12
0x18007f280  lea     rax, [rbp+var_10]
0x18007f284  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18007f288  mov     qword ptr [rbp+hstringHeader.Reserved+8], r12
0x18007f28c  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18007f290  xor     edx, edx; length
0x18007f292  mov     rcx, [rbp+var_18]; string
0x18007f296  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f29c  lea     rcx, [rbp+hstringHeader.Reserved+8]; this
0x18007f2a0  mov     qword ptr [rsp+80h+var_60], rcx; int
0x18007f2a5  mov     r9, r14; struct IInspectable *
0x18007f2a8  mov     r8, r15; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007f2ab  mov     rdx, rax; unsigned __int16 *
0x18007f2ae  call    ?GetInfoForShellNewEntry@StateRepoNewMenuCache@@AEAAJPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@PEAUIInspectable@@PEAPEAUNewMenuEntry@@@Z; StateRepoNewMenuCache::GetInfoForShellNewEntry(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *,IInspectable *,NewMenuEntry * *)
0x18007f2b3  mov     ebx, eax
0x18007f2b5  cmp     byte ptr [rbp+hstringHeader.Reserved+10h], r12b
0x18007f2b9  jz      short loc_18007F2D3
0x18007f2bb  mov     rdx, qword ptr [rbp+hstringHeader.Reserved]; unsigned int
0x18007f2bf  mov     rcx, [rdx]; this
0x18007f2c2  mov     rax, qword ptr [rbp+hstringHeader.Reserved+8]
0x18007f2c6  mov     [rdx], rax
0x18007f2c9  test    rcx, rcx
0x18007f2cc  jz      short loc_18007F2D3
0x18007f2ce  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007f2d3  test    ebx, ebx
0x18007f2d5  js      loc_18007F3C1
0x18007f2db  xor     edx, edx; length
0x18007f2dd  mov     rcx, [rbp+var_18]; string
0x18007f2e1  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f2e7  mov     [rbp+ppwsz], rax
0x18007f2eb  mov     rcx, [rdi+10h]
0x18007f2ef  test    rcx, rcx
0x18007f2f2  jnz     short loc_18007F34A
0x18007f2f4  mov     rax, [rbp+var_10]
0x18007f2f8  mov     [rbp+var_50], rax
0x18007f2fc  xor     edx, edx; length
0x18007f2fe  mov     rcx, [rbp+var_18]; string
0x18007f302  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f308  mov     [rbp+ppwsz], r12
0x18007f30c  lea     rdx, [rbp+ppwsz]; ppwsz
0x18007f310  mov     rcx, rax; psz
0x18007f313  call    cs:__imp_SHStrDupW
0x18007f319  test    eax, eax
0x18007f31b  jns     loc_18007F4D1
0x18007f321  mov     rcx, [rbp+var_10]; this
0x18007f325  mov     [rbp+var_10], r12
0x18007f329  test    rcx, rcx
0x18007f32c  jz      short loc_18007F334
0x18007f32e  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007f333  nop
0x18007f334  mov     rcx, [rbp+var_18]; string
0x18007f338  call    cs:__imp_WindowsDeleteString
0x18007f33e  jmp     loc_18007F225
0x18007f343  mov     bl, 1
0x18007f345  jmp     loc_18007F207
0x18007f34a  lea     r8, [rbp+ppwsz]
0x18007f34e  mov     edx, [rdi+4]
0x18007f351  call    ?s_LookupEntry@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAAEAVHashBucket@1@PEAV21@IAEBQEBG@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::HashBucket *,uint,ushort const * const &)
0x18007f356  cmp     dword ptr [rax], 1
0x18007f359  jnz     short loc_18007F2F4
0x18007f35b  mov     rbx, [rax+10h]
0x18007f35f  xor     edx, edx; length
0x18007f361  mov     rcx, [rbp+var_18]; string
0x18007f365  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f36b  mov     r8, r15; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007f36e  mov     rdx, rax; unsigned __int16 *
0x18007f371  call    ?IsDefaultHandler@StateRepoNewMenuCache@@AEAA_NPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@@Z; StateRepoNewMenuCache::IsDefaultHandler(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *)
0x18007f376  test    al, al
0x18007f378  jz      short loc_18007F321
0x18007f37a  mov     rax, [rbp+var_10]
0x18007f37e  mov     [rbp+ppwsz], rax
0x18007f382  xor     edx, edx; length
0x18007f384  mov     rcx, [rbp+var_18]; string
0x18007f388  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f38e  mov     [rbp+var_50], rax
0x18007f392  lea     r9, [rbp+ppwsz]
0x18007f396  lea     r8, [rbp+var_50]
0x18007f39a  xor     edx, edx
0x18007f39c  mov     rcx, rdi
0x18007f39f  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBQEAUNewMenuEntry@@PEAPEAU2@@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,NewMenuEntry * const &,NewMenuEntry * *)
0x18007f3a4  test    eax, eax
0x18007f3a6  js      loc_18007F321
0x18007f3ac  test    rbx, rbx
0x18007f3af  jz      short loc_18007F3B9
0x18007f3b1  mov     rcx, rbx; this
0x18007f3b4  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007f3b9  mov     rcx, r12
0x18007f3bc  jmp     loc_18007F325
0x18007f3c1  mov     rcx, [rbp+28h]; this
0x18007f3c5  mov     r9d, ebx; char *
0x18007f3c8  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007f3cf  mov     edx, 1CEh; void *
0x18007f3d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f3d9  nop
0x18007f3da  mov     rcx, [rbp+var_10]; this
0x18007f3de  mov     [rbp+var_10], r12
0x18007f3e2  test    rcx, rcx
0x18007f3e5  jz      short loc_18007F3ED
0x18007f3e7  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007f3ec  nop
0x18007f3ed  mov     rcx, [rbp+var_18]; string
0x18007f3f1  call    cs:__imp_WindowsDeleteString
0x18007f3f7  mov     rcx, [rbp+28h]; this
0x18007f3fb  mov     r9d, ebx; char *
0x18007f3fe  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007f405  mov     edx, 205h; void *
0x18007f40a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f40f  mov     eax, ebx
0x18007f411  jmp     loc_18007F227
0x18007f416  mov     rcx, [rbp+28h]; this
0x18007f41a  mov     r9d, eax; char *
0x18007f41d  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007f424  mov     edx, 0D0h; void *
0x18007f429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f42e  nop
0x18007f42f  mov     rcx, [rbp+var_18]
0x18007f433  test    rcx, rcx
0x18007f436  jz      short loc_18007F449
0x18007f438  mov     [rbp+var_18], r12
0x18007f43c  mov     rax, [rcx]
0x18007f43f  mov     rax, [rax+10h]
0x18007f443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f448  nop
0x18007f449  mov     rcx, [rbp+28h]; this
0x18007f44d  mov     r9d, ebx; char *
0x18007f450  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007f457  mov     edx, 1C6h; void *
0x18007f45c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f461  jmp     short loc_18007F3F7
0x18007f463  xor     r9d, r9d; lpArguments
0x18007f466  xor     r8d, r8d; nNumberOfArguments
0x18007f469  lea     edx, [r9+1]; dwExceptionFlags
0x18007f46d  mov     ecx, eax; dwExceptionCode
0x18007f46f  call    cs:__imp_RaiseException
0x18007f475  int     3; Trap to Debugger
0x18007f476  mov     edx, 0D5h
0x18007f47b  jmp     short loc_18007F495
0x18007f47d  xor     r9d, r9d; lpArguments
0x18007f480  xor     r8d, r8d; nNumberOfArguments
0x18007f483  lea     edx, [r9+1]; dwExceptionFlags
0x18007f487  mov     ecx, eax; dwExceptionCode
0x18007f489  call    cs:__imp_RaiseException
0x18007f48f  int     3; Trap to Debugger
0x18007f490  mov     edx, 0D7h; void *
0x18007f495  mov     r9d, eax; char *
0x18007f498  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007f49f  mov     rcx, [rbp+28h]; this
0x18007f4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f4a8  nop
0x18007f4a9  lea     rcx, [rbp+var_18]
0x18007f4ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f4b2  jmp     short loc_18007F449
0x18007f4b4  mov     rcx, [rbp+28h]; this
0x18007f4b8  mov     r9d, eax; char *
0x18007f4bb  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007f4c2  mov     edx, 1CBh; void *
0x18007f4c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f4cc  jmp     loc_18007F3ED
0x18007f4d1  lea     r9, [rbp+var_50]
0x18007f4d5  lea     r8, [rbp+ppwsz]
0x18007f4d9  mov     edx, 1
0x18007f4de  mov     rcx, rdi
0x18007f4e1  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBQEAUNewMenuEntry@@PEAPEAU2@@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,NewMenuEntry * const &,NewMenuEntry * *)
0x18007f4e6  test    eax, eax
0x18007f4e8  jns     short loc_18007F4F9
0x18007f4ea  mov     rcx, [rbp+ppwsz]; pv
0x18007f4ee  call    cs:__imp_CoTaskMemFree
0x18007f4f4  jmp     loc_18007F321
0x18007f4f9  xor     edx, edx; length
0x18007f4fb  mov     rcx, [rbp+var_18]; string
0x18007f4ff  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f505  mov     [rbp+var_50], rax
0x18007f509  lea     rcx, [rbp+var_50]
0x18007f50d  call    ??$ShellNew_CentennialExtCached@PEBG@FileExplorerTelemetry@@SAX$$QEAPEBG@Z; FileExplorerTelemetry::ShellNew_CentennialExtCached<ushort const *>(ushort const * &&)
0x18007f512  jmp     loc_18007F3B9
```
