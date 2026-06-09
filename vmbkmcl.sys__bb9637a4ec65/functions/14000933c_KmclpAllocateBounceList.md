# KmclpAllocateBounceList

- ea: `0x14000933c`
- end: `0x1400095fc`
- name: `KmclpAllocateBounceList`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000a2f4`

## callees

- `0x14000933c`
- `0x1400097ec`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400093b3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400093b3`
- `HAL!KeQueryPerformanceCounter` at `0x140009369`
- `HAL!KeQueryPerformanceCounter` at `0x140009583`
- `HAL!KeQueryPerformanceCounter` at `0x140009369`
- `HAL!KeQueryPerformanceCounter` at `0x140009583`

## pseudocode

```c
__int64 __fastcall KmclpAllocateBounceList(__int64 a1, __int64 a2)
{
  char v2; // al
  _QWORD *v3; // r15
  LARGE_INTEGER PerformanceCounter; // rbx
  unsigned int v7; // esi
  unsigned int v8; // r12d
  __int64 *v9; // r14
  unsigned int v10; // eax
  _DWORD *v11; // rax
  _DWORD *v12; // r8
  unsigned int v13; // edx
  char *v14; // r13
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  unsigned __int64 v17; // r9
  char **v18; // r10
  _DWORD *v19; // rcx
  char *v20; // rax
  char *v21; // r11
  char **v22; // r11
  __int64 v23; // rax
  _QWORD *v24; // r10
  _QWORD *v25; // rsi
  _QWORD *v26; // rax
  int v27; // esi
  LONGLONG v28; // rax
  char v30; // [rsp+78h] [rbp+10h]

  v2 = 0;
  v3 = 0;
  PerformanceCounter.QuadPart = 0;
  v30 = 0;
  if ( KmclPerformanceCounterTimingCounters )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v2 = 0;
  }
  v7 = *(_DWORD *)(a2 + 72);
  v8 = *(_DWORD *)(a2 + 76);
  v9 = *(__int64 **)(a2 + 64);
  while ( 1 )
  {
    if ( !v9 || v2 )
    {
      ++*(_QWORD *)(a1 + 560);
      v27 = 0;
      goto LABEL_42;
    }
    v10 = *((_DWORD *)v9 + 10);
    if ( v7 >= v10 )
    {
      v7 -= v10;
      goto LABEL_34;
    }
    v11 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 2944));
    v12 = v11;
    if ( !v11 )
      break;
    v13 = *((_DWORD *)v9 + 10) - v7;
    if ( v8 )
    {
      if ( (*(_BYTE *)(a2 + 62) & 1) != 0 || v8 <= v13 )
      {
        v13 = v8;
        v30 = 1;
      }
      else
      {
        v8 -= v13;
      }
    }
    *(_QWORD *)v11 = 0;
    v14 = (char *)(v11 + 4);
    v11[2] = v13;
    v11[3] = ((_WORD)v7 + (unsigned __int16)*((_DWORD *)v9 + 11)) & 0xFFF;
    *((_QWORD *)v11 + 3) = v11 + 4;
    *((_QWORD *)v11 + 2) = v11 + 4;
    if ( v3 )
      *v3 = v11;
    else
      *(_QWORD *)(a2 + 80) = v11;
    v15 = (_QWORD *)(a1 + 2904);
    v16 = *(_QWORD **)(a1 + 2904);
    v17 = ((v12[3] & 0xFFF) + (unsigned __int64)(unsigned int)v12[2] + 4095) >> 12;
    if ( v16 != (_QWORD *)(a1 + 2904) )
    {
      while ( v16 != v15 )
      {
        v18 = (char **)(v16 + 2);
        v19 = v16 + 5;
        while ( 1 )
        {
          v20 = *v18;
          if ( *v18 == (char *)v18 )
            break;
          v19 = v16 + 5;
          if ( !(_DWORD)v17 )
            break;
          v19 = v16 + 5;
          v16[7] = 0;
          ++*((_DWORD *)v16 + 10);
          if ( *((char ***)v20 + 1) != v18 )
            goto LABEL_35;
          v21 = *(char **)v20;
          if ( *(char **)(*(_QWORD *)v20 + 8LL) != v20 )
            goto LABEL_35;
          *v18 = v21;
          *((_QWORD *)v21 + 1) = v18;
          v22 = (char **)*((_QWORD *)v12 + 3);
          if ( *v22 != v14 )
            goto LABEL_35;
          *(_QWORD *)v20 = v14;
          LODWORD(v17) = v17 - 1;
          *((_QWORD *)v20 + 1) = v22;
          *v22 = v20;
          *((_QWORD *)v12 + 3) = v20;
        }
        if ( *v19 == *((_DWORD *)v16 + 11) )
        {
          v23 = *v16;
          if ( *(_QWORD **)(*v16 + 8LL) != v16
            || (v24 = (_QWORD *)v16[1], (_QWORD *)*v24 != v16)
            || (*v24 = v23, *(_QWORD *)(v23 + 8) = v24, v25 = *(_QWORD **)(a1 + 2928), *v25 != a1 + 2920) )
          {
LABEL_35:
            __fastfail(3u);
          }
          v26 = v16;
          v16[1] = v25;
          v16 = v24;
          *v26 = a1 + 2920;
          *v25 = v26;
          *(_QWORD *)(a1 + 2928) = v26;
          *((_BYTE *)v26 + 50) = 1;
        }
        if ( !(_DWORD)v17 )
          break;
        v16 = (_QWORD *)*v16;
        v15 = (_QWORD *)(a1 + 2904);
      }
    }
    v7 = 0;
    v3 = v12;
    if ( (_DWORD)v17 )
    {
      v27 = -1073741801;
      goto LABEL_38;
    }
LABEL_34:
    v9 = (__int64 *)*v9;
    v2 = v30;
  }
  v27 = -1073741670;
LABEL_38:
  if ( *(_QWORD *)(a2 + 80) )
    KmclpFreeBounceList(a1);
  *(_QWORD *)(a2 + 80) = 0;
  ++*(_QWORD *)(a1 + 568);
LABEL_42:
  if ( KmclPerformanceCounterTimingCounters )
  {
    v28 = *(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart;
    if ( (unsigned __int64)v28 > *(_QWORD *)(a1 + 584) )
      *(_QWORD *)(a1 + 584) = v28;
    if ( (unsigned __int64)v28 < *(_QWORD *)(a1 + 592) )
      *(_QWORD *)(a1 + 592) = v28;
    if ( v27 < 0 )
    {
      *(__m128i *)(a1 + 624) = _mm_add_epi64(
                                 _mm_unpacklo_epi64((__m128i)1uLL, (__m128i)(unsigned __int64)v28),
                                 _mm_loadu_si128((const __m128i *)(a1 + 624)));
    }
    else
    {
      ++*(_QWORD *)(a1 + 616);
      *(_QWORD *)(a1 + 640) += v28;
    }
  }
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x14000933c  push    rbx
0x14000933e  push    rbp
0x14000933f  push    rsi
0x140009340  push    rdi
0x140009341  push    r12
0x140009343  push    r13
0x140009345  push    r14
0x140009347  push    r15
0x140009349  sub     rsp, 28h
0x14000934d  xor     al, al
0x14000934f  xor     r15d, r15d
0x140009352  xor     ebx, ebx
0x140009354  mov     [rsp+68h+arg_8], al
0x140009358  cmp     cs:KmclPerformanceCounterTimingCounters, rbx
0x14000935f  mov     rbp, rdx
0x140009362  mov     rdi, rcx
0x140009365  jz      short loc_14000937B
0x140009367  xor     ecx, ecx; PerformanceFrequency
0x140009369  call    cs:__imp_KeQueryPerformanceCounter
0x140009370  nop     dword ptr [rax+rax+00h]
0x140009375  mov     rbx, rax
0x140009378  mov     al, r15b
0x14000937b  mov     esi, [rbp+48h]
0x14000937e  mov     r13d, 1
0x140009384  mov     r12d, [rbp+4Ch]
0x140009388  mov     r14, [rbp+40h]
0x14000938c  test    r14, r14
0x14000938f  jz      loc_14000956E
0x140009395  test    al, al
0x140009397  jnz     loc_14000956E
0x14000939d  mov     eax, [r14+28h]
0x1400093a1  cmp     esi, eax
0x1400093a3  jb      short loc_1400093AC
0x1400093a5  sub     esi, eax
0x1400093a7  jmp     loc_14000952D
0x1400093ac  lea     rcx, [rdi+0B80h]; Lookaside
0x1400093b3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400093ba  nop     dword ptr [rax+rax+00h]
0x1400093bf  mov     r8, rax
0x1400093c2  test    rax, rax
0x1400093c5  jz      loc_140009547
0x1400093cb  mov     edx, [r14+28h]
0x1400093cf  sub     edx, esi
0x1400093d1  test    r12d, r12d
0x1400093d4  jz      short loc_1400093EE
0x1400093d6  test    [rbp+3Eh], r13b
0x1400093da  jnz     short loc_1400093E6
0x1400093dc  cmp     r12d, edx
0x1400093df  jbe     short loc_1400093E6
0x1400093e1  sub     r12d, edx
0x1400093e4  jmp     short loc_1400093EE
0x1400093e6  mov     edx, r12d
0x1400093e9  mov     [rsp+68h+arg_8], r13b
0x1400093ee  mov     qword ptr [rax], 0
0x1400093f5  lea     r13, [r8+10h]
0x1400093f9  mov     [rax+8], edx
0x1400093fc  mov     eax, [r14+2Ch]
0x140009400  add     eax, esi
0x140009402  and     eax, 0FFFh
0x140009407  mov     [r8+0Ch], eax
0x14000940b  mov     [r8+18h], r13
0x14000940f  mov     [r13+0], r13
0x140009413  test    r15, r15
0x140009416  jz      short loc_14000941D
0x140009418  mov     [r15], r8
0x14000941b  jmp     short loc_140009421
0x14000941d  mov     [rbp+50h], r8
0x140009421  mov     ecx, [r8+0Ch]
0x140009425  lea     rax, [rdi+0B58h]
0x14000942c  mov     r9d, [r8+8]
0x140009430  and     ecx, 0FFFh
0x140009436  mov     rdx, [rax]
0x140009439  add     r9, 0FFFh
0x140009440  add     r9, rcx
0x140009443  shr     r9, 0Ch
0x140009447  cmp     rdx, rax
0x14000944a  jz      loc_14000951F
0x140009450  cmp     rdx, rax
0x140009453  jz      loc_14000951F
0x140009459  lea     r10, [rdx+10h]
0x14000945d  lea     rcx, [rdx+28h]
0x140009461  mov     rax, [r10]
0x140009464  cmp     rax, r10
0x140009467  jz      short loc_1400094BE
0x140009469  lea     rcx, [rdx+28h]
0x14000946d  test    r9d, r9d
0x140009470  jz      short loc_1400094BE
0x140009472  lea     rcx, [rdx+28h]
0x140009476  mov     qword ptr [rdx+38h], 0
0x14000947e  inc     dword ptr [rcx]
0x140009480  cmp     [rax+8], r10
0x140009484  jnz     loc_140009539
0x14000948a  mov     r11, [rax]
0x14000948d  cmp     [r11+8], rax
0x140009491  jnz     loc_140009539
0x140009497  mov     [r10], r11
0x14000949a  mov     [r11+8], r10
0x14000949e  mov     r11, [r13+8]
0x1400094a2  cmp     [r11], r13
0x1400094a5  jnz     loc_140009539
0x1400094ab  mov     [rax], r13
0x1400094ae  dec     r9d
0x1400094b1  mov     [rax+8], r11
0x1400094b5  mov     [r11], rax
0x1400094b8  mov     [r13+8], rax
0x1400094bc  jmp     short loc_140009461
0x1400094be  mov     eax, [rdx+2Ch]
0x1400094c1  cmp     [rcx], eax
0x1400094c3  jnz     short loc_14000950B
0x1400094c5  mov     rax, [rdx]
0x1400094c8  cmp     [rax+8], rdx
0x1400094cc  jnz     short loc_140009539
0x1400094ce  lea     r15, [rdx+8]
0x1400094d2  mov     r10, [r15]
0x1400094d5  cmp     [r10], rdx
0x1400094d8  jnz     short loc_140009539
0x1400094da  mov     [r10], rax
0x1400094dd  lea     r11, [rdi+0B68h]
0x1400094e4  mov     [rax+8], r10
0x1400094e8  mov     rsi, [r11+8]
0x1400094ec  cmp     [rsi], r11
0x1400094ef  jnz     short loc_140009539
0x1400094f1  mov     rax, rdx
0x1400094f4  mov     [r15], rsi
0x1400094f7  mov     rcx, rdx
0x1400094fa  mov     rdx, r10
0x1400094fd  mov     [rax], r11
0x140009500  mov     [rsi], rax
0x140009503  mov     [r11+8], rax
0x140009507  mov     byte ptr [rax+32h], 1
0x14000950b  test    r9d, r9d
0x14000950e  jz      short loc_14000951F
0x140009510  mov     rdx, [rdx]
0x140009513  lea     rax, [rdi+0B58h]
0x14000951a  jmp     loc_140009450
0x14000951f  xor     esi, esi
0x140009521  mov     r15, r8
0x140009524  lea     r13d, [rsi+1]
0x140009528  test    r9d, r9d
0x14000952b  jnz     short loc_140009540
0x14000952d  mov     r14, [r14]
0x140009530  mov     al, [rsp+68h+arg_8]
0x140009534  jmp     loc_14000938C
0x140009539  mov     ecx, 3
0x14000953e  int     29h; Win8: RtlFailFast(ecx)
0x140009540  mov     esi, 0C0000017h
0x140009545  jmp     short loc_14000954C
0x140009547  mov     esi, 0C000009Ah
0x14000954c  mov     rdx, [rbp+50h]
0x140009550  test    rdx, rdx
0x140009553  jz      short loc_14000955D
0x140009555  mov     rcx, rdi
0x140009558  call    KmclpFreeBounceList
0x14000955d  mov     qword ptr [rbp+50h], 0
0x140009565  add     [rdi+238h], r13
0x14000956c  jmp     short loc_140009577
0x14000956e  add     [rdi+230h], r13
0x140009575  xor     esi, esi
0x140009577  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x14000957f  jz      short loc_1400095E8
0x140009581  xor     ecx, ecx; PerformanceFrequency
0x140009583  call    cs:__imp_KeQueryPerformanceCounter
0x14000958a  nop     dword ptr [rax+rax+00h]
0x14000958f  sub     rax, rbx
0x140009592  cmp     rax, [rdi+248h]
0x140009599  jbe     short loc_1400095A2
0x14000959b  mov     [rdi+248h], rax
0x1400095a2  cmp     rax, [rdi+250h]
0x1400095a9  jnb     short loc_1400095B2
0x1400095ab  mov     [rdi+250h], rax
0x1400095b2  test    esi, esi
0x1400095b4  js      short loc_1400095C6
0x1400095b6  add     [rdi+268h], r13
0x1400095bd  add     [rdi+280h], rax
0x1400095c4  jmp     short loc_1400095E8
0x1400095c6  movq    xmm0, rax
0x1400095cb  movq    xmm1, r13
0x1400095d0  punpcklqdq xmm1, xmm0
0x1400095d4  movdqu  xmm0, xmmword ptr [rdi+270h]
0x1400095dc  paddq   xmm1, xmm0
0x1400095e0  movdqu  xmmword ptr [rdi+270h], xmm1
0x1400095e8  mov     eax, esi
0x1400095ea  add     rsp, 28h
0x1400095ee  pop     r15
0x1400095f0  pop     r14
0x1400095f2  pop     r13
0x1400095f4  pop     r12
0x1400095f6  pop     rdi
0x1400095f7  pop     rsi
0x1400095f8  pop     rbp
0x1400095f9  pop     rbx
0x1400095fa  retn
```
