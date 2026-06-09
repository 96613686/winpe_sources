# CdsQueryParser::ProcessRelExp(void)

- ea: `0x14006e644`
- end: `0x14006edfc`
- name: `?ProcessRelExp@CdsQueryParser@@AEAAJXZ`
- size: `1976`
- prototype: `__int64 __fastcall(CdsQueryParser *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x14006dc3c`

## callees

- `0x140003690`
- `0x140003750`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000b5c4`
- `0x14000c920`
- `0x140024688`
- `0x140028670`
- `0x140028f0c`
- `0x1400360b0`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140047798`
- `0x14006b87c`
- `0x14006c14c`
- `0x14006c1a8`
- `0x14006cc78`
- `0x14006d124`
- `0x14006da78`
- `0x14006e644`
- `0x14006ef18`
- `0x14006fa64`
- `0x140071550`
- `0x1400718bc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14006ebab`
- `KERNEL32!CompareStringW` at `0x14006ec20`
- `KERNEL32!CompareStringW` at `0x14006ebab`
- `KERNEL32!CompareStringW` at `0x14006ec20`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CdsQueryParser::ProcessRelExp(const void **this)
{
  _QWORD *v2; // r14
  PVOID *v3; // r10
  int NextToken; // ebx
  unsigned int AtomForName; // eax
  unsigned int v6; // r12d
  __int64 v7; // r9
  __int64 v8; // rdx
  unsigned int BinaryOp; // eax
  unsigned int v10; // r15d
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  CdsParseLevel *v14; // rsi
  CdsParseProduct *CurrentProduct; // rax
  PCNZWCH *v17; // rax
  int v18; // ebx
  char v19; // r14
  PVOID *v20; // rcx
  __int64 v21; // rdx
  PCNZWCH *v22; // rax
  int v23; // ebx
  __int64 v24; // r8
  CdsParseProduct *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r9
  _BYTE v28[80]; // [rsp+30h] [rbp-50h] BYREF
  struct CdsQuery *v29; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v30);
  v2 = this + 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &v32,
    this + 3);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, *v2);
  }
  ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v28);
  if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&CdsQueryParser::m_attrRegex, *v2, v28, 0) )
  {
    AtomForName = CdsValues::GetAtomForName(v32);
    v6 = AtomForName;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, AtomForName);
    }
    NextToken = CdsQueryParser::ReadNextToken((CdsQueryParser *)this);
    if ( NextToken < 0 )
      goto LABEL_62;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = *((unsigned int *)this + 4);
    if ( (_DWORD)v7 != 2 )
    {
      if ( v3 == &WPP_GLOBAL_Control || (*((_BYTE *)v3 + 28) & 8) == 0 || *((_BYTE *)v3 + 25) < 2u )
        goto LABEL_14;
      v8 = 233;
      goto LABEL_29;
    }
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v30, this + 3);
    BinaryOp = CdsQueryParser::GetBinaryOp(&v30);
    v10 = BinaryOp;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, BinaryOp);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        WPP_SF_(v11[2], 235, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      NextToken = CdsQueryParser::ReadNextToken((CdsQueryParser *)this);
      if ( NextToken < 0 )
        goto LABEL_62;
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !*((_BYTE *)this + 32) || *((_DWORD *)this + 4) != 3 )
      {
        if ( v3 == &WPP_GLOBAL_Control || (*((_BYTE *)v3 + 28) & 8) == 0 || *((_BYTE *)v3 + 25) < 2u )
          goto LABEL_14;
        WPP_SF_ld(v3[2], v12, v13, *((unsigned __int8 *)this + 32), *((_DWORD *)this + 4));
        goto LABEL_13;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v31,
        this + 3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      }
      v29 = 0;
      if ( (int)CdsBinaryOpQuery::CreateInstance(&v29) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        }
        NextToken = -2147220616;
      }
      else
      {
        NextToken = CdsBinaryOpQuery::Initialize(v29, v6, v10, &v31);
        if ( NextToken >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
          }
          v14 = (CdsParseLevel *)(this + 11);
          CurrentProduct = CdsParseLevel::get_CurrentProduct(v14);
          CdsParseProduct::AddQuery(CurrentProduct, v29);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v31);
LABEL_113:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
          }
          *(_DWORD *)v14 = 1;
          goto LABEL_62;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v31);
LABEL_62:
      v3 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_63;
    }
    if ( (unsigned __int8)CdsQueryParser::IsExistsOp(&v30) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      }
      NextToken = CdsQueryParser::ReadNextToken((CdsQueryParser *)this);
      if ( NextToken < 0 )
        goto LABEL_62;
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      v7 = *((unsigned int *)this + 4);
      if ( (_DWORD)v7 != 2 )
      {
        if ( v3 == &WPP_GLOBAL_Control || (*((_BYTE *)v3 + 28) & 8) == 0 || *((_BYTE *)v3 + 25) < 2u )
          goto LABEL_14;
        v8 = 244;
LABEL_29:
        WPP_SF_d(v3[2], v8, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, v7);
        goto LABEL_13;
      }
      v17 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                         this + 3,
                         &v29,
                         4);
      v18 = CompareStringW(0x7Fu, 1u, *v17, -1, L"true", -1);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v29);
      if ( v18 == 2 )
      {
        v19 = 1;
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v21 = 245;
LABEL_102:
            WPP_SF_(v20[2], v21, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
            v20 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_103;
          }
          goto LABEL_103;
        }
        goto LABEL_107;
      }
      v22 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                         this + 3,
                         &v29,
                         5);
      v23 = CompareStringW(0x7Fu, 1u, *v22, -1, L"false", -1);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v29);
      if ( v23 == 2 )
      {
        v19 = 0;
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v21 = 246;
            goto LABEL_102;
          }
LABEL_103:
          if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 && *((_BYTE *)v20 + 25) >= 5u )
            WPP_SF_(v20[2], 248, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        }
LABEL_107:
        v29 = 0;
        NextToken = CdsExistsQuery::CreateInstance(&v29);
        if ( NextToken < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
          }
          NextToken = -2147220628;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
          goto LABEL_62;
        }
        LOBYTE(v24) = v19;
        CdsExistsQuery::Set(v29, v6, v24);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
        }
        v14 = (CdsParseLevel *)(this + 11);
        v25 = CdsParseLevel::get_CurrentProduct(v14);
        CdsParseProduct::AddQuery(v25, v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
        goto LABEL_113;
      }
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v26 = 247;
      v27 = *v2;
    }
    else
    {
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v26 = 251;
      v27 = v30;
    }
    WPP_SF_S(v3[2], v26, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, v27);
    goto LABEL_13;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_14;
  }
  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
LABEL_13:
  v3 = (PVOID *)WPP_GLOBAL_Control;
LABEL_14:
  NextToken = -2147220628;
LABEL_63:
  if ( v3 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v3 + 28) & 1) != 0
    && *((unsigned __int8 *)v3 + 25) >= ((NextToken >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v3[2], 253, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, (unsigned int)NextToken);
  }
  ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v28);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v32);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v30);
  return (unsigned int)NextToken;
}

```

## disassembly

```asm
0x14006e644  push    rbp
0x14006e646  push    rbx
0x14006e647  push    rsi
0x14006e648  push    r12
0x14006e64a  push    r13
0x14006e64c  push    r14
0x14006e64e  push    r15
0x14006e650  mov     rbp, rsp
0x14006e653  sub     rsp, 80h
0x14006e65a  mov     rsi, rcx
0x14006e65d  lea     r13, WPP_GLOBAL_Control
0x14006e664  lea     rbx, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e672  cmp     rcx, r13
0x14006e675  jz      short loc_14006E68E
0x14006e677  test    byte ptr [rcx+1Ch], 1
0x14006e67b  jz      short loc_14006E68E
0x14006e67d  mov     edx, 0E4h
0x14006e682  mov     r8, rbx
0x14006e685  mov     rcx, [rcx+10h]
0x14006e689  call    WPP_SF_
0x14006e68e  lea     rcx, [rbp+arg_8]
0x14006e692  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14006e697  nop
0x14006e698  lea     r14, [rsi+18h]
0x14006e69c  mov     rdx, r14
0x14006e69f  lea     rcx, [rbp+arg_18]
0x14006e6a3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14006e6a8  nop
0x14006e6a9  mov     r15b, 8
0x14006e6ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e6b3  cmp     rcx, r13
0x14006e6b6  jz      short loc_14006E6D8
0x14006e6b8  test    [rcx+1Ch], r15b
0x14006e6bc  jz      short loc_14006E6D8
0x14006e6be  cmp     byte ptr [rcx+19h], 5
0x14006e6c2  jb      short loc_14006E6D8
0x14006e6c4  mov     edx, 0E5h
0x14006e6c9  mov     r9, [r14]
0x14006e6cc  mov     r8, rbx
0x14006e6cf  mov     rcx, [rcx+10h]
0x14006e6d3  call    WPP_SF_S
0x14006e6d8  lea     rcx, [rbp+var_50]
0x14006e6dc  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x14006e6e1  nop
0x14006e6e2  xor     r9d, r9d
0x14006e6e5  lea     r8, [rbp+var_50]
0x14006e6e9  mov     rdx, [r14]
0x14006e6ec  lea     rcx, ?m_attrRegex@CdsQueryParser@@0V?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@A; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW> CdsQueryParser::m_attrRegex
0x14006e6f3  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x14006e6f8  test    eax, eax
0x14006e6fa  jnz     short loc_14006E737
0x14006e6fc  mov     r10, cs:WPP_GLOBAL_Control
0x14006e703  cmp     r10, r13
0x14006e706  jz      short loc_14006E72D
0x14006e708  test    [r10+1Ch], r15b
0x14006e70c  jz      short loc_14006E72D
0x14006e70e  cmp     byte ptr [r10+19h], 2
0x14006e713  jb      short loc_14006E72D
0x14006e715  mov     edx, 0E6h
0x14006e71a  mov     r8, rbx
0x14006e71d  mov     rcx, [r10+10h]
0x14006e721  call    WPP_SF_
0x14006e726  mov     r10, cs:WPP_GLOBAL_Control
0x14006e72d  mov     ebx, 8004036Ch
0x14006e732  jmp     loc_14006E9E6
0x14006e737  mov     rcx, [rbp+arg_18]
0x14006e73b  call    ?GetAtomForName@CdsValues@@SA?AW4Value@CdsValue@@PEBG@Z; CdsValues::GetAtomForName(ushort const *)
0x14006e740  mov     r12d, eax
0x14006e743  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e74a  cmp     rcx, r13
0x14006e74d  jz      short loc_14006E76F
0x14006e74f  test    [rcx+1Ch], r15b
0x14006e753  jz      short loc_14006E76F
0x14006e755  cmp     byte ptr [rcx+19h], 5
0x14006e759  jb      short loc_14006E76F
0x14006e75b  mov     edx, 0E7h
0x14006e760  mov     r9d, eax
0x14006e763  mov     r8, rbx
0x14006e766  mov     rcx, [rcx+10h]
0x14006e76a  call    WPP_SF_d
0x14006e76f  mov     rcx, rsi; this
0x14006e772  call    ?ReadNextToken@CdsQueryParser@@AEAAJXZ; CdsQueryParser::ReadNextToken(void)
0x14006e777  mov     ebx, eax
0x14006e779  test    eax, eax
0x14006e77b  js      loc_14006E9DF
0x14006e781  mov     r10, cs:WPP_GLOBAL_Control
0x14006e788  cmp     r10, r13
0x14006e78b  jz      short loc_14006E7B6
0x14006e78d  test    [r10+1Ch], r15b
0x14006e791  jz      short loc_14006E7B6
0x14006e793  cmp     byte ptr [r10+19h], 5
0x14006e798  jb      short loc_14006E7B6
0x14006e79a  mov     edx, 0E8h
0x14006e79f  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e7a6  mov     rcx, [r10+10h]
0x14006e7aa  call    WPP_SF_
0x14006e7af  mov     r10, cs:WPP_GLOBAL_Control
0x14006e7b6  mov     r9d, [rsi+10h]
0x14006e7ba  cmp     r9d, 2
0x14006e7be  jz      short loc_14006E7F8
0x14006e7c0  cmp     r10, r13
0x14006e7c3  jz      loc_14006E72D
0x14006e7c9  test    [r10+1Ch], r15b
0x14006e7cd  jz      loc_14006E72D
0x14006e7d3  cmp     byte ptr [r10+19h], 2
0x14006e7d8  jb      loc_14006E72D
0x14006e7de  mov     edx, 0E9h
0x14006e7e3  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e7ea  mov     rcx, [r10+10h]
0x14006e7ee  call    WPP_SF_d
0x14006e7f3  jmp     loc_14006E726
0x14006e7f8  mov     rdx, r14
0x14006e7fb  lea     rcx, [rbp+arg_8]
0x14006e7ff  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14006e804  lea     rcx, [rbp+arg_8]
0x14006e808  call    ?GetBinaryOp@CdsQueryParser@@CA?AW4Op@CdsBinaryOp@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CdsQueryParser::GetBinaryOp(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14006e80d  mov     r15d, eax
0x14006e810  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e817  cmp     rcx, r13
0x14006e81a  jz      short loc_14006E847
0x14006e81c  test    byte ptr [rcx+1Ch], 8
0x14006e820  jz      short loc_14006E847
0x14006e822  cmp     byte ptr [rcx+19h], 5
0x14006e826  jb      short loc_14006E847
0x14006e828  mov     edx, 0EAh
0x14006e82d  mov     r9d, eax
0x14006e830  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e837  mov     rcx, [rcx+10h]
0x14006e83b  call    WPP_SF_d
0x14006e840  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e847  test    r15d, r15d
0x14006e84a  jz      loc_14006EABF
0x14006e850  cmp     rcx, r13
0x14006e853  jz      short loc_14006E876
0x14006e855  test    byte ptr [rcx+1Ch], 8
0x14006e859  jz      short loc_14006E876
0x14006e85b  cmp     byte ptr [rcx+19h], 5
0x14006e85f  jb      short loc_14006E876
0x14006e861  mov     edx, 0EBh
0x14006e866  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e86d  mov     rcx, [rcx+10h]
0x14006e871  call    WPP_SF_
0x14006e876  mov     rcx, rsi; this
0x14006e879  call    ?ReadNextToken@CdsQueryParser@@AEAAJXZ; CdsQueryParser::ReadNextToken(void)
0x14006e87e  mov     ebx, eax
0x14006e880  test    eax, eax
0x14006e882  js      loc_14006E9DF
0x14006e888  mov     r10, cs:WPP_GLOBAL_Control
0x14006e88f  cmp     r10, r13
0x14006e892  jz      short loc_14006E8BE
0x14006e894  test    byte ptr [r10+1Ch], 8
0x14006e899  jz      short loc_14006E8BE
0x14006e89b  cmp     byte ptr [r10+19h], 5
0x14006e8a0  jb      short loc_14006E8BE
0x14006e8a2  mov     edx, 0ECh
0x14006e8a7  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e8ae  mov     rcx, [r10+10h]
0x14006e8b2  call    WPP_SF_
0x14006e8b7  mov     r10, cs:WPP_GLOBAL_Control
0x14006e8be  movzx   eax, byte ptr [rsi+20h]
0x14006e8c2  test    al, al
0x14006e8c4  jz      loc_14006EA88
0x14006e8ca  cmp     dword ptr [rsi+10h], 3
0x14006e8ce  jnz     loc_14006EA88
0x14006e8d4  mov     rdx, r14
0x14006e8d7  lea     rcx, [rbp+arg_10]
0x14006e8db  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14006e8e0  nop
0x14006e8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e8e8  cmp     rcx, r13
0x14006e8eb  jz      short loc_14006E90E
0x14006e8ed  test    byte ptr [rcx+1Ch], 8
0x14006e8f1  jz      short loc_14006E90E
0x14006e8f3  cmp     byte ptr [rcx+19h], 5
0x14006e8f7  jb      short loc_14006E90E
0x14006e8f9  mov     edx, 0EEh
0x14006e8fe  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e905  mov     rcx, [rcx+10h]
0x14006e909  call    WPP_SF_
0x14006e90e  mov     [rbp+arg_0], 0
0x14006e916  lea     rcx, [rbp+arg_0]; struct CdsBinaryOpQuery **
0x14006e91a  call    ?CreateInstance@CdsBinaryOpQuery@@SAJPEAPEAV1@@Z; CdsBinaryOpQuery::CreateInstance(CdsBinaryOpQuery * *)
0x14006e91f  test    eax, eax
0x14006e921  js      loc_14006EA51
0x14006e927  lea     r9, [rbp+arg_10]
0x14006e92b  mov     r8d, r15d
0x14006e92e  mov     edx, r12d
0x14006e931  mov     rcx, [rbp+arg_0]
0x14006e935  call    ?Initialize@CdsBinaryOpQuery@@QEAAJW4Value@CdsValue@@W4Op@CdsBinaryOp@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CdsBinaryOpQuery::Initialize(CdsValue::Value,CdsBinaryOp::Op,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14006e93a  mov     ebx, eax
0x14006e93c  test    eax, eax
0x14006e93e  js      short loc_14006E99E
0x14006e940  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e947  cmp     rcx, r13
0x14006e94a  jz      short loc_14006E96D
0x14006e94c  test    byte ptr [rcx+1Ch], 8
0x14006e950  jz      short loc_14006E96D
0x14006e952  cmp     byte ptr [rcx+19h], 5
0x14006e956  jb      short loc_14006E96D
0x14006e958  mov     edx, 0EFh
0x14006e95d  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e964  mov     rcx, [rcx+10h]
0x14006e968  call    WPP_SF_
0x14006e96d  add     rsi, 58h ; 'X'
0x14006e971  mov     rcx, rsi; this
0x14006e974  call    ?get_CurrentProduct@CdsParseLevel@@QEAAPEAVCdsParseProduct@@XZ; CdsParseLevel::get_CurrentProduct(void)
0x14006e979  mov     rdx, [rbp+arg_0]; struct CdsQuery *
0x14006e97d  mov     rcx, rax; this
0x14006e980  call    ?AddQuery@CdsParseProduct@@QEAAJPEBVCdsQuery@@@Z; CdsParseProduct::AddQuery(CdsQuery const *)
0x14006e985  nop
0x14006e986  lea     rcx, [rbp+arg_0]
0x14006e98a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006e98f  nop
0x14006e990  lea     rcx, [rbp+arg_10]
0x14006e994  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006e999  jmp     loc_14006ED10
0x14006e99e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e9a5  cmp     rcx, r13
0x14006e9a8  jz      short loc_14006E9CC
0x14006e9aa  test    byte ptr [rcx+1Ch], 8
0x14006e9ae  jz      short loc_14006E9CC
0x14006e9b0  cmp     byte ptr [rcx+19h], 5
0x14006e9b4  jb      short loc_14006E9CC
0x14006e9b6  mov     edx, 0F0h
0x14006e9bb  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e9c2  mov     rcx, [rcx+10h]
0x14006e9c6  call    WPP_SF_
0x14006e9cb  nop
0x14006e9cc  lea     rcx, [rbp+arg_0]
0x14006e9d0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006e9d5  nop
0x14006e9d6  lea     rcx, [rbp+arg_10]
0x14006e9da  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006e9df  mov     r10, cs:WPP_GLOBAL_Control
0x14006e9e6  cmp     r10, r13
0x14006e9e9  jz      short loc_14006EA1F
0x14006e9eb  test    byte ptr [r10+1Ch], 1
0x14006e9f0  jz      short loc_14006EA1F
0x14006e9f2  mov     ecx, ebx
0x14006e9f4  sar     ecx, 1Fh
0x14006e9f7  and     ecx, 0FFFFFFFDh
0x14006e9fa  add     ecx, 5
0x14006e9fd  movzx   eax, byte ptr [r10+19h]
0x14006ea02  cmp     eax, ecx
0x14006ea04  jb      short loc_14006EA1F
0x14006ea06  mov     edx, 0FDh
0x14006ea0b  mov     r9d, ebx
0x14006ea0e  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006ea15  mov     rcx, [r10+10h]
0x14006ea19  call    WPP_SF_d
0x14006ea1e  nop
0x14006ea1f  lea     rcx, [rbp+var_50]
0x14006ea23  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x14006ea28  nop
0x14006ea29  lea     rcx, [rbp+arg_18]
0x14006ea2d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006ea32  nop
0x14006ea33  lea     rcx, [rbp+arg_8]
0x14006ea37  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006ea3c  mov     eax, ebx
0x14006ea3e  add     rsp, 80h
0x14006ea45  pop     r15
0x14006ea47  pop     r14
0x14006ea49  pop     r13
0x14006ea4b  pop     r12
0x14006ea4d  pop     rsi
0x14006ea4e  pop     rbx
0x14006ea4f  pop     rbp
0x14006ea50  retn
0x14006ea51  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ea58  cmp     rcx, r13
0x14006ea5b  jz      short loc_14006EA7E
0x14006ea5d  test    byte ptr [rcx+1Ch], 8
0x14006ea61  jz      short loc_14006EA7E
0x14006ea63  cmp     byte ptr [rcx+19h], 2
0x14006ea67  jb      short loc_14006EA7E
0x14006ea69  mov     edx, 0F1h
0x14006ea6e  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006ea75  mov     rcx, [rcx+10h]
0x14006ea79  call    WPP_SF_
0x14006ea7e  mov     ebx, 80040378h
0x14006ea83  jmp     loc_14006E9CC
0x14006ea88  cmp     r10, r13
0x14006ea8b  jz      loc_14006E72D
0x14006ea91  test    byte ptr [r10+1Ch], 8
0x14006ea96  jz      loc_14006E72D
0x14006ea9c  cmp     byte ptr [r10+19h], 2
0x14006eaa1  jb      loc_14006E72D
0x14006eaa7  mov     r9d, eax
0x14006eaaa  mov     eax, [rsi+10h]
0x14006eaad  mov     dword ptr [rsp+80h+lpString2], eax
0x14006eab1  mov     rcx, [r10+10h]
0x14006eab5  call    WPP_SF_ld
0x14006eaba  jmp     loc_14006E726
0x14006eabf  lea     rcx, [rbp+arg_8]
0x14006eac3  call    ?IsExistsOp@CdsQueryParser@@CA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CdsQueryParser::IsExistsOp(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14006eac8  test    al, al
0x14006eaca  jz      loc_14006EDCA
0x14006ead0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
