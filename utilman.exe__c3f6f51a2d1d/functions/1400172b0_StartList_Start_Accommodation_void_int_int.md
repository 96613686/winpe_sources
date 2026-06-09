# StartList::Start(Accommodation *,void *,int,int)

- ea: `0x1400172b0`
- end: `0x14001768f`
- name: `?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z`
- size: `991`
- prototype: `__int64 __usercall@<rax>(StartList *__hidden this@<rcx>, struct Accommodation *@<rdx>, void *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140017290`

## callees

- `0x14000d75c`
- `0x14000e550`
- `0x14000f2d0`
- `0x14000f5b8`
- `0x14001355c`
- `0x1400135f0`
- `0x1400136e4`
- `0x140013ad0`
- `0x140013e40`
- `0x140013ec4`
- `0x140013fa8`
- `0x140014560`
- `0x140014844`
- `0x140014d0c`
- `0x140015c40`
- `0x140015fb8`
- `0x140016568`
- `0x1400169b8`
- `0x140016e8c`
- `0x140017290`
- `0x1400172b0`
- `0x140018ac8`
- `0x1400191d0`
- `0x14001aa78`
- `0x14001c64c`
- `0x14001ccb0`
- `0x14001cd1c`
- `0x140026a44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140017392`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140017392`

## string_xrefs

- `0x14001752d`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Start *__fastcall StartList::Start(Start *this, const wchar_t **a2, void *a3, int a4, int a5)
{
  char v8; // r15
  Start *result; // rax
  unsigned int v10; // r14d
  struct Accommodation *v11; // rax
  int v12; // eax
  StartList *v13; // rcx
  const unsigned __int16 *v14; // rbx
  unsigned int v15; // eax
  _QWORD *v16; // rax
  bool v17; // bl
  _QWORD *v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rax
  WCHAR *v21; // rcx
  unsigned __int16 *v22; // r9
  int ATProcess; // eax
  StartList *v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rbx
  _QWORD *v27; // rax
  HKEY v28; // [rsp+38h] [rbp-D0h]
  HKEY v29[4]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v30[352]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE *v31; // [rsp+208h] [rbp+100h] BYREF

  HIDWORD(v31) = HIDWORD(a3);
  v8 = 0;
  LODWORD(v31) = 0;
  if ( !a2 )
    return (Start *)2147942487LL;
  result = (Start *)StartList::LoadSettings(this);
  v10 = (unsigned int)result;
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)ATL::operator!=(a2 + 9) && !(unsigned int)IsInteractiveUser() )
    {
      if ( CATUtils::IsDesktopOOBEUserSessionActive() && !wcscmp_0(a2[5], L"SystemSetting") )
        StartList::Add(this, (struct Accommodation *)a2);
      v11 = Accommodation::Open(a2[9]);
      if ( v11 )
        return (Start *)StartList::Start(this, v11, 0, 0);
      else
        return (Start *)2147942414LL;
    }
    v12 = wcscmp_0(a2[5], L"SystemSetting");
    v14 = a2[3];
    if ( !v12 )
    {
      v15 = _o__wtoi(a2[3]);
      if ( v15 < 0x16 )
      {
        v10 = SystemSettings::TurnOn(a2, v15, 0, *((_DWORD *)this + 73));
        if ( (v10 & 0x80000000) == 0 )
        {
          v17 = 0;
          if ( (unsigned int)IsInteractiveUser() )
          {
            v16 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              &v31,
                              a2);
            v8 = 1;
            if ( ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                   this,
                   *v16) )
            {
              v17 = 1;
            }
          }
          if ( (v8 & 1) != 0 )
            ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
          if ( v17 )
          {
            v18 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              &v31,
                              a2);
            v19 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                    (char *)this + 48,
                    *v18);
            ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
            if ( !v19 )
            {
              v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                &v31,
                                a2);
              ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
                (char *)this + 48,
                *v20);
              ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
            }
            StartList::SaveSessionKey(this);
          }
          else if ( CATUtils::IsDesktopOOBEUserSessionActive() )
          {
            StartList::Add(this, (struct Accommodation *)a2);
          }
        }
      }
      return (Start *)v10;
    }
    if ( !v14 )
      return (Start *)2147500037LL;
    if ( a5 || StartList::IsColorFiltering(v13, (struct Accommodation *)a2) )
    {
      if ( StartList::IsColorFiltering(v13, (struct Accommodation *)a2) )
        ColorFiltering::ColorFilterHelper::UpdateActiveFilter();
    }
    else
    {
      if ( (unsigned int)IsInteractiveUser() && !CATUtils::IsProcessInATJob(v21) )
      {
        if ( *((_DWORD *)a2 + 16) )
        {
          memset(v29, 0, 24);
          if ( !(unsigned int)ATL::CRegKey::Create(
                                (ATL::CRegKey *)v29,
                                HKEY_CURRENT_USER,
                                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                                v22,
                                1u,
                                0x2001Fu,
                                v28,
                                0) )
            ATL::CRegKey::SetDWORDValue(v29, *a2, 3);
          ATL::CRegKey::Close((ATL::CRegKey *)v29);
          SendWinkeyPlusU();
        }
        else if ( a4 )
        {
          StartList::CreateBreakawayATProcess(v21, (struct Accommodation *)a2, 1);
        }
        else
        {
          StartList::CreateATProcess((StartList *)v21, v14, (struct Accommodation *)a2);
        }
        return 0;
      }
      if ( *((_DWORD *)a2 + 16) || !(unsigned int)IsInteractiveUser() )
        ATProcess = StartList::CreateATProcess((StartList *)v21, v14, (struct Accommodation *)a2);
      else
        ATProcess = StartList::CreateBreakawayATProcess(v21, (struct Accommodation *)a2, 0);
      v10 = ATProcess;
      if ( ATProcess < 0 )
        return (Start *)v10;
    }
    StartList::LogAccomodationToSQM(v24, (struct Accommodation *)a2);
    if ( (unsigned int)IsInteractiveUser() )
    {
      v25 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        &v31,
                        a2);
      v26 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 48,
              *v25);
      ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
      if ( !v26 )
      {
        v27 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          &v31,
                          a2);
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          (char *)this + 48,
          *v27);
        ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
      }
      StartList::SaveSessionKey(this);
      if ( *((_DWORD *)a2 + 17) || !*((_DWORD *)a2 + 16) )
      {
        ATManager::ATManager((ATManager *)v30, 1);
        v31 = v30;
        SettingsCopier::InteractiveDesktopCopy((SettingsCopier *)&v31);
        ATManager::~ATManager((ATManager *)v30);
      }
    }
    return (Start *)v10;
  }
  return result;
}

```

## disassembly

```asm
0x1400172b0  mov     rax, rsp
0x1400172b3  mov     [rax+8], rbx
0x1400172b7  mov     [rax+10h], rsi
0x1400172bb  mov     [rax+18h], r8
0x1400172bf  push    rbp
0x1400172c0  push    rdi
0x1400172c1  push    r12
0x1400172c3  push    r14
0x1400172c5  push    r15
0x1400172c7  lea     rbp, [rax-0E8h]
0x1400172ce  sub     rsp, 1C0h
0x1400172d5  mov     r12d, r9d
0x1400172d8  mov     rdi, rdx
0x1400172db  mov     rsi, rcx
0x1400172de  xor     r15d, r15d
0x1400172e1  mov     dword ptr [rbp+0E0h+arg_10], r15d
0x1400172e8  test    rdx, rdx
0x1400172eb  jnz     short loc_1400172F7
0x1400172ed  mov     eax, 80070057h
0x1400172f2  jmp     loc_140017672
0x1400172f7  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x1400172fc  mov     r14d, eax
0x1400172ff  test    eax, eax
0x140017301  js      loc_140017672
0x140017307  lea     rcx, [rdi+48h]
0x14001730b  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x140017310  test    al, al
0x140017312  jz      short loc_140017373
0x140017314  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140017319  test    eax, eax
0x14001731b  jnz     short loc_140017373
0x14001731d  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x140017322  test    al, al
0x140017324  jz      short loc_140017345
0x140017326  lea     rdx, aSystemsetting; "SystemSetting"
0x14001732d  mov     rcx, [rdi+28h]; String1
0x140017331  call    wcscmp_0
0x140017336  test    eax, eax
0x140017338  jnz     short loc_140017345
0x14001733a  mov     rdx, rdi; struct Accommodation *
0x14001733d  mov     rcx, rsi; this
0x140017340  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x140017345  mov     rcx, [rdi+48h]; unsigned __int16 *
0x140017349  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14001734e  test    rax, rax
0x140017351  jnz     short loc_14001735D
0x140017353  mov     eax, 8007000Eh
0x140017358  jmp     loc_140017672
0x14001735d  xor     r9d, r9d; int
0x140017360  xor     r8d, r8d; int
0x140017363  mov     rdx, rax; struct Accommodation *
0x140017366  mov     rcx, rsi; this
0x140017369  call    ?Start@StartList@@QEAAJPEAVAccommodation@@HH@Z; StartList::Start(Accommodation *,int,int)
0x14001736e  jmp     loc_140017672
0x140017373  lea     rdx, aSystemsetting; "SystemSetting"
0x14001737a  mov     rcx, [rdi+28h]; String1
0x14001737e  call    wcscmp_0
0x140017383  mov     rbx, [rdi+18h]
0x140017387  test    eax, eax
0x140017389  jnz     loc_14001749D
0x14001738f  mov     rcx, rbx
0x140017392  call    cs:__imp__o__wtoi
0x140017399  nop     dword ptr [rax+rax+00h]
0x14001739e  cmp     eax, 16h
0x1400173a1  jnb     loc_14001766F
0x1400173a7  mov     r9d, [rsi+124h]
0x1400173ae  xor     r8d, r8d
0x1400173b1  mov     edx, eax
0x1400173b3  mov     rcx, rdi
0x1400173b6  call    ?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x1400173bb  mov     r14d, eax
0x1400173be  test    eax, eax
0x1400173c0  js      loc_14001766F
0x1400173c6  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400173cb  test    eax, eax
0x1400173cd  jz      short loc_1400173F9
0x1400173cf  mov     rdx, rdi
0x1400173d2  lea     rcx, [rbp+0E0h+arg_10]
0x1400173d9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400173de  mov     r15d, 1
0x1400173e4  mov     rdx, [rax]
0x1400173e7  mov     rcx, rsi
0x1400173ea  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x1400173ef  test    rax, rax
0x1400173f2  jz      short loc_1400173F9
0x1400173f4  mov     bl, r15b
0x1400173f7  jmp     short loc_1400173FB
0x1400173f9  xor     bl, bl
0x1400173fb  test    r15b, 1
0x1400173ff  jz      short loc_140017411
0x140017401  mov     rcx, [rbp+0E0h+arg_10]
0x140017408  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001740c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017411  test    bl, bl
0x140017413  jz      short loc_140017480
0x140017415  mov     rdx, rdi
0x140017418  lea     rcx, [rbp+0E0h+arg_10]
0x14001741f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017424  mov     rdx, [rax]
0x140017427  lea     rcx, [rsi+30h]
0x14001742b  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140017430  mov     rbx, rax
0x140017433  mov     rcx, [rbp+0E0h+arg_10]
0x14001743a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001743e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017443  test    rbx, rbx
0x140017446  jnz     short loc_140017473
0x140017448  mov     rdx, rdi
0x14001744b  lea     rcx, [rbp+0E0h+arg_10]
0x140017452  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017457  mov     rdx, [rax]
0x14001745a  lea     rcx, [rsi+30h]
0x14001745e  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140017463  mov     rcx, [rbp+0E0h+arg_10]
0x14001746a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001746e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017473  mov     rcx, rsi; this
0x140017476  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x14001747b  jmp     loc_14001766F
0x140017480  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x140017485  test    al, al
0x140017487  jz      loc_14001766F
0x14001748d  mov     rdx, rdi; struct Accommodation *
0x140017490  mov     rcx, rsi; this
0x140017493  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x140017498  jmp     loc_14001766F
0x14001749d  test    rbx, rbx
0x1400174a0  jnz     short loc_1400174AC
0x1400174a2  mov     eax, 80004005h
0x1400174a7  jmp     loc_140017672
0x1400174ac  cmp     [rbp+0E0h+arg_20], r15d
0x1400174b3  jnz     loc_1400175A4
0x1400174b9  mov     rdx, rdi; struct Accommodation *
0x1400174bc  call    ?IsColorFiltering@StartList@@AEAA_NPEAVAccommodation@@@Z; StartList::IsColorFiltering(Accommodation *)
0x1400174c1  test    al, al
0x1400174c3  jnz     loc_1400175A4
0x1400174c9  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400174ce  test    eax, eax
0x1400174d0  jz      loc_140017570
0x1400174d6  call    ?IsProcessInATJob@CATUtils@@SAHPEAX@Z; CATUtils::IsProcessInATJob(void *)
0x1400174db  test    eax, eax
0x1400174dd  jnz     loc_140017570
0x1400174e3  cmp     [rdi+40h], r15d
0x1400174e7  jnz     short loc_140017509
0x1400174e9  test    r12d, r12d
0x1400174ec  jz      short loc_1400174FC
0x1400174ee  lea     r8d, [rax+1]; int
0x1400174f2  mov     rdx, rdi; struct Accommodation *
0x1400174f5  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x1400174fa  jmp     short loc_140017569
0x1400174fc  mov     r8, rdi; struct Accommodation *
0x1400174ff  mov     rdx, rbx; unsigned __int16 *
0x140017502  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x140017507  jmp     short loc_140017569
0x140017509  mov     [rsp+1E0h+var_1A0], r15
0x14001750e  mov     [rsp+1E0h+var_198], r15
0x140017513  mov     [rsp+1E0h+var_190], r15
0x140017518  mov     [rsp+1E0h+var_1A8], r15; unsigned int *
0x14001751d  mov     [rsp+1E0h+var_1B8], 2001Fh; REGSAM
0x140017525  mov     [rsp+1E0h+var_1C0], 1; DWORD
0x14001752d  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x140017534  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001753b  lea     rcx, [rsp+1E0h+var_1A0]; this
0x140017540  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140017545  test    eax, eax
0x140017547  jnz     short loc_14001755A
0x140017549  lea     r8d, [rax+3]; unsigned int
0x14001754d  mov     rdx, [rdi]; unsigned __int16 *
0x140017550  lea     rcx, [rsp+1E0h+var_1A0]; this
0x140017555  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14001755a  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14001755f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017564  call    ?SendWinkeyPlusU@@YAXXZ; SendWinkeyPlusU(void)
0x140017569  xor     eax, eax
0x14001756b  jmp     loc_140017672
0x140017570  cmp     [rdi+40h], r15d
0x140017574  jnz     short loc_14001758C
0x140017576  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001757b  test    eax, eax
0x14001757d  jz      short loc_14001758C
0x14001757f  xor     r8d, r8d; int
0x140017582  mov     rdx, rdi; struct Accommodation *
0x140017585  call    ?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z; StartList::CreateBreakawayATProcess(Accommodation *,int)
0x14001758a  jmp     short loc_140017597
0x14001758c  mov     r8, rdi; struct Accommodation *
0x14001758f  mov     rdx, rbx; unsigned __int16 *
0x140017592  call    ?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z; StartList::CreateATProcess(ushort const *,Accommodation *,int)
0x140017597  mov     r14d, eax
0x14001759a  test    eax, eax
0x14001759c  js      loc_14001766F
0x1400175a2  jmp     short loc_1400175B5
0x1400175a4  mov     rdx, rdi; struct Accommodation *
0x1400175a7  call    ?IsColorFiltering@StartList@@AEAA_NPEAVAccommodation@@@Z; StartList::IsColorFiltering(Accommodation *)
0x1400175ac  test    al, al
0x1400175ae  jz      short loc_1400175B5
0x1400175b0  call    ?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ; ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
0x1400175b5  mov     rdx, rdi; struct Accommodation *
0x1400175b8  call    ?LogAccomodationToSQM@StartList@@AEAAXPEAVAccommodation@@@Z; StartList::LogAccomodationToSQM(Accommodation *)
0x1400175bd  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400175c2  test    eax, eax
0x1400175c4  jz      loc_14001766F
0x1400175ca  mov     rdx, rdi
0x1400175cd  lea     rcx, [rbp+0E0h+arg_10]
0x1400175d4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400175d9  mov     rdx, [rax]
0x1400175dc  lea     rcx, [rsi+30h]
0x1400175e0  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x1400175e5  mov     rbx, rax
0x1400175e8  mov     rcx, [rbp+0E0h+arg_10]
0x1400175ef  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400175f3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400175f8  test    rbx, rbx
0x1400175fb  jnz     short loc_140017628
0x1400175fd  mov     rdx, rdi
0x140017600  lea     rcx, [rbp+0E0h+arg_10]
0x140017607  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001760c  mov     rdx, [rax]
0x14001760f  lea     rcx, [rsi+30h]
0x140017613  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140017618  mov     rcx, [rbp+0E0h+arg_10]
0x14001761f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140017623  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017628  mov     rcx, rsi; this
0x14001762b  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x140017630  cmp     [rdi+44h], r15d
0x140017634  jnz     short loc_14001763C
0x140017636  cmp     [rdi+40h], r15d
0x14001763a  jnz     short loc_14001766F
0x14001763c  mov     edx, 1; int
0x140017641  lea     rcx, [rsp+1E0h+var_180]; this
0x140017646  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x14001764b  nop
0x14001764c  lea     rax, [rsp+1E0h+var_180]
0x140017651  mov     [rbp+0E0h+arg_10], rax
0x140017658  lea     rcx, [rbp+0E0h+arg_10]; this
0x14001765f  call    ?InteractiveDesktopCopy@SettingsCopier@@QEAAJXZ; SettingsCopier::InteractiveDesktopCopy(void)
0x140017664  nop
0x140017665  lea     rcx, [rsp+1E0h+var_180]; this
0x14001766a  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14001766f  mov     eax, r14d
0x140017672  lea     r11, [rsp+1E0h+var_20]
0x14001767a  mov     rbx, [r11+30h]
0x14001767e  mov     rsi, [r11+38h]
0x140017682  mov     rsp, r11
0x140017685  pop     r15
0x140017687  pop     r14
0x140017689  pop     r12
0x14001768b  pop     rdi
0x14001768c  pop     rbp
0x14001768d  retn
```
