# PinCacheAdd

- ea: `0x1800391c4`
- end: `0x1800395ec`
- name: `PinCacheAdd`
- size: `1064`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001b6f8`
- `0x18003a1a4`

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18000d9d0`
- `0x180038e28`
- `0x180038e7c`
- `0x180039068`
- `0x18003916c`
- `0x1800391c4`
- `0x18003c1f6`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800394df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039542`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800394df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039542`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039449`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800394ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039449`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800394ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003943b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003949d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800394d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800394ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003943b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003949d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800394d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800394ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039531`

## pseudocode

```c
__int64 __fastcall PinCacheAdd(
        _QWORD *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall *a5)(__int64, __int64),
        __int64 a6)
{
  unsigned int v6; // r15d
  void *v7; // rbp
  unsigned int v9; // r9d
  unsigned int Luid; // ebx
  _OWORD *v11; // r14
  void **v12; // rdi
  unsigned int v13; // eax
  int v14; // r13d
  unsigned int v15; // eax
  void *v16; // r12
  int v17; // ecx
  unsigned __int8 v18; // cf
  int v19; // ecx
  int v20; // eax
  BOOL v21; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // rax
  int v24; // r14d
  unsigned __int64 v25; // rax
  unsigned int v26; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v28; // r8
  void *v29; // rax
  void *v30; // r12
  void *v31; // rbx
  HANDLE v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  HANDLE v35; // rax
  HANDLE v36; // rax
  _OWORD *v37; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  _QWORD *v40; // rax
  _BYTE *v41; // rax
  __int64 v42; // rcx
  int v44; // [rsp+30h] [rbp-68h]
  BOOL v45; // [rsp+34h] [rbp-64h]
  unsigned int v46; // [rsp+38h] [rbp-60h]
  void *Buf1; // [rsp+40h] [rbp-58h] BYREF
  int v50; // [rsp+B0h] [rbp+18h]
  size_t Size; // [rsp+B8h] [rbp+20h] BYREF

  v50 = a3;
  v6 = 0;
  v7 = 0;
  LODWORD(Size) = 0;
  v9 = *(_DWORD *)a4;
  Buf1 = 0;
  if ( v9 - 1 > 7 )
  {
    Luid = 160;
    goto LABEL_56;
  }
  if ( a3 && (unsigned int)(*(_DWORD *)(a3 + 24) - 2) <= 1 )
  {
    Luid = a5(a4, a6);
    goto LABEL_56;
  }
  v11 = (_OWORD *)*a1;
  v46 = v9 - 1;
  v44 = *(_DWORD *)(a4 + 4);
  if ( *a1 )
  {
    v12 = (void **)*((_QWORD *)v11 + v9 - 1);
    v13 = I_PinCacheLookup(v12);
    Luid = v13;
    if ( v13 && v13 != 4306 )
      goto LABEL_56;
  }
  else
  {
    v12 = 0;
    Luid = 4306;
  }
  v14 = 0;
  v45 = Luid == 0;
  if ( v12 )
  {
    v15 = I_PinCacheDecryptPin(v12, &Buf1, &Size);
    v7 = Buf1;
    Luid = v15;
    if ( v15 )
    {
      v6 = Size;
      goto LABEL_41;
    }
    v6 = Size;
    if ( *((_DWORD *)v12 + 8)
      || *(_DWORD *)(a4 + 12) != (_DWORD)Size
      || memcmp_0(Buf1, *(const void **)(a4 + 16), (unsigned int)Size) )
    {
      v14 = 1;
    }
  }
  else
  {
    Luid = 0;
  }
  v16 = *(void **)(a4 + 32);
  Buf1 = v16;
  if ( v16 )
  {
    v14 = 1;
    LODWORD(Size) = *(_DWORD *)(a4 + 24);
  }
  else
  {
    v17 = a2;
    v18 = _bittest(&v17, *(_DWORD *)a4);
    v16 = *(void **)(a4 + 16);
    v19 = *(_DWORD *)(a4 + 4);
    if ( !v18 )
      v14 = 1;
    v20 = *(_DWORD *)(a4 + 12);
    LODWORD(Size) = v20;
    Buf1 = v16;
    v44 = v19;
    if ( !v14 && v12 )
      goto LABEL_28;
  }
  Luid = a5(a4, a6);
  if ( Luid )
    goto LABEL_41;
  if ( *(_QWORD *)(a4 + 48) )
  {
    v16 = *(void **)(a4 + 48);
    v20 = *(_DWORD *)(a4 + 40);
    Buf1 = v16;
    LODWORD(Size) = v20;
    v44 = 1;
  }
  else
  {
    v20 = Size;
  }
  if ( v12 )
  {
LABEL_28:
    if ( v20 == v6 && !memcmp_0(v16, v7, v6) )
    {
      v21 = v45;
    }
    else
    {
      memset_0(*v12, 0, 8LL * *((unsigned int *)v12 + 3));
      v21 = 0;
      *((_DWORD *)v12 + 2) = 0;
    }
    if ( !v21 )
    {
      v22 = *((unsigned int *)v12 + 3);
      if ( (unsigned int)v22 <= *((_DWORD *)v12 + 2) )
      {
        v23 = 2 * v22;
        if ( v23 > 0xFFFFFFFF || (v24 = v23, v25 = 8LL * (unsigned int)v23, v25 > 0xFFFFFFFF) )
        {
          Luid = 534;
          goto LABEL_41;
        }
        v26 = v25;
        ProcessHeap = GetProcessHeap();
        v28 = v26;
        Luid = 8;
        v29 = HeapAlloc(ProcessHeap, 8u, v28);
        v30 = v29;
        if ( !v29 )
          goto LABEL_41;
        memcpy_0(v29, *v12, 8LL * *((unsigned int *)v12 + 3));
        v31 = *v12;
        *((_DWORD *)v12 + 3) = v24;
        v32 = GetProcessHeap();
        HeapFree(v32, 0, v31);
        *v12 = v30;
      }
      Luid = I_PinCacheGetLuid((_QWORD *)*v12 + *((unsigned int *)v12 + 2));
      if ( Luid )
        goto LABEL_41;
      ++*((_DWORD *)v12 + 2);
    }
    if ( v14 )
      goto LABEL_54;
    goto LABEL_41;
  }
  Luid = 8;
  if ( !v11 )
  {
    v36 = GetProcessHeap();
    v37 = HeapAlloc(v36, 8u, 0x40u);
    v11 = v37;
    if ( !v37 )
      goto LABEL_41;
    *v37 = 0;
    v37[1] = 0;
    v37[2] = 0;
    v37[3] = 0;
  }
  v38 = GetProcessHeap();
  v12 = (void **)HeapAlloc(v38, 8u, 0x38u);
  if ( v12 )
  {
    *((_QWORD *)v11 + v46) = v12;
    *((_DWORD *)v12 + 3) = 10;
    v39 = GetProcessHeap();
    v40 = HeapAlloc(v39, 8u, 0x50u);
    *v12 = v40;
    if ( v40 )
    {
      Luid = I_PinCacheGetLuid(v40);
      if ( !Luid )
      {
        ++*((_DWORD *)v12 + 2);
        *a1 = v11;
LABEL_54:
        Luid = I_CommitPinToCache((_DWORD)v12, (_DWORD)Buf1, Size, v50, v44);
      }
    }
  }
LABEL_41:
  if ( v7 )
  {
    v33 = v6;
    v34 = v7;
    if ( v6 )
    {
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v7);
  }
LABEL_56:
  v41 = *(_BYTE **)(a4 + 48);
  if ( v41 )
  {
    v42 = *(unsigned int *)(a4 + 40);
    if ( *(_DWORD *)(a4 + 40) )
    {
      do
      {
        *v41++ = 0;
        --v42;
      }
      while ( v42 );
    }
    CspFreeH(*(_QWORD *)(a4 + 48));
    *(_QWORD *)(a4 + 48) = 0;
  }
  return Luid;
}

```

## disassembly

```asm
0x1800391c4  mov     rax, rsp
0x1800391c7  mov     [rax+18h], r8
0x1800391cb  mov     [rax+10h], edx
0x1800391ce  mov     [rax+8], rcx
0x1800391d2  push    rbx
0x1800391d3  push    rbp
0x1800391d4  push    rsi
0x1800391d5  push    rdi
0x1800391d6  push    r12
0x1800391d8  push    r13
0x1800391da  push    r14
0x1800391dc  push    r15
0x1800391de  sub     rsp, 58h
0x1800391e2  xor     r15d, r15d
0x1800391e5  xor     ebp, ebp
0x1800391e7  mov     rsi, r9
0x1800391ea  mov     [rax+20h], r15d
0x1800391ee  mov     r9d, [r9]
0x1800391f1  mov     [rax-58h], rbp
0x1800391f5  lea     r12d, [r15+1]
0x1800391f9  lea     eax, [r9-1]
0x1800391fd  cmp     eax, 7
0x180039200  ja      loc_1800395A7
0x180039206  test    r8, r8
0x180039209  jz      short loc_180039236
0x18003920b  mov     eax, [r8+18h]
0x18003920f  sub     eax, 2
0x180039212  cmp     eax, r12d
0x180039215  ja      short loc_180039236
0x180039217  mov     rdx, [rsp+98h+arg_28]
0x18003921f  mov     rcx, rsi
0x180039222  mov     rax, [rsp+98h+arg_20]
0x18003922a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003922f  mov     ebx, eax
0x180039231  jmp     loc_1800395AC
0x180039236  mov     r14, [rcx]
0x180039239  lea     eax, [r9-1]
0x18003923d  mov     ecx, [rsi+4]
0x180039240  mov     [rsp+98h+var_60], eax
0x180039244  mov     [rsp+98h+var_68], ecx
0x180039248  test    r14, r14
0x18003924b  jnz     short loc_180039256
0x18003924d  xor     edi, edi
0x18003924f  mov     ebx, 10D2h
0x180039254  jmp     short loc_180039273
0x180039256  mov     rdi, [r14+rax*8]
0x18003925a  mov     rcx, rdi
0x18003925d  call    I_PinCacheLookup
0x180039262  mov     ebx, eax
0x180039264  test    eax, eax
0x180039266  jz      short loc_180039273
0x180039268  cmp     eax, 10D2h
0x18003926d  jnz     loc_1800395AC
0x180039273  xor     eax, eax
0x180039275  xor     r13d, r13d
0x180039278  test    ebx, ebx
0x18003927a  setz    al
0x18003927d  mov     [rsp+98h+var_64], eax
0x180039281  test    rdi, rdi
0x180039284  jz      short loc_1800392DF
0x180039286  lea     r8, [rsp+98h+Size]
0x18003928e  mov     rcx, rdi
0x180039291  lea     rdx, [rsp+98h+Buf1]
0x180039296  call    I_PinCacheDecryptPin
0x18003929b  mov     rbp, [rsp+98h+Buf1]
0x1800392a0  mov     ebx, eax
0x1800392a2  test    eax, eax
0x1800392a4  jnz     short loc_1800392D2
0x1800392a6  mov     r15d, dword ptr [rsp+98h+Size]
0x1800392ae  cmp     [rdi+20h], r13d
0x1800392b2  jnz     short loc_1800392CD
0x1800392b4  cmp     [rsi+0Ch], r15d
0x1800392b8  jnz     short loc_1800392CD
0x1800392ba  mov     rdx, [rsi+10h]; Buf2
0x1800392be  mov     r8d, r15d; Size
0x1800392c1  mov     rcx, rbp; Buf1
0x1800392c4  call    memcmp_0
0x1800392c9  test    eax, eax
0x1800392cb  jz      short loc_1800392E1
0x1800392cd  mov     r13d, r12d
0x1800392d0  jmp     short loc_1800392E1
0x1800392d2  mov     r15d, dword ptr [rsp+98h+Size]
0x1800392da  jmp     loc_18003947E
0x1800392df  xor     ebx, ebx
0x1800392e1  mov     r12, [rsi+20h]
0x1800392e5  mov     [rsp+98h+Buf1], r12
0x1800392ea  test    r12, r12
0x1800392ed  jz      short loc_180039303
0x1800392ef  mov     r8d, [rsi+18h]
0x1800392f3  mov     r13d, 1
0x1800392f9  mov     dword ptr [rsp+98h+Size], r8d
0x180039301  jmp     short loc_18003933C
0x180039303  mov     eax, [rsi]
0x180039305  mov     ecx, [rsp+98h+arg_8]
0x18003930c  bt      ecx, eax
0x18003930f  mov     r12, [rsi+10h]
0x180039313  mov     eax, 1
0x180039318  mov     ecx, [rsi+4]
0x18003931b  cmovnb  r13d, eax
0x18003931f  mov     eax, [rsi+0Ch]
0x180039322  mov     dword ptr [rsp+98h+Size], eax
0x180039329  mov     [rsp+98h+Buf1], r12
0x18003932e  mov     [rsp+98h+var_68], ecx
0x180039332  test    r13d, r13d
0x180039335  jnz     short loc_18003933C
0x180039337  test    rdi, rdi
0x18003933a  jnz     short loc_180039392
0x18003933c  mov     rdx, [rsp+98h+arg_28]
0x180039344  mov     rcx, rsi
0x180039347  mov     rax, [rsp+98h+arg_20]
0x18003934f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039354  mov     ebx, eax
0x180039356  test    eax, eax
0x180039358  jnz     loc_180039478
0x18003935e  cmp     qword ptr [rsi+30h], 0
0x180039363  jz      short loc_180039382
0x180039365  mov     r12, [rsi+30h]
0x180039369  mov     eax, [rsi+28h]
0x18003936c  mov     [rsp+98h+Buf1], r12
0x180039371  mov     dword ptr [rsp+98h+Size], eax
0x180039378  mov     [rsp+98h+var_68], 1
0x180039380  jmp     short loc_180039389
0x180039382  mov     eax, dword ptr [rsp+98h+Size]
0x180039389  test    rdi, rdi
0x18003938c  jz      loc_1800394C6
0x180039392  cmp     eax, r15d
0x180039395  jnz     short loc_1800393AF
0x180039397  mov     r8d, r15d; Size
0x18003939a  mov     rdx, rbp; Buf2
0x18003939d  mov     rcx, r12; Buf1
0x1800393a0  call    memcmp_0
0x1800393a5  test    eax, eax
0x1800393a7  jnz     short loc_1800393AF
0x1800393a9  mov     eax, [rsp+98h+var_64]
0x1800393ad  jmp     short loc_1800393C6
0x1800393af  mov     r8d, [rdi+0Ch]
0x1800393b3  xor     edx, edx; Val
0x1800393b5  mov     rcx, [rdi]; void *
0x1800393b8  shl     r8, 3; Size
0x1800393bc  call    memset_0
0x1800393c1  xor     eax, eax
0x1800393c3  mov     [rdi+8], eax
0x1800393c6  test    rdi, rdi
0x1800393c9  jz      loc_1800394C6
0x1800393cf  test    eax, eax
0x1800393d1  jnz     loc_1800394B6
0x1800393d7  mov     eax, [rdi+0Ch]
0x1800393da  cmp     eax, [rdi+8]
0x1800393dd  ja      short loc_180039452
0x1800393df  add     rax, rax
0x1800393e2  mov     ecx, 0FFFFFFFFh
0x1800393e7  cmp     rax, rcx
0x1800393ea  ja      loc_180039473
0x1800393f0  mov     r14d, eax
0x1800393f3  mov     eax, eax
0x1800393f5  shl     rax, 3
0x1800393f9  cmp     rax, rcx
0x1800393fc  ja      short loc_180039473
0x1800393fe  mov     ebx, eax
0x180039400  call    cs:__imp_GetProcessHeap
0x180039406  mov     r8d, ebx; dwBytes
0x180039409  mov     ebx, 8
0x18003940e  mov     edx, ebx; dwFlags
0x180039410  mov     rcx, rax; hHeap
0x180039413  call    cs:__imp_HeapAlloc
0x180039419  mov     r12, rax
0x18003941c  test    rax, rax
0x18003941f  jz      short loc_180039478
0x180039421  mov     r8d, [rdi+0Ch]
0x180039425  mov     rcx, rax; void *
0x180039428  mov     rdx, [rdi]; Src
0x18003942b  shl     r8, 3; Size
0x18003942f  call    memcpy_0
0x180039434  mov     rbx, [rdi]
0x180039437  mov     [rdi+0Ch], r14d
0x18003943b  call    cs:__imp_GetProcessHeap
0x180039441  mov     r8, rbx; lpMem
0x180039444  xor     edx, edx; dwFlags
0x180039446  mov     rcx, rax; hHeap
0x180039449  call    cs:__imp_HeapFree
0x18003944f  mov     [rdi], r12
0x180039452  mov     ecx, [rdi+8]
0x180039455  mov     rax, [rdi]
0x180039458  lea     rcx, [rax+rcx*8]
0x18003945c  call    I_PinCacheGetLuid
0x180039461  mov     ebx, eax
0x180039463  mov     r12d, 1
0x180039469  test    eax, eax
0x18003946b  jnz     short loc_18003947E
0x18003946d  add     [rdi+8], r12d
0x180039471  jmp     short loc_1800394BC
0x180039473  mov     ebx, 216h
0x180039478  mov     r12d, 1
0x18003947e  test    rbp, rbp
0x180039481  jz      loc_1800395AC
0x180039487  mov     ecx, r15d
0x18003948a  mov     rax, rbp
0x18003948d  test    r15d, r15d
0x180039490  jz      short loc_18003949D
0x180039492  mov     byte ptr [rax], 0
0x180039495  add     rax, r12
0x180039498  sub     rcx, r12
0x18003949b  jnz     short loc_180039492
0x18003949d  call    cs:__imp_GetProcessHeap
0x1800394a3  mov     r8, rbp; lpMem
0x1800394a6  xor     edx, edx; dwFlags
0x1800394a8  mov     rcx, rax; hHeap
0x1800394ab  call    cs:__imp_HeapFree
0x1800394b1  jmp     loc_1800395AC
0x1800394b6  mov     r12d, 1
0x1800394bc  test    r13d, r13d
0x1800394bf  jz      short loc_18003947E
0x1800394c1  jmp     loc_18003957B
0x1800394c6  mov     ebx, 8
0x1800394cb  test    r14, r14
0x1800394ce  jnz     short loc_1800394FF
0x1800394d0  call    cs:__imp_GetProcessHeap
0x1800394d6  lea     r8d, [rbx+38h]; dwBytes
0x1800394da  mov     edx, ebx; dwFlags
0x1800394dc  mov     rcx, rax; hHeap
0x1800394df  call    cs:__imp_HeapAlloc
0x1800394e5  mov     r14, rax
0x1800394e8  test    rax, rax
0x1800394eb  jz      short loc_180039478
0x1800394ed  xorps   xmm0, xmm0
0x1800394f0  movups  xmmword ptr [rax], xmm0
0x1800394f3  movups  xmmword ptr [rax+10h], xmm0
0x1800394f7  movups  xmmword ptr [rax+20h], xmm0
0x1800394fb  movups  xmmword ptr [rax+30h], xmm0
0x1800394ff  call    cs:__imp_GetProcessHeap
0x180039505  mov     r8d, 38h ; '8'; dwBytes
0x18003950b  mov     edx, ebx; dwFlags
0x18003950d  mov     rcx, rax; hHeap
0x180039510  call    cs:__imp_HeapAlloc
0x180039516  mov     rdi, rax
0x180039519  test    rax, rax
0x18003951c  jz      loc_180039478
0x180039522  mov     eax, [rsp+98h+var_60]
0x180039526  mov     [r14+rax*8], rdi
0x18003952a  mov     dword ptr [rdi+0Ch], 0Ah
0x180039531  call    cs:__imp_GetProcessHeap
0x180039537  mov     r8d, 50h ; 'P'; dwBytes
0x18003953d  mov     edx, ebx; dwFlags
0x18003953f  mov     rcx, rax; hHeap
0x180039542  call    cs:__imp_HeapAlloc
0x180039548  mov     [rdi], rax
0x18003954b  test    rax, rax
0x18003954e  jz      loc_180039478
0x180039554  mov     rcx, rax
0x180039557  call    I_PinCacheGetLuid
0x18003955c  mov     ebx, eax
0x18003955e  mov     r12d, 1
0x180039564  test    eax, eax
0x180039566  jnz     loc_18003947E
0x18003956c  mov     rax, [rsp+98h+arg_0]
0x180039574  add     [rdi+8], r12d
0x180039578  mov     [rax], r14
0x18003957b  mov     eax, [rsp+98h+var_68]
0x18003957f  mov     rcx, rdi
0x180039582  mov     r9, [rsp+98h+arg_10]
0x18003958a  mov     r8d, dword ptr [rsp+98h+Size]
0x180039592  mov     rdx, [rsp+98h+Buf1]
0x180039597  mov     [rsp+98h+var_78], eax
0x18003959b  call    I_CommitPinToCache
0x1800395a0  mov     ebx, eax
0x1800395a2  jmp     loc_18003947E
0x1800395a7  mov     ebx, 0A0h
0x1800395ac  mov     rax, [rsi+30h]
0x1800395b0  test    rax, rax
0x1800395b3  jz      short loc_1800395D9
0x1800395b5  mov     ecx, [rsi+28h]
0x1800395b8  test    rcx, rcx
0x1800395bb  jz      short loc_1800395C8
0x1800395bd  mov     byte ptr [rax], 0
0x1800395c0  add     rax, r12
0x1800395c3  sub     rcx, r12
0x1800395c6  jnz     short loc_1800395BD
0x1800395c8  mov     rcx, [rsi+30h]
0x1800395cc  call    CspFreeH
0x1800395d1  mov     qword ptr [rsi+30h], 0
0x1800395d9  mov     eax, ebx
0x1800395db  add     rsp, 58h
0x1800395df  pop     r15
0x1800395e1  pop     r14
0x1800395e3  pop     r13
0x1800395e5  pop     r12
0x1800395e7  pop     rdi
0x1800395e8  pop     rsi
0x1800395e9  pop     rbp
0x1800395ea  pop     rbx
0x1800395eb  retn
```
