# LresFromHr(long)

- ea: `0x180006134`
- end: `0x18000615c`
- name: `?LresFromHr@@YA_JJ@Z`
- size: `40`
- prototype: `__int64 __fastcall(int)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180009380`
- `0x180009dd0`
- `0x180009f38`
- `0x18000a4b4`
- `0x18000a690`
- `0x18000a7f8`
- `0x18000b078`
- `0x18000b2e8`
- `0x18000b3a8`
- `0x18000c290`
- `0x18000c824`
- `0x18000df1c`
- `0x18000e148`
- `0x18000e31c`
- `0x18000eed8`
- `0x180012124`
- `0x180012660`
- `0x180013120`
- `0x180013570`
- `0x180013af0`
- `0x180013e54`

## callees

- `0x180006134`

## pseudocode

```c
__int64 __fastcall LresFromHr(int a1)
{
  __int64 result; // rax

  if ( a1 == -2147180479 )
    return 1;
  if ( a1 == -2147180478 )
    return 2;
  result = 0;
  if ( a1 < 0 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180006134  movsxd  rdx, ecx
0x180006137  cmp     edx, 8004A041h
0x18000613d  jnz     short loc_180006145
0x18000613f  mov     eax, 1
0x180006144  retn
0x180006145  cmp     edx, 8004A042h
0x18000614b  jnz     short loc_180006153
0x18000614d  mov     eax, 2
0x180006152  retn
0x180006153  xor     eax, eax
0x180006155  test    ecx, ecx
0x180006157  cmovs   rax, rdx
0x18000615b  retn
```
