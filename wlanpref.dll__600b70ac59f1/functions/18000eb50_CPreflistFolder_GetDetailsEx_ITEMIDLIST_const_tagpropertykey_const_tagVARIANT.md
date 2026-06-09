# CPreflistFolder::GetDetailsEx(_ITEMIDLIST const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x18000eb50`
- end: `0x18000ee95`
- name: `?GetDetailsEx@CPreflistFolder@@UEAAJPEFBU_ITEMIDLIST@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `837`
- prototype: `int(CPreflistFolder *__hidden this, const struct _ITEMIDLIST *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1800036ac`
- `0x1800036fc`
- `0x180008484`
- `0x18000d388`
- `0x18000d494`
- `0x18000eb50`
- `0x18000f28c`
- `0x18000fc60`
- `0x180010f08`
- `0x1800110a4`
- `0x180027594`
- `0x180027ad4`
- `0x180027db0`
- `0x18002868c`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ec00`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ecf0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000edd5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ee5d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ec00`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ecf0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000edd5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ee5d`
- `OLEAUT32!__imp_VariantInit` at `0x18000eb92`
- `OLEAUT32!__imp_VariantInit` at `0x18000eb92`

## string_xrefs

- `0x18000ee23`: `^System.Wireless.Security;`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPreflistFolder::GetDetailsEx(
        CPreflistFolder *this,
        const struct _ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  CProfile *v8; // rcx
  __int64 v9; // rax
  int v10; // ebx
  OLECHAR *v11; // rcx
  DWORD pid; // eax
  __int64 v13; // rax
  LONG v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int64 i; // rbx
  __int64 v19; // rax
  OLECHAR *strIn; // [rsp+20h] [rbp-79h] BYREF
  __int128 v21; // [rsp+28h] [rbp-71h] BYREF
  __int64 v22; // [rsp+38h] [rbp-61h]
  __int128 v23; // [rsp+40h] [rbp-59h]
  int v24; // [rsp+50h] [rbp-49h]
  _BYTE v25[96]; // [rsp+60h] [rbp-39h] BYREF

  if ( a2 )
  {
    if ( a4 )
    {
      VariantInit(a4);
      if ( a3 )
      {
        StructToProfile((CProfile *)v25, (const struct WPLDATA *)a2->mkid.abID);
        if ( a3->pid == 8 )
        {
          v9 = *(_QWORD *)&a3->fmtid.Data1 - 0x488D949C9B34BBB9LL;
          if ( *(_QWORD *)&a3->fmtid.Data1 == 0x488D949C9B34BBB9LL )
            v9 = *(_QWORD *)a3->fmtid.Data4 - 0x2F7A847CB4EE6D9ALL;
          if ( !v9 )
          {
            strIn = (OLECHAR *)WTL::_atltmpPchNil;
            WTL::CString::LoadStringW((WTL::CString *)&strIn, 20016 - (v25[81] != 0));
            a4->vt = 8;
            a4->llVal = (LONGLONG)SysAllocStringLen(strIn, *((_DWORD *)strIn - 2));
            v10 = 0;
LABEL_36:
            WTL::CString::~CString((WTL::CString *)&strIn);
            goto LABEL_37;
          }
        }
        if ( CProfile::HasProperty(v8, a3) )
        {
          CProfile::GetProperty(v25, &strIn, a3);
          v11 = strIn;
LABEL_23:
          a4->vt = 8;
          a4->llVal = (LONGLONG)SysAllocStringLen(v11, *((_DWORD *)v11 - 2));
          v10 = 0;
          goto LABEL_36;
        }
        pid = a3->pid;
        switch ( pid )
        {
          case 3u:
            v13 = *(_QWORD *)&a3->fmtid.Data1 - 0x488D949C9B34BBB9LL;
            if ( *(_QWORD *)&a3->fmtid.Data1 == 0x488D949C9B34BBB9LL )
              v13 = *(_QWORD *)a3->fmtid.Data4 - 0x2F7A847CB4EE6D9ALL;
            if ( !v13 )
            {
              CPreflistFolder::InitializeDataSource((CPreflistFolder *)((char *)this - 8));
              v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                                + 64LL))(
                      CSingletonPtr<CWlanProfileStore>::s_pInstance,
                      v25);
              a4->vt = 22;
              a4->lVal = v14;
              v10 = 0;
LABEL_37:
              CProfile::~CProfile((CProfile *)v25);
              return (unsigned int)v10;
            }
            v15 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1;
            if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1 )
              v15 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_TileInfo.fmtid.Data4;
LABEL_28:
            if ( !v15 )
            {
              strIn = (OLECHAR *)WTL::_atltmpPchNil;
              v21 = 0;
              v22 = 0;
              v23 = 0;
              v24 = 10;
              ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(&v21);
              for ( i = 0; i < 6; ++i )
              {
                if ( LODWORD(qword_18003F5B0[6 * i + 4]) )
                  ATL::CAtlList<_tagpropertykey,ATL::CElementTraits<_tagpropertykey>>::AddTail(
                    &v21,
                    &qword_18003F5B0[6 * i]);
              }
              v10 = CPreflistFolder::PropertyKeyListToString(&v21, &strIn);
              if ( v10 >= 0 )
              {
                a4->vt = 8;
                a4->llVal = (LONGLONG)SysAllocStringLen(strIn, *((_DWORD *)strIn - 2));
              }
              ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(&v21);
              goto LABEL_36;
            }
            break;
          case 4u:
            v16 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1;
            if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1 )
              v16 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_InfoTip.fmtid.Data4;
            if ( !v16 )
            {
              CPreflistFolder::GetInfoTip((char *)this - 8, &strIn, v25);
              v11 = strIn;
              if ( !*strIn )
              {
                v10 = -2147467263;
                goto LABEL_36;
              }
              goto LABEL_23;
            }
            break;
          case 8u:
            v15 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1;
            if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 )
              v15 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4;
            goto LABEL_28;
          case 9u:
            v19 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_ExtendedTileInfo.fmtid.Data1;
            if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_ExtendedTileInfo.fmtid.Data1 )
              v19 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_ExtendedTileInfo.fmtid.Data4;
            if ( !v19 )
            {
              v10 = 0;
              strIn = (OLECHAR *)WTL::_atltmpPchNil;
              WTL::CString::operator=((WTL::CString *)&strIn, L"prop:");
              WTL::CString::operator+=((WTL::CString *)&strIn, L"^System.Wireless.Security;");
              WTL::CString::operator+=((WTL::CString *)&strIn, L"^System.Wireless.RadioType;");
              WTL::CString::operator+=((WTL::CString *)&strIn, L"^~System.Wireless.ConnectionMode;");
              a4->vt = 8;
              a4->llVal = (LONGLONG)SysAllocStringLen(strIn, *((_DWORD *)strIn - 2));
              goto LABEL_36;
            }
            break;
        }
        v10 = -2147467263;
        goto LABEL_37;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000eb50  push    rbp
0x18000eb52  push    rbx
0x18000eb53  push    rsi
0x18000eb54  push    rdi
0x18000eb55  push    r14
0x18000eb57  lea     rbp, [rsp-37h]
0x18000eb5c  sub     rsp, 0D0h
0x18000eb63  mov     rax, cs:__security_cookie
0x18000eb6a  xor     rax, rsp
0x18000eb6d  mov     [rbp+57h+var_30], rax
0x18000eb71  mov     rdi, r9
0x18000eb74  mov     rbx, r8
0x18000eb77  mov     rsi, rdx
0x18000eb7a  mov     r14, rcx
0x18000eb7d  test    rdx, rdx
0x18000eb80  jz      loc_18000EE76
0x18000eb86  test    r9, r9
0x18000eb89  jz      loc_18000EE76
0x18000eb8f  mov     rcx, r9; pvarg
0x18000eb92  call    cs:__imp_VariantInit
0x18000eb98  test    rbx, rbx
0x18000eb9b  jz      loc_18000EE76
0x18000eba1  lea     rdx, [rsi+2]
0x18000eba5  lea     rcx, [rbp+57h+var_90]
0x18000eba9  call    ?StructToProfile@@YA?AVCProfile@@AEBUWPLDATA@@@Z; StructToProfile(WPLDATA const &)
0x18000ebae  nop
0x18000ebaf  mov     esi, 8
0x18000ebb4  cmp     [rbx+10h], esi
0x18000ebb7  jnz     short loc_18000EC11
0x18000ebb9  mov     rax, [rbx]
0x18000ebbc  sub     rax, qword ptr cs:xmmword_1800354A8
0x18000ebc3  jnz     short loc_18000EBD0
0x18000ebc5  mov     rax, [rbx+8]
0x18000ebc9  sub     rax, qword ptr cs:xmmword_1800354A8+8
0x18000ebd0  test    rax, rax
0x18000ebd3  jnz     short loc_18000EC11
0x18000ebd5  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18000ebdc  mov     [rbp+57h+strIn], rax
0x18000ebe0  mov     al, [rbp+57h+var_3F]
0x18000ebe3  neg     al
0x18000ebe5  sbb     edx, edx
0x18000ebe7  add     edx, 4E30h; uID
0x18000ebed  lea     rcx, [rbp+57h+strIn]; this
0x18000ebf1  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x18000ebf6  mov     [rdi], si
0x18000ebf9  mov     rcx, [rbp+57h+strIn]; strIn
0x18000ebfd  mov     edx, [rcx-8]; ui
0x18000ec00  call    cs:__imp_SysAllocStringLen
0x18000ec06  mov     [rdi+8], rax
0x18000ec0a  xor     ebx, ebx
0x18000ec0c  jmp     loc_18000EDB1
0x18000ec11  mov     rdx, rbx; struct _tagpropertykey *
0x18000ec14  call    ?HasProperty@CProfile@@QEBA_NAEBU_tagpropertykey@@@Z; CProfile::HasProperty(_tagpropertykey const &)
0x18000ec19  test    al, al
0x18000ec1b  jz      short loc_18000EC36
0x18000ec1d  mov     r8, rbx
0x18000ec20  lea     rdx, [rbp+57h+strIn]
0x18000ec24  lea     rcx, [rbp+57h+var_90]
0x18000ec28  call    ?GetProperty@CProfile@@QEBA?AVCString@WTL@@AEBU_tagpropertykey@@@Z; CProfile::GetProperty(_tagpropertykey const &)
0x18000ec2d  mov     rcx, [rbp+57h+strIn]
0x18000ec31  jmp     loc_18000ECEA
0x18000ec36  mov     eax, [rbx+10h]
0x18000ec39  cmp     eax, 3
0x18000ec3c  jnz     short loc_18000ECA9
0x18000ec3e  mov     rax, [rbx]
0x18000ec41  sub     rax, qword ptr cs:stru_1800354C0.fmtid.Data1
0x18000ec48  jnz     short loc_18000EC55
0x18000ec4a  mov     rax, [rbx+8]
0x18000ec4e  sub     rax, qword ptr cs:stru_1800354C0.fmtid.Data4
0x18000ec55  test    rax, rax
0x18000ec58  jnz     short loc_18000EC89
0x18000ec5a  lea     rcx, [r14-8]; this
0x18000ec5e  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000ec63  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000ec6a  mov     rax, [rcx]
0x18000ec6d  lea     rdx, [rbp+57h+var_90]
0x18000ec71  mov     rax, [rax+40h]
0x18000ec75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec7a  mov     word ptr [rdi], 16h
0x18000ec7f  mov     [rdi+8], eax
0x18000ec82  xor     ebx, ebx
0x18000ec84  jmp     loc_18000EDBB
0x18000ec89  mov     rax, [rbx]
0x18000ec8c  sub     rax, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data1
0x18000ec93  jnz     loc_18000ED2A
0x18000ec99  mov     rax, [rbx+8]
0x18000ec9d  sub     rax, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data4
0x18000eca4  jmp     loc_18000ED2A
0x18000eca9  cmp     eax, 4
0x18000ecac  jnz     short loc_18000ED0B
0x18000ecae  mov     rax, [rbx]
0x18000ecb1  sub     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data1
0x18000ecb8  jnz     short loc_18000ECC5
0x18000ecba  mov     rax, [rbx+8]
0x18000ecbe  sub     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data4
0x18000ecc5  test    rax, rax
0x18000ecc8  jnz     loc_18000EE6C
0x18000ecce  lea     rcx, [r14-8]
0x18000ecd2  lea     r8, [rbp+57h+var_90]
0x18000ecd6  lea     rdx, [rbp+57h+strIn]
0x18000ecda  call    ?GetInfoTip@CPreflistFolder@@IEAA?AVCString@WTL@@AEBVCProfile@@@Z; CPreflistFolder::GetInfoTip(CProfile const &)
0x18000ecdf  mov     rcx, [rbp+57h+strIn]; strIn
0x18000ece3  xor     eax, eax
0x18000ece5  cmp     [rcx], ax
0x18000ece8  jz      short loc_18000ED01
0x18000ecea  mov     [rdi], si
0x18000eced  mov     edx, [rcx-8]; ui
0x18000ecf0  call    cs:__imp_SysAllocStringLen
0x18000ecf6  mov     [rdi+8], rax
0x18000ecfa  xor     ebx, ebx
0x18000ecfc  jmp     loc_18000EDB1
0x18000ed01  mov     ebx, 80004001h
0x18000ed06  jmp     loc_18000EDB1
0x18000ed0b  cmp     eax, esi
0x18000ed0d  jnz     loc_18000EDE1
0x18000ed13  mov     rax, [rbx]
0x18000ed16  sub     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x18000ed1d  jnz     short loc_18000ED2A
0x18000ed1f  mov     rax, [rbx+8]
0x18000ed23  sub     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x18000ed2a  test    rax, rax
0x18000ed2d  jnz     loc_18000EE6C
0x18000ed33  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18000ed3a  mov     [rbp+57h+strIn], rax
0x18000ed3e  xorps   xmm0, xmm0
0x18000ed41  movdqu  [rbp+57h+var_C8], xmm0
0x18000ed46  mov     [rbp+57h+var_B8], 0
0x18000ed4e  xorps   xmm1, xmm1
0x18000ed51  movdqu  [rbp+57h+var_B0], xmm1
0x18000ed56  mov     [rbp+57h+var_A0], 0Ah
0x18000ed5d  lea     rcx, [rbp+57h+var_C8]
0x18000ed61  call    ?RemoveAll@?$CAtlList@PEAU_InterfaceInfo@@V?$CElementTraits@PEAU_InterfaceInfo@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(void)
0x18000ed66  xor     ebx, ebx
0x18000ed68  lea     r14, qword_18003F5B0
0x18000ed6f  lea     rax, [rbx+rbx*2]
0x18000ed73  add     rax, rax
0x18000ed76  cmp     dword ptr [r14+rax*8+20h], 0
0x18000ed7c  jz      short loc_18000ED8B
0x18000ed7e  lea     rdx, [r14+rax*8]
0x18000ed82  lea     rcx, [rbp+57h+var_C8]
0x18000ed86  call    ?AddTail@?$CAtlList@U_tagpropertykey@@V?$CElementTraits@U_tagpropertykey@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBU_tagpropertykey@@@Z; ATL::CAtlList<_tagpropertykey,ATL::CElementTraits<_tagpropertykey>>::AddTail(_tagpropertykey const &)
0x18000ed8b  inc     rbx
0x18000ed8e  cmp     rbx, 6
0x18000ed92  jb      short loc_18000ED6F
0x18000ed94  lea     rdx, [rbp+57h+strIn]
0x18000ed98  lea     rcx, [rbp+57h+var_C8]
0x18000ed9c  call    ?PropertyKeyListToString@CPreflistFolder@@CAJAEBV?$CAtlList@U_tagpropertykey@@V?$CElementTraits@U_tagpropertykey@@@ATL@@@ATL@@AEAVCString@WTL@@@Z; CPreflistFolder::PropertyKeyListToString(ATL::CAtlList<_tagpropertykey,ATL::CElementTraits<_tagpropertykey>> const &,WTL::CString &)
0x18000eda1  mov     ebx, eax
0x18000eda3  test    eax, eax
0x18000eda5  jns     short loc_18000EDCB
0x18000eda7  lea     rcx, [rbp+57h+var_C8]
0x18000edab  call    ?RemoveAll@?$CAtlList@PEAU_InterfaceInfo@@V?$CElementTraits@PEAU_InterfaceInfo@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(void)
0x18000edb0  nop
0x18000edb1  lea     rcx, [rbp+57h+strIn]; this
0x18000edb5  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000edba  nop
0x18000edbb  lea     rcx, [rbp+57h+var_90]; this
0x18000edbf  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18000edc4  mov     eax, ebx
0x18000edc6  jmp     loc_18000EE7B
0x18000edcb  mov     [rdi], si
0x18000edce  mov     rcx, [rbp+57h+strIn]; strIn
0x18000edd2  mov     edx, [rcx-8]; ui
0x18000edd5  call    cs:__imp_SysAllocStringLen
0x18000eddb  mov     [rdi+8], rax
0x18000eddf  jmp     short loc_18000EDA7
0x18000ede1  cmp     eax, 9
0x18000ede4  jnz     loc_18000EE6C
0x18000edea  mov     rax, [rbx]
0x18000eded  sub     rax, qword ptr cs:PKEY_PropList_ExtendedTileInfo.fmtid.Data1
0x18000edf4  jnz     short loc_18000EE01
0x18000edf6  mov     rax, [rbx+8]
0x18000edfa  sub     rax, qword ptr cs:PKEY_PropList_ExtendedTileInfo.fmtid.Data4
0x18000ee01  test    rax, rax
0x18000ee04  jnz     short loc_18000EE6C
0x18000ee06  xor     ebx, ebx
0x18000ee08  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18000ee0f  mov     [rbp+57h+strIn], rax
0x18000ee13  lea     rdx, aProp; "prop:"
0x18000ee1a  lea     rcx, [rbp+57h+strIn]; this
0x18000ee1e  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18000ee23  lea     rdx, aSystemWireless_1; "^System.Wireless.Security;"
0x18000ee2a  lea     rcx, [rbp+57h+strIn]; this
0x18000ee2e  call    ??YCString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator+=(ushort const *)
0x18000ee33  lea     rdx, aSystemWireless_5; "^System.Wireless.RadioType;"
0x18000ee3a  lea     rcx, [rbp+57h+strIn]; this
0x18000ee3e  call    ??YCString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator+=(ushort const *)
0x18000ee43  lea     rdx, aSystemWireless_4; "^~System.Wireless.ConnectionMode;"
0x18000ee4a  lea     rcx, [rbp+57h+strIn]; this
0x18000ee4e  call    ??YCString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator+=(ushort const *)
0x18000ee53  mov     [rdi], si
0x18000ee56  mov     rcx, [rbp+57h+strIn]; strIn
0x18000ee5a  mov     edx, [rcx-8]; ui
0x18000ee5d  call    cs:__imp_SysAllocStringLen
0x18000ee63  mov     [rdi+8], rax
0x18000ee67  jmp     loc_18000EDB1
0x18000ee6c  mov     ebx, 80004001h
0x18000ee71  jmp     loc_18000EDBB
0x18000ee76  mov     eax, 80070057h
0x18000ee7b  mov     rcx, [rbp+57h+var_30]
0x18000ee7f  xor     rcx, rsp; StackCookie
0x18000ee82  call    __security_check_cookie
0x18000ee87  add     rsp, 0D0h
0x18000ee8e  pop     r14
0x18000ee90  pop     rdi
0x18000ee91  pop     rsi
0x18000ee92  pop     rbx
0x18000ee93  pop     rbp
0x18000ee94  retn
```
