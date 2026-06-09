# KmclDiscountOldDpcCycles

- ea: `0x140006f90`
- end: `0x140006fed`
- name: `KmclDiscountOldDpcCycles`
- size: `93`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`

## callees

- `0x140006f90`

## pseudocode

```c
__int64 __fastcall KmclDiscountOldDpcCycles(__int64 a1)
{
  __int64 result; // rax
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx

  result = MEMORY[0xFFFFF78000000320];
  v2 = MEMORY[0xFFFFF78000000320] - *(_QWORD *)(a1 + 1472);
  if ( MEMORY[0xFFFFF78000000320] != *(_QWORD *)(a1 + 1472) )
  {
    if ( v2 < 0x10 )
    {
      v4 = *(_QWORD *)(a1 + 1480);
      if ( v2 == 1 )
        v3 = v4 - (v4 >> 4);
      else
        v3 = ((16 - v2) * v4) >> 4;
    }
    else
    {
      v3 = 0;
    }
    *(_QWORD *)(a1 + 1480) = v3;
    *(_QWORD *)(a1 + 1472) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140006f90  mov     rax, 0FFFFF78000000320h
0x140006f9a  mov     r9, rcx
0x140006f9d  mov     rax, [rax]
0x140006fa0  mov     r8, rax
0x140006fa3  sub     r8, [rcx+5C0h]
0x140006faa  jz      short locret_140006FEC
0x140006fac  mov     ecx, 10h
0x140006fb1  cmp     r8, rcx
0x140006fb4  jb      short loc_140006FBA
0x140006fb6  xor     edx, edx
0x140006fb8  jmp     short loc_140006FDE
0x140006fba  mov     rdx, [r9+5C8h]
0x140006fc1  cmp     r8, 1
0x140006fc5  jnz     short loc_140006FD3
0x140006fc7  mov     rcx, rdx
0x140006fca  shr     rcx, 4
0x140006fce  sub     rdx, rcx
0x140006fd1  jmp     short loc_140006FDE
0x140006fd3  sub     rcx, r8
0x140006fd6  imul    rdx, rcx
0x140006fda  shr     rdx, 4
0x140006fde  mov     [r9+5C8h], rdx
0x140006fe5  mov     [r9+5C0h], rax
0x140006fec  retn
```
