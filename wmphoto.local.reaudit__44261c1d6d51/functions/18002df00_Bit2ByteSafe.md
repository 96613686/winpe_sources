# Bit2ByteSafe

- ea: `0x18002df00`
- end: `0x18002df31`
- name: `Bit2ByteSafe`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180028940`
- `0x180031850`
- `0x180033ee0`
- `0x180039e90`

## callees

- `0x18002df00`

## pseudocode

```c
__int64 __fastcall Bit2ByteSafe(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  unsigned __int64 v3; // rax
  __int64 result; // rax
  unsigned __int64 v5; // rcx

  v3 = a1 * a2;
  if ( is_mul_ok(a1, a2) && v3 + 7 >= v3 )
  {
    v5 = (v3 + 7) >> 3;
    result = 0;
  }
  else
  {
    result = -1;
    v5 = -1;
  }
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x18002df00  mov     rax, rdx
0x18002df03  mov     [rsp+arg_18], 0
0x18002df0c  mul     rcx
0x18002df0f  test    rdx, rdx
0x18002df12  jnz     short loc_18002DF1D
0x18002df14  lea     rcx, [rax+7]
0x18002df18  cmp     rcx, rax
0x18002df1b  jnb     short loc_18002DF29
0x18002df1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002df21  mov     rcx, rax
0x18002df24  mov     [r8], rcx
0x18002df27  retn
0x18002df29  shr     rcx, 3
0x18002df2d  xor     eax, eax
0x18002df2f  jmp     short loc_18002DF24
```
