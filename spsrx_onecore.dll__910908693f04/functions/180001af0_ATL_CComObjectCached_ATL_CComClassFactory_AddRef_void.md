# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180001af0`
- end: `0x180001b21`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800019a0`

## callees

- `0x180001af0`
- `0x180002f3c`
- `0x180010010`

## pseudocode

```c
unsigned int __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int result; // eax

  result = ATL::CComMultiThreadModel::SafeIncrementReference((int *)(a1 + 8));
  if ( result == 2 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    return 2;
  }
  return result;
}

```

## disassembly

```asm
0x180001af0  push    rbx
0x180001af2  sub     rsp, 20h
0x180001af6  add     rcx, 8; int *
0x180001afa  call    ?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeIncrementReference(long *)
0x180001aff  mov     ebx, eax
0x180001b01  cmp     eax, 2
0x180001b04  jnz     short loc_180001B1B
0x180001b06  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001b0d  mov     rdx, [rcx]
0x180001b10  mov     rax, [rdx+8]
0x180001b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b19  mov     eax, ebx
0x180001b1b  add     rsp, 20h
0x180001b1f  pop     rbx
0x180001b20  retn
```
