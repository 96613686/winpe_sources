# ATL::CComAggObject<CElevateWlanUi>::AddRef(void)

- ea: `0x180002fe0`
- end: `0x180003009`
- name: `?AddRef@?$CComAggObject@VCElevateWlanUi@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fe0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CElevateWlanUi>::AddRef(__int64 a1)
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
0x180002fe0  mov     r9d, 7FFFFFFFh
0x180002fe6  jmp     short loc_180002FF6
0x180002fe8  lea     edx, [r8+1]
0x180002fec  mov     eax, r8d
0x180002fef  lock cmpxchg [rcx+8], edx
0x180002ff4  jz      short loc_180003001
0x180002ff6  mov     r8d, [rcx+8]
0x180002ffa  cmp     r8d, r9d
0x180002ffd  jnz     short loc_180002FE8
0x180002fff  jmp     short loc_180003005
0x180003001  lea     r9d, [r8+1]
0x180003005  mov     eax, r9d
0x180003008  retn
```
