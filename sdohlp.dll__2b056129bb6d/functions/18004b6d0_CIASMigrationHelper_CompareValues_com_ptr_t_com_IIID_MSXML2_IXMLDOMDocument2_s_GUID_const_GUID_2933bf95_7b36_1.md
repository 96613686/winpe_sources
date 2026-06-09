# CIASMigrationHelper::CompareValues(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,long (*)(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &),ulong)

- ea: `0x18004b6d0`
- end: `0x18004bdb3`
- name: `?CompareValues@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1P6AJ11W4CompareOperator@@AEAHAEAV_bstr_t@@@ZK@Z`
- size: `1763`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002cd74`
- `0x18002d08c`
- `0x18002efa0`
- `0x1800403bc`
- `0x180042a80`
- `0x180047604`
- `0x18004b6d0`
- `0x18004cfcc`
- `0x18004d11c`
- `0x180050044`
- `0x180051e7c`
- `0x1800524fc`
- `0x180052588`
- `0x180052d80`
- `0x180058010`

## string_xrefs

- `0x18004b90e`: `Comparing values for %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CIASMigrationHelper::CompareValues(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall *a5)(__int64 *, __int64 *, _QWORD, int *, __int64 **),
        int a6)
{
  __int64 result; // rax
  struct IUnknown *v9; // rbx
  __int64 v10; // rbx
  int StringValueFromNode; // edi
  struct IUnknown *v12; // rdi
  __int64 v13; // rsi
  struct IUnknown *v14; // rax
  __int64 *v15; // rdi
  __int64 v16; // r15
  struct IUnknown *v17; // rax
  struct IUnknown *v18; // r14
  __int64 v19; // r14
  struct IUnknown *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // r12d
  struct IUnknown *v24; // rax
  __int64 *Node; // rax
  __int64 v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rax
  struct IUnknown *v29; // rax
  __int64 *v30; // rax
  __int64 v31; // r12
  __int64 v32; // [rsp+38h] [rbp-49h] BYREF
  __int64 *v33; // [rsp+40h] [rbp-41h] BYREF
  __int64 v34; // [rsp+48h] [rbp-39h] BYREF
  __int64 v35; // [rsp+50h] [rbp-31h] BYREF
  __int64 v36; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-21h] BYREF
  int v38; // [rsp+64h] [rbp-1Dh] BYREF
  __int64 v39; // [rsp+68h] [rbp-19h] BYREF
  __int64 v40; // [rsp+70h] [rbp-11h]
  __int64 v41; // [rsp+78h] [rbp-9h] BYREF
  __int64 v42; // [rsp+80h] [rbp-1h] BYREF
  _BYTE v43[8]; // [rsp+88h] [rbp+7h] BYREF
  __int64 v44; // [rsp+90h] [rbp+Fh]
  int v46; // [rsp+E8h] [rbp+67h]

  v46 = a3;
  if ( !a5 )
    return 2147549183LL;
  v37 = 0;
  result = CIASMigrationHelper::GetOperatorFromNode(a4, &v37);
  if ( (int)result >= 0 )
  {
    v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a4);
    _bstr_t::_bstr_t((_bstr_t *)&v39, L"./Name");
    MSXML2::IXMLDOMNode::selectSingleNode(v9);
    v10 = v42;
    if ( v42 )
    {
      v32 = 0;
      StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v42, &v32);
      if ( StringValueFromNode < 0 )
      {
        _bstr_t::_Free((_bstr_t *)&v32);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        return (unsigned int)StringValueFromNode;
      }
      v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
      _bstr_t::_bstr_t((_bstr_t *)&v33, L"./Properties");
      MSXML2::IXMLDOMNode::selectSingleNode(v12);
      v13 = v39;
      if ( !v39 )
      {
        _bstr_t::_Free((_bstr_t *)&v32);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        return 2147549183LL;
      }
      v14 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v39);
      v15 = (__int64 *)v32;
      v36 = v32;
      if ( v32 )
        _InterlockedIncrement((volatile signed __int32 *)(v32 + 16));
      MSXML2::IXMLDOMNode::selectNodes(v14);
      v16 = v41;
      if ( !v41 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        _bstr_t::_Free((_bstr_t *)&v32);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        return 0;
      }
      v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v41);
      MSXML2::IXMLDOMNodeList::nextNode(v17);
      while ( 2 )
      {
        if ( !v35 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          _bstr_t::_Free((_bstr_t *)&v32);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          return 0;
        }
        v18 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a4);
        _bstr_t::_bstr_t((_bstr_t *)v43, L"./Value");
        MSXML2::IXMLDOMNode::selectNodes(v18);
        v19 = v36;
        if ( v36 )
        {
          v20 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v36);
          MSXML2::IXMLDOMNodeList::nextNode(v20);
          v21 = v34;
          if ( v34 )
          {
            while ( 1 )
            {
              if ( !v21 )
                goto LABEL_46;
              v33 = 0;
              v38 = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WppDbgPrint("Comparing values for %S");
                if ( v15 )
                  v22 = *v15;
                else
                  v22 = 0;
                WPP_SF_sS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
                  (unsigned int)"NPSDS",
                  v22);
              }
              v23 = a5(&v34, &v35, v37, &v38, &v33);
              if ( v23 < 0 )
              {
                _bstr_t::_Free((_bstr_t *)&v33);
                if ( v34 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                if ( v35 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                _bstr_t::_Free((_bstr_t *)&v32);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
                return (unsigned int)v23;
              }
              if ( v38 )
                break;
              v24 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v36);
              Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v24);
              v26 = v34;
              if ( v34 != *Node )
              {
                v34 = *Node;
                _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v34);
                if ( v26 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              if ( v44 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              _bstr_t::_Free((_bstr_t *)&v33);
              v21 = v34;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WppDbgPrint("Adding Error for %S: value=%S");
              if ( v33 )
                v27 = *v33;
              else
                v27 = 0;
              if ( v15 )
                v28 = *v15;
              else
                v28 = 0;
              WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v27);
            }
            StringValueFromNode = CIasMigErrorHelper::AddError(a2, a4, v46, a6, (__int64)&v32, (__int64)&v33);
            if ( StringValueFromNode >= 0 )
            {
              _bstr_t::_Free((_bstr_t *)&v33);
              v15 = (__int64 *)v32;
LABEL_46:
              v29 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v41);
              v30 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v29);
              v31 = v35;
              if ( v35 != *v30 )
              {
                v35 = *v30;
                _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v35);
                if ( v31 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              }
              if ( v40 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              if ( v34 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              continue;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WppDbgPrint("AddError() failed: %!hresult!");
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
                (unsigned int)"NPSDS",
                StringValueFromNode);
            }
            _bstr_t::_Free((_bstr_t *)&v33);
            if ( v34 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            _bstr_t::_Free((_bstr_t *)&v32);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            return (unsigned int)StringValueFromNode;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        else if ( v35 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        break;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      _bstr_t::_Free((_bstr_t *)&v32);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004b6d0  mov     rax, rsp
0x18004b6d3  mov     [rax+8], rbx
0x18004b6d7  mov     [rax+18h], r8
0x18004b6db  mov     [rax+10h], rdx
0x18004b6df  push    rbp
0x18004b6e0  push    rsi
0x18004b6e1  push    rdi
0x18004b6e2  push    r12
0x18004b6e4  push    r13
0x18004b6e6  push    r14
0x18004b6e8  push    r15
0x18004b6ea  lea     rbp, [rax-4Fh]
0x18004b6ee  sub     rsp, 90h
0x18004b6f5  mov     r13, r9
0x18004b6f8  mov     rsi, r8
0x18004b6fb  cmp     [rbp+47h+arg_20], 0
0x18004b700  jnz     short loc_18004B70C
0x18004b702  mov     eax, 8000FFFFh
0x18004b707  jmp     loc_18004BD98
0x18004b70c  mov     [rbp+47h+var_68], 0
0x18004b713  lea     rdx, [rbp+47h+var_68]
0x18004b717  mov     rcx, r13
0x18004b71a  call    ?GetOperatorFromNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAW4CompareOperator@@@Z; CIASMigrationHelper::GetOperatorFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator &)
0x18004b71f  test    eax, eax
0x18004b721  js      loc_18004BD98
0x18004b727  mov     rcx, r13
0x18004b72a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b72f  mov     rbx, rax
0x18004b732  lea     rdx, ?m_migNameQuery@CIASMigrationHelper@@1QBGB; "./Name"
0x18004b739  lea     rcx, [rbp+47h+var_60]; this
0x18004b73d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b742  mov     r8, rax
0x18004b745  lea     rdx, [rbp+47h+var_48]
0x18004b749  mov     rcx, rbx; struct IUnknown *
0x18004b74c  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004b751  nop
0x18004b752  mov     rbx, [rbp+47h+var_48]
0x18004b756  test    rbx, rbx
0x18004b759  jnz     short loc_18004B75D
0x18004b75b  jmp     short loc_18004B702
0x18004b75d  mov     [rbp+47h+var_90], 0
0x18004b765  lea     rdx, [rbp+47h+var_90]
0x18004b769  lea     rcx, [rbp+47h+var_48]
0x18004b76d  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004b772  mov     edi, eax
0x18004b774  test    eax, eax
0x18004b776  jns     short loc_18004B799
0x18004b778  lea     rcx, [rbp+47h+var_90]; this
0x18004b77c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b781  nop
0x18004b782  mov     rcx, [rbx]
0x18004b785  mov     rax, [rcx+10h]
0x18004b789  mov     rcx, rbx
0x18004b78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b791  nop
0x18004b792  mov     eax, edi
0x18004b794  jmp     loc_18004BD98
0x18004b799  mov     rcx, rsi
0x18004b79c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b7a1  mov     rdi, rax
0x18004b7a4  lea     rdx, ?m_migPropertiesQuery@CIASMigrationHelper@@1QBGB; "./Properties"
0x18004b7ab  lea     rcx, [rbp+47h+var_88]; this
0x18004b7af  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b7b4  mov     r8, rax
0x18004b7b7  lea     rdx, [rbp+47h+var_60]
0x18004b7bb  mov     rcx, rdi; struct IUnknown *
0x18004b7be  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004b7c3  nop
0x18004b7c4  mov     rsi, [rbp+47h+var_60]
0x18004b7c8  test    rsi, rsi
0x18004b7cb  jnz     short loc_18004B7EC
0x18004b7cd  lea     rcx, [rbp+47h+var_90]; this
0x18004b7d1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b7d6  nop
0x18004b7d7  mov     rax, [rbx]
0x18004b7da  mov     rcx, rbx
0x18004b7dd  mov     rax, [rax+10h]
0x18004b7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7e6  nop
0x18004b7e7  jmp     loc_18004B702
0x18004b7ec  lea     rcx, [rbp+47h+var_60]
0x18004b7f0  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b7f5  mov     rdi, [rbp+47h+var_90]
0x18004b7f9  mov     [rbp+47h+var_70], rdi
0x18004b7fd  test    rdi, rdi
0x18004b800  jz      short loc_18004B806
0x18004b802  lock inc dword ptr [rdi+10h]
0x18004b806  lea     r8, [rbp+47h+var_70]
0x18004b80a  lea     rdx, [rbp+47h+var_50]
0x18004b80e  mov     rcx, rax; struct IUnknown *
0x18004b811  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x18004b816  nop
0x18004b817  mov     r15, [rbp+47h+var_50]
0x18004b81b  test    r15, r15
0x18004b81e  jnz     short loc_18004B84F
0x18004b820  mov     rax, [rsi]
0x18004b823  mov     rcx, rsi
0x18004b826  mov     rax, [rax+10h]
0x18004b82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b82f  nop
0x18004b830  lea     rcx, [rbp+47h+var_90]; this
0x18004b834  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b839  nop
0x18004b83a  mov     rax, [rbx]
0x18004b83d  mov     rcx, rbx
0x18004b840  mov     rax, [rax+10h]
0x18004b844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b849  nop
0x18004b84a  jmp     loc_18004BD96
0x18004b84f  lea     rcx, [rbp+47h+var_50]
0x18004b853  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b858  lea     rdx, [rbp+47h+var_78]
0x18004b85c  mov     rcx, rax; struct IUnknown *
0x18004b85f  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004b864  nop
0x18004b865  lea     r12, WPP_GLOBAL_Control
0x18004b86c  cmp     [rbp+47h+var_78], 0
0x18004b871  jz      loc_18004BD5C
0x18004b877  mov     rcx, r13
0x18004b87a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b87f  mov     r14, rax
0x18004b882  lea     rdx, ?m_migValueQuery@CIASMigrationHelper@@1QBGB; "./Value"
0x18004b889  lea     rcx, [rbp+47h+var_40]; this
0x18004b88d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b892  mov     r8, rax
0x18004b895  lea     rdx, [rbp+47h+var_70]
0x18004b899  mov     rcx, r14; struct IUnknown *
0x18004b89c  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x18004b8a1  nop
0x18004b8a2  mov     r14, [rbp+47h+var_70]
0x18004b8a6  test    r14, r14
0x18004b8a9  jz      loc_18004BD07
0x18004b8af  lea     rcx, [rbp+47h+var_70]
0x18004b8b3  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b8b8  lea     rdx, [rbp+47h+var_80]
0x18004b8bc  mov     rcx, rax; struct IUnknown *
0x18004b8bf  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004b8c4  nop
0x18004b8c5  mov     rax, [rbp+47h+var_80]
0x18004b8c9  test    rax, rax
0x18004b8cc  jz      loc_18004BCA2
0x18004b8d2  test    rax, rax
0x18004b8d5  jz      loc_18004BAC2
0x18004b8db  mov     [rbp+47h+var_88], 0
0x18004b8e3  mov     [rbp+47h+var_64], 0
0x18004b8ea  mov     rax, cs:WPP_GLOBAL_Control
0x18004b8f1  cmp     rax, r12
0x18004b8f4  jz      short loc_18004B94E
0x18004b8f6  cmp     byte ptr [rax+19h], 4
0x18004b8fa  jb      short loc_18004B94E
0x18004b8fc  test    byte ptr [rax+1Ch], 10h
0x18004b900  jz      short loc_18004B94E
0x18004b902  test    rdi, rdi
0x18004b905  jz      short loc_18004B90C
0x18004b907  mov     rdx, [rdi]
0x18004b90a  jmp     short loc_18004B90E
0x18004b90c  xor     edx, edx
0x18004b90e  lea     rcx, aComparingValue; "Comparing values for %S"
0x18004b915  call    WppDbgPrint
0x18004b91a  test    rdi, rdi
0x18004b91d  jz      short loc_18004B924
0x18004b91f  mov     rax, [rdi]
0x18004b922  jmp     short loc_18004B926
0x18004b924  xor     eax, eax
0x18004b926  mov     edx, 13h
0x18004b92b  mov     [rsp+0C0h+var_A0], rax
0x18004b930  lea     r9, aNpsds; "NPSDS"
0x18004b937  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004b93e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b945  mov     rcx, [rcx+10h]
0x18004b949  call    WPP_SF_sS
0x18004b94e  lea     rax, [rbp+47h+var_88]
0x18004b952  mov     [rsp+0C0h+var_A0], rax
0x18004b957  lea     r9, [rbp+47h+var_64]
0x18004b95b  mov     r8d, [rbp+47h+var_68]
0x18004b95f  lea     rdx, [rbp+47h+var_78]
0x18004b963  lea     rcx, [rbp+47h+var_80]
0x18004b967  mov     rax, [rbp+47h+arg_20]
0x18004b96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b970  mov     r12d, eax
0x18004b973  test    eax, eax
0x18004b975  js      loc_18004BC1A
0x18004b97b  cmp     [rbp+47h+var_64], 0
0x18004b97f  jnz     short loc_18004B9F4
0x18004b981  lea     rcx, [rbp+47h+var_70]
0x18004b985  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004b98a  lea     rdx, [rbp+47h+var_38]
0x18004b98e  mov     rcx, rax; struct IUnknown *
0x18004b991  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004b996  mov     rcx, [rax]
0x18004b999  mov     r12, [rbp+47h+var_80]
0x18004b99d  cmp     r12, rcx
0x18004b9a0  jz      short loc_18004B9C5
0x18004b9a2  mov     [rbp+47h+var_80], rcx
0x18004b9a6  lea     rcx, [rbp+47h+var_80]
0x18004b9aa  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004b9af  test    r12, r12
0x18004b9b2  jz      short loc_18004B9C5
0x18004b9b4  mov     rax, [r12]
0x18004b9b8  mov     rcx, r12
0x18004b9bb  mov     rax, [rax+10h]
0x18004b9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9c4  nop
0x18004b9c5  mov     rcx, [rbp+47h+var_38]
0x18004b9c9  test    rcx, rcx
0x18004b9cc  jz      short loc_18004B9DB
0x18004b9ce  mov     rax, [rcx]
0x18004b9d1  mov     rax, [rax+10h]
0x18004b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9da  nop
0x18004b9db  lea     rcx, [rbp+47h+var_88]; this
0x18004b9df  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b9e4  mov     rax, [rbp+47h+var_80]
0x18004b9e8  lea     r12, WPP_GLOBAL_Control
0x18004b9ef  jmp     loc_18004B8D2
0x18004b9f4  mov     rax, cs:WPP_GLOBAL_Control
0x18004b9fb  lea     r12, WPP_GLOBAL_Control
0x18004ba02  cmp     rax, r12
0x18004ba05  jz      short loc_18004BA85
0x18004ba07  cmp     byte ptr [rax+19h], 4
0x18004ba0b  jb      short loc_18004BA85
0x18004ba0d  test    byte ptr [rax+1Ch], 10h
0x18004ba11  jz      short loc_18004BA85
0x18004ba13  mov     rax, [rbp+47h+var_88]
0x18004ba17  test    rax, rax
0x18004ba1a  jz      short loc_18004BA21
0x18004ba1c  mov     r8, [rax]
0x18004ba1f  jmp     short loc_18004BA24
0x18004ba21  xor     r8d, r8d
0x18004ba24  test    rdi, rdi
0x18004ba27  jz      short loc_18004BA2E
0x18004ba29  mov     rdx, [rdi]
0x18004ba2c  jmp     short loc_18004BA30
0x18004ba2e  xor     edx, edx
0x18004ba30  lea     rcx, aAddingErrorFor; "Adding Error for %S: value=%S"
0x18004ba37  call    WppDbgPrint
0x18004ba3c  mov     rax, [rbp+47h+var_88]
0x18004ba40  test    rax, rax
0x18004ba43  jz      short loc_18004BA4A
0x18004ba45  mov     rcx, [rax]
0x18004ba48  jmp     short loc_18004BA4C
0x18004ba4a  xor     ecx, ecx
0x18004ba4c  test    rdi, rdi
0x18004ba4f  jz      short loc_18004BA56
0x18004ba51  mov     rax, [rdi]
0x18004ba54  jmp     short loc_18004BA58
0x18004ba56  xor     eax, eax
0x18004ba58  mov     edx, 14h
0x18004ba5d  mov     [rsp+28h], rcx; __int64
0x18004ba62  mov     [rsp+0C0h+var_A0], rax; __int64
0x18004ba67  lea     r9, aNpsds; "NPSDS"
0x18004ba6e  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004ba75  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba7c  mov     rcx, [rcx+10h]; LoggerHandle
0x18004ba80  call    WPP_SF_sSS
0x18004ba85  lea     rax, [rbp+47h+var_88]
0x18004ba89  mov     [rsp+28h], rax
0x18004ba8e  lea     rax, [rbp+47h+var_90]
0x18004ba92  mov     [rsp+0C0h+var_A0], rax
0x18004ba97  mov     r9d, [rbp+47h+arg_28]
0x18004ba9b  mov     r8, [rbp+47h+arg_10]
0x18004ba9f  mov     rdx, r13
0x18004baa2  mov     rcx, [rbp+47h+arg_8]
0x18004baa6  call    ?AddError@CIasMigErrorHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1KAEAV_bstr_t@@2@Z; CIasMigErrorHelper::AddError(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong,_bstr_t &,_bstr_t &)
0x18004baab  mov     edi, eax
0x18004baad  test    eax, eax
0x18004baaf  js      loc_18004BB47
0x18004bab5  lea     rcx, [rbp+47h+var_88]; this
0x18004bab9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004babe  mov     rdi, [rbp+47h+var_90]
0x18004bac2  lea     rcx, [rbp+47h+var_50]
0x18004bac6  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004bacb  lea     rdx, [rbp+47h+var_58]
0x18004bacf  mov     rcx, rax; struct IUnknown *
0x18004bad2  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004bad7  mov     rcx, [rax]
0x18004bada  mov     r12, [rbp+47h+var_78]
0x18004bade  cmp     r12, rcx
0x18004bae1  jz      short loc_18004BB06
0x18004bae3  mov     [rbp+47h+var_78], rcx
0x18004bae7  lea     rcx, [rbp+47h+var_78]
0x18004baeb  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004baf0  test    r12, r12
0x18004baf3  jz      short loc_18004BB06
0x18004baf5  mov     rax, [r12]
0x18004baf9  mov     rcx, r12
0x18004bafc  mov     rax, [rax+10h]
0x18004bb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb05  nop
0x18004bb06  mov     rcx, [rbp+47h+var_58]
0x18004bb0a  test    rcx, rcx
0x18004bb0d  jz      short loc_18004BB1C
0x18004bb0f  mov     rax, [rcx]
0x18004bb12  mov     rax, [rax+10h]
0x18004bb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb1b  nop
0x18004bb1c  mov     rcx, [rbp+47h+var_80]
0x18004bb20  test    rcx, rcx
0x18004bb23  jz      short loc_18004BB32
0x18004bb25  mov     rax, [rcx]
  ... truncated ...
```
