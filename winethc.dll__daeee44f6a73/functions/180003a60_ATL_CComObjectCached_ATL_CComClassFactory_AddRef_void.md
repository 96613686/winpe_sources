# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180003a60`
- end: `0x180003aab`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003a60`
- `0x180014010`

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
0x180003a60  push    rbx
0x180003a62  sub     rsp, 20h
0x180003a66  mov     ebx, 7FFFFFFFh
0x180003a6b  jmp     short loc_180003A7B
0x180003a6d  lea     edx, [r8+1]
0x180003a71  mov     eax, r8d
0x180003a74  lock cmpxchg [rcx+8], edx
0x180003a79  jz      short loc_180003A86
0x180003a7b  mov     r8d, [rcx+8]
0x180003a7f  cmp     r8d, ebx
0x180003a82  jnz     short loc_180003A6D
0x180003a84  jmp     short loc_180003AA2
0x180003a86  lea     ebx, [r8+1]
0x180003a8a  cmp     ebx, 2
0x180003a8d  jnz     short loc_180003AA2
0x180003a8f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003a96  mov     rax, [rcx]
0x180003a99  mov     rax, [rax+8]
0x180003a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa2  mov     eax, ebx
0x180003aa4  add     rsp, 20h
0x180003aa8  pop     rbx
0x180003aa9  retn
```
