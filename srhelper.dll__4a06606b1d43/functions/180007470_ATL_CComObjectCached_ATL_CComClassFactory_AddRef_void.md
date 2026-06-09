# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180007470`
- end: `0x1800074ba`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007470`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      if ( v2 == 1 )
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180007470  push    rbx
0x180007472  sub     rsp, 20h
0x180007476  mov     ebx, 7FFFFFFFh
0x18000747b  jmp     short loc_18000748B
0x18000747d  lea     edx, [r8+1]
0x180007481  mov     eax, r8d
0x180007484  lock cmpxchg [rcx+8], edx
0x180007489  jz      short loc_180007496
0x18000748b  mov     r8d, [rcx+8]
0x18000748f  cmp     r8d, ebx
0x180007492  jnz     short loc_18000747D
0x180007494  jmp     short loc_1800074B2
0x180007496  lea     ebx, [r8+1]
0x18000749a  cmp     ebx, 2
0x18000749d  jnz     short loc_1800074B2
0x18000749f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800074a6  mov     rax, [rcx]
0x1800074a9  mov     rax, [rax+8]
0x1800074ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b2  mov     eax, ebx
0x1800074b4  add     rsp, 20h
0x1800074b8  pop     rbx
0x1800074b9  retn
```
