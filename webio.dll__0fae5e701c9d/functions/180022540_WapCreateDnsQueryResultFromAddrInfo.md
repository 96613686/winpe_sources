# WapCreateDnsQueryResultFromAddrInfo

- ea: `0x180022540`
- end: `0x180022a93`
- name: `WapCreateDnsQueryResultFromAddrInfo`
- size: `1363`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002095c`
- `0x18005f910`

## callees

- `0x180022540`
- `0x18002e460`
- `0x1800391c0`
- `0x1800722f0`
- `0x180072c70`
- `0x180083f78`
- `0x180091678`
- `0x18009218c`
- `0x180092564`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022766`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800228f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022908`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800228f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022908`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022780`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022780`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800226ef`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800226ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a82`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002293a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002293a`

## pseudocode

```c
__int64 __fastcall WapCreateDnsQueryResultFromAddrInfo(
        unsigned int *a1,
        char a2,
        char a3,
        unsigned __int8 a4,
        __int64 a5,
        unsigned int a6,
        __int64 *a7)
{
  unsigned int *v7; // r15
  char v8; // si
  unsigned __int64 v9; // rdi
  unsigned int *v10; // rdx
  unsigned int *v11; // rax
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  const void **v17; // r12
  unsigned __int64 v18; // rbp
  unsigned __int64 v20; // r13
  unsigned __int64 QuadPart; // r10
  __int64 Heap; // rax
  __int64 v23; // rdi
  unsigned int *v24; // rbp
  __int64 v25; // rbx
  unsigned int v26; // eax
  size_t v27; // r8
  _WORD *v28; // rcx
  _WORD *v29; // rcx
  unsigned int v30; // ecx
  void *v31; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v33; // rax
  size_t v34; // r8
  size_t v35; // r8
  unsigned __int8 v36; // [rsp+40h] [rbp-78h]
  char v37; // [rsp+41h] [rbp-77h]
  unsigned int *v39; // [rsp+48h] [rbp-70h]
  __int64 TtlFromAddrInfo; // [rsp+50h] [rbp-68h]
  const void **v41; // [rsp+58h] [rbp-60h]
  HANDLE TargetHandle; // [rsp+68h] [rbp-50h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-40h] BYREF

  v7 = a1;
  v8 = a3;
  v9 = 0;
  *a7 = 0;
  v10 = 0;
  v11 = a1;
  v36 = a4;
  v37 = a3;
  v39 = 0;
  TargetHandle = 0;
  SystemTimeAsFileTime = 0;
  while ( v11 )
  {
    v30 = v11[1];
    if ( v30 == 2 || v30 == 23 )
    {
      if ( !v10 )
      {
        if ( v30 == 2 )
          v10 = v11;
        v39 = v10;
      }
      if ( !++v9 )
        return 87;
    }
    v11 = (unsigned int *)*((_QWORD *)v11 + 8);
  }
  if ( !v9 )
    return 87;
  v12 = -1;
  v41 = (const void **)(v7 + 6);
  v13 = *((_QWORD *)v7 + 3);
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v13 + 2 * v14) );
    v15 = 0;
  }
  else
  {
    v15 = 0;
    v14 = 0;
  }
  v16 = *((_QWORD *)v7 + 10);
  v17 = (const void **)(v7 + 20);
  if ( v16 )
  {
    do
      ++v12;
    while ( *(_WORD *)(v16 + 2 * v12) );
  }
  else
  {
    v12 = 0;
  }
  if ( a3 && (v9 < 2 || !v10 || v7[1] != 23) )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
    {
      WPP_SF_(1027, 10, WPP_4cc0ac28e49031c412f222b038a01f5a_Traceguids);
      a4 = v36;
      v15 = 0;
    }
    v8 = 0;
    v37 = 0;
  }
  v18 = v9 + 1;
  if ( !v8 )
    v18 = v9;
  if ( v18 > 0xFFFFFFFFFFFFFFLL )
    return 87;
  v20 = v18 << 7;
  QuadPart = (v18 << 7) + 2 * (v12 + v14) + 124;
  PerformanceCount.QuadPart = QuadPart;
  if ( QuadPart > 0x20000000 )
    return 87;
  TtlFromAddrInfo = 0;
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    WPP_SF_dd(1027, 11, WPP_4cc0ac28e49031c412f222b038a01f5a_Traceguids, *v7, v7[18]);
    QuadPart = PerformanceCount.QuadPart;
    a4 = v36;
  }
  if ( (*v7 & 0x80000000) != 0 )
  {
    if ( (int)v7[18] >= 4 )
    {
      if ( (xmmword_1800AD720 & 8) != 0 )
      {
        WPP_SF_q(1027, 12, WPP_4cc0ac28e49031c412f222b038a01f5a_Traceguids, *((_QWORD *)v7 + 12));
        QuadPart = PerformanceCount.QuadPart;
        a4 = v36;
      }
      if ( *((_QWORD *)v7 + 12) )
      {
        v31 = (void *)*((_QWORD *)v7 + 12);
        CurrentProcess = GetCurrentProcess();
        v33 = GetCurrentProcess();
        if ( !DuplicateHandle(v33, v31, CurrentProcess, &TargetHandle, 0, 0, 2u) )
          return WaGetLastError(v15);
        v8 = v37;
        QuadPart = PerformanceCount.QuadPart;
        a4 = v36;
      }
    }
    if ( (int)v7[18] >= 5 )
      TtlFromAddrInfo = WapGetTtlFromAddrInfo(v7, a4, a6);
  }
  Heap = WxAllocateHeapEx(v15, QuadPart);
  v23 = Heap;
  if ( Heap )
  {
    *(_DWORD *)Heap = 1381191236;
    *(_DWORD *)(Heap + 4) = 1;
    InitializeSRWLock((PSRWLOCK)(Heap + 8));
    PerformanceCount.QuadPart = 0;
    *(_QWORD *)(v23 + 24) = v23 + 16;
    *(_QWORD *)(v23 + 16) = v23 + 16;
    *(_QWORD *)(v23 + 32) = v23 + 120;
    *(_QWORD *)(v23 + 40) = v18;
    *(_QWORD *)(v23 + 48) = v23 + v20 + 120;
    *(_QWORD *)(v23 + 56) = v14;
    *(_QWORD *)(v23 + 72) = v12;
    *(_QWORD *)(v23 + 64) = v23 + v20 + 2 * v14 + 122;
    *(_QWORD *)(v23 + 80) = TargetHandle;
    *(_BYTE *)(v23 + 88) = a2;
    *(_QWORD *)(v23 + 96) = a5;
    *(_BYTE *)(v23 + 89) = v8;
    QueryPerformanceCounter(&PerformanceCount);
    *(LARGE_INTEGER *)(v23 + 104) = PerformanceCount;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)(v23 + 112) = *(_QWORD *)&SystemTimeAsFileTime + TtlFromAddrInfo;
    memset_0(*(void **)(v23 + 32), 0, v18 << 7);
    if ( v8 )
    {
      v34 = *((_QWORD *)v7 + 2);
      if ( v34 > 0x80 )
        v34 = 128;
      memcpy_0(*(void **)(v23 + 32), *((const void **)v7 + 4), v34);
      v24 = v39;
      v35 = *((_QWORD *)v39 + 2);
      if ( v35 > 0x80 )
        v35 = 128;
      memcpy_0((void *)(*(_QWORD *)(v23 + 32) + 128LL), *((const void **)v39 + 4), v35);
      v25 = 2;
    }
    else
    {
      v24 = v39;
      v25 = 0;
    }
    do
    {
      v26 = v7[1];
      if ( (v26 == 2 || v26 == 23) && (!v8 || v7 != v24) )
      {
        v27 = *((_QWORD *)v7 + 2);
        if ( v27 > 0x80 )
          v27 = 128;
        memcpy_0((void *)(*(_QWORD *)(v23 + 32) + (v25++ << 7)), *((const void **)v7 + 4), v27);
      }
      v7 = (unsigned int *)*((_QWORD *)v7 + 8);
    }
    while ( v7 );
    v28 = *(_WORD **)(v23 + 48);
    if ( *v41 )
      memcpy_0(v28, *v41, 2LL * *(_QWORD *)(v23 + 56) + 2);
    else
      *v28 = 0;
    v29 = *(_WORD **)(v23 + 64);
    if ( *v17 )
      memcpy_0(v29, *v17, 2LL * *(_QWORD *)(v23 + 72) + 2);
    else
      *v29 = 0;
    *a7 = v23;
    return 0;
  }
  else
  {
    if ( TargetHandle )
      CloseHandle(TargetHandle);
    return 14;
  }
}

```

## disassembly

```asm
0x180022540  mov     r11, rsp
0x180022543  push    rsi
0x180022544  push    rdi
0x180022545  push    r15
0x180022547  sub     rsp, 0A0h
0x18002254e  mov     rax, cs:__security_cookie
0x180022555  xor     rax, rsp
0x180022558  mov     [rsp+0B8h+var_38], rax
0x180022560  mov     rax, [rsp+0B8h+arg_30]
0x180022568  mov     r15, rcx
0x18002256b  xor     ecx, ecx
0x18002256d  mov     [r11+10h], rbx
0x180022571  mov     [r11+18h], rbp
0x180022575  movzx   esi, r8b
0x180022579  mov     [r11+20h], r12
0x18002257d  mov     edi, ecx
0x18002257f  mov     [rax], rcx
0x180022582  mov     [rsp+0B8h+var_76], dl
0x180022586  mov     edx, ecx
0x180022588  mov     [rsp+0B8h+var_58], rax
0x18002258d  mov     rax, r15
0x180022590  mov     [r11-20h], r13
0x180022594  mov     [rsp+0B8h+var_78], r9b
0x180022599  mov     [rsp+0B8h+var_77], r8b
0x18002259e  mov     [rsp+0B8h+var_70], rcx
0x1800225a3  mov     [r11-50h], rcx
0x1800225a7  mov     [r11-40h], rcx
0x1800225ab  mov     [r11-28h], r14
0x1800225af  test    rax, rax
0x1800225b2  jnz     loc_180022856
0x1800225b8  test    rdi, rdi
0x1800225bb  jz      short loc_18002262E
0x1800225bd  lea     rax, [r15+18h]
0x1800225c1  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800225c8  mov     [rsp+0B8h+var_60], rax
0x1800225cd  mov     rax, [rax]
0x1800225d0  test    rax, rax
0x1800225d3  jz      loc_180022966
0x1800225d9  mov     rbx, r14
0x1800225dc  nop     dword ptr [rax+00h]
0x1800225e0  inc     rbx
0x1800225e3  cmp     word ptr [rax+rbx*2], 0
0x1800225e8  jnz     short loc_1800225E0
0x1800225ea  xor     ecx, ecx
0x1800225ec  mov     rax, [r15+50h]
0x1800225f0  lea     r12, [r15+50h]
0x1800225f4  test    rax, rax
0x1800225f7  jz      loc_1800229C9
0x1800225fd  nop     dword ptr [rax]
0x180022600  inc     r14
0x180022603  cmp     word ptr [rax+r14*2], 0
0x180022609  jnz     short loc_180022600
0x18002260b  test    r8b, r8b
0x18002260e  jnz     loc_180022882
0x180022614  test    sil, sil
0x180022617  lea     rbp, [rdi+1]
0x18002261b  mov     rax, 0FFFFFFFFFFFFFFh
0x180022625  cmovz   rbp, rdi
0x180022629  cmp     rbp, rax
0x18002262c  jbe     short loc_180022678
0x18002262e  mov     eax, 57h ; 'W'
0x180022633  mov     r14, [rsp+0B8h+var_28]
0x18002263b  mov     r13, [rsp+0B8h+var_20]
0x180022643  mov     r12, [rsp+0B8h+arg_18]
0x18002264b  mov     rbp, [rsp+0B8h+arg_10]
0x180022653  mov     rbx, [rsp+0B8h+arg_8]
0x18002265b  mov     rcx, [rsp+0B8h+var_38]
0x180022663  xor     rcx, rsp; StackCookie
0x180022666  call    __security_check_cookie
0x18002266b  add     rsp, 0A0h
0x180022672  pop     r15
0x180022674  pop     rdi
0x180022675  pop     rsi
0x180022676  retn
0x180022678  mov     r13, rbp
0x18002267b  lea     rax, [r14+rbx]
0x18002267f  shl     r13, 7
0x180022683  lea     r10, ds:7Ch[rax*2]
0x18002268b  add     r10, r13
0x18002268e  mov     qword ptr [rsp+0B8h+PerformanceCount], r10
0x180022693  cmp     r10, 20000000h
0x18002269a  ja      short loc_18002262E
0x18002269c  test    byte ptr cs:xmmword_1800AD720, 8
0x1800226a3  mov     [rsp+0B8h+var_68], rcx
0x1800226a8  jnz     loc_1800229F4
0x1800226ae  cmp     dword ptr [r15], 0
0x1800226b2  jge     short loc_1800226CA
0x1800226b4  cmp     dword ptr [r15+48h], 4
0x1800226b9  jge     loc_1800228DD
0x1800226bf  cmp     dword ptr [r15+48h], 5
0x1800226c4  jge     loc_180022A64
0x1800226ca  mov     rdx, r10
0x1800226cd  call    WxAllocateHeapEx
0x1800226d2  mov     rdi, rax
0x1800226d5  test    rax, rax
0x1800226d8  jz      loc_1800228A2
0x1800226de  lea     rcx, [rax+8]; SRWLock
0x1800226e2  mov     dword ptr [rax], 52534E44h
0x1800226e8  mov     dword ptr [rax+4], 1
0x1800226ef  call    cs:__imp_InitializeSRWLock
0x1800226f6  nop     dword ptr [rax+rax+00h]
0x1800226fb  lea     rax, [rdi+10h]
0x1800226ff  mov     qword ptr [rsp+0B8h+PerformanceCount], 0
0x180022708  mov     [rax+8], rax
0x18002270c  lea     rcx, [rsp+0B8h+PerformanceCount]; lpPerformanceCount
0x180022711  mov     [rax], rax
0x180022714  lea     rax, [rdi+78h]
0x180022718  mov     [rdi+20h], rax
0x18002271c  lea     rax, [r13+78h]
0x180022720  add     rax, rdi
0x180022723  mov     [rdi+28h], rbp
0x180022727  mov     [rdi+30h], rax
0x18002272b  lea     rax, ds:7Ah[rbx*2]
0x180022733  add     rax, r13
0x180022736  mov     [rdi+38h], rbx
0x18002273a  add     rax, rdi
0x18002273d  mov     [rdi+48h], r14
0x180022741  mov     [rdi+40h], rax
0x180022745  mov     rax, [rsp+0B8h+TargetHandle]
0x18002274a  mov     [rdi+50h], rax
0x18002274e  movzx   eax, [rsp+0B8h+var_76]
0x180022753  mov     [rdi+58h], al
0x180022756  mov     rax, [rsp+0B8h+arg_20]
0x18002275e  mov     [rdi+60h], rax
0x180022762  mov     [rdi+59h], sil
0x180022766  call    cs:__imp_QueryPerformanceCounter
0x18002276d  nop     dword ptr [rax+rax+00h]
0x180022772  mov     rax, qword ptr [rsp+0B8h+PerformanceCount]
0x180022777  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002277c  mov     [rdi+68h], rax
0x180022780  call    cs:__imp_GetSystemTimeAsFileTime
0x180022787  nop     dword ptr [rax+rax+00h]
0x18002278c  mov     rcx, [rsp+0B8h+var_68]
0x180022791  mov     r8, r13; Size
0x180022794  add     rcx, qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x180022799  xor     edx, edx; Val
0x18002279b  mov     [rdi+70h], rcx
0x18002279f  mov     rcx, [rdi+20h]; void *
0x1800227a3  call    memset_0
0x1800227a8  mov     r14d, 80h
0x1800227ae  test    sil, sil
0x1800227b1  jnz     loc_180022979
0x1800227b7  mov     rbp, [rsp+0B8h+var_70]
0x1800227bc  xor     ebx, ebx
0x1800227be  mov     eax, [r15+4]
0x1800227c2  cmp     eax, 2
0x1800227c5  jnz     loc_1800229BB
0x1800227cb  test    sil, sil
0x1800227ce  jnz     loc_180022958
0x1800227d4  mov     r8, [r15+10h]
0x1800227d8  mov     rcx, rbx
0x1800227db  mov     rdx, [r15+20h]; Src
0x1800227df  cmp     r8, r14
0x1800227e2  cmova   r8, r14; Size
0x1800227e6  shl     rcx, 7
0x1800227ea  add     rcx, [rdi+20h]; void *
0x1800227ee  call    memcpy_0
0x1800227f3  inc     rbx
0x1800227f6  mov     r15, [r15+40h]
0x1800227fa  test    r15, r15
0x1800227fd  jnz     short loc_1800227BE
0x1800227ff  mov     rdx, [rsp+0B8h+var_60]
0x180022804  mov     rcx, [rdi+30h]; void *
0x180022808  mov     rdx, [rdx]; Src
0x18002280b  test    rdx, rdx
0x18002280e  jz      loc_18002296F
0x180022814  mov     r8, [rdi+38h]
0x180022818  lea     r8, ds:2[r8*2]; Size
0x180022820  call    memcpy_0
0x180022825  mov     rdx, [r12]; Src
0x180022829  mov     rcx, [rdi+40h]; void *
0x18002282d  test    rdx, rdx
0x180022830  jz      loc_1800228D3
0x180022836  mov     r8, [rdi+48h]
0x18002283a  lea     r8, ds:2[r8*2]; Size
0x180022842  call    memcpy_0
0x180022847  mov     rax, [rsp+0B8h+var_58]
0x18002284c  mov     [rax], rdi
0x18002284f  xor     eax, eax
0x180022851  jmp     loc_180022633
0x180022856  mov     ecx, [rax+4]
0x180022859  cmp     ecx, 2
0x18002285c  jnz     short loc_1800228BA
0x18002285e  test    rdx, rdx
0x180022861  jnz     short loc_18002286F
0x180022863  cmp     ecx, 2
0x180022866  cmovz   rdx, rax
0x18002286a  mov     [rsp+0B8h+var_70], rdx
0x18002286f  add     rdi, 1
0x180022873  jz      loc_18002262E
0x180022879  mov     rax, [rax+40h]
0x18002287d  jmp     loc_1800225AF
0x180022882  cmp     rdi, 2
0x180022886  jnb     short loc_1800228C1
0x180022888  test    byte ptr cs:xmmword_1800AD720, 8
0x18002288f  jnz     loc_1800229D1
0x180022895  xor     sil, sil
0x180022898  mov     [rsp+0B8h+var_77], sil
0x18002289d  jmp     loc_180022614
0x1800228a2  mov     rcx, [rsp+0B8h+TargetHandle]; hObject
0x1800228a7  test    rcx, rcx
0x1800228aa  jnz     loc_180022A82
0x1800228b0  mov     eax, 0Eh
0x1800228b5  jmp     loc_180022633
0x1800228ba  cmp     ecx, 17h
0x1800228bd  jnz     short loc_180022879
0x1800228bf  jmp     short loc_18002285E
0x1800228c1  test    rdx, rdx
0x1800228c4  jz      short loc_180022888
0x1800228c6  cmp     dword ptr [r15+4], 17h
0x1800228cb  jz      loc_180022614
0x1800228d1  jmp     short loc_180022888
0x1800228d3  xor     eax, eax
0x1800228d5  mov     [rcx], ax
0x1800228d8  jmp     loc_180022847
0x1800228dd  test    byte ptr cs:xmmword_1800AD720, 8
0x1800228e4  jnz     loc_180022A25
0x1800228ea  cmp     qword ptr [r15+60h], 0
0x1800228ef  jz      loc_1800226BF
0x1800228f5  mov     rsi, [r15+60h]
0x1800228f9  call    cs:__imp_GetCurrentProcess
0x180022900  nop     dword ptr [rax+rax+00h]
0x180022905  mov     rdi, rax
0x180022908  call    cs:__imp_GetCurrentProcess
0x18002290f  nop     dword ptr [rax+rax+00h]
0x180022914  mov     [rsp+0B8h+dwOptions], 2; dwOptions
0x18002291c  lea     r9, [rsp+0B8h+TargetHandle]; lpTargetHandle
0x180022921  mov     rcx, rax; hSourceProcessHandle
0x180022924  mov     [rsp+0B8h+bInheritHandle], 0; bInheritHandle
0x18002292c  mov     r8, rdi; hTargetProcessHandle
0x18002292f  mov     [rsp+0B8h+dwDesiredAccess], 0; dwDesiredAccess
0x180022937  mov     rdx, rsi; hSourceHandle
0x18002293a  call    cs:__imp_DuplicateHandle
0x180022941  nop     dword ptr [rax+rax+00h]
0x180022946  test    eax, eax
0x180022948  jnz     loc_180022A4F
0x18002294e  call    WaGetLastError
0x180022953  jmp     loc_180022633
0x180022958  cmp     r15, rbp
0x18002295b  jnz     loc_1800227D4
0x180022961  jmp     loc_1800227F6
0x180022966  xor     ecx, ecx
0x180022968  mov     ebx, ecx
0x18002296a  jmp     loc_1800225EC
0x18002296f  xor     eax, eax
0x180022971  mov     [rcx], ax
0x180022974  jmp     loc_180022825
0x180022979  mov     r8, [r15+10h]
0x18002297d  mov     rdx, [r15+20h]; Src
0x180022981  cmp     r8, r14
0x180022984  mov     rcx, [rdi+20h]; void *
0x180022988  cmova   r8, r14; Size
0x18002298c  call    memcpy_0
0x180022991  mov     rbp, [rsp+0B8h+var_70]
0x180022996  mov     rcx, [rdi+20h]
0x18002299a  mov     r8, [rbp+10h]
0x18002299e  mov     rdx, [rbp+20h]; Src
0x1800229a2  cmp     r8, r14
0x1800229a5  cmova   r8, r14; Size
0x1800229a9  add     rcx, r14; void *
0x1800229ac  call    memcpy_0
0x1800229b1  mov     ebx, 2
0x1800229b6  jmp     loc_1800227BE
0x1800229bb  cmp     eax, 17h
0x1800229be  jz      loc_1800227CB
0x1800229c4  jmp     loc_1800227F6
0x1800229c9  mov     r14, rcx
0x1800229cc  jmp     loc_18002260B
0x1800229d1  mov     edx, 0Ah
0x1800229d6  lea     r8, WPP_4cc0ac28e49031c412f222b038a01f5a_Traceguids
0x1800229dd  mov     ecx, 403h
0x1800229e2  call    WPP_SF_
0x1800229e7  movzx   r9d, [rsp+0B8h+var_78]
0x1800229ed  xor     ecx, ecx
0x1800229ef  jmp     loc_180022895
0x1800229f4  mov     eax, [r15+48h]
0x1800229f8  lea     r8, WPP_4cc0ac28e49031c412f222b038a01f5a_Traceguids
0x1800229ff  mov     r9d, [r15]
0x180022a02  mov     edx, 0Bh
0x180022a07  mov     ecx, 403h
0x180022a0c  mov     [rsp+0B8h+dwDesiredAccess], eax
0x180022a10  call    WPP_SF_dd
0x180022a15  mov     r10, qword ptr [rsp+0B8h+PerformanceCount]
0x180022a1a  movzx   r9d, [rsp+0B8h+var_78]
0x180022a20  jmp     loc_1800226AE
0x180022a25  mov     r9, [r15+60h]
0x180022a29  lea     r8, WPP_4cc0ac28e49031c412f222b038a01f5a_Traceguids
0x180022a30  mov     edx, 0Ch
0x180022a35  mov     ecx, 403h
0x180022a3a  call    WPP_SF_q
0x180022a3f  mov     r10, qword ptr [rsp+0B8h+PerformanceCount]
0x180022a44  movzx   r9d, [rsp+0B8h+var_78]
0x180022a4a  jmp     loc_1800228EA
0x180022a4f  movzx   esi, [rsp+0B8h+var_77]
0x180022a54  mov     r10, qword ptr [rsp+0B8h+PerformanceCount]
0x180022a59  movzx   r9d, [rsp+0B8h+var_78]
0x180022a5f  jmp     loc_1800226BF
0x180022a64  mov     r8d, [rsp+0B8h+arg_28]
0x180022a6c  movzx   edx, r9b
0x180022a70  mov     rcx, r15
  ... truncated ...
```
