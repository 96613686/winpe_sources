# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180003710`
- end: `0x180003741`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003710`
- `0x180003e08`
- `0x18000c010`

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
0x180003710  push    rbx
0x180003712  sub     rsp, 20h
0x180003716  add     rcx, 8; volatile int *
0x18000371a  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000371f  mov     ebx, eax
0x180003721  cmp     eax, 2
0x180003724  jnz     short loc_180003739
0x180003726  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000372d  mov     rdx, [rcx]
0x180003730  mov     rax, [rdx+8]
0x180003734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003739  mov     eax, ebx
0x18000373b  add     rsp, 20h
0x18000373f  pop     rbx
0x180003740  retn
```
