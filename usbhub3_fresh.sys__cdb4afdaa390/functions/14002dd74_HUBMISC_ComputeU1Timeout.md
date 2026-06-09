# HUBMISC_ComputeU1Timeout

- ea: `0x14002dd74`
- end: `0x14002dfa0`
- name: `HUBMISC_ComputeU1Timeout`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140020d20`

## callees

- `0x14002dd74`

## pseudocode

```c
__int64 __fastcall HUBMISC_ComputeU1Timeout(__int64 *a1)
{
  unsigned __int8 v1; // r9
  bool v3; // cl
  __int64 v4; // rdx
  int v5; // r10d
  char v6; // cl
  unsigned __int16 v7; // si
  _QWORD *v8; // rdi
  char v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rdx
  unsigned int v12; // r11d
  __int64 v13; // r10
  _QWORD *v14; // rdx
  unsigned int v15; // ebp
  __int64 v16; // r11
  _BYTE *v17; // r10
  unsigned __int16 v18; // dx
  unsigned __int16 v19; // dx
  _QWORD *v20; // rax
  __int64 result; // rax

  v1 = 1;
  if ( (*(_DWORD *)(a1[1] + 204) & 0x800) != 0 )
  {
    v3 = (*(_DWORD *)(a1[1] + 204) & 0x400) != 0;
    if ( *((_DWORD *)a1 + 683) == 2 )
      v3 = 0;
  }
  else
  {
    v3 = (*(_DWORD *)(a1[1] + 204) & 0x400) != 0;
  }
  if ( (*((_DWORD *)a1 + 413) & 0x80u) != 0
    || (v4 = *a1, (*(_DWORD *)(*a1 + 40) & 0x8000) != 0)
    || (v5 = *((_DWORD *)a1 + 556), (v5 & 0x140) != 0)
    || (*(_DWORD *)(v4 + 44) & 8) != 0
    || (*(_DWORD *)(v4 + 2512) & 8) != 0
    || v3 )
  {
LABEL_46:
    v1 = 0;
    _InterlockedAnd((volatile signed __int32 *)a1 + 556, 0xFFFFFFEF);
    goto LABEL_47;
  }
  v6 = *((_BYTE *)a1 + 2228);
  *((_DWORD *)a1 + 556) = v5 ^ ((unsigned __int8)v5 ^ (unsigned __int8)(16 * v6)) & 0x10;
  if ( (v6 & 4) == 0 )
  {
    v1 = 0;
    goto LABEL_47;
  }
  if ( (v6 & 0x10) == 0 )
  {
    v1 = -1;
    goto LABEL_47;
  }
  if ( v6 < 0 )
    goto LABEL_47;
  if ( (v6 & 0x40) != 0 )
  {
    v1 = 127;
    goto LABEL_47;
  }
  v7 = 0;
  v8 = (_QWORD *)(a1[6] + 16);
  v9 = 0;
  v10 = *v8 - 8LL;
  v11 = v10;
  if ( v8 != (_QWORD *)*v8 )
  {
    while ( 1 )
    {
      v12 = *(_DWORD *)(v11 + 24);
      v13 = 0;
      if ( v12 )
        break;
LABEL_23:
      v14 = *(_QWORD **)(v11 + 8);
      if ( v8 == v14 )
        goto LABEL_26;
      v11 = (__int64)(v14 - 1);
    }
    while ( (*(_BYTE *)(*(_QWORD *)(v11 + 80 * v13 + 72) + 3LL) & 3) == 0 )
    {
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= v12 )
        goto LABEL_23;
    }
    v9 = 1;
LABEL_26:
    while ( 1 )
    {
      v15 = *(_DWORD *)(v10 + 24);
      v16 = 0;
      if ( v15 )
        break;
LABEL_42:
      v20 = *(_QWORD **)(v10 + 8);
      v10 = (__int64)(v20 - 1);
      if ( v8 == v20 )
        goto LABEL_43;
    }
    while ( 1 )
    {
      v17 = *(_BYTE **)(v10 + 80 * v16 + 72);
      if ( (char)v17[2] >= 0 )
        v18 = *((_WORD *)a1 + 1105);
      else
        v18 = *((unsigned __int8 *)a1 + 2204);
      if ( (v17[3] & 3) != 0 )
      {
        if ( (v17[3] & 3) == 1 )
        {
          if ( v18 > 125 * (unsigned int)(unsigned __int8)v17[6] )
            goto LABEL_46;
          v19 = 1;
          goto LABEL_39;
        }
        if ( (v17[3] & 3u) - 2 < 2 )
        {
LABEL_38:
          v19 = 5 * v18;
          goto LABEL_39;
        }
        v19 = 0;
      }
      else
      {
        if ( !v9 )
          goto LABEL_38;
        v19 = 5;
      }
LABEL_39:
      if ( v7 <= v19 )
        v7 = v19;
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= v15 )
        goto LABEL_42;
    }
  }
LABEL_43:
  v1 = 127;
  if ( (unsigned __int8)v7 < 0x7Fu )
    v1 = v7;
LABEL_47:
  result = *a1;
  if ( (*(_DWORD *)(*a1 + 40) & 0x10000000) != 0 )
  {
    result = *((unsigned int *)a1 + 410);
    if ( (result & 2) != 0 )
    {
      result = v1;
      if ( v1 )
        result = 255;
      v1 = result;
    }
  }
  *((_BYTE *)a1 + 2222) = v1;
  return result;
}

```

## disassembly

```asm
0x14002dd74  push    rbx
0x14002dd76  push    rbp
0x14002dd77  push    rsi
0x14002dd78  push    rdi
0x14002dd79  push    r14
0x14002dd7b  push    r15
0x14002dd7d  mov     rax, [rcx+8]
0x14002dd81  mov     r9d, 1
0x14002dd87  mov     r8, rcx
0x14002dd8a  mov     edx, [rax+0CCh]
0x14002dd90  mov     eax, edx
0x14002dd92  shr     eax, 0Ah
0x14002dd95  and     al, r9b
0x14002dd98  bt      edx, 0Bh
0x14002dd9c  jnb     short loc_14002DDB0
0x14002dd9e  movzx   ecx, al
0x14002dda1  xor     eax, eax
0x14002dda3  cmp     dword ptr [r8+0AACh], 2
0x14002ddab  cmovz   ecx, eax
0x14002ddae  jmp     short loc_14002DDB2
0x14002ddb0  mov     cl, al
0x14002ddb2  mov     eax, [r8+674h]
0x14002ddb9  mov     r15d, 0FFh
0x14002ddbf  test    al, al
0x14002ddc1  js      loc_14002DF5E
0x14002ddc7  mov     rdx, [r8]
0x14002ddca  test    dword ptr [rdx+28h], 8000h
0x14002ddd1  jnz     loc_14002DF5E
0x14002ddd7  mov     r10d, [r8+8B0h]
0x14002ddde  test    r10d, 140h
0x14002dde5  jnz     loc_14002DF5E
0x14002ddeb  mov     eax, [rdx+2Ch]
0x14002ddee  test    al, 8
0x14002ddf0  jnz     loc_14002DF5E
0x14002ddf6  mov     eax, [rdx+9D0h]
0x14002ddfc  test    al, 8
0x14002ddfe  jnz     loc_14002DF5E
0x14002de04  cmp     cl, r9b
0x14002de07  jz      loc_14002DF5E
0x14002de0d  movzx   ecx, byte ptr [r8+8B4h]
0x14002de15  mov     eax, ecx
0x14002de17  shl     eax, 4
0x14002de1a  xor     eax, r10d
0x14002de1d  and     eax, 10h
0x14002de20  xor     eax, r10d
0x14002de23  mov     [r8+8B0h], eax
0x14002de2a  test    cl, 4
0x14002de2d  jnz     short loc_14002DE37
0x14002de2f  xor     r9b, r9b
0x14002de32  jmp     loc_14002DF6A
0x14002de37  test    cl, 10h
0x14002de3a  jnz     short loc_14002DE44
0x14002de3c  mov     r9b, r15b
0x14002de3f  jmp     loc_14002DF6A
0x14002de44  test    cl, cl
0x14002de46  js      loc_14002DF6A
0x14002de4c  test    cl, 40h
0x14002de4f  jz      short loc_14002DE5C
0x14002de51  mov     r9d, 7Fh
0x14002de57  jmp     loc_14002DF6A
0x14002de5c  mov     rdi, [r8+30h]
0x14002de60  xor     esi, esi
0x14002de62  add     rdi, 10h
0x14002de66  xor     r14b, r14b
0x14002de69  mov     rax, [rdi]
0x14002de6c  lea     rbx, [rax-8]
0x14002de70  mov     rdx, rbx
0x14002de73  cmp     rdi, rax
0x14002de76  jz      loc_14002DF4B
0x14002de7c  mov     r11d, [rdx+18h]
0x14002de80  xor     r10d, r10d
0x14002de83  test    r11d, r11d
0x14002de86  jz      short loc_14002DEA2
0x14002de88  lea     rax, [r10+r10*4]
0x14002de8c  add     rax, rax
0x14002de8f  mov     rax, [rdx+rax*8+48h]
0x14002de94  test    byte ptr [rax+3], 3
0x14002de98  jnz     short loc_14002DEB1
0x14002de9a  add     r10d, r9d
0x14002de9d  cmp     r10d, r11d
0x14002dea0  jb      short loc_14002DE88
0x14002dea2  mov     rdx, [rdx+8]
0x14002dea6  cmp     rdi, rdx
0x14002dea9  jz      short loc_14002DEB4
0x14002deab  add     rdx, 0FFFFFFFFFFFFFFF8h
0x14002deaf  jmp     short loc_14002DE7C
0x14002deb1  mov     r14b, r9b
0x14002deb4  mov     ebp, [rbx+18h]
0x14002deb7  xor     r11d, r11d
0x14002deba  test    ebp, ebp
0x14002debc  jz      short loc_14002DF3A
0x14002debe  lea     rcx, [r11+r11*4]
0x14002dec2  add     rcx, rcx
0x14002dec5  mov     r10, [rbx+rcx*8+48h]
0x14002deca  cmp     byte ptr [r10+2], 0
0x14002decf  jge     short loc_14002DEDB
0x14002ded1  movzx   edx, byte ptr [r8+89Ch]
0x14002ded9  jmp     short loc_14002DEE3
0x14002dedb  movzx   edx, word ptr [r8+8A2h]
0x14002dee3  movzx   ecx, byte ptr [r10+3]
0x14002dee8  and     ecx, 3
0x14002deeb  jz      short loc_14002DF15
0x14002deed  sub     ecx, r9d
0x14002def0  jz      short loc_14002DF00
0x14002def2  sub     ecx, r9d
0x14002def5  jz      short loc_14002DF21
0x14002def7  cmp     ecx, r9d
0x14002defa  jz      short loc_14002DF21
0x14002defc  xor     edx, edx
0x14002defe  jmp     short loc_14002DF2B
0x14002df00  movzx   eax, byte ptr [r10+6]
0x14002df05  imul    ecx, eax, 7Dh ; '}'
0x14002df08  movzx   eax, dx
0x14002df0b  cmp     eax, ecx
0x14002df0d  ja      short loc_14002DF5E
0x14002df0f  movzx   edx, r9w
0x14002df13  jmp     short loc_14002DF2B
0x14002df15  test    r14b, r14b
0x14002df18  jz      short loc_14002DF21
0x14002df1a  mov     edx, 5
0x14002df1f  jmp     short loc_14002DF2B
0x14002df21  movzx   eax, dx
0x14002df24  shl     ax, 2
0x14002df28  add     dx, ax
0x14002df2b  cmp     si, dx
0x14002df2e  cmovbe  si, dx
0x14002df32  add     r11d, r9d
0x14002df35  cmp     r11d, ebp
0x14002df38  jb      short loc_14002DEBE
0x14002df3a  mov     rax, [rbx+8]
0x14002df3e  lea     rbx, [rax-8]
0x14002df42  cmp     rdi, rax
0x14002df45  jnz     loc_14002DEB4
0x14002df4b  movzx   eax, sil
0x14002df4f  mov     r9d, 7Fh
0x14002df55  cmp     al, r9b
0x14002df58  cmovb   r9d, eax
0x14002df5c  jmp     short loc_14002DF6A
0x14002df5e  xor     r9b, r9b
0x14002df61  lock and dword ptr [r8+8B0h], 0FFFFFFEFh
0x14002df6a  mov     rax, [r8]
0x14002df6d  test    dword ptr [rax+28h], 10000000h
0x14002df74  jz      short loc_14002DF8F
0x14002df76  mov     eax, [r8+668h]
0x14002df7d  test    al, 2
0x14002df7f  jz      short loc_14002DF8F
0x14002df81  test    r9b, r9b
0x14002df84  movzx   eax, r9b
0x14002df88  cmovnz  eax, r15d
0x14002df8c  mov     r9b, al
0x14002df8f  mov     [r8+8AEh], r9b
0x14002df96  pop     r15
0x14002df98  pop     r14
0x14002df9a  pop     rdi
0x14002df9b  pop     rsi
0x14002df9c  pop     rbp
0x14002df9d  pop     rbx
0x14002df9e  retn
```
