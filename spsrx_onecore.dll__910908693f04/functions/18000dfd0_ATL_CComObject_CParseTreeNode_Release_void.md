# ATL::CComObject<CParseTreeNode>::Release(void)

- ea: `0x18000dfd0`
- end: `0x18000e036`
- name: `?Release@?$CComObject@VCParseTreeNode@@@ATL@@UEAAKXZ`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005294`
- `0x18000dfd0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CParseTreeNode>::Release(int *a1)
{
  unsigned int v2; // edi

  v2 = ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(a1 + 2);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(int *, _QWORD))(*(_QWORD *)a1 + 88LL))(a1, v2 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000dfd0  mov     [rsp+arg_0], rbx
0x18000dfd5  push    rdi
0x18000dfd6  sub     rsp, 20h
0x18000dfda  mov     rbx, rcx
0x18000dfdd  add     rcx, 8
0x18000dfe1  call    ?InternalRelease@?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(void)
0x18000dfe6  mov     edi, eax
0x18000dfe8  test    eax, eax
0x18000dfea  jnz     short loc_18000E029
0x18000dfec  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dff3  mov     rdx, [rcx]
0x18000dff6  mov     rax, [rdx+8]
0x18000dffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfff  test    rbx, rbx
0x18000e002  jz      short loc_18000E016
0x18000e004  mov     rax, [rbx]
0x18000e007  lea     edx, [rdi+1]
0x18000e00a  mov     rcx, rbx
0x18000e00d  mov     rax, [rax+58h]
0x18000e011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e016  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e01d  mov     rax, [rcx]
0x18000e020  mov     rax, [rax+10h]
0x18000e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e029  mov     rbx, [rsp+28h+arg_0]
0x18000e02e  mov     eax, edi
0x18000e030  add     rsp, 20h
0x18000e034  pop     rdi
0x18000e035  retn
```
