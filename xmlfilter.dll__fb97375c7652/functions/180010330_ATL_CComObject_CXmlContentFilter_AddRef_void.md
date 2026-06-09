# ATL::CComObject<CXmlContentFilter>::AddRef(void)

- ea: `0x180010330`
- end: `0x180010359`
- name: `?AddRef@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010360`
- `0x180010370`

## callees

- `0x180010330`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComObject<CXmlContentFilter>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 24);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180010330  mov     r9d, 7FFFFFFFh
0x180010336  jmp     short loc_180010346
0x180010338  lea     edx, [r8+1]
0x18001033c  mov     eax, r8d
0x18001033f  lock cmpxchg [rcx+18h], edx
0x180010344  jz      short loc_180010351
0x180010346  mov     r8d, [rcx+18h]
0x18001034a  cmp     r8d, r9d
0x18001034d  jnz     short loc_180010338
0x18001034f  jmp     short loc_180010355
0x180010351  lea     r9d, [r8+1]
0x180010355  mov     eax, r9d
0x180010358  retn
```
