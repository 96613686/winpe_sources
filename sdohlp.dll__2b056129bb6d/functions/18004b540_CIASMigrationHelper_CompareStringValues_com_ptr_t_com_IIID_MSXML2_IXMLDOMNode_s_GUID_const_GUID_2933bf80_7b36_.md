# CIASMigrationHelper::CompareStringValues(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &)

- ea: `0x18004b540`
- end: `0x18004b6bc`
- name: `?CompareStringValues@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0W4CompareOperator@@AEAHAEAV_bstr_t@@@Z`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002efa0`
- `0x180039830`
- `0x18004b540`
- `0x18004d11c`
- `0x180054e70`
- `0x180058010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18004b652`
- `KERNEL32!EnterCriticalSection` at `0x18004b652`
- `KERNEL32!LeaveCriticalSection` at `0x18004b686`
- `KERNEL32!LeaveCriticalSection` at `0x18004b686`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b5cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b5cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIASMigrationHelper::CompareStringValues(__int64 *a1, __int64 *a2, int a3, _DWORD *a4, __int64 a5)
{
  int StringValueFromNode; // ebx
  const OLECHAR *v9; // rbx
  OLECHAR *v10; // rbx
  __int64 v11; // rdx
  void *v12; // rbx
  void *v13; // [rsp+20h] [rbp-28h] BYREF
  const OLECHAR **v14; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v15[3]; // [rsp+30h] [rbp-18h] BYREF
  __int16 v16; // [rsp+80h] [rbp+38h] BYREF

  if ( a3 != 2 )
    return 2147549183LL;
  v15[0] = 0;
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(a2, (__int64)v15);
  if ( StringValueFromNode >= 0 )
  {
    v14 = 0;
    StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(a1, (__int64)&v14);
    if ( StringValueFromNode >= 0 )
    {
      *a4 = 0;
      v13 = 0;
      if ( v14 )
        v9 = *v14;
      else
        v9 = 0;
      if ( (int)RegularExpression::checkInit(&v13) >= 0 )
      {
        v10 = SysAllocString(v9);
        if ( v10 )
        {
          (*(void (__fastcall **)(void *, OLECHAR *))(*(_QWORD *)v13 + 64LL))(v13, v10);
          SysFreeString(v10);
        }
      }
      if ( v15[0] )
        v11 = *(_QWORD *)v15[0];
      else
        v11 = 0;
      v16 = 0;
      (*(void (__fastcall **)(void *, __int64, __int16 *))(*(_QWORD *)v13 + 128LL))(v13, v11, &v16);
      if ( v16 )
      {
        _bstr_t::operator=(a5, &v14);
        *a4 = 1;
      }
      v12 = v13;
      if ( v13 )
      {
        EnterCriticalSection(&CriticalSection);
        if ( !--dword_1800765C8 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          ppv = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      }
      StringValueFromNode = 0;
    }
    _bstr_t::_Free((_bstr_t *)&v14);
  }
  _bstr_t::_Free((_bstr_t *)v15);
  return (unsigned int)StringValueFromNode;
}

```

## disassembly

```asm
0x18004b540  push    rbp
0x18004b542  push    rbx
0x18004b543  push    rsi
0x18004b544  push    rdi
0x18004b545  mov     rbp, rsp
0x18004b548  sub     rsp, 48h
0x18004b54c  mov     rdi, r9
0x18004b54f  mov     rax, rdx
0x18004b552  mov     rsi, rcx
0x18004b555  cmp     r8d, 2
0x18004b559  jz      short loc_18004B565
0x18004b55b  mov     eax, 8000FFFFh
0x18004b560  jmp     loc_18004B6B3
0x18004b565  mov     [rbp+var_18], 0
0x18004b56d  lea     rdx, [rbp+var_18]
0x18004b571  mov     rcx, rax
0x18004b574  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004b579  mov     ebx, eax
0x18004b57b  test    eax, eax
0x18004b57d  js      loc_18004B6A8
0x18004b583  mov     [rbp+var_20], 0
0x18004b58b  lea     rdx, [rbp+var_20]
0x18004b58f  mov     rcx, rsi
0x18004b592  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004b597  mov     ebx, eax
0x18004b599  test    eax, eax
0x18004b59b  js      loc_18004B69E
0x18004b5a1  mov     dword ptr [rdi], 0
0x18004b5a7  mov     [rbp+var_28], 0
0x18004b5af  mov     rax, [rbp+var_20]
0x18004b5b3  test    rax, rax
0x18004b5b6  jz      short loc_18004B5BD
0x18004b5b8  mov     rbx, [rax]
0x18004b5bb  jmp     short loc_18004B5BF
0x18004b5bd  xor     ebx, ebx
0x18004b5bf  lea     rcx, [rbp+var_28]; this
0x18004b5c3  call    ?checkInit@RegularExpression@@IEAAJXZ; RegularExpression::checkInit(void)
0x18004b5c8  test    eax, eax
0x18004b5ca  js      short loc_18004B5FA
0x18004b5cc  mov     rcx, rbx; psz
0x18004b5cf  call    cs:__imp_SysAllocString
0x18004b5d5  mov     rbx, rax
0x18004b5d8  test    rax, rax
0x18004b5db  jz      short loc_18004B5FA
0x18004b5dd  mov     rcx, [rbp+var_28]
0x18004b5e1  mov     rdx, [rcx]
0x18004b5e4  mov     rax, [rdx+40h]
0x18004b5e8  mov     rdx, rbx
0x18004b5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5f0  mov     rcx, rbx; bstrString
0x18004b5f3  call    cs:__imp_SysFreeString
0x18004b5f9  nop
0x18004b5fa  mov     rax, [rbp+var_18]
0x18004b5fe  test    rax, rax
0x18004b601  jz      short loc_18004B608
0x18004b603  mov     rdx, [rax]
0x18004b606  jmp     short loc_18004B60A
0x18004b608  xor     edx, edx
0x18004b60a  xor     eax, eax
0x18004b60c  mov     [rbp+arg_10], ax
0x18004b610  mov     rcx, [rbp+var_28]
0x18004b614  mov     rax, [rcx]
0x18004b617  lea     r8, [rbp+arg_10]
0x18004b61b  mov     rax, [rax+80h]
0x18004b622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b627  movsx   eax, [rbp+arg_10]
0x18004b62b  test    eax, eax
0x18004b62d  jz      short loc_18004B642
0x18004b62f  lea     rdx, [rbp+var_20]
0x18004b633  mov     rcx, [rbp+arg_20]
0x18004b637  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004b63c  mov     dword ptr [rdi], 1
0x18004b642  mov     rbx, [rbp+var_28]
0x18004b646  test    rbx, rbx
0x18004b649  jz      short loc_18004B69C
0x18004b64b  lea     rcx, CriticalSection; lpCriticalSection
0x18004b652  call    cs:__imp_EnterCriticalSection
0x18004b658  add     cs:dword_1800765C8, 0FFFFFFFFh
0x18004b65f  jnz     short loc_18004B67F
0x18004b661  mov     rcx, cs:ppv
0x18004b668  mov     rax, [rcx]
0x18004b66b  mov     rax, [rax+10h]
0x18004b66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b674  mov     cs:ppv, 0
0x18004b67f  lea     rcx, CriticalSection; lpCriticalSection
0x18004b686  call    cs:__imp_LeaveCriticalSection
0x18004b68c  mov     rax, [rbx]
0x18004b68f  mov     rcx, rbx
0x18004b692  mov     rax, [rax+10h]
0x18004b696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b69b  nop
0x18004b69c  xor     ebx, ebx
0x18004b69e  lea     rcx, [rbp+var_20]; this
0x18004b6a2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b6a7  nop
0x18004b6a8  lea     rcx, [rbp+var_18]; this
0x18004b6ac  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b6b1  mov     eax, ebx
0x18004b6b3  add     rsp, 48h
0x18004b6b7  pop     rdi
0x18004b6b8  pop     rsi
0x18004b6b9  pop     rbx
0x18004b6ba  pop     rbp
0x18004b6bb  retn
```
