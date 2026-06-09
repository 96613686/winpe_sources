# HUBMISC_ComputeU2Timeout

- ea: `0x14002dfa8`
- end: `0x14002e269`
- name: `HUBMISC_ComputeU2Timeout`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140020d20`

## callees

- `0x14002dfa8`

## pseudocode

```c
char __fastcall HUBMISC_ComputeU2Timeout(__int64 *a1)
{
  bool v2; // r8
  volatile signed __int32 *v3; // rdx
  int v4; // r10d
  char v5; // cl
  char v6; // r8
  unsigned __int16 v7; // r8
  _QWORD *v8; // r14
  char v9; // r13
  __int64 v10; // rsi
  __int64 v11; // r10
  unsigned int v12; // edi
  __int64 i; // r11
  _QWORD *v14; // r10
  char v15; // di
  char v16; // bp
  unsigned int v17; // r12d
  __int64 v18; // r15
  _BYTE *v19; // r11
  unsigned int v20; // r10d
  unsigned __int16 v21; // ax
  _QWORD *v22; // rax
  __int64 v23; // rax

  if ( (*(_DWORD *)(a1[1] + 204) & 0x800) != 0 )
  {
    v2 = (*(_DWORD *)(a1[1] + 204) & 0x400) != 0;
    if ( *((_DWORD *)a1 + 683) == 2 )
      v2 = 0;
  }
  else
  {
    v2 = (*(_DWORD *)(a1[1] + 204) & 0x400) != 0;
  }
  if ( (*((_DWORD *)a1 + 413) & 0x80u) == 0 && (*(_DWORD *)(*a1 + 40) & 0x8000) == 0 )
  {
    v3 = (volatile signed __int32 *)(a1 + 278);
    v4 = *((_DWORD *)a1 + 556);
    if ( (v4 & 0x180) == 0 && !v2 )
    {
      v5 = *((_BYTE *)a1 + 2228);
      *v3 = v4 ^ ((unsigned __int8)v4 ^ (unsigned __int8)(16 * v5)) & 0x20;
      if ( (v5 & 8) == 0 )
      {
        v6 = 0;
        goto LABEL_56;
      }
      if ( (a1[205] & 2) != 0 || (v5 & 0x20) == 0 )
      {
        v6 = -1;
        goto LABEL_56;
      }
      if ( v5 < 0 )
      {
        v6 = 1;
        goto LABEL_56;
      }
      if ( (v5 & 0x40) != 0 )
      {
        v6 = -2;
        goto LABEL_56;
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
          for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
          {
            if ( (*(_BYTE *)(*(_QWORD *)(v11 + 80 * i + 72) + 3LL) & 3) != 0 )
            {
              v15 = 0;
              v9 = 1;
              v16 = 0;
              goto LABEL_26;
            }
          }
          v14 = *(_QWORD **)(v11 + 8);
          if ( v8 == v14 )
            break;
          v11 = (__int64)(v14 - 1);
        }
      }
      v15 = 0;
      v16 = 0;
      if ( v8 != (_QWORD *)*v8 )
      {
        do
        {
LABEL_26:
          v17 = *(_DWORD *)(v10 + 24);
          v18 = 0;
          if ( v17 )
          {
            while ( 1 )
            {
              v19 = *(_BYTE **)(v10 + 80 * v18 + 72);
              v20 = *(unsigned __int16 *)((char *)a1 + (((__int64)(char)v19[2] >> 63) & 0xFFFFFFFFFFFFFFFAuLL) + 2212);
              if ( (v19[3] & 3) == 0 )
                break;
              switch ( v19[3] & 3 )
              {
                case 1:
                  if ( v20 > 125 * (unsigned int)(unsigned __int8)v19[6] )
                    goto LABEL_55;
LABEL_38:
                  v21 = 1;
                  break;
                case 2:
                  goto LABEL_39;
                case 3:
                  if ( (v19[3] & 0x30) != 0 || (v16 = 1, v20 <= 125 * (unsigned int)(unsigned __int8)v19[6]) )
                  {
LABEL_39:
                    v21 = 5 * v20;
                    break;
                  }
                  v15 = 1;
                  v21 = 255;
                  break;
                default:
                  v21 = 0;
                  break;
              }
              if ( v7 <= v21 )
                v7 = v21;
              v18 = (unsigned int)(v18 + 1);
              if ( (unsigned int)v18 >= v17 )
                goto LABEL_43;
            }
            if ( !v9 )
              goto LABEL_39;
            goto LABEL_38;
          }
LABEL_43:
          v22 = *(_QWORD **)(v10 + 8);
          v10 = (__int64)(v22 - 1);
        }
        while ( v8 != v22 );
        if ( v15 )
        {
          v6 = -1;
          goto LABEL_56;
        }
        if ( v16 && *((_BYTE *)a1 + 2222) )
          *((_BYTE *)a1 + 2222) = -1;
        if ( v7 >= 0xFE00u )
        {
          v6 = -2;
          goto LABEL_56;
        }
      }
      v6 = HIBYTE(v7) + 1;
      goto LABEL_56;
    }
  }
  v3 = (volatile signed __int32 *)(a1 + 278);
LABEL_55:
  v6 = 0;
  _InterlockedAnd(v3, 0xFFFFFFDF);
LABEL_56:
  v23 = *a1;
  if ( (*(_DWORD *)(*a1 + 40) & 0x10000000) != 0 )
  {
    LODWORD(v23) = *((_DWORD *)a1 + 410);
    if ( (v23 & 2) == 0 )
    {
      LOBYTE(v23) = *((_BYTE *)a1 + 2222) - 1;
      if ( (unsigned __int8)v23 <= 0xFDu && v6 == -1 )
      {
        v6 = 0;
        _InterlockedAnd(v3, 0xFFFFFFDF);
      }
    }
  }
  *((_BYTE *)a1 + 2223) = v6;
  return v23;
}

```

## disassembly

```asm
0x14002dfa8  push    rbx
0x14002dfaa  push    rbp
0x14002dfab  push    rsi
0x14002dfac  push    rdi
0x14002dfad  push    r12
0x14002dfaf  push    r13
0x14002dfb1  push    r14
0x14002dfb3  push    r15
0x14002dfb5  mov     rax, [rcx+8]
0x14002dfb9  mov     ebp, 1
0x14002dfbe  mov     r9, rcx
0x14002dfc1  mov     edx, [rax+0CCh]
0x14002dfc7  mov     eax, edx
0x14002dfc9  shr     eax, 0Ah
0x14002dfcc  and     al, bpl
0x14002dfcf  bt      edx, 0Bh
0x14002dfd3  jnb     short loc_14002DFE8
0x14002dfd5  movzx   r8d, al
0x14002dfd9  xor     eax, eax
0x14002dfdb  cmp     dword ptr [rcx+0AACh], 2
0x14002dfe2  cmovz   r8d, eax
0x14002dfe6  jmp     short loc_14002DFEB
0x14002dfe8  mov     r8b, al
0x14002dfeb  mov     eax, [rcx+674h]
0x14002dff1  mov     r11d, 0FFh
0x14002dff7  test    al, al
0x14002dff9  js      loc_14002E215
0x14002dfff  mov     rax, [rcx]
0x14002e002  test    dword ptr [rax+28h], 8000h
0x14002e009  jnz     loc_14002E215
0x14002e00f  lea     rdx, [rcx+8B0h]
0x14002e016  mov     r10d, [rdx]
0x14002e019  test    r10d, 180h
0x14002e020  jnz     loc_14002E215
0x14002e026  cmp     r8b, bpl
0x14002e029  jz      loc_14002E215
0x14002e02f  movzx   ecx, byte ptr [rcx+8B4h]
0x14002e036  mov     eax, ecx
0x14002e038  shl     eax, 4
0x14002e03b  xor     eax, r10d
0x14002e03e  and     eax, 20h
0x14002e041  xor     eax, r10d
0x14002e044  mov     [rdx], eax
0x14002e046  test    cl, 8
0x14002e049  jnz     short loc_14002E053
0x14002e04b  xor     r8b, r8b
0x14002e04e  jmp     loc_14002E223
0x14002e053  mov     eax, [r9+668h]
0x14002e05a  test    al, 2
0x14002e05c  jnz     loc_14002E210
0x14002e062  test    cl, 20h
0x14002e065  jz      loc_14002E210
0x14002e06b  test    cl, cl
0x14002e06d  jns     short loc_14002E077
0x14002e06f  mov     r8b, bpl
0x14002e072  jmp     loc_14002E223
0x14002e077  test    cl, 40h
0x14002e07a  jz      short loc_14002E084
0x14002e07c  mov     r8b, 0FEh
0x14002e07f  jmp     loc_14002E223
0x14002e084  mov     r14, [r9+30h]
0x14002e088  xor     r8d, r8d
0x14002e08b  add     r14, 10h
0x14002e08f  xor     r13b, r13b
0x14002e092  mov     rbx, [r14]
0x14002e095  lea     rsi, [rbx-8]
0x14002e099  mov     r10, rsi
0x14002e09c  cmp     r14, rbx
0x14002e09f  jz      short loc_14002E0E0
0x14002e0a1  mov     edi, [r10+18h]
0x14002e0a5  xor     r11d, r11d
0x14002e0a8  test    edi, edi
0x14002e0aa  jz      short loc_14002E0C6
0x14002e0ac  lea     rax, [r11+r11*4]
0x14002e0b0  add     rax, rax
0x14002e0b3  mov     rax, [r10+rax*8+48h]
0x14002e0b8  test    byte ptr [rax+3], 3
0x14002e0bc  jnz     short loc_14002E0D5
0x14002e0be  add     r11d, ebp
0x14002e0c1  cmp     r11d, edi
0x14002e0c4  jb      short loc_14002E0AC
0x14002e0c6  mov     r10, [r10+8]
0x14002e0ca  cmp     r14, r10
0x14002e0cd  jz      short loc_14002E0E0
0x14002e0cf  add     r10, 0FFFFFFFFFFFFFFF8h
0x14002e0d3  jmp     short loc_14002E0A1
0x14002e0d5  xor     dil, dil
0x14002e0d8  mov     r13b, bpl
0x14002e0db  xor     bpl, bpl
0x14002e0de  jmp     short loc_14002E0EF
0x14002e0e0  xor     dil, dil
0x14002e0e3  xor     bpl, bpl
0x14002e0e6  cmp     r14, rbx
0x14002e0e9  jz      loc_14002E1FB
0x14002e0ef  mov     r12d, [rsi+18h]
0x14002e0f3  xor     r15d, r15d
0x14002e0f6  test    r12d, r12d
0x14002e0f9  jz      loc_14002E1AF
0x14002e0ff  lea     rcx, [r15+r15*4]
0x14002e103  add     rcx, rcx
0x14002e106  mov     r11, [rsi+rcx*8+48h]
0x14002e10b  movsx   rax, byte ptr [r11+2]
0x14002e110  movzx   ebx, byte ptr [r11+3]
0x14002e115  sar     rax, 3Fh
0x14002e119  mov     ecx, ebx
0x14002e11b  and     rax, 0FFFFFFFFFFFFFFFAh
0x14002e11f  movzx   r10d, word ptr [rax+r9+8A4h]
0x14002e128  and     ecx, 3
0x14002e12b  jz      short loc_14002E181
0x14002e12d  sub     ecx, 1
0x14002e130  jz      short loc_14002E164
0x14002e132  sub     ecx, 1
0x14002e135  jz      short loc_14002E18D
0x14002e137  cmp     ecx, 1
0x14002e13a  jz      short loc_14002E140
0x14002e13c  xor     eax, eax
0x14002e13e  jmp     short loc_14002E19A
0x14002e140  test    bl, 30h
0x14002e143  jnz     short loc_14002E18D
0x14002e145  movzx   eax, byte ptr [r11+6]
0x14002e14a  mov     ebx, 1
0x14002e14f  imul    ecx, eax, 7Dh ; '}'
0x14002e152  mov     bpl, bl
0x14002e155  cmp     r10d, ecx
0x14002e158  jbe     short loc_14002E18D
0x14002e15a  mov     dil, bl
0x14002e15d  mov     eax, 0FFh
0x14002e162  jmp     short loc_14002E19A
0x14002e164  movzx   eax, byte ptr [r11+6]
0x14002e169  imul    ecx, eax, 7Dh ; '}'
0x14002e16c  cmp     r10d, ecx
0x14002e16f  jbe     short loc_14002E186
0x14002e171  mov     ebp, 1
0x14002e176  mov     r11d, 0FFh
0x14002e17c  jmp     loc_14002E21C
0x14002e181  test    r13b, r13b
0x14002e184  jz      short loc_14002E18D
0x14002e186  mov     eax, 1
0x14002e18b  jmp     short loc_14002E19A
0x14002e18d  movzx   eax, r10w
0x14002e191  shl     r10w, 2
0x14002e196  add     ax, r10w
0x14002e19a  cmp     r8w, ax
0x14002e19e  cmovbe  r8w, ax
0x14002e1a3  inc     r15d
0x14002e1a6  cmp     r15d, r12d
0x14002e1a9  jb      loc_14002E0FF
0x14002e1af  mov     rax, [rsi+8]
0x14002e1b3  lea     rsi, [rax-8]
0x14002e1b7  cmp     r14, rax
0x14002e1ba  jnz     loc_14002E0EF
0x14002e1c0  mov     r11d, 0FFh
0x14002e1c6  test    dil, dil
0x14002e1c9  jz      short loc_14002E1D5
0x14002e1cb  mov     r8b, r11b
0x14002e1ce  mov     ebp, 1
0x14002e1d3  jmp     short loc_14002E223
0x14002e1d5  test    bpl, bpl
0x14002e1d8  jz      short loc_14002E1EB
0x14002e1da  cmp     byte ptr [r9+8AEh], 0
0x14002e1e2  jbe     short loc_14002E1EB
0x14002e1e4  mov     [r9+8AEh], r11b
0x14002e1eb  mov     eax, 0FE00h
0x14002e1f0  cmp     r8w, ax
0x14002e1f4  jb      short loc_14002E1FB
0x14002e1f6  mov     r8b, 0FEh
0x14002e1f9  jmp     short loc_14002E1CE
0x14002e1fb  shr     r8w, 8
0x14002e200  mov     ebp, 1
0x14002e205  add     r8b, bpl
0x14002e208  mov     r11d, 0FFh
0x14002e20e  jmp     short loc_14002E223
0x14002e210  mov     r8b, r11b
0x14002e213  jmp     short loc_14002E223
0x14002e215  lea     rdx, [rcx+8B0h]
0x14002e21c  xor     r8b, r8b
0x14002e21f  lock and dword ptr [rdx], 0FFFFFFDFh
0x14002e223  mov     rax, [r9]
0x14002e226  test    dword ptr [rax+28h], 10000000h
0x14002e22d  jz      short loc_14002E254
0x14002e22f  mov     eax, [r9+668h]
0x14002e236  test    al, 2
0x14002e238  jnz     short loc_14002E254
0x14002e23a  mov     al, [r9+8AEh]
0x14002e241  sub     al, bpl
0x14002e244  cmp     al, 0FDh
0x14002e246  ja      short loc_14002E254
0x14002e248  cmp     r8b, r11b
0x14002e24b  jnz     short loc_14002E254
0x14002e24d  xor     r8b, r8b
0x14002e250  lock and dword ptr [rdx], 0FFFFFFDFh
0x14002e254  mov     [r9+8AFh], r8b
0x14002e25b  pop     r15
0x14002e25d  pop     r14
0x14002e25f  pop     r13
0x14002e261  pop     r12
0x14002e263  pop     rdi
0x14002e264  pop     rsi
0x14002e265  pop     rbp
0x14002e266  pop     rbx
0x14002e267  retn
```
