# SkpgComputeContextSize

- ea: `0x1400a2dac`
- end: `0x1400a322c`
- name: `SkpgComputeContextSize`
- size: `1152`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400a3234`

## callees

- `0x140063650`
- `0x140078cfc`
- `0x1400a2dac`
- `0x1400a3798`
- `0x1400a4f20`

## pseudocode

```c
__int64 SkpgComputeContextSize(__int64 a1, __int64 a2, _DWORD *a3, ...)
{
  __int64 v3; // rdx
  int *v4; // r14
  __int64 v5; // rdi
  __int64 v6; // r12
  __int64 v7; // r11
  __int64 v8; // r9
  int v9; // r10d
  int v10; // r13d
  unsigned int v11; // ebx
  unsigned __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // r8
  _WORD *v16; // rbp
  unsigned int PageCountBeyondImage; // eax
  unsigned int v18; // r15d
  __int64 v19; // r14
  __int64 v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // rax
  __int64 v27; // r8
  int v28; // eax
  bool v29; // zf
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // ebp
  __int64 v38; // rdi
  int v39; // eax
  int v40; // ecx
  __int64 v41; // rdx
  BOOL v42; // [rsp+30h] [rbp-58h]
  __int64 v43; // [rsp+38h] [rbp-50h]
  int v44; // [rsp+90h] [rbp+8h]
  __int64 v45; // [rsp+98h] [rbp+10h] BYREF
  _DWORD *v46; // [rsp+A0h] [rbp+18h]
  int *v47; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  va_list va1; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v47 = va_arg(va1, int *);
  v46 = a3;
  v3 = a1 + (a2 << 6);
  v44 = 0;
  v4 = v47;
  v45 = v3;
  v5 = a1;
  v6 = 0;
  v7 = 1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 888;
  v42 = (*v47 & 3) != 0;
  while ( 1 )
  {
    v43 = v8;
    if ( v5 == v3 )
      break;
    v13 = *(_QWORD *)(v5 + 8);
    v14 = *(_QWORD *)(v5 + 16);
    if ( v13 )
    {
      if ( !(unsigned int)SkpgProbePointer(v13, *(_QWORD *)(v5 + 16)) )
        return 0;
    }
    else if ( v14 )
    {
      return 0;
    }
    v16 = (_WORD *)(v5 + 24);
    if ( !v8 && *v16 != 4096 || *(_DWORD *)(v5 + 16) != v14 || *(_WORD *)(v5 + 26) >= 2u )
      return 0;
    if ( v6 )
    {
      v16 = (_WORD *)(v5 + 24);
      if ( *(_WORD *)(v5 + 24) != 4098 || *(_QWORD *)(v5 + 48) != v6 )
      {
        PageCountBeyondImage = SkmmGetPageCountBeyondImage(v6);
        if ( PageCountBeyondImage )
        {
          v18 = v11 + PageCountBeyondImage;
          if ( v11 + PageCountBeyondImage <= v11 )
            return 0;
          v19 = PageCountBeyondImage;
          if ( v12 + 48LL * PageCountBeyondImage <= v12 || !(unsigned int)SkmmQueryNtImageBounds(v6, 0, 0) )
            return 0;
          v11 = v18;
        }
        else
        {
          v19 = 0;
        }
        v8 = v43;
        v20 = 3 * v19;
        v4 = v47;
        v6 = 0;
        v9 = v44;
        v7 = 1;
        v12 += 16 * v20;
      }
    }
    v21 = (unsigned __int16)*v16;
    if ( v21 > 0x1005 )
    {
      v30 = v21 - 4102;
      if ( v30 )
      {
        v31 = v30 - 3;
        if ( !v31 )
        {
          if ( (unsigned __int64)(*(_QWORD *)(v5 + 16) - v7) > 0xFFF || v10 && *(char *)(v5 + 47) < 0 )
            return 0;
          goto LABEL_46;
        }
        v32 = v31 - 1;
        if ( !v32 )
        {
          if ( *(_QWORD *)(v5 + 16) != 4096 || (*(_DWORD *)(v5 + 8) & 0xFFF) != 0 )
            return 0;
LABEL_46:
          if ( v11 + 1 < v11 || v12 + 48 < v12 )
            return 0;
          ++v11;
          v12 += 48LL;
          goto LABEL_66;
        }
        v33 = v32 - 1;
        if ( !v33 )
        {
          v35 = *(unsigned int *)(v5 + 32);
          if ( (unsigned int)v35 >= v4[1] || !SkeProcessorBlock[v35] )
            return 0;
          v29 = *(_QWORD *)(v5 + 16) == 0;
          goto LABEL_57;
        }
        if ( v33 != 1 )
          return 0;
      }
LABEL_64:
      v34 = *(unsigned int *)(v5 + 52);
      if ( (unsigned int)v34 >= v4[1] || !SkeProcessorBlock[v34] )
        return 0;
      goto LABEL_66;
    }
    if ( v21 != 4101 )
    {
      v22 = v21 - 4096;
      if ( !v22 )
      {
        if ( v8 )
          return 0;
        v28 = *(_DWORD *)(v5 + 44);
        v10 = v7 & v28;
        if ( ((unsigned int)v7 & v28) != 0 )
        {
          if ( (v28 & 4) != 0 )
            v9 = v7;
          if ( (SkmiFlags & 0x80u) == 0 )
            v9 = v7;
          v44 = v9;
        }
        v29 = v10 == ((unsigned int)v7 & ((unsigned int)SkmiFlags >> 4));
LABEL_57:
        if ( !v29 )
          return 0;
        goto LABEL_66;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        if ( v10 && *(char *)(v5 + 47) < 0 || !*(_QWORD *)(v5 + 16) )
          goto LABEL_66;
        goto LABEL_46;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        if ( *(_QWORD *)(v5 + 16) != 4096
          || *(_QWORD *)(v5 + 48) + (unsigned int)(*(_DWORD *)(v5 + 56) << 12) != *(_QWORD *)(v5 + 8)
          || !(unsigned int)SkpgProbePointer(*(_QWORD *)(v5 + 48), 4096)
          || v11 + 1 < v11
          || v12 + 48 < v12 )
        {
          return 0;
        }
        if ( !v10 || *(char *)(v5 + 47) >= 0 || ((unsigned __int8)v7 & *(_BYTE *)(v5 + 26)) == 0 || v9 )
        {
          v6 = v27;
          ++v11;
          v12 += 48LL;
        }
        goto LABEL_66;
      }
      v25 = v24 - 1;
      if ( !v25 )
        goto LABEL_64;
      if ( v25 != 1 )
        return 0;
    }
    v26 = *(unsigned int *)(v5 + 48);
    if ( (unsigned int)v26 >= v4[1] || !SkeProcessorBlock[v26] || (unsigned __int64)(*(_QWORD *)(v5 + 16) - v7) > 0xFFF )
      return 0;
    v42 = v7;
    if ( (SkmiFlags & 0x1000) == 0 )
      goto LABEL_46;
LABEL_66:
    v3 = v45;
    v5 += 64;
    v8 += v7;
  }
  if ( !v42 )
    return 0;
  if ( v6 )
  {
    v36 = SkmmGetPageCountBeyondImage(v6);
    if ( v36 )
    {
      v37 = v11 + v36;
      if ( v11 + v36 > v11 )
      {
        v38 = v36;
        if ( v12 + 48LL * v36 > v12 )
        {
          if ( (unsigned int)SkmmQueryNtImageBounds(v6, 0, 0) )
          {
            v11 = v37;
            goto LABEL_85;
          }
        }
      }
      return 0;
    }
    v38 = 0;
LABEL_85:
    v12 += 48 * v38;
  }
  v39 = *v4;
  v40 = 0;
  LODWORD(v47) = 0;
  v41 = 0;
  v45 = 0;
  if ( (v39 & 2) == 0 )
  {
    SkpgCreateSecureKernelExtents(0, 0, (unsigned int)&v45, (unsigned int)va, (__int64)v4);
    v41 = v45;
    if ( v12 + v45 < v12 )
      return 0;
    v40 = (int)v47;
    if ( (unsigned int)v47 + v11 < v11 )
      return 0;
  }
  *v46 = v40 + v11;
  return v12 + v41;
}

```

## disassembly

```asm
0x1400a2dac  mov     [rsp+arg_18], r9
0x1400a2db1  mov     [rsp+arg_10], r8
0x1400a2db6  push    rbx
0x1400a2db7  push    rbp
0x1400a2db8  push    rsi
0x1400a2db9  push    rdi
0x1400a2dba  push    r12
0x1400a2dbc  push    r13
0x1400a2dbe  push    r14
0x1400a2dc0  push    r15
0x1400a2dc2  sub     rsp, 48h
0x1400a2dc6  xor     r15d, r15d
0x1400a2dc9  shl     rdx, 6
0x1400a2dcd  add     rdx, rcx
0x1400a2dd0  mov     [rsp+88h+arg_0], r15d
0x1400a2dd8  mov     r14, r9
0x1400a2ddb  mov     [rsp+88h+arg_8], rdx
0x1400a2de3  mov     rdi, rcx
0x1400a2de6  mov     r12d, r15d
0x1400a2de9  mov     ecx, r15d
0x1400a2dec  lea     r11d, [r15+1]
0x1400a2df0  mov     r9d, r15d
0x1400a2df3  mov     r10d, r15d
0x1400a2df6  mov     eax, [r14]
0x1400a2df9  mov     r13d, r15d
0x1400a2dfc  test    al, 3
0x1400a2dfe  mov     ebx, r15d
0x1400a2e01  mov     esi, 378h
0x1400a2e06  mov     eax, 1000h
0x1400a2e0b  setnz   cl
0x1400a2e0e  mov     [rsp+88h+var_58], ecx
0x1400a2e12  mov     [rsp+88h+var_50], r9
0x1400a2e17  cmp     rdi, rdx
0x1400a2e1a  jz      loc_1400A3151
0x1400a2e20  mov     rcx, [rdi+8]
0x1400a2e24  mov     r8, [rdi+10h]
0x1400a2e28  test    rcx, rcx
0x1400a2e2b  jnz     short loc_1400A2E46
0x1400a2e2d  test    r8, r8
0x1400a2e30  jz      short loc_1400A2E57
0x1400a2e32  xor     eax, eax
0x1400a2e34  add     rsp, 48h
0x1400a2e38  pop     r15
0x1400a2e3a  pop     r14
0x1400a2e3c  pop     r13
0x1400a2e3e  pop     r12
0x1400a2e40  pop     rdi
0x1400a2e41  pop     rsi
0x1400a2e42  pop     rbp
0x1400a2e43  pop     rbx
0x1400a2e44  retn
0x1400a2e46  mov     rdx, r8
0x1400a2e49  call    SkpgProbePointer
0x1400a2e4e  test    eax, eax
0x1400a2e50  jz      short loc_1400A2E32
0x1400a2e52  mov     eax, 1000h
0x1400a2e57  lea     rbp, [rdi+18h]
0x1400a2e5b  test    r9, r9
0x1400a2e5e  jnz     short loc_1400A2E66
0x1400a2e60  cmp     [rbp+0], ax
0x1400a2e64  jnz     short loc_1400A2E32
0x1400a2e66  mov     eax, [rdi+10h]
0x1400a2e69  cmp     rax, r8
0x1400a2e6c  jnz     short loc_1400A2E32
0x1400a2e6e  cmp     word ptr [rdi+1Ah], 2
0x1400a2e73  jnb     short loc_1400A2E32
0x1400a2e75  test    r12, r12
0x1400a2e78  jz      loc_1400A2F08
0x1400a2e7e  lea     rbp, [rdi+18h]
0x1400a2e82  mov     eax, 1002h
0x1400a2e87  cmp     [rbp+0], ax
0x1400a2e8b  jnz     short loc_1400A2E93
0x1400a2e8d  cmp     [rdi+30h], r12
0x1400a2e91  jz      short loc_1400A2F08
0x1400a2e93  mov     rcx, r12
0x1400a2e96  call    SkmmGetPageCountBeyondImage
0x1400a2e9b  test    eax, eax
0x1400a2e9d  jz      short loc_1400A2EDC
0x1400a2e9f  lea     r15d, [rbx+rax]
0x1400a2ea3  cmp     r15d, ebx
0x1400a2ea6  jbe     short loc_1400A2E32
0x1400a2ea8  mov     r14d, eax
0x1400a2eab  lea     rax, [r14+r14*2]
0x1400a2eaf  shl     rax, 4
0x1400a2eb3  add     rax, rsi
0x1400a2eb6  cmp     rax, rsi
0x1400a2eb9  jbe     loc_1400A2E32
0x1400a2ebf  xor     r8d, r8d
0x1400a2ec2  xor     edx, edx
0x1400a2ec4  mov     rcx, r12
0x1400a2ec7  call    SkmmQueryNtImageBounds
0x1400a2ecc  test    eax, eax
0x1400a2ece  jz      loc_1400A2E32
0x1400a2ed4  mov     ebx, r15d
0x1400a2ed7  xor     r15d, r15d
0x1400a2eda  jmp     short loc_1400A2EDF
0x1400a2edc  mov     r14, r15
0x1400a2edf  mov     r9, [rsp+88h+var_50]
0x1400a2ee4  lea     rax, [r14+r14*2]
0x1400a2ee8  mov     r14, [rsp+88h+arg_18]
0x1400a2ef0  mov     r12, r15
0x1400a2ef3  mov     r10d, [rsp+88h+arg_0]
0x1400a2efb  mov     r11d, 1
0x1400a2f01  shl     rax, 4
0x1400a2f05  add     rsi, rax
0x1400a2f08  movzx   ecx, word ptr [rbp+0]
0x1400a2f0c  cmp     ecx, 1005h
0x1400a2f12  ja      loc_1400A3084
0x1400a2f18  jz      short loc_1400A2F47
0x1400a2f1a  mov     eax, 1000h
0x1400a2f1f  sub     ecx, eax
0x1400a2f21  jz      loc_1400A3040
0x1400a2f27  sub     ecx, 1
0x1400a2f2a  jz      loc_1400A3005
0x1400a2f30  sub     ecx, 1
0x1400a2f33  jz      short loc_1400A2F92
0x1400a2f35  sub     ecx, 1
0x1400a2f38  jz      loc_1400A30A8
0x1400a2f3e  cmp     ecx, 1
0x1400a2f41  jnz     loc_1400A2E32
0x1400a2f47  mov     eax, [rdi+30h]
0x1400a2f4a  cmp     eax, [r14+4]
0x1400a2f4e  jnb     loc_1400A2E32
0x1400a2f54  lea     rcx, SkeProcessorBlock
0x1400a2f5b  cmp     [rcx+rax*8], r15
0x1400a2f5f  jz      loc_1400A2E32
0x1400a2f65  mov     rax, [rdi+10h]
0x1400a2f69  sub     rax, r11
0x1400a2f6c  cmp     rax, 0FFFh
0x1400a2f72  ja      loc_1400A2E32
0x1400a2f78  test    cs:SkmiFlags, 1000h
0x1400a2f82  mov     [rsp+88h+var_58], r11d
0x1400a2f87  jnz     loc_1400A30C6
0x1400a2f8d  jmp     loc_1400A301E
0x1400a2f92  cmp     [rdi+10h], rax
0x1400a2f96  jnz     loc_1400A2E32
0x1400a2f9c  mov     ecx, [rdi+38h]
0x1400a2f9f  mov     r8, [rdi+30h]
0x1400a2fa3  shl     ecx, 0Ch
0x1400a2fa6  add     rcx, r8
0x1400a2fa9  cmp     rcx, [rdi+8]
0x1400a2fad  jnz     loc_1400A2E32
0x1400a2fb3  mov     rdx, rax
0x1400a2fb6  mov     rcx, r8
0x1400a2fb9  call    SkpgProbePointer
0x1400a2fbe  test    eax, eax
0x1400a2fc0  jz      loc_1400A2E32
0x1400a2fc6  lea     edx, [rbx+1]
0x1400a2fc9  cmp     edx, ebx
0x1400a2fcb  jb      loc_1400A2E32
0x1400a2fd1  lea     rcx, [rsi+30h]
0x1400a2fd5  cmp     rcx, rsi
0x1400a2fd8  jb      loc_1400A2E32
0x1400a2fde  test    r13d, r13d
0x1400a2fe1  jz      short loc_1400A2FF8
0x1400a2fe3  cmp     [rdi+2Fh], r15b
0x1400a2fe7  jge     short loc_1400A2FF8
0x1400a2fe9  test    [rdi+1Ah], r11b
0x1400a2fed  jz      short loc_1400A2FF8
0x1400a2fef  test    r10d, r10d
0x1400a2ff2  jz      loc_1400A30C6
0x1400a2ff8  mov     r12, r8
0x1400a2ffb  mov     ebx, edx
0x1400a2ffd  mov     rsi, rcx
0x1400a3000  jmp     loc_1400A30C6
0x1400a3005  test    r13d, r13d
0x1400a3008  jz      short loc_1400A3014
0x1400a300a  cmp     [rdi+2Fh], r15b
0x1400a300e  jl      loc_1400A30CB
0x1400a3014  cmp     [rdi+10h], r15
0x1400a3018  jz      loc_1400A30CB
0x1400a301e  lea     ecx, [rbx+1]
0x1400a3021  cmp     ecx, ebx
0x1400a3023  jb      loc_1400A2E32
0x1400a3029  lea     rax, [rsi+30h]
0x1400a302d  cmp     rax, rsi
0x1400a3030  jb      loc_1400A2E32
0x1400a3036  mov     ebx, ecx
0x1400a3038  mov     rsi, rax
0x1400a303b  jmp     loc_1400A30C6
0x1400a3040  test    r9, r9
0x1400a3043  jnz     loc_1400A2E32
0x1400a3049  mov     eax, [rdi+2Ch]
0x1400a304c  mov     r13d, eax
0x1400a304f  and     r13d, r11d
0x1400a3052  jz      short loc_1400A306D
0x1400a3054  test    al, 4
0x1400a3056  cmovnz  r10d, r11d
0x1400a305a  test    byte ptr cs:SkmiFlags, 80h
0x1400a3061  cmovz   r10d, r11d
0x1400a3065  mov     [rsp+88h+arg_0], r10d
0x1400a306d  mov     eax, cs:SkmiFlags
0x1400a3073  shr     eax, 4
0x1400a3076  and     eax, r11d
0x1400a3079  cmp     r13d, eax
0x1400a307c  jnz     loc_1400A2E32
0x1400a3082  jmp     short loc_1400A30C6
0x1400a3084  sub     ecx, 1006h
0x1400a308a  jz      short loc_1400A30A8
0x1400a308c  sub     ecx, 3
0x1400a308f  jz      loc_1400A3126
0x1400a3095  sub     ecx, 1
0x1400a3098  jz      short loc_1400A3106
0x1400a309a  sub     ecx, 1
0x1400a309d  jz      short loc_1400A30DF
0x1400a309f  cmp     ecx, 1
0x1400a30a2  jnz     loc_1400A2E32
0x1400a30a8  mov     eax, [rdi+34h]
0x1400a30ab  cmp     eax, [r14+4]
0x1400a30af  jnb     loc_1400A2E32
0x1400a30b5  lea     rcx, SkeProcessorBlock
0x1400a30bc  cmp     [rcx+rax*8], r15
0x1400a30c0  jz      loc_1400A2E32
0x1400a30c6  mov     eax, 1000h
0x1400a30cb  mov     rdx, [rsp+88h+arg_8]
0x1400a30d3  add     rdi, 40h ; '@'
0x1400a30d7  add     r9, r11
0x1400a30da  jmp     loc_1400A2E12
0x1400a30df  mov     eax, [rdi+20h]
0x1400a30e2  cmp     eax, [r14+4]
0x1400a30e6  jnb     loc_1400A2E32
0x1400a30ec  lea     rcx, SkeProcessorBlock
0x1400a30f3  cmp     [rcx+rax*8], r15
0x1400a30f7  jz      loc_1400A2E32
0x1400a30fd  cmp     [rdi+10h], r15
0x1400a3101  jmp     loc_1400A307C
0x1400a3106  cmp     qword ptr [rdi+10h], 1000h
0x1400a310e  jnz     loc_1400A2E32
0x1400a3114  test    dword ptr [rdi+8], 0FFFh
0x1400a311b  jnz     loc_1400A2E32
0x1400a3121  jmp     loc_1400A301E
0x1400a3126  mov     rax, [rdi+10h]
0x1400a312a  sub     rax, r11
0x1400a312d  cmp     rax, 0FFFh
0x1400a3133  ja      loc_1400A2E32
0x1400a3139  test    r13d, r13d
0x1400a313c  jz      loc_1400A301E
0x1400a3142  cmp     [rdi+2Fh], r15b
0x1400a3146  jl      loc_1400A2E32
0x1400a314c  jmp     loc_1400A301E
0x1400a3151  cmp     [rsp+88h+var_58], r15d
0x1400a3156  jz      loc_1400A2E32
0x1400a315c  test    r12, r12
0x1400a315f  jz      short loc_1400A31B5
0x1400a3161  mov     rcx, r12
0x1400a3164  call    SkmmGetPageCountBeyondImage
0x1400a3169  test    eax, eax
0x1400a316b  jz      short loc_1400A31A7
0x1400a316d  lea     ebp, [rbx+rax]
0x1400a3170  cmp     ebp, ebx
0x1400a3172  jbe     loc_1400A2E32
0x1400a3178  mov     edi, eax
0x1400a317a  lea     rax, [rdi+rdi*2]
0x1400a317e  shl     rax, 4
0x1400a3182  add     rax, rsi
0x1400a3185  cmp     rax, rsi
0x1400a3188  jbe     loc_1400A2E32
0x1400a318e  xor     r8d, r8d
0x1400a3191  xor     edx, edx
0x1400a3193  mov     rcx, r12
0x1400a3196  call    SkmmQueryNtImageBounds
0x1400a319b  test    eax, eax
0x1400a319d  jz      loc_1400A2E32
0x1400a31a3  mov     ebx, ebp
0x1400a31a5  jmp     short loc_1400A31AA
0x1400a31a7  mov     rdi, r15
0x1400a31aa  lea     rax, [rdi+rdi*2]
0x1400a31ae  shl     rax, 4
0x1400a31b2  add     rsi, rax
0x1400a31b5  mov     eax, [r14]
0x1400a31b8  mov     ecx, r15d
0x1400a31bb  mov     dword ptr [rsp+88h+arg_18], ecx
0x1400a31c2  mov     rdx, r15
0x1400a31c5  mov     [rsp+88h+arg_8], rdx
0x1400a31cd  test    al, 2
0x1400a31cf  jnz     short loc_1400A3216
0x1400a31d1  lea     r9, [rsp+88h+arg_18]
0x1400a31d9  mov     [rsp+88h+var_68], r14
0x1400a31de  lea     r8, [rsp+88h+arg_8]
0x1400a31e6  xor     edx, edx
0x1400a31e8  xor     ecx, ecx
0x1400a31ea  call    SkpgCreateSecureKernelExtents
0x1400a31ef  mov     rdx, [rsp+88h+arg_8]
0x1400a31f7  lea     rax, [rsi+rdx]
0x1400a31fb  cmp     rax, rsi
0x1400a31fe  jb      loc_1400A2E32
0x1400a3204  mov     ecx, dword ptr [rsp+88h+arg_18]
0x1400a320b  lea     eax, [rcx+rbx]
0x1400a320e  cmp     eax, ebx
0x1400a3210  jb      loc_1400A2E32
0x1400a3216  lea     eax, [rcx+rbx]
0x1400a3219  mov     rcx, [rsp+88h+arg_10]
0x1400a3221  mov     [rcx], eax
0x1400a3223  lea     rax, [rsi+rdx]
0x1400a3227  jmp     loc_1400A2E34
```
