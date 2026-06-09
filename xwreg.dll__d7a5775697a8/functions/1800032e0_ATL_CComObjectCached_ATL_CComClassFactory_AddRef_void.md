# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800032e0`
- end: `0x180003311`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800032e0`
- `0x180005e2c`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 == 2 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x1800032e0  push    rbx
0x1800032e2  sub     rsp, 20h
0x1800032e6  add     rcx, 8; volatile int *
0x1800032ea  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800032ef  mov     ebx, eax
0x1800032f1  cmp     eax, 2
0x1800032f4  jnz     short loc_180003309
0x1800032f6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800032fd  mov     rdx, [rcx]
0x180003300  mov     rax, [rdx+8]
0x180003304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003309  mov     eax, ebx
0x18000330b  add     rsp, 20h
0x18000330f  pop     rbx
0x180003310  retn
```
