# CIndexedLocationsBasket::_AddBasketRow(ushort const *)

- ea: `0x18001681c`
- end: `0x180016a3e`
- name: `?_AddBasketRow@CIndexedLocationsBasket@@AEAAJPEBG@Z`
- size: `546`
- prototype: `__int64 __fastcall(CIndexedLocationsBasket *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014880`

## callees

- `0x180003ac8`
- `0x18000420c`
- `0x180005cc0`
- `0x18001681c`
- `0x180016aa0`
- `0x180016ba0`
- `0x180016ccc`
- `0x18002c980`
- `0x18002cb8c`
- `0x18002cda8`
- `0x18002d17c`
- `0x18002d474`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800169c6`
- `SHELL32!__imp_ILFree` at `0x1800169c6`
- `SHELL32!__imp_IsUserAnAdmin` at `0x180016877`
- `SHELL32!__imp_IsUserAnAdmin` at `0x180016877`
- `SHLWAPI!SHStrDupW` at `0x180016910`
- `SHLWAPI!SHStrDupW` at `0x180016910`
- `SHLWAPI!UrlIsW` at `0x1800169d6`
- `SHLWAPI!UrlIsW` at `0x1800169d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001693e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001693e`

## pseudocode

```c
__int64 __fastcall CIndexedLocationsBasket::_AddBasketRow(CIndexedLocationsBasket *this, const unsigned __int16 *a2)
{
  int UserNameW; // ebx
  CShellWrappers *v5; // rcx
  LPWSTR v6; // rcx
  bool v7; // r12
  int v8; // r14d
  HRESULT v9; // eax
  bool v10; // zf
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST pidl; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v17[264]; // [rsp+260h] [rbp+160h] BYREF

  UserNameW = CShellWrappers::GetUserNameW(a2, v17);
  v12 = -1;
  if ( UserNameW >= 0 || *((_DWORD *)this + 10) || IsUserAnAdmin() )
  {
    pidl = 0;
    UserNameW = CShellWrappers::GetAbsPidlFromPath(
                  (CIndexedLocationsBasket *)((char *)this + 48),
                  a2,
                  (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
    if ( UserNameW >= 0 )
    {
      LODWORD(ppwsz) = 0;
      v14 = 0;
      UserNameW = CShellWrappers::GetAttribsFromAbsPidl(
                    v5,
                    (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                    (unsigned int *)&ppwsz,
                    &v14);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60654889>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60654889>::GetImpl'::`2'::impl) )
      {
        v7 = 0;
        v8 = (unsigned __int16)ppwsz & 0x400;
        if ( ((unsigned __int16)ppwsz & 0x400) != 0 )
        {
          ppwsz = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &ppwsz,
            0);
          v9 = SHStrDupW(a2, &ppwsz);
          v6 = ppwsz;
          if ( v9 >= 0 && ppwsz )
          {
            v7 = (unsigned int)CShellWrappers::IsCloudFilesPlaceholder(ppwsz, &ppwsz) != 0;
            v6 = ppwsz;
          }
          if ( v6 )
            CoTaskMemFree(v6);
        }
        if ( UserNameW < 0 || (v14 & 0x8000) != 0 )
          goto LABEL_22;
        if ( !v8 )
          goto LABEL_19;
        v10 = !v7;
      }
      else
      {
        if ( UserNameW < 0 )
          goto LABEL_22;
        LOBYTE(v6) = !_bittest((const signed __int32 *)&v14, 0xFu);
        v10 = ((unsigned __int8)v6 & !_bittest((const signed __int32 *)&ppwsz, 0xAu)) == 0;
      }
      if ( !v10 )
      {
LABEL_19:
        UserNameW = CShellWrappers::GetDisplayNameFromAbsPidl(
                      (CShellWrappers *)v6,
                      (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                      v16,
                      1);
        if ( UserNameW >= 0 )
        {
          UserNameW = CShellWrappers::GetIconFromAbsPidl(
                        (CIndexedLocationsBasket *)((char *)this + 48),
                        (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                        &v12);
          if ( UserNameW >= 0 )
            CIndexedLocationsBasket::_InsertListViewItem(this, v12, v16, a2, v12);
        }
      }
LABEL_22:
      ILFree(pidl);
      return (unsigned int)UserNameW;
    }
    if ( !UrlIsW(a2, URLIS_FILEURL)
      && !CShellWrappers::GetOfflineDisplayProperties((CIndexedLocationsBasket *)((char *)this + 48), a2, v16, &v12) )
    {
      CIndexedLocationsBasket::_InsertListViewItem(this, v12, v16, a2, v12);
    }
  }
  return (unsigned int)UserNameW;
}

```

## disassembly

```asm
0x18001681c  mov     [rsp-8+arg_10], rbx
0x180016821  mov     [rsp-8+arg_18], rsi
0x180016826  push    rbp
0x180016827  push    rdi
0x180016828  push    r12
0x18001682a  push    r14
0x18001682c  push    r15
0x18001682e  lea     rbp, [rsp-380h]
0x180016836  sub     rsp, 480h
0x18001683d  mov     rax, cs:__security_cookie
0x180016844  xor     rax, rsp
0x180016847  mov     [rbp+3A0h+var_30], rax
0x18001684e  mov     rdi, rdx
0x180016851  mov     rsi, rcx
0x180016854  lea     rdx, [rbp+3A0h+var_240]; unsigned __int16 *
0x18001685b  mov     rcx, rdi; pszFirst
0x18001685e  call    ?GetUserNameW@CShellWrappers@@SAJPEBGPEAG@Z; CShellWrappers::GetUserNameW(ushort const *,ushort *)
0x180016863  mov     ebx, eax
0x180016865  mov     [rsp+4A0h+var_470], 0FFFFFFFFh
0x18001686d  test    eax, eax
0x18001686f  jns     short loc_180016885
0x180016871  cmp     dword ptr [rsi+28h], 0
0x180016875  jnz     short loc_180016885
0x180016877  call    cs:__imp_IsUserAnAdmin
0x18001687d  test    eax, eax
0x18001687f  jz      loc_180016A11
0x180016885  mov     [rsp+4A0h+pidl], 0
0x18001688e  lea     r15, [rsi+30h]
0x180016892  lea     r8, [rsp+4A0h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180016897  mov     rdx, rdi; unsigned __int16 *
0x18001689a  mov     rcx, r15; this
0x18001689d  call    ?GetAbsPidlFromPath@CShellWrappers@@QEAAJPEBGPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CShellWrappers::GetAbsPidlFromPath(ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800168a2  mov     ebx, eax
0x1800168a4  test    eax, eax
0x1800168a6  js      loc_1800169CE
0x1800168ac  mov     dword ptr [rsp+4A0h+ppwsz], 0
0x1800168b4  mov     [rsp+4A0h+var_460], 0
0x1800168bc  lea     r9, [rsp+4A0h+var_460]; unsigned int *
0x1800168c1  lea     r8, [rsp+4A0h+ppwsz]; unsigned int *
0x1800168c6  mov     rdx, [rsp+4A0h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800168cb  call    ?GetAttribsFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAK1@Z; CShellWrappers::GetAttribsFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ulong *,ulong *)
0x1800168d0  mov     ebx, eax
0x1800168d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60654889@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60654889@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60654889> `wil::Feature<__WilFeatureTraits_Feature_60654889>::GetImpl(void)'::`2'::impl
0x1800168d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60654889@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60654889>::__private_IsEnabled(void)
0x1800168de  test    al, al
0x1800168e0  jz      short loc_18001695C
0x1800168e2  xor     r12b, r12b
0x1800168e5  mov     r14d, dword ptr [rsp+4A0h+ppwsz]
0x1800168ea  and     r14d, 400h
0x1800168f1  jz      short loc_180016944
0x1800168f3  mov     [rsp+4A0h+ppwsz], 0
0x1800168fc  xor     edx, edx
0x1800168fe  lea     rcx, [rsp+4A0h+ppwsz]
0x180016903  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016908  lea     rdx, [rsp+4A0h+ppwsz]; ppwsz
0x18001690d  mov     rcx, rdi; psz
0x180016910  call    cs:__imp_SHStrDupW
0x180016916  mov     rcx, [rsp+4A0h+ppwsz]
0x18001691b  test    eax, eax
0x18001691d  js      short loc_180016939
0x18001691f  test    rcx, rcx
0x180016922  jz      short loc_180016939
0x180016924  lea     rdx, [rsp+4A0h+ppwsz]
0x180016929  call    ?IsCloudFilesPlaceholder@CShellWrappers@@QEAAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CShellWrappers::IsCloudFilesPlaceholder(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18001692e  test    eax, eax
0x180016930  setnz   r12b
0x180016934  mov     rcx, [rsp+4A0h+ppwsz]; pv
0x180016939  test    rcx, rcx
0x18001693c  jz      short loc_180016944
0x18001693e  call    cs:__imp_CoTaskMemFree
0x180016944  test    ebx, ebx
0x180016946  js      short loc_1800169C1
0x180016948  test    [rsp+4A0h+var_460], 8000h
0x180016950  jnz     short loc_1800169C1
0x180016952  test    r14d, r14d
0x180016955  jz      short loc_180016976
0x180016957  test    r12b, r12b
0x18001695a  jmp     short loc_180016974
0x18001695c  test    ebx, ebx
0x18001695e  js      short loc_1800169C1
0x180016960  bt      [rsp+4A0h+var_460], 0Fh
0x180016966  setnb   cl; this
0x180016969  bt      dword ptr [rsp+4A0h+ppwsz], 0Ah
0x18001696f  setnb   al
0x180016972  test    al, cl
0x180016974  jz      short loc_1800169C1
0x180016976  mov     r9d, 1; int
0x18001697c  lea     r8, [rsp+4A0h+var_450]; unsigned __int16 *
0x180016981  mov     rdx, [rsp+4A0h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180016986  call    ?GetDisplayNameFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAGH@Z; CShellWrappers::GetDisplayNameFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort *,int)
0x18001698b  test    eax, eax
0x18001698d  mov     ebx, eax
0x18001698f  js      short loc_1800169C1
0x180016991  lea     r8, [rsp+4A0h+var_470]; int *
0x180016996  mov     rdx, [rsp+4A0h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x18001699b  mov     rcx, r15; this
0x18001699e  call    ?GetIconFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAH@Z; CShellWrappers::GetIconFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,int *)
0x1800169a3  test    eax, eax
0x1800169a5  mov     ebx, eax
0x1800169a7  js      short loc_1800169C1
0x1800169a9  mov     edx, [rsp+4A0h+var_470]; int
0x1800169ad  mov     [rsp+4A0h+var_480], edx; int
0x1800169b1  mov     r9, rdi; unsigned __int16 *
0x1800169b4  lea     r8, [rsp+4A0h+var_450]; unsigned __int16 *
0x1800169b9  mov     rcx, rsi; this
0x1800169bc  call    ?_InsertListViewItem@CIndexedLocationsBasket@@AEAAXHPEBG0H@Z; CIndexedLocationsBasket::_InsertListViewItem(int,ushort const *,ushort const *,int)
0x1800169c1  mov     rcx, [rsp+4A0h+pidl]; pidl
0x1800169c6  call    cs:__imp_ILFree
0x1800169cc  jmp     short loc_180016A11
0x1800169ce  mov     edx, 3; UrlIs
0x1800169d3  mov     rcx, rdi; pszUrl
0x1800169d6  call    cs:__imp_UrlIsW
0x1800169dc  test    eax, eax
0x1800169de  jnz     short loc_180016A11
0x1800169e0  lea     r9, [rsp+4A0h+var_470]; int *
0x1800169e5  lea     r8, [rsp+4A0h+var_450]; unsigned __int16 *
0x1800169ea  mov     rdx, rdi; unsigned __int16 *
0x1800169ed  mov     rcx, r15; this
0x1800169f0  call    ?GetOfflineDisplayProperties@CShellWrappers@@QEBAJPEBGPEAGPEAH@Z; CShellWrappers::GetOfflineDisplayProperties(ushort const *,ushort *,int *)
0x1800169f5  test    eax, eax
0x1800169f7  jnz     short loc_180016A11
0x1800169f9  mov     edx, [rsp+4A0h+var_470]; int
0x1800169fd  mov     [rsp+4A0h+var_480], edx; int
0x180016a01  mov     r9, rdi; unsigned __int16 *
0x180016a04  lea     r8, [rsp+4A0h+var_450]; unsigned __int16 *
0x180016a09  mov     rcx, rsi; this
0x180016a0c  call    ?_InsertListViewItem@CIndexedLocationsBasket@@AEAAXHPEBG0H@Z; CIndexedLocationsBasket::_InsertListViewItem(int,ushort const *,ushort const *,int)
0x180016a11  mov     eax, ebx
0x180016a13  mov     rcx, [rbp+3A0h+var_30]
0x180016a1a  xor     rcx, rsp; StackCookie
0x180016a1d  call    __security_check_cookie
0x180016a22  lea     r11, [rsp+4A0h+var_20]
0x180016a2a  mov     rbx, [r11+40h]
0x180016a2e  mov     rsi, [r11+48h]
0x180016a32  mov     rsp, r11
0x180016a35  pop     r15
0x180016a37  pop     r14
0x180016a39  pop     r12
0x180016a3b  pop     rdi
0x180016a3c  pop     rbp
0x180016a3d  retn
```
