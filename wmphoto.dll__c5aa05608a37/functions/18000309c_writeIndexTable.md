# writeIndexTable

- ea: `0x18000309c`
- end: `0x1800033c4`
- name: `writeIndexTable`
- size: `808`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800029b8`
- `0x180007340`

## callees

- `0x18000290c`
- `0x180003038`
- `0x18000309c`
- `0x180003760`
- `0x180035e50`

## pseudocode

```c
__int64 __fastcall writeIndexTable(__int64 a1)
{
  __int64 v2; // rbp
  unsigned int v3; // esi
  __int64 v4; // r13
  int v5; // r14d
  int v6; // r15d
  unsigned __int64 v7; // rcx
  unsigned int v8; // r8d
  unsigned int m; // r10d
  unsigned __int64 v10; // r11
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r9
  __int64 v13; // rax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r11d
  unsigned int v18; // r9d
  unsigned int i; // r10d
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 j; // rcx
  unsigned int v23; // ebx
  unsigned int v24; // r14d
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // r8d
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // r12
  unsigned int v32; // r14d
  __int64 k; // r15
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // r8
  __int128 v38; // [rsp+20h] [rbp-78h]
  __int128 v39; // [rsp+30h] [rbp-68h]

  if ( !*(_QWORD *)(a1 + 34480) )
    return 0;
  v2 = *(_QWORD *)(a1 + 34368);
  v3 = 1;
  v4 = *(_QWORD *)(a1 + 34376);
  v5 = *(_DWORD *)(a1 + 16604);
  v6 = *(_DWORD *)(a1 + 34480);
  putBit16z(v2, 1, 16);
  v8 = *(_DWORD *)(a1 + 16604);
LABEL_3:
  if ( !v8 || *(_DWORD *)(a1 + 34360) )
  {
    v15 = *(unsigned __int8 *)(a1 + 34352);
    if ( (unsigned __int8)v15 < 2u )
      *(_DWORD *)(a1 + 164) = 0;
    if ( *(_DWORD *)(a1 + 164) )
    {
      v16 = 0;
      v17 = v15;
      v38 = 0;
      v39 = 0;
      if ( v15 > 1 )
      {
        v18 = (*(_DWORD *)(a1 + 16604) + 1) * (*(_DWORD *)(a1 + 216) + 1);
        do
        {
          for ( i = 0; i < v18; *((_QWORD *)&v38 + v20) += v21 )
          {
            if ( v16 <= 2 )
              v20 = v16 + 1;
            else
              v20 = 3;
            v21 = 0;
            if ( *(_QWORD *)(v4 + 8LL * (v16 + i * v17)) > 4u )
              v21 = *(_QWORD *)(v4 + 8LL * (v16 + i * v17));
            ++i;
          }
          ++v16;
        }
        while ( v16 + 1 < v17 );
      }
      for ( j = 0; j != 2; ++j )
        *((_QWORD *)&v39 + j) += *((_QWORD *)&v38 + j + 1);
      v23 = 0;
      v7 = (unsigned int)((*(_DWORD *)(a1 + 216) + 1) * (*(_DWORD *)(a1 + 16604) + 1));
      if ( (_DWORD)v7 )
      {
        do
        {
          v24 = 0;
          if ( *(_BYTE *)(a1 + 34352) )
          {
            do
            {
              writeIS(v7, v2);
              v25 = 3;
              v26 = 255;
              if ( v24 < 3 )
                v25 = v24;
              v27 = *((_QWORD *)&v38 + v25);
              if ( *(_QWORD *)(v4 + 8LL * (v24 + v23 * *(unsigned __int8 *)(a1 + 34352))) > 4u )
                v26 = 0;
              PutVLWordEsc(v2, v26, v27);
              v28 = *(unsigned __int8 *)(a1 + 34352);
              v29 = 3;
              if ( v24 < 3 )
                v29 = v24;
              v7 = *(_QWORD *)(v4 + 8LL * (v24 + v23 * *(unsigned __int8 *)(a1 + 34352)));
              v30 = 0;
              if ( v7 > 4 )
                v30 = *(_QWORD *)(v4 + 8LL * (v24 + v23 * *(unsigned __int8 *)(a1 + 34352)));
              ++v24;
              *((_QWORD *)&v38 + v29) += v30;
            }
            while ( v24 < v28 );
          }
          ++v23;
          v7 = (unsigned int)((*(_DWORD *)(a1 + 216) + 1) * (*(_DWORD *)(a1 + 16604) + 1));
        }
        while ( v23 < (unsigned int)v7 );
      }
    }
    else
    {
      v31 = 0;
      v32 = v6 * (v5 + 1);
      for ( k = 0; (unsigned int)k < v32; v31 += v35 )
      {
        writeIS(v7, v2);
        v34 = 255;
        if ( *(_QWORD *)(v4 + 8 * k) > 4u )
          v34 = 0;
        PutVLWordEsc(v2, v34, v31);
        v35 = 0;
        if ( *(_QWORD *)(v4 + 8 * k) > 4u )
          v35 = *(_QWORD *)(v4 + 8 * k);
        k = (unsigned int)(k + 1);
      }
    }
    writeIS(v7, v2);
    if ( *(_DWORD *)(a1 + 160) )
    {
      putBit16z(v2, 4, 16);
      putBit16z(v2, *(unsigned __int8 *)(a1 + 33020), 8);
      putBit16z(v2, *(unsigned __int8 *)(a1 + 33021), v36);
      putBit16z(v2, 0, 15);
      v37 = 1;
    }
    else
    {
      v3 = 255;
      v37 = 8;
    }
    putBit16z(v2, v3, v37);
    putBit16z(v2, 0, -*(_DWORD *)(v2 + 8) & 7);
    return 0;
  }
  for ( m = 0; ; ++m )
  {
    v10 = *(_QWORD *)(a1 + 34480);
    if ( m >= v10 )
    {
      --v8;
      goto LABEL_3;
    }
    v11 = m + v10 * v8;
    v12 = *(_QWORD *)(v4 + 8 * v11);
    v7 = m + v10 * (v8 - 1);
    v13 = *(_QWORD *)(a1 + 34376);
    if ( v12 < *(_QWORD *)(v13 + 8 * v7) )
      break;
    *(_QWORD *)(v4 + 8 * v11) = v12 - *(_QWORD *)(v13 + 8 * v7);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000309c  push    rbx
0x18000309e  push    rbp
0x18000309f  push    rsi
0x1800030a0  push    rdi
0x1800030a1  push    r12
0x1800030a3  push    r13
0x1800030a5  push    r14
0x1800030a7  push    r15
0x1800030a9  sub     rsp, 58h
0x1800030ad  mov     rax, cs:__security_cookie
0x1800030b4  xor     rax, rsp
0x1800030b7  mov     [rsp+98h+var_58], rax
0x1800030bc  cmp     qword ptr [rcx+86B0h], 0
0x1800030c4  mov     rdi, rcx
0x1800030c7  jbe     loc_1800033A4
0x1800030cd  mov     rbp, [rcx+8640h]
0x1800030d4  mov     esi, 1
0x1800030d9  mov     r13, [rcx+8648h]
0x1800030e0  mov     edx, esi
0x1800030e2  mov     r14d, [rcx+40DCh]
0x1800030e9  mov     r15d, [rcx+86B0h]
0x1800030f0  mov     rcx, rbp
0x1800030f3  lea     r8d, [rsi+0Fh]
0x1800030f7  call    putBit16z
0x1800030fc  mov     r8d, [rdi+40DCh]
0x180003103  test    r8d, r8d
0x180003106  jz      short loc_180003167
0x180003108  cmp     dword ptr [rdi+8638h], 0
0x18000310f  jnz     short loc_180003167
0x180003111  xor     r10d, r10d
0x180003114  lea     ebx, [r8-1]
0x180003118  mov     r11, [rdi+86B0h]
0x18000311f  mov     eax, r10d
0x180003122  cmp     rax, r11
0x180003125  jnb     short loc_18000315A
0x180003127  mov     edx, r8d
0x18000312a  imul    rdx, r11
0x18000312e  mov     ecx, ebx
0x180003130  add     rdx, rax
0x180003133  imul    rcx, r11
0x180003137  mov     r9, [r13+rdx*8+0]
0x18000313c  add     rcx, rax
0x18000313f  mov     rax, [rdi+8648h]
0x180003146  cmp     r9, [rax+rcx*8]
0x18000314a  jb      short loc_18000315F
0x18000314c  sub     r9, [rax+rcx*8]
0x180003150  mov     [r13+rdx*8+0], r9
0x180003155  add     r10d, esi
0x180003158  jmp     short loc_180003118
0x18000315a  mov     r8d, ebx
0x18000315d  jmp     short loc_180003103
0x18000315f  or      eax, 0FFFFFFFFh
0x180003162  jmp     loc_1800033A6
0x180003167  movzx   eax, byte ptr [rdi+8630h]
0x18000316e  cmp     al, 2
0x180003170  jnb     short loc_18000317C
0x180003172  mov     dword ptr [rdi+0A4h], 0
0x18000317c  cmp     dword ptr [rdi+0A4h], 0
0x180003183  jz      loc_1800032D3
0x180003189  xor     r8d, r8d
0x18000318c  xorps   xmm0, xmm0
0x18000318f  mov     r11d, eax
0x180003192  movups  [rsp+98h+var_78], xmm0
0x180003197  lea     r15d, [r8+3]
0x18000319b  movups  [rsp+98h+var_68], xmm0
0x1800031a0  cmp     eax, esi
0x1800031a2  jbe     short loc_180003203
0x1800031a4  mov     r9d, [rdi+0D8h]
0x1800031ab  mov     eax, [rdi+40DCh]
0x1800031b1  add     r9d, esi
0x1800031b4  add     eax, esi
0x1800031b6  imul    r9d, eax
0x1800031ba  xor     r10d, r10d
0x1800031bd  test    r9d, r9d
0x1800031c0  jz      short loc_1800031F7
0x1800031c2  cmp     r8d, 2
0x1800031c6  jbe     short loc_1800031CD
0x1800031c8  mov     ecx, r15d
0x1800031cb  jmp     short loc_1800031D1
0x1800031cd  lea     ecx, [r8+1]
0x1800031d1  mov     eax, r11d
0x1800031d4  imul    eax, r10d
0x1800031d8  add     eax, r8d
0x1800031db  mov     rdx, [r13+rax*8+0]
0x1800031e0  xor     eax, eax
0x1800031e2  cmp     rdx, 4
0x1800031e6  cmova   rax, rdx
0x1800031ea  add     r10d, esi
0x1800031ed  add     qword ptr [rsp+rcx*8+98h+var_78], rax
0x1800031f2  cmp     r10d, r9d
0x1800031f5  jb      short loc_1800031C2
0x1800031f7  add     r8d, esi
0x1800031fa  lea     eax, [r8+1]
0x1800031fe  cmp     eax, r11d
0x180003201  jb      short loc_1800031BA
0x180003203  xor     ecx, ecx
0x180003205  mov     rax, qword ptr [rsp+rcx*8+98h+var_78+8]
0x18000320a  add     qword ptr [rsp+rcx*8+98h+var_68], rax
0x18000320f  add     rcx, rsi
0x180003212  cmp     rcx, 2
0x180003216  jnz     short loc_180003205
0x180003218  mov     ecx, [rdi+40DCh]
0x18000321e  xor     ebx, ebx
0x180003220  mov     eax, [rdi+0D8h]
0x180003226  add     ecx, esi
0x180003228  add     eax, esi
0x18000322a  imul    ecx, eax
0x18000322d  test    ecx, ecx
0x18000322f  jz      loc_180003321
0x180003235  xor     r14d, r14d
0x180003238  cmp     [rdi+8630h], r14b
0x18000323f  jbe     short loc_1800032B4
0x180003241  mov     rdx, rbp
0x180003244  call    writeIS
0x180003249  movzx   ecx, byte ptr [rdi+8630h]
0x180003250  cmp     r14d, r15d
0x180003253  mov     r8d, r15d
0x180003256  mov     edx, 0FFh
0x18000325b  cmovb   r8d, r14d
0x18000325f  imul    ecx, ebx
0x180003262  xor     eax, eax
0x180003264  mov     r8, qword ptr [rsp+r8*8+98h+var_78]
0x180003269  add     ecx, r14d
0x18000326c  cmp     qword ptr [r13+rcx*8+0], 4
0x180003272  mov     rcx, rbp
0x180003275  cmova   edx, eax
0x180003278  call    PutVLWordEsc
0x18000327d  movzx   r8d, byte ptr [rdi+8630h]
0x180003285  cmp     r14d, r15d
0x180003288  mov     eax, r8d
0x18000328b  mov     edx, r15d
0x18000328e  cmovb   edx, r14d
0x180003292  imul    eax, ebx
0x180003295  add     eax, r14d
0x180003298  mov     rcx, [r13+rax*8+0]
0x18000329d  xor     eax, eax
0x18000329f  cmp     rcx, 4
0x1800032a3  cmova   rax, rcx
0x1800032a7  add     r14d, esi
0x1800032aa  add     qword ptr [rsp+rdx*8+98h+var_78], rax
0x1800032af  cmp     r14d, r8d
0x1800032b2  jb      short loc_180003241
0x1800032b4  mov     ecx, [rdi+40DCh]
0x1800032ba  add     ebx, esi
0x1800032bc  mov     eax, [rdi+0D8h]
0x1800032c2  add     ecx, esi
0x1800032c4  add     eax, esi
0x1800032c6  imul    ecx, eax
0x1800032c9  cmp     ebx, ecx
0x1800032cb  jb      loc_180003235
0x1800032d1  jmp     short loc_180003321
0x1800032d3  inc     r14d
0x1800032d6  xor     r12d, r12d
0x1800032d9  imul    r14d, r15d
0x1800032dd  xor     r15d, r15d
0x1800032e0  test    r14d, r14d
0x1800032e3  jz      short loc_180003321
0x1800032e5  mov     rdx, rbp
0x1800032e8  call    writeIS
0x1800032ed  xor     eax, eax
0x1800032ef  mov     edx, 0FFh
0x1800032f4  cmp     qword ptr [r13+r15*8+0], 4
0x1800032fa  mov     r8, r12
0x1800032fd  mov     rcx, rbp
0x180003300  cmova   edx, eax
0x180003303  call    PutVLWordEsc
0x180003308  xor     eax, eax
0x18000330a  cmp     qword ptr [r13+r15*8+0], 4
0x180003310  cmova   rax, [r13+r15*8+0]
0x180003316  add     r15d, esi
0x180003319  add     r12, rax
0x18000331c  cmp     r15d, r14d
0x18000331f  jb      short loc_1800032E5
0x180003321  mov     rdx, rbp
0x180003324  call    writeIS
0x180003329  cmp     dword ptr [rdi+0A0h], 0
0x180003330  jz      short loc_18000337A
0x180003332  mov     edx, 4
0x180003337  mov     rcx, rbp
0x18000333a  lea     r8d, [rdx+0Ch]
0x18000333e  call    putBit16z
0x180003343  movzx   edx, byte ptr [rdi+80FCh]
0x18000334a  mov     rcx, rbp
0x18000334d  mov     r8d, 8
0x180003353  call    putBit16z
0x180003358  movzx   edx, byte ptr [rdi+80FDh]
0x18000335f  mov     rcx, rbp
0x180003362  call    putBit16z
0x180003367  xor     edx, edx
0x180003369  mov     rcx, rbp
0x18000336c  lea     r8d, [rdx+0Fh]
0x180003370  call    putBit16z
0x180003375  mov     r8d, esi
0x180003378  jmp     short loc_180003385
0x18000337a  mov     esi, 0FFh
0x18000337f  mov     r8d, 8
0x180003385  mov     edx, esi
0x180003387  mov     rcx, rbp
0x18000338a  call    putBit16z
0x18000338f  mov     r8d, [rbp+8]
0x180003393  xor     edx, edx
0x180003395  neg     r8d
0x180003398  mov     rcx, rbp
0x18000339b  and     r8d, 7
0x18000339f  call    putBit16z
0x1800033a4  xor     eax, eax
0x1800033a6  mov     rcx, [rsp+98h+var_58]
0x1800033ab  xor     rcx, rsp; StackCookie
0x1800033ae  call    __security_check_cookie
0x1800033b3  add     rsp, 58h
0x1800033b7  pop     r15
0x1800033b9  pop     r14
0x1800033bb  pop     r13
0x1800033bd  pop     r12
0x1800033bf  pop     rdi
0x1800033c0  pop     rsi
0x1800033c1  pop     rbp
0x1800033c2  pop     rbx
0x1800033c3  retn
```
