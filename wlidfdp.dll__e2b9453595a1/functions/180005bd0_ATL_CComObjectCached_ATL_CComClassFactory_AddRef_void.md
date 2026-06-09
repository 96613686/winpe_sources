# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180005bd0`
- end: `0x180005c01`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005bd0`
- `0x1800086a4`
- `0x180012010`

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
0x180005bd0  push    rbx
0x180005bd2  sub     rsp, 20h
0x180005bd6  add     rcx, 8; volatile int *
0x180005bda  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180005bdf  mov     ebx, eax
0x180005be1  cmp     eax, 2
0x180005be4  jnz     short loc_180005BF9
0x180005be6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005bed  mov     rdx, [rcx]
0x180005bf0  mov     rax, [rdx+8]
0x180005bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf9  mov     eax, ebx
0x180005bfb  add     rsp, 20h
0x180005bff  pop     rbx
0x180005c00  retn
```
