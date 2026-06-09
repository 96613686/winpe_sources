# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180010380`
- end: `0x1800103ca`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010380`
- `0x180017010`

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
0x180010380  push    rbx
0x180010382  sub     rsp, 20h
0x180010386  mov     ebx, 7FFFFFFFh
0x18001038b  jmp     short loc_18001039B
0x18001038d  lea     edx, [r8+1]
0x180010391  mov     eax, r8d
0x180010394  lock cmpxchg [rcx+8], edx
0x180010399  jz      short loc_1800103A6
0x18001039b  mov     r8d, [rcx+8]
0x18001039f  cmp     r8d, ebx
0x1800103a2  jnz     short loc_18001038D
0x1800103a4  jmp     short loc_1800103C2
0x1800103a6  lea     ebx, [r8+1]
0x1800103aa  cmp     ebx, 2
0x1800103ad  jnz     short loc_1800103C2
0x1800103af  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800103b6  mov     rax, [rcx]
0x1800103b9  mov     rax, [rax+8]
0x1800103bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c2  mov     eax, ebx
0x1800103c4  add     rsp, 20h
0x1800103c8  pop     rbx
0x1800103c9  retn
```
