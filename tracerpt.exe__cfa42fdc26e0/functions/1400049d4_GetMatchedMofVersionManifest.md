# GetMatchedMofVersionManifest

- ea: `0x1400049d4`
- end: `0x140004af4`
- name: `GetMatchedMofVersionManifest`
- size: `288`
- prototype: `__int64 __fastcall(struct _EVENT_RECORD *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004f08`

## callees

- `0x1400049d4`
- `0x1400053b4`

## pseudocode

```c
__int64 __fastcall GetMatchedMofVersionManifest(struct _EVENT_RECORD *a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v5; // r10
  _QWORD *v6; // r11
  _QWORD *v7; // r9
  __int16 v8; // dx
  __int64 v9; // rbx
  __int64 MofVersionFromTDHGetEvent; // rax

  v5 = 0;
  v6 = (_QWORD *)(a2 + 16 * (*(unsigned __int8 *)(a3 + 2) + 4LL));
  v7 = (_QWORD *)*v6;
  if ( v6 == (_QWORD *)*v6 )
    return v5;
  do
  {
    v8 = *((_WORD *)v7 + 12);
    if ( v8 != *(_WORD *)a3 || *((_BYTE *)v7 + 26) != *(_BYTE *)(a3 + 2) )
    {
      if ( v8 == -1 && *((_BYTE *)v7 + 26) == 0xFF )
        v5 = (__int64)v7;
      goto LABEL_15;
    }
    v5 = (__int64)v7;
    if ( a4 )
      *((_BYTE *)v7 + 40) = 1;
    if ( *((_WORD *)v7 + 15) == *(_WORD *)(a3 + 6)
      && *((_BYTE *)v7 + 29) == *(_BYTE *)(a3 + 5)
      && *((_BYTE *)v7 + 28) == *(_BYTE *)(a3 + 4)
      && *((_BYTE *)v7 + 27) == *(_BYTE *)(a3 + 3)
      && v7[4] == *(_QWORD *)(a3 + 8) )
    {
      break;
    }
LABEL_15:
    v7 = (_QWORD *)*v7;
  }
  while ( v6 != v7 );
  if ( v5
    && (*(_WORD *)(v5 + 24) != 0xFFFF || *(_BYTE *)(v5 + 29) != 0xFF || *(_BYTE *)(v5 + 26) != 0xFF)
    && (*(_WORD *)(v5 + 30) != *(_WORD *)(a3 + 6)
     || *(_BYTE *)(v5 + 29) != *(_BYTE *)(a3 + 5)
     || *(_BYTE *)(v5 + 28) != *(_BYTE *)(a3 + 4)
     || *(_BYTE *)(v5 + 27) != *(_BYTE *)(a3 + 3)
     || *(_QWORD *)(v5 + 32) != *(_QWORD *)(a3 + 8)) )
  {
    v9 = v5;
    MofVersionFromTDHGetEvent = GetMofVersionFromTDHGetEvent(a1);
    v5 = MofVersionFromTDHGetEvent;
    if ( MofVersionFromTDHGetEvent )
    {
      if ( *(_BYTE *)(v9 + 40) )
        *(_BYTE *)(MofVersionFromTDHGetEvent + 40) = 1;
    }
    else
    {
      return v9;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400049d4  push    rbx
0x1400049d6  push    rsi
0x1400049d7  push    rdi
0x1400049d8  push    r14
0x1400049da  sub     rsp, 28h
0x1400049de  movzx   r11d, byte ptr [r8+2]
0x1400049e3  mov     bl, r9b
0x1400049e6  add     r11, 4
0x1400049ea  xor     r10d, r10d
0x1400049ed  shl     r11, 4
0x1400049f1  mov     rdi, rdx
0x1400049f4  add     r11, rdx
0x1400049f7  mov     r9, [r11]
0x1400049fa  cmp     r11, r9
0x1400049fd  jz      loc_140004AE7
0x140004a03  mov     r14d, 0FFFFh
0x140004a09  movzx   edx, word ptr [r9+18h]
0x140004a0e  cmp     dx, [r8]
0x140004a12  jnz     short loc_140004A60
0x140004a14  mov     al, [r8+2]
0x140004a18  cmp     [r9+1Ah], al
0x140004a1c  jnz     short loc_140004A60
0x140004a1e  mov     r10, r9
0x140004a21  test    bl, bl
0x140004a23  jz      short loc_140004A2A
0x140004a25  mov     byte ptr [r9+28h], 1
0x140004a2a  movzx   eax, word ptr [r8+6]
0x140004a2f  cmp     [r9+1Eh], ax
0x140004a34  jnz     short loc_140004A6F
0x140004a36  mov     al, [r8+5]
0x140004a3a  cmp     [r9+1Dh], al
0x140004a3e  jnz     short loc_140004A6F
0x140004a40  mov     al, [r8+4]
0x140004a44  cmp     [r9+1Ch], al
0x140004a48  jnz     short loc_140004A6F
0x140004a4a  mov     al, [r8+3]
0x140004a4e  cmp     [r9+1Bh], al
0x140004a52  jnz     short loc_140004A6F
0x140004a54  mov     rax, [r8+8]
0x140004a58  cmp     [r9+20h], rax
0x140004a5c  jz      short loc_140004A77
0x140004a5e  jmp     short loc_140004A6F
0x140004a60  cmp     r14w, dx
0x140004a64  jnz     short loc_140004A6F
0x140004a66  cmp     byte ptr [r9+1Ah], 0FFh
0x140004a6b  cmovz   r10, r9
0x140004a6f  mov     r9, [r9]
0x140004a72  cmp     r11, r9
0x140004a75  jnz     short loc_140004A09
0x140004a77  test    r10, r10
0x140004a7a  jz      short loc_140004AE7
0x140004a7c  cmp     r14w, [r10+18h]
0x140004a81  jnz     short loc_140004A91
0x140004a83  cmp     byte ptr [r10+1Dh], 0FFh
0x140004a88  jnz     short loc_140004A91
0x140004a8a  cmp     byte ptr [r10+1Ah], 0FFh
0x140004a8f  jz      short loc_140004AE7
0x140004a91  movzx   eax, word ptr [r8+6]
0x140004a96  cmp     [r10+1Eh], ax
0x140004a9b  jnz     short loc_140004AC5
0x140004a9d  mov     al, [r8+5]
0x140004aa1  cmp     [r10+1Dh], al
0x140004aa5  jnz     short loc_140004AC5
0x140004aa7  mov     al, [r8+4]
0x140004aab  cmp     [r10+1Ch], al
0x140004aaf  jnz     short loc_140004AC5
0x140004ab1  mov     al, [r8+3]
0x140004ab5  cmp     [r10+1Bh], al
0x140004ab9  jnz     short loc_140004AC5
0x140004abb  mov     rax, [r8+8]
0x140004abf  cmp     [r10+20h], rax
0x140004ac3  jz      short loc_140004AE7
0x140004ac5  mov     rdx, rdi
0x140004ac8  mov     rbx, r10
0x140004acb  call    GetMofVersionFromTDHGetEvent
0x140004ad0  mov     r10, rax
0x140004ad3  test    rax, rax
0x140004ad6  jz      short loc_140004AE4
0x140004ad8  cmp     byte ptr [rbx+28h], 0
0x140004adc  jz      short loc_140004AE7
0x140004ade  mov     byte ptr [rax+28h], 1
0x140004ae2  jmp     short loc_140004AE7
0x140004ae4  mov     r10, rbx
0x140004ae7  mov     rax, r10
0x140004aea  add     rsp, 28h
0x140004aee  pop     r14
0x140004af0  pop     rdi
0x140004af1  pop     rsi
0x140004af2  pop     rbx
0x140004af3  retn
```
