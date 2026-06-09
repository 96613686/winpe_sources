# ATL::CComObject<CWinInetHelperClass>::AddRef(void)

- ea: `0x180003a10`
- end: `0x180003a39`
- name: `?AddRef@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003a40`
- `0x180003a50`

## callees

- `0x180003a10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWinInetHelperClass>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 64);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180003a10  mov     r9d, 7FFFFFFFh
0x180003a16  jmp     short loc_180003A26
0x180003a18  lea     edx, [r8+1]
0x180003a1c  mov     eax, r8d
0x180003a1f  lock cmpxchg [rcx+40h], edx
0x180003a24  jz      short loc_180003A31
0x180003a26  mov     r8d, [rcx+40h]
0x180003a2a  cmp     r8d, r9d
0x180003a2d  jnz     short loc_180003A18
0x180003a2f  jmp     short loc_180003A35
0x180003a31  lea     r9d, [r8+1]
0x180003a35  mov     eax, r9d
0x180003a38  retn
```
