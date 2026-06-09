# advanceOneMBRow

- ea: `0x18002194c`
- end: `0x1800219a8`
- name: `advanceOneMBRow`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007340`
- `0x18000f244`
- `0x180021280`
- `0x1800219b0`

## callees

- `0x18002194c`

## pseudocode

```c
__int64 __fastcall advanceOneMBRow(__int64 a1)
{
  __int64 v1; // rdx
  _BOOL8 v2; // r10
  unsigned __int64 i; // r8
  unsigned __int64 j; // r9
  __int64 v5; // rcx
  __int64 result; // rax

  v1 = a1;
  v2 = *(_QWORD *)(a1 + 35664) != 0;
  for ( i = 0; i <= v2; ++i )
  {
    for ( j = 0; j < *(_QWORD *)(v1 + 34240); ++j )
    {
      v5 = *(_QWORD *)(v1 + 8 * j + 35392);
      result = *(_QWORD *)(v1 + 8 * j + 35520);
      *(_QWORD *)(v1 + 8 * j + 35392) = result;
      *(_QWORD *)(v1 + 8 * j + 35520) = v5;
    }
    v1 = *(_QWORD *)(v1 + 35664);
  }
  return result;
}

```

## disassembly

```asm
0x18002194c  xor     r10d, r10d
0x18002194f  mov     rdx, rcx
0x180021952  cmp     [rcx+8B50h], r10
0x180021959  setnz   r10b
0x18002195d  xor     r8d, r8d
0x180021960  xor     r9d, r9d
0x180021963  cmp     [rdx+85C0h], r9
0x18002196a  jbe     short loc_180021998
0x18002196c  mov     rcx, [rdx+r9*8+8A40h]
0x180021974  mov     rax, [rdx+r9*8+8AC0h]
0x18002197c  mov     [rdx+r9*8+8A40h], rax
0x180021984  mov     [rdx+r9*8+8AC0h], rcx
0x18002198c  inc     r9
0x18002198f  cmp     r9, [rdx+85C0h]
0x180021996  jb      short loc_18002196C
0x180021998  mov     rdx, [rdx+8B50h]
0x18002199f  inc     r8
0x1800219a2  cmp     r8, r10
0x1800219a5  jbe     short loc_180021960
0x1800219a7  retn
```
