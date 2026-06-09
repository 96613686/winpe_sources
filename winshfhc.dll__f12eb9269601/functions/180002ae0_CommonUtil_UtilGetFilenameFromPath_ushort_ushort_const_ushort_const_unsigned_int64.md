# CommonUtil::UtilGetFilenameFromPath<ushort>(ushort const *,ushort const * *,unsigned __int64 *)

- ea: `0x180002ae0`
- end: `0x180002cfa`
- name: `??$UtilGetFilenameFromPath@G@CommonUtil@@YAJPEBGPEAPEBGPEA_K@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800019e0`

## callees

- `0x180002ae0`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFilenameFromPath<unsigned short>(_WORD *a1, _QWORD *a2)
{
  bool v3; // zf
  char v5; // bl
  __int64 v6; // r9
  __int16 v7; // ax
  __int16 v8; // cx
  unsigned __int64 v9; // r11
  __int64 v10; // rdx
  unsigned __int64 v11; // r10
  unsigned __int64 v12; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx

  v3 = *a1 == 47;
  *a2 = 0;
  v5 = 0;
  v6 = 0;
  if ( !v3 && *a1 != 92 || a1[1] != 47 && a1[1] != 92 )
    goto LABEL_28;
  v7 = a1[2];
  if ( v7 == 46 )
  {
    if ( a1[3] == 47 || a1[3] == 92 )
    {
      v6 = 4;
      goto LABEL_28;
    }
    goto LABEL_26;
  }
  if ( v7 != 63 )
  {
    if ( v7 == 47 || v7 == 92 )
      goto LABEL_28;
LABEL_26:
    v6 = 2;
LABEL_27:
    v5 = 1;
    goto LABEL_28;
  }
  if ( a1[3] != 47 && a1[3] != 92 )
    goto LABEL_26;
  v8 = a1[4];
  if ( ((v8 - 85) & 0xFFDF) == 0 && ((a1[5] - 78) & 0xFFDF) == 0 && ((a1[6] - 67) & 0xFFDF) == 0 )
  {
    if ( a1[7] != 47 && a1[7] != 92 )
      return 2147942402LL;
    v6 = 8;
    goto LABEL_27;
  }
  if ( (unsigned __int16)(v8 - 97) > 0x19u && (unsigned __int16)(v8 - 65) > 0x19u )
    return 2147942402LL;
  if ( a1[5] != 58 )
    return 2147942402LL;
  v6 = 4;
  if ( a1[6] != 47 && a1[6] != 92 )
    return 2147942402LL;
LABEL_28:
  v9 = 0;
  v10 = v6;
  v11 = v6;
  v12 = v6;
  if ( !a1[v6] )
    goto LABEL_41;
  while ( 1 )
  {
    if ( a1[v11] == 47 || a1[v11] == 92 )
    {
      while ( 1 )
      {
        v10 = v12 + 1;
        if ( a1[v12 + 1] != 47 && a1[v10] != 92 )
          break;
        ++v12;
      }
      goto LABEL_39;
    }
    if ( a1[v11] == 58 )
      break;
LABEL_40:
    v11 = v12 + 1;
    v12 = v11;
    if ( !a1[v11] )
      goto LABEL_41;
  }
  if ( v12 - v6 == 1 )
  {
    while ( 1 )
    {
      v10 = v12 + 1;
      if ( a1[v12 + 1] != 47 && a1[v10] != 92 )
        break;
      ++v12;
    }
LABEL_39:
    ++v9;
    goto LABEL_40;
  }
  if ( a1[v11 + 1] == 47 && a1[v11 + 2] == 47 )
    return 2147500033LL;
LABEL_41:
  if ( v12 > 0x104 && !v6 )
    return 2147942561LL;
  if ( v5 && v9 < 2 )
    return 2147942402LL;
  v14 = v12 - v10;
  if ( v14 > 2 )
    goto LABEL_55;
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_53;
  if ( v15 != 1 )
    return 2147942402LL;
  if ( a1[v10 + 1] == 46 )
  {
LABEL_53:
    if ( a1[v10] == 46 )
      return 2147942402LL;
  }
LABEL_55:
  v3 = a1[v11] == 0;
  *a2 = &a1[v10];
  return !v3;
}

```

## disassembly

```asm
0x180002ae0  mov     [rsp+arg_0], rbx
0x180002ae5  mov     [rsp+arg_10], r8
0x180002aea  push    rdi
0x180002aeb  push    r14
0x180002aed  xor     r14d, r14d
0x180002af0  mov     rdi, rdx
0x180002af3  cmp     word ptr [rcx], 2Fh ; '/'
0x180002af7  mov     r8, rcx
0x180002afa  mov     [rdx], r14
0x180002afd  mov     bl, r14b
0x180002b00  mov     r9d, r14d
0x180002b03  jz      short loc_180002B0F
0x180002b05  cmp     word ptr [rcx], 5Ch ; '\'
0x180002b09  jnz     loc_180002BFF
0x180002b0f  cmp     word ptr [rcx+2], 2Fh ; '/'
0x180002b14  jz      short loc_180002B21
0x180002b16  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180002b1b  jnz     loc_180002BFF
0x180002b21  movzx   eax, word ptr [rcx+4]
0x180002b25  cmp     ax, 2Eh ; '.'
0x180002b29  jnz     short loc_180002B48
0x180002b2b  cmp     word ptr [rcx+6], 2Fh ; '/'
0x180002b30  jz      short loc_180002B3D
0x180002b32  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180002b37  jnz     loc_180002BF7
0x180002b3d  mov     r9d, 4
0x180002b43  jmp     loc_180002BFF
0x180002b48  cmp     ax, 3Fh ; '?'
0x180002b4c  jnz     loc_180002BEB
0x180002b52  cmp     word ptr [rcx+6], 2Fh ; '/'
0x180002b57  jz      short loc_180002B64
0x180002b59  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180002b5e  jnz     loc_180002BF7
0x180002b64  movzx   ecx, word ptr [rcx+8]
0x180002b68  mov     edx, 0FFDFh
0x180002b6d  lea     eax, [rcx-55h]
0x180002b70  test    dx, ax
0x180002b73  jnz     short loc_180002BAD
0x180002b75  movzx   eax, word ptr [r8+0Ah]
0x180002b7a  sub     ax, 4Eh ; 'N'
0x180002b7e  test    dx, ax
0x180002b81  jnz     short loc_180002BAD
0x180002b83  movzx   eax, word ptr [r8+0Ch]
0x180002b88  sub     ax, 43h ; 'C'
0x180002b8c  test    dx, ax
0x180002b8f  jnz     short loc_180002BAD
0x180002b91  cmp     word ptr [r8+0Eh], 2Fh ; '/'
0x180002b97  jz      short loc_180002BA5
0x180002b99  cmp     word ptr [r8+0Eh], 5Ch ; '\'
0x180002b9f  jnz     loc_180002CD7
0x180002ba5  mov     r9d, 8
0x180002bab  jmp     short loc_180002BFD
0x180002bad  lea     eax, [rcx-61h]
0x180002bb0  cmp     ax, 19h
0x180002bb4  jbe     short loc_180002BC4
0x180002bb6  sub     cx, 41h ; 'A'
0x180002bba  cmp     cx, 19h
0x180002bbe  ja      loc_180002CD7
0x180002bc4  cmp     word ptr [r8+0Ah], 3Ah ; ':'
0x180002bca  jnz     loc_180002CD7
0x180002bd0  cmp     word ptr [r8+0Ch], 2Fh ; '/'
0x180002bd6  mov     r9d, 4
0x180002bdc  jz      short loc_180002BFF
0x180002bde  cmp     word ptr [r8+0Ch], 5Ch ; '\'
0x180002be4  jz      short loc_180002BFF
0x180002be6  jmp     loc_180002CD7
0x180002beb  cmp     ax, 2Fh ; '/'
0x180002bef  jz      short loc_180002BFF
0x180002bf1  cmp     ax, 5Ch ; '\'
0x180002bf5  jz      short loc_180002BFF
0x180002bf7  mov     r9d, 2
0x180002bfd  mov     bl, 1
0x180002bff  mov     r11, r14
0x180002c02  mov     rdx, r9
0x180002c05  mov     r10, r9
0x180002c08  mov     rcx, r9
0x180002c0b  cmp     [r8+r9*2], r14w
0x180002c10  jz      short loc_180002C79
0x180002c12  cmp     word ptr [r8+r10*2], 2Fh ; '/'
0x180002c18  jz      short loc_180002C4F
0x180002c1a  cmp     word ptr [r8+r10*2], 5Ch ; '\'
0x180002c20  jz      short loc_180002C4F
0x180002c22  cmp     word ptr [r8+r10*2], 3Ah ; ':'
0x180002c28  jnz     short loc_180002C6B
0x180002c2a  mov     rax, rcx
0x180002c2d  sub     rax, r9
0x180002c30  cmp     rax, 1
0x180002c34  jnz     short loc_180002C8E
0x180002c36  lea     rdx, [rcx+1]
0x180002c3a  cmp     word ptr [r8+rdx*2], 2Fh ; '/'
0x180002c40  jz      short loc_180002C4A
0x180002c42  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x180002c48  jnz     short loc_180002C68
0x180002c4a  mov     rcx, rdx
0x180002c4d  jmp     short loc_180002C36
0x180002c4f  lea     rdx, [rcx+1]
0x180002c53  cmp     word ptr [r8+rdx*2], 2Fh ; '/'
0x180002c59  jz      short loc_180002C63
0x180002c5b  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x180002c61  jnz     short loc_180002C68
0x180002c63  mov     rcx, rdx
0x180002c66  jmp     short loc_180002C4F
0x180002c68  inc     r11
0x180002c6b  lea     r10, [rcx+1]
0x180002c6f  mov     rcx, r10
0x180002c72  cmp     [r8+r10*2], r14w
0x180002c77  jnz     short loc_180002C12
0x180002c79  cmp     rcx, 104h
0x180002c80  jbe     short loc_180002CA7
0x180002c82  test    r9, r9
0x180002c85  jnz     short loc_180002CA7
0x180002c87  mov     eax, 800700A1h
0x180002c8c  jmp     short loc_180002CF0
0x180002c8e  cmp     word ptr [r8+r10*2+2], 2Fh ; '/'
0x180002c95  jnz     short loc_180002C79
0x180002c97  cmp     word ptr [r8+r10*2+4], 2Fh ; '/'
0x180002c9e  jnz     short loc_180002C79
0x180002ca0  mov     eax, 80004001h
0x180002ca5  jmp     short loc_180002CF0
0x180002ca7  test    bl, bl
0x180002ca9  jz      short loc_180002CB1
0x180002cab  cmp     r11, 2
0x180002caf  jb      short loc_180002CD7
0x180002cb1  sub     rcx, rdx
0x180002cb4  cmp     rcx, 2
0x180002cb8  ja      short loc_180002CDE
0x180002cba  sub     rcx, 1
0x180002cbe  jz      short loc_180002CCF
0x180002cc0  cmp     rcx, 1
0x180002cc4  jnz     short loc_180002CD7
0x180002cc6  cmp     word ptr [r8+rdx*2+2], 2Eh ; '.'
0x180002ccd  jnz     short loc_180002CDE
0x180002ccf  cmp     word ptr [r8+rdx*2], 2Eh ; '.'
0x180002cd5  jnz     short loc_180002CDE
0x180002cd7  mov     eax, 80070002h
0x180002cdc  jmp     short loc_180002CF0
0x180002cde  cmp     r14w, [r8+r10*2]
0x180002ce3  lea     rax, [r8+rdx*2]
0x180002ce7  mov     [rdi], rax
0x180002cea  mov     eax, r14d
0x180002ced  setnz   al
0x180002cf0  mov     rbx, [rsp+10h+arg_0]
0x180002cf5  pop     r14
0x180002cf7  pop     rdi
0x180002cf8  retn
```
