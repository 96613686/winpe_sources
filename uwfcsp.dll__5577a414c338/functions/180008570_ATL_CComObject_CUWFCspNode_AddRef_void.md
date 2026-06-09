# ATL::CComObject<CUWFCspNode>::AddRef(void)

- ea: `0x180008570`
- end: `0x180008599`
- name: `?AddRef@?$CComObject@VCUWFCspNode@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800085a0`

## callees

- `0x180008570`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspNode>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 72);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 72), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180008570  mov     r9d, 7FFFFFFFh
0x180008576  jmp     short loc_180008586
0x180008578  lea     edx, [r8+1]
0x18000857c  mov     eax, r8d
0x18000857f  lock cmpxchg [rcx+48h], edx
0x180008584  jz      short loc_180008591
0x180008586  mov     r8d, [rcx+48h]
0x18000858a  cmp     r8d, r9d
0x18000858d  jnz     short loc_180008578
0x18000858f  jmp     short loc_180008595
0x180008591  lea     r9d, [r8+1]
0x180008595  mov     eax, r9d
0x180008598  retn
```
