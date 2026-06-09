# StartList::SaveSessionKey(void)

- ea: `0x140016e8c`
- end: `0x1400170a0`
- name: `?SaveSessionKey@StartList@@AEAAXXZ`
- size: `532`
- prototype: `void __fastcall(StartList *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1400172b0`
- `0x140017904`

## callees

- `0x14000d75c`
- `0x14000ea8c`
- `0x14000f5f4`
- `0x1400136e4`
- `0x140013bac`
- `0x140014290`
- `0x1400169b8`
- `0x140016e8c`
- `0x1400180c8`
- `0x140018130`
- `0x14001827c`
- `0x14001cb14`
- `0x14001cb68`
- `0x14001cdb0`

## string_xrefs

- `0x140016fba`: `SecureConfiguration`
- `0x140017009`: `Configuration`

## pseudocode

```c
void __fastcall StartList::SaveSessionKey(StartList *this)
{
  char v2; // si
  LPCWSTR *v3; // rax
  int v4; // ebx
  LPCWSTR *v5; // rax
  unsigned __int16 *v6; // r9
  int v7; // ebx
  _QWORD *v8; // rax
  int v9; // r8d
  ATL::CStringData *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r8
  unsigned __int16 *v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // r8
  HKEY v16; // [rsp+30h] [rbp-40h]
  _BYTE v17[16]; // [rsp+40h] [rbp-30h] BYREF
  HKEY v18[4]; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v19; // [rsp+98h] [rbp+28h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+30h] BYREF

  v2 = 0;
  LODWORD(v19) = 0;
  _Trace::_Trace((_Trace *)v17, L"StartList::SaveSessionKey", 0);
  memset(v18, 0, 24);
  v3 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v19);
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)v18, HKEY_LOCAL_MACHINE, *v3, 0x20006u);
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
  if ( !v4
    || (v5 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v20),
        v7 = ATL::CRegKey::Create((ATL::CRegKey *)v18, HKEY_LOCAL_MACHINE, *v5, v6, 1u, 3u, v16, (unsigned int *)&v19),
        ATL::CStringData::Release((ATL::CStringData *)(v20 - 24)),
        !v7) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v19);
    StartList::BuildConfigString(&v19, (char *)this + 96);
    v11 = ATL::CRegKey::SetStringValue(v18, L"SecureConfiguration", (const BYTE *)v19);
    if ( v11 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v12, v11);
    StartList::BuildConfigString(&v19, (char *)this + 48);
    v13 = v19;
    v14 = ATL::CRegKey::SetStringValue(v18, StartList::_configuration, (const BYTE *)v19);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v15, v14);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v13);
    }
    v10 = (ATL::CStringData *)(v13 - 12);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v8 = (_QWORD *)CATUtils::SessionKeyString((__int64)&v19);
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v9, *v8, v7);
    v2 = 1;
  }
  if ( (v2 & 1) != 0 )
  {
    v10 = (ATL::CStringData *)(v19 - 12);
LABEL_20:
    ATL::CStringData::Release(v10);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v18);
  _Trace::~_Trace((_Trace *)v17);
}

```

## disassembly

```asm
0x140016e8c  mov     [rsp-18h+arg_0], rbx
0x140016e91  mov     [rsp-18h+arg_18], rsi
0x140016e96  push    rbp
0x140016e97  push    rdi
0x140016e98  push    r14
0x140016e9a  mov     rbp, rsp
0x140016e9d  sub     rsp, 70h
0x140016ea1  mov     r14, rcx
0x140016ea4  lea     rdx, aStartlistSaves; "StartList::SaveSessionKey"
0x140016eab  xor     esi, esi
0x140016ead  lea     rcx, [rbp+var_30]; this
0x140016eb1  xor     r8d, r8d; int *
0x140016eb4  mov     dword ptr [rbp+arg_8], esi
0x140016eb7  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x140016ebc  lea     rcx, [rbp+arg_8]
0x140016ec0  mov     [rbp+var_20], rsi
0x140016ec4  mov     [rbp+var_18], rsi
0x140016ec8  mov     [rbp+var_10], rsi
0x140016ecc  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140016ed1  mov     rdi, 0FFFFFFFF80000002h
0x140016ed8  lea     rcx, [rbp+var_20]; this
0x140016edc  mov     r9d, 20006h; unsigned int
0x140016ee2  mov     rdx, rdi; hKey
0x140016ee5  mov     r8, [rax]; lpSubKey
0x140016ee8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140016eed  mov     rcx, [rbp+arg_8]
0x140016ef1  mov     ebx, eax
0x140016ef3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140016ef7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140016efc  test    ebx, ebx
0x140016efe  jz      loc_140016FA0
0x140016f04  lea     rcx, [rbp+arg_10]
0x140016f08  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140016f0d  lea     rcx, [rbp+arg_8]
0x140016f11  mov     rdx, rdi; hKey
0x140016f14  mov     [rsp+70h+var_38], rcx; unsigned int *
0x140016f19  lea     rcx, [rbp+var_20]; this
0x140016f1d  mov     [rsp+70h+var_48], 3; REGSAM
0x140016f25  mov     r8, [rax]; lpSubKey
0x140016f28  mov     [rsp+70h+var_50], 1; DWORD
0x140016f30  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140016f35  mov     rcx, [rbp+arg_10]
0x140016f39  mov     ebx, eax
0x140016f3b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140016f3f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140016f44  test    ebx, ebx
0x140016f46  jz      short loc_140016FA0
0x140016f48  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f4f  lea     rdi, WPP_GLOBAL_Control
0x140016f56  cmp     rcx, rdi
0x140016f59  jz      short loc_140016F89
0x140016f5b  test    byte ptr [rcx+1Ch], 8
0x140016f5f  jz      short loc_140016F89
0x140016f61  lea     rcx, [rbp+arg_8]
0x140016f65  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140016f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f71  lea     edx, [rsi+19h]
0x140016f74  mov     [rsp+70h+var_50], ebx
0x140016f78  mov     r9, [rax]
0x140016f7b  mov     rcx, [rcx+10h]
0x140016f7f  call    WPP_SF_Sd
0x140016f84  mov     esi, 1
0x140016f89  test    sil, 1
0x140016f8d  jz      loc_140017078
0x140016f93  mov     rcx, [rbp+arg_8]
0x140016f97  add     rcx, 0FFFFFFFFFFFFFFE8h
0x140016f9b  jmp     loc_140017073
0x140016fa0  lea     rcx, [rbp+arg_8]
0x140016fa4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140016fa9  lea     rdx, [r14+60h]
0x140016fad  lea     rcx, [rbp+arg_8]
0x140016fb1  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140016fb6  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x140016fba  lea     rdx, ?c_secureConfiguration@StartList@@0QBGB; "SecureConfiguration"
0x140016fc1  lea     rcx, [rbp+var_20]; this
0x140016fc5  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140016fca  lea     rdi, WPP_GLOBAL_Control
0x140016fd1  test    eax, eax
0x140016fd3  jz      short loc_140016FF8
0x140016fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fdc  cmp     rcx, rdi
0x140016fdf  jz      short loc_140016FF8
0x140016fe1  test    byte ptr [rcx+1Ch], 8
0x140016fe5  jz      short loc_140016FF8
0x140016fe7  mov     rcx, [rcx+10h]
0x140016feb  mov     edx, 1Ah
0x140016ff0  mov     r9d, eax
0x140016ff3  call    WPP_SF_d
0x140016ff8  lea     rdx, [r14+30h]
0x140016ffc  lea     rcx, [rbp+arg_8]
0x140017000  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140017005  mov     rbx, [rbp+arg_8]
0x140017009  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x140017010  mov     r8, rbx; unsigned __int16 *
0x140017013  lea     rcx, [rbp+var_20]; this
0x140017017  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x14001701c  test    eax, eax
0x14001701e  jz      short loc_140017045
0x140017020  mov     rcx, cs:WPP_GLOBAL_Control
0x140017027  cmp     rcx, rdi
0x14001702a  jz      short loc_14001706F
0x14001702c  test    byte ptr [rcx+1Ch], 8
0x140017030  jz      short loc_14001706F
0x140017032  mov     rcx, [rcx+10h]
0x140017036  mov     edx, 1Bh
0x14001703b  mov     r9d, eax
0x14001703e  call    WPP_SF_d
0x140017043  jmp     short loc_14001706F
0x140017045  mov     rcx, cs:WPP_GLOBAL_Control
0x14001704c  cmp     rcx, rdi
0x14001704f  jz      short loc_14001706F
0x140017051  test    byte ptr [rcx+1Ch], 10h
0x140017055  jz      short loc_14001706F
0x140017057  mov     rcx, [rcx+10h]
0x14001705b  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140017062  mov     edx, 1Ch
0x140017067  mov     r9, rbx
0x14001706a  call    WPP_SF_S
0x14001706f  lea     rcx, [rbx-18h]; this
0x140017073  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140017078  lea     rcx, [rbp+var_20]; this
0x14001707c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017081  lea     rcx, [rbp+var_30]; this
0x140017085  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14001708a  lea     r11, [rsp+70h+var_s0]
0x14001708f  mov     rbx, [r11+20h]
0x140017093  mov     rsi, [r11+38h]
0x140017097  mov     rsp, r11
0x14001709a  pop     r14
0x14001709c  pop     rdi
0x14001709d  pop     rbp
0x14001709e  retn
```
