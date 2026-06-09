# GetTableOffset

- ea: `0x180002a80`
- end: `0x180002b22`
- name: `GetTableOffset`
- size: `162`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f60`
- `0x18000291c`
- `0x180004320`
- `0x18000bde0`
- `0x18002a15c`

## callees

- `0x180002a80`

## pseudocode

```c
__int64 __fastcall GetTableOffset(__int64 a1, int a2)
{
  int i; // eax
  __int64 v4; // r11
  unsigned int v5; // edx

  for ( i = 0; i < ((unsigned __int16)(*(_WORD *)(a1 + 4) << 8) | HIBYTE(*(unsigned __int16 *)(a1 + 4))); ++i )
  {
    v4 = 16 * i;
    v5 = (unsigned __int16)HIWORD(*(_DWORD *)(v4 + a1 + 12));
    if ( ((unsigned __int16)((_WORD)v5 << 8)
        | (v5 >> 8)
        | (((unsigned __int16)((unsigned __int16)*(_DWORD *)(v4 + a1 + 12) << 8) | BYTE1(*(_DWORD *)(v4 + a1 + 12))) << 16)) == a2 )
      return HIBYTE(*(_DWORD *)(v4 + a1 + 20))
           | ((unsigned __int16)__ROR2__(*(_DWORD *)(v4 + a1 + 20), 8) << 16)
           | (unsigned int)(unsigned __int16)(HIWORD(*(_DWORD *)(v4 + a1 + 20)) << 8);
  }
  return 0;
}

```

## disassembly

```asm
0x180002a80  push    rbx
0x180002a82  push    rsi
0x180002a83  push    rdi
0x180002a84  movzx   eax, word ptr [rcx+4]
0x180002a88  xor     esi, esi
0x180002a8a  mov     r10d, eax
0x180002a8d  mov     edi, edx
0x180002a8f  shl     ax, 8
0x180002a93  mov     rbx, rcx
0x180002a96  movzx   eax, ax
0x180002a99  shr     r10d, 8
0x180002a9d  or      r10d, eax
0x180002aa0  xor     eax, eax
0x180002aa2  cmp     eax, r10d
0x180002aa5  jge     short loc_180002B1E
0x180002aa7  mov     ecx, eax
0x180002aa9  shl     ecx, 4
0x180002aac  movsxd  r11, ecx
0x180002aaf  mov     edx, [r11+rbx+0Ch]
0x180002ab4  mov     ecx, edx
0x180002ab6  sar     ecx, 10h
0x180002ab9  movzx   r8d, cx
0x180002abd  movzx   ecx, dx
0x180002ac0  mov     edx, r8d
0x180002ac3  mov     r9d, ecx
0x180002ac6  shl     r8w, 8
0x180002acb  shr     r9d, 8
0x180002acf  shl     cx, 8
0x180002ad3  movzx   ecx, cx
0x180002ad6  or      r9d, ecx
0x180002ad9  shr     edx, 8
0x180002adc  shl     r9d, 10h
0x180002ae0  movzx   ecx, r8w
0x180002ae4  or      edx, ecx
0x180002ae6  or      r9d, edx
0x180002ae9  cmp     r9d, edi
0x180002aec  jz      short loc_180002AF2
0x180002aee  inc     eax
0x180002af0  jmp     short loc_180002AA2
0x180002af2  mov     ecx, [r11+rbx+14h]
0x180002af7  mov     eax, ecx
0x180002af9  shr     eax, 10h
0x180002afc  mov     edx, eax
0x180002afe  ror     cx, 8
0x180002b02  shr     eax, 8
0x180002b05  shl     dx, 8
0x180002b09  movzx   r8d, cx
0x180002b0d  shl     r8d, 10h
0x180002b11  or      r8d, eax
0x180002b14  movzx   eax, dx
0x180002b17  or      eax, r8d
0x180002b1a  pop     rdi
0x180002b1b  pop     rsi
0x180002b1c  pop     rbx
0x180002b1d  retn
0x180002b1e  mov     eax, esi
0x180002b20  jmp     short loc_180002B1A
```
