# ATL::CComObject<CAttributeString>::Release(void)

- ea: `0x18000df60`
- end: `0x18000dfc6`
- name: `?Release@?$CComObject@VCAttributeString@@@ATL@@UEAAKXZ`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005294`
- `0x18000df60`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAttributeString>::Release(int *a1)
{
  unsigned int v2; // edi

  v2 = ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(a1 + 2);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(int *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v2 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000df60  mov     [rsp+arg_0], rbx
0x18000df65  push    rdi
0x18000df66  sub     rsp, 20h
0x18000df6a  mov     rbx, rcx
0x18000df6d  add     rcx, 8
0x18000df71  call    ?InternalRelease@?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(void)
0x18000df76  mov     edi, eax
0x18000df78  test    eax, eax
0x18000df7a  jnz     short loc_18000DFB9
0x18000df7c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000df83  mov     rdx, [rcx]
0x18000df86  mov     rax, [rdx+8]
0x18000df8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df8f  test    rbx, rbx
0x18000df92  jz      short loc_18000DFA6
0x18000df94  mov     rax, [rbx]
0x18000df97  lea     edx, [rdi+1]
0x18000df9a  mov     rcx, rbx
0x18000df9d  mov     rax, [rax+38h]
0x18000dfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dfad  mov     rax, [rcx]
0x18000dfb0  mov     rax, [rax+10h]
0x18000dfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfb9  mov     rbx, [rsp+28h+arg_0]
0x18000dfbe  mov     eax, edi
0x18000dfc0  add     rsp, 20h
0x18000dfc4  pop     rdi
0x18000dfc5  retn
```
