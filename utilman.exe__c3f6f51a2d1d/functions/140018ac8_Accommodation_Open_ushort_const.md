# Accommodation::Open(ushort const *)

- ea: `0x140018ac8`
- end: `0x140018cca`
- name: `?Open@Accommodation@@SAPEAV1@PEBG@Z`
- size: `514`
- prototype: `struct Accommodation *__fastcall(const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012f54`
- `0x1400137c4`
- `0x140015720`
- `0x1400172b0`
- `0x140017698`
- `0x1400178a4`
- `0x140017b08`
- `0x14001cfa0`
- `0x14002227c`
- `0x140022b10`

## callees

- `0x140002760`
- `0x14000d75c`
- `0x14000ea8c`
- `0x140013bac`
- `0x140013ea0`
- `0x140014030`
- `0x1400169b8`
- `0x1400171ec`
- `0x140018694`
- `0x140018a6c`
- `0x140018ac8`
- `0x140018cd0`
- `0x140018d0c`

## string_xrefs

- `0x140018aeb`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\`
- `0x140018c52`: `SecureDesktopAccommodation`
- `0x140018c3d`: `CopySettingsToLockedDesktop`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct Accommodation *__fastcall Accommodation::Open(const unsigned __int16 *a1)
{
  LPCWSTR v2; // rbx
  unsigned int *v3; // rdi
  _QWORD v5[5]; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp+10h] BYREF
  Accommodation *v7; // [rsp+60h] [rbp+18h]

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
  ATL::CSimpleStringT<unsigned short,0>::SetString(
    (char **)&lpSubKey,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs\\",
    0x3Fu);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, a1);
  memset(v5, 0, 24);
  v2 = lpSubKey;
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v5, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u)
    || (v7 = (Accommodation *)operator new(0x58u),
        v3 = (unsigned int *)Accommodation::Accommodation(v7, a1),
        (v7 = (Accommodation *)v3) == 0) )
  {
    ATL::CRegKey::Close((ATL::CRegKey *)v5);
    ATL::CStringData::Release((ATL::CStringData *)(v2 - 12));
    return 0;
  }
  else
  {
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"ApplicationName");
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"Description");
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"StartExe");
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"StartParams");
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"SimpleProfile");
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"Profile");
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"ATExe");
    Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v5, L"TerminateOnDesktopSwitch", v3 + 16, 1u);
    Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v5, L"CopySettingsToLockedDesktop", v3 + 17, 0);
    Accommodation::QueryStringValue((ATL::CRegKey *)v5, L"SecureDesktopAccommodation");
    Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v5, L"PassiveAutoStartBehavior", v3 + 20, 0);
    if ( (unsigned __int8)ATL::operator!=(v3 + 10) )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(v3 + 10);
    ATL::CRegKey::Close((ATL::CRegKey *)v5);
    ATL::CStringData::Release((ATL::CStringData *)(v2 - 12));
    return (struct Accommodation *)v3;
  }
}

```

## disassembly

```asm
0x140018ac8  mov     [rsp+arg_0], rbx
0x140018acd  mov     [rsp+arg_18], rsi
0x140018ad2  push    rdi
0x140018ad3  sub     rsp, 40h
0x140018ad7  mov     rdi, rcx
0x140018ada  lea     rcx, [rsp+48h+lpSubKey]
0x140018adf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140018ae4  nop
0x140018ae5  mov     r8d, 3Fh ; '?'
0x140018aeb  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x140018af2  lea     rcx, [rsp+48h+lpSubKey]
0x140018af7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140018afc  mov     rdx, rdi
0x140018aff  lea     rcx, [rsp+48h+lpSubKey]
0x140018b04  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x140018b09  nop
0x140018b0a  mov     [rsp+48h+var_28], 0
0x140018b13  mov     [rsp+48h+var_20], 0
0x140018b1c  mov     [rsp+48h+var_18], 0
0x140018b25  mov     r9d, 20019h; unsigned int
0x140018b2b  mov     rbx, [rsp+48h+lpSubKey]
0x140018b30  mov     r8, rbx; lpSubKey
0x140018b33  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140018b3a  lea     rcx, [rsp+48h+var_28]; this
0x140018b3f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140018b44  test    eax, eax
0x140018b46  jz      short loc_140018B5C
0x140018b48  lea     rcx, [rsp+48h+var_28]; this
0x140018b4d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140018b52  nop
0x140018b53  lea     rcx, [rbx-18h]
0x140018b57  jmp     loc_140018CB2
0x140018b5c  mov     ecx, 58h ; 'X'; Size
0x140018b61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018b66  mov     [rsp+48h+arg_10], rax
0x140018b6b  mov     rdx, rdi; unsigned __int16 *
0x140018b6e  mov     rcx, rax; this
0x140018b71  call    ??0Accommodation@@AEAA@PEBG@Z; Accommodation::Accommodation(ushort const *)
0x140018b76  mov     rdi, rax
0x140018b79  mov     [rsp+48h+arg_10], rax
0x140018b7e  test    rax, rax
0x140018b81  jnz     short loc_140018B85
0x140018b83  jmp     short loc_140018B48
0x140018b85  lea     r8, [rax+8]
0x140018b89  lea     rdx, aApplicationnam; "ApplicationName"
0x140018b90  lea     rcx, [rsp+48h+var_28]; this
0x140018b95  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018b9a  lea     r8, [rdi+10h]
0x140018b9e  lea     rdx, aDescription; "Description"
0x140018ba5  lea     rcx, [rsp+48h+var_28]; this
0x140018baa  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018baf  lea     r8, [rdi+18h]
0x140018bb3  lea     rdx, aStartexe; "StartExe"
0x140018bba  lea     rcx, [rsp+48h+var_28]; this
0x140018bbf  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018bc4  lea     r8, [rdi+20h]
0x140018bc8  lea     rdx, aStartparams; "StartParams"
0x140018bcf  lea     rcx, [rsp+48h+var_28]; this
0x140018bd4  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018bd9  lea     rsi, [rdi+28h]
0x140018bdd  mov     r8, rsi
0x140018be0  lea     rdx, aSimpleprofile; "SimpleProfile"
0x140018be7  lea     rcx, [rsp+48h+var_28]; this
0x140018bec  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018bf1  lea     r8, [rdi+30h]
0x140018bf5  lea     rdx, aProfile; "Profile"
0x140018bfc  lea     rcx, [rsp+48h+var_28]; this
0x140018c01  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018c06  lea     r8, [rdi+38h]
0x140018c0a  lea     rdx, aAtexe; "ATExe"
0x140018c11  lea     rcx, [rsp+48h+var_28]; this
0x140018c16  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018c1b  lea     r8, [rdi+40h]; unsigned int *
0x140018c1f  mov     r9d, 1; unsigned int
0x140018c25  lea     rdx, aTerminateondes; "TerminateOnDesktopSwitch"
0x140018c2c  lea     rcx, [rsp+48h+var_28]; struct ATL::CRegKey *
0x140018c31  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x140018c36  lea     r8, [rdi+44h]; unsigned int *
0x140018c3a  xor     r9d, r9d; unsigned int
0x140018c3d  lea     rdx, aCopysettingsto; "CopySettingsToLockedDesktop"
0x140018c44  lea     rcx, [rsp+48h+var_28]; struct ATL::CRegKey *
0x140018c49  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x140018c4e  lea     r8, [rdi+48h]
0x140018c52  lea     rdx, aSecuredesktopa; "SecureDesktopAccommodation"
0x140018c59  lea     rcx, [rsp+48h+var_28]; this
0x140018c5e  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140018c63  lea     r8, [rdi+50h]; unsigned int *
0x140018c67  xor     r9d, r9d; unsigned int
0x140018c6a  lea     rdx, aPassiveautosta; "PassiveAutoStartBehavior"
0x140018c71  lea     rcx, [rsp+48h+var_28]; struct ATL::CRegKey *
0x140018c76  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x140018c7b  mov     rcx, rsi
0x140018c7e  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x140018c83  test    al, al
0x140018c85  jz      short loc_140018C90
0x140018c87  mov     rcx, rsi
0x140018c8a  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x140018c8f  nop
0x140018c90  lea     rcx, [rsp+48h+var_28]; this
0x140018c95  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140018c9a  nop
0x140018c9b  lea     rcx, [rbx-18h]; this
0x140018c9f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140018ca4  mov     rax, rdi
0x140018ca7  jmp     short loc_140018CB9
0x140018ca9  mov     rcx, [rsp+48h+lpSubKey]
0x140018cae  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140018cb2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140018cb7  xor     eax, eax
0x140018cb9  mov     rbx, [rsp+48h+arg_0]
0x140018cbe  mov     rsi, [rsp+48h+arg_18]
0x140018cc3  add     rsp, 40h
0x140018cc7  pop     rdi
0x140018cc8  retn
```
