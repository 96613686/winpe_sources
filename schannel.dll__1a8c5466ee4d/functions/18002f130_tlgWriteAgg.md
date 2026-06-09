# _tlgWriteAgg

- ea: `0x18002f130`
- end: `0x18002f63a`
- name: `_tlgWriteAgg`
- size: `1290`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800014cc`
- `0x180001588`
- `0x180001674`
- `0x180001c84`
- `0x18002ec34`
- `0x18002ef5c`

## callees

- `0x18002f130`
- `0x18002f640`
- `0x18002f8fc`
- `0x18002ff38`
- `0x18005a831`
- `0x180088a48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f4ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f4ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f3aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f3aa`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR a5)
{
  __int64 v7; // rdi
  ULONGLONG v9; // rax
  unsigned __int16 *v10; // rdx
  ULONGLONG Ptr; // rax
  unsigned __int8 v12; // r11
  ULONGLONG v13; // r9
  char *v14; // rax
  char v15; // cl
  char *v18; // rcx
  char v19; // r8
  UCHAR v20; // dl
  __int64 v21; // rcx
  __int64 v22; // r15
  unsigned __int8 v23; // r12
  unsigned __int8 v24; // r11
  unsigned int v25; // r13d
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  int v30; // ecx
  unsigned int i; // edx
  unsigned __int64 j; // r8
  int v33; // eax
  RTL_SRWLOCK *v34; // r14
  unsigned int v35; // ebx
  volatile signed __int64 *k; // rbp
  volatile signed __int64 v37; // rbp
  int v38; // ecx
  __int64 v39; // r15
  int v40; // eax
  unsigned int m; // ebx
  __int64 v42; // rdx
  unsigned __int8 n; // dl
  signed __int64 v44; // r10
  __int64 v45; // rax
  int v46; // r8d
  volatile signed __int64 *v47; // r9
  signed __int64 v48; // rax
  int v49; // ebx
  unsigned int v51; // eax
  volatile signed __int64 v52; // rtt
  signed __int64 v53; // [rsp+30h] [rbp-68h]
  RTL_SRWLOCK *v54; // [rsp+38h] [rbp-60h]
  signed __int64 v55; // [rsp+40h] [rbp-58h] BYREF
  __int64 v56; // [rsp+48h] [rbp-50h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-48h] BYREF
  int NewEventEntry; // [rsp+A0h] [rbp+8h]
  unsigned int v59; // [rsp+A8h] [rbp+10h]
  unsigned __int8 v60; // [rsp+C0h] [rbp+28h]

  v7 = 2;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v9 = *(_QWORD *)(a2 + 3);
  v10 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v9;
  a5->Ptr = *(_QWORD *)(a1 + 8);
  a5->Size = **(unsigned __int16 **)(a1 + 8);
  a5->Reserved = 2;
  a5[1].Ptr = (ULONGLONG)v10;
  a5[1].Size = *v10;
  a5[1].Reserved = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  Ptr = a5[1].Ptr;
  v12 = 0;
  v13 = Ptr + a5[1].Size;
  v14 = (char *)(Ptr + 2);
  do
    v15 = *v14++;
  while ( v15 < 0 );
  while ( *v14++ )
    ;
  while ( (unsigned __int64)v14 < v13 )
  {
    while ( *v14++ )
      ;
    if ( *v14 >= 0 )
      break;
    v18 = v14 + 1;
    v19 = *v14 & 0x7F;
    v14 += 2;
    if ( *v18 >= 0 )
      break;
    while ( 1 )
    {
      v20 = *v14;
      if ( *v14 >= 0 )
        break;
      if ( v20 != 0x80 )
        goto LABEL_15;
      ++v14;
    }
    if ( v19 != 9 || (unsigned __int8)(v20 - 113) > 2u )
      break;
    v21 = v12++;
    a5[v21 + 2].Reserved1 = v20;
  }
LABEL_15:
  v60 = v12;
  if ( !v12 )
    return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, a5);
  v22 = *(_QWORD *)(a1 + 48);
  v56 = v22;
  v53 = 0;
  v55 = 0;
  NewEventEntry = 0;
  _mm_lfence();
  v24 = v12 + 2;
  v23 = v24;
  v25 = a4;
  v26 = 1025
      * (BYTE3(a5[1].Ptr)
       + ((1025
         * (BYTE2(a5[1].Ptr)
          + ((1025 * (BYTE1(a5[1].Ptr) + ((1025 * LOBYTE(a5[1].Ptr)) ^ ((1025 * (unsigned int)LOBYTE(a5[1].Ptr)) >> 6))))
           ^ ((1025 * (BYTE1(a5[1].Ptr) + ((1025 * LOBYTE(a5[1].Ptr)) ^ ((1025 * (unsigned int)LOBYTE(a5[1].Ptr)) >> 6)))) >> 6))))
        ^ ((1025
          * (BYTE2(a5[1].Ptr)
           + ((1025 * (BYTE1(a5[1].Ptr) + ((1025 * LOBYTE(a5[1].Ptr)) ^ ((1025 * (unsigned int)LOBYTE(a5[1].Ptr)) >> 6))))
            ^ ((1025
              * (BYTE1(a5[1].Ptr) + ((1025 * LOBYTE(a5[1].Ptr)) ^ ((1025 * (unsigned int)LOBYTE(a5[1].Ptr)) >> 6)))) >> 6)))) >> 6)));
  v27 = 1025 * (BYTE4(a5[1].Ptr) + (v26 ^ (v26 >> 6)));
  v28 = 1025 * (BYTE5(a5[1].Ptr) + (v27 ^ (v27 >> 6)));
  v29 = 1025 * (BYTE6(a5[1].Ptr) + (v28 ^ (v28 >> 6)));
  v30 = HIBYTE(a5[1].Ptr) + (v29 ^ (v29 >> 6));
  for ( i = (1025 * v30) ^ ((unsigned int)(1025 * v30) >> 6); v24 < a4; ++v24 )
  {
    for ( j = 0; j < a5[v24].Size; i = (1025 * (i + v33)) ^ ((1025 * (i + v33)) >> 6) )
      v33 = *(unsigned __int8 *)(a5[v24].Ptr + j++);
  }
  v34 = (RTL_SRWLOCK *)(v22 + 264);
  v54 = (RTL_SRWLOCK *)(v22 + 264);
  v35 = 32769 * ((9 * i) ^ ((9 * i) >> 11));
  v59 = v35;
  AcquireSRWLockShared((PSRWLOCK)(v22 + 264));
  for ( k = (volatile signed __int64 *)(v22 + 8LL * (v35 & 0x1F));
        ;
        k = (volatile signed __int64 *)((((__int64)v40 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + v37 + 32) )
  {
    if ( !*k )
    {
      if ( *(_DWORD *)(v22 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v22 + 300);
        v49 = 234;
        goto LABEL_42;
      }
      if ( !v53 )
      {
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          (unsigned __int8)v25,
                          (_DWORD)a5,
                          v60,
                          v35,
                          (__int64)&v55);
        v53 = v55;
        if ( !v55 )
        {
          v49 = NewEventEntry;
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v22 + 304);
          else
            ++*(_DWORD *)(v22 + 308);
          goto LABEL_42;
        }
      }
      if ( !_InterlockedCompareExchange64(k, v53, 0) )
      {
        v53 = 0;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v22 + 256)) == 1 )
          EnableFlushTimer(*(struct _TP_TIMER **)(v22 + 344), *(_DWORD *)(v22 + 352));
        v51 = *(_DWORD *)(v22 + 256);
        v49 = NewEventEntry;
        if ( *(_DWORD *)(v22 + 288) < v51 )
          *(_DWORD *)(v22 + 288) = v51;
        goto LABEL_42;
      }
    }
    v37 = *k;
    v38 = *(_DWORD *)(v37 + 40);
    if ( v35 == v38 )
    {
      v39 = *(_QWORD *)(v37 + 16);
      v40 = memcmp_0(&a5[1], (const void *)(v39 + 16), 8u);
      if ( !v40 )
      {
        for ( m = *(unsigned __int8 *)(v37 + 45) + 2; m < v25; ++m )
        {
          v42 = v39 + 16LL * m;
          v40 = a5[m].Size - *(_DWORD *)(v42 + 8);
          if ( v40 )
            goto LABEL_30;
          v40 = memcmp_0((const void *)a5[m].Ptr, *(const void **)v42, a5[m].Size);
          if ( v40 )
            goto LABEL_30;
        }
        v40 = 0;
LABEL_30:
        v35 = v59;
        v34 = v54;
      }
      v22 = v56;
    }
    else
    {
      v40 = v35 - v38;
    }
    if ( !v40 )
      break;
  }
  if ( v37 )
  {
    for ( n = 2; n < v23; ++v7 )
    {
      v44 = *(_QWORD *)a5[v7].Ptr;
      v45 = *(_QWORD *)(v37 + 16);
      v46 = *(unsigned __int8 *)(v45 + 16 * v7 + 13);
      v47 = *(volatile signed __int64 **)(v45 + 16 * v7);
      if ( (_BYTE)v46 == 115 )
        goto LABEL_38;
      if ( v46 == 113 )
      {
        _InterlockedAdd64(v47, v44);
      }
      else if ( v46 == 114 )
      {
        do
        {
LABEL_38:
          v48 = *v47;
          if ( (_BYTE)v46 == 114 )
          {
            if ( v44 >= v48 )
              break;
          }
          else if ( v44 <= v48 )
          {
            break;
          }
          v52 = *v47;
        }
        while ( v52 != _InterlockedCompareExchange64(v47, v44, v48) );
      }
      ++n;
    }
  }
  v49 = NewEventEntry;
LABEL_42:
  ReleaseSRWLockShared(v34);
  if ( v53 )
    DestroyEventEntry(v53);
  return v49;
}

```

## disassembly

```asm
0x18002f130  push    rbx
0x18002f132  push    rsi
0x18002f133  push    rdi
0x18002f134  sub     rsp, 80h
0x18002f13b  movzx   eax, byte ptr [rdx]
0x18002f13e  mov     r10, rcx
0x18002f141  mov     rsi, [rsp+98h+arg_20]
0x18002f149  mov     edi, 2
0x18002f14e  shl     eax, 18h
0x18002f151  mov     ebx, r9d
0x18002f154  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x18002f158  movzx   eax, word ptr [rdx+1]
0x18002f15c  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x18002f160  mov     rax, [rdx+3]
0x18002f164  add     rdx, 0Bh
0x18002f168  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x18002f16d  mov     rax, [rcx+8]
0x18002f171  mov     [rsi], rax
0x18002f174  mov     rax, [rcx+8]
0x18002f178  movzx   ecx, word ptr [rax]
0x18002f17b  mov     [rsi+8], ecx
0x18002f17e  lea     rcx, _TraceLoggingMetadata
0x18002f185  mov     [rsi+0Ch], edi
0x18002f188  mov     [rsi+10h], rdx
0x18002f18c  movzx   eax, word ptr [rdx]
0x18002f18f  mov     [rsi+18h], eax
0x18002f192  lea     rax, _TraceLoggingMetadataEnd
0x18002f199  sub     eax, ecx
0x18002f19b  mov     dword ptr [rsi+1Ch], 1
0x18002f1a2  mov     dword ptr [rsp+98h+arg_20], eax
0x18002f1a9  mov     eax, dword ptr [rsp+98h+arg_20]
0x18002f1b0  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18002f1b7  cmp     [r10+28h], rax
0x18002f1bb  jnz     loc_18002F630
0x18002f1c1  mov     rax, [rsi+10h]
0x18002f1c5  xor     r11b, r11b
0x18002f1c8  mov     r9d, [rsi+18h]
0x18002f1cc  add     r9, rax
0x18002f1cf  add     rax, rdi
0x18002f1d2  movzx   ecx, byte ptr [rax]
0x18002f1d5  inc     rax
0x18002f1d8  test    cl, cl
0x18002f1da  js      short loc_18002F1D2
0x18002f1dc  nop     dword ptr [rax+00h]
0x18002f1e0  movzx   ecx, byte ptr [rax]
0x18002f1e3  inc     rax
0x18002f1e6  test    cl, cl
0x18002f1e8  jnz     short loc_18002F1E0
0x18002f1ea  nop     word ptr [rax+rax+00h]
0x18002f1f0  cmp     rax, r9
0x18002f1f3  jnb     short loc_18002F247
0x18002f1f5  movzx   ecx, byte ptr [rax]
0x18002f1f8  inc     rax
0x18002f1fb  test    cl, cl
0x18002f1fd  jnz     short loc_18002F1F5
0x18002f1ff  movzx   r8d, byte ptr [rax]
0x18002f203  test    r8b, r8b
0x18002f206  jns     short loc_18002F247
0x18002f208  lea     rcx, [rax+1]
0x18002f20c  and     r8b, 7Fh
0x18002f210  add     rax, rdi
0x18002f213  cmp     byte ptr [rcx], 0
0x18002f216  jge     short loc_18002F247
0x18002f218  movzx   edx, byte ptr [rax]
0x18002f21b  test    dl, dl
0x18002f21d  jns     short loc_18002F229
0x18002f21f  cmp     dl, 80h
0x18002f222  jnz     short loc_18002F247
0x18002f224  inc     rax
0x18002f227  jmp     short loc_18002F218
0x18002f229  cmp     r8b, 9
0x18002f22d  jnz     short loc_18002F247
0x18002f22f  lea     ecx, [rdx-71h]
0x18002f232  cmp     cl, dil
0x18002f235  ja      short loc_18002F247
0x18002f237  movzx   ecx, r11b
0x18002f23b  add     rcx, rcx
0x18002f23e  inc     r11b
0x18002f241  mov     [rsi+rcx*8+2Dh], dl
0x18002f245  jmp     short loc_18002F1F0
0x18002f247  mov     byte ptr [rsp+98h+arg_20], r11b
0x18002f24f  test    r11b, r11b
0x18002f252  jz      loc_18002F5F8
0x18002f258  mov     [rsp+98h+arg_10], rbp
0x18002f260  xor     eax, eax
0x18002f262  mov     [rsp+98h+var_20], r12
0x18002f267  mov     [rsp+98h+var_28], r13
0x18002f26c  mov     [rsp+98h+var_30], r14
0x18002f271  mov     [rsp+98h+var_38], r15
0x18002f276  mov     r15, [r10+30h]
0x18002f27a  mov     [rsp+98h+var_50], r15
0x18002f27f  mov     [rsp+98h+var_68], rax
0x18002f284  mov     [rsp+98h+var_58], rax
0x18002f289  mov     [rsp+98h+arg_0], eax
0x18002f290  lfence
0x18002f293  movzx   eax, byte ptr [rsi+10h]
0x18002f297  lea     r12d, [r11+2]
0x18002f29b  imul    ecx, eax, 401h
0x18002f2a1  movzx   r11d, r12b
0x18002f2a5  movzx   eax, byte ptr [rsi+11h]
0x18002f2a9  movzx   r13d, bl
0x18002f2ad  mov     edx, ecx
0x18002f2af  shr     edx, 6
0x18002f2b2  xor     edx, ecx
0x18002f2b4  add     edx, eax
0x18002f2b6  imul    eax, edx, 401h
0x18002f2bc  mov     ecx, eax
0x18002f2be  shr     ecx, 6
0x18002f2c1  xor     ecx, eax
0x18002f2c3  movzx   eax, byte ptr [rsi+12h]
0x18002f2c7  add     ecx, eax
0x18002f2c9  imul    eax, ecx, 401h
0x18002f2cf  mov     ecx, eax
0x18002f2d1  shr     ecx, 6
0x18002f2d4  xor     ecx, eax
0x18002f2d6  movzx   eax, byte ptr [rsi+13h]
0x18002f2da  add     ecx, eax
0x18002f2dc  imul    eax, ecx, 401h
0x18002f2e2  mov     ecx, eax
0x18002f2e4  shr     ecx, 6
0x18002f2e7  xor     ecx, eax
0x18002f2e9  movzx   eax, byte ptr [rsi+14h]
0x18002f2ed  add     ecx, eax
0x18002f2ef  imul    eax, ecx, 401h
0x18002f2f5  mov     ecx, eax
0x18002f2f7  shr     ecx, 6
0x18002f2fa  xor     ecx, eax
0x18002f2fc  movzx   eax, byte ptr [rsi+15h]
0x18002f300  add     ecx, eax
0x18002f302  imul    eax, ecx, 401h
0x18002f308  mov     ecx, eax
0x18002f30a  shr     ecx, 6
0x18002f30d  xor     ecx, eax
0x18002f30f  movzx   eax, byte ptr [rsi+16h]
0x18002f313  add     ecx, eax
0x18002f315  imul    eax, ecx, 401h
0x18002f31b  mov     ecx, eax
0x18002f31d  shr     ecx, 6
0x18002f320  xor     ecx, eax
0x18002f322  movzx   eax, byte ptr [rsi+17h]
0x18002f326  add     ecx, eax
0x18002f328  imul    eax, ecx, 401h
0x18002f32e  mov     edx, eax
0x18002f330  shr     edx, 6
0x18002f333  xor     edx, eax
0x18002f335  cmp     r12b, r13b
0x18002f338  jnb     short loc_18002F384
0x18002f33a  nop     word ptr [rax+rax+00h]
0x18002f340  movzx   eax, r11b
0x18002f344  xor     r8d, r8d
0x18002f347  add     rax, rax
0x18002f34a  mov     r9d, [rsi+rax*8+8]
0x18002f34f  mov     r10, [rsi+rax*8]
0x18002f353  test    r9, r9
0x18002f356  jz      short loc_18002F37C
0x18002f358  nop     dword ptr [rax+rax+00000000h]
0x18002f360  movzx   eax, byte ptr [r10+r8]
0x18002f365  inc     r8
0x18002f368  add     eax, edx
0x18002f36a  imul    ecx, eax, 401h
0x18002f370  mov     edx, ecx
0x18002f372  shr     edx, 6
0x18002f375  xor     edx, ecx
0x18002f377  cmp     r8, r9
0x18002f37a  jb      short loc_18002F360
0x18002f37c  inc     r11b
0x18002f37f  cmp     r11b, r13b
0x18002f382  jb      short loc_18002F340
0x18002f384  lea     eax, [rdx+rdx*8]
0x18002f387  mov     ecx, eax
0x18002f389  lea     r14, [r15+108h]
0x18002f390  shr     ecx, 0Bh
0x18002f393  xor     ecx, eax
0x18002f395  mov     [rsp+98h+var_60], r14
0x18002f39a  imul    ebx, ecx, 8001h
0x18002f3a0  mov     rcx, r14; SRWLock
0x18002f3a3  mov     [rsp+98h+arg_8], ebx
0x18002f3aa  call    cs:__imp_AcquireSRWLockShared
0x18002f3b0  mov     eax, ebx
0x18002f3b2  and     eax, 1Fh
0x18002f3b5  lea     rbp, [r15+rax*8]
0x18002f3b9  cmp     qword ptr [rbp+0], 0
0x18002f3be  jz      loc_18002F4E9
0x18002f3c4  mov     rbp, [rbp+0]
0x18002f3c8  mov     ecx, [rbp+28h]
0x18002f3cb  cmp     ebx, ecx
0x18002f3cd  jnz     loc_18002F51A
0x18002f3d3  mov     r15, [rbp+10h]
0x18002f3d7  lea     rcx, [rsi+10h]; Buf1
0x18002f3db  mov     r8d, 8; Size
0x18002f3e1  lea     rdx, [r15+10h]; Buf2
0x18002f3e5  call    memcmp_0
0x18002f3ea  test    eax, eax
0x18002f3ec  jnz     short loc_18002F434
0x18002f3ee  movzx   ebx, byte ptr [rbp+2Dh]
0x18002f3f2  add     ebx, edi
0x18002f3f4  cmp     ebx, r13d
0x18002f3f7  jnb     short loc_18002F426
0x18002f3f9  mov     eax, ebx
0x18002f3fb  add     rax, rax
0x18002f3fe  mov     r8d, [rsi+rax*8+8]; Size
0x18002f403  lea     rcx, [rsi+rax*8]
0x18002f407  lea     rdx, [r15+rax*8]
0x18002f40b  mov     eax, r8d
0x18002f40e  sub     eax, [rdx+8]
0x18002f411  jnz     short loc_18002F428
0x18002f413  mov     rdx, [rdx]; Buf2
0x18002f416  mov     rcx, [rcx]; Buf1
0x18002f419  call    memcmp_0
0x18002f41e  test    eax, eax
0x18002f420  jnz     short loc_18002F428
0x18002f422  inc     ebx
0x18002f424  jmp     short loc_18002F3F4
0x18002f426  xor     eax, eax
0x18002f428  mov     ebx, [rsp+98h+arg_8]
0x18002f42f  mov     r14, [rsp+98h+var_60]
0x18002f434  mov     r15, [rsp+98h+var_50]
0x18002f439  test    eax, eax
0x18002f43b  jnz     loc_18002F504
0x18002f441  test    rbp, rbp
0x18002f444  jz      short loc_18002F4A2
0x18002f446  movzx   edx, dil
0x18002f44a  cmp     r12b, dl
0x18002f44d  jbe     short loc_18002F4A2
0x18002f44f  nop
0x18002f450  mov     rcx, rdi
0x18002f453  add     rcx, rcx
0x18002f456  mov     rax, [rsi+rcx*8]
0x18002f45a  mov     r10, [rax]
0x18002f45d  mov     rax, [rbp+10h]
0x18002f461  movzx   r8d, byte ptr [rax+rcx*8+0Dh]
0x18002f467  mov     r9, [rax+rcx*8]
0x18002f46b  cmp     r8b, 73h ; 's'
0x18002f46f  jz      short loc_18002F482
0x18002f471  mov     ecx, r8d
0x18002f474  sub     ecx, 71h ; 'q'
0x18002f477  jz      loc_18008DCF2
0x18002f47d  cmp     ecx, 1
0x18002f480  jnz     short loc_18002F498
0x18002f482  mov     rax, [r9]
0x18002f485  cmp     r8b, 72h ; 'r'
0x18002f489  jnz     loc_18008DCFB
0x18002f48f  cmp     r10, rax
0x18002f492  jl      loc_18008DD04
0x18002f498  inc     dl
0x18002f49a  inc     rdi
0x18002f49d  cmp     dl, r12b
0x18002f4a0  jb      short loc_18002F450
0x18002f4a2  mov     ebx, [rsp+98h+arg_0]
0x18002f4a9  mov     rcx, r14; SRWLock
0x18002f4ac  call    cs:__imp_ReleaseSRWLockShared
0x18002f4b2  mov     rax, [rsp+98h+var_68]
0x18002f4b7  mov     r15, [rsp+98h+var_38]
0x18002f4bc  mov     r14, [rsp+98h+var_30]
0x18002f4c1  mov     r13, [rsp+98h+var_28]
0x18002f4c6  mov     r12, [rsp+98h+var_20]
0x18002f4cb  mov     rbp, [rsp+98h+arg_10]
0x18002f4d3  test    rax, rax
0x18002f4d6  jnz     loc_18002F623
0x18002f4dc  mov     eax, ebx
0x18002f4de  add     rsp, 80h
0x18002f4e5  pop     rdi
0x18002f4e6  pop     rsi
0x18002f4e7  pop     rbx
0x18002f4e8  retn
0x18002f4e9  cmp     dword ptr [r15+100h], 400h
0x18002f4f4  jb      short loc_18002F523
0x18002f4f6  inc     dword ptr [r15+12Ch]
0x18002f4fd  mov     ebx, 0EAh
0x18002f502  jmp     short loc_18002F4A9
0x18002f504  cdqe
0x18002f506  add     rbp, 20h ; ' '
0x18002f50a  sar     rax, 3Fh
0x18002f50e  and     rax, 0FFFFFFFFFFFFFFF8h
0x18002f512  add     rbp, rax
0x18002f515  jmp     loc_18002F3B9
0x18002f51a  mov     eax, ebx
0x18002f51c  sub     eax, ecx
0x18002f51e  jmp     loc_18002F439
0x18002f523  cmp     [rsp+98h+var_68], 0
0x18002f529  jnz     short loc_18002F569
0x18002f52b  movzx   r9d, byte ptr [rsp+98h+arg_20]
0x18002f534  lea     rax, [rsp+98h+var_58]
0x18002f539  mov     [rsp+98h+UserData], rax
0x18002f53e  lea     rcx, [rsp+98h+EventDescriptor]
0x18002f543  mov     r8, rsi
0x18002f546  mov     [rsp+98h+UserDataCount], ebx
0x18002f54a  movzx   edx, r13b
0x18002f54e  call    CreateNewEventEntry
0x18002f553  mov     [rsp+98h+arg_0], eax
0x18002f55a  mov     rax, [rsp+98h+var_58]
0x18002f55f  mov     [rsp+98h+var_68], rax
0x18002f564  test    rax, rax
0x18002f567  jz      short loc_18002F5D4
0x18002f569  mov     rcx, [rsp+98h+var_68]
0x18002f56e  xor     eax, eax
0x18002f570  lock cmpxchg [rbp+0], rcx
0x18002f576  jnz     loc_18002F3C4
0x18002f57c  mov     [rsp+98h+var_68], 0
0x18002f585  mov     eax, 1
  ... truncated ...
```
