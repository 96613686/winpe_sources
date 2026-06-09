# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002ba0`
- end: `0x180002beb`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002ba0`
- `0x18000d010`

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
0x180002ba0  push    rbx
0x180002ba2  sub     rsp, 20h
0x180002ba6  mov     ebx, 7FFFFFFFh
0x180002bab  jmp     short loc_180002BBB
0x180002bad  lea     edx, [r8+1]
0x180002bb1  mov     eax, r8d
0x180002bb4  lock cmpxchg [rcx+8], edx
0x180002bb9  jz      short loc_180002BC6
0x180002bbb  mov     r8d, [rcx+8]
0x180002bbf  cmp     r8d, ebx
0x180002bc2  jnz     short loc_180002BAD
0x180002bc4  jmp     short loc_180002BE2
0x180002bc6  lea     ebx, [r8+1]
0x180002bca  cmp     ebx, 2
0x180002bcd  jnz     short loc_180002BE2
0x180002bcf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002bd6  mov     rax, [rcx]
0x180002bd9  mov     rax, [rax+8]
0x180002bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be2  mov     eax, ebx
0x180002be4  add     rsp, 20h
0x180002be8  pop     rbx
0x180002be9  retn
```
