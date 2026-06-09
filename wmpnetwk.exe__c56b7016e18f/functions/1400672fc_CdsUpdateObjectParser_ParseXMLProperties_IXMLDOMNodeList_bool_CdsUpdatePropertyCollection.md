# CdsUpdateObjectParser::ParseXMLProperties(IXMLDOMNodeList *,bool,CdsUpdatePropertyCollection *)

- ea: `0x1400672fc`
- end: `0x140067731`
- name: `?ParseXMLProperties@CdsUpdateObjectParser@@AEAAJPEAUIXMLDOMNodeList@@_NPEAVCdsUpdatePropertyCollection@@@Z`
- size: `1077`
- prototype: `__int64 __fastcall(CdsUpdateObjectParser *__hidden this, struct IXMLDOMNodeList *, bool, struct CdsUpdatePropertyCollection *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006706c`
- `0x1400672fc`

## callees

- `0x14000b3b0`
- `0x14000b5c4`
- `0x14000c780`
- `0x14000c920`
- `0x1400207a0`
- `0x140024688`
- `0x14003f17c`
- `0x14003fad8`
- `0x140066b3c`
- `0x1400672fc`
- `0x140067838`
- `0x140099660`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140067541`
- `KERNEL32!CompareStringOrdinal` at `0x140067541`
- `OLEAUT32!__imp_SysFreeString` at `0x1400674be`
- `OLEAUT32!__imp_SysFreeString` at `0x14006756c`
- `OLEAUT32!__imp_SysFreeString` at `0x140067605`
- `OLEAUT32!__imp_SysFreeString` at `0x14006761a`
- `OLEAUT32!__imp_SysFreeString` at `0x140067646`
- `OLEAUT32!__imp_SysFreeString` at `0x14006766b`
- `OLEAUT32!__imp_SysFreeString` at `0x14006768d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400674be`
- `OLEAUT32!__imp_SysFreeString` at `0x14006756c`
- `OLEAUT32!__imp_SysFreeString` at `0x140067605`
- `OLEAUT32!__imp_SysFreeString` at `0x14006761a`
- `OLEAUT32!__imp_SysFreeString` at `0x140067646`
- `OLEAUT32!__imp_SysFreeString` at `0x14006766b`
- `OLEAUT32!__imp_SysFreeString` at `0x14006768d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CdsUpdateObjectParser::ParseXMLProperties(
        CdsUpdateObjectParser *this,
        struct IXMLDOMNodeList *a2,
        __int64 a3,
        struct CdsUpdatePropertyCollection *a4)
{
  char v5; // r12
  CdsUpdateObjectParser *v7; // rdi
  int v8; // ebx
  unsigned int v9; // r15d
  unsigned int AtomForName; // eax
  unsigned int v11; // esi
  struct IXMLDOMNodeList *v12; // rdi
  HRESULT (__stdcall *get_item)(IXMLDOMNodeList *, int, IXMLDOMNode **); // rbx
  ATL::CComBSTR *v14; // rax
  unsigned int i; // edi
  __int64 v16; // rbx
  bool v17; // zf
  __int64 v19; // [rsp+30h] [rbp-39h] BYREF
  BSTR v20; // [rsp+38h] [rbp-31h] BYREF
  struct IXMLDOMNodeList *v21; // [rsp+40h] [rbp-29h] BYREF
  int v22; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  int ElementTypeForAtom; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-1h] BYREF
  BSTR v27; // [rsp+70h] [rbp+7h] BYREF
  BSTR bstrString[9]; // [rsp+78h] [rbp+Fh] BYREF

  v5 = a3;
  v7 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qlq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, (unsigned __int8)a3, a4);
  }
  v22 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))a2->lpVtbl->get_length)(a2, &v22);
  if ( v8 < 0 )
  {
LABEL_53:
    v8 = -2147220633;
    goto LABEL_54;
  }
  v9 = 0;
LABEL_7:
  if ( (int)v9 < v22 )
  {
    v19 = 0;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, __int64 *))a2->lpVtbl->get_item)(a2, v9, &v19);
    if ( v8 < 0 )
      goto LABEL_49;
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 56LL))(v19, &v20);
    if ( v8 < 0 )
      goto LABEL_48;
    AtomForName = CdsValues::GetAtomForName(v20);
    v11 = AtomForName;
    if ( !AtomForName )
    {
      v8 = -2147220633;
      goto LABEL_48;
    }
    if ( AtomForName == 78 )
    {
      if ( !v5 )
        goto LABEL_33;
      v21 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNodeList **))(*(_QWORD *)v19 + 96LL))(v19, &v21);
      if ( v8 >= 0 )
      {
        v8 = CdsUpdateObjectParser::ParseXMLProperties(v7, v21, 0, a4);
        if ( v8 >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
          goto LABEL_37;
        }
      }
      goto LABEL_38;
    }
    if ( ((AtomForName - 26) & 0xFFFFFFFD) != 0 )
      goto LABEL_33;
    v21 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNodeList **))(*(_QWORD *)v19 + 136LL))(v19, &v21);
    if ( v8 < 0 )
      goto LABEL_38;
    v23 = 0;
    v12 = v21;
    get_item = v21->lpVtbl->get_item;
    v14 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"role");
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, __int64 *))get_item)(v12, *(_QWORD *)v14, &v23);
    SysFreeString(bstrString[0]);
    if ( v8 < 0 )
      goto LABEL_41;
    lpString1 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v23 + 208LL))(v23, &lpString1);
    if ( v8 < 0 )
      goto LABEL_40;
    for ( i = 0; ; ++i )
    {
      if ( i >= 6 )
      {
LABEL_31:
        if ( ((v11 - 26) & 0xFFFFFFFD) == 0 )
        {
          v8 = -2147220633;
LABEL_40:
          SysFreeString((BSTR)lpString1);
LABEL_41:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
LABEL_38:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
          goto LABEL_48;
        }
        SysFreeString((BSTR)lpString1);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
        v7 = this;
LABEL_33:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v25);
        ElementTypeForAtom = CdsValues::GetElementTypeForAtom(v11);
        if ( ElementTypeForAtom == -1 )
        {
          v8 = -2147220633;
          goto LABEL_45;
        }
        v27 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 208LL))(v19, &v27);
        if ( v8 < 0 )
          goto LABEL_44;
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, v27);
        CdsValues::XMLUnescape(&v25);
        if ( *(int *)(v25 - 16) > 1024 )
        {
          v8 = -2147220624;
LABEL_44:
          SysFreeString(v27);
LABEL_45:
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v25);
LABEL_48:
          SysFreeString(v20);
LABEL_49:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
          goto LABEL_50;
        }
        ATL::CAtlArray<CDSUpdatePropertyInfo,ATL::CElementTraits<CDSUpdatePropertyInfo>>::Add(
          (__int64 *)a4 + 1,
          (__int64)&ElementTypeForAtom);
        SysFreeString(v27);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v25);
LABEL_37:
        SysFreeString(v20);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        ++v9;
        goto LABEL_7;
      }
      v16 = 32LL * i;
      if ( v11 == 26 )
        break;
      if ( v11 == 28 )
      {
        v17 = *(_DWORD *)((char *)&CdsValues::s_aliasTable + v16 + 4) == 11;
LABEL_26:
        if ( !v17 )
          continue;
      }
      if ( *(_DWORD *)((char *)&CdsValues::s_aliasTable + v16 + 8) == 21
        && CompareStringOrdinal(lpString1, -1, *(LPCWCH *)((char *)&CdsValues::s_aliasTable + v16 + 16), -1, 0) == 2 )
      {
        v11 = *(_DWORD *)((char *)&CdsValues::s_aliasTable + v16);
        goto LABEL_31;
      }
    }
    v17 = *(_DWORD *)((char *)&CdsValues::s_aliasTable + v16 + 4) == 10;
    goto LABEL_26;
  }
LABEL_50:
  if ( !v22 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v25);
    ElementTypeForAtom = -1;
    ATL::CAtlArray<CDSUpdatePropertyInfo,ATL::CElementTraits<CDSUpdatePropertyInfo>>::Add(
      (__int64 *)a4 + 1,
      (__int64)&ElementTypeForAtom);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v25);
  }
  if ( v8 < 0 )
    goto LABEL_53;
LABEL_54:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_5bc790e457bb3992ae758839568a0175_Traceguids,
      (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400672fc  mov     [rsp-8+arg_0], rcx
0x140067301  push    rbp
0x140067302  push    rbx
0x140067303  push    rsi
0x140067304  push    rdi
0x140067305  push    r12
0x140067307  push    r13
0x140067309  push    r14
0x14006730b  push    r15
0x14006730d  lea     rbp, [rsp-1Fh]
0x140067312  sub     rsp, 88h
0x140067319  mov     r13, r9
0x14006731c  movzx   r12d, r8b
0x140067320  mov     r14, rdx
0x140067323  mov     rdi, rcx
0x140067326  lea     rsi, WPP_GLOBAL_Control
0x14006732d  mov     rcx, cs:WPP_GLOBAL_Control
0x140067334  cmp     rcx, rsi
0x140067337  jz      short loc_14006735B
0x140067339  test    byte ptr [rcx+1Ch], 1
0x14006733d  jz      short loc_14006735B
0x14006733f  cmp     byte ptr [rcx+19h], 5
0x140067343  jb      short loc_14006735B
0x140067345  mov     [rsp+0C0h+var_98], r9
0x14006734a  mov     [rsp+0C0h+bIgnoreCase], r12d
0x14006734f  mov     r9, rdx
0x140067352  mov     rcx, [rcx+10h]
0x140067356  call    WPP_SF_qlq
0x14006735b  mov     [rbp+57h+var_78], 0
0x140067362  mov     rax, [r14]
0x140067365  lea     rdx, [rbp+57h+var_78]
0x140067369  mov     rcx, r14
0x14006736c  mov     rax, [rax+40h]
0x140067370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067375  mov     ebx, eax
0x140067377  test    eax, eax
0x140067379  js      loc_1400676D4
0x14006737f  xor     r15d, r15d
0x140067382  cmp     r15d, [rbp+57h+var_78]
0x140067386  jge     loc_14006769D
0x14006738c  mov     [rbp+57h+var_90], 0
0x140067394  mov     rax, [r14]
0x140067397  lea     r8, [rbp+57h+var_90]
0x14006739b  mov     edx, r15d
0x14006739e  mov     rcx, r14
0x1400673a1  mov     rax, [rax+38h]
0x1400673a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400673aa  mov     ebx, eax
0x1400673ac  test    eax, eax
0x1400673ae  js      loc_140067694
0x1400673b4  mov     [rbp+57h+var_88], 0
0x1400673bc  mov     rcx, [rbp+57h+var_90]
0x1400673c0  mov     rax, [rcx]
0x1400673c3  lea     rdx, [rbp+57h+var_88]
0x1400673c7  mov     rax, [rax+38h]
0x1400673cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400673d0  mov     ebx, eax
0x1400673d2  test    eax, eax
0x1400673d4  js      loc_140067689
0x1400673da  mov     rcx, [rbp+57h+var_88]
0x1400673de  call    ?GetAtomForName@CdsValues@@SA?AW4Value@CdsValue@@PEBG@Z; CdsValues::GetAtomForName(ushort const *)
0x1400673e3  mov     esi, eax
0x1400673e5  test    eax, eax
0x1400673e7  jz      loc_140067684
0x1400673ed  cmp     eax, 4Eh ; 'N'
0x1400673f0  jnz     short loc_14006744B
0x1400673f2  test    r12b, r12b
0x1400673f5  jz      loc_14006758A
0x1400673fb  mov     [rbp+57h+var_80], 0
0x140067403  mov     rcx, [rbp+57h+var_90]
0x140067407  mov     rax, [rcx]
0x14006740a  lea     rdx, [rbp+57h+var_80]
0x14006740e  mov     rax, [rax+60h]
0x140067412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067417  mov     ebx, eax
0x140067419  test    eax, eax
0x14006741b  js      loc_140067632
0x140067421  mov     r9, r13; struct CdsUpdatePropertyCollection *
0x140067424  xor     r8d, r8d; bool
0x140067427  mov     rdx, [rbp+57h+var_80]; struct IXMLDOMNodeList *
0x14006742b  mov     rcx, rdi; this
0x14006742e  call    ?ParseXMLProperties@CdsUpdateObjectParser@@AEAAJPEAUIXMLDOMNodeList@@_NPEAVCdsUpdatePropertyCollection@@@Z; CdsUpdateObjectParser::ParseXMLProperties(IXMLDOMNodeList *,bool,CdsUpdatePropertyCollection *)
0x140067433  mov     ebx, eax
0x140067435  lea     rcx, [rbp+57h+var_80]
0x140067439  test    eax, eax
0x14006743b  js      loc_140067636
0x140067441  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140067446  jmp     loc_140067616
0x14006744b  add     eax, 0FFFFFFE6h
0x14006744e  test    eax, 0FFFFFFFDh
0x140067453  jnz     loc_14006758A
0x140067459  mov     [rbp+57h+var_80], 0
0x140067461  mov     rcx, [rbp+57h+var_90]
0x140067465  mov     rax, [rcx]
0x140067468  lea     rdx, [rbp+57h+var_80]
0x14006746c  mov     rax, [rax+88h]
0x140067473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067478  mov     ebx, eax
0x14006747a  test    eax, eax
0x14006747c  js      loc_140067657
0x140067482  mov     [rbp+57h+var_70], 0
0x14006748a  mov     rdi, [rbp+57h+var_80]
0x14006748e  mov     rax, [rdi]
0x140067491  mov     rbx, [rax+38h]
0x140067495  lea     rdx, aRole; "role"
0x14006749c  lea     rcx, [rbp+57h+bstrString]; this
0x1400674a0  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400674a5  nop
0x1400674a6  lea     r8, [rbp+57h+var_70]
0x1400674aa  mov     rdx, [rax]
0x1400674ad  mov     rcx, rdi
0x1400674b0  mov     rax, rbx
0x1400674b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400674b8  mov     ebx, eax
0x1400674ba  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400674be  call    cs:__imp_SysFreeString
0x1400674c4  test    ebx, ebx
0x1400674c6  js      loc_14006764D
0x1400674cc  mov     [rbp+57h+lpString1], 0
0x1400674d4  mov     rcx, [rbp+57h+var_70]
0x1400674d8  mov     rax, [rcx]
0x1400674db  lea     rdx, [rbp+57h+lpString1]
0x1400674df  mov     rax, [rax+0D0h]
0x1400674e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400674eb  mov     ebx, eax
0x1400674ed  test    eax, eax
0x1400674ef  js      loc_140067642
0x1400674f5  xor     edi, edi
0x1400674f7  cmp     edi, 6
0x1400674fa  jnb     short loc_14006755A
0x1400674fc  mov     ebx, edi
0x1400674fe  shl     rbx, 5
0x140067502  lea     rax, ?s_aliasTable@CdsValues@@2PAUCdsAliasMappingInfo@@A; CdsAliasMappingInfo near * CdsValues::s_aliasTable
0x140067509  cmp     esi, 1Ah
0x14006750c  jnz     short loc_140067515
0x14006750e  cmp     dword ptr [rbx+rax+4], 0Ah
0x140067513  jmp     short loc_14006751F
0x140067515  cmp     esi, 1Ch
0x140067518  jnz     short loc_140067521
0x14006751a  cmp     dword ptr [rbx+rax+4], 0Bh
0x14006751f  jnz     short loc_14006754C
0x140067521  cmp     dword ptr [rbx+rax+8], 15h
0x140067526  jnz     short loc_14006754C
0x140067528  mov     [rsp+0C0h+bIgnoreCase], 0; bIgnoreCase
0x140067530  or      ecx, 0FFFFFFFFh
0x140067533  mov     r9d, ecx; cchCount2
0x140067536  mov     r8, [rbx+rax+10h]; lpString2
0x14006753b  mov     edx, ecx; cchCount1
0x14006753d  mov     rcx, [rbp+57h+lpString1]; lpString1
0x140067541  call    cs:__imp_CompareStringOrdinal
0x140067547  cmp     eax, 2
0x14006754a  jz      short loc_140067550
0x14006754c  inc     edi
0x14006754e  jmp     short loc_1400674F7
0x140067550  lea     rax, ?s_aliasTable@CdsValues@@2PAUCdsAliasMappingInfo@@A; CdsAliasMappingInfo near * CdsValues::s_aliasTable
0x140067557  mov     esi, [rbx+rax]
0x14006755a  lea     eax, [rsi-1Ah]
0x14006755d  test    eax, 0FFFFFFFDh
0x140067562  jz      loc_14006763D
0x140067568  mov     rcx, [rbp+57h+lpString1]; bstrString
0x14006756c  call    cs:__imp_SysFreeString
0x140067572  nop
0x140067573  lea     rcx, [rbp+57h+var_70]
0x140067577  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006757c  nop
0x14006757d  lea     rcx, [rbp+57h+var_80]
0x140067581  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140067586  mov     rdi, [rbp+57h+arg_0]
0x14006758a  lea     rcx, [rbp+57h+var_60]
0x14006758e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140067593  nop
0x140067594  mov     ecx, esi
0x140067596  call    ?GetElementTypeForAtom@CdsValues@@SA?AW4CDS_ELEMENT_VALUE@@W4Value@CdsValue@@@Z; CdsValues::GetElementTypeForAtom(CdsValue::Value)
0x14006759b  mov     [rbp+57h+var_68], eax
0x14006759e  cmp     eax, 0FFFFFFFFh
0x1400675a1  jz      loc_14006767D
0x1400675a7  mov     [rbp+57h+var_50], 0
0x1400675af  mov     rcx, [rbp+57h+var_90]
0x1400675b3  mov     rax, [rcx]
0x1400675b6  lea     rdx, [rbp+57h+var_50]
0x1400675ba  mov     rax, [rax+0D0h]
0x1400675c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400675c6  mov     ebx, eax
0x1400675c8  test    eax, eax
0x1400675ca  js      loc_140067667
0x1400675d0  mov     rdx, [rbp+57h+var_50]
0x1400675d4  lea     rcx, [rbp+57h+var_60]
0x1400675d8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1400675dd  lea     rcx, [rbp+57h+var_60]
0x1400675e1  call    ?XMLUnescape@CdsValues@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CdsValues::XMLUnescape(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x1400675e6  mov     rax, [rbp+57h+var_60]
0x1400675ea  cmp     dword ptr [rax-10h], 400h
0x1400675f1  jg      short loc_140067662
0x1400675f3  lea     rcx, [r13+8]
0x1400675f7  lea     rdx, [rbp+57h+var_68]
0x1400675fb  call    ?Add@?$CAtlArray@UCDSUpdatePropertyInfo@@V?$CElementTraits@UCDSUpdatePropertyInfo@@@ATL@@@ATL@@QEAA_KAEBUCDSUpdatePropertyInfo@@@Z; ATL::CAtlArray<CDSUpdatePropertyInfo,ATL::CElementTraits<CDSUpdatePropertyInfo>>::Add(CDSUpdatePropertyInfo const &)
0x140067600  nop
0x140067601  mov     rcx, [rbp+57h+var_50]; bstrString
0x140067605  call    cs:__imp_SysFreeString
0x14006760b  nop
0x14006760c  lea     rcx, [rbp+57h+var_60]
0x140067610  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140067615  nop
0x140067616  mov     rcx, [rbp+57h+var_88]; bstrString
0x14006761a  call    cs:__imp_SysFreeString
0x140067620  nop
0x140067621  lea     rcx, [rbp+57h+var_90]
0x140067625  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006762a  inc     r15d
0x14006762d  jmp     loc_140067382
0x140067632  lea     rcx, [rbp+57h+var_80]
0x140067636  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006763b  jmp     short loc_140067689
0x14006763d  mov     ebx, 80040367h
0x140067642  mov     rcx, [rbp+57h+lpString1]; bstrString
0x140067646  call    cs:__imp_SysFreeString
0x14006764c  nop
0x14006764d  lea     rcx, [rbp+57h+var_70]
0x140067651  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140067656  nop
0x140067657  lea     rcx, [rbp+57h+var_80]
0x14006765b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140067660  jmp     short loc_140067689
0x140067662  mov     ebx, 80040370h
0x140067667  mov     rcx, [rbp+57h+var_50]; bstrString
0x14006766b  call    cs:__imp_SysFreeString
0x140067671  nop
0x140067672  lea     rcx, [rbp+57h+var_60]
0x140067676  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006767b  jmp     short loc_140067689
0x14006767d  mov     ebx, 80040367h
0x140067682  jmp     short loc_140067672
0x140067684  mov     ebx, 80040367h
0x140067689  mov     rcx, [rbp+57h+var_88]; bstrString
0x14006768d  call    cs:__imp_SysFreeString
0x140067693  nop
0x140067694  lea     rcx, [rbp+57h+var_90]
0x140067698  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006769d  cmp     [rbp+57h+var_78], 0
0x1400676a1  jnz     short loc_1400676C9
0x1400676a3  lea     rcx, [rbp+57h+var_60]
0x1400676a7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400676ac  mov     [rbp+57h+var_68], 0FFFFFFFFh
0x1400676b3  lea     rcx, [r13+8]
0x1400676b7  lea     rdx, [rbp+57h+var_68]
0x1400676bb  call    ?Add@?$CAtlArray@UCDSUpdatePropertyInfo@@V?$CElementTraits@UCDSUpdatePropertyInfo@@@ATL@@@ATL@@QEAA_KAEBUCDSUpdatePropertyInfo@@@Z; ATL::CAtlArray<CDSUpdatePropertyInfo,ATL::CElementTraits<CDSUpdatePropertyInfo>>::Add(CDSUpdatePropertyInfo const &)
0x1400676c0  lea     rcx, [rbp+57h+var_60]
0x1400676c4  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400676c9  lea     rsi, WPP_GLOBAL_Control
0x1400676d0  test    ebx, ebx
0x1400676d2  jns     short loc_1400676D9
0x1400676d4  mov     ebx, 80040367h
0x1400676d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400676e0  cmp     rcx, rsi
0x1400676e3  jz      short loc_14006771B
0x1400676e5  test    byte ptr [rcx+1Ch], 1
0x1400676e9  jz      short loc_14006771B
0x1400676eb  mov     r8d, ebx
0x1400676ee  sar     r8d, 1Fh
0x1400676f2  and     r8d, 0FFFFFFFDh
0x1400676f6  add     r8d, 5
0x1400676fa  movzx   eax, byte ptr [rcx+19h]
0x1400676fe  cmp     eax, r8d
0x140067701  jb      short loc_14006771B
0x140067703  mov     edx, 1Ah
0x140067708  mov     r9d, ebx
0x14006770b  lea     r8, WPP_5bc790e457bb3992ae758839568a0175_Traceguids
0x140067712  mov     rcx, [rcx+10h]
0x140067716  call    WPP_SF_d
0x14006771b  mov     eax, ebx
0x14006771d  add     rsp, 88h
0x140067724  pop     r15
0x140067726  pop     r14
0x140067728  pop     r13
0x14006772a  pop     r12
0x14006772c  pop     rdi
0x14006772d  pop     rsi
0x14006772e  pop     rbx
0x14006772f  pop     rbp
0x140067730  retn
```
