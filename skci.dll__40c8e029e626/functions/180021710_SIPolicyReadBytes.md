# SIPolicyReadBytes

- ea: `0x180021710`
- end: `0x18002173f`
- name: `SIPolicyReadBytes`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, _QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001f33c`
- `0x18001f800`
- `0x18001f960`
- `0x18002165c`
- `0x1800217d0`
- `0x18002189c`

## callees

- `0x180021710`

## pseudocode

```c
__int64 __fastcall SIPolicyReadBytes(_QWORD *a1, unsigned __int64 a2, _QWORD *a3)
{
  __int64 v3; // r9

  v3 = a1[2];
  if ( a1[1] - *a1 - v3 < a2 )
    return 3236495363LL;
  *a3 = *a1 + v3;
  a1[2] = v3 + a2;
  return 0;
}

```

## disassembly

```asm
0x180021710  mov     r10, [rcx]
0x180021713  mov     rax, [rcx+8]
0x180021717  mov     r9, [rcx+10h]
0x18002171b  sub     rax, r10
0x18002171e  sub     rax, r9
0x180021721  cmp     rax, rdx
0x180021724  jnb     short loc_18002172D
0x180021726  mov     eax, 0C0E90003h
0x18002172b  retn
0x18002172d  lea     rax, [r10+r9]
0x180021731  mov     [r8], rax
0x180021734  lea     rax, [r9+rdx]
0x180021738  mov     [rcx+10h], rax
0x18002173c  xor     eax, eax
0x18002173e  retn
```
