# CdsBinaryOpQuery::ValidateQuotedValueAndOperation(CdsValue::Value,CdsBinaryOp::Op,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140070980`
- end: `0x140071548`
- name: `?ValidateQuotedValueAndOperation@CdsBinaryOpQuery@@CAJW4Value@CdsValue@@W4Op@CdsBinaryOp@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@AEAV67@@Z`
- size: `3016`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14006d124`

## callees

- `0x140007020`
- `0x14000b3b0`
- `0x14000c780`
- `0x14000c920`
- `0x140014f90`
- `0x140022bc4`
- `0x140028670`
- `0x140028f0c`
- `0x1400360b0`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140047798`
- `0x14004a834`
- `0x140062014`
- `0x1400621bc`
- `0x14006cf50`
- `0x14006fe94`
- `0x14006ff5c`
- `0x140070980`
- `0x14007166c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140070b93`
- `KERNEL32!CompareStringW` at `0x140070bc5`
- `KERNEL32!CompareStringW` at `0x140070be9`
- `KERNEL32!CompareStringW` at `0x140070c14`
- `KERNEL32!CompareStringW` at `0x140070c46`
- `KERNEL32!CompareStringW` at `0x140070c66`
- `KERNEL32!CompareStringW` at `0x140070b93`
- `KERNEL32!CompareStringW` at `0x140070bc5`
- `KERNEL32!CompareStringW` at `0x140070be9`
- `KERNEL32!CompareStringW` at `0x140070c14`
- `KERNEL32!CompareStringW` at `0x140070c46`
- `KERNEL32!CompareStringW` at `0x140070c66`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CdsBinaryOpQuery::ValidateQuotedValueAndOperation(
        unsigned int a1,
        unsigned int a2,
        __int64 *a3,
        __int64 a4)
{
  int v8; // ebx
  PVOID *v9; // r10
  __int64 InfoForAtom; // rax
  PVOID *v12; // r8
  __int64 v13; // r14
  int v14; // eax
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // esi
  unsigned int v19; // edi
  PVOID *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  __int64 v28; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+50h] [rbp-39h] BYREF
  int v30; // [rsp+58h] [rbp-31h] BYREF
  int v31; // [rsp+5Ch] [rbp-2Dh] BYREF
  _DWORD v32[32]; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v33; // [rsp+F0h] [rbp+67h] BYREF
  __int64 *v34; // [rsp+100h] [rbp+77h]

  v34 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ddS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      (unsigned int)&WPP_0792b396bb7638c3e84271d90cfade20_Traceguids,
      a1,
      a2,
      *a3);
  }
  v8 = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
  if ( !a1 )
    goto LABEL_44;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 == 9 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    {
      WPP_SF_(v9[2], 118, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a1 != 17 && a1 - 39 > 1 )
    {
      if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 8) == 0 || *((_BYTE *)v9 + 25) < 2u )
        goto LABEL_22;
      WPP_SF_(v9[2], 119, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
LABEL_21:
      v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_22:
      v8 = -2147220628;
      goto LABEL_23;
    }
  }
  InfoForAtom = CdsValues::GetInfoForAtom(a1);
  v13 = InfoForAtom;
  if ( !InfoForAtom )
  {
    v8 = -2147467259;
    goto LABEL_23;
  }
  v14 = *(_DWORD *)(InfoForAtom + 16);
  if ( v14 != 1 )
  {
    if ( (unsigned int)(v14 - 3) > 1 )
    {
      switch ( a1 )
      {
        case 0x20u:
          if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
          {
            WPP_SF_(v9[2], 130, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            v9 = (PVOID *)WPP_GLOBAL_Control;
            v12 = &WPP_GLOBAL_Control;
          }
          if ( a2 - 7 > 1 )
          {
            if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
              WPP_SF_(v9[2], 132, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v32);
            if ( !(unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(
                                  &CdsBinaryOpQuery::m_dateRegex,
                                  *a3,
                                  v32,
                                  0) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
              }
              v8 = -2147220628;
              goto LABEL_71;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                134,
                &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids,
                v32[0]);
            }
            v28 = 0;
            v29 = 0;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v27);
            ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(v32, 1, &v28, &v29);
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v27, v28, (v29 - v28) >> 1);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, v27);
            }
            v33 = 0;
            if ( (int)ConvertStringToUINT32(&v27, &v33) >= 0 )
            {
              v18 = v33;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  137,
                  &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids,
                  v33);
              }
              ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(v32, 2, &v28, &v29);
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v27, v28, (v29 - v28) >> 1);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  138,
                  &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids,
                  v27);
              }
              v33 = 0;
              v8 = ConvertStringToUINT32(&v27, &v33);
              if ( v8 >= 0 )
              {
                v19 = v33;
                v20 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    140,
                    &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids,
                    v33);
                  v20 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v18 - 1 > 0xB || v19 - 1 > 0x1E )
                {
                  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 && *((_BYTE *)v20 + 25) >= 2u )
                    WPP_SF_Dd(v20[2], 141, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, v18);
                  goto LABEL_86;
                }
                if ( v18 == 2 )
                {
                  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 && *((_BYTE *)v20 + 25) >= 5u )
                  {
                    WPP_SF_(v20[2], 142, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
                    v20 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v19 <= 0x1D )
                    goto LABEL_87;
                  if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 8) == 0 || *((_BYTE *)v20 + 25) < 2u )
                  {
LABEL_86:
                    v8 = -2147220628;
LABEL_87:
                    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v27);
LABEL_71:
                    ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v32);
                    goto LABEL_44;
                  }
                  v21 = 143;
                }
                else
                {
                  if ( v18 > 0xB )
                    goto LABEL_87;
                  v22 = 2608;
                  if ( !_bittest(&v22, v18) )
                    goto LABEL_87;
                  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 && *((_BYTE *)v20 + 25) >= 5u )
                  {
                    WPP_SF_(v20[2], 144, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
                    v20 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v19 <= 0x1E )
                    goto LABEL_87;
                  if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 8) == 0 || *((_BYTE *)v20 + 25) < 2u )
                    goto LABEL_86;
                  v21 = 145;
                }
                WPP_SF_d(v20[2], v21, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, v19);
                goto LABEL_86;
              }
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_86;
              }
              v17 = 139;
            }
            else
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_86;
              }
              v17 = 136;
            }
            WPP_SF_(v16[2], v17, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            goto LABEL_86;
          }
          if ( v9 == v12 )
            goto LABEL_27;
          if ( (*((_BYTE *)v9 + 28) & 8) == 0 || *((_BYTE *)v9 + 25) < 5u )
            goto LABEL_23;
          v23 = 131;
          break;
        case 9u:
          if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
          {
            WPP_SF_(v9[2], 146, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            v9 = (PVOID *)WPP_GLOBAL_Control;
            v12 = &WPP_GLOBAL_Control;
          }
          if ( a2 - 7 > 1 )
          {
            if ( a2 - 1 > 1 )
            {
              if ( v9 == v12 || (*((_BYTE *)v9 + 28) & 8) == 0 || *((_BYTE *)v9 + 25) < 2u )
                goto LABEL_22;
              WPP_SF_d(v9[2], 148, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, a2);
              goto LABEL_21;
            }
            if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
              WPP_SF_(v9[2], 149, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v32);
            v24 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Trim(a3);
            if ( !(unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(
                                  &CdsBinaryOpQuery::m_resolutionRegex,
                                  *v24,
                                  v32,
                                  0) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
              }
              v8 = -2147220628;
              goto LABEL_71;
            }
            ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v32);
LABEL_138:
            v9 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_23;
          }
          if ( v9 == v12 )
            goto LABEL_27;
          if ( (*((_BYTE *)v9 + 28) & 8) == 0 || *((_BYTE *)v9 + 25) < 5u )
            goto LABEL_23;
          v23 = 147;
          break;
        case 7u:
          if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
          {
            WPP_SF_(v9[2], 151, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            v9 = (PVOID *)WPP_GLOBAL_Control;
            v12 = &WPP_GLOBAL_Control;
          }
          if ( a2 - 7 > 1 )
          {
            if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
              WPP_SF_(v9[2], 153, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            LODWORD(v27) = 0;
            LODWORD(v29) = 0;
            LODWORD(v28) = 0;
            v31 = 0;
            v30 = 0;
            v33 = 0;
            v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Trim(a3);
            v8 = CdsBinaryOpQuery::ValidateDurationValue(
                   v25,
                   (unsigned int)&v27,
                   (unsigned int)&v29,
                   (unsigned int)&v28,
                   (__int64)&v31,
                   (__int64)&v30,
                   (__int64)&v33);
            goto LABEL_138;
          }
          if ( v9 == v12 )
            goto LABEL_27;
          if ( (*((_BYTE *)v9 + 28) & 8) == 0 || *((_BYTE *)v9 + 25) < 5u )
            goto LABEL_23;
          v23 = 152;
          break;
        default:
          goto LABEL_23;
      }
      WPP_SF_(v9[2], v23, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      goto LABEL_138;
    }
    if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    {
      WPP_SF_(v9[2], 125, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
      v12 = &WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(v13 + 16) == 3 )
    {
      if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
        WPP_SF_(v9[2], 126, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v33 = 0;
      v8 = ConvertStringToUINT32(a3, &v33);
      if ( v8 >= 0 )
        goto LABEL_44;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 127;
LABEL_194:
        WPP_SF_(v9[2], v26, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
        WPP_SF_(v9[2], 128, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v27 = 0;
      v8 = ConvertStringToUINT64(a3, &v27);
      if ( v8 >= 0 )
        goto LABEL_44;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 129;
        goto LABEL_194;
      }
    }
    v8 = -2147220628;
    goto LABEL_23;
  }
  if ( v9 != v12 && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_(v9[2], 121, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
  if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)*a3, -1, L"true", -1) == 2
    || CompareStringW(0x7Fu, 1u, (PCNZWCH)*a3, -1, L"yes", -1) == 2
    || CompareStringW(0x7Fu, 1u, (PCNZWCH)*a3, -1, L"1", -1) == 2 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(a4, L"1");
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_23;
    v15 = 122;
    goto LABEL_53;
  }
  if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)*a3, -1, L"false", -1) == 2
    || CompareStringW(0x7Fu, 1u, (PCNZWCH)*a3, -1, L"no", -1) == 2
    || CompareStringW(0x7Fu, 1u, (PCNZWCH)*a3, -1, L"0", -1) == 2 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(a4, L"0");
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_23;
    v15 = 123;
LABEL_53:
    WPP_SF_(v9[2], v15, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
    goto LABEL_44;
  }
  v8 = -2147220628;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, *a3);
LABEL_44:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v9 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v9 + 28) & 1) != 0
    && *((unsigned __int8 *)v9 + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v9[2], 154, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, (unsigned int)v8);
  }
LABEL_27:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(a3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140070980  mov     [rsp-8+arg_8], rbx
0x140070985  mov     [rsp-8+arg_10], r8
0x14007098a  push    rbp
0x14007098b  push    rsi
0x14007098c  push    rdi
0x14007098d  push    r12
0x14007098f  push    r13
0x140070991  push    r14
0x140070993  push    r15
0x140070995  lea     rbp, [rsp-27h]
0x14007099a  sub     rsp, 0B0h
0x1400709a1  mov     r15, r9
0x1400709a4  mov     r12, r8
0x1400709a7  mov     esi, edx
0x1400709a9  mov     edi, ecx
0x1400709ab  lea     r14, WPP_GLOBAL_Control
0x1400709b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400709b9  cmp     rcx, r14
0x1400709bc  jz      short loc_1400709EE
0x1400709be  test    byte ptr [rcx+1Ch], 1
0x1400709c2  jz      short loc_1400709EE
0x1400709c4  cmp     byte ptr [rcx+19h], 5
0x1400709c8  jb      short loc_1400709EE
0x1400709ca  mov     edx, 74h ; 't'
0x1400709cf  mov     rax, [r8]
0x1400709d2  mov     qword ptr [rsp+0E0h+cchCount2], rax
0x1400709d7  mov     dword ptr [rsp+0E0h+lpString2], esi
0x1400709db  mov     r9d, edi
0x1400709de  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x1400709e5  mov     rcx, [rcx+10h]
0x1400709e9  call    WPP_SF_ddS
0x1400709ee  xor     ebx, ebx
0x1400709f0  mov     rcx, r15
0x1400709f3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400709f8  test    edi, edi
0x1400709fa  jz      loc_140070CB9
0x140070a00  mov     r13b, 8
0x140070a03  mov     r10, cs:WPP_GLOBAL_Control
0x140070a0a  lea     r8, WPP_GLOBAL_Control
0x140070a11  cmp     r10, r8
0x140070a14  jz      short loc_140070A44
0x140070a16  test    [r10+1Ch], r13b
0x140070a1a  jz      short loc_140070A44
0x140070a1c  cmp     byte ptr [r10+19h], 5
0x140070a21  jb      short loc_140070A44
0x140070a23  lea     edx, [rbx+75h]
0x140070a26  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070a2d  mov     rcx, [r10+10h]
0x140070a31  call    WPP_SF_
0x140070a36  mov     r10, cs:WPP_GLOBAL_Control
0x140070a3d  lea     r8, WPP_GLOBAL_Control
0x140070a44  cmp     esi, 9
0x140070a47  jnz     loc_140070B2D
0x140070a4d  cmp     r10, r8
0x140070a50  jz      short loc_140070A80
0x140070a52  test    [r10+1Ch], r13b
0x140070a56  jz      short loc_140070A80
0x140070a58  cmp     byte ptr [r10+19h], 5
0x140070a5d  jb      short loc_140070A80
0x140070a5f  lea     edx, [rsi+6Dh]
0x140070a62  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070a69  mov     rcx, [r10+10h]
0x140070a6d  call    WPP_SF_
0x140070a72  mov     r10, cs:WPP_GLOBAL_Control
0x140070a79  lea     r8, WPP_GLOBAL_Control
0x140070a80  cmp     edi, 11h
0x140070a83  jz      loc_140070B2D
0x140070a89  lea     eax, [rdi-27h]
0x140070a8c  cmp     eax, 1
0x140070a8f  jbe     loc_140070B2D
0x140070a95  cmp     r10, r8
0x140070a98  jz      short loc_140070AC3
0x140070a9a  test    [r10+1Ch], r13b
0x140070a9e  jz      short loc_140070AC3
0x140070aa0  cmp     byte ptr [r10+19h], 2
0x140070aa5  jb      short loc_140070AC3
0x140070aa7  mov     edx, 77h ; 'w'
0x140070aac  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070ab3  mov     rcx, [r10+10h]
0x140070ab7  call    WPP_SF_
0x140070abc  mov     r10, cs:WPP_GLOBAL_Control
0x140070ac3  mov     ebx, 8004036Ch
0x140070ac8  lea     r14, WPP_GLOBAL_Control
0x140070acf  cmp     r10, r14
0x140070ad2  jz      short loc_140070B08
0x140070ad4  test    byte ptr [r10+1Ch], 1
0x140070ad9  jz      short loc_140070B08
0x140070adb  mov     ecx, ebx
0x140070add  sar     ecx, 1Fh
0x140070ae0  and     ecx, 0FFFFFFFDh
0x140070ae3  add     ecx, 5
0x140070ae6  movzx   eax, byte ptr [r10+19h]
0x140070aeb  cmp     eax, ecx
0x140070aed  jb      short loc_140070B08
0x140070aef  mov     edx, 9Ah
0x140070af4  mov     r9d, ebx
0x140070af7  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070afe  mov     rcx, [r10+10h]
0x140070b02  call    WPP_SF_d
0x140070b07  nop
0x140070b08  mov     rcx, r12
0x140070b0b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140070b10  mov     eax, ebx
0x140070b12  mov     rbx, [rsp+0E0h+arg_8]
0x140070b1a  add     rsp, 0B0h
0x140070b21  pop     r15
0x140070b23  pop     r14
0x140070b25  pop     r13
0x140070b27  pop     r12
0x140070b29  pop     rdi
0x140070b2a  pop     rsi
0x140070b2b  pop     rbp
0x140070b2c  retn
0x140070b2d  mov     ecx, edi
0x140070b2f  call    ?GetInfoForAtom@CdsValues@@SAPEBUCdsValueInfo@@W4Value@CdsValue@@@Z; CdsValues::GetInfoForAtom(CdsValue::Value)
0x140070b34  mov     r14, rax
0x140070b37  test    rax, rax
0x140070b3a  jz      loc_140071531
0x140070b40  mov     eax, [rax+10h]
0x140070b43  cmp     eax, 1
0x140070b46  jnz     loc_140070D54
0x140070b4c  cmp     r10, r8
0x140070b4f  jz      short loc_140070B71
0x140070b51  test    [r10+1Ch], r13b
0x140070b55  jz      short loc_140070B71
0x140070b57  cmp     byte ptr [r10+19h], 5
0x140070b5c  jb      short loc_140070B71
0x140070b5e  lea     edx, [rax+78h]
0x140070b61  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070b68  mov     rcx, [r10+10h]
0x140070b6c  call    WPP_SF_
0x140070b71  or      esi, 0FFFFFFFFh
0x140070b74  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x140070b78  lea     rax, aTrue; "true"
0x140070b7f  mov     [rsp+0E0h+lpString2], rax; lpString2
0x140070b84  mov     r9d, esi; cchCount1
0x140070b87  mov     r8, [r12]; lpString1
0x140070b8b  lea     edx, [rsi+2]; dwCmpFlags
0x140070b8e  lea     edi, [rdx+7Eh]
0x140070b91  mov     ecx, edi; Locale
0x140070b93  call    cs:__imp_CompareStringW
0x140070b99  lea     r14, a1_0; "1"
0x140070ba0  cmp     eax, 2
0x140070ba3  jz      loc_140070D03
0x140070ba9  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x140070bad  lea     rax, aYes; "yes"
0x140070bb4  mov     [rsp+0E0h+lpString2], rax; lpString2
0x140070bb9  mov     r9d, esi; cchCount1
0x140070bbc  mov     r8, [r12]; lpString1
0x140070bc0  lea     edx, [rsi+2]; dwCmpFlags
0x140070bc3  mov     ecx, edi; Locale
0x140070bc5  call    cs:__imp_CompareStringW
0x140070bcb  cmp     eax, 2
0x140070bce  jz      loc_140070D03
0x140070bd4  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x140070bd8  mov     [rsp+0E0h+lpString2], r14; lpString2
0x140070bdd  mov     r9d, esi; cchCount1
0x140070be0  mov     r8, [r12]; lpString1
0x140070be4  lea     edx, [rsi+2]; dwCmpFlags
0x140070be7  mov     ecx, edi; Locale
0x140070be9  call    cs:__imp_CompareStringW
0x140070bef  cmp     eax, 2
0x140070bf2  jz      loc_140070D03
0x140070bf8  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x140070bfc  lea     rax, aFalse; "false"
0x140070c03  mov     [rsp+0E0h+lpString2], rax; lpString2
0x140070c08  mov     r9d, esi; cchCount1
0x140070c0b  mov     r8, [r12]; lpString1
0x140070c0f  lea     edx, [rsi+2]; dwCmpFlags
0x140070c12  mov     ecx, edi; Locale
0x140070c14  call    cs:__imp_CompareStringW
0x140070c1a  lea     r14, a0; "0"
0x140070c21  cmp     eax, 2
0x140070c24  jz      loc_140070CC5
0x140070c2a  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x140070c2e  lea     rax, aNo; "no"
0x140070c35  mov     [rsp+0E0h+lpString2], rax; lpString2
0x140070c3a  mov     r9d, esi; cchCount1
0x140070c3d  mov     r8, [r12]; lpString1
0x140070c41  lea     edx, [rsi+2]; dwCmpFlags
0x140070c44  mov     ecx, edi; Locale
0x140070c46  call    cs:__imp_CompareStringW
0x140070c4c  cmp     eax, 2
0x140070c4f  jz      short loc_140070CC5
0x140070c51  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x140070c55  mov     [rsp+0E0h+lpString2], r14; lpString2
0x140070c5a  mov     r9d, esi; cchCount1
0x140070c5d  mov     r8, [r12]; lpString1
0x140070c61  lea     edx, [rsi+2]; dwCmpFlags
0x140070c64  mov     ecx, edi; Locale
0x140070c66  call    cs:__imp_CompareStringW
0x140070c6c  cmp     eax, 2
0x140070c6f  jz      short loc_140070CC5
0x140070c71  mov     ebx, 8004036Ch
0x140070c76  mov     r10, cs:WPP_GLOBAL_Control
0x140070c7d  lea     r14, WPP_GLOBAL_Control
0x140070c84  cmp     r10, r14
0x140070c87  jz      loc_140070B08
0x140070c8d  test    [r10+1Ch], r13b
0x140070c91  jz      loc_140070ACF
0x140070c97  cmp     byte ptr [r10+19h], 2
0x140070c9c  jb      loc_140070ACF
0x140070ca2  lea     edx, [rsi+7Dh]
0x140070ca5  mov     r9, [r12]
0x140070ca9  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070cb0  mov     rcx, [r10+10h]
0x140070cb4  call    WPP_SF_S
0x140070cb9  mov     r10, cs:WPP_GLOBAL_Control
0x140070cc0  jmp     loc_140070ACF
0x140070cc5  mov     rdx, r14
0x140070cc8  mov     rcx, r15
0x140070ccb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140070cd0  mov     r10, cs:WPP_GLOBAL_Control
0x140070cd7  lea     r14, WPP_GLOBAL_Control
0x140070cde  cmp     r10, r14
0x140070ce1  jz      loc_140070B08
0x140070ce7  test    [r10+1Ch], r13b
0x140070ceb  jz      loc_140070ACF
0x140070cf1  cmp     byte ptr [r10+19h], 5
0x140070cf6  jb      loc_140070ACF
0x140070cfc  mov     edx, 7Bh ; '{'
0x140070d01  jmp     short loc_140070D3F
0x140070d03  mov     rdx, r14
0x140070d06  mov     rcx, r15
0x140070d09  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140070d0e  mov     r10, cs:WPP_GLOBAL_Control
0x140070d15  lea     r14, WPP_GLOBAL_Control
0x140070d1c  cmp     r10, r14
0x140070d1f  jz      loc_140070B08
0x140070d25  test    [r10+1Ch], r13b
0x140070d29  jz      loc_140070ACF
0x140070d2f  cmp     byte ptr [r10+19h], 5
0x140070d34  jb      loc_140070ACF
0x140070d3a  mov     edx, 7Ah ; 'z'
0x140070d3f  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070d46  mov     rcx, [r10+10h]
0x140070d4a  call    WPP_SF_
0x140070d4f  jmp     loc_140070CB9
0x140070d54  add     eax, 0FFFFFFFDh
0x140070d57  mov     r15d, 1
0x140070d5d  cmp     eax, r15d
0x140070d60  jbe     loc_140071404
0x140070d66  cmp     edi, 20h ; ' '
0x140070d69  jnz     loc_1400711C9
0x140070d6f  cmp     r10, r8
0x140070d72  jz      short loc_140070DA2
0x140070d74  test    [r10+1Ch], r13b
0x140070d78  jz      short loc_140070DA2
0x140070d7a  cmp     byte ptr [r10+19h], 5
0x140070d7f  jb      short loc_140070DA2
0x140070d81  lea     edx, [rdi+62h]
0x140070d84  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070d8b  mov     rcx, [r10+10h]
0x140070d8f  call    WPP_SF_
0x140070d94  mov     r10, cs:WPP_GLOBAL_Control
0x140070d9b  lea     r8, WPP_GLOBAL_Control
0x140070da2  lea     eax, [rsi-7]
0x140070da5  cmp     eax, r15d
0x140070da8  jbe     loc_14007118A
0x140070dae  cmp     r10, r8
0x140070db1  jz      short loc_140070DD5
0x140070db3  test    [r10+1Ch], r13b
0x140070db7  jz      short loc_140070DD5
0x140070db9  cmp     byte ptr [r10+19h], 5
0x140070dbe  jb      short loc_140070DD5
0x140070dc0  mov     edx, 84h
0x140070dc5  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070dcc  mov     rcx, [r10+10h]
0x140070dd0  call    WPP_SF_
0x140070dd5  lea     rcx, [rbp+57h+var_80]
0x140070dd9  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x140070dde  nop
0x140070ddf  xor     r9d, r9d
0x140070de2  lea     r8, [rbp+57h+var_80]
0x140070de6  mov     rdx, [r12]
0x140070dea  lea     rcx, ?m_dateRegex@CdsBinaryOpQuery@@0V?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@A; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW> CdsBinaryOpQuery::m_dateRegex
0x140070df1  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x140070df6  xor     edi, edi
0x140070df8  test    eax, eax
0x140070dfa  jnz     short loc_140070E43
0x140070dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140070e03  lea     r14, WPP_GLOBAL_Control
0x140070e0a  cmp     rcx, r14
0x140070e0d  jz      short loc_140070E30
0x140070e0f  test    [rcx+1Ch], r13b
0x140070e13  jz      short loc_140070E30
0x140070e15  cmp     byte ptr [rcx+19h], 2
0x140070e19  jb      short loc_140070E30
0x140070e1b  mov     edx, 85h
0x140070e20  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x140070e27  mov     rcx, [rcx+10h]
0x140070e2b  call    WPP_SF_
0x140070e30  mov     ebx, 8004036Ch
0x140070e35  lea     rcx, [rbp+57h+var_80]
0x140070e39  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x140070e3e  jmp     loc_140070CB9
0x140070e43  mov     rcx, cs:WPP_GLOBAL_Control
0x140070e4a  lea     r14, WPP_GLOBAL_Control
0x140070e51  cmp     rcx, r14
0x140070e54  jz      short loc_140070E7B
  ... truncated ...
```
