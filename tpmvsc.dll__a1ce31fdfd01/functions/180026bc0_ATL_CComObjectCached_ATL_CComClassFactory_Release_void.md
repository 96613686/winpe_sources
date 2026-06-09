# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180026bc0`
- end: `0x180026c07`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002602c`
- `0x180026bc0`
- `0x180026c10`
- `0x180037010`

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
0x180026bc0  push    rbx
0x180026bc2  sub     rsp, 20h
0x180026bc6  mov     r10, rcx
0x180026bc9  add     rcx, 8; volatile int *
0x180026bcd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180026bd2  mov     ebx, eax
0x180026bd4  test    eax, eax
0x180026bd6  jnz     short loc_180026BE7
0x180026bd8  test    r10, r10
0x180026bdb  jz      short loc_180026BFF
0x180026bdd  mov     rcx, r10; Block
0x180026be0  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180026be5  jmp     short loc_180026BFF
0x180026be7  cmp     ebx, 1
0x180026bea  jnz     short loc_180026BFF
0x180026bec  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180026bf3  mov     rax, [rcx]
0x180026bf6  mov     rax, [rax+10h]
0x180026bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bff  mov     eax, ebx
0x180026c01  add     rsp, 20h
0x180026c05  pop     rbx
0x180026c06  retn
```
