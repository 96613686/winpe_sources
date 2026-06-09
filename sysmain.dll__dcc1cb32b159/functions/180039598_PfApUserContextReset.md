# PfApUserContextReset

- ea: `0x180039598`
- end: `0x180039a3b`
- name: `PfApUserContextReset`
- size: `1187`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039a44`
- `0x18006a020`

## callees

- `0x180039598`
- `0x18003cbe4`
- `0x18003eaa0`
- `0x18003eb44`
- `0x180057710`
- `0x180057aa4`
- `0x18005b9a8`
- `0x18005c994`
- `0x180065cbc`
- `0x180068f3c`
- `0x180069540`
- `0x18006d124`
- `0x1800736c8`
- `0x180073e28`
- `0x180074148`
- `0x1800b645a`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039704`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039704`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003996c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003998c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039a26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003996c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003998c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039a26`

## pseudocode

```c
__int64 __fastcall PfApUserContextReset(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  void **v4; // rbx
  __int64 v6; // rsi
  __int64 v10; // rbx
  void *v11; // rcx
  __int64 v12; // rsi
  void *v13; // rbx
  DWORD LengthSid; // eax
  unsigned int SidHash; // eax
  unsigned __int64 *v16; // r13
  unsigned __int64 v17; // rbx
  _DWORD *v18; // rsi
  void *v19; // r8
  __int64 result; // rax
  unsigned __int64 v21; // rsi
  unsigned __int64 *v22; // rdx
  unsigned __int64 v23; // rax
  unsigned __int64 *i; // rcx
  unsigned __int64 v25; // r15
  unsigned __int64 *v26; // r12
  unsigned __int64 v27; // rsi
  _DWORD *v28; // r14
  void *v29; // rsi
  void *v30; // r8
  unsigned __int64 *v31; // rdx
  void *v32; // r14
  unsigned __int64 *j; // rcx
  unsigned __int64 v34; // [rsp+60h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+48h]

  v4 = (void **)(a1 + 168);
  v6 = a1 + 16;
  if ( *(_QWORD *)(a1 + 168) )
  {
    PfApUserActivitySync(a1, 0);
    v10 = PfApUserTimeGet(a1 + 184);
    PfPreAddEvent(v6, 0, 9, v10);
    if ( (a4 & 2) != 0 )
      PfPreAddEvent(v6, 0, 11, v10);
    v34 = 0x7FFFFFFFFFFFFFFFLL;
    PfsActionItemQueueEx((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1720LL), 0x2Du, &v34, 0);
    v4 = (void **)(a1 + 168);
  }
  if ( (*(_BYTE *)(a1 + 216) & 4) != 0 )
  {
    PfSvPowerNotifyUnregister(a1, 3 - (unsigned int)(*(_DWORD *)(a1 + 176) != 0));
    *(_WORD *)(a1 + 216) &= ~4u;
  }
  PfPreContextCleanup(v6);
  memset_0((void *)v6, 0, 0x70u);
  *(_DWORD *)(v6 + 36) = 0;
  *(_OWORD *)(v6 + 48) = 0;
  *(_DWORD *)(v6 + 52) = 0;
  *(_OWORD *)(v6 + 64) = 0;
  *(_OWORD *)(v6 + 80) = 0;
  *(_OWORD *)(v6 + 96) = 0;
  *(_DWORD *)(v6 + 68) = 0;
  if ( a2 )
  {
    PfApFetchContextCleanup(a2);
    *(_OWORD *)(a2 + 88) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 72) = 0;
    *(_DWORD *)(a2 + 80) = -1;
    *(_OWORD *)(a2 + 40) = 0;
    *(_OWORD *)(a2 + 56) = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 32) = 0;
  }
  if ( a3 )
  {
    PfApLaunchContextCleanup(a3);
    PfApLaunchContextInitialize(a3);
  }
  v11 = *v4;
  if ( *v4 )
  {
    v12 = a1 + 184;
    v13 = *v4;
    LengthSid = GetLengthSid(v11);
    SidHash = PfsGetSidHash(v13, LengthSid);
    PfApUserTimeCtxCleanup(a1 + 184, SidHash);
  }
  else
  {
    v34 = 0x7FFFFFFFFFFFFFFFLL;
    PfsActionItemQueueEx((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1720LL), 0x30u, &v34, 0);
    v12 = a1 + 184;
  }
  PfApUserTimeCtxInitialize(v12);
  v16 = *(unsigned __int64 **)(a1 + 8);
  v17 = (unsigned __int64)v16;
  while ( 1 )
  {
    v34 = v17;
    if ( !v17 )
      break;
    if ( (*(_QWORD *)v17 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
    {
      PfsHashTableCorruptionCallback(a1, 30, &v34);
      v17 = v34;
    }
    if ( !v17 )
      break;
    v17 = *(_QWORD *)v17;
    if ( (v17 & 1) != 0 )
      break;
    v18 = (_DWORD *)(a1 + 4);
LABEL_29:
    if ( !v17 )
      goto LABEL_25;
    v34 = v17;
    v21 = v17;
    v22 = (unsigned __int64 *)v17;
    v23 = *(_QWORD *)v17 & 0x8000000000000002uLL;
    lpMem = (LPVOID)v17;
    if ( v23 == 0x8000000000000002uLL )
    {
      PfsHashTableCorruptionCallback(a1, 40, &v34);
      v22 = (unsigned __int64 *)v34;
    }
    for ( i = v16; (*i & 1) == 0; i = (unsigned __int64 *)*i )
    {
      if ( (unsigned __int64 *)*i == v22 )
      {
        v17 = (unsigned __int64)i;
        *i = *v22;
        --*(_DWORD *)a1;
        *(_QWORD *)v34 |= 0x8000000000000002uLL;
        goto LABEL_38;
      }
    }
    PfsHashTableCorruptionCallback(a1, 50, &v34);
LABEL_38:
    v25 = v21 + 424;
    v26 = *(unsigned __int64 **)(v21 + 432);
    v27 = (unsigned __int64)v26;
    while ( 1 )
    {
      v34 = v27;
      if ( !v27 )
        break;
      if ( (*(_QWORD *)v27 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
      {
        PfsHashTableCorruptionCallback(v25, 30, &v34);
        v27 = v34;
      }
      if ( !v27 )
        break;
      v27 = *(_QWORD *)v27;
      if ( (v27 & 1) != 0 )
        break;
      v28 = (_DWORD *)(v25 + 4);
LABEL_53:
      if ( !v27 )
        goto LABEL_49;
      v31 = (unsigned __int64 *)v27;
      v32 = (void *)v27;
      v34 = v27;
      if ( (*(_QWORD *)v27 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
      {
        PfsHashTableCorruptionCallback(v25, 40, &v34);
        v31 = (unsigned __int64 *)v34;
      }
      for ( j = v26; (*j & 1) == 0; j = (unsigned __int64 *)*j )
      {
        if ( (unsigned __int64 *)*j == v31 )
        {
          v27 = (unsigned __int64)j;
          *j = *v31;
          --*(_DWORD *)v25;
          *(_QWORD *)v34 |= 0x8000000000000002uLL;
          goto LABEL_62;
        }
      }
      PfsHashTableCorruptionCallback(v25, 50, &v34);
LABEL_62:
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v32);
    }
    v28 = (_DWORD *)(v25 + 4);
    for ( ++v26;
          (unsigned __int64)v26 < *(_QWORD *)(v25 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(v25 + 4) >> 5);
          ++v26 )
    {
      v27 = *v26;
      if ( (*v26 & 1) == 0 )
      {
        v34 = *v26;
        goto LABEL_53;
      }
    }
LABEL_49:
    v29 = lpMem;
    v30 = (void *)*((_QWORD *)lpMem + 54);
    if ( v30 )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v30);
    *(_DWORD *)v25 = 0;
    *(_QWORD *)(v25 + 8) = 0;
    *v28 = 0;
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v29);
  }
  v18 = (_DWORD *)(a1 + 4);
  for ( ++v16; (unsigned __int64)v16 < *(_QWORD *)(a1 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 4) >> 5); ++v16 )
  {
    v17 = *v16;
    if ( (*v16 & 1) == 0 )
    {
      v34 = *v16;
      goto LABEL_29;
    }
  }
LABEL_25:
  v19 = *(void **)(a1 + 8);
  if ( v19 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v19);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *v18 = 0;
  *(_WORD *)(a1 + 216) &= ~2u;
  *(_WORD *)(a1 + 218) = 0;
  result = PfsFileExtentDataCleanup(a1 + 168);
  *(_OWORD *)(a1 + 168) = 0;
  *(_DWORD *)(a1 + 176) = -1;
  return result;
}

```

## disassembly

```asm
0x180039598  mov     [rsp-38h+arg_10], rbx
0x18003959d  push    rbp
0x18003959e  push    rsi
0x18003959f  push    rdi
0x1800395a0  push    r12
0x1800395a2  push    r13
0x1800395a4  push    r14
0x1800395a6  push    r15
0x1800395a8  mov     rbp, rsp
0x1800395ab  sub     rsp, 20h
0x1800395af  lea     rbx, [rcx+0A8h]
0x1800395b6  mov     r12d, r9d
0x1800395b9  cmp     qword ptr [rbx], 0
0x1800395bd  lea     rsi, [rcx+10h]
0x1800395c1  mov     r15, r8
0x1800395c4  mov     r14, rdx
0x1800395c7  mov     rdi, rcx
0x1800395ca  mov     r13, 7FFFFFFFFFFFFFFFh
0x1800395d4  jz      short loc_18003963D
0x1800395d6  xor     edx, edx
0x1800395d8  call    PfApUserActivitySync
0x1800395dd  lea     rcx, [rdi+0B8h]
0x1800395e4  call    PfApUserTimeGet
0x1800395e9  xor     edx, edx
0x1800395eb  mov     r9, rax
0x1800395ee  mov     rcx, rsi
0x1800395f1  mov     rbx, rax
0x1800395f4  lea     r8d, [rdx+9]
0x1800395f8  call    PfPreAddEvent
0x1800395fd  test    r12b, 2
0x180039601  jz      short loc_180039614
0x180039603  xor     edx, edx
0x180039605  mov     r9, rbx
0x180039608  mov     rcx, rsi
0x18003960b  lea     r8d, [rdx+0Bh]
0x18003960f  call    PfPreAddEvent
0x180039614  mov     rcx, cs:PfSvcGlobals
0x18003961b  lea     r8, [rbp+arg_0]
0x18003961f  xor     r9d, r9d
0x180039622  mov     [rbp+arg_0], r13
0x180039626  add     rcx, 6B8h; lpCriticalSection
0x18003962d  lea     edx, [r9+2Dh]
0x180039631  call    PfsActionItemQueueEx
0x180039636  lea     rbx, [rdi+0A8h]
0x18003963d  test    byte ptr [rdi+0D8h], 4
0x180039644  jz      short loc_180039664
0x180039646  mov     eax, [rdi+0B0h]
0x18003964c  neg     eax
0x18003964e  sbb     edx, edx
0x180039650  add     edx, 3
0x180039653  call    PfSvPowerNotifyUnregister
0x180039658  mov     eax, 0FFFBh
0x18003965d  and     [rdi+0D8h], ax
0x180039664  mov     rcx, rsi
0x180039667  call    PfPreContextCleanup
0x18003966c  xor     edx, edx; Val
0x18003966e  mov     rcx, rsi; void *
0x180039671  lea     r8d, [rdx+70h]; Size
0x180039675  call    memset_0
0x18003967a  xor     r12d, r12d
0x18003967d  xorps   xmm0, xmm0
0x180039680  mov     [rsi+24h], r12d
0x180039684  movups  xmmword ptr [rsi+30h], xmm0
0x180039688  mov     [rsi+34h], r12d
0x18003968c  movups  xmmword ptr [rsi+40h], xmm0
0x180039690  movups  xmmword ptr [rsi+50h], xmm0
0x180039694  movups  xmmword ptr [rsi+60h], xmm0
0x180039698  mov     [rsi+44h], r12d
0x18003969c  test    r14, r14
0x18003969f  jz      short loc_1800396DD
0x1800396a1  mov     rcx, r14
0x1800396a4  call    PfApFetchContextCleanup
0x1800396a9  xorps   xmm0, xmm0
0x1800396ac  xorps   xmm1, xmm1
0x1800396af  movups  xmmword ptr [r14+58h], xmm0
0x1800396b4  mov     [r14], r12
0x1800396b7  xor     eax, eax
0x1800396b9  mov     [r14+8], r12
0x1800396bd  movups  xmmword ptr [r14+48h], xmm0
0x1800396c2  mov     dword ptr [r14+50h], 0FFFFFFFFh
0x1800396ca  movups  xmmword ptr [r14+28h], xmm0
0x1800396cf  movups  xmmword ptr [r14+38h], xmm0
0x1800396d4  movups  xmmword ptr [r14+10h], xmm1
0x1800396d9  mov     [r14+20h], rax
0x1800396dd  test    r15, r15
0x1800396e0  jz      short loc_1800396F2
0x1800396e2  mov     rcx, r15
0x1800396e5  call    PfApLaunchContextCleanup
0x1800396ea  mov     rcx, r15
0x1800396ed  call    PfApLaunchContextInitialize
0x1800396f2  mov     rcx, [rbx]; pSid
0x1800396f5  test    rcx, rcx
0x1800396f8  jz      short loc_180039720
0x1800396fa  lea     rsi, [rdi+0B8h]
0x180039701  mov     rbx, rcx
0x180039704  call    cs:__imp_GetLengthSid
0x18003970a  mov     edx, eax
0x18003970c  mov     rcx, rbx
0x18003970f  call    PfsGetSidHash
0x180039714  mov     edx, eax
0x180039716  mov     rcx, rsi
0x180039719  call    PfApUserTimeCtxCleanup
0x18003971e  jmp     short loc_180039749
0x180039720  mov     rcx, cs:PfSvcGlobals
0x180039727  lea     r8, [rbp+arg_0]
0x18003972b  xor     r9d, r9d
0x18003972e  mov     [rbp+arg_0], r13
0x180039732  add     rcx, 6B8h; lpCriticalSection
0x180039739  lea     edx, [r9+30h]
0x18003973d  call    PfsActionItemQueueEx
0x180039742  lea     rsi, [rdi+0B8h]
0x180039749  mov     rcx, rsi
0x18003974c  call    PfApUserTimeCtxInitialize
0x180039751  mov     r13, [rdi+8]
0x180039755  mov     rbx, r13
0x180039758  mov     [rbp+arg_0], rbx
0x18003975c  mov     r8, 8000000000000002h
0x180039766  test    rbx, rbx
0x180039769  jz      short loc_1800397AB
0x18003976b  mov     rax, [rbx]
0x18003976e  and     rax, r8
0x180039771  cmp     rax, r8
0x180039774  jnz     short loc_180039795
0x180039776  lea     r8, [rbp+arg_0]
0x18003977a  mov     edx, 1Eh
0x18003977f  mov     rcx, rdi
0x180039782  call    PfsHashTableCorruptionCallback
0x180039787  mov     rbx, [rbp+arg_0]
0x18003978b  mov     r8, 8000000000000002h
0x180039795  test    rbx, rbx
0x180039798  jz      short loc_1800397AB
0x18003979a  mov     rbx, [rbx]
0x18003979d  test    bl, 1
0x1800397a0  jnz     short loc_1800397AB
0x1800397a2  lea     rsi, [rdi+4]
0x1800397a6  jmp     loc_180039844
0x1800397ab  mov     rax, [rdi+8]
0x1800397af  lea     rsi, [rdi+4]
0x1800397b3  mov     ecx, [rsi]
0x1800397b5  add     r13, 8
0x1800397b9  shr     rcx, 5
0x1800397bd  lea     rdx, [rax+rcx*8]
0x1800397c1  jmp     short loc_1800397D0
0x1800397c3  mov     rbx, [r13+0]
0x1800397c7  test    bl, 1
0x1800397ca  jz      short loc_180039840
0x1800397cc  add     r13, 8
0x1800397d0  cmp     r13, rdx
0x1800397d3  jb      short loc_1800397C3
0x1800397d5  mov     r8, [rdi+8]; lpMem
0x1800397d9  test    r8, r8
0x1800397dc  jz      short loc_1800397F1
0x1800397de  mov     rcx, cs:PfSvcGlobals
0x1800397e5  xor     edx, edx; dwFlags
0x1800397e7  mov     rcx, [rcx+58h]; hHeap
0x1800397eb  call    cs:__imp_HeapFree
0x1800397f1  mov     [rdi], r12d
0x1800397f4  lea     rbx, [rdi+0A8h]
0x1800397fb  mov     [rdi+8], r12
0x1800397ff  mov     eax, 0FFFDh
0x180039804  mov     [rsi], r12d
0x180039807  mov     rcx, rbx
0x18003980a  and     [rdi+0D8h], ax
0x180039811  mov     [rdi+0DAh], r12w
0x180039819  call    PfsFileExtentDataCleanup
0x18003981e  xorps   xmm0, xmm0
0x180039821  movups  xmmword ptr [rbx], xmm0
0x180039824  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18003982b  mov     rbx, [rsp+20h+arg_10]
0x180039830  add     rsp, 20h
0x180039834  pop     r15
0x180039836  pop     r14
0x180039838  pop     r13
0x18003983a  pop     r12
0x18003983c  pop     rdi
0x18003983d  pop     rsi
0x18003983e  pop     rbp
0x18003983f  retn
0x180039840  mov     [rbp+arg_0], rbx
0x180039844  mov     rax, rbx
0x180039847  test    rax, rax
0x18003984a  jz      short loc_1800397D5
0x18003984c  mov     [rbp+arg_0], rbx
0x180039850  mov     rsi, rbx
0x180039853  mov     rax, [rbx]
0x180039856  mov     rdx, rbx
0x180039859  and     rax, r8
0x18003985c  mov     [rbp+lpMem], rbx
0x180039860  cmp     rax, r8
0x180039863  jnz     short loc_180039884
0x180039865  lea     r8, [rbp+arg_0]
0x180039869  mov     edx, 28h ; '('
0x18003986e  mov     rcx, rdi
0x180039871  call    PfsHashTableCorruptionCallback
0x180039876  mov     rdx, [rbp+arg_0]
0x18003987a  mov     r8, 8000000000000002h
0x180039884  mov     rcx, r13
0x180039887  mov     rax, [rcx]
0x18003988a  test    al, 1
0x18003988c  jnz     short loc_1800398B0
0x18003988e  cmp     rax, rdx
0x180039891  jz      short loc_180039898
0x180039893  mov     rcx, rax
0x180039896  jmp     short loc_180039887
0x180039898  mov     rax, [rdx]
0x18003989b  mov     rbx, rcx
0x18003989e  mov     [rcx], rax
0x1800398a1  mov     eax, [rdi]
0x1800398a3  dec     eax
0x1800398a5  mov     [rdi], eax
0x1800398a7  mov     rax, [rbp+arg_0]
0x1800398ab  or      [rax], r8
0x1800398ae  jmp     short loc_1800398CB
0x1800398b0  lea     r8, [rbp+arg_0]
0x1800398b4  mov     edx, 32h ; '2'
0x1800398b9  mov     rcx, rdi
0x1800398bc  call    PfsHashTableCorruptionCallback
0x1800398c1  mov     r8, 8000000000000002h
0x1800398cb  lea     r15, [rsi+1A8h]
0x1800398d2  mov     r12, [r15+8]
0x1800398d6  mov     rsi, r12
0x1800398d9  mov     [rbp+arg_0], rsi
0x1800398dd  test    rsi, rsi
0x1800398e0  jz      short loc_180039920
0x1800398e2  mov     rax, [rsi]
0x1800398e5  and     rax, r8
0x1800398e8  cmp     rax, r8
0x1800398eb  jnz     short loc_18003990C
0x1800398ed  lea     r8, [rbp+arg_0]
0x1800398f1  mov     edx, 1Eh
0x1800398f6  mov     rcx, r15
0x1800398f9  call    PfsHashTableCorruptionCallback
0x1800398fe  mov     rsi, [rbp+arg_0]
0x180039902  mov     r8, 8000000000000002h
0x18003990c  test    rsi, rsi
0x18003990f  jz      short loc_180039920
0x180039911  mov     rsi, [rsi]
0x180039914  test    sil, 1
0x180039918  jnz     short loc_180039920
0x18003991a  lea     r14, [r15+4]
0x18003991e  jmp     short loc_18003999B
0x180039920  mov     rax, [r15+8]
0x180039924  lea     r14, [r15+4]
0x180039928  mov     ecx, [r14]
0x18003992b  add     r12, 8
0x18003992f  shr     rcx, 5
0x180039933  lea     rdx, [rax+rcx*8]
0x180039937  jmp     short loc_180039947
0x180039939  mov     rsi, [r12]
0x18003993d  test    sil, 1
0x180039941  jz      short loc_180039997
0x180039943  add     r12, 8
0x180039947  cmp     r12, rdx
0x18003994a  jb      short loc_180039939
0x18003994c  mov     rsi, [rbp+lpMem]
0x180039950  xor     r12d, r12d
0x180039953  mov     r8, [rsi+1B0h]; lpMem
0x18003995a  test    r8, r8
0x18003995d  jz      short loc_180039972
0x18003995f  mov     rcx, cs:PfSvcGlobals
0x180039966  xor     edx, edx; dwFlags
0x180039968  mov     rcx, [rcx+58h]; hHeap
0x18003996c  call    cs:__imp_HeapFree
0x180039972  mov     [r15], r12d
0x180039975  mov     r8, rsi; lpMem
0x180039978  mov     [r15+8], r12
0x18003997c  xor     edx, edx; dwFlags
0x18003997e  mov     [r14], r12d
0x180039981  mov     rcx, cs:PfSvcGlobals
0x180039988  mov     rcx, [rcx+58h]; hHeap
0x18003998c  call    cs:__imp_HeapFree
0x180039992  jmp     loc_180039758
0x180039997  mov     [rbp+arg_0], rsi
0x18003999b  mov     rax, rsi
0x18003999e  test    rax, rax
0x1800399a1  jz      short loc_18003994C
0x1800399a3  mov     rdx, rsi
0x1800399a6  mov     r14, rsi
0x1800399a9  mov     [rbp+arg_0], rdx
0x1800399ad  mov     rax, [rsi]
0x1800399b0  and     rax, r8
0x1800399b3  cmp     rax, r8
0x1800399b6  jnz     short loc_1800399D7
0x1800399b8  lea     r8, [rbp+arg_0]
0x1800399bc  mov     edx, 28h ; '('
0x1800399c1  mov     rcx, r15
0x1800399c4  call    PfsHashTableCorruptionCallback
0x1800399c9  mov     rdx, [rbp+arg_0]
0x1800399cd  mov     r8, 8000000000000002h
0x1800399d7  mov     rcx, r12
0x1800399da  mov     rax, [rcx]
0x1800399dd  test    al, 1
0x1800399df  jnz     short loc_180039A05
0x1800399e1  cmp     rax, rdx
0x1800399e4  jz      short loc_1800399EB
0x1800399e6  mov     rcx, rax
0x1800399e9  jmp     short loc_1800399DA
0x1800399eb  mov     rax, [rdx]
0x1800399ee  mov     rsi, rcx
0x1800399f1  mov     [rcx], rax
  ... truncated ...
```
