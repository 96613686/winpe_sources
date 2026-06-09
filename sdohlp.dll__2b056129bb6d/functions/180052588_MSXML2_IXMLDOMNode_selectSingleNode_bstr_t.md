# MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)

- ea: `0x180052588`
- end: `0x18005260c`
- name: `?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `16`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049500`
- `0x18004a0c8`
- `0x18004a3b0`
- `0x18004b6d0`
- `0x18004c16c`
- `0x18004c610`
- `0x18004c8d0`
- `0x18004cfcc`
- `0x18004dea0`
- `0x18004e1b0`
- `0x18004e430`
- `0x18004e630`
- `0x18004ef90`
- `0x18004f2cc`
- `0x180052d80`
- `0x1800534b0`

## callees

- `0x18002efa0`
- `0x18004115c`
- `0x180052588`
- `0x180058010`

## pseudocode

```c
_QWORD *__fastcall MSXML2::IXMLDOMNode::selectSingleNode(struct IUnknown *a1, _QWORD *a2, _bstr_t *a3)
{
  __int64 v6; // rdx
  int v7; // eax
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  _bstr_t *v10; // [rsp+50h] [rbp+18h]

  v10 = a3;
  v9 = 0;
  if ( *(_QWORD *)a3 )
    v6 = **(_QWORD **)a3;
  else
    v6 = 0;
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))a1->lpVtbl[12].AddRef)(a1, v6, &v9);
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  *a2 = v9;
  _bstr_t::_Free(a3);
  return a2;
}

```

## disassembly

```asm
0x180052588  mov     rax, rsp
0x18005258b  mov     [rax+10h], rbx
0x18005258f  mov     [rax+20h], rsi
0x180052593  mov     [rax+18h], r8
0x180052597  push    rdi
0x180052598  sub     rsp, 30h
0x18005259c  mov     rdi, r8
0x18005259f  mov     rbx, rdx
0x1800525a2  mov     rsi, rcx
0x1800525a5  mov     qword ptr [rax+8], 0
0x1800525ad  mov     rax, [rcx]
0x1800525b0  mov     r9, [rax+128h]
0x1800525b7  mov     rax, [r8]
0x1800525ba  test    rax, rax
0x1800525bd  jz      short loc_1800525C4
0x1800525bf  mov     rdx, [rax]
0x1800525c2  jmp     short loc_1800525C6
0x1800525c4  xor     edx, edx
0x1800525c6  lea     r8, [rsp+38h+arg_0]
0x1800525cb  mov     rax, r9
0x1800525ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525d3  test    eax, eax
0x1800525d5  jns     short loc_1800525E9
0x1800525d7  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x1800525de  mov     rdx, rsi; struct IUnknown *
0x1800525e1  mov     ecx, eax; int
0x1800525e3  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x1800525e9  mov     rax, [rsp+38h+arg_0]
0x1800525ee  mov     [rbx], rax
0x1800525f1  mov     rcx, rdi; this
0x1800525f4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800525f9  mov     rax, rbx
0x1800525fc  mov     rbx, [rsp+38h+arg_8]
0x180052601  mov     rsi, [rsp+38h+arg_18]
0x180052606  add     rsp, 30h
0x18005260a  pop     rdi
0x18005260b  retn
```
