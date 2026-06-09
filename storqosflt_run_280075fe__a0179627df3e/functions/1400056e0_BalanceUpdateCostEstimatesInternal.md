# BalanceUpdateCostEstimatesInternal

- ea: `0x1400056e0`
- end: `0x140005a6d`
- name: `BalanceUpdateCostEstimatesInternal`
- size: `909`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001380`
- `0x140002bf0`

## callees

- `0x140004280`
- `0x140004610`
- `0x1400056e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005a34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a34`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a08`

## pseudocode

```c
__int64 __fastcall BalanceUpdateCostEstimatesInternal(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int64 v7; // xmm2_8
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 i; // r8
  int v11; // ecx
  unsigned int v12; // r11d
  __int64 v13; // r10
  __int64 v14; // r8
  __int64 j; // rcx
  __int64 v16; // rax
  __int64 k; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 m; // rax
  __int64 n; // r8
  __int64 ii; // rcx
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 jj; // rax
  __int64 v29; // rcx
  __int64 kk; // r8
  __int64 v31; // rax
  __int64 mm; // r8
  __int64 nn; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  _QWORD v36[16]; // [rsp+20h] [rbp-39h]

  result = *(_QWORD *)(a1 + 1184);
  if ( result )
  {
    v5 = *(_OWORD *)(a1 + 1184);
    v6 = *(_OWORD *)(a1 + 1200);
    v7 = *(_QWORD *)(a1 + 1216);
    v8 = 5LL * *(unsigned int *)(a1 + 2928);
    *(_OWORD *)(a1 + 8 * v8 + 1328) = v5;
    *(_OWORD *)(a1 + 8 * v8 + 1344) = v6;
    *(_QWORD *)(a1 + 8 * v8 + 1360) = v7;
    if ( ++*(_DWORD *)(a1 + 2928) == 40 )
      *(_DWORD *)(a1 + 2928) = 0;
    v9 = *(_DWORD *)(a1 + 2932);
    if ( v9 < 0x28 )
      *(_DWORD *)(a1 + 2932) = v9 + 1;
    for ( i = 0; i != 4; ++i )
      *(_QWORD *)(a1 + 8 * i + 1224) = ((*(_QWORD *)(a1 + 8 * i + 1184) << 23) + 7168LL * *(_QWORD *)(a1 + 8 * i + 1224))
                                     / 0x2000;
    v11 = *(_DWORD *)(a1 + 2932);
    v12 = 0;
    v13 = (*(_DWORD *)(a1 + 2928) - v11 + 40) % 0x28u;
    if ( v11 )
    {
      do
      {
        v14 = *(_QWORD *)(a1 + 40 * v13 + 1360) << 13;
        for ( j = 0; j != 4; ++j )
          v36[j + 8] = *(_QWORD *)(a1 + 40 * v13 + 8 * j + 1328);
        v16 = 0;
        for ( k = 0; k != 4; ++k )
        {
          v18 = *(_QWORD *)(a1 + 8 * k + 1296) * v36[k + 8];
          v36[k + 12] = v18;
          v16 += v18;
        }
        v19 = 0;
        v20 = ((v14 - v16) << 6) / 0x2000;
        do
        {
          v21 = v36[v19 + 12];
          v36[v19] = v21;
          if ( v21 < 0 )
          {
            v21 = -v21;
            v36[v19] = v21;
          }
          if ( v21 < 1 )
            v36[v19] = 1;
          ++v19;
        }
        while ( v19 != 4 );
        v22 = 0;
        for ( m = 0; m != 4; ++m )
          v22 += v36[m];
        if ( v22 < 1 )
          v22 = 0x7FFFFFFFFFFFFFFFLL;
        for ( n = 0; n != 4; ++n )
          v36[n + 4] = (v36[n] << 13) / v22;
        for ( ii = 0; ii != 4; ++ii )
        {
          v26 = v36[ii + 8];
          if ( v26 )
            v27 = v36[ii + 4] * v20 / v26 / 0x2000;
          else
            v27 = 0;
          v36[ii + 12] = v27;
          *(_QWORD *)(a1 + 8 * ii + 1296) += v27;
        }
        for ( jj = 0; jj != 4; ++jj )
        {
          if ( *(__int64 *)(a1 + 8 * jj + 1224) < 64 )
          {
            *(_QWORD *)(a1 + 8 * jj + 1224) = 64;
            *(_QWORD *)(a1 + 8 * jj + 1296) = 1;
          }
        }
        v29 = 0;
        for ( kk = 0; kk != 4; ++kk )
        {
          v31 = *(_QWORD *)(a1 + 8 * kk + 1224) * *(_QWORD *)(a1 + 8 * kk + 1296) / 0x2000LL;
          if ( v31 < 0 )
            v31 = *(_QWORD *)(a1 + 8 * kk + 1224) * *(_QWORD *)(a1 + 8 * kk + 1296) / -8192LL;
          v36[kk + 4] = v31;
          v29 += v31;
        }
        if ( v29 < 1 )
          v29 = 1;
        for ( mm = 0; mm != 4; ++mm )
        {
          if ( (v36[mm + 4] << 13) / v29 < 5 )
            *(_QWORD *)(a1 + 8 * mm + 1296) = 10 * v29 / *(_QWORD *)(a1 + 8 * mm + 1224);
        }
        for ( nn = 0; nn != 4; ++nn )
        {
          v34 = *(_QWORD *)(a1 + 8 * nn + 1296);
          if ( v34 < 1 )
          {
            v34 = 1;
            *(_QWORD *)(a1 + 8 * nn + 1296) = 1;
          }
          v35 = e_max_fp[nn];
          if ( v34 > v35 )
            *(_QWORD *)(a1 + 8 * nn + 1296) = v35;
        }
        ++v12;
        v13 = ((int)v13 + 1) % 0x28u;
      }
      while ( v12 < *(_DWORD *)(a1 + 2932) );
    }
    *(_BYTE *)(a1 + 1096) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1088));
    if ( !(unsigned __int8)SqospAreExternalDeviceCostEstimatesValid(a1) )
      BalanceRestoreCostEstimates();
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1088), *(_BYTE *)(a1 + 1096));
    *(_QWORD *)(a1 + 1168) = a2;
    return (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1152), 0, 4);
  }
  return result;
}

```

## disassembly

```asm
0x1400056e0  mov     [rsp-8+arg_8], rbx
0x1400056e5  mov     [rsp-8+arg_10], rsi
0x1400056ea  push    rbp
0x1400056eb  push    rdi
0x1400056ec  push    r15
0x1400056ee  lea     rbp, [rsp-47h]
0x1400056f3  sub     rsp, 0A0h
0x1400056fa  mov     rax, [rcx+4A0h]
0x140005701  mov     rsi, rdx
0x140005704  mov     rbx, rcx
0x140005707  test    rax, rax
0x14000570a  jz      loc_140005A54
0x140005710  mov     eax, [rcx+0B70h]
0x140005716  mov     edi, 1
0x14000571b  movups  xmm0, xmmword ptr [rcx+4A0h]
0x140005722  movups  xmm1, xmmword ptr [rcx+4B0h]
0x140005729  movsd   xmm2, qword ptr [rcx+4C0h]
0x140005731  lea     rcx, [rax+rax*4]
0x140005735  movups  xmmword ptr [rbx+rcx*8+530h], xmm0
0x14000573d  movups  xmmword ptr [rbx+rcx*8+540h], xmm1
0x140005745  movsd   qword ptr [rbx+rcx*8+550h], xmm2
0x14000574e  add     [rbx+0B70h], edi
0x140005754  cmp     dword ptr [rbx+0B70h], 28h ; '('
0x14000575b  jnz     short loc_140005767
0x14000575d  mov     dword ptr [rbx+0B70h], 0
0x140005767  mov     eax, [rbx+0B74h]
0x14000576d  cmp     eax, 28h ; '('
0x140005770  jnb     short loc_14000577A
0x140005772  inc     eax
0x140005774  mov     [rbx+0B74h], eax
0x14000577a  xor     r8d, r8d
0x14000577d  mov     r15d, 2000h
0x140005783  mov     rcx, [rbx+r8*8+4A0h]
0x14000578b  imul    rax, [rbx+r8*8+4C8h], 1C00h
0x140005797  shl     rcx, 17h
0x14000579b  add     rax, rcx
0x14000579e  cqo
0x1400057a0  idiv    r15
0x1400057a3  mov     [rbx+r8*8+4C8h], rax
0x1400057ab  add     r8, rdi
0x1400057ae  cmp     r8, 4
0x1400057b2  jnz     short loc_140005783
0x1400057b4  mov     ecx, [rbx+0B74h]
0x1400057ba  mov     eax, 0CCCCCCCDh
0x1400057bf  mov     r10d, [rbx+0B70h]
0x1400057c6  xor     r11d, r11d
0x1400057c9  sub     r10d, ecx
0x1400057cc  add     r10d, 28h ; '('
0x1400057d0  mul     r10d
0x1400057d3  shr     edx, 5
0x1400057d6  lea     eax, [rdx+rdx*4]
0x1400057d9  shl     eax, 3
0x1400057dc  sub     r10d, eax
0x1400057df  test    ecx, ecx
0x1400057e1  jz      loc_1400059FE
0x1400057e7  lea     rcx, [r10+r10*4]
0x1400057eb  mov     r8, [rbx+rcx*8+550h]
0x1400057f3  lea     rdx, [rbx+rcx*8]
0x1400057f7  shl     r8, 0Dh
0x1400057fb  xor     ecx, ecx
0x1400057fd  mov     rax, [rdx+rcx*8+530h]
0x140005805  mov     [rbp+rcx*8+57h+var_50], rax
0x14000580a  add     rcx, rdi
0x14000580d  cmp     rcx, 4
0x140005811  jnz     short loc_1400057FD
0x140005813  xor     eax, eax
0x140005815  xor     edx, edx
0x140005817  mov     rcx, [rbp+rdx*8+57h+var_50]
0x14000581c  imul    rcx, [rbx+rdx*8+510h]
0x140005825  mov     [rbp+rdx*8+57h+var_30], rcx
0x14000582a  add     rax, rcx
0x14000582d  add     rdx, rdi
0x140005830  cmp     rdx, 4
0x140005834  jnz     short loc_140005817
0x140005836  sub     r8, rax
0x140005839  shl     r8, 6
0x14000583d  mov     rax, r8
0x140005840  cqo
0x140005842  idiv    r15
0x140005845  xor     edx, edx
0x140005847  mov     r9, rax
0x14000584a  mov     rcx, [rbp+rdx*8+57h+var_30]
0x14000584f  mov     [rbp+rdx*8+57h+var_90], rcx
0x140005854  test    rcx, rcx
0x140005857  jns     short loc_140005861
0x140005859  neg     rcx
0x14000585c  mov     [rbp+rdx*8+57h+var_90], rcx
0x140005861  cmp     rcx, rdi
0x140005864  jge     short loc_14000586B
0x140005866  mov     [rbp+rdx*8+57h+var_90], rdi
0x14000586b  add     rdx, rdi
0x14000586e  cmp     rdx, 4
0x140005872  jnz     short loc_14000584A
0x140005874  xor     ecx, ecx
0x140005876  xor     eax, eax
0x140005878  add     rcx, [rbp+rax*8+57h+var_90]
0x14000587d  add     rax, rdi
0x140005880  cmp     rax, 4
0x140005884  jnz     short loc_140005878
0x140005886  cmp     rcx, rdi
0x140005889  mov     rax, 7FFFFFFFFFFFFFFFh
0x140005893  cmovl   rcx, rax
0x140005897  xor     r8d, r8d
0x14000589a  mov     rax, [rbp+r8*8+57h+var_90]
0x14000589f  shl     rax, 0Dh
0x1400058a3  cqo
0x1400058a5  idiv    rcx
0x1400058a8  mov     [rbp+r8*8+57h+var_70], rax
0x1400058ad  add     r8, rdi
0x1400058b0  cmp     r8, 4
0x1400058b4  jnz     short loc_14000589A
0x1400058b6  xor     ecx, ecx
0x1400058b8  mov     r8, [rbp+rcx*8+57h+var_50]
0x1400058bd  test    r8, r8
0x1400058c0  jz      short loc_1400058D7
0x1400058c2  mov     rax, r9
0x1400058c5  imul    rax, [rbp+rcx*8+57h+var_70]
0x1400058cb  cqo
0x1400058cd  idiv    r8
0x1400058d0  cqo
0x1400058d2  idiv    r15
0x1400058d5  jmp     short loc_1400058D9
0x1400058d7  xor     eax, eax
0x1400058d9  mov     [rbp+rcx*8+57h+var_30], rax
0x1400058de  add     [rbx+rcx*8+510h], rax
0x1400058e6  add     rcx, rdi
0x1400058e9  cmp     rcx, 4
0x1400058ed  jnz     short loc_1400058B8
0x1400058ef  xor     eax, eax
0x1400058f1  cmp     qword ptr [rbx+rax*8+4C8h], 40h ; '@'
0x1400058fa  jge     short loc_140005910
0x1400058fc  mov     qword ptr [rbx+rax*8+4C8h], 40h ; '@'
0x140005908  mov     [rbx+rax*8+510h], rdi
0x140005910  add     rax, rdi
0x140005913  cmp     rax, 4
0x140005917  jnz     short loc_1400058F1
0x140005919  xor     ecx, ecx
0x14000591b  xor     r8d, r8d
0x14000591e  mov     r9, [rbx+r8*8+510h]
0x140005926  imul    r9, [rbx+r8*8+4C8h]
0x14000592f  mov     rax, r9
0x140005932  cqo
0x140005934  idiv    r15
0x140005937  test    rax, rax
0x14000593a  jns     short loc_14000594B
0x14000593c  mov     rax, r9
0x14000593f  mov     r9, 0FFFFFFFFFFFFE000h
0x140005946  cqo
0x140005948  idiv    r9
0x14000594b  mov     [rbp+r8*8+57h+var_70], rax
0x140005950  add     rcx, rax
0x140005953  add     r8, rdi
0x140005956  cmp     r8, 4
0x14000595a  jnz     short loc_14000591E
0x14000595c  cmp     rcx, rdi
0x14000595f  cmovl   rcx, rdi
0x140005963  xor     r8d, r8d
0x140005966  mov     rax, [rbp+r8*8+57h+var_70]
0x14000596b  shl     rax, 0Dh
0x14000596f  cqo
0x140005971  idiv    rcx
0x140005974  cmp     rax, 5
0x140005978  jge     short loc_140005993
0x14000597a  lea     rax, [rcx+rcx*4]
0x14000597e  add     rax, rax
0x140005981  cqo
0x140005983  idiv    qword ptr [rbx+r8*8+4C8h]
0x14000598b  mov     [rbx+r8*8+510h], rax
0x140005993  add     r8, rdi
0x140005996  cmp     r8, 4
0x14000599a  jnz     short loc_140005966
0x14000599c  xor     eax, eax
0x14000599e  mov     rcx, [rbx+rax*8+510h]
0x1400059a6  cmp     rcx, rdi
0x1400059a9  jge     short loc_1400059B6
0x1400059ab  mov     rcx, rdi
0x1400059ae  mov     [rbx+rax*8+510h], rdi
0x1400059b6  lea     rdx, e_max_fp
0x1400059bd  mov     rdx, [rdx+rax*8]
0x1400059c1  cmp     rcx, rdx
0x1400059c4  jle     short loc_1400059CE
0x1400059c6  mov     [rbx+rax*8+510h], rdx
0x1400059ce  add     rax, rdi
0x1400059d1  cmp     rax, 4
0x1400059d5  jnz     short loc_14000599E
0x1400059d7  add     r11d, edi
0x1400059da  mov     eax, 0CCCCCCCDh
0x1400059df  inc     r10d
0x1400059e2  mul     r10d
0x1400059e5  shr     edx, 5
0x1400059e8  lea     eax, [rdx+rdx*4]
0x1400059eb  shl     eax, 3
0x1400059ee  sub     r10d, eax
0x1400059f1  cmp     r11d, [rbx+0B74h]
0x1400059f8  jb      loc_1400057E7
0x1400059fe  lea     rdi, [rbx+440h]
0x140005a05  mov     rcx, rdi; SpinLock
0x140005a08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005a0f  nop     dword ptr [rax+rax+00h]
0x140005a14  mov     rcx, rbx
0x140005a17  mov     [rbx+448h], al
0x140005a1d  call    SqospAreExternalDeviceCostEstimatesValid
0x140005a22  test    al, al
0x140005a24  jnz     short loc_140005A2B
0x140005a26  call    BalanceRestoreCostEstimates
0x140005a2b  mov     dl, [rbx+448h]; NewIrql
0x140005a31  mov     rcx, rdi; SpinLock
0x140005a34  call    cs:__imp_KeReleaseSpinLock
0x140005a3b  nop     dword ptr [rax+rax+00h]
0x140005a40  xor     ecx, ecx
0x140005a42  mov     [rbx+490h], rsi
0x140005a49  lea     eax, [rcx+4]
0x140005a4c  lock cmpxchg [rbx+480h], ecx
0x140005a54  lea     r11, [rsp+0B0h+var_10]
0x140005a5c  mov     rbx, [r11+28h]
0x140005a60  mov     rsi, [r11+30h]
0x140005a64  mov     rsp, r11
0x140005a67  pop     r15
0x140005a69  pop     rdi
0x140005a6a  pop     rbp
0x140005a6b  retn
```
