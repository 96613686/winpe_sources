# CEaseOfAccessDialog::CopySecureDesktopToolsToOOBEConfig(void)

- ea: `0x14001cfa0`
- end: `0x14001d144`
- name: `?CopySecureDesktopToolsToOOBEConfig@CEaseOfAccessDialog@@SA_NXZ`
- size: `420`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012f54`

## callees

- `0x14000d75c`
- `0x14000ea8c`
- `0x14000f5f4`
- `0x140013b44`
- `0x140013bac`
- `0x140013bd4`
- `0x140013d30`
- `0x140013ec4`
- `0x140014290`
- `0x140014d0c`
- `0x140014ffc`
- `0x140015fb8`
- `0x1400169b8`
- `0x140016ab4`
- `0x140018ac8`
- `0x14001ccd0`
- `0x14001cfa0`

## string_xrefs

- `0x14001d0fa`: `Configuration`
- `0x14001d0b7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char CEaseOfAccessDialog::CopySecureDesktopToolsToOOBEConfig(void)
{
  char v0; // si
  const unsigned __int16 **v1; // rdi
  _QWORD *v2; // rax
  __int64 v3; // rbx
  struct Accommodation *v4; // rax
  unsigned __int16 *v5; // rbx
  HKEY v7[3]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h]
  __int128 v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+60h] [rbp-A0h]
  _BYTE v12[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v14; // [rsp+1D0h] [rbp+D0h] BYREF

  v0 = 0;
  if ( CATUtils::IsMachineOOBERunning() )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = 10;
    StartList::GetLogonConfigList(&v8);
    if ( v9 )
    {
      StartList::StartList((StartList *)v12, 0);
      v1 = (const unsigned __int16 **)&c_rgpszATsLaunchableInOOBE;
      do
      {
        v2 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         &v14,
                         *v1);
        v3 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
               &v8,
               *v2);
        ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
        if ( v3 )
        {
          v4 = Accommodation::Open(*v1);
          if ( (int)StartList::Add((StartList *)v12, v4) >= 0 )
            v0 = 1;
        }
        ++v1;
      }
      while ( v1 != (const unsigned __int16 **)&`AccessibilityFlyoutTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner );
      if ( v0 )
      {
        StartList::LoadSettings((StartList *)v12);
        if ( v13 )
        {
          memset(v7, 0, sizeof(v7));
          if ( !(unsigned int)ATL::CRegKey::Open(
                                (ATL::CRegKey *)v7,
                                HKEY_LOCAL_MACHINE,
                                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
                                0x20006u) )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v14);
            StartList::BuildConfigString(&v14, v12);
            v5 = v14;
            ATL::CRegKey::SetStringValue(v7, L"Configuration", (const BYTE *)v14);
            ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
          }
          ATL::CRegKey::Close((ATL::CRegKey *)v7);
        }
      }
      StartList::~StartList((StartList *)v12);
    }
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v8);
  }
  return v0;
}

```

## disassembly

```asm
0x14001cfa0  push    rbp
0x14001cfa2  push    rbx
0x14001cfa3  push    rsi
0x14001cfa4  push    rdi
0x14001cfa5  lea     rbp, [rsp-0A8h]
0x14001cfad  sub     rsp, 1A8h
0x14001cfb4  xor     sil, sil
0x14001cfb7  call    ?IsMachineOOBERunning@CATUtils@@SA_NXZ; CATUtils::IsMachineOOBERunning(void)
0x14001cfbc  test    al, al
0x14001cfbe  jz      loc_14001D134
0x14001cfc4  xorps   xmm0, xmm0
0x14001cfc7  movdqu  [rsp+1C0h+var_188], xmm0
0x14001cfcd  mov     [rsp+1C0h+var_178], 0
0x14001cfd6  xorps   xmm1, xmm1
0x14001cfd9  movdqu  [rsp+1C0h+var_170], xmm1
0x14001cfdf  mov     [rsp+1C0h+var_160], 0Ah
0x14001cfe7  lea     rcx, [rsp+1C0h+var_188]
0x14001cfec  call    ?GetLogonConfigList@StartList@@SAXAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; StartList::GetLogonConfigList(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14001cff1  cmp     [rsp+1C0h+var_178], 0
0x14001cff7  jz      loc_14001D12A
0x14001cffd  xor     edx, edx; int
0x14001cfff  lea     rcx, [rsp+1C0h+var_150]; this
0x14001d004  call    ??0StartList@@QEAA@H@Z; StartList::StartList(int)
0x14001d009  nop
0x14001d00a  lea     rdi, ?c_rgpszATsLaunchableInOOBE@@3PAPEBGA; ushort const * near * c_rgpszATsLaunchableInOOBE
0x14001d011  mov     rdx, [rdi]
0x14001d014  lea     rcx, [rbp+0C0h+arg_0]
0x14001d01b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001d020  mov     rdx, [rax]
0x14001d023  lea     rcx, [rsp+1C0h+var_188]
0x14001d028  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14001d02d  mov     rbx, rax
0x14001d030  mov     rcx, [rbp+0C0h+arg_0]
0x14001d037  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001d03b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001d040  test    rbx, rbx
0x14001d043  jz      short loc_14001D068
0x14001d045  mov     rcx, [rdi]; unsigned __int16 *
0x14001d048  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14001d04d  mov     rdx, rax; struct Accommodation *
0x14001d050  lea     rcx, [rsp+1C0h+var_150]; this
0x14001d055  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x14001d05a  movzx   esi, sil
0x14001d05e  mov     ecx, 1
0x14001d063  test    eax, eax
0x14001d065  cmovns  esi, ecx
0x14001d068  add     rdi, 8
0x14001d06c  lea     rax, ?__hInner@?1???0StaticHandle@AccessibilityFlyoutTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AccessibilityFlyoutTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14001d073  cmp     rdi, rax
0x14001d076  jnz     short loc_14001D011
0x14001d078  test    sil, sil
0x14001d07b  jz      loc_14001D11F
0x14001d081  lea     rcx, [rsp+1C0h+var_150]; this
0x14001d086  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x14001d08b  cmp     [rbp+0C0h+var_140], 0
0x14001d090  jz      loc_14001D11F
0x14001d096  mov     [rsp+1C0h+var_1A0], 0
0x14001d09f  mov     [rsp+1C0h+var_198], 0
0x14001d0a8  mov     [rsp+1C0h+var_190], 0
0x14001d0b1  mov     r9d, 20006h; unsigned int
0x14001d0b7  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001d0be  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001d0c5  lea     rcx, [rsp+1C0h+var_1A0]; this
0x14001d0ca  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001d0cf  test    eax, eax
0x14001d0d1  jnz     short loc_14001D114
0x14001d0d3  lea     rcx, [rbp+0C0h+arg_0]
0x14001d0da  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14001d0df  lea     rdx, [rsp+1C0h+var_150]
0x14001d0e4  lea     rcx, [rbp+0C0h+arg_0]
0x14001d0eb  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14001d0f0  mov     rbx, [rbp+0C0h+arg_0]
0x14001d0f7  mov     r8, rbx; unsigned __int16 *
0x14001d0fa  lea     rdx, aConfiguration; "Configuration"
0x14001d101  lea     rcx, [rsp+1C0h+var_1A0]; this
0x14001d106  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x14001d10b  lea     rcx, [rbx-18h]; this
0x14001d10f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001d114  lea     rcx, [rsp+1C0h+var_1A0]; this
0x14001d119  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001d11e  nop
0x14001d11f  lea     rcx, [rsp+1C0h+var_150]; this
0x14001d124  call    ??1StartList@@QEAA@XZ; StartList::~StartList(void)
0x14001d129  nop
0x14001d12a  lea     rcx, [rsp+1C0h+var_188]
0x14001d12f  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x14001d134  mov     al, sil
0x14001d137  add     rsp, 1A8h
0x14001d13e  pop     rdi
0x14001d13f  pop     rsi
0x14001d140  pop     rbx
0x14001d141  pop     rbp
0x14001d142  retn
```
