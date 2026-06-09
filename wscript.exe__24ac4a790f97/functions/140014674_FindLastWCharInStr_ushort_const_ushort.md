# FindLastWCharInStr(ushort const *,ushort)

- ea: `0x140014674`
- end: `0x1400146a5`
- name: `?FindLastWCharInStr@@YAPEBGPEBGG@Z`
- size: `49`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *, unsigned __int16)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000757c`
- `0x140007930`
- `0x14000ad50`
- `0x14000ff80`
- `0x1400111d0`
- `0x140011e90`

## callees

- `0x140014674`

## pseudocode

```c
const unsigned __int16 *__fastcall FindLastWCharInStr(const unsigned __int16 *a1, __int16 a2)
{
  const unsigned __int16 *v2; // r8
  const unsigned __int16 *result; // rax
  unsigned __int16 i; // r9
  const unsigned __int16 *v5; // rcx

  v2 = a1;
  result = 0;
  if ( a1 )
  {
    for ( i = *a1; i; i = *v2 )
    {
      v5 = v2;
      if ( i != a2 )
        v5 = result;
      ++v2;
      result = v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014674  xor     r10d, r10d
0x140014677  mov     r8, rcx
0x14001467a  mov     eax, r10d
0x14001467d  test    rcx, rcx
0x140014680  jz      short locret_1400146A4
0x140014682  movzx   r9d, word ptr [rcx]
0x140014686  jmp     short loc_14001469E
0x140014688  cmp     r9w, dx
0x14001468c  mov     rcx, r8
0x14001468f  cmovnz  rcx, rax
0x140014693  add     r8, 2
0x140014697  mov     rax, rcx
0x14001469a  movzx   r9d, word ptr [r8]
0x14001469e  test    r9w, r9w
0x1400146a2  jnz     short loc_140014688
0x1400146a4  retn
```
