# ATL::CComAggObject<CXmlContentFilter>::AddRef(void)

- ea: `0x1800102c0`
- end: `0x1800102e9`
- name: `?AddRef@?$CComAggObject@VCXmlContentFilter@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800102c0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CXmlContentFilter>::AddRef(__int64 a1)
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
0x1800102c0  mov     r9d, 7FFFFFFFh
0x1800102c6  jmp     short loc_1800102D6
0x1800102c8  lea     edx, [r8+1]
0x1800102cc  mov     eax, r8d
0x1800102cf  lock cmpxchg [rcx+8], edx
0x1800102d4  jz      short loc_1800102E1
0x1800102d6  mov     r8d, [rcx+8]
0x1800102da  cmp     r8d, r9d
0x1800102dd  jnz     short loc_1800102C8
0x1800102df  jmp     short loc_1800102E5
0x1800102e1  lea     r9d, [r8+1]
0x1800102e5  mov     eax, r9d
0x1800102e8  retn
```
