# RtlpCopyXStateChunk

- ea: `0x1400d8ff4`
- end: `0x1400d9275`
- name: `RtlpCopyXStateChunk`
- size: `641`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400d85cc`
- `0x1400fd9b8`

## callees

- `0x1400d6de4`
- `0x1400d8ff4`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall RtlpCopyXStateChunk(char a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, unsigned int a6)
{
  unsigned int v6; // r13d
  __int64 XStateConfiguration2; // rax
  __int64 v9; // r8
  __int64 v10; // r11
  __int64 v11; // r10
  __int64 v12; // r9
  _QWORD *v13; // r10
  __int64 v14; // r9
  unsigned __int64 v15; // rbx
  unsigned int v16; // edi
  unsigned __int64 *v17; // r15
  __int64 v18; // rsi
  unsigned __int64 v19; // rdx
  __int64 v20; // r11
  __int64 v21; // rbp
  __int64 v22; // r10
  unsigned __int64 v23; // rcx
  unsigned int v25; // ebx
  unsigned int v26; // r12d
  unsigned int v27; // r14d
  __int64 v28; // rdx
  char v29; // r15
  unsigned int v30; // [rsp+20h] [rbp-78h]
  unsigned __int64 v31; // [rsp+28h] [rbp-70h]
  __int64 v32; // [rsp+30h] [rbp-68h]
  __int64 v33; // [rsp+38h] [rbp-60h]
  _QWORD *v34; // [rsp+40h] [rbp-58h]
  unsigned __int64 *v35; // [rsp+48h] [rbp-50h]
  unsigned int v36; // [rsp+B0h] [rbp+18h]
  char v37; // [rsp+C0h] [rbp+28h]

  v6 = 64;
  v36 = *(_DWORD *)(a3 + 20);
  if ( v36 < 0x40 )
    return 2147483653LL;
  v30 = *(_DWORD *)(a5 + 20);
  if ( v30 < 0x40 )
    return 2147483653LL;
  XStateConfiguration2 = RtlpGetXStateConfiguration2(a6);
  v13 = (_QWORD *)(v12 + *(int *)(v11 + 16));
  v32 = XStateConfiguration2;
  v34 = v13;
  v14 = XStateConfiguration2;
  v15 = *v13 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( (~(*(_QWORD *)XStateConfiguration2 | *(_QWORD *)(XStateConfiguration2 + 536)) & v15) != 0 )
    return 3221225485LL;
  v16 = 2;
  v17 = (unsigned __int64 *)(v10 + *(int *)(v9 + 16));
  v35 = v17;
  if ( (*(_DWORD *)(XStateConfiguration2 + 20) & 2) == 0 )
  {
    v18 = 0;
    v33 = 0;
    v37 = 0;
LABEL_14:
    v31 = *v13 & 0xFFFFFFFFFFFFFFFCuLL;
    memset_0(v17, 0, 0x40u);
    v14 = v32;
    v23 = v15;
    v20 = v33;
    v22 = v15;
    v17[1] = v18;
    v21 = v18;
    goto LABEL_15;
  }
  v18 = v13[1];
  v19 = *(_QWORD *)XStateConfiguration2 | *(_QWORD *)(XStateConfiguration2 + 536) | 0x8000000000000003uLL;
  if ( (~v19 & v18) != 0 || v18 >= 0 || (v15 & ~v18) != 0 )
    return 3221225485LL;
  v20 = *(_QWORD *)(XStateConfiguration2 + 544);
  v33 = v20;
  v37 = 1;
  if ( (a1 & 2) != 0 )
    goto LABEL_14;
  v21 = v17[1];
  if ( v21 >= 0 || (v21 & *v17) != *v17 || (v19 & v21) != v21 )
    goto LABEL_14;
  v22 = v21 & v15;
  v31 = v21 & v15;
  v23 = v21 & v15 | ~v18 & *v17;
LABEL_15:
  *v17 = v23;
  if ( (a1 & 1) == 0 )
  {
    v25 = 64;
    v26 = 64;
    v27 = 64;
    while ( v22 && v16 < 0x40 )
    {
      v28 = 1LL << v16;
      if ( v37 )
      {
        if ( (v28 & v18) != 0 )
        {
          if ( (v28 & v20) != 0 )
            v25 = (v6 + 63) & 0xFFFFFFC0;
          else
            v25 = v6;
          v29 = v16;
          v6 = v25 + *(_DWORD *)(v14 + 4LL * v16 + 556);
        }
        else
        {
          v29 = v16;
        }
        if ( (v28 & v21) != 0 )
        {
          if ( (v28 & v20) != 0 )
            v27 = (v26 + 63) & 0xFFFFFFC0;
          else
            v27 = v26;
          v26 = v27 + *(_DWORD *)(v14 + 4LL * v16 + 556);
        }
      }
      else
      {
        v29 = v16;
        v25 = *(_DWORD *)(v14 + 8LL * v16 + 24) - 512;
        v26 = v25 + *(_DWORD *)(v14 + 8LL * v16 + 28);
        v27 = v25;
        v6 = v26;
      }
      if ( (v28 & v22) != 0 )
      {
        if ( v26 > v36 || v6 > v30 )
          return 2147483653LL;
        memmove((char *)v35 + v27, (char *)v34 + v25, v6 - v25);
        v22 = v31 & ~(1LL << v29);
        v31 = v22;
      }
      v14 = v32;
      ++v16;
      v20 = v33;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400d8ff4  push    rbx
0x1400d8ff6  push    rbp
0x1400d8ff7  push    rsi
0x1400d8ff8  push    rdi
0x1400d8ff9  push    r12
0x1400d8ffb  push    r13
0x1400d8ffd  push    r14
0x1400d8fff  push    r15
0x1400d9001  sub     rsp, 58h
0x1400d9005  mov     eax, [r8+14h]
0x1400d9009  mov     r13d, 40h ; '@'
0x1400d900f  mov     [rsp+98h+arg_10], eax
0x1400d9016  mov     r11, rdx
0x1400d9019  mov     r14d, ecx
0x1400d901c  cmp     eax, r13d
0x1400d901f  jb      loc_1400D925E
0x1400d9025  mov     r10, [rsp+98h+arg_20]
0x1400d902d  mov     eax, [r10+14h]
0x1400d9031  mov     [rsp+98h+var_78], eax
0x1400d9035  cmp     eax, r13d
0x1400d9038  jb      loc_1400D925E
0x1400d903e  mov     ecx, [rsp+98h+arg_28]
0x1400d9045  call    RtlpGetXStateConfiguration2
0x1400d904a  movsxd  r10, dword ptr [r10+10h]
0x1400d904e  add     r10, r9
0x1400d9051  mov     [rsp+98h+var_68], rax
0x1400d9056  mov     [rsp+98h+var_58], r10
0x1400d905b  mov     r9, rax
0x1400d905e  mov     rdx, [rax+218h]
0x1400d9065  or      rdx, [rax]
0x1400d9068  mov     rbx, [r10]
0x1400d906b  mov     rcx, rdx
0x1400d906e  not     rcx
0x1400d9071  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400d9075  test    rbx, rcx
0x1400d9078  jnz     loc_1400D9257
0x1400d907e  movsxd  r15, dword ptr [r8+10h]
0x1400d9082  lea     edi, [r13-3Eh]
0x1400d9086  mov     eax, [rax+14h]
0x1400d9089  add     r15, r11
0x1400d908c  mov     [rsp+98h+var_50], r15
0x1400d9091  test    dil, al
0x1400d9094  jz      loc_1400D9120
0x1400d909a  mov     rsi, [r10+8]
0x1400d909e  mov     rax, 8000000000000003h
0x1400d90a8  or      rdx, rax
0x1400d90ab  mov     rax, rdx
0x1400d90ae  not     rax
0x1400d90b1  test    rsi, rax
0x1400d90b4  jnz     loc_1400D9257
0x1400d90ba  test    rsi, rsi
0x1400d90bd  jns     loc_1400D9257
0x1400d90c3  mov     r8, rsi
0x1400d90c6  not     r8
0x1400d90c9  test    r8, rbx
0x1400d90cc  jnz     loc_1400D9257
0x1400d90d2  mov     r11, [r9+220h]
0x1400d90d9  mov     [rsp+98h+var_60], r11
0x1400d90de  mov     byte ptr [rsp+98h+arg_20], 1
0x1400d90e6  test    dil, r14b
0x1400d90e9  jnz     short loc_1400D9133
0x1400d90eb  mov     rbp, [r15+8]
0x1400d90ef  test    rbp, rbp
0x1400d90f2  jns     short loc_1400D9133
0x1400d90f4  mov     rcx, [r15]
0x1400d90f7  mov     rax, rcx
0x1400d90fa  and     rax, rbp
0x1400d90fd  cmp     rax, rcx
0x1400d9100  jnz     short loc_1400D9133
0x1400d9102  mov     rax, rbp
0x1400d9105  and     rax, rdx
0x1400d9108  cmp     rax, rbp
0x1400d910b  jnz     short loc_1400D9133
0x1400d910d  and     rbx, rbp
0x1400d9110  and     rcx, r8
0x1400d9113  mov     r10, rbx
0x1400d9116  mov     [rsp+98h+var_70], rbx
0x1400d911b  or      rcx, rbx
0x1400d911e  jmp     short loc_1400D915C
0x1400d9120  xor     esi, esi
0x1400d9122  mov     [rsp+98h+var_60], 0
0x1400d912b  mov     byte ptr [rsp+98h+arg_20], sil
0x1400d9133  mov     r8, r13; Size
0x1400d9136  mov     [rsp+98h+var_70], rbx
0x1400d913b  xor     edx, edx; Val
0x1400d913d  mov     rcx, r15; void *
0x1400d9140  call    memset_0
0x1400d9145  mov     r9, [rsp+98h+var_68]
0x1400d914a  mov     rcx, rbx
0x1400d914d  mov     r11, [rsp+98h+var_60]
0x1400d9152  mov     r10, rbx
0x1400d9155  mov     [r15+8], rsi
0x1400d9159  mov     rbp, rsi
0x1400d915c  mov     [r15], rcx
0x1400d915f  test    r14b, 1
0x1400d9163  jz      short loc_1400D916C
0x1400d9165  xor     eax, eax
0x1400d9167  jmp     loc_1400D9263
0x1400d916c  mov     ebx, r13d
0x1400d916f  mov     r12d, r13d
0x1400d9172  mov     r14d, ebx
0x1400d9175  jmp     loc_1400D9249
0x1400d917a  cmp     edi, 40h ; '@'
0x1400d917d  jnb     short loc_1400D9165
0x1400d917f  mov     ecx, edi
0x1400d9181  mov     edx, 1
0x1400d9186  shl     rdx, cl
0x1400d9189  cmp     byte ptr [rsp+98h+arg_20], 0
0x1400d9191  jz      short loc_1400D91E3
0x1400d9193  test    rsi, rdx
0x1400d9196  jz      short loc_1400D91B9
0x1400d9198  test    r11, rdx
0x1400d919b  jz      short loc_1400D91A6
0x1400d919d  lea     ebx, [r13+3Fh]
0x1400d91a1  and     ebx, 0FFFFFFC0h
0x1400d91a4  jmp     short loc_1400D91A9
0x1400d91a6  mov     ebx, r13d
0x1400d91a9  mov     r15d, edi
0x1400d91ac  mov     r13d, [r9+r15*4+22Ch]
0x1400d91b4  add     r13d, ebx
0x1400d91b7  jmp     short loc_1400D91BC
0x1400d91b9  mov     r15d, edi
0x1400d91bc  test    rbp, rdx
0x1400d91bf  jz      short loc_1400D91FF
0x1400d91c1  test    r11, rdx
0x1400d91c4  jz      short loc_1400D91D1
0x1400d91c6  lea     r14d, [r12+3Fh]
0x1400d91cb  and     r14d, 0FFFFFFC0h
0x1400d91cf  jmp     short loc_1400D91D4
0x1400d91d1  mov     r14d, r12d
0x1400d91d4  mov     eax, edi
0x1400d91d6  mov     r12d, [r9+rax*4+22Ch]
0x1400d91de  add     r12d, r14d
0x1400d91e1  jmp     short loc_1400D91FF
0x1400d91e3  mov     r15d, edi
0x1400d91e6  mov     ebx, [r9+r15*8+18h]
0x1400d91eb  mov     r12d, [r9+r15*8+1Ch]
0x1400d91f0  add     ebx, 0FFFFFE00h
0x1400d91f6  add     r12d, ebx
0x1400d91f9  mov     r14d, ebx
0x1400d91fc  mov     r13d, r12d
0x1400d91ff  test    r10, rdx
0x1400d9202  jz      short loc_1400D923D
0x1400d9204  cmp     r12d, [rsp+98h+arg_10]
0x1400d920c  ja      short loc_1400D925E
0x1400d920e  cmp     r13d, [rsp+98h+var_78]
0x1400d9213  ja      short loc_1400D925E
0x1400d9215  mov     r8d, r13d
0x1400d9218  mov     edx, ebx
0x1400d921a  add     rdx, [rsp+98h+var_58]; Src
0x1400d921f  sub     r8d, ebx; Size
0x1400d9222  mov     ecx, r14d
0x1400d9225  add     rcx, [rsp+98h+var_50]; void *
0x1400d922a  call    memmove
0x1400d922f  mov     r10, [rsp+98h+var_70]
0x1400d9234  btr     r10, r15
0x1400d9238  mov     [rsp+98h+var_70], r10
0x1400d923d  mov     r9, [rsp+98h+var_68]
0x1400d9242  inc     edi
0x1400d9244  mov     r11, [rsp+98h+var_60]
0x1400d9249  test    r10, r10
0x1400d924c  jnz     loc_1400D917A
0x1400d9252  jmp     loc_1400D9165
0x1400d9257  mov     eax, 0C000000Dh
0x1400d925c  jmp     short loc_1400D9263
0x1400d925e  mov     eax, 80000005h
0x1400d9263  add     rsp, 58h
0x1400d9267  pop     r15
0x1400d9269  pop     r14
0x1400d926b  pop     r13
0x1400d926d  pop     r12
0x1400d926f  pop     rdi
0x1400d9270  pop     rsi
0x1400d9271  pop     rbp
0x1400d9272  pop     rbx
0x1400d9273  retn
```
