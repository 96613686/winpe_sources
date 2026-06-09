# CThemeFile::GetThemeMagicValue(ushort * *)

- ea: `0x180009610`
- end: `0x1800097a4`
- name: `?GetThemeMagicValue@CThemeFile@@UEAAJPEAPEAG@Z`
- size: `404`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180009610`
- `0x18000a9a0`
- `0x18000dd60`
- `0x1800358c0`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009794`
- `OLEAUT32!__imp_SysAllocString` at `0x1800096ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800096ab`

## pseudocode

```c
__int64 __fastcall CThemeFile::GetThemeMagicValue(CThemeFile *this, unsigned __int16 **a2)
{
  OLECHAR *v3; // rdi
  int CachedProfile; // ebx
  unsigned __int16 *v6; // rax
  int v7; // eax
  struct ICachedPrivateProfile *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  struct ICachedPrivateProfile *v12; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR *v13; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[528]; // [rsp+270h] [rbp+170h] BYREF

  *a2 = 0;
  v3 = 0;
  v13 = 0;
  v12 = 0;
  CachedProfile = CThemeFile::_GetCachedProfile((CThemeFile *)((char *)this - 16), 1, &v12);
  if ( CachedProfile >= 0 )
  {
    pv = 0;
    v7 = StringCchPrintfW(v14, 0x104u, L"%s.MUI", L"MTSM");
    v8 = v12;
    if ( v7 >= 0
      && (*(int (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPVOID *))(*(_QWORD *)v12 + 48LL))(
           v12,
           L"MasterThemeSelector",
           v14,
           0,
           1,
           &pv) >= 0
      || (CachedProfile = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, const WCHAR *, _QWORD, int, LPVOID *))(*(_QWORD *)v8 + 48LL))(
                            v8,
                            L"MasterThemeSelector",
                            L"MTSM",
                            0,
                            1,
                            &pv),
          CachedProfile >= 0) )
    {
      memset_0(v15, 0, 0x208u);
      CachedProfile = _AllocString<CTCoAllocPolicy>(v10, v9, pv, &v13);
      CoTaskMemFree(pv);
      v3 = v13;
    }
    (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( CachedProfile >= 0 )
    {
      CachedProfile = 0;
      v6 = SysAllocString(v3);
      *a2 = v6;
      if ( v3 && !v6 )
        CachedProfile = -2147024882;
      CoTaskMemFree(v3);
    }
  }
  return (unsigned int)CachedProfile;
}

```

## disassembly

```asm
0x180009610  mov     [rsp-8+arg_10], rbx
0x180009615  mov     [rsp-8+arg_18], rsi
0x18000961a  push    rbp
0x18000961b  push    rdi
0x18000961c  push    r14
0x18000961e  lea     rbp, [rsp-390h]
0x180009626  sub     rsp, 490h
0x18000962d  mov     rax, cs:__security_cookie
0x180009634  xor     rax, rsp
0x180009637  mov     [rbp+3A0h+var_20], rax
0x18000963e  mov     r14, rdx
0x180009641  mov     qword ptr [rdx], 0
0x180009648  xor     edi, edi
0x18000964a  lea     r8, [rsp+4A0h+var_458]; struct ICachedPrivateProfile **
0x18000964f  mov     dl, 1; bool
0x180009651  mov     [rsp+4A0h+var_450], rdi
0x180009656  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18000965a  mov     [rsp+4A0h+var_458], rdi
0x18000965f  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180009664  mov     ebx, eax
0x180009666  test    eax, eax
0x180009668  jns     short loc_1800096CF
0x18000966a  mov     eax, ebx
0x18000966c  mov     rcx, [rbp+3A0h+var_20]
0x180009673  xor     rcx, rsp; StackCookie
0x180009676  call    __security_check_cookie
0x18000967b  lea     r11, [rsp+4A0h+var_10]
0x180009683  mov     rbx, [r11+30h]
0x180009687  mov     rsi, [r11+38h]
0x18000968b  mov     rsp, r11
0x18000968e  pop     r14
0x180009690  pop     rdi
0x180009691  pop     rbp
0x180009692  retn
0x180009693  mov     rax, [rsi]
0x180009696  mov     rcx, rsi
0x180009699  mov     rax, [rax+10h]
0x18000969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a2  test    ebx, ebx
0x1800096a4  js      short loc_18000966A
0x1800096a6  mov     rcx, rdi; psz
0x1800096a9  xor     ebx, ebx
0x1800096ab  call    cs:__imp_SysAllocString
0x1800096b1  mov     [r14], rax
0x1800096b4  test    rdi, rdi
0x1800096b7  jz      short loc_1800096C4
0x1800096b9  test    rax, rax
0x1800096bc  mov     ecx, 8007000Eh
0x1800096c1  cmovz   ebx, ecx
0x1800096c4  mov     rcx, rdi; pv
0x1800096c7  call    cs:__imp_CoTaskMemFree
0x1800096cd  jmp     short loc_18000966A
0x1800096cf  lea     r9, KeyName; "MTSM"
0x1800096d6  mov     [rsp+4A0h+pv], rdi
0x1800096db  lea     r8, aSMui; "%s.MUI"
0x1800096e2  mov     edx, 104h; unsigned __int64
0x1800096e7  lea     rcx, [rsp+4A0h+var_440]; unsigned __int16 *
0x1800096ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800096f1  mov     rsi, [rsp+4A0h+var_458]
0x1800096f6  test    eax, eax
0x1800096f8  js      short loc_18000972E
0x1800096fa  mov     rax, [rsi]
0x1800096fd  lea     rcx, [rsp+4A0h+pv]
0x180009702  mov     [rsp+4A0h+var_478], rcx
0x180009707  lea     r8, [rsp+4A0h+var_440]
0x18000970c  xor     r9d, r9d
0x18000970f  mov     [rsp+4A0h+var_480], 1
0x180009717  lea     rdx, AppName; "MasterThemeSelector"
0x18000971e  mov     rcx, rsi
0x180009721  mov     rax, [rax+30h]
0x180009725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000972a  test    eax, eax
0x18000972c  jns     short loc_18000976A
0x18000972e  mov     rax, [rsi]
0x180009731  lea     rcx, [rsp+4A0h+pv]
0x180009736  mov     [rsp+4A0h+var_478], rcx
0x18000973b  lea     r8, KeyName; "MTSM"
0x180009742  xor     r9d, r9d
0x180009745  mov     [rsp+4A0h+var_480], 1
0x18000974d  lea     rdx, AppName; "MasterThemeSelector"
0x180009754  mov     rcx, rsi
0x180009757  mov     rax, [rax+30h]
0x18000975b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009760  mov     ebx, eax
0x180009762  test    eax, eax
0x180009764  js      loc_180009693
0x18000976a  xor     edx, edx; Val
0x18000976c  lea     rcx, [rbp+3A0h+var_230]; void *
0x180009773  mov     r8d, 208h; Size
0x180009779  call    memset_0
0x18000977e  mov     r8, [rsp+4A0h+pv]
0x180009783  lea     r9, [rsp+4A0h+var_450]
0x180009788  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000978d  mov     rcx, [rsp+4A0h+pv]; pv
0x180009792  mov     ebx, eax
0x180009794  call    cs:__imp_CoTaskMemFree
0x18000979a  mov     rdi, [rsp+4A0h+var_450]
0x18000979f  jmp     loc_180009693
```
