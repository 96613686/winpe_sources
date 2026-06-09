# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180005d60`
- end: `0x180005da7`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f98`
- `0x180005d60`
- `0x180005e04`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 v2; // r10

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
0x180005d60  push    rbx
0x180005d62  sub     rsp, 20h
0x180005d66  mov     r10, rcx
0x180005d69  add     rcx, 8; volatile int *
0x180005d6d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005d72  mov     ebx, eax
0x180005d74  test    eax, eax
0x180005d76  jnz     short loc_180005D87
0x180005d78  test    r10, r10
0x180005d7b  jz      short loc_180005D9F
0x180005d7d  mov     rcx, r10
0x180005d80  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180005d85  jmp     short loc_180005D9F
0x180005d87  cmp     ebx, 1
0x180005d8a  jnz     short loc_180005D9F
0x180005d8c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d93  mov     rax, [rcx]
0x180005d96  mov     rax, [rax+10h]
0x180005d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9f  mov     eax, ebx
0x180005da1  add     rsp, 20h
0x180005da5  pop     rbx
0x180005da6  retn
```
