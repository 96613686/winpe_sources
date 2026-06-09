# ReadImagePlaneHeader

- ea: `0x18002d9a0`
- end: `0x18002dcd5`
- name: `ReadImagePlaneHeader`
- size: `821`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007400`
- `0x1800102e0`
- `0x1800108a8`

## callees

- `0x18002d908`
- `0x18002d9a0`
- `0x18002dcdc`

## pseudocode

```c
__int64 __fastcall ReadImagePlaneHeader(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int Bit32_SB; // eax
  int v9; // ecx
  int v10; // edx
  bool v11; // zf
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  bool v19; // cc
  _QWORD *v20; // rsi
  int v21; // eax

  Bit32_SB = getBit32_SB(a4, 3);
  *(_DWORD *)(a3 + 8) = Bit32_SB;
  if ( (unsigned int)Bit32_SB > 6 )
    goto LABEL_2;
  v10 = *(_DWORD *)(a1 + 16);
  if ( v10 )
  {
    if ( v10 == 4 || v10 == 6 )
    {
      v11 = v10 == Bit32_SB;
LABEL_9:
      if ( v11 )
        goto LABEL_10;
LABEL_2:
      v9 = -106;
      return (unsigned int)-(v9 != 0);
    }
    if ( v10 != 7 )
    {
      if ( v10 != 8 )
        goto LABEL_2;
      goto LABEL_8;
    }
    if ( *(_DWORD *)(a1 + 20) == 7 || *(_DWORD *)(a1 + 20) == 4 )
    {
LABEL_8:
      v11 = Bit32_SB == 3;
      goto LABEL_9;
    }
    v19 = Bit32_SB <= 3;
  }
  else
  {
    v19 = Bit32_SB <= 0;
  }
  if ( !v19 )
    goto LABEL_2;
LABEL_10:
  *(_DWORD *)(a2 + 8) = Bit32_SB;
  *(_DWORD *)(a3 + 16) = getBit32_SB(a4, 1);
  v12 = getBit32_SB(a4, 4);
  *(_DWORD *)(a2 + 52) = v12;
  if ( v12 >= 4 )
    goto LABEL_2;
  v13 = *(_DWORD *)(a3 + 8);
  if ( !v13 )
  {
    *(_QWORD *)(a3 + 32) = 1;
    goto LABEL_32;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    *(_QWORD *)(a3 + 32) = 3;
    getBit32_SB(a4, 1);
    *(_BYTE *)(a1 + 53) = getBit32_SB(a4, 3);
    getBit32_SB(a4, 1);
    *(_BYTE *)(a1 + 54) = getBit32_SB(a4, 3);
    goto LABEL_32;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    *(_QWORD *)(a3 + 32) = 3;
    getBit32_SB(a4, 1);
    *(_BYTE *)(a1 + 53) = getBit32_SB(a4, 3);
    goto LABEL_29;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    *(_QWORD *)(a3 + 32) = 3;
    getBit32_SB(a4, 4);
    goto LABEL_29;
  }
  v17 = v16 - 1;
  if ( v17 && (v18 = v17 - 1) != 0 )
  {
    if ( v18 == 1 )
    {
      *(_QWORD *)(a3 + 32) = (int)(getBit32_SB(a4, 4) + 1);
LABEL_29:
      getBit32_SB(a4, 4);
    }
  }
  else
  {
    *(_QWORD *)(a3 + 32) = 4;
  }
LABEL_32:
  if ( *(_DWORD *)(a1 + 20) == 2 || *(_DWORD *)(a1 + 20) == 3 || *(_DWORD *)(a1 + 20) == 5 || *(_DWORD *)(a1 + 20) == 6 )
  {
    *(_BYTE *)(a2 + 32856) = getBit32_SB(a4, 8);
  }
  else if ( *(_DWORD *)(a1 + 20) == 7 )
  {
    *(_BYTE *)(a2 + 32856) = getBit32_SB(a4, 8);
    *(_BYTE *)(a2 + 32857) = getBit32_SB(a4, 8);
  }
  *(_DWORD *)(a3 + 76) = 0;
  v20 = (_QWORD *)(a3 + 32);
  if ( (unsigned int)getBit32_SB(a4, 1) == 1 )
    *(_DWORD *)(a3 + 76) += 8 * (unsigned __int8)readQuantizerSB(a3 + 80, a4, *v20);
  else
    ++*(_DWORD *)(a3 + 76);
  v21 = *(_DWORD *)(a3 + 76);
  if ( *(_DWORD *)(a2 + 52) == 3 )
    goto LABEL_57;
  if ( (unsigned int)getBit32_SB(a4, 1) )
  {
    v21 = *(_DWORD *)(a3 + 76) + 2 * ((*(_DWORD *)(a3 + 76) & 1) + 2 * (*(_DWORD *)(a3 + 76) & 0x18));
    *(_DWORD *)(a3 + 76) = v21;
  }
  else
  {
    *(_DWORD *)(a3 + 76) += 512;
    *(_DWORD *)(a3 + 76) += (unsigned int)getBit32_SB(a4, 1) == 1
                          ? 32 * (unsigned __int8)readQuantizerSB(a3 + 96, a4, *v20)
                          : 2;
    v21 = *(_DWORD *)(a3 + 76);
  }
  if ( *(_DWORD *)(a2 + 52) != 2 )
  {
    if ( (unsigned int)getBit32_SB(a4, 1) )
    {
      v21 = *(_DWORD *)(a3 + 76) + 2 * ((*(_DWORD *)(a3 + 76) & 2) + 2 * (*(_DWORD *)(a3 + 76) & 0x60));
      *(_DWORD *)(a3 + 76) = v21;
    }
    else
    {
      *(_DWORD *)(a3 + 76) += 1024;
      if ( (unsigned int)getBit32_SB(a4, 1) == 1 )
        *(_DWORD *)(a3 + 76) += (unsigned __int8)readQuantizerSB(a3 + 112, a4, *v20) << 7;
      else
        *(_DWORD *)(a3 + 76) += 4;
      v21 = *(_DWORD *)(a3 + 76);
    }
  }
  if ( *(_DWORD *)(a2 + 52) == 3 )
  {
LABEL_57:
    v21 |= 0x200u;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 52) != 2 )
      goto LABEL_61;
    v21 |= 0x400u;
  }
  *(_DWORD *)(a3 + 76) = v21;
LABEL_61:
  if ( (v21 & 0x600) != 0 )
  {
    v9 = 0;
    *(_BYTE *)(a4 + 12) = 0;
    *(_DWORD *)(a4 + 16) = 0;
  }
  else
  {
    v9 = -104;
  }
  return (unsigned int)-(v9 != 0);
}

```

## disassembly

```asm
0x18002d9a0  push    rbx
0x18002d9a2  push    rbp
0x18002d9a3  push    rsi
0x18002d9a4  push    rdi
0x18002d9a5  push    r12
0x18002d9a7  push    r13
0x18002d9a9  push    r14
0x18002d9ab  sub     rsp, 20h
0x18002d9af  mov     rbp, rdx
0x18002d9b2  mov     rsi, rcx
0x18002d9b5  mov     r13d, 3
0x18002d9bb  mov     rcx, r9
0x18002d9be  mov     edx, r13d
0x18002d9c1  mov     rdi, r9
0x18002d9c4  mov     rbx, r8
0x18002d9c7  call    getBit32_SB
0x18002d9cc  mov     [rbx+8], eax
0x18002d9cf  cmp     eax, 6
0x18002d9d2  jbe     short loc_18002D9DE
0x18002d9d4  mov     ecx, 0FFFFFF96h
0x18002d9d9  jmp     loc_18002DCBD
0x18002d9de  mov     edx, [rsi+10h]
0x18002d9e1  mov     r12d, 4
0x18002d9e7  mov     ecx, edx
0x18002d9e9  test    edx, edx
0x18002d9eb  jz      loc_18002DAA8
0x18002d9f1  sub     ecx, r12d
0x18002d9f4  jz      loc_18002DAA1
0x18002d9fa  sub     ecx, 2
0x18002d9fd  jz      loc_18002DAA1
0x18002da03  sub     ecx, 1
0x18002da06  jz      short loc_18002DA83
0x18002da08  cmp     ecx, 1
0x18002da0b  jnz     short loc_18002D9D4
0x18002da0d  cmp     eax, r13d
0x18002da10  jnz     short loc_18002D9D4
0x18002da12  mov     r14d, 1
0x18002da18  mov     [rbp+8], eax
0x18002da1b  mov     edx, r14d
0x18002da1e  mov     rcx, rdi
0x18002da21  call    getBit32_SB
0x18002da26  mov     edx, r12d
0x18002da29  mov     [rbx+10h], eax
0x18002da2c  mov     rcx, rdi
0x18002da2f  call    getBit32_SB
0x18002da34  mov     [rbp+34h], eax
0x18002da37  cmp     eax, r12d
0x18002da3a  jge     short loc_18002D9D4
0x18002da3c  mov     ecx, [rbx+8]
0x18002da3f  test    ecx, ecx
0x18002da41  jz      loc_18002DB25
0x18002da47  sub     ecx, r14d
0x18002da4a  jz      loc_18002DAED
0x18002da50  sub     ecx, r14d
0x18002da53  jz      short loc_18002DAC3
0x18002da55  sub     ecx, r14d
0x18002da58  jz      short loc_18002DAB2
0x18002da5a  sub     ecx, r14d
0x18002da5d  jz      short loc_18002DAAC
0x18002da5f  sub     ecx, r14d
0x18002da62  jz      short loc_18002DAAC
0x18002da64  cmp     ecx, r14d
0x18002da67  jnz     loc_18002DB29
0x18002da6d  mov     edx, r12d
0x18002da70  mov     rcx, rdi
0x18002da73  call    getBit32_SB
0x18002da78  add     eax, r14d
0x18002da7b  cdqe
0x18002da7d  mov     [rbx+20h], rax
0x18002da81  jmp     short loc_18002DAE0
0x18002da83  cmp     dword ptr [rsi+14h], 7
0x18002da87  jz      short loc_18002DA0D
0x18002da89  cmp     [rsi+14h], r12d
0x18002da8d  jz      loc_18002DA0D
0x18002da93  cmp     eax, r13d
0x18002da96  jle     loc_18002DA12
0x18002da9c  jmp     loc_18002D9D4
0x18002daa1  cmp     edx, eax
0x18002daa3  jmp     loc_18002DA10
0x18002daa8  cmp     eax, edx
0x18002daaa  jmp     short loc_18002DA96
0x18002daac  mov     [rbx+20h], r12
0x18002dab0  jmp     short loc_18002DB29
0x18002dab2  mov     edx, r12d
0x18002dab5  mov     [rbx+20h], r13
0x18002dab9  mov     rcx, rdi
0x18002dabc  call    getBit32_SB
0x18002dac1  jmp     short loc_18002DAE0
0x18002dac3  mov     edx, r14d
0x18002dac6  mov     [rbx+20h], r13
0x18002daca  mov     rcx, rdi
0x18002dacd  call    getBit32_SB
0x18002dad2  mov     edx, r13d
0x18002dad5  mov     rcx, rdi
0x18002dad8  call    getBit32_SB
0x18002dadd  mov     [rsi+35h], al
0x18002dae0  mov     edx, r12d
0x18002dae3  mov     rcx, rdi
0x18002dae6  call    getBit32_SB
0x18002daeb  jmp     short loc_18002DB29
0x18002daed  mov     edx, r14d
0x18002daf0  mov     [rbx+20h], r13
0x18002daf4  mov     rcx, rdi
0x18002daf7  call    getBit32_SB
0x18002dafc  mov     edx, r13d
0x18002daff  mov     rcx, rdi
0x18002db02  call    getBit32_SB
0x18002db07  mov     edx, r14d
0x18002db0a  mov     [rsi+35h], al
0x18002db0d  mov     rcx, rdi
0x18002db10  call    getBit32_SB
0x18002db15  mov     edx, r13d
0x18002db18  mov     rcx, rdi
0x18002db1b  call    getBit32_SB
0x18002db20  mov     [rsi+36h], al
0x18002db23  jmp     short loc_18002DB29
0x18002db25  mov     [rbx+20h], r14
0x18002db29  mov     ecx, [rsi+14h]
0x18002db2c  sub     ecx, 2
0x18002db2f  jz      short loc_18002DB6D
0x18002db31  sub     ecx, r14d
0x18002db34  jz      short loc_18002DB6D
0x18002db36  sub     ecx, 2
0x18002db39  jz      short loc_18002DB6D
0x18002db3b  sub     ecx, r14d
0x18002db3e  jz      short loc_18002DB6D
0x18002db40  cmp     ecx, r14d
0x18002db43  jnz     short loc_18002DB80
0x18002db45  mov     edx, 8
0x18002db4a  mov     rcx, rdi
0x18002db4d  call    getBit32_SB
0x18002db52  mov     edx, 8
0x18002db57  mov     [rbp+8058h], al
0x18002db5d  mov     rcx, rdi
0x18002db60  call    getBit32_SB
0x18002db65  mov     [rbp+8059h], al
0x18002db6b  jmp     short loc_18002DB80
0x18002db6d  mov     edx, 8
0x18002db72  mov     rcx, rdi
0x18002db75  call    getBit32_SB
0x18002db7a  mov     [rbp+8058h], al
0x18002db80  mov     edx, r14d
0x18002db83  mov     dword ptr [rbx+4Ch], 0
0x18002db8a  mov     rcx, rdi
0x18002db8d  lea     rsi, [rbx+20h]
0x18002db91  call    getBit32_SB
0x18002db96  cmp     eax, r14d
0x18002db99  jnz     short loc_18002DBB5
0x18002db9b  mov     r8, [rsi]
0x18002db9e  lea     rcx, [rbx+50h]
0x18002dba2  mov     rdx, rdi
0x18002dba5  call    readQuantizerSB
0x18002dbaa  movzx   eax, al
0x18002dbad  shl     eax, 3
0x18002dbb0  add     [rbx+4Ch], eax
0x18002dbb3  jmp     short loc_18002DBB9
0x18002dbb5  add     [rbx+4Ch], r14d
0x18002dbb9  mov     eax, [rbx+4Ch]
0x18002dbbc  cmp     [rbp+34h], r13d
0x18002dbc0  jz      loc_18002DC94
0x18002dbc6  mov     edx, r14d
0x18002dbc9  mov     rcx, rdi
0x18002dbcc  call    getBit32_SB
0x18002dbd1  mov     edx, [rbx+4Ch]
0x18002dbd4  test    eax, eax
0x18002dbd6  jnz     short loc_18002DC14
0x18002dbd8  lea     eax, [rdx+200h]
0x18002dbde  mov     rcx, rdi
0x18002dbe1  mov     edx, r14d
0x18002dbe4  mov     [rbx+4Ch], eax
0x18002dbe7  call    getBit32_SB
0x18002dbec  cmp     eax, r14d
0x18002dbef  jnz     short loc_18002DC0B
0x18002dbf1  mov     r8, [rsi]
0x18002dbf4  lea     rcx, [rbx+60h]
0x18002dbf8  mov     rdx, rdi
0x18002dbfb  call    readQuantizerSB
0x18002dc00  movzx   eax, al
0x18002dc03  shl     eax, 5
0x18002dc06  add     [rbx+4Ch], eax
0x18002dc09  jmp     short loc_18002DC0F
0x18002dc0b  add     dword ptr [rbx+4Ch], 2
0x18002dc0f  mov     eax, [rbx+4Ch]
0x18002dc12  jmp     short loc_18002DC27
0x18002dc14  mov     ecx, edx
0x18002dc16  mov     eax, edx
0x18002dc18  and     ecx, 18h
0x18002dc1b  and     eax, r14d
0x18002dc1e  lea     eax, [rax+rcx*2]
0x18002dc21  lea     eax, [rdx+rax*2]
0x18002dc24  mov     [rbx+4Ch], eax
0x18002dc27  cmp     dword ptr [rbp+34h], 2
0x18002dc2b  jz      short loc_18002DC8E
0x18002dc2d  mov     edx, r14d
0x18002dc30  mov     rcx, rdi
0x18002dc33  call    getBit32_SB
0x18002dc38  mov     edx, [rbx+4Ch]
0x18002dc3b  test    eax, eax
0x18002dc3d  jnz     short loc_18002DC7B
0x18002dc3f  lea     eax, [rdx+400h]
0x18002dc45  mov     rcx, rdi
0x18002dc48  mov     edx, r14d
0x18002dc4b  mov     [rbx+4Ch], eax
0x18002dc4e  call    getBit32_SB
0x18002dc53  cmp     eax, r14d
0x18002dc56  jnz     short loc_18002DC72
0x18002dc58  mov     r8, [rsi]
0x18002dc5b  lea     rcx, [rbx+70h]
0x18002dc5f  mov     rdx, rdi
0x18002dc62  call    readQuantizerSB
0x18002dc67  movzx   eax, al
0x18002dc6a  shl     eax, 7
0x18002dc6d  add     [rbx+4Ch], eax
0x18002dc70  jmp     short loc_18002DC76
0x18002dc72  add     [rbx+4Ch], r12d
0x18002dc76  mov     eax, [rbx+4Ch]
0x18002dc79  jmp     short loc_18002DC8E
0x18002dc7b  mov     ecx, edx
0x18002dc7d  mov     eax, edx
0x18002dc7f  and     ecx, 60h
0x18002dc82  and     eax, 2
0x18002dc85  lea     eax, [rax+rcx*2]
0x18002dc88  lea     eax, [rdx+rax*2]
0x18002dc8b  mov     [rbx+4Ch], eax
0x18002dc8e  cmp     [rbp+34h], r13d
0x18002dc92  jnz     short loc_18002DC9A
0x18002dc94  bts     eax, 9
0x18002dc98  jmp     short loc_18002DCA4
0x18002dc9a  cmp     dword ptr [rbp+34h], 2
0x18002dc9e  jnz     short loc_18002DCA7
0x18002dca0  bts     eax, 0Ah
0x18002dca4  mov     [rbx+4Ch], eax
0x18002dca7  test    eax, 600h
0x18002dcac  jnz     short loc_18002DCB5
0x18002dcae  mov     ecx, 0FFFFFF98h
0x18002dcb3  jmp     short loc_18002DCBD
0x18002dcb5  xor     ecx, ecx
0x18002dcb7  mov     [rdi+0Ch], cl
0x18002dcba  mov     [rdi+10h], ecx
0x18002dcbd  xor     eax, eax
0x18002dcbf  sub     eax, ecx
0x18002dcc1  neg     eax
0x18002dcc3  sbb     eax, eax
0x18002dcc5  add     rsp, 20h
0x18002dcc9  pop     r14
0x18002dccb  pop     r13
0x18002dccd  pop     r12
0x18002dccf  pop     rdi
0x18002dcd0  pop     rsi
0x18002dcd1  pop     rbp
0x18002dcd2  pop     rbx
0x18002dcd3  retn
```
