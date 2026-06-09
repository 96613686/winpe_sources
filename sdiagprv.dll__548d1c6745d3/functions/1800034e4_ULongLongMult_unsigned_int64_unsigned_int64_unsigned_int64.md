# ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)

- ea: `0x1800034e4`
- end: `0x18000350c`
- name: `?ULongLongMult@@YAJ_K0PEA_K@Z`
- size: `40`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180002840`
- `0x180002ac4`
- `0x180002dc0`
- `0x1800087e0`
- `0x180008cdc`
- `0x180008f00`
- `0x18000a964`
- `0x18000c2a0`
- `0x18000dc8c`
- `0x18000e1bc`
- `0x18000e7f4`
- `0x18000f654`
- `0x180015324`
- `0x180015fa8`

## callees

- `0x1800034e4`

## pseudocode

```c
__int64 __fastcall ULongLongMult(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  unsigned __int64 v4; // rcx
  __int64 result; // rax

  v4 = a1 * a2;
  if ( is_mul_ok(a1, a2) )
  {
    result = 0;
  }
  else
  {
    result = 2147942934LL;
    v4 = -1;
  }
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x1800034e4  mov     rax, rdx
0x1800034e7  mov     [rsp+arg_18], 0
0x1800034f0  mul     rcx
0x1800034f3  mov     rcx, rax
0x1800034f6  test    rdx, rdx
0x1800034f9  jnz     short loc_1800034FF
0x1800034fb  xor     eax, eax
0x1800034fd  jmp     short loc_180003508
0x1800034ff  mov     eax, 80070216h
0x180003504  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003508  mov     [r8], rcx
0x18000350b  retn
```
