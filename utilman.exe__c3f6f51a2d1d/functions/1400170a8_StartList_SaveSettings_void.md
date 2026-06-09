# StartList::SaveSettings(void)

- ea: `0x1400170a8`
- end: `0x1400171ae`
- name: `?SaveSettings@StartList@@AEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013ec4`
- `0x1400169e8`
- `0x140017b08`

## callees

- `0x14000e550`
- `0x140013bac`
- `0x140014290`
- `0x1400169b8`
- `0x1400170a8`
- `0x140017e18`
- `0x14001cb14`
- `0x14001cb68`
- `0x14001ccb0`

## string_xrefs

- `0x14001711b`: `SettingConfiguration`
- `0x14001716a`: `Configuration`
- `0x140017111`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140017174`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140017108`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
__int64 __fastcall StartList::SaveSettings(StartList *this)
{
  bool IsDesktopOOBEUserSessionActive; // bp
  int v3; // edi
  unsigned __int16 *v4; // rbx
  const WCHAR *v5; // rdx
  StartList *v6; // rdx
  unsigned __int16 *v7; // rbx
  unsigned int v8; // ebx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  _Trace::_Trace((_Trace *)v10, L"StartList::SaveSettings", (int *)&v11);
  IsDesktopOOBEUserSessionActive = CATUtils::IsDesktopOOBEUserSessionActive();
  v3 = IsInteractiveUser();
  if ( IsDesktopOOBEUserSessionActive )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
    StartList::BuildConfigString(&v12, (char *)this + 144);
    v4 = v12;
    v5 = StartList::_accessibilityKeyString;
    if ( !v3 )
      v5 = StartList::_oobeAccessibilityKeyString;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      (HKEY)(-(__int64)(v3 != 0) - 2147483646),
      v5,
      StartList::_settingConfiguration,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  }
  if ( v3 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
    v6 = (StartList *)((char *)this + 48);
    if ( !IsDesktopOOBEUserSessionActive )
      v6 = this;
    StartList::BuildConfigString(&v12, v6);
    v7 = v12;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      HKEY_CURRENT_USER,
      StartList::_accessibilityKeyString,
      StartList::_configuration,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  }
  v8 = v11;
  _Trace::~_Trace((_Trace *)v10);
  return v8;
}

```

## disassembly

```asm
0x1400170a8  mov     rax, rsp
0x1400170ab  mov     [rax+8], rbx
0x1400170af  push    rbp
0x1400170b0  push    rsi
0x1400170b1  push    rdi
0x1400170b2  sub     rsp, 30h
0x1400170b6  mov     rsi, rcx
0x1400170b9  mov     dword ptr [rax+10h], 0
0x1400170c0  lea     rcx, [rax-28h]; this
0x1400170c4  lea     r8, [rax+10h]; int *
0x1400170c8  lea     rdx, aStartlistSaves_0; "StartList::SaveSettings"
0x1400170cf  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x1400170d4  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x1400170d9  mov     bpl, al
0x1400170dc  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400170e1  mov     edi, eax
0x1400170e3  test    bpl, bpl
0x1400170e6  jz      short loc_140017142
0x1400170e8  lea     rcx, [rsp+48h+arg_10]
0x1400170ed  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400170f2  lea     rdx, [rsi+90h]
0x1400170f9  lea     rcx, [rsp+48h+arg_10]
0x1400170fe  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140017103  mov     rbx, [rsp+48h+arg_10]
0x140017108  lea     rax, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001710f  test    edi, edi
0x140017111  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140017118  mov     r9, rbx; unsigned __int16 *
0x14001711b  lea     r8, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x140017122  cmovz   rdx, rax; lpSubKey
0x140017126  mov     eax, edi
0x140017128  neg     eax
0x14001712a  sbb     rcx, rcx
0x14001712d  add     rcx, 0FFFFFFFF80000002h; hKey
0x140017134  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x140017139  lea     rcx, [rbx-18h]; this
0x14001713d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017142  test    edi, edi
0x140017144  jz      short loc_140017190
0x140017146  lea     rcx, [rsp+48h+arg_10]
0x14001714b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140017150  test    bpl, bpl
0x140017153  lea     rdx, [rsi+30h]
0x140017157  lea     rcx, [rsp+48h+arg_10]
0x14001715c  cmovz   rdx, rsi
0x140017160  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140017165  mov     rbx, [rsp+48h+arg_10]
0x14001716a  lea     r8, ?_configuration@StartList@@0PAGA; "Configuration"
0x140017171  mov     r9, rbx; unsigned __int16 *
0x140017174  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001717b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140017182  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x140017187  lea     rcx, [rbx-18h]; this
0x14001718b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017190  mov     ebx, [rsp+48h+arg_8]
0x140017194  lea     rcx, [rsp+48h+var_28]; this
0x140017199  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14001719e  mov     eax, ebx
0x1400171a0  mov     rbx, [rsp+48h+arg_0]
0x1400171a5  add     rsp, 30h
0x1400171a9  pop     rdi
0x1400171aa  pop     rsi
0x1400171ab  pop     rbp
0x1400171ac  retn
```
