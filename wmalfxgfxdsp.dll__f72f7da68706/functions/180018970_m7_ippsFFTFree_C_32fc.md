# m7_ippsFFTFree_C_32fc

- ea: `0x180018970`
- end: `0x180018989`
- name: `m7_ippsFFTFree_C_32fc`
- size: `25`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c438`
- `0x18001c530`
- `0x18001c9d0`
- `0x18001cbe0`
- `0x18001d830`
- `0x18001da40`
- `0x18001e5c0`
- `0x18001e7d0`

## callees

- `0x180018970`
- `0x18001f8f0`

## pseudocode

```c
__int64 __fastcall m7_ippsFFTFree_C_32fc(_DWORD *a1)
{
  *a1 = 0;
  if ( a1[7] == 1 )
    m7_ippsFree((__int64)a1);
  return 0;
}

```

## disassembly

```asm
0x180018970  sub     rsp, 28h
0x180018974  and     dword ptr [rcx], 0
0x180018977  cmp     dword ptr [rcx+1Ch], 1
0x18001897b  jnz     short loc_180018982
0x18001897d  call    m7_ippsFree
0x180018982  xor     eax, eax
0x180018984  add     rsp, 28h
0x180018988  retn
```
