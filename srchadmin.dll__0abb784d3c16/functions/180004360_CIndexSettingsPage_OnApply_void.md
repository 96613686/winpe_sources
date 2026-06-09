# CIndexSettingsPage::_OnApply(void)

- ea: `0x180004360`
- end: `0x1800044da`
- name: `?_OnApply@CIndexSettingsPage@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(WCHAR *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800192dc`

## callees

- `0x180004360`
- `0x180004798`
- `0x180004844`
- `0x18000a07c`
- `0x180019ea8`
- `0x180019f80`

## import_xrefs

- `SHLWAPI!SHSetValueW` at `0x18000441d`
- `SHLWAPI!SHSetValueW` at `0x18000441d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800043b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800043b7`
- `USER32!IsDlgButtonChecked` at `0x1800043d7`
- `USER32!IsDlgButtonChecked` at `0x180004440`
- `USER32!IsDlgButtonChecked` at `0x1800044a6`
- `USER32!IsDlgButtonChecked` at `0x1800043d7`
- `USER32!IsDlgButtonChecked` at `0x180004440`
- `USER32!IsDlgButtonChecked` at `0x1800044a6`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_OnApply(WCHAR *this)
{
  signed int v2; // ebx
  const unsigned __int16 *lpString2; // rbp
  int v4; // esi
  int v5; // ecx
  LSTATUS v6; // eax
  int v7; // ebp
  __int64 v8; // rbx
  __int64 v9; // rax
  BOOL v10; // edx
  CMSSAdmin *v11; // rcx
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  if ( *((_DWORD *)this + 19) )
  {
    lpString2 = this + 300;
    v4 = 0;
    if ( this[300] && this[40] && CompareStringW(0x7Fu, 1u, this + 40, -1, lpString2, -1) != 2 )
      v2 = CIndexSettingsPage::_SetDataDirNew((CIndexSettingsPage *)this, lpString2);
    v5 = IsDlgButtonChecked(*(HWND *)this, 902) == 1;
    pvData = v5;
    if ( v2 >= 0 && *((_DWORD *)this + 15) != v5 )
    {
      v6 = SHSetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\Windows Search\\Preferences",
             L"AllowIndexingEncryptedStoresOrItems",
             4u,
             &pvData,
             4u);
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      if ( v2 >= 0 )
        v4 = 1;
    }
    v7 = IsDlgButtonChecked(*(HWND *)this, 903) == 1;
    if ( v2 >= 0
      && *((_DWORD *)this + 16) != v7
      && (v8 = *((_QWORD *)this + 1),
          v14 = v7,
          SearchOptionsTelemetry::DiacriticBehaviorClicked<int &>(&v14),
          v2 = CMSSAdmin::SetDiacritics((CMSSAdmin *)(v8 + 24), v7),
          v2 >= 0)
      || v4 )
    {
      v9 = *((_QWORD *)this + 1);
      *(_DWORD *)v9 = 5;
      *(_QWORD *)(v9 + 4) = 1;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_46595479>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_46595479>::GetImpl'::`2'::impl) )
    {
      v10 = IsDlgButtonChecked(*(HWND *)this, 917) == 1;
      if ( v2 >= 0 )
        v2 = CMSSAdmin::SetEnableSemanticIndexing(v11, v10);
    }
    if ( v2 == 1 )
      return 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004360  mov     [rsp+arg_10], rbx
0x180004365  push    rbp
0x180004366  push    rsi
0x180004367  push    rdi
0x180004368  push    r14
0x18000436a  push    r15
0x18000436c  sub     rsp, 30h
0x180004370  xor     r14d, r14d
0x180004373  mov     rdi, rcx
0x180004376  mov     ebx, r14d
0x180004379  cmp     [rcx+4Ch], r14d
0x18000437d  jz      loc_1800044C7
0x180004383  lea     rbp, [rcx+258h]
0x18000438a  mov     esi, r14d
0x18000438d  lea     r15d, [r14+1]
0x180004391  cmp     [rbp+0], r14w
0x180004396  jz      short loc_1800043CF
0x180004398  lea     r8, [rcx+50h]; lpString1
0x18000439c  cmp     [r8], r14w
0x1800043a0  jz      short loc_1800043CF
0x1800043a2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800043a6  lea     ecx, [r14+7Fh]; Locale
0x1800043aa  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800043af  mov     edx, r15d; dwCmpFlags
0x1800043b2  mov     [rsp+58h+lpString2], rbp; lpString2
0x1800043b7  call    cs:__imp_CompareStringW
0x1800043bd  cmp     eax, 2
0x1800043c0  jz      short loc_1800043CF
0x1800043c2  mov     rdx, rbp; unsigned __int16 *
0x1800043c5  mov     rcx, rdi; this
0x1800043c8  call    ?_SetDataDirNew@CIndexSettingsPage@@AEAAJPEBG@Z; CIndexSettingsPage::_SetDataDirNew(ushort const *)
0x1800043cd  mov     ebx, eax
0x1800043cf  mov     rcx, [rdi]; hDlg
0x1800043d2  mov     edx, 386h; nIDButton
0x1800043d7  call    cs:__imp_IsDlgButtonChecked
0x1800043dd  cmp     eax, r15d
0x1800043e0  mov     ecx, r14d
0x1800043e3  setz    cl
0x1800043e6  mov     [rsp+58h+pvData], ecx
0x1800043ea  test    ebx, ebx
0x1800043ec  js      short loc_180004438
0x1800043ee  cmp     [rdi+3Ch], ecx
0x1800043f1  jz      short loc_180004438
0x1800043f3  mov     r9d, 4; dwType
0x1800043f9  lea     rax, [rsp+58h+pvData]
0x1800043fe  mov     [rsp+58h+cchCount2], r9d; cbData
0x180004403  lea     r8, aAllowindexinge; "AllowIndexingEncryptedStoresOrItems"
0x18000440a  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\Windows S"...
0x180004411  mov     [rsp+58h+lpString2], rax; pvData
0x180004416  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000441d  call    cs:__imp_SHSetValueW
0x180004423  mov     ebx, eax
0x180004425  test    eax, eax
0x180004427  jle     short loc_180004432
0x180004429  movzx   ebx, ax
0x18000442c  or      ebx, 80070000h
0x180004432  test    ebx, ebx
0x180004434  cmovns  esi, r15d
0x180004438  mov     rcx, [rdi]; hDlg
0x18000443b  mov     edx, 387h; nIDButton
0x180004440  call    cs:__imp_IsDlgButtonChecked
0x180004446  cmp     eax, r15d
0x180004449  mov     ebp, r14d
0x18000444c  setz    bpl
0x180004450  test    ebx, ebx
0x180004452  js      short loc_18000447C
0x180004454  cmp     [rdi+40h], ebp
0x180004457  jz      short loc_18000447C
0x180004459  mov     rbx, [rdi+8]
0x18000445d  lea     rcx, [rsp+58h+arg_8]
0x180004462  mov     [rsp+58h+arg_8], ebp
0x180004466  call    ??$DiacriticBehaviorClicked@AEAH@SearchOptionsTelemetry@@SAXAEAH@Z; SearchOptionsTelemetry::DiacriticBehaviorClicked<int &>(int &)
0x18000446b  lea     rcx, [rbx+18h]; this
0x18000446f  mov     edx, ebp; int
0x180004471  call    ?SetDiacritics@CMSSAdmin@@QEAAJH@Z; CMSSAdmin::SetDiacritics(int)
0x180004476  mov     ebx, eax
0x180004478  test    eax, eax
0x18000447a  jns     short loc_180004480
0x18000447c  test    esi, esi
0x18000447e  jz      short loc_18000448E
0x180004480  mov     rax, [rdi+8]
0x180004484  mov     dword ptr [rax], 5
0x18000448a  mov     [rax+4], r15
0x18000448e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46595479@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46595479@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46595479> `wil::Feature<__WilFeatureTraits_Feature_46595479>::GetImpl(void)'::`2'::impl
0x180004495  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_46595479@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46595479>::__private_IsEnabled(void)
0x18000449a  test    al, al
0x18000449c  jz      short loc_1800044C0
0x18000449e  mov     rcx, [rdi]; hDlg
0x1800044a1  mov     edx, 395h; nIDButton
0x1800044a6  call    cs:__imp_IsDlgButtonChecked
0x1800044ac  cmp     eax, r15d
0x1800044af  mov     edx, r14d
0x1800044b2  setz    dl; int
0x1800044b5  test    ebx, ebx
0x1800044b7  js      short loc_1800044C0
0x1800044b9  call    ?SetEnableSemanticIndexing@CMSSAdmin@@QEAAJH@Z; CMSSAdmin::SetEnableSemanticIndexing(int)
0x1800044be  mov     ebx, eax
0x1800044c0  cmp     ebx, r15d
0x1800044c3  cmovz   ebx, r14d
0x1800044c7  mov     eax, ebx
0x1800044c9  mov     rbx, [rsp+58h+arg_10]
0x1800044ce  add     rsp, 30h
0x1800044d2  pop     r15
0x1800044d4  pop     r14
0x1800044d6  pop     rdi
0x1800044d7  pop     rsi
0x1800044d8  pop     rbp
0x1800044d9  retn
```
