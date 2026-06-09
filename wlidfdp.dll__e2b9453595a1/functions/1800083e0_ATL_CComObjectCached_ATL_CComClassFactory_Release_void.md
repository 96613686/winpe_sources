# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800083e0`
- end: `0x180008427`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000592c`
- `0x1800083e0`
- `0x18000867c`
- `0x180012010`

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
0x1800083e0  push    rbx
0x1800083e2  sub     rsp, 20h
0x1800083e6  mov     r10, rcx
0x1800083e9  add     rcx, 8; volatile int *
0x1800083ed  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800083f2  mov     ebx, eax
0x1800083f4  test    eax, eax
0x1800083f6  jnz     short loc_180008407
0x1800083f8  test    r10, r10
0x1800083fb  jz      short loc_18000841F
0x1800083fd  mov     rcx, r10; Block
0x180008400  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180008405  jmp     short loc_18000841F
0x180008407  cmp     ebx, 1
0x18000840a  jnz     short loc_18000841F
0x18000840c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008413  mov     rax, [rcx]
0x180008416  mov     rax, [rax+10h]
0x18000841a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000841f  mov     eax, ebx
0x180008421  add     rsp, 20h
0x180008425  pop     rbx
0x180008426  retn
```
