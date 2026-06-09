# Bit2ByteSafe

- ea: `0x18002de74`
- end: `0x18002dea4`
- name: `Bit2ByteSafe`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180028980`
- `0x1800314f0`
- `0x180033930`
- `0x180039770`

## callees

- `0x18002de74`

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
0x18002de74  mov     rax, rdx
0x18002de77  mov     [rsp+arg_18], 0
0x18002de80  mul     rcx
0x18002de83  test    rdx, rdx
0x18002de86  jnz     short loc_18002DE91
0x18002de88  lea     rcx, [rax+7]
0x18002de8c  cmp     rcx, rax
0x18002de8f  jnb     short loc_18002DE9C
0x18002de91  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002de95  mov     rcx, rax
0x18002de98  mov     [r8], rcx
0x18002de9b  retn
0x18002de9c  shr     rcx, 3
0x18002dea0  xor     eax, eax
0x18002dea2  jmp     short loc_18002DE98
```
