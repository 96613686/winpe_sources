# CContextMenuDUI::_InsertButton(ushort const *,IInspectable *)

- ea: `0x18007bc00`
- end: `0x18007bdb9`
- name: `?_InsertButton@CContextMenuDUI@@AEAAJPEBGPEAUIInspectable@@@Z`
- size: `441`
- prototype: `int(CContextMenuDUI *__hidden this, const unsigned __int16 *, struct IInspectable *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007be88`

## callees

- `0x18000af00`
- `0x1800738cc`
- `0x18007bc00`

## import_xrefs

- `PROPSYS!PropVariantToStringAlloc` at `0x18007bd42`
- `PROPSYS!PropVariantToStringAlloc` at `0x18007bd42`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x18007bcfd`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x18007bcfd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007bc6a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007bc6a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007bd72`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007bd72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bc57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bd95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bc57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bd95`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18007bd59`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18007bd59`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18007bc9b`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18007bc9b`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18007bccc`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18007bccc`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007bd85`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007bd85`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18007bcb8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18007bcb8`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x18007bc88`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x18007bc88`

## pseudocode

```c
__int64 __fastcall CContextMenuDUI::_InsertButton(CContextMenuDUI *this, const unsigned __int16 *a2, IUnknown *a3)
{
  __int64 v4; // r8
  int v7; // ebx
  HRESULT v8; // eax
  DirectUI::Element *v9; // rdi
  DirectUI::Element *v11; // [rsp+30h] [rbp-40h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h]
  __int64 v14; // [rsp+48h] [rbp-28h]
  PROPVARIANT ppropvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h]
  unsigned int v17; // [rsp+90h] [rbp+20h] BYREF
  LPWSTR ppwsz; // [rsp+A8h] [rbp+38h] BYREF

  v11 = 0;
  v4 = *((_QWORD *)this + 13);
  v17 = 0;
  v7 = ContextMenu_ParserCreateElement<UIContextMenuButton>(this, a2, v4, &v17, &v11);
  if ( v7 >= 0 )
  {
    ppwsz = 0;
    CoTaskMemFree(0);
    v8 = SHStrDupW(a2, &ppwsz);
    v9 = v11;
    v7 = v8;
    if ( v8 < 0
      || (SHStripMneumonicW(ppwsz), v7 = DirectUI::Element::SetContentString(v9, ppwsz), v7 < 0)
      || (v7 = DirectUI::Element::Add(*((DirectUI::Element **)this + 13), v9),
          DirectUI::Element::EndDefer(v9, v17),
          v7 < 0) )
    {
      DirectUI::Element::Destroy(v9, 1);
    }
    else if ( a3 )
    {
      *(_OWORD *)ppropvar = 0;
      v16 = 0;
      if ( WinRTPropertyValueToPropVariant(a3, ppropvar) >= 0 )
      {
        ppszOut = 0;
        v13 = 0;
        v14 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszOut);
        v13 = -1;
        v14 = -1;
        if ( PropVariantToStringAlloc(ppropvar, &ppszOut) >= 0 )
          DirectUI::Element::SetID(v9, ppszOut);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszOut);
      }
      PropVariantClear(ppropvar);
    }
    CoTaskMemFree(ppwsz);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007bc00  mov     [rsp-18h+arg_8], rbx
0x18007bc05  mov     [rsp-18h+arg_10], rsi
0x18007bc0a  push    rbp
0x18007bc0b  push    rdi
0x18007bc0c  push    r14
0x18007bc0e  mov     rbp, rsp
0x18007bc11  sub     rsp, 70h
0x18007bc15  mov     rsi, r8
0x18007bc18  mov     [rbp+var_40], 0
0x18007bc20  mov     r8, [rcx+68h]
0x18007bc24  lea     rax, [rbp+var_40]
0x18007bc28  lea     r9, [rbp+arg_0]
0x18007bc2c  mov     [rsp+70h+var_50], rax
0x18007bc31  mov     rdi, rdx
0x18007bc34  mov     [rbp+arg_0], 0
0x18007bc3b  mov     r14, rcx
0x18007bc3e  call    ??$ContextMenu_ParserCreateElement@VUIContextMenuButton@@@@YAJPEBGPEAVElement@DirectUI@@1PEAKPEAPEAVUIContextMenuButton@@@Z; ContextMenu_ParserCreateElement<UIContextMenuButton>(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,UIContextMenuButton * *)
0x18007bc43  mov     ebx, eax
0x18007bc45  test    eax, eax
0x18007bc47  js      loc_18007BDA1
0x18007bc4d  xor     ecx, ecx; pv
0x18007bc4f  mov     [rbp+ppwsz], 0
0x18007bc57  call    cs:__imp_CoTaskMemFree
0x18007bc5e  nop     dword ptr [rax+rax+00h]
0x18007bc63  lea     rdx, [rbp+ppwsz]; ppwsz
0x18007bc67  mov     rcx, rdi; psz
0x18007bc6a  call    cs:__imp_SHStrDupW
0x18007bc71  nop     dword ptr [rax+rax+00h]
0x18007bc76  mov     rdi, [rbp+var_40]
0x18007bc7a  mov     ebx, eax
0x18007bc7c  test    eax, eax
0x18007bc7e  js      loc_18007BD80
0x18007bc84  mov     rcx, [rbp+ppwsz]; pszMenu
0x18007bc88  call    cs:__imp_SHStripMneumonicW
0x18007bc8f  nop     dword ptr [rax+rax+00h]
0x18007bc94  mov     rdx, [rbp+ppwsz]
0x18007bc98  mov     rcx, rdi
0x18007bc9b  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18007bca2  nop     dword ptr [rax+rax+00h]
0x18007bca7  mov     ebx, eax
0x18007bca9  test    eax, eax
0x18007bcab  js      loc_18007BD80
0x18007bcb1  mov     rcx, [r14+68h]
0x18007bcb5  mov     rdx, rdi
0x18007bcb8  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18007bcbf  nop     dword ptr [rax+rax+00h]
0x18007bcc4  mov     edx, [rbp+arg_0]
0x18007bcc7  mov     rcx, rdi
0x18007bcca  mov     ebx, eax
0x18007bccc  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18007bcd3  nop     dword ptr [rax+rax+00h]
0x18007bcd8  test    ebx, ebx
0x18007bcda  js      loc_18007BD80
0x18007bce0  test    rsi, rsi
0x18007bce3  jz      loc_18007BD91
0x18007bce9  xorps   xmm0, xmm0
0x18007bcec  lea     rdx, [rbp+ppropvar]; ppropvar
0x18007bcf0  xor     eax, eax
0x18007bcf2  mov     rcx, rsi; punkPropertyValue
0x18007bcf5  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18007bcf9  mov     [rbp+var_10], rax
0x18007bcfd  call    cs:__imp_WinRTPropertyValueToPropVariant
0x18007bd04  nop     dword ptr [rax+rax+00h]
0x18007bd09  test    eax, eax
0x18007bd0b  js      short loc_18007BD6E
0x18007bd0d  lea     rcx, [rbp+ppszOut]
0x18007bd11  mov     [rbp+ppszOut], 0
0x18007bd19  mov     [rbp+var_30], 0
0x18007bd21  mov     [rbp+var_28], 0
0x18007bd29  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007bd2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007bd32  lea     rdx, [rbp+ppszOut]; ppszOut
0x18007bd36  lea     rcx, [rbp+ppropvar]; propvar
0x18007bd3a  mov     [rbp+var_30], rax
0x18007bd3e  mov     [rbp+var_28], rax
0x18007bd42  call    cs:__imp_PropVariantToStringAlloc
0x18007bd49  nop     dword ptr [rax+rax+00h]
0x18007bd4e  test    eax, eax
0x18007bd50  js      short loc_18007BD65
0x18007bd52  mov     rdx, [rbp+ppszOut]
0x18007bd56  mov     rcx, rdi
0x18007bd59  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18007bd60  nop     dword ptr [rax+rax+00h]
0x18007bd65  lea     rcx, [rbp+ppszOut]
0x18007bd69  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007bd6e  lea     rcx, [rbp+ppropvar]; pvar
0x18007bd72  call    cs:__imp_PropVariantClear
0x18007bd79  nop     dword ptr [rax+rax+00h]
0x18007bd7e  jmp     short loc_18007BD91
0x18007bd80  mov     dl, 1
0x18007bd82  mov     rcx, rdi
0x18007bd85  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18007bd8c  nop     dword ptr [rax+rax+00h]
0x18007bd91  mov     rcx, [rbp+ppwsz]; pv
0x18007bd95  call    cs:__imp_CoTaskMemFree
0x18007bd9c  nop     dword ptr [rax+rax+00h]
0x18007bda1  lea     r11, [rsp+70h+var_s0]
0x18007bda6  mov     eax, ebx
0x18007bda8  mov     rbx, [r11+28h]
0x18007bdac  mov     rsi, [r11+30h]
0x18007bdb0  mov     rsp, r11
0x18007bdb3  pop     r14
0x18007bdb5  pop     rdi
0x18007bdb6  pop     rbp
0x18007bdb7  retn
```
