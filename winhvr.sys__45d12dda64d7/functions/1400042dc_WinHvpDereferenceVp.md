# WinHvpDereferenceVp

- ea: `0x1400042dc`
- end: `0x140004310`
- name: `WinHvpDereferenceVp`
- size: `52`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140004270`
- `0x1400096b0`
- `0x14000b060`
- `0x1400226bc`
- `0x140023ba0`
- `0x140023c00`
- `0x14002648c`

## callees

- `0x1400042dc`
- `0x14000b040`

## pseudocode

```c
void __fastcall WinHvpDereferenceVp(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // zf
  bool v3; // sf
  bool v4; // of
  signed __int64 v5; // rax

  v1 = _InterlockedExchangeAdd64(a1 + 2, 0xFFFFFFFFFFFFFFFFuLL);
  v4 = __OFSUB__(v1, 1);
  v2 = v1 == 1;
  v3 = v1 - 1 < 0;
  v5 = v1 - 1;
  if ( v3 ^ v4 | v2 )
  {
    if ( v5 )
      __fastfail(0xEu);
    WinHvpFreePoolWithTag((void *)a1, 0x57764857u);
  }
}

```

## disassembly

```asm
0x1400042dc  sub     rsp, 28h
0x1400042e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400042e4  lock xadd [rcx+10h], rax
0x1400042ea  sub     rax, 1
0x1400042ee  jle     short loc_1400042F6
0x1400042f0  add     rsp, 28h
0x1400042f4  retn
0x1400042f6  test    rax, rax
0x1400042f9  jnz     short loc_140004307
0x1400042fb  mov     edx, 57764857h
0x140004300  call    WinHvpFreePoolWithTag
0x140004305  jmp     short loc_1400042F0
0x140004307  mov     ecx, 0Eh
0x14000430c  int     29h; Win8: RtlFailFast(ecx)
0x14000430e  jmp     short loc_1400042F0
```
