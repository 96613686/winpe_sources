# StartList::LoadSettings(void)

- ea: `0x140015fb8`
- end: `0x14001641b`
- name: `?LoadSettings@StartList@@AEAAJXZ`
- size: `1123`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `7`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013ec4`
- `0x1400169e8`
- `0x1400172b0`
- `0x140017698`
- `0x140017904`
- `0x140017b08`
- `0x14001cfa0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000d75c`
- `0x14000e550`
- `0x14000ea8c`
- `0x14000ecdc`
- `0x140013b44`
- `0x140013bac`
- `0x140014058`
- `0x140014128`
- `0x140014310`
- `0x14001443c`
- `0x140015210`
- `0x140015300`
- `0x140015468`
- `0x140015600`
- `0x140015720`
- `0x140015fb8`
- `0x1400169b8`
- `0x1400171ec`
- `0x140018084`
- `0x14001cc74`
- `0x14001ccd0`
- `0x1400269f0`

## string_xrefs

- `0x140016310`: `Configuration`
- `0x1400162e3`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StartList::LoadSettings(StartList *this)
{
  StartList *v3; // rcx
  unsigned int v4; // r8d
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // r8d
  StartList *v9; // rcx
  unsigned int v10; // r8d
  int UserValue; // eax
  int v12; // edi
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  StartList *v16; // rcx
  __int64 v17; // r8
  StartList *v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // r8
  __int64 v21; // r8
  unsigned int v22; // [rsp+20h] [rbp-E0h]
  char *v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v30[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v31[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v32[1024]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v33[1024]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v34[1024]; // [rsp+10A0h] [rbp+FA0h] BYREF

  if ( *((_DWORD *)this + 72) )
    return 0;
  *((_DWORD *)this + 72) = 1;
  if ( CATUtils::IsDesktopOOBERunning() )
  {
    memset_0(v33, 0, sizeof(v33));
    v26 = 0;
    v27 = 0;
    v28 = 0;
    StartList::GetSettingConfigurationValue(v3, v33, v4, (struct ATL::CRegKey *)&v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v25,
      v33);
    StartList::BuildConfigList(&v25, (char *)this + 144);
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    ATL::CRegKey::Close((ATL::CRegKey *)&v26);
  }
  v5 = IsInteractiveUser();
  memset(v31, 0, 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
  StartList::BuildSessionListStringBasedOnCurrentSessionContext(v6, v5, &v25, v31);
  StartList::BuildConfigList(&v25, (char *)this + 48);
  memset_0(v32, 0, sizeof(v32));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v23);
  v7 = v25;
  if ( !v5 )
  {
    if ( !CATUtils::IsMachineOOBERunning() )
    {
      StartList::GetSessionValue(v18, v32, v19, (struct ATL::CRegKey *)v31, 1);
      v21 = -1;
      do
        ++v21;
      while ( v32[v21] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, v32, v21);
      if ( *((_DWORD *)v23 - 4) )
        ATL::CSimpleStringT<unsigned short,0>::Append(&v23, L",", 1);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v23, v7, *(unsigned int *)(v7 - 16));
      goto LABEL_36;
    }
    v26 = 0;
    v27 = 0;
    v28 = 0;
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)&v26,
                          HKEY_LOCAL_MACHINE,
                          StartList::_oobeAccessibilityKeyString,
                          0x20019u) )
    {
      v24[0] = 1024;
      if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v26, L"Configuration", v32, v24) )
        v32[0] = 0;
    }
    v20 = -1;
    do
      ++v20;
    while ( v32[v20] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, v32, v20);
LABEL_30:
    ATL::CRegKey::Close((ATL::CRegKey *)&v26);
LABEL_36:
    StartList::BuildConfigList(&v23, this);
    v12 = 0;
    goto LABEL_37;
  }
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v33, 0, sizeof(v33));
  memset_0(v34, 0, sizeof(v34));
  StartList::GetTempValue(this, v33, v8, v34, v22, (struct ATL::CRegKey *)&v26);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v29,
    v33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v24,
    v34);
  StartList::BuildConfigList(&v29, (char *)this + 192);
  StartList::BuildConfigList(v24, (char *)this + 240);
  memset(v30, 0, sizeof(v30));
  UserValue = StartList::GetUserValue(v9, v32, v10, (struct ATL::CRegKey *)v30);
  v12 = UserValue;
  if ( UserValue >= 0 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v32[v17] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, v32, v17);
LABEL_22:
    StartList::ClearSessionSecureConfiguration(v16, (struct ATL::CRegKey *)v31);
    ATL::CRegKey::Close((ATL::CRegKey *)v30);
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v24 - 24LL));
    ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
    goto LABEL_30;
  }
  v13 = UserValue & 0x1FFF0000;
  if ( (_DWORD)v13 == 458752 )
    UserValue = (unsigned __int16)UserValue;
  if ( UserValue == 2 )
  {
    v12 = StartList::HandleFirstTime(v13, (LPCWSTR *)this + 6, &v23, (ATL::CRegKey *)v30);
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_18;
      v15 = 21;
      goto LABEL_17;
    }
    goto LABEL_22;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    goto LABEL_18;
  v15 = 20;
LABEL_17:
  WPP_SF_D(v14[2], v15, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, (unsigned int)v12);
LABEL_18:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v24 - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)&v26);
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140015fb8  mov     [rsp-8+arg_8], rbx
0x140015fbd  mov     [rsp-8+arg_10], rsi
0x140015fc2  push    rbp
0x140015fc3  push    rdi
0x140015fc4  push    r13
0x140015fc6  push    r14
0x140015fc8  push    r15
0x140015fca  lea     rbp, [rsp-17B0h]
0x140015fd2  mov     eax, 18B0h
0x140015fd7  call    _alloca_probe
0x140015fdc  sub     rsp, rax
0x140015fdf  mov     rax, cs:__security_cookie
0x140015fe6  xor     rax, rsp
0x140015fe9  mov     [rbp+17D0h+var_30], rax
0x140015ff0  mov     rsi, rcx
0x140015ff3  xor     r15d, r15d
0x140015ff6  cmp     [rcx+120h], r15d
0x140015ffd  jz      short loc_140016006
0x140015fff  xor     eax, eax
0x140016001  jmp     loc_1400163EF
0x140016006  mov     dword ptr [rcx+120h], 1
0x140016010  call    ?IsDesktopOOBERunning@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBERunning(void)
0x140016015  mov     r13d, 800h
0x14001601b  test    al, al
0x14001601d  jz      short loc_14001608A
0x14001601f  mov     r8d, r13d; Size
0x140016022  xor     edx, edx; Val
0x140016024  lea     rcx, [rbp+17D0h+var_1030]; void *
0x14001602b  call    memset_0
0x140016030  mov     [rsp+18D0h+var_1888], r15
0x140016035  mov     [rsp+18D0h+var_1880], r15
0x14001603a  mov     [rsp+18D0h+var_1878], r15
0x14001603f  lea     r9, [rsp+18D0h+var_1888]; struct ATL::CRegKey *
0x140016044  lea     rdx, [rbp+17D0h+var_1030]; unsigned __int16 *
0x14001604b  call    ?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)
0x140016050  lea     rdx, [rbp+17D0h+var_1030]
0x140016057  lea     rcx, [rsp+18D0h+var_1890]
0x14001605c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140016061  lea     rdx, [rsi+90h]
0x140016068  lea     rcx, [rsp+18D0h+var_1890]
0x14001606d  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x140016072  mov     rcx, [rsp+18D0h+var_1890]
0x140016077  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001607b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140016080  lea     rcx, [rsp+18D0h+var_1888]; this
0x140016085  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001608a  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001608f  mov     edi, eax
0x140016091  mov     [rbp+17D0h+var_1850], r15
0x140016095  mov     [rbp+17D0h+var_1848], r15
0x140016099  mov     [rbp+17D0h+var_1840], r15
0x14001609d  lea     rcx, [rsp+18D0h+var_1890]
0x1400160a2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400160a7  nop
0x1400160a8  lea     r9, [rbp+17D0h+var_1850]
0x1400160ac  lea     r8, [rsp+18D0h+var_1890]
0x1400160b1  mov     edx, edi
0x1400160b3  call    ?BuildSessionListStringBasedOnCurrentSessionContext@StartList@@AEBAXHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@@Z; StartList::BuildSessionListStringBasedOnCurrentSessionContext(int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x1400160b8  lea     rdx, [rsi+30h]
0x1400160bc  lea     rcx, [rsp+18D0h+var_1890]
0x1400160c1  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x1400160c6  mov     r8, r13; Size
0x1400160c9  xor     edx, edx; Val
0x1400160cb  lea     rcx, [rbp+17D0h+var_1830]; void *
0x1400160cf  call    memset_0
0x1400160d4  lea     rcx, [rsp+18D0h+var_18A0]
0x1400160d9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400160de  nop
0x1400160df  mov     rbx, [rsp+18D0h+var_1890]
0x1400160e4  test    edi, edi
0x1400160e6  jz      loc_1400162C1
0x1400160ec  mov     [rsp+18D0h+var_1888], r15
0x1400160f1  mov     [rsp+18D0h+var_1880], r15
0x1400160f6  mov     [rsp+18D0h+var_1878], r15
0x1400160fb  mov     r8, r13; Size
0x1400160fe  xor     edx, edx; Val
0x140016100  lea     rcx, [rbp+17D0h+var_1030]; void *
0x140016107  call    memset_0
0x14001610c  mov     r8, r13; Size
0x14001610f  xor     edx, edx; Val
0x140016111  lea     rcx, [rbp+17D0h+var_830]; void *
0x140016118  call    memset_0
0x14001611d  lea     rax, [rsp+18D0h+var_1888]
0x140016122  mov     [rsp+18D0h+var_18A8], rax; struct ATL::CRegKey *
0x140016127  lea     r9, [rbp+17D0h+var_830]; unsigned __int16 *
0x14001612e  lea     rdx, [rbp+17D0h+var_1030]; unsigned __int16 *
0x140016135  mov     rcx, rsi; this
0x140016138  call    ?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z; StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)
0x14001613d  lea     rdx, [rbp+17D0h+var_1030]
0x140016144  lea     rcx, [rsp+18D0h+var_1870]
0x140016149  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001614e  nop
0x14001614f  lea     rdx, [rbp+17D0h+var_830]
0x140016156  lea     rcx, [rsp+18D0h+var_1898]
0x14001615b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140016160  nop
0x140016161  lea     rdx, [rsi+0C0h]
0x140016168  lea     rcx, [rsp+18D0h+var_1870]
0x14001616d  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x140016172  lea     rdx, [rsi+0F0h]
0x140016179  lea     rcx, [rsp+18D0h+var_1898]
0x14001617e  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x140016183  mov     [rsp+18D0h+var_1868], r15
0x140016188  mov     [rsp+18D0h+var_1860], r15
0x14001618d  mov     [rsp+18D0h+var_1858], r15
0x140016192  lea     r9, [rsp+18D0h+var_1868]; struct ATL::CRegKey *
0x140016197  lea     rdx, [rbp+17D0h+var_1830]; unsigned __int16 *
0x14001619b  call    ?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)
0x1400161a0  mov     edi, eax
0x1400161a2  test    eax, eax
0x1400161a4  jns     loc_140016269
0x1400161aa  mov     ecx, eax
0x1400161ac  and     ecx, 1FFF0000h
0x1400161b2  cmp     ecx, 70000h
0x1400161b8  jnz     short loc_1400161BD
0x1400161ba  movzx   eax, di
0x1400161bd  cmp     eax, 2
0x1400161c0  jz      short loc_1400161E2
0x1400161c2  lea     rax, WPP_GLOBAL_Control
0x1400161c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400161d0  cmp     rcx, rax
0x1400161d3  jz      short loc_140016231
0x1400161d5  test    byte ptr [rcx+1Ch], 8
0x1400161d9  jz      short loc_140016231
0x1400161db  mov     edx, 14h
0x1400161e0  jmp     short loc_14001621D
0x1400161e2  lea     r9, [rsp+18D0h+var_1868]
0x1400161e7  lea     r8, [rsp+18D0h+var_18A0]
0x1400161ec  lea     rdx, [rsi+30h]
0x1400161f0  call    ?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z; StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x1400161f5  mov     edi, eax
0x1400161f7  test    eax, eax
0x1400161f9  jns     loc_140016289
0x1400161ff  lea     rax, WPP_GLOBAL_Control
0x140016206  mov     rcx, cs:WPP_GLOBAL_Control
0x14001620d  cmp     rcx, rax
0x140016210  jz      short loc_140016231
0x140016212  test    byte ptr [rcx+1Ch], 8
0x140016216  jz      short loc_140016231
0x140016218  mov     edx, 15h
0x14001621d  mov     r9d, edi
0x140016220  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140016227  mov     rcx, [rcx+10h]
0x14001622b  call    WPP_SF_D
0x140016230  nop
0x140016231  lea     rcx, [rsp+18D0h+var_1868]; this
0x140016236  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001623b  nop
0x14001623c  mov     rcx, qword ptr [rsp+18D0h+var_1898]
0x140016241  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140016245  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001624a  nop
0x14001624b  mov     rcx, [rsp+18D0h+var_1870]
0x140016250  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140016254  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140016259  nop
0x14001625a  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001625f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140016264  jmp     loc_1400163CB
0x140016269  lea     rax, [rbp+17D0h+var_1830]
0x14001626d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140016271  inc     r8
0x140016274  cmp     [rax+r8*2], r15w
0x140016279  jnz     short loc_140016271
0x14001627b  lea     rdx, [rbp+17D0h+var_1830]
0x14001627f  lea     rcx, [rsp+18D0h+var_18A0]
0x140016284  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016289  lea     rdx, [rbp+17D0h+var_1850]; struct ATL::CRegKey *
0x14001628d  call    ?ClearSessionSecureConfiguration@StartList@@AEBAXAEAVCRegKey@ATL@@@Z; StartList::ClearSessionSecureConfiguration(ATL::CRegKey &)
0x140016292  nop
0x140016293  lea     rcx, [rsp+18D0h+var_1868]; this
0x140016298  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001629d  nop
0x14001629e  mov     rcx, qword ptr [rsp+18D0h+var_1898]
0x1400162a3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400162a7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400162ac  nop
0x1400162ad  mov     rcx, [rsp+18D0h+var_1870]
0x1400162b2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400162b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400162bb  nop
0x1400162bc  jmp     loc_14001634A
0x1400162c1  call    ?IsMachineOOBERunning@CATUtils@@SA_NXZ; CATUtils::IsMachineOOBERunning(void)
0x1400162c6  test    al, al
0x1400162c8  jz      loc_140016356
0x1400162ce  mov     [rsp+18D0h+var_1888], r15
0x1400162d3  mov     [rsp+18D0h+var_1880], r15
0x1400162d8  mov     [rsp+18D0h+var_1878], r15
0x1400162dd  mov     r9d, 20019h; unsigned int
0x1400162e3  lea     r8, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400162ea  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400162f1  lea     rcx, [rsp+18D0h+var_1888]; this
0x1400162f6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400162fb  test    eax, eax
0x1400162fd  jnz     short loc_14001632A
0x1400162ff  mov     [rsp+18D0h+var_1898], 400h
0x140016307  lea     r9, [rsp+18D0h+var_1898]; unsigned int *
0x14001630c  lea     r8, [rbp+17D0h+var_1830]; unsigned __int16 *
0x140016310  lea     rdx, aConfiguration; "Configuration"
0x140016317  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001631c  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140016321  test    eax, eax
0x140016323  jz      short loc_14001632A
0x140016325  mov     [rbp+17D0h+var_1830], r15w
0x14001632a  lea     rax, [rbp+17D0h+var_1830]
0x14001632e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140016332  inc     r8
0x140016335  cmp     [rax+r8*2], r15w
0x14001633a  jnz     short loc_140016332
0x14001633c  lea     rdx, [rbp+17D0h+var_1830]
0x140016340  lea     rcx, [rsp+18D0h+var_18A0]
0x140016345  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001634a  lea     rcx, [rsp+18D0h+var_1888]; this
0x14001634f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140016354  jmp     short loc_1400163BB
0x140016356  mov     [rsp+18D0h+var_18B0], 1; bool
0x14001635b  lea     r9, [rbp+17D0h+var_1850]; struct ATL::CRegKey *
0x14001635f  lea     rdx, [rbp+17D0h+var_1830]; unsigned __int16 *
0x140016363  call    ?GetSessionValue@StartList@@AEBAXPEAGIAEAVCRegKey@ATL@@_N@Z; StartList::GetSessionValue(ushort *,uint,ATL::CRegKey &,bool)
0x140016368  lea     rax, [rbp+17D0h+var_1830]
0x14001636c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140016370  inc     r8
0x140016373  cmp     [rax+r8*2], r15w
0x140016378  jnz     short loc_140016370
0x14001637a  lea     rdx, [rbp+17D0h+var_1830]
0x14001637e  lea     rcx, [rsp+18D0h+var_18A0]
0x140016383  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016388  mov     rax, [rsp+18D0h+var_18A0]
0x14001638d  cmp     [rax-10h], r15d
0x140016391  jz      short loc_1400163AA
0x140016393  mov     r8d, 1
0x140016399  lea     rdx, asc_14002D6B4; ","
0x1400163a0  lea     rcx, [rsp+18D0h+var_18A0]
0x1400163a5  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400163aa  mov     r8d, [rbx-10h]
0x1400163ae  mov     rdx, rbx
0x1400163b1  lea     rcx, [rsp+18D0h+var_18A0]
0x1400163b6  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400163bb  mov     rdx, rsi
0x1400163be  lea     rcx, [rsp+18D0h+var_18A0]
0x1400163c3  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x1400163c8  mov     edi, r15d
0x1400163cb  mov     rcx, [rsp+18D0h+var_18A0]
0x1400163d0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400163d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400163d9  nop
0x1400163da  lea     rcx, [rbx-18h]; this
0x1400163de  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400163e3  nop
0x1400163e4  lea     rcx, [rbp+17D0h+var_1850]; this
0x1400163e8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400163ed  mov     eax, edi
0x1400163ef  mov     rcx, [rbp+17D0h+var_30]
0x1400163f6  xor     rcx, rsp; StackCookie
0x1400163f9  call    __security_check_cookie
0x1400163fe  lea     r11, [rsp+18D0h+var_20]
0x140016406  mov     rbx, [r11+38h]
0x14001640a  mov     rsi, [r11+40h]
0x14001640e  mov     rsp, r11
0x140016411  pop     r15
0x140016413  pop     r14
0x140016415  pop     r13
0x140016417  pop     rdi
0x140016418  pop     rbp
0x140016419  retn
```
