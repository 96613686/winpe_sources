# advanceOneMBRow

- ea: `0x180021b8c`
- end: `0x180021be8`
- name: `advanceOneMBRow`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007400`
- `0x18000f3b4`
- `0x1800214bc`
- `0x180021bf0`

## callees

- `0x180021b8c`

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
0x180021b8c  xor     r10d, r10d
0x180021b8f  mov     rdx, rcx
0x180021b92  cmp     [rcx+8B50h], r10
0x180021b99  setnz   r10b
0x180021b9d  xor     r8d, r8d
0x180021ba0  xor     r9d, r9d
0x180021ba3  cmp     [rdx+85C0h], r9
0x180021baa  jbe     short loc_180021BD8
0x180021bac  mov     rcx, [rdx+r9*8+8A40h]
0x180021bb4  mov     rax, [rdx+r9*8+8AC0h]
0x180021bbc  mov     [rdx+r9*8+8A40h], rax
0x180021bc4  mov     [rdx+r9*8+8AC0h], rcx
0x180021bcc  inc     r9
0x180021bcf  cmp     r9, [rdx+85C0h]
0x180021bd6  jb      short loc_180021BAC
0x180021bd8  mov     rdx, [rdx+8B50h]
0x180021bdf  inc     r8
0x180021be2  cmp     r8, r10
0x180021be5  jbe     short loc_180021BA0
0x180021be7  retn
```
