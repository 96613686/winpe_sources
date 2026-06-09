# HUBMISC_StripSymbolicNamePrefix

- ea: `0x14003309c`
- end: `0x1400330eb`
- name: `HUBMISC_StripSymbolicNamePrefix`
- size: `79`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1400185e8`
- `0x14007c64c`
- `0x14007d144`
- `0x14008d828`
- `0x14008d9e0`
- `0x14008e0e0`

## callees

- `0x14003309c`

## pseudocode

```c
_WORD *__fastcall HUBMISC_StripSymbolicNamePrefix(unsigned __int16 *a1, _QWORD *a2)
{
  _WORD *result; // rax
  __int64 v3; // rcx

  result = (_WORD *)*((_QWORD *)a1 + 1);
  if ( result )
  {
    v3 = *a1;
    if ( *result == 92 )
    {
      ++result;
      v3 -= 2;
      while ( *result && *result != 92 )
      {
        ++result;
        v3 -= 2;
      }
      if ( *result == 92 )
      {
        ++result;
        v3 -= 2;
      }
    }
  }
  else
  {
    v3 = 0;
  }
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x14003309c  mov     rax, [rcx+8]
0x1400330a0  xor     r9d, r9d
0x1400330a3  mov     r8, rdx
0x1400330a6  test    rax, rax
0x1400330a9  jnz     short loc_1400330B0
0x1400330ab  mov     ecx, r9d
0x1400330ae  jmp     short loc_1400330E7
0x1400330b0  cmp     word ptr [rax], 5Ch ; '\'
0x1400330b4  movzx   ecx, word ptr [rcx]
0x1400330b7  jnz     short loc_1400330E7
0x1400330b9  add     rax, 2
0x1400330bd  add     rcx, 0FFFFFFFFFFFFFFFEh
0x1400330c1  jmp     short loc_1400330D1
0x1400330c3  cmp     dx, 5Ch ; '\'
0x1400330c7  jz      short loc_1400330D9
0x1400330c9  add     rax, 2
0x1400330cd  sub     rcx, 2
0x1400330d1  movzx   edx, word ptr [rax]
0x1400330d4  test    dx, dx
0x1400330d7  jnz     short loc_1400330C3
0x1400330d9  cmp     word ptr [rax], 5Ch ; '\'
0x1400330dd  jnz     short loc_1400330E7
0x1400330df  add     rax, 2
0x1400330e3  sub     rcx, 2
0x1400330e7  mov     [r8], rcx
0x1400330ea  retn
```
