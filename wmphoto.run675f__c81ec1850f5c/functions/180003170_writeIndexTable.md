# writeIndexTable

- ea: `0x180003170`
- end: `0x180003499`
- name: `writeIndexTable`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a50`
- `0x180007400`

## callees

- `0x1800029a4`
- `0x180003108`
- `0x180003170`
- `0x180003830`
- `0x180036420`

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
0x180003170  push    rbx
0x180003172  push    rbp
0x180003173  push    rsi
0x180003174  push    rdi
0x180003175  push    r12
0x180003177  push    r13
0x180003179  push    r14
0x18000317b  push    r15
0x18000317d  sub     rsp, 58h
0x180003181  mov     rax, cs:__security_cookie
0x180003188  xor     rax, rsp
0x18000318b  mov     [rsp+98h+var_58], rax
0x180003190  cmp     qword ptr [rcx+86B0h], 0
0x180003198  mov     rdi, rcx
0x18000319b  jbe     loc_180003478
0x1800031a1  mov     rbp, [rcx+8640h]
0x1800031a8  mov     esi, 1
0x1800031ad  mov     r13, [rcx+8648h]
0x1800031b4  mov     edx, esi
0x1800031b6  mov     r14d, [rcx+40DCh]
0x1800031bd  mov     r15d, [rcx+86B0h]
0x1800031c4  mov     rcx, rbp
0x1800031c7  lea     r8d, [rsi+0Fh]
0x1800031cb  call    putBit16z
0x1800031d0  mov     r8d, [rdi+40DCh]
0x1800031d7  test    r8d, r8d
0x1800031da  jz      short loc_18000323B
0x1800031dc  cmp     dword ptr [rdi+8638h], 0
0x1800031e3  jnz     short loc_18000323B
0x1800031e5  xor     r10d, r10d
0x1800031e8  lea     ebx, [r8-1]
0x1800031ec  mov     r11, [rdi+86B0h]
0x1800031f3  mov     eax, r10d
0x1800031f6  cmp     rax, r11
0x1800031f9  jnb     short loc_18000322E
0x1800031fb  mov     edx, r8d
0x1800031fe  imul    rdx, r11
0x180003202  mov     ecx, ebx
0x180003204  add     rdx, rax
0x180003207  imul    rcx, r11
0x18000320b  mov     r9, [r13+rdx*8+0]
0x180003210  add     rcx, rax
0x180003213  mov     rax, [rdi+8648h]
0x18000321a  cmp     r9, [rax+rcx*8]
0x18000321e  jb      short loc_180003233
0x180003220  sub     r9, [rax+rcx*8]
0x180003224  mov     [r13+rdx*8+0], r9
0x180003229  add     r10d, esi
0x18000322c  jmp     short loc_1800031EC
0x18000322e  mov     r8d, ebx
0x180003231  jmp     short loc_1800031D7
0x180003233  or      eax, 0FFFFFFFFh
0x180003236  jmp     loc_18000347A
0x18000323b  movzx   eax, byte ptr [rdi+8630h]
0x180003242  cmp     al, 2
0x180003244  jnb     short loc_180003250
0x180003246  mov     dword ptr [rdi+0A4h], 0
0x180003250  cmp     dword ptr [rdi+0A4h], 0
0x180003257  jz      loc_1800033A7
0x18000325d  xor     r8d, r8d
0x180003260  xorps   xmm0, xmm0
0x180003263  mov     r11d, eax
0x180003266  movups  [rsp+98h+var_78], xmm0
0x18000326b  lea     r15d, [r8+3]
0x18000326f  movups  [rsp+98h+var_68], xmm0
0x180003274  cmp     eax, esi
0x180003276  jbe     short loc_1800032D7
0x180003278  mov     r9d, [rdi+0D8h]
0x18000327f  mov     eax, [rdi+40DCh]
0x180003285  add     r9d, esi
0x180003288  add     eax, esi
0x18000328a  imul    r9d, eax
0x18000328e  xor     r10d, r10d
0x180003291  test    r9d, r9d
0x180003294  jz      short loc_1800032CB
0x180003296  cmp     r8d, 2
0x18000329a  jbe     short loc_1800032A1
0x18000329c  mov     ecx, r15d
0x18000329f  jmp     short loc_1800032A5
0x1800032a1  lea     ecx, [r8+1]
0x1800032a5  mov     eax, r11d
0x1800032a8  imul    eax, r10d
0x1800032ac  add     eax, r8d
0x1800032af  mov     rdx, [r13+rax*8+0]
0x1800032b4  xor     eax, eax
0x1800032b6  cmp     rdx, 4
0x1800032ba  cmova   rax, rdx
0x1800032be  add     r10d, esi
0x1800032c1  add     qword ptr [rsp+rcx*8+98h+var_78], rax
0x1800032c6  cmp     r10d, r9d
0x1800032c9  jb      short loc_180003296
0x1800032cb  add     r8d, esi
0x1800032ce  lea     eax, [r8+1]
0x1800032d2  cmp     eax, r11d
0x1800032d5  jb      short loc_18000328E
0x1800032d7  xor     ecx, ecx
0x1800032d9  mov     rax, qword ptr [rsp+rcx*8+98h+var_78+8]
0x1800032de  add     qword ptr [rsp+rcx*8+98h+var_68], rax
0x1800032e3  add     rcx, rsi
0x1800032e6  cmp     rcx, 2
0x1800032ea  jnz     short loc_1800032D9
0x1800032ec  mov     ecx, [rdi+40DCh]
0x1800032f2  xor     ebx, ebx
0x1800032f4  mov     eax, [rdi+0D8h]
0x1800032fa  add     ecx, esi
0x1800032fc  add     eax, esi
0x1800032fe  imul    ecx, eax
0x180003301  test    ecx, ecx
0x180003303  jz      loc_1800033F5
0x180003309  xor     r14d, r14d
0x18000330c  cmp     [rdi+8630h], r14b
0x180003313  jbe     short loc_180003388
0x180003315  mov     rdx, rbp
0x180003318  call    writeIS
0x18000331d  movzx   ecx, byte ptr [rdi+8630h]
0x180003324  cmp     r14d, r15d
0x180003327  mov     r8d, r15d
0x18000332a  mov     edx, 0FFh
0x18000332f  cmovb   r8d, r14d
0x180003333  imul    ecx, ebx
0x180003336  xor     eax, eax
0x180003338  mov     r8, qword ptr [rsp+r8*8+98h+var_78]
0x18000333d  add     ecx, r14d
0x180003340  cmp     qword ptr [r13+rcx*8+0], 4
0x180003346  mov     rcx, rbp
0x180003349  cmova   edx, eax
0x18000334c  call    PutVLWordEsc
0x180003351  movzx   r8d, byte ptr [rdi+8630h]
0x180003359  cmp     r14d, r15d
0x18000335c  mov     eax, r8d
0x18000335f  mov     edx, r15d
0x180003362  cmovb   edx, r14d
0x180003366  imul    eax, ebx
0x180003369  add     eax, r14d
0x18000336c  mov     rcx, [r13+rax*8+0]
0x180003371  xor     eax, eax
0x180003373  cmp     rcx, 4
0x180003377  cmova   rax, rcx
0x18000337b  add     r14d, esi
0x18000337e  add     qword ptr [rsp+rdx*8+98h+var_78], rax
0x180003383  cmp     r14d, r8d
0x180003386  jb      short loc_180003315
0x180003388  mov     ecx, [rdi+40DCh]
0x18000338e  add     ebx, esi
0x180003390  mov     eax, [rdi+0D8h]
0x180003396  add     ecx, esi
0x180003398  add     eax, esi
0x18000339a  imul    ecx, eax
0x18000339d  cmp     ebx, ecx
0x18000339f  jb      loc_180003309
0x1800033a5  jmp     short loc_1800033F5
0x1800033a7  inc     r14d
0x1800033aa  xor     r12d, r12d
0x1800033ad  imul    r14d, r15d
0x1800033b1  xor     r15d, r15d
0x1800033b4  test    r14d, r14d
0x1800033b7  jz      short loc_1800033F5
0x1800033b9  mov     rdx, rbp
0x1800033bc  call    writeIS
0x1800033c1  xor     eax, eax
0x1800033c3  mov     edx, 0FFh
0x1800033c8  cmp     qword ptr [r13+r15*8+0], 4
0x1800033ce  mov     r8, r12
0x1800033d1  mov     rcx, rbp
0x1800033d4  cmova   edx, eax
0x1800033d7  call    PutVLWordEsc
0x1800033dc  xor     eax, eax
0x1800033de  cmp     qword ptr [r13+r15*8+0], 4
0x1800033e4  cmova   rax, [r13+r15*8+0]
0x1800033ea  add     r15d, esi
0x1800033ed  add     r12, rax
0x1800033f0  cmp     r15d, r14d
0x1800033f3  jb      short loc_1800033B9
0x1800033f5  mov     rdx, rbp
0x1800033f8  call    writeIS
0x1800033fd  cmp     dword ptr [rdi+0A0h], 0
0x180003404  jz      short loc_18000344E
0x180003406  mov     edx, 4
0x18000340b  mov     rcx, rbp
0x18000340e  lea     r8d, [rdx+0Ch]
0x180003412  call    putBit16z
0x180003417  movzx   edx, byte ptr [rdi+80FCh]
0x18000341e  mov     rcx, rbp
0x180003421  mov     r8d, 8
0x180003427  call    putBit16z
0x18000342c  movzx   edx, byte ptr [rdi+80FDh]
0x180003433  mov     rcx, rbp
0x180003436  call    putBit16z
0x18000343b  xor     edx, edx
0x18000343d  mov     rcx, rbp
0x180003440  lea     r8d, [rdx+0Fh]
0x180003444  call    putBit16z
0x180003449  mov     r8d, esi
0x18000344c  jmp     short loc_180003459
0x18000344e  mov     esi, 0FFh
0x180003453  mov     r8d, 8
0x180003459  mov     edx, esi
0x18000345b  mov     rcx, rbp
0x18000345e  call    putBit16z
0x180003463  mov     r8d, [rbp+8]
0x180003467  xor     edx, edx
0x180003469  neg     r8d
0x18000346c  mov     rcx, rbp
0x18000346f  and     r8d, 7
0x180003473  call    putBit16z
0x180003478  xor     eax, eax
0x18000347a  mov     rcx, [rsp+98h+var_58]
0x18000347f  xor     rcx, rsp; StackCookie
0x180003482  call    __security_check_cookie
0x180003487  add     rsp, 58h
0x18000348b  pop     r15
0x18000348d  pop     r14
0x18000348f  pop     r13
0x180003491  pop     r12
0x180003493  pop     rdi
0x180003494  pop     rsi
0x180003495  pop     rbp
0x180003496  pop     rbx
0x180003497  retn
```
