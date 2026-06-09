# WinNatCompareTransportAndSockAddr

- ea: `0x1400061d0`
- end: `0x140006233`
- name: `WinNatCompareTransportAndSockAddr`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004a80`
- `0x14001b50c`

## callees

- `0x1400061d0`
- `0x14001f020`

## pseudocode

```c
bool __fastcall WinNatCompareTransportAndSockAddr(_WORD *a1, _WORD *a2, char a3)
{
  __int64 v3; // rax
  size_t v4; // r8

  if ( *a2 != *a1 || !a3 && a2[1] != a1[1] )
    return 0;
  v3 = 2;
  v4 = 4;
  if ( *a1 != 2 )
    v4 = 16;
  if ( *a2 != 2 )
    v3 = 4;
  return memcmp(&a2[v3], a1 + 2, v4) == 0;
}

```

## disassembly

```asm
0x1400061d0  sub     rsp, 28h
0x1400061d4  mov     r9, rdx
0x1400061d7  movzx   edx, word ptr [rcx]
0x1400061da  movzx   r10d, word ptr [r9]
0x1400061de  cmp     r10w, dx
0x1400061e2  jnz     short loc_14000622F
0x1400061e4  test    r8b, r8b
0x1400061e7  jnz     short loc_1400061F4
0x1400061e9  movzx   eax, word ptr [rcx+2]
0x1400061ed  cmp     [r9+2], ax
0x1400061f2  jnz     short loc_14000622F
0x1400061f4  cmp     dx, 2
0x1400061f8  mov     eax, 4
0x1400061fd  mov     r8d, eax
0x140006200  lea     rdx, [rcx+4]; Buf2
0x140006204  mov     r11d, 10h
0x14000620a  mov     ecx, 8
0x14000620f  cmovnz  r8d, r11d; Size
0x140006213  cmp     r10w, 2
0x140006218  cmovnz  eax, ecx
0x14000621b  lea     rcx, [r9+rax]; Buf1
0x14000621f  call    memcmp
0x140006224  test    eax, eax
0x140006226  setz    al
0x140006229  add     rsp, 28h
0x14000622d  retn
0x14000622f  xor     al, al
0x140006231  jmp     short loc_140006229
```
