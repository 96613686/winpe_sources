# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180003d90`
- end: `0x180003dd7`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800036c8`
- `0x180003d90`
- `0x180003de0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 )
  {
    if ( v1 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  else if ( v2 )
  {
    ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x180003d90  push    rbx
0x180003d92  sub     rsp, 20h
0x180003d96  mov     r10, rcx
0x180003d99  add     rcx, 8; volatile int *
0x180003d9d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180003da2  mov     ebx, eax
0x180003da4  test    eax, eax
0x180003da6  jnz     short loc_180003DB7
0x180003da8  test    r10, r10
0x180003dab  jz      short loc_180003DCF
0x180003dad  mov     rcx, r10; Block
0x180003db0  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180003db5  jmp     short loc_180003DCF
0x180003db7  cmp     ebx, 1
0x180003dba  jnz     short loc_180003DCF
0x180003dbc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003dc3  mov     rax, [rcx]
0x180003dc6  mov     rax, [rax+10h]
0x180003dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dcf  mov     eax, ebx
0x180003dd1  add     rsp, 20h
0x180003dd5  pop     rbx
0x180003dd6  retn
```
