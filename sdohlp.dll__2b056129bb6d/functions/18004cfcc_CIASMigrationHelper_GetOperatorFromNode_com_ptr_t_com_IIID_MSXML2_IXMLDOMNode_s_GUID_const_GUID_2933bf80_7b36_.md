# CIASMigrationHelper::GetOperatorFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator &)

- ea: `0x18004cfcc`
- end: `0x18004d114`
- name: `?GetOperatorFromNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAW4CompareOperator@@@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b6d0`

## callees

- `0x18002d08c`
- `0x18002efa0`
- `0x180047604`
- `0x18004cfcc`
- `0x18004d11c`
- `0x180052588`
- `0x180058010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18004d06f`
- `KERNEL32!lstrcmpW` at `0x18004d090`
- `KERNEL32!lstrcmpW` at `0x18004d0b5`
- `KERNEL32!lstrcmpW` at `0x18004d06f`
- `KERNEL32!lstrcmpW` at `0x18004d090`
- `KERNEL32!lstrcmpW` at `0x18004d0b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIASMigrationHelper::GetOperatorFromNode(__int64 *a1, _DWORD *a2)
{
  struct IUnknown *v3; // rbx
  _bstr_t *v4; // rax
  __int64 v5; // rdi
  int StringValueFromNode; // ebx
  const WCHAR **v8; // rbx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rcx
  const WCHAR **v12; // [rsp+40h] [rbp+18h] BYREF
  __int64 v13; // [rsp+48h] [rbp+20h] BYREF

  v3 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v4 = _bstr_t::_bstr_t((_bstr_t *)&v12, L"./Operation");
  MSXML2::IXMLDOMNode::selectSingleNode(v3, &v13, v4);
  v5 = v13;
  if ( v13 )
  {
    v12 = 0;
    StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v13, (__int64)&v12);
    if ( StringValueFromNode < 0 )
    {
      _bstr_t::_Free((_bstr_t *)&v12);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return (unsigned int)StringValueFromNode;
    }
    v8 = v12;
    if ( v12 )
      v9 = *v12;
    else
      v9 = 0;
    if ( !lstrcmpW(v9, L"equals") )
    {
      *a2 = 0;
LABEL_19:
      _bstr_t::_Free((_bstr_t *)&v12);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return 0;
    }
    if ( v8 )
      v10 = *v8;
    else
      v10 = 0;
    if ( !lstrcmpW(v10, L"not equals") )
    {
      *a2 = 1;
      goto LABEL_19;
    }
    if ( v8 )
      v11 = *v8;
    else
      v11 = 0;
    if ( !lstrcmpW(v11, L"regexp") )
    {
      *a2 = 2;
      goto LABEL_19;
    }
    _bstr_t::_Free((_bstr_t *)&v12);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18004cfcc  mov     [rsp+arg_0], rbx
0x18004cfd1  mov     [rsp+arg_8], rsi
0x18004cfd6  push    rdi
0x18004cfd7  sub     rsp, 20h
0x18004cfdb  mov     rsi, rdx
0x18004cfde  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004cfe3  mov     rbx, rax
0x18004cfe6  lea     rdx, ?m_migOperationQuery@CIASMigrationHelper@@1QBGB; "./Operation"
0x18004cfed  lea     rcx, [rsp+28h+arg_10]; this
0x18004cff2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004cff7  mov     r8, rax
0x18004cffa  lea     rdx, [rsp+28h+arg_18]
0x18004cfff  mov     rcx, rbx; struct IUnknown *
0x18004d002  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004d007  nop
0x18004d008  mov     rdi, [rsp+28h+arg_18]
0x18004d00d  test    rdi, rdi
0x18004d010  jnz     short loc_18004D017
0x18004d012  jmp     loc_18004D0FF
0x18004d017  mov     [rsp+28h+arg_10], 0
0x18004d020  lea     rdx, [rsp+28h+arg_10]
0x18004d025  lea     rcx, [rsp+28h+arg_18]
0x18004d02a  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004d02f  mov     ebx, eax
0x18004d031  test    eax, eax
0x18004d033  jns     short loc_18004D057
0x18004d035  lea     rcx, [rsp+28h+arg_10]; this
0x18004d03a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d03f  nop
0x18004d040  mov     rcx, [rdi]
0x18004d043  mov     rax, [rcx+10h]
0x18004d047  mov     rcx, rdi
0x18004d04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d04f  nop
0x18004d050  mov     eax, ebx
0x18004d052  jmp     loc_18004D104
0x18004d057  mov     rbx, [rsp+28h+arg_10]
0x18004d05c  test    rbx, rbx
0x18004d05f  jz      short loc_18004D066
0x18004d061  mov     rcx, [rbx]
0x18004d064  jmp     short loc_18004D068
0x18004d066  xor     ecx, ecx; lpString1
0x18004d068  lea     rdx, ?m_intEquals@CIASMigrationHelper@@1QBGB; "equals"
0x18004d06f  call    cs:__imp_lstrcmpW
0x18004d075  test    eax, eax
0x18004d077  jnz     short loc_18004D07D
0x18004d079  mov     [rsi], eax
0x18004d07b  jmp     short loc_18004D0C5
0x18004d07d  test    rbx, rbx
0x18004d080  jz      short loc_18004D087
0x18004d082  mov     rcx, [rbx]
0x18004d085  jmp     short loc_18004D089
0x18004d087  xor     ecx, ecx; lpString1
0x18004d089  lea     rdx, ?m_intNotEquals@CIASMigrationHelper@@1QBGB; "not equals"
0x18004d090  call    cs:__imp_lstrcmpW
0x18004d096  test    eax, eax
0x18004d098  jnz     short loc_18004D0A2
0x18004d09a  mov     dword ptr [rsi], 1
0x18004d0a0  jmp     short loc_18004D0C5
0x18004d0a2  test    rbx, rbx
0x18004d0a5  jz      short loc_18004D0AC
0x18004d0a7  mov     rcx, [rbx]
0x18004d0aa  jmp     short loc_18004D0AE
0x18004d0ac  xor     ecx, ecx; lpString1
0x18004d0ae  lea     rdx, ?m_strRegexp@CIASMigrationHelper@@1QBGB; "regexp"
0x18004d0b5  call    cs:__imp_lstrcmpW
0x18004d0bb  test    eax, eax
0x18004d0bd  jnz     short loc_18004D0E4
0x18004d0bf  mov     dword ptr [rsi], 2
0x18004d0c5  lea     rcx, [rsp+28h+arg_10]; this
0x18004d0ca  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d0cf  nop
0x18004d0d0  mov     rax, [rdi]
0x18004d0d3  mov     rcx, rdi
0x18004d0d6  mov     rax, [rax+10h]
0x18004d0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0df  nop
0x18004d0e0  xor     eax, eax
0x18004d0e2  jmp     short loc_18004D104
0x18004d0e4  lea     rcx, [rsp+28h+arg_10]; this
0x18004d0e9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d0ee  nop
0x18004d0ef  mov     rax, [rdi]
0x18004d0f2  mov     rcx, rdi
0x18004d0f5  mov     rax, [rax+10h]
0x18004d0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0fe  nop
0x18004d0ff  mov     eax, 8000FFFFh
0x18004d104  mov     rbx, [rsp+28h+arg_0]
0x18004d109  mov     rsi, [rsp+28h+arg_8]
0x18004d10e  add     rsp, 20h
0x18004d112  pop     rdi
0x18004d113  retn
```
