# ATL::CComObject<CSrDrvWuHelper>::AddRef(void)

- ea: `0x180007440`
- end: `0x180007469`
- name: `?AddRef@?$CComObject@VCSrDrvWuHelper@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007440`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSrDrvWuHelper>::AddRef(__int64 a1)
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
0x180007440  mov     r9d, 7FFFFFFFh
0x180007446  jmp     short loc_180007456
0x180007448  lea     edx, [r8+1]
0x18000744c  mov     eax, r8d
0x18000744f  lock cmpxchg [rcx+8], edx
0x180007454  jz      short loc_180007461
0x180007456  mov     r8d, [rcx+8]
0x18000745a  cmp     r8d, r9d
0x18000745d  jnz     short loc_180007448
0x18000745f  jmp     short loc_180007465
0x180007461  lea     r9d, [r8+1]
0x180007465  mov     eax, r9d
0x180007468  retn
```
