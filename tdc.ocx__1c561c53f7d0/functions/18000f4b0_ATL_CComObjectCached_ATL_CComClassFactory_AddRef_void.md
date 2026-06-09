# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x18000f4b0`
- end: `0x18000f4fa`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f4b0`
- `0x180015010`

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
0x18000f4b0  push    rbx
0x18000f4b2  sub     rsp, 20h
0x18000f4b6  mov     ebx, 7FFFFFFFh
0x18000f4bb  jmp     short loc_18000F4CB
0x18000f4bd  lea     edx, [r8+1]
0x18000f4c1  mov     eax, r8d
0x18000f4c4  lock cmpxchg [rcx+8], edx
0x18000f4c9  jz      short loc_18000F4D6
0x18000f4cb  mov     r8d, [rcx+8]
0x18000f4cf  cmp     r8d, ebx
0x18000f4d2  jnz     short loc_18000F4BD
0x18000f4d4  jmp     short loc_18000F4F2
0x18000f4d6  lea     ebx, [r8+1]
0x18000f4da  cmp     ebx, 2
0x18000f4dd  jnz     short loc_18000F4F2
0x18000f4df  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f4e6  mov     rax, [rcx]
0x18000f4e9  mov     rax, [rax+8]
0x18000f4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4f2  mov     eax, ebx
0x18000f4f4  add     rsp, 20h
0x18000f4f8  pop     rbx
0x18000f4f9  retn
```
