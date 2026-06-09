# CanMoveToPreviousEntry

- ea: `0x180018f1c`
- end: `0x180018f36`
- name: `CanMoveToPreviousEntry`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018eec`
- `0x180019940`

## callees

- `0x180018f1c`

## pseudocode

```c
__int64 __fastcall CanMoveToPreviousEntry(__int64 a1)
{
  __int16 v1; // dx
  __int64 result; // rax

  v1 = *(_WORD *)(a1 + 16);
  if ( !v1 )
    return 0;
  result = 1;
  if ( v1 == *(_WORD *)(a1 + 64) )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180018f1c  movzx   edx, word ptr [rcx+10h]
0x180018f20  xor     r8d, r8d
0x180018f23  test    dx, dx
0x180018f26  jz      short loc_180018F32
0x180018f28  lea     eax, [r8+1]
0x180018f2c  cmp     dx, [rcx+40h]
0x180018f30  jnz     short locret_180018F35
0x180018f32  mov     eax, r8d
0x180018f35  retn
```
