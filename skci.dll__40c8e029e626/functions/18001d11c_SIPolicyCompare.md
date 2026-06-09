# SIPolicyCompare

- ea: `0x18001d11c`
- end: `0x18001d153`
- name: `SIPolicyCompare`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800492f8`

## callees

- `0x18001d11c`
- `0x18003391a`

## pseudocode

```c
bool __fastcall SIPolicyCompare(__int64 a1, __int64 a2)
{
  unsigned int v2; // eax

  v2 = *(_DWORD *)(a1 + 144);
  return v2 == *(_DWORD *)(a2 + 144) && memcmp_0(*(const void **)(a1 + 136), *(const void **)(a2 + 136), v2) == 0;
}

```

## disassembly

```asm
0x18001d11c  sub     rsp, 28h
0x18001d120  mov     eax, [rcx+90h]
0x18001d126  cmp     eax, [rdx+90h]
0x18001d12c  jnz     short loc_18001D14B
0x18001d12e  mov     rdx, [rdx+88h]; Buf2
0x18001d135  mov     r8d, eax; Size
0x18001d138  mov     rcx, [rcx+88h]; Buf1
0x18001d13f  call    memcmp_0
0x18001d144  test    eax, eax
0x18001d146  setz    al
0x18001d149  jmp     short loc_18001D14D
0x18001d14b  xor     al, al
0x18001d14d  add     rsp, 28h
0x18001d151  retn
```
