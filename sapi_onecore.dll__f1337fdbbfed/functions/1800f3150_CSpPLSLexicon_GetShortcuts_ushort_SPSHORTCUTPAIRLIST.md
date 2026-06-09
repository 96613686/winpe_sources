# CSpPLSLexicon::GetShortcuts(ushort,SPSHORTCUTPAIRLIST *)

- ea: `0x1800f3150`
- end: `0x1800f3367`
- name: `?GetShortcuts@CSpPLSLexicon@@UEAAJGPEAUSPSHORTCUTPAIRLIST@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(CSpPLSLexicon *__hidden this, unsigned __int16, struct SPSHORTCUTPAIRLIST *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800f2cb8`
- `0x1800f2de4`
- `0x1800f3150`
- `0x1800f3910`
- `0x1800f3f20`
- `0x1800f474c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f318f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f318f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f330e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f330e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f31d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f32e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f32fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f31d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f32e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f32fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f32cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f32cf`

## pseudocode

```c
__int64 __fastcall CSpPLSLexicon::GetShortcuts(CSpPLSLexicon *this, unsigned __int16 a2, struct SPSHORTCUTPAIRLIST *a3)
{
  __int64 v4; // r13
  struct SPSHORTCUTPAIR *v7; // rsi
  unsigned int v8; // edi
  BYTE **p_pvBuffer; // r14
  ULONG v10; // r12d
  BYTE *pvBuffer; // rcx
  CPLSWord *NextEntry; // rax
  CPLSWord *v13; // rdi
  _QWORD *i; // rax
  _QWORD *v15; // rcx
  struct SPSHORTCUTPAIR *v16; // rax
  __int128 v17; // xmm1
  SPSHORTCUTPAIR *v18; // rax
  struct SPSHORTCUTPAIR *v19; // rbx
  struct SPSHORTCUTPAIR *pNextSHORTCUTPAIR; // rbx
  const struct SPSHORTCUTPAIR *v22; // r14
  struct SPSHORTCUTPAIR *v23; // rax
  __int64 v24; // [rsp+20h] [rbp-40h] BYREF
  struct SPSHORTCUTPAIR *v25; // [rsp+28h] [rbp-38h]
  void *v26; // [rsp+30h] [rbp-30h] BYREF
  _QWORD *v27; // [rsp+38h] [rbp-28h]
  __int128 v28; // [rsp+40h] [rbp-20h]
  __int128 v29; // [rsp+50h] [rbp-10h]
  unsigned int v30; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 v31; // [rsp+A8h] [rbp+48h]
  int v32; // [rsp+B8h] [rbp+58h] BYREF

  v31 = a2;
  v4 = (__int64)this + 24;
  if ( this == (CSpPLSLexicon *)32 )
    v4 = 8;
  EnterCriticalSection((LPCRITICAL_SECTION)v4);
  v7 = 0;
  v24 = 0;
  v32 = 0;
  if ( a2 != *((_WORD *)this + 91) )
  {
    v8 = -2147200999;
    p_pvBuffer = &a3->pvBuffer;
LABEL_24:
    CoTaskMemFree(*p_pvBuffer);
    *p_pvBuffer = 0;
LABEL_25:
    if ( !v7 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    goto LABEL_27;
  }
  v25 = 0;
  v10 = 0;
  p_pvBuffer = &a3->pvBuffer;
  pvBuffer = a3->pvBuffer;
  if ( pvBuffer )
  {
    CoTaskMemFree(pvBuffer);
    *p_pvBuffer = 0;
  }
  while ( 1 )
  {
    NextEntry = (CPLSWord *)CSPHash<unsigned short const *,CPLSWord *>::GetNextEntry((char *)this + 144, &v32, &v24);
    v13 = NextEntry;
    if ( !NextEntry )
      break;
    v26 = CPLSWord::EnumLexeme(NextEntry);
    v30 = 0;
    while ( CPLSWord::NextLexemeID(v13, &v30, &v26) )
    {
      for ( i = *(_QWORD **)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * (int)v30) + 48LL); i; i = v27 )
      {
        v27 = (_QWORD *)*i;
        v15 = (_QWORD *)i[2];
        if ( v15 )
        {
          *(_QWORD *)&v28 = 0;
          *((_QWORD *)&v28 + 1) = v31 | 0xFFFFFFFF00000000uLL;
          *(_QWORD *)&v29 = v24;
          *((_QWORD *)&v29 + 1) = *v15;
          v16 = (struct SPSHORTCUTPAIR *)CoTaskMemAlloc(0x20u);
          if ( !v16 )
            goto LABEL_23;
          v17 = v29;
          *(_OWORD *)&v16->pNextSHORTCUTPAIR = v28;
          *(_OWORD *)&v16->pszDisplay = v17;
          if ( v7 )
            v25->pNextSHORTCUTPAIR = v16;
          else
            v7 = v16;
          v25 = v16;
          v10 += PairSize(v16);
        }
      }
    }
  }
  v8 = 0;
  if ( !v10 )
    goto LABEL_25;
  v18 = (SPSHORTCUTPAIR *)CoTaskMemAlloc(v10);
  v19 = v18;
  if ( !v18 )
  {
LABEL_23:
    v8 = -2147024882;
    goto LABEL_24;
  }
  *p_pvBuffer = (BYTE *)v18;
  v22 = v7;
  a3->ulSize = v10;
  a3->pFirstShortcutPair = v18;
  if ( !v7 )
    goto LABEL_27;
  do
  {
    v23 = CopyPair(v19, v22);
    v19->pNextSHORTCUTPAIR = v23;
    if ( v22->pNextSHORTCUTPAIR )
    {
      v19 = v23;
    }
    else
    {
      v19->pNextSHORTCUTPAIR = 0;
      v19 = 0;
    }
    v22 = v22->pNextSHORTCUTPAIR;
  }
  while ( v22 );
  do
  {
LABEL_26:
    pNextSHORTCUTPAIR = v7->pNextSHORTCUTPAIR;
    CoTaskMemFree(v7);
    v7 = pNextSHORTCUTPAIR;
  }
  while ( pNextSHORTCUTPAIR );
LABEL_27:
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  return v8;
}

```

## disassembly

```asm
0x1800f3150  mov     [rsp-38h+arg_10], rbx
0x1800f3155  mov     [rsp-38h+arg_8], dx
0x1800f315a  push    rbp
0x1800f315b  push    rsi
0x1800f315c  push    rdi
0x1800f315d  push    r12
0x1800f315f  push    r13
0x1800f3161  push    r14
0x1800f3163  push    r15
0x1800f3165  mov     rbp, rsp
0x1800f3168  sub     rsp, 60h
0x1800f316c  lea     rax, [rcx-20h]
0x1800f3170  mov     rbx, rcx
0x1800f3173  lea     r13, [rcx+18h]
0x1800f3177  xor     r14d, r14d
0x1800f317a  test    rax, rax
0x1800f317d  mov     ecx, 8
0x1800f3182  mov     r15, r8
0x1800f3185  movzx   edi, dx
0x1800f3188  cmovz   r13, rcx
0x1800f318c  mov     rcx, r13; lpCriticalSection
0x1800f318f  call    cs:__imp_EnterCriticalSection
0x1800f3195  mov     esi, r14d
0x1800f3198  mov     [rbp+var_40], r14
0x1800f319c  mov     [rbp+arg_18], r14d
0x1800f31a0  cmp     di, [rbx+0B6h]
0x1800f31a7  jz      short loc_1800F31B7
0x1800f31a9  mov     edi, 80045019h
0x1800f31ae  lea     r14, [r15+8]
0x1800f31b2  jmp     loc_1800F32E2
0x1800f31b7  test    r15, r15
0x1800f31ba  jnz     short loc_1800F31C6
0x1800f31bc  mov     edi, 80070057h
0x1800f31c1  jmp     loc_1800F330B
0x1800f31c6  mov     [rbp+var_38], r14
0x1800f31ca  mov     r12d, r14d
0x1800f31cd  lea     r14, [r15+8]
0x1800f31d1  mov     rcx, [r14]; pv
0x1800f31d4  test    rcx, rcx
0x1800f31d7  jz      short loc_1800F31E2
0x1800f31d9  call    cs:__imp_CoTaskMemFree
0x1800f31df  mov     [r14], rsi
0x1800f31e2  lea     rax, [rbx+90h]
0x1800f31e9  mov     rcx, rax
0x1800f31ec  lea     r8, [rbp+var_40]
0x1800f31f0  lea     rdx, [rbp+arg_18]
0x1800f31f4  call    ?GetNextEntry@?$CSPHash@PEBGPEAVCPLSWord@@@@QEBAPEAVCPLSWord@@PEAIPEAPEBG@Z; CSPHash<ushort const *,CPLSWord *>::GetNextEntry(uint *,ushort const * *)
0x1800f31f9  mov     rdi, rax
0x1800f31fc  test    rax, rax
0x1800f31ff  jz      loc_1800F32C5
0x1800f3205  mov     rcx, rax; this
0x1800f3208  call    ?EnumLexeme@CPLSWord@@QEAAPEAXXZ; CPLSWord::EnumLexeme(void)
0x1800f320d  mov     [rbp+var_30], rax
0x1800f3211  mov     [rbp+arg_0], 0
0x1800f3218  lea     r8, [rbp+var_30]; void **
0x1800f321c  mov     rcx, rdi; this
0x1800f321f  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800f3223  call    ?NextLexemeID@CPLSWord@@QEAA_NPEAKPEAPEAX@Z; CPLSWord::NextLexemeID(ulong *,void * *)
0x1800f3228  test    al, al
0x1800f322a  jz      short loc_1800F31E2
0x1800f322c  mov     rax, [rbx+50h]
0x1800f3230  movsxd  rcx, [rbp+arg_0]
0x1800f3234  mov     rcx, [rax+rcx*8]
0x1800f3238  mov     rax, [rcx+30h]
0x1800f323c  test    rax, rax
0x1800f323f  jz      short loc_1800F3218
0x1800f3241  mov     rcx, [rax]
0x1800f3244  mov     [rbp+var_28], rcx
0x1800f3248  mov     rcx, [rax+10h]
0x1800f324c  test    rcx, rcx
0x1800f324f  jz      short loc_1800F32BC
0x1800f3251  xor     eax, eax
0x1800f3253  mov     qword ptr [rbp+var_20], 0
0x1800f325b  mov     word ptr [rbp+var_20+0Ah], ax
0x1800f325f  movzx   eax, [rbp+arg_8]
0x1800f3263  mov     word ptr [rbp+var_20+8], ax
0x1800f3267  mov     rax, [rbp+var_40]
0x1800f326b  mov     qword ptr [rbp+var_10], rax
0x1800f326f  mov     rax, [rcx]
0x1800f3272  mov     ecx, 20h ; ' '; cb
0x1800f3277  mov     qword ptr [rbp+var_10+8], rax
0x1800f327b  mov     dword ptr [rbp+var_20+0Ch], 0FFFFFFFFh
0x1800f3282  call    cs:__imp_CoTaskMemAlloc
0x1800f3288  test    rax, rax
0x1800f328b  jz      short loc_1800F32DD
0x1800f328d  movups  xmm0, [rbp+var_20]
0x1800f3291  movups  xmm1, [rbp+var_10]
0x1800f3295  movups  xmmword ptr [rax], xmm0
0x1800f3298  movups  xmmword ptr [rax+10h], xmm1
0x1800f329c  test    rsi, rsi
0x1800f329f  jnz     short loc_1800F32A6
0x1800f32a1  mov     rsi, rax
0x1800f32a4  jmp     short loc_1800F32AD
0x1800f32a6  mov     rcx, [rbp+var_38]
0x1800f32aa  mov     [rcx], rax
0x1800f32ad  mov     rcx, rax; struct SPSHORTCUTPAIR *
0x1800f32b0  mov     [rbp+var_38], rax
0x1800f32b4  call    ?PairSize@@YAKPEBUSPSHORTCUTPAIR@@@Z; PairSize(SPSHORTCUTPAIR const *)
0x1800f32b9  add     r12d, eax
0x1800f32bc  mov     rax, [rbp+var_28]
0x1800f32c0  jmp     loc_1800F323C
0x1800f32c5  xor     edi, edi
0x1800f32c7  test    r12d, r12d
0x1800f32ca  jz      short loc_1800F32F2
0x1800f32cc  mov     ecx, r12d; cb
0x1800f32cf  call    cs:__imp_CoTaskMemAlloc
0x1800f32d5  mov     rbx, rax
0x1800f32d8  test    rax, rax
0x1800f32db  jnz     short loc_1800F332E
0x1800f32dd  mov     edi, 8007000Eh
0x1800f32e2  mov     rcx, [r14]; pv
0x1800f32e5  call    cs:__imp_CoTaskMemFree
0x1800f32eb  mov     qword ptr [r14], 0
0x1800f32f2  test    rsi, rsi
0x1800f32f5  jz      short loc_1800F330B
0x1800f32f7  mov     rbx, [rsi]
0x1800f32fa  mov     rcx, rsi; pv
0x1800f32fd  call    cs:__imp_CoTaskMemFree
0x1800f3303  mov     rsi, rbx
0x1800f3306  test    rbx, rbx
0x1800f3309  jnz     short loc_1800F32F7
0x1800f330b  mov     rcx, r13; lpCriticalSection
0x1800f330e  call    cs:__imp_LeaveCriticalSection
0x1800f3314  mov     rbx, [rsp+60h+arg_10]
0x1800f331c  mov     eax, edi
0x1800f331e  add     rsp, 60h
0x1800f3322  pop     r15
0x1800f3324  pop     r14
0x1800f3326  pop     r13
0x1800f3328  pop     r12
0x1800f332a  pop     rdi
0x1800f332b  pop     rsi
0x1800f332c  pop     rbp
0x1800f332d  retn
0x1800f332e  mov     [r14], rax
0x1800f3331  mov     r14, rsi
0x1800f3334  mov     [r15], r12d
0x1800f3337  mov     [r15+10h], rax
0x1800f333b  test    rsi, rsi
0x1800f333e  jz      short loc_1800F330B
0x1800f3340  mov     rdx, r14; struct SPSHORTCUTPAIR *
0x1800f3343  mov     rcx, rbx; struct SPSHORTCUTPAIR *
0x1800f3346  call    ?CopyPair@@YAPEAUSPSHORTCUTPAIR@@PEAU1@PEBU1@@Z; CopyPair(SPSHORTCUTPAIR *,SPSHORTCUTPAIR const *)
0x1800f334b  mov     [rbx], rax
0x1800f334e  cmp     [r14], rdi
0x1800f3351  jnz     short loc_1800F335A
0x1800f3353  mov     [rbx], rdi
0x1800f3356  xor     ebx, ebx
0x1800f3358  jmp     short loc_1800F335D
0x1800f335a  mov     rbx, rax
0x1800f335d  mov     r14, [r14]
0x1800f3360  test    r14, r14
0x1800f3363  jnz     short loc_1800F3340
0x1800f3365  jmp     short loc_1800F32F7
```
