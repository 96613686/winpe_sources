# ATL::CComObjectNoLock<ATL::CComClassFactory>::AddRef(void)

- ea: `0x140002380`
- end: `0x1400023a9`
- name: `?AddRef@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002380`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140002380  mov     r9d, 7FFFFFFFh
0x140002386  jmp     short loc_140002396
0x140002388  lea     edx, [r8+1]
0x14000238c  mov     eax, r8d
0x14000238f  lock cmpxchg [rcx+8], edx
0x140002394  jz      short loc_1400023A1
0x140002396  mov     r8d, [rcx+8]
0x14000239a  cmp     r8d, r9d
0x14000239d  jnz     short loc_140002388
0x14000239f  jmp     short loc_1400023A5
0x1400023a1  lea     r9d, [r8+1]
0x1400023a5  mov     eax, r9d
0x1400023a8  retn
```
