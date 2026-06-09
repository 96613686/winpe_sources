# CEventWrite

- ea: `0x18000b660`
- end: `0x18000bb84`
- name: `CEventWrite`
- size: `1316`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000a850`

## callees

- `0x18000b660`
- `0x18000bb90`
- `0x18003d270`
- `0x18003dd2c`
- `0x18003f485`
- `0x18003f491`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b873`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b8ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bb68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b873`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b8ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bb68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b737`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b795`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b7d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b837`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b737`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b795`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b7d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b77e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b77e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b91b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b91b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb4e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000b6fe`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000b6fe`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b99f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b99f`
- `ntdll!RtlEnterCriticalSection` at `0x18000b6e6`
- `ntdll!RtlEnterCriticalSection` at `0x18000b6e6`
- `ntdll!EtwEventWrite` at `0x18000b95a`
- `ntdll!EtwEventWrite` at `0x18000b95a`

## pseudocode

```c
__int64 __fastcall CEventWrite(__int64 *a1, _OWORD *a2, unsigned int a3, struct _FILETIME a4, DWORD a5)
{
  struct _FILETIME v6; // rdi
  _BYTE *v8; // rax
  _BYTE *v9; // r15
  HANDLE ProcessHeap; // rax
  char *v11; // rax
  char *v12; // r14
  bool v13; // zf
  unsigned int v14; // r12d
  HANDLE v15; // rax
  _OWORD *v16; // rax
  HANDLE v17; // rax
  void *v18; // rax
  void **v19; // r13
  unsigned int j; // ebp
  unsigned int v21; // ebx
  _QWORD *v22; // rdi
  HANDLE v23; // rax
  void *v24; // rcx
  DWORD v25; // r12d
  struct _FILETIME **v26; // rbx
  struct _FILETIME ***v27; // rsi
  __int64 v28; // r12
  struct _FILETIME **v29; // r13
  __int64 v30; // rdi
  __int64 v31; // rdx
  struct _FILETIME **v32; // rcx
  struct _FILETIME *v33; // rax
  HANDLE v34; // rax
  struct _FILETIME *v35; // rdi
  __int64 v36; // rdx
  unsigned int v37; // edi
  struct _FILETIME ***v38; // rcx
  _QWORD *v40; // rdx
  struct _FILETIME *v41; // r13
  __int64 v42; // rax
  unsigned int v43; // ebp
  unsigned int k; // esi
  HANDLE v45; // rax
  HANDLE v46; // rax
  unsigned int i; // ebx
  void *v48; // rdi
  HANDLE v49; // rax
  void *v50; // rbx
  HANDLE v51; // rax
  void *v52; // rbx
  HANDLE v53; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-C8h] BYREF
  unsigned int v55; // [rsp+28h] [rbp-C0h]
  struct _FILETIME v56; // [rsp+30h] [rbp-B8h]
  _OWORD *v57; // [rsp+38h] [rbp-B0h]
  _QWORD Buffer[2]; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v59; // [rsp+50h] [rbp-98h]
  __int128 v60; // [rsp+60h] [rbp-88h]
  __int64 v61; // [rsp+70h] [rbp-78h]
  __int64 v62; // [rsp+78h] [rbp-70h]
  __int64 v63; // [rsp+80h] [rbp-68h]

  v62 = *a1;
  v56 = a4;
  v55 = a3;
  v6 = a4;
  v57 = a2;
  Buffer[0] = 0;
  Buffer[1] = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v63 = 0;
  if ( !byte_1800A5340 )
    return 6;
  RtlEnterCriticalSection(&stru_1800A52B0);
  v8 = RtlLookupElementGenericTableAvl(&Table, Buffer);
  v9 = v8;
  if ( !v8 || !v8[64] )
  {
    v37 = 6;
    goto LABEL_30;
  }
  ProcessHeap = GetProcessHeap();
  v11 = (char *)HeapAlloc(ProcessHeap, 0, 0x38u);
  v12 = v11;
  if ( !v11 )
  {
LABEL_56:
    v37 = 14;
    goto LABEL_30;
  }
  v13 = (*((_DWORD *)v9 + 8) & 1) == 0;
  *(_OWORD *)v11 = 0;
  if ( !v13 )
    v6 = 0;
  v14 = a3;
  *((_OWORD *)v11 + 1) = 0;
  if ( !v13 )
    v14 = 0;
  SystemTimeAsFileTime = v6;
  *((_OWORD *)v11 + 2) = 0;
  *((_QWORD *)v11 + 6) = 0;
  v15 = GetProcessHeap();
  v16 = HeapAlloc(v15, 0, 0x10u);
  *(_QWORD *)v12 = v16;
  if ( !v16 )
  {
    v19 = (void **)(v12 + 16);
LABEL_48:
    if ( *v19 )
    {
      for ( i = 0; i < v14; ++i )
      {
        v48 = (void *)*((_QWORD *)*v19 + 2 * i);
        if ( !v48 )
          break;
        v49 = GetProcessHeap();
        HeapFree(v49, 0, v48);
      }
    }
    v50 = *v19;
    if ( *v19 )
    {
      v51 = GetProcessHeap();
      HeapFree(v51, 0, v50);
    }
    v52 = *(void **)v12;
    if ( *(_QWORD *)v12 )
    {
      v53 = GetProcessHeap();
      HeapFree(v53, 0, v52);
    }
    goto LABEL_56;
  }
  *v16 = *a2;
  *((_DWORD *)v12 + 2) = v14;
  v17 = GetProcessHeap();
  v18 = HeapAlloc(v17, 0, 16LL * v14);
  *((_QWORD *)v12 + 2) = v18;
  v19 = (void **)(v12 + 16);
  if ( !v18 )
    goto LABEL_48;
  memset_0(v18, 0, 16LL * *((unsigned int *)v12 + 2));
  for ( j = 0; j < v14; ++j )
  {
    *((_DWORD *)*v19 + 4 * j + 2) = *(_DWORD *)(*(_QWORD *)&v6 + 16LL * j + 8);
    v21 = *(_DWORD *)(*(_QWORD *)&v6 + 16LL * j + 8);
    v22 = *v19;
    v23 = GetProcessHeap();
    v22[2 * j] = HeapAlloc(v23, 0, v21);
    v24 = (void *)*((_QWORD *)*v19 + 2 * j);
    if ( !v24 )
      goto LABEL_48;
    v6 = SystemTimeAsFileTime;
    memcpy_0(
      v24,
      *(const void **)(*(_QWORD *)&SystemTimeAsFileTime + 16LL * j),
      *(unsigned int *)(*(_QWORD *)&SystemTimeAsFileTime + 16LL * j + 8));
  }
  GetSystemTimeAsFileTime((LPFILETIME)v12 + 3);
  v25 = a5;
  v26 = (struct _FILETIME **)(v9 + 40);
  *((_DWORD *)v12 + 8) = a5;
  v27 = (struct _FILETIME ***)*((_QWORD *)v9 + 5);
  if ( v27 != (struct _FILETIME ***)(v9 + 40) )
  {
    do
    {
      v28 = *((unsigned int *)v27 - 2);
      v29 = *v27;
      SystemTimeAsFileTime = 0;
      if ( (_DWORD)v28 != -1 )
      {
        v30 = (__int64)*(v27 - 2);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v31 = *(_QWORD *)&SystemTimeAsFileTime - v30;
        if ( *(_QWORD *)&SystemTimeAsFileTime - v30 < 0 || v31 > 10000 * v28 )
        {
          v32 = *v27;
          if ( (*v27)[1] != (struct _FILETIME *)v27 )
            goto LABEL_57;
          v33 = (struct _FILETIME *)v27[1];
          if ( (struct _FILETIME ***)*v33 != v27 )
            goto LABEL_57;
          *v33 = (struct _FILETIME)v32;
          v32[1] = v33;
          deinitEventEntry(v27 - 5, v31);
          v34 = GetProcessHeap();
          HeapFree(v34, 0, v27 - 5);
        }
      }
      v27 = (struct _FILETIME ***)v29;
    }
    while ( v29 != v26 );
    v25 = a5;
  }
  v35 = *v26;
  while ( 1 )
  {
LABEL_25:
    if ( v35 == (struct _FILETIME *)v26 )
    {
      v37 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))EtwEventWrite)(*((_QWORD *)v9 + 7), v57, v55, v56);
      if ( v37 || !v25 )
      {
        deinitEventEntry(v12, v36);
        v45 = GetProcessHeap();
        HeapFree(v45, 0, v12);
        goto LABEL_30;
      }
      v38 = (struct _FILETIME ***)*((_QWORD *)v9 + 6);
      if ( *v38 == v26 )
      {
        *((_QWORD *)v12 + 5) = v26;
        *((_QWORD *)v12 + 6) = v38;
        *v38 = (struct _FILETIME **)(v12 + 40);
        *((_QWORD *)v9 + 6) = v12 + 40;
        goto LABEL_30;
      }
LABEL_57:
      __fastfail(3u);
    }
    v40 = (_QWORD *)v35[-5];
    v41 = v35;
    v35 = (struct _FILETIME *)*v35;
    v42 = **(_QWORD **)v12 - *v40;
    if ( !v42 )
      v42 = *(_QWORD *)(*(_QWORD *)v12 + 8LL) - v40[1];
    if ( !v42 )
    {
      v43 = *((_DWORD *)v12 + 2);
      if ( v43 == v41[-4].dwLowDateTime )
        break;
    }
  }
  for ( k = 0; k < v43; ++k )
  {
    if ( memcmp_0(
           *(const void **)(*((_QWORD *)v12 + 2) + 16LL * k),
           *(const void **)(*(_QWORD *)&v41[-3] + 16LL * k),
           *(unsigned int *)(*((_QWORD *)v12 + 2) + 16LL * k + 8)) )
    {
      goto LABEL_25;
    }
  }
  if ( (v9[32] & 2) != 0 )
  {
    GetSystemTimeAsFileTime(v41 - 2);
    v41[-1].dwLowDateTime = v25;
  }
  deinitEventEntry(v12, v40);
  v46 = GetProcessHeap();
  HeapFree(v46, 0, v12);
  v37 = 0;
LABEL_30:
  RtlLeaveCriticalSection(&stru_1800A52B0);
  return v37;
}

```

## disassembly

```asm
0x18000b660  push    rbx
0x18000b662  push    rbp
0x18000b663  push    rsi
0x18000b664  push    rdi
0x18000b665  push    r12
0x18000b667  push    r13
0x18000b669  push    r14
0x18000b66b  push    r15
0x18000b66d  sub     rsp, 0A8h
0x18000b674  mov     rax, cs:__security_cookie
0x18000b67b  xor     rax, rsp
0x18000b67e  mov     [rsp+0E8h+var_58], rax
0x18000b686  mov     rax, [rcx]
0x18000b689  xor     esi, esi
0x18000b68b  mov     [rsp+0E8h+var_70], rax
0x18000b690  mov     ebx, r8d
0x18000b693  movzx   eax, cs:byte_1800A5340
0x18000b69a  xorps   xmm0, xmm0
0x18000b69d  mov     [rsp+0E8h+var_B8], r9
0x18000b6a2  xorps   xmm1, xmm1
0x18000b6a5  mov     [rsp+0E8h+var_C0], ebx
0x18000b6a9  mov     rdi, r9
0x18000b6ac  mov     [rsp+0E8h+var_B0], rdx
0x18000b6b1  mov     r13, rdx
0x18000b6b4  mov     [rsp+0E8h+Buffer], rsi
0x18000b6b9  mov     [rsp+0E8h+var_A0], rsi
0x18000b6be  movdqa  [rsp+0E8h+var_98], xmm0
0x18000b6c4  movdqa  [rsp+0E8h+var_88], xmm1
0x18000b6ca  mov     [rsp+0E8h+var_78], rsi
0x18000b6cf  mov     [rsp+0E8h+var_68], rsi
0x18000b6d7  test    al, al
0x18000b6d9  jz      loc_18000BAB0
0x18000b6df  lea     rcx, stru_1800A52B0; CriticalSection
0x18000b6e6  call    cs:__imp_RtlEnterCriticalSection
0x18000b6ed  nop     dword ptr [rax+rax+00h]
0x18000b6f2  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x18000b6f7  lea     rcx, Table; Table
0x18000b6fe  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000b705  nop     dword ptr [rax+rax+00h]
0x18000b70a  mov     r15, rax
0x18000b70d  test    rax, rax
0x18000b710  jz      loc_18000BAA6
0x18000b716  cmp     [rax+40h], sil
0x18000b71a  jz      loc_18000BAA6
0x18000b720  call    cs:__imp_GetProcessHeap
0x18000b727  nop     dword ptr [rax+rax+00h]
0x18000b72c  xor     edx, edx; dwFlags
0x18000b72e  mov     r8d, 38h ; '8'; dwBytes
0x18000b734  mov     rcx, rax; hHeap
0x18000b737  call    cs:__imp_HeapAlloc
0x18000b73e  nop     dword ptr [rax+rax+00h]
0x18000b743  mov     r14, rax
0x18000b746  test    rax, rax
0x18000b749  jz      loc_18000BB5A
0x18000b74f  test    dword ptr [r15+20h], 1
0x18000b757  xorps   xmm0, xmm0
0x18000b75a  movups  xmmword ptr [r14], xmm0
0x18000b75e  cmovnz  rdi, rsi
0x18000b762  mov     r12d, ebx
0x18000b765  movups  xmmword ptr [r14+10h], xmm0
0x18000b76a  cmovnz  r12d, esi
0x18000b76e  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18000b773  xor     eax, eax
0x18000b775  movups  xmmword ptr [r14+20h], xmm0
0x18000b77a  mov     [r14+30h], rax
0x18000b77e  call    cs:__imp_GetProcessHeap
0x18000b785  nop     dword ptr [rax+rax+00h]
0x18000b78a  xor     edx, edx; dwFlags
0x18000b78c  mov     r8d, 10h; dwBytes
0x18000b792  mov     rcx, rax; hHeap
0x18000b795  call    cs:__imp_HeapAlloc
0x18000b79c  nop     dword ptr [rax+rax+00h]
0x18000b7a1  mov     [r14], rax
0x18000b7a4  test    rax, rax
0x18000b7a7  jz      loc_18000BABE
0x18000b7ad  movups  xmm0, xmmword ptr [r13+0]
0x18000b7b2  mov     ebx, r12d
0x18000b7b5  shl     rbx, 4
0x18000b7b9  movups  xmmword ptr [rax], xmm0
0x18000b7bc  mov     [r14+8], r12d
0x18000b7c0  call    cs:__imp_GetProcessHeap
0x18000b7c7  nop     dword ptr [rax+rax+00h]
0x18000b7cc  mov     r8, rbx; dwBytes
0x18000b7cf  xor     edx, edx; dwFlags
0x18000b7d1  mov     rcx, rax; hHeap
0x18000b7d4  call    cs:__imp_HeapAlloc
0x18000b7db  nop     dword ptr [rax+rax+00h]
0x18000b7e0  mov     [r14+10h], rax
0x18000b7e4  lea     r13, [r14+10h]
0x18000b7e8  test    rax, rax
0x18000b7eb  jz      loc_18000BAC2
0x18000b7f1  mov     r8d, [r14+8]
0x18000b7f5  xor     edx, edx; Val
0x18000b7f7  shl     r8, 4; Size
0x18000b7fb  mov     rcx, rax; void *
0x18000b7fe  call    memset_0
0x18000b803  mov     ebp, esi
0x18000b805  cmp     ebp, r12d
0x18000b808  jnb     short loc_18000B86F
0x18000b80a  mov     rcx, [r13+0]
0x18000b80e  mov     esi, ebp
0x18000b810  add     rsi, rsi
0x18000b813  mov     eax, [rdi+rsi*8+8]
0x18000b817  mov     [rcx+rsi*8+8], eax
0x18000b81b  mov     ebx, [rdi+rsi*8+8]
0x18000b81f  mov     rdi, [r13+0]
0x18000b823  call    cs:__imp_GetProcessHeap
0x18000b82a  nop     dword ptr [rax+rax+00h]
0x18000b82f  mov     r8d, ebx; dwBytes
0x18000b832  xor     edx, edx; dwFlags
0x18000b834  mov     rcx, rax; hHeap
0x18000b837  call    cs:__imp_HeapAlloc
0x18000b83e  nop     dword ptr [rax+rax+00h]
0x18000b843  mov     [rdi+rsi*8], rax
0x18000b847  mov     rax, [r13+0]
0x18000b84b  mov     rcx, [rax+rsi*8]; void *
0x18000b84f  test    rcx, rcx
0x18000b852  jz      loc_18000BABA
0x18000b858  mov     rdi, qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x18000b85d  mov     r8d, [rdi+rsi*8+8]; Size
0x18000b862  mov     rdx, [rdi+rsi*8]; Src
0x18000b866  call    memcpy_0
0x18000b86b  inc     ebp
0x18000b86d  jmp     short loc_18000B805
0x18000b86f  lea     rcx, [r14+18h]; lpSystemTimeAsFileTime
0x18000b873  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b87a  nop     dword ptr [rax+rax+00h]
0x18000b87f  mov     r12d, [rsp+0E8h+arg_20]
0x18000b887  lea     rbx, [r15+28h]
0x18000b88b  mov     [r14+20h], r12d
0x18000b88f  mov     rsi, [rbx]
0x18000b892  cmp     rsi, rbx
0x18000b895  jz      loc_18000B93B
0x18000b89b  mov     r12d, [rsi-8]
0x18000b89f  mov     r13, [rsi]
0x18000b8a2  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000b8ab  cmp     r12d, 0FFFFFFFFh
0x18000b8af  jz      short loc_18000B927
0x18000b8b1  mov     rdi, [rsi-10h]
0x18000b8b5  lea     rcx, [rsp+0E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000b8ba  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b8c1  nop     dword ptr [rax+rax+00h]
0x18000b8c6  mov     rdx, qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x18000b8cb  sub     rdx, rdi
0x18000b8ce  js      short loc_18000B8DC
0x18000b8d0  imul    rcx, r12, 2710h
0x18000b8d7  cmp     rdx, rcx
0x18000b8da  jle     short loc_18000B927
0x18000b8dc  mov     rcx, [rsi]
0x18000b8df  cmp     [rcx+8], rsi
0x18000b8e3  jnz     loc_18000BB7D
0x18000b8e9  mov     rax, [rsi+8]
0x18000b8ed  cmp     [rax], rsi
0x18000b8f0  jnz     loc_18000BB7D
0x18000b8f6  mov     [rax], rcx
0x18000b8f9  mov     [rcx+8], rax
0x18000b8fd  lea     rcx, [rsi-28h]
0x18000b901  call    deinitEventEntry
0x18000b906  call    cs:__imp_GetProcessHeap
0x18000b90d  nop     dword ptr [rax+rax+00h]
0x18000b912  lea     r8, [rsi-28h]; lpMem
0x18000b916  xor     edx, edx; dwFlags
0x18000b918  mov     rcx, rax; hHeap
0x18000b91b  call    cs:__imp_HeapFree
0x18000b922  nop     dword ptr [rax+rax+00h]
0x18000b927  mov     rsi, r13
0x18000b92a  cmp     r13, rbx
0x18000b92d  jnz     loc_18000B89B
0x18000b933  mov     r12d, [rsp+0E8h+arg_20]
0x18000b93b  mov     rdi, [rbx]
0x18000b93e  cmp     rdi, rbx
0x18000b941  jnz     loc_18000B9D2
0x18000b947  mov     r9, [rsp+0E8h+var_B8]
0x18000b94c  mov     r8d, [rsp+0E8h+var_C0]
0x18000b951  mov     rdx, [rsp+0E8h+var_B0]
0x18000b956  mov     rcx, [r15+38h]
0x18000b95a  call    cs:__imp_EtwEventWrite
0x18000b961  nop     dword ptr [rax+rax+00h]
0x18000b966  mov     edi, eax
0x18000b968  test    eax, eax
0x18000b96a  jnz     loc_18000BA3F
0x18000b970  test    r12d, r12d
0x18000b973  jz      loc_18000BA3F
0x18000b979  mov     rcx, [rbx+8]
0x18000b97d  cmp     [rcx], rbx
0x18000b980  jnz     loc_18000BB7D
0x18000b986  lea     rax, [r14+28h]
0x18000b98a  mov     [rax], rbx
0x18000b98d  mov     [rax+8], rcx
0x18000b991  mov     [rcx], rax
0x18000b994  mov     [rbx+8], rax
0x18000b998  lea     rcx, stru_1800A52B0; CriticalSection
0x18000b99f  call    cs:__imp_RtlLeaveCriticalSection
0x18000b9a6  nop     dword ptr [rax+rax+00h]
0x18000b9ab  mov     eax, edi
0x18000b9ad  mov     rcx, [rsp+0E8h+var_58]
0x18000b9b5  xor     rcx, rsp; StackCookie
0x18000b9b8  call    __security_check_cookie
0x18000b9bd  add     rsp, 0A8h
0x18000b9c4  pop     r15
0x18000b9c6  pop     r14
0x18000b9c8  pop     r13
0x18000b9ca  pop     r12
0x18000b9cc  pop     rdi
0x18000b9cd  pop     rsi
0x18000b9ce  pop     rbp
0x18000b9cf  pop     rbx
0x18000b9d0  retn
0x18000b9d2  mov     rdx, [rdi-28h]
0x18000b9d6  lea     rax, [rdi-28h]
0x18000b9da  mov     rcx, [r14]
0x18000b9dd  mov     r13, rdi
0x18000b9e0  mov     rdi, [rdi]
0x18000b9e3  mov     rax, [rcx]
0x18000b9e6  sub     rax, [rdx]
0x18000b9e9  jnz     short loc_18000B9F3
0x18000b9eb  mov     rax, [rcx+8]
0x18000b9ef  sub     rax, [rdx+8]
0x18000b9f3  test    rax, rax
0x18000b9f6  jnz     loc_18000B93E
0x18000b9fc  mov     ebp, [r14+8]
0x18000ba00  cmp     ebp, [r13-20h]
0x18000ba04  jnz     loc_18000B93E
0x18000ba0a  xor     esi, esi
0x18000ba0c  nop     dword ptr [rax+00h]
0x18000ba10  cmp     esi, ebp
0x18000ba12  jnb     short loc_18000BA6C
0x18000ba14  mov     rax, [r14+10h]
0x18000ba18  mov     rdx, [r13-18h]
0x18000ba1c  mov     ecx, esi
0x18000ba1e  add     rcx, rcx
0x18000ba21  mov     r8d, [rax+rcx*8+8]; Size
0x18000ba26  mov     rdx, [rdx+rcx*8]; Buf2
0x18000ba2a  mov     rcx, [rax+rcx*8]; Buf1
0x18000ba2e  call    memcmp_0
0x18000ba33  test    eax, eax
0x18000ba35  jnz     loc_18000B93E
0x18000ba3b  inc     esi
0x18000ba3d  jmp     short loc_18000BA10
0x18000ba3f  mov     rcx, r14
0x18000ba42  call    deinitEventEntry
0x18000ba47  call    cs:__imp_GetProcessHeap
0x18000ba4e  nop     dword ptr [rax+rax+00h]
0x18000ba53  mov     r8, r14; lpMem
0x18000ba56  xor     edx, edx; dwFlags
0x18000ba58  mov     rcx, rax; hHeap
0x18000ba5b  call    cs:__imp_HeapFree
0x18000ba62  nop     dword ptr [rax+rax+00h]
0x18000ba67  jmp     loc_18000B998
0x18000ba6c  test    byte ptr [r15+20h], 2
0x18000ba71  jnz     loc_18000BB64
0x18000ba77  mov     rcx, r14
0x18000ba7a  call    deinitEventEntry
0x18000ba7f  call    cs:__imp_GetProcessHeap
0x18000ba86  nop     dword ptr [rax+rax+00h]
0x18000ba8b  mov     r8, r14; lpMem
0x18000ba8e  xor     edx, edx; dwFlags
0x18000ba90  mov     rcx, rax; hHeap
0x18000ba93  call    cs:__imp_HeapFree
0x18000ba9a  nop     dword ptr [rax+rax+00h]
0x18000ba9f  xor     edi, edi
0x18000baa1  jmp     loc_18000B998
0x18000baa6  mov     edi, 6
0x18000baab  jmp     loc_18000B998
0x18000bab0  mov     edi, 6
0x18000bab5  jmp     loc_18000B9AB
0x18000baba  xor     esi, esi
0x18000babc  jmp     short loc_18000BAC2
0x18000babe  lea     r13, [r14+10h]
0x18000bac2  cmp     qword ptr [r13+0], 0
0x18000bac7  jz      short loc_18000BB09
0x18000bac9  mov     ebx, esi
0x18000bacb  test    r12d, r12d
0x18000bace  jz      short loc_18000BB09
0x18000bad0  mov     rax, [r13+0]
0x18000bad4  mov     ecx, ebx
0x18000bad6  add     rcx, rcx
0x18000bad9  mov     rdi, [rax+rcx*8]
0x18000badd  test    rdi, rdi
0x18000bae0  jz      short loc_18000BB09
0x18000bae2  call    cs:__imp_GetProcessHeap
0x18000bae9  nop     dword ptr [rax+rax+00h]
0x18000baee  mov     r8, rdi; lpMem
0x18000baf1  xor     edx, edx; dwFlags
0x18000baf3  mov     rcx, rax; hHeap
0x18000baf6  call    cs:__imp_HeapFree
0x18000bafd  nop     dword ptr [rax+rax+00h]
0x18000bb02  inc     ebx
0x18000bb04  cmp     ebx, r12d
0x18000bb07  jb      short loc_18000BAD0
0x18000bb09  mov     rbx, [r13+0]
0x18000bb0d  test    rbx, rbx
0x18000bb10  jz      short loc_18000BB32
0x18000bb12  call    cs:__imp_GetProcessHeap
0x18000bb19  nop     dword ptr [rax+rax+00h]
0x18000bb1e  mov     r8, rbx; lpMem
0x18000bb21  xor     edx, edx; dwFlags
0x18000bb23  mov     rcx, rax; hHeap
0x18000bb26  call    cs:__imp_HeapFree
0x18000bb2d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
