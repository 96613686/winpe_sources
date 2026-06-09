# BtDbFileReadEx

- ea: `0x180008770`
- end: `0x180008dd9`
- name: `BtDbFileReadEx`
- size: `1641`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180054874`
- `0x180054960`
- `0x180089ee0`
- `0x18008a32c`
- `0x18008d184`

## callees

- `0x180002d84`
- `0x180008770`
- `0x180008de0`
- `0x180009344`
- `0x18000a138`
- `0x18000a4d8`
- `0x18002341c`
- `0x180031b10`
- `0x180031b64`
- `0x180078746`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b7010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180008cd3`
- `msvcrt!_wcsnicmp` at `0x180008cd3`
- `ntdll!NtQueryInformationThread` at `0x1800087f7`
- `ntdll!NtQueryInformationThread` at `0x1800087f7`
- `ntdll!RtlNtStatusToDosError` at `0x1800089f6`
- `ntdll!RtlNtStatusToDosError` at `0x1800089f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800087d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000880a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008894`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800087d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000880a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008894`

## pseudocode

```c
__int64 __fastcall BtDbFileReadEx(
        struct _BTDB_FILE_HEADER *a1,
        int a2,
        struct _BTDB_FILE_CALLBACKS *a3,
        __int64 a4,
        int a5)
{
  struct _BTDB_FILE_CALLBACKS *v5; // r13
  HANDLE CurrentThread; // rax
  int v10; // eax
  int v11; // r14d
  HANDLE v12; // rax
  int v13; // r8d
  unsigned int v14; // ebx
  HANDLE v15; // rax
  HANDLE v17; // rax
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v21; // rax
  __int64 v22; // r8
  unsigned __int8 *v23; // rdi
  unsigned int v24; // r12d
  __int64 i; // r9
  unsigned int j; // r12d
  __int64 v27; // rax
  unsigned __int64 v28; // rdi
  __int64 v29; // rax
  __int64 v30; // xmm1_8
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(struct _BTDB_FILE_HEADER *, __int64, unsigned __int64, _QWORD); // rax
  struct _BTDB_RANGE_CONTAINER *v34; // r13
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rcx
  __int128 v37; // xmm0
  __int64 v38; // rax
  __int64 v39; // r12
  unsigned int v40; // eax
  unsigned __int64 v41; // rcx
  const wchar_t *v42; // rbx
  __int16 v43; // di
  __int64 v44; // r12
  char *v45; // r13
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r8
  __int64 v53; // r8
  __int64 v54; // r8
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // rbx
  unsigned __int64 v59; // r12
  struct _BTDB_RANGE_CONTAINER *v60; // rdi
  __int64 (__fastcall *v61)(struct _BTDB_FILE_HEADER *, __int64, unsigned __int64, _QWORD); // rax
  int v62; // eax
  unsigned int v63; // edx
  unsigned __int8 *v64; // rcx
  int ThreadInformation; // [rsp+30h] [rbp-D0h] BYREF
  struct _BTDB_FILE_CALLBACKS *v66; // [rsp+38h] [rbp-C8h]
  int v67; // [rsp+40h] [rbp-C0h]
  char *v68; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v69[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v70; // [rsp+70h] [rbp-90h]
  unsigned __int64 v71; // [rsp+78h] [rbp-88h]
  __int128 v72; // [rsp+80h] [rbp-80h] BYREF
  __int128 v73; // [rsp+90h] [rbp-70h]
  __int64 v74; // [rsp+A0h] [rbp-60h]
  __int64 v75; // [rsp+A8h] [rbp-58h]
  __int128 v76; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v77; // [rsp+C0h] [rbp-40h]
  __int64 v78; // [rsp+C8h] [rbp-38h]
  _OWORD v79[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F4h] [rbp-Ch]
  __int128 v82; // [rsp+100h] [rbp+0h]
  __int64 v83; // [rsp+110h] [rbp+10h]

  v66 = a3;
  v74 = 0;
  v5 = a3;
  memset(v69, 0, sizeof(v69));
  v72 = 0;
  v73 = 0;
  memset_0(v79, 0, 0x48u);
  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v10 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v10 < 0 )
  {
    RtlNtStatusToDosError(v10);
    v11 = 8;
  }
  else
  {
    v11 = ThreadInformation;
  }
  v12 = GetCurrentThread();
  PfSetPagePriorityThread(v12);
  if ( *(_DWORD *)a1 != 3
    || 10000 * (unsigned int)PfDbFileVerifyCommon((_DWORD)a1, a2, v13, 1, (__int64)BtDbRangeListVerify) )
  {
    v14 = 11;
    goto LABEL_6;
  }
  if ( v11 != 8 )
  {
    v17 = GetCurrentThread();
    PfSetPagePriorityThread(v17);
    v11 = 8;
  }
  BtDbParametersSetDefault(v79);
  v18 = *((_OWORD *)a1 + 2);
  v19 = *((_OWORD *)a1 + 1);
  v80 = *((_DWORD *)a1 + 12);
  v79[1] = v18;
  v20 = *(_OWORD *)(a4 + 624);
  v21 = *(_QWORD *)(a4 + 604);
  v79[0] = v19;
  *(_QWORD *)&v19 = *(_QWORD *)(a4 + 640);
  v82 = v20;
  v81 = v21;
  v83 = v19;
  BtDbDatabaseInitialize((void *)a4);
  v23 = (unsigned __int8 *)a1 + *((unsigned int *)a1 + 2);
  v24 = 0;
  v67 = 0;
  i = 1;
LABEL_12:
  if ( v24 < *((_DWORD *)a1 + 13) )
  {
    v35 = (unsigned __int64)(v23 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    v36 = v35 + *(unsigned int *)(a4 + 568);
    v71 = v35;
    v37 = *(_OWORD *)(v35 + 32);
    v78 = *(_QWORD *)(v35 + 56);
    v77 = v36;
    WORD1(v78) &= ~1u;
    v76 = v37;
    v23 = (unsigned __int8 *)(v36 + 2LL * ((unsigned int)(unsigned __int16)v78 + 1));
    v38 = BtDbVolumeCreate(a4, &v76);
    v75 = v38;
    v39 = v38;
    if ( !v38 )
    {
LABEL_19:
      v14 = 8;
      goto LABEL_6;
    }
    memcpy_0((void *)(v38 + 96), (const void *)(v35 + 96), (unsigned int)(*(_DWORD *)(a4 + 568) - 96));
    if ( *(_QWORD *)v5 )
    {
      v14 = (*(__int64 (__fastcall **)(struct _BTDB_FILE_HEADER *, __int64, unsigned __int64, _QWORD))v5)(
              a1,
              v39,
              v35,
              *((_QWORD *)v5 + 3));
      if ( v14 )
        goto LABEL_6;
      v35 = v71;
    }
    v40 = 0;
    for ( i = 1; ; i = 1 )
    {
      ThreadInformation = v40;
      if ( v40 >= *(_DWORD *)(v35 + 16) )
      {
        v24 = ++v67;
        goto LABEL_12;
      }
      v41 = (unsigned __int64)(v23 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      v42 = (const wchar_t *)(v41 + *(unsigned int *)(a4 + 572));
      v70 = v41;
      memset(v69, 0, sizeof(v69));
      v43 = (((*(_QWORD *)(v41 + 16) >> 1) & 1) << 7) | 0x10;
      v44 = 8 * (*(_WORD *)(v41 + 16) & 1LL);
      v45 = (char *)&v42[(unsigned int)(*(_QWORD *)(v41 + 16) >> 2) + 1];
      v68 = v45;
      if ( a5 )
      {
        v62 = _wcsnicmp(v42, L"\\Windows\\SysWow64", 0x11u);
        v63 = 0;
        if ( !v62 )
        {
          v23 = (unsigned __int8 *)((unsigned __int64)(v45 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
          if ( *(_DWORD *)(v70 + 32) )
          {
            v64 = (unsigned __int8 *)((unsigned __int64)(v45 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
            do
            {
              v23 = &v64[*(unsigned int *)(a4 + 4 * (((unsigned __int64)*v64 >> 1) & 3) + 580)];
              v63 += v64[1] + 1;
              v64 = v23;
            }
            while ( v63 < *(_DWORD *)(v70 + 32) );
          }
          v5 = v66;
          goto LABEL_46;
        }
      }
      *(_DWORD *)((char *)&v72 + 10) = *(_DWORD *)((char *)v69 + 10);
      HIWORD(v72) = HIWORD(v69[0]);
      HIDWORD(v73) = HIDWORD(v69[1]);
      v46 = -1;
      *(_QWORD *)&v72 = v44;
      WORD4(v72) = v43;
      *(_QWORD *)&v73 = v42;
      do
        ++v46;
      while ( v42[v46] );
      v47 = 314159;
      DWORD2(v73) = v46;
      v48 = 2LL * (unsigned int)v46;
      if ( (unsigned __int64)v48 >= 8 )
      {
        do
        {
          v48 -= 8;
          v49 = *((unsigned __int8 *)v42 + 7);
          v50 = 37
              * (*((unsigned __int8 *)v42 + 6)
               + 37
               * (*((unsigned __int8 *)v42 + 5)
                + 37
                * (*((unsigned __int8 *)v42 + 4)
                 + 37
                 * (*((unsigned __int8 *)v42 + 3)
                  + 37
                  * (*((unsigned __int8 *)v42 + 2)
                   + 37 * (*((unsigned __int8 *)v42 + 1) + 37 * (*(unsigned __int8 *)v42 + 37 * v47)))))));
          v42 += 4;
          v47 = v49 + v50;
        }
        while ( v48 >= 8 );
      }
      v51 = v48 - 1;
      if ( v51 )
      {
        v52 = v51 - 1;
        if ( v52 )
        {
          v53 = v52 - 1;
          if ( v53 )
          {
            v54 = v53 - 1;
            if ( v54 )
            {
              v55 = v54 - 1;
              if ( v55 )
              {
                v56 = v55 - 1;
                if ( v56 )
                {
                  if ( v56 != 1 )
                    goto LABEL_42;
                  v47 = *(unsigned __int8 *)v42 + 37 * v47;
                  v42 = (const wchar_t *)((char *)v42 + 1);
                }
                v47 = *(unsigned __int8 *)v42 + 37 * v47;
                v42 = (const wchar_t *)((char *)v42 + 1);
              }
              v47 = *(unsigned __int8 *)v42 + 37 * v47;
              v42 = (const wchar_t *)((char *)v42 + 1);
            }
            v47 = *(unsigned __int8 *)v42 + 37 * v47;
            v42 = (const wchar_t *)((char *)v42 + 1);
          }
          v47 = *(unsigned __int8 *)v42 + 37 * v47;
          v42 = (const wchar_t *)((char *)v42 + 1);
        }
        v47 = *(unsigned __int8 *)v42 + 37 * v47;
        v42 = (const wchar_t *)((char *)v42 + 1);
      }
      v47 = *(unsigned __int8 *)v42 + 37 * v47;
LABEL_42:
      v74 = v47;
      v57 = BtDbSectionCreate(a4, v75, &v72, 1);
      v58 = v57;
      if ( !v57 )
        goto LABEL_19;
      v59 = v70;
      memcpy_0((void *)(v57 + 56), (const void *)(v70 + 56), (unsigned int)(*(_DWORD *)(a4 + 572) - 56));
      v5 = v66;
      v60 = (struct _BTDB_RANGE_CONTAINER *)(v58 + 32);
      v61 = (__int64 (__fastcall *)(struct _BTDB_FILE_HEADER *, __int64, unsigned __int64, _QWORD))*((_QWORD *)v66 + 1);
      if ( v61 )
      {
        v14 = v61(a1, v58 + 32, v59 + 32, *((_QWORD *)v66 + 3));
        if ( v14 )
          goto LABEL_6;
      }
      v14 = BtDbFileReadRanges(
              (struct _BTDB_DATABASE *)a4,
              a1,
              &v68,
              (struct _BTDB_RANGE_CONTAINER *)(v59 + 32),
              v60,
              v5);
      if ( v14 )
        goto LABEL_6;
      v23 = (unsigned __int8 *)v68;
LABEL_46:
      v35 = v71;
      v40 = ThreadInformation + 1;
    }
  }
  for ( j = 0; j < *((_DWORD *)a1 + 16); ++j )
  {
    v27 = *(unsigned int *)(a4 + 576);
    v28 = (unsigned __int64)(v23 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    *(_OWORD *)((char *)v69 + 8) = 0;
    v68 = (char *)(v28 + v27);
    v29 = *(_QWORD *)(v28 + 8);
    v30 = *(_QWORD *)(v28 + 32);
    v69[0] = *(_OWORD *)(v28 + 16);
    *((_QWORD *)&v69[1] + 1) = v29;
    *(_QWORD *)&v69[1] = v30;
    v31 = BtDbSourceCreate(a4, v69, v22, i);
    v32 = v31;
    if ( !v31 )
      goto LABEL_19;
    *(_OWORD *)(v31 + 40) = *(_OWORD *)(v28 + 40);
    memcpy_0((void *)(v31 + 80), (const void *)(v28 + 80), (unsigned int)(*(_DWORD *)(a4 + 576) - 80));
    v33 = (__int64 (__fastcall *)(struct _BTDB_FILE_HEADER *, __int64, unsigned __int64, _QWORD))*((_QWORD *)v5 + 1);
    v34 = (struct _BTDB_RANGE_CONTAINER *)(v32 + 56);
    if ( v33 )
    {
      v14 = v33(a1, v32 + 56, v28 + 56, *((_QWORD *)v66 + 3));
      if ( v14 )
        goto LABEL_6;
    }
    v14 = BtDbFileReadRanges(
            (struct _BTDB_DATABASE *)a4,
            a1,
            &v68,
            (struct _BTDB_RANGE_CONTAINER *)(v28 + 56),
            v34,
            v66);
    if ( v14 )
      goto LABEL_6;
    v23 = (unsigned __int8 *)v68;
    v5 = v66;
  }
  v14 = 0;
LABEL_6:
  if ( v11 != 8 )
  {
    v15 = GetCurrentThread();
    PfSetPagePriorityThread(v15);
  }
  return v14;
}

```

## disassembly

```asm
0x180008770  mov     [rsp-8+arg_8], rbx
0x180008775  push    rbp
0x180008776  push    rsi
0x180008777  push    rdi
0x180008778  push    r12
0x18000877a  push    r13
0x18000877c  push    r14
0x18000877e  push    r15
0x180008780  lea     rbp, [rsp-30h]
0x180008785  sub     rsp, 130h
0x18000878c  mov     rax, cs:__security_cookie
0x180008793  xor     rax, rsp
0x180008796  mov     [rbp+60h+var_40], rax
0x18000879a  xor     eax, eax
0x18000879c  mov     [rsp+160h+var_128], r8
0x1800087a1  xorps   xmm0, xmm0
0x1800087a4  mov     [rbp+60h+var_C0], rax
0x1800087a8  xorps   xmm1, xmm1
0x1800087ab  mov     r13, r8
0x1800087ae  mov     ebx, edx
0x1800087b0  mov     rsi, rcx
0x1800087b3  lea     r8d, [rax+48h]; Size
0x1800087b7  xor     edx, edx; Val
0x1800087b9  lea     rcx, [rbp+60h+var_90]; void *
0x1800087bd  mov     r15, r9
0x1800087c0  movups  [rsp+160h+var_110], xmm0
0x1800087c5  movups  [rsp+160h+var_100], xmm0
0x1800087ca  movups  [rbp+60h+var_E0], xmm1
0x1800087ce  movups  [rbp+60h+var_D0], xmm1
0x1800087d2  call    memset_0
0x1800087d7  call    cs:__imp_GetCurrentThread
0x1800087dd  xor     edi, edi
0x1800087df  lea     r8, [rsp+160h+ThreadInformation]; ThreadInformation
0x1800087e4  mov     rcx, rax; ThreadHandle
0x1800087e7  mov     [rsp+160h+ThreadInformation], edi
0x1800087eb  mov     [rsp+160h+ReturnLength], rdi; ReturnLength
0x1800087f0  lea     r9d, [rdi+4]; ThreadInformationLength
0x1800087f4  lea     edx, [rdi+18h]; ThreadInformationClass
0x1800087f7  call    cs:__imp_NtQueryInformationThread
0x1800087fd  test    eax, eax
0x1800087ff  js      loc_1800089F4
0x180008805  mov     r14d, [rsp+160h+ThreadInformation]
0x18000880a  call    cs:__imp_GetCurrentThread
0x180008810  mov     r12d, 1
0x180008816  mov     rcx, rax; ThreadHandle
0x180008819  mov     edx, r12d
0x18000881c  call    PfSetPagePriorityThread
0x180008821  cmp     dword ptr [rsi], 3
0x180008824  jnz     short loc_180008849
0x180008826  lea     rax, ?BtDbRangeListVerify@@YAKPEAU_PFDB_FILE_HEADER@@PEAXPEA_K1PEAK@Z; BtDbRangeListVerify(_PFDB_FILE_HEADER *,void *,unsigned __int64 *,void *,ulong *)
0x18000882d  mov     r9d, r12d
0x180008830  mov     edx, ebx
0x180008832  mov     [rsp+160h+ReturnLength], rax
0x180008837  mov     rcx, rsi
0x18000883a  call    PfDbFileVerifyCommon
0x18000883f  imul    ecx, eax, 2710h
0x180008845  test    ecx, ecx
0x180008847  jz      short loc_18000888E
0x180008849  mov     ebx, 0Bh
0x18000884e  cmp     r14d, 8
0x180008852  jz      short loc_180008865
0x180008854  call    cs:__imp_GetCurrentThread
0x18000885a  mov     rcx, rax; ThreadHandle
0x18000885d  mov     edx, r14d
0x180008860  call    PfSetPagePriorityThread
0x180008865  mov     eax, ebx
0x180008867  mov     rcx, [rbp+60h+var_40]
0x18000886b  xor     rcx, rsp; StackCookie
0x18000886e  call    __security_check_cookie
0x180008873  mov     rbx, [rsp+160h+arg_8]
0x18000887b  add     rsp, 130h
0x180008882  pop     r15
0x180008884  pop     r14
0x180008886  pop     r13
0x180008888  pop     r12
0x18000888a  pop     rdi
0x18000888b  pop     rsi
0x18000888c  pop     rbp
0x18000888d  retn
0x18000888e  cmp     r14d, 8
0x180008892  jz      short loc_1800088AB
0x180008894  call    cs:__imp_GetCurrentThread
0x18000889a  mov     rcx, rax; ThreadHandle
0x18000889d  mov     edx, r14d
0x1800088a0  call    PfSetPagePriorityThread
0x1800088a5  mov     r14d, 8
0x1800088ab  lea     rcx, [rbp+60h+var_90]
0x1800088af  call    BtDbParametersSetDefault
0x1800088b4  movups  xmm0, xmmword ptr [rsi+20h]
0x1800088b8  mov     eax, [rsi+30h]
0x1800088bb  lea     rdx, [rbp+60h+var_90]
0x1800088bf  movups  xmm1, xmmword ptr [rsi+10h]
0x1800088c3  mov     rcx, r15; void *
0x1800088c6  mov     [rbp+60h+var_70], eax
0x1800088c9  movaps  [rbp+60h+var_80], xmm0
0x1800088cd  movups  xmm0, xmmword ptr [r15+270h]
0x1800088d5  mov     rax, [r15+25Ch]
0x1800088dc  movaps  [rbp+60h+var_90], xmm1
0x1800088e0  movsd   xmm1, qword ptr [r15+280h]
0x1800088e9  movaps  [rbp+60h+var_60], xmm0
0x1800088ed  mov     [rbp+60h+var_6C], rax
0x1800088f1  movsd   [rbp+60h+var_50], xmm1
0x1800088f6  call    BtDbDatabaseInitialize
0x1800088fb  mov     edi, [rsi+8]
0x1800088fe  add     rdi, rsi
0x180008901  xor     edx, edx
0x180008903  mov     r12d, edx
0x180008906  mov     [rsp+160h+var_120], edx
0x18000890a  lea     r9d, [rdx+1]
0x18000890e  cmp     r12d, [rsi+34h]
0x180008912  jb      loc_180008A07
0x180008918  mov     r12d, edx
0x18000891b  cmp     r12d, [rsi+40h]
0x18000891f  jnb     loc_180008DD2
0x180008925  mov     eax, [r15+240h]
0x18000892c  lea     rdx, [rsp+160h+var_110]
0x180008931  xorps   xmm0, xmm0
0x180008934  add     rdi, 7
0x180008938  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18000893c  mov     rcx, r15
0x18000893f  movdqu  [rsp+160h+var_110+8], xmm0
0x180008945  add     rax, rdi
0x180008948  mov     [rsp+160h+var_118], rax
0x18000894d  movups  xmm0, xmmword ptr [rdi+10h]
0x180008951  mov     rax, [rdi+8]
0x180008955  movsd   xmm1, qword ptr [rdi+20h]
0x18000895a  movups  [rsp+160h+var_110], xmm0
0x18000895f  mov     qword ptr [rsp+160h+var_100+8], rax
0x180008964  movsd   qword ptr [rsp+160h+var_100], xmm1
0x18000896a  call    BtDbSourceCreate
0x18000896f  mov     rbx, rax
0x180008972  test    rax, rax
0x180008975  jz      short loc_1800089EA
0x180008977  movups  xmm0, xmmword ptr [rdi+28h]
0x18000897b  lea     rdx, [rdi+50h]; Src
0x18000897f  lea     rcx, [rax+50h]; void *
0x180008983  movdqu  xmmword ptr [rax+28h], xmm0
0x180008988  mov     r8d, [r15+240h]
0x18000898f  sub     r8d, 50h ; 'P'; Size
0x180008993  call    memcpy_0
0x180008998  mov     rax, [r13+8]
0x18000899c  lea     r13, [rbx+38h]
0x1800089a0  test    rax, rax
0x1800089a3  jnz     loc_180008DAB
0x1800089a9  mov     rax, [rsp+160h+var_128]
0x1800089ae  lea     r9, [rdi+38h]; struct _BTDB_RANGE_CONTAINER *
0x1800089b2  mov     [rsp+160h+var_138], rax; struct _BTDB_FILE_CALLBACKS *
0x1800089b7  lea     r8, [rsp+160h+var_118]; char **
0x1800089bc  mov     rdx, rsi; struct _BTDB_FILE_HEADER *
0x1800089bf  mov     [rsp+160h+ReturnLength], r13; struct _BTDB_RANGE_CONTAINER *
0x1800089c4  mov     rcx, r15; struct _BTDB_DATABASE *
0x1800089c7  call    ?BtDbFileReadRanges@@YAKPEAU_BTDB_DATABASE@@PEAU_BTDB_FILE_HEADER@@PEAPEADPEAU_BTDB_RANGE_CONTAINER@@3PEAU_BTDB_FILE_CALLBACKS@@@Z; BtDbFileReadRanges(_BTDB_DATABASE *,_BTDB_FILE_HEADER *,char * *,_BTDB_RANGE_CONTAINER *,_BTDB_RANGE_CONTAINER *,_BTDB_FILE_CALLBACKS *)
0x1800089cc  xor     edx, edx
0x1800089ce  mov     ebx, eax
0x1800089d0  test    eax, eax
0x1800089d2  jnz     loc_18000884E
0x1800089d8  mov     rdi, [rsp+160h+var_118]
0x1800089dd  inc     r12d
0x1800089e0  mov     r13, [rsp+160h+var_128]
0x1800089e5  jmp     loc_18000891B
0x1800089ea  mov     ebx, 8
0x1800089ef  jmp     loc_18000884E
0x1800089f4  mov     ecx, eax; Status
0x1800089f6  call    cs:__imp_RtlNtStatusToDosError
0x1800089fc  mov     r14d, 8
0x180008a02  jmp     loc_18000880A
0x180008a07  mov     ecx, [r15+238h]
0x180008a0e  lea     rbx, [rdi+7]
0x180008a12  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180008a16  mov     edx, 0FFFEh
0x180008a1b  add     rcx, rbx
0x180008a1e  mov     [rsp+160h+var_E8], rbx
0x180008a23  movups  xmm1, xmmword ptr [rbx+30h]
0x180008a27  movups  xmm0, xmmword ptr [rbx+20h]
0x180008a2b  movups  [rbp+60h+var_A0], xmm1
0x180008a2f  mov     rax, qword ptr [rbp+60h+var_A0+8]
0x180008a33  shr     rax, 10h
0x180008a37  and     ax, dx
0x180008a3a  mov     qword ptr [rbp+60h+var_A0], rcx
0x180008a3e  mov     word ptr [rbp+60h+var_A0+0Ah], ax
0x180008a42  lea     rdx, [rbp+60h+var_B0]
0x180008a46  movzx   eax, word ptr [rbp+60h+var_A0+8]
0x180008a4a  add     eax, r9d
0x180008a4d  movups  [rbp+60h+var_B0], xmm0
0x180008a51  lea     rdi, [rcx+rax*2]
0x180008a55  mov     rcx, r15
0x180008a58  call    BtDbVolumeCreate
0x180008a5d  mov     [rbp+60h+var_B8], rax
0x180008a61  mov     r12, rax
0x180008a64  test    rax, rax
0x180008a67  jz      short loc_1800089EA
0x180008a69  mov     r8d, [r15+238h]
0x180008a70  lea     rdx, [rbx+60h]; Src
0x180008a74  sub     r8d, 60h ; '`'; Size
0x180008a78  lea     rcx, [rax+60h]; void *
0x180008a7c  call    memcpy_0
0x180008a81  mov     rax, [r13+0]
0x180008a85  xor     edx, edx
0x180008a87  test    rax, rax
0x180008a8a  jnz     loc_180008CFA
0x180008a90  mov     eax, edx
0x180008a92  mov     r9d, 1
0x180008a98  mov     [rsp+160h+ThreadInformation], eax
0x180008a9c  cmp     eax, [rbx+10h]
0x180008a9f  jnb     loc_180008D99
0x180008aa5  mov     ebx, [r15+23Ch]
0x180008aac  lea     rcx, [rdi+7]
0x180008ab0  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180008ab4  xorps   xmm0, xmm0
0x180008ab7  add     rbx, rcx
0x180008aba  mov     [rsp+160h+var_F0], rcx
0x180008abf  movups  [rsp+160h+var_110], xmm0
0x180008ac4  mov     rax, [rcx+10h]
0x180008ac8  movzx   r12d, word ptr [rcx+10h]
0x180008acd  mov     rdi, rax
0x180008ad0  shr     rdi, 1
0x180008ad3  and     r12, r9
0x180008ad6  and     di, r9w
0x180008ada  shr     rax, 2
0x180008ade  shl     di, 7
0x180008ae2  or      di, 10h
0x180008ae6  shl     r12, 3
0x180008aea  movups  [rsp+160h+var_100], xmm0
0x180008aef  lea     r13d, ds:2[rax*2]
0x180008af7  add     r13, rbx
0x180008afa  mov     [rsp+160h+var_118], r13
0x180008aff  cmp     [rbp+60h+arg_20], edx
0x180008b05  jnz     loc_180008CC3
0x180008b0b  mov     eax, dword ptr [rsp+160h+var_110+0Ah]
0x180008b0f  mov     dword ptr [rbp+60h+var_E0+0Ah], eax
0x180008b12  movzx   eax, word ptr [rsp+160h+var_110+0Eh]
0x180008b17  mov     word ptr [rbp+60h+var_E0+0Eh], ax
0x180008b1b  mov     eax, dword ptr [rsp+160h+var_100+0Ch]
0x180008b1f  mov     dword ptr [rbp+60h+var_D0+0Ch], eax
0x180008b22  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008b26  mov     qword ptr [rbp+60h+var_E0], r12
0x180008b2a  mov     word ptr [rbp+60h+var_E0+8], di
0x180008b2e  mov     qword ptr [rbp+60h+var_D0], rbx
0x180008b32  inc     rax
0x180008b35  cmp     [rbx+rax*2], dx
0x180008b39  jnz     short loc_180008B32
0x180008b3b  mov     r8d, eax
0x180008b3e  mov     ecx, 4CB2Fh
0x180008b43  mov     dword ptr [rbp+60h+var_D0+8], r8d
0x180008b47  add     r8, r8
0x180008b4a  cmp     r8, 8
0x180008b4e  jb      short loc_180008BB5
0x180008b50  movzx   eax, byte ptr [rbx]
0x180008b53  sub     r8, 8
0x180008b57  imul    rcx, 25h ; '%'
0x180008b5b  add     rcx, rax
0x180008b5e  movzx   eax, byte ptr [rbx+1]
0x180008b62  imul    rdx, rcx, 25h ; '%'
0x180008b66  add     rdx, rax
0x180008b69  movzx   eax, byte ptr [rbx+2]
0x180008b6d  imul    rcx, rdx, 25h ; '%'
0x180008b71  add     rcx, rax
0x180008b74  movzx   eax, byte ptr [rbx+3]
0x180008b78  imul    rdx, rcx, 25h ; '%'
0x180008b7c  add     rdx, rax
0x180008b7f  movzx   eax, byte ptr [rbx+4]
0x180008b83  imul    rcx, rdx, 25h ; '%'
0x180008b87  add     rcx, rax
0x180008b8a  movzx   eax, byte ptr [rbx+5]
0x180008b8e  imul    rdx, rcx, 25h ; '%'
0x180008b92  add     rdx, rax
0x180008b95  movzx   eax, byte ptr [rbx+6]
0x180008b99  imul    rcx, rdx, 25h ; '%'
0x180008b9d  add     rcx, rax
0x180008ba0  movzx   eax, byte ptr [rbx+7]
0x180008ba4  imul    rcx, 25h ; '%'
0x180008ba8  add     rbx, 8
0x180008bac  add     rcx, rax
0x180008baf  cmp     r8, 8
0x180008bb3  jge     short loc_180008B50
0x180008bb5  sub     r8, 1
0x180008bb9  jz      short loc_180008C1E
0x180008bbb  sub     r8, 1
0x180008bbf  jz      short loc_180008C11
0x180008bc1  sub     r8, 1
0x180008bc5  jz      short loc_180008C04
0x180008bc7  sub     r8, 1
0x180008bcb  jz      short loc_180008BF7
0x180008bcd  sub     r8, 1
0x180008bd1  jz      short loc_180008BEA
0x180008bd3  sub     r8, 1
0x180008bd7  jnz     loc_180008D5A
0x180008bdd  movzx   eax, byte ptr [rbx]
0x180008be0  imul    rcx, 25h ; '%'
0x180008be4  add     rcx, rax
0x180008be7  add     rbx, r9
0x180008bea  movzx   eax, byte ptr [rbx]
0x180008bed  imul    rcx, 25h ; '%'
0x180008bf1  add     rcx, rax
0x180008bf4  add     rbx, r9
0x180008bf7  movzx   eax, byte ptr [rbx]
0x180008bfa  imul    rcx, 25h ; '%'
0x180008bfe  add     rcx, rax
0x180008c01  add     rbx, r9
0x180008c04  movzx   eax, byte ptr [rbx]
  ... truncated ...
```
