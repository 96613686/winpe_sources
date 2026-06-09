# UbpmCreateAggEventWithConstraints

- ea: `0x180014420`
- end: `0x180014835`
- name: `UbpmCreateAggEventWithConstraints`
- size: `1045`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013b60`
- `0x180036604`

## callees

- `0x180014420`
- `0x18001e9f4`
- `0x18003d810`

## import_xrefs

- `EventAggregation!EACreateAggregateEvent` at `0x18001459f`
- `EventAggregation!EACreateAggregateEvent` at `0x180014641`
- `EventAggregation!EACreateAggregateEvent` at `0x180014670`
- `EventAggregation!EACreateAggregateEvent` at `0x18001459f`
- `EventAggregation!EACreateAggregateEvent` at `0x180014641`
- `EventAggregation!EACreateAggregateEvent` at `0x180014670`

## pseudocode

```c
__int64 __fastcall UbpmCreateAggEventWithConstraints(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int16 v8; // r10
  unsigned int v11; // r8d
  char v12; // r11
  unsigned int v13; // edi
  int v14; // r9d
  unsigned int i; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  bool v18; // zf
  unsigned int v19; // ebx
  unsigned int n; // ecx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  int v26; // edx
  unsigned int j; // ecx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned int m; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned int k; // ecx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  _BYTE v43[56]; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v44[20]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v45; // [rsp+7Ch] [rbp-3Dh]
  int v46; // [rsp+8Ch] [rbp-2Dh]
  _BYTE v47[20]; // [rsp+90h] [rbp-29h] BYREF
  __int128 v48; // [rsp+A4h] [rbp-15h]
  int v49; // [rsp+B4h] [rbp-5h]

  v8 = a1;
  memset(v44, 0, sizeof(v44));
  v46 = 0;
  memset(v47, 0, sizeof(v47));
  v49 = 0;
  v11 = 0;
  memset(&v43[4], 0, 48);
  *(_QWORD *)v43 = a2;
  *(_QWORD *)&v43[48] = a5;
  v45 = 0;
  v48 = 0;
  if ( !a1 )
    goto LABEL_21;
  v12 = 0;
  v13 = 0;
  v14 = a1 & 2;
  if ( (a1 & 2) != 0 || (a1 & 4) != 0 )
  {
    for ( i = 0; i < 5; ++i )
    {
      v16 = 28LL * i;
      if ( *(_DWORD *)((char *)&g_CSebConditions + v16 + 4) == 4121 )
      {
        v17 = *(__int64 *)((char *)&g_CSebConditions + v16 + 20);
        v18 = v14 == 0;
        if ( (a1 & 2) != 0 )
        {
          *(_QWORD *)v44 = *(struct _UBPM_GLOBAL_STATE_CONDITIONS near **)((char *)&g_CSebConditions + v16 + 20);
          v18 = v14 == 0;
        }
        LOBYTE(v11) = !v18;
        if ( (a1 & 4) != 0 )
        {
          *(_QWORD *)v47 = v17;
          v13 = 1;
        }
        if ( v11 != v13 )
          v12 = 1;
        goto LABEL_13;
      }
    }
    return 1168;
  }
LABEL_13:
  if ( (a1 & 0x40) != 0 || (a1 & 0x80u) != 0 )
  {
    for ( j = 0; j < 5; ++j )
    {
      v28 = 28LL * j;
      if ( *(_DWORD *)((char *)&g_CSebConditions + v28 + 4) == 4102 )
      {
        v29 = *(__int64 *)((char *)&g_CSebConditions + v28 + 20);
        if ( (v8 & 0x40) != 0 )
        {
          v30 = v11++;
          *(_QWORD *)&v44[8 * v30] = v29;
        }
        if ( (v8 & 0x80u) != 0 )
        {
          v31 = v13++;
          *(_QWORD *)&v47[8 * v31] = v29;
        }
        if ( v11 != v13 )
          v12 = 1;
        goto LABEL_15;
      }
    }
    return 1168;
  }
LABEL_15:
  if ( (v8 & 0x200) != 0 )
  {
    for ( k = 0; k < 5; ++k )
    {
      v37 = 28LL * k;
      if ( *(_DWORD *)((char *)&g_CSebConditions + v37 + 4) == 4113 )
      {
        v38 = *(__int64 *)((char *)&g_CSebConditions + v37 + 20);
        v39 = v11++;
        *(_QWORD *)&v44[8 * v39] = v38;
        v40 = v13++;
        *(_QWORD *)&v47[8 * v40] = v38;
        goto LABEL_16;
      }
    }
    return 1168;
  }
LABEL_16:
  if ( (v8 & 0x800) != 0 || (v8 & 0x1000) != 0 )
  {
    for ( m = 0; m < 5; ++m )
    {
      v33 = 28LL * m;
      if ( *(_DWORD *)((char *)&g_CSebConditions + v33 + 4) == 4125 )
      {
        v34 = *(__int64 *)((char *)&g_CSebConditions + v33 + 20);
        if ( (v8 & 0x800) != 0 )
        {
          v35 = v11++;
          *(_QWORD *)&v44[8 * v35] = v34;
        }
        if ( (v8 & 0x1000) != 0 )
        {
          v42 = v13++;
          *(_QWORD *)&v47[8 * v42] = v34;
        }
        if ( v11 != v13 )
          v12 = 1;
        goto LABEL_18;
      }
    }
    return 1168;
  }
LABEL_18:
  if ( (v8 & 0x4000) != 0 || v8 < 0 )
  {
    for ( n = 0; n < 5; ++n )
    {
      v22 = 28LL * n;
      if ( *(_DWORD *)((char *)&g_CSebConditions + v22 + 4) == 4145 )
      {
        v23 = *(__int64 *)((char *)&g_CSebConditions + v22 + 20);
        if ( (v8 & 0x4000) != 0 )
        {
          v24 = v11++;
          *(_QWORD *)&v44[8 * v24] = v23;
        }
        if ( v8 < 0 )
        {
          v41 = v13++;
          *(_QWORD *)&v47[8 * v41] = v23;
        }
        if ( v11 == v13 )
          goto LABEL_20;
        goto LABEL_32;
      }
    }
    return 1168;
  }
LABEL_20:
  if ( v12 )
  {
LABEL_32:
    *(_QWORD *)&v43[32] = a3;
    *(_QWORD *)&v43[16] = v44;
    *(_QWORD *)&v43[40] = 0;
    *(_DWORD *)&v43[24] = 0;
    *(_DWORD *)&v43[12] = v11;
    v19 = EACreateAggregateEvent(v43, a6);
    if ( v19 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v19;
      v26 = 11;
    }
    else
    {
      *(_QWORD *)&v43[32] = 0;
      *(_QWORD *)&v43[16] = v47;
      *(_QWORD *)&v43[40] = a4;
      *(_DWORD *)&v43[24] = 0;
      *(_DWORD *)&v43[12] = v13;
      v19 = EACreateAggregateEvent(v43, a7);
      if ( !v19 )
        return v19;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v19;
      v26 = 12;
    }
LABEL_73:
    WPP_SF_Sd(v25[2], v26, (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids, a8, v19);
    return v19;
  }
LABEL_21:
  *(_QWORD *)&v43[32] = a3;
  *(_QWORD *)&v43[16] = v44;
  *(_QWORD *)&v43[40] = a4;
  *(_DWORD *)&v43[24] = 0;
  *(_DWORD *)&v43[12] = v11;
  v19 = EACreateAggregateEvent(v43, a6);
  if ( v19 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v26 = 13;
      goto LABEL_73;
    }
  }
  return v19;
}

```

## disassembly

```asm
0x180014420  mov     [rsp-8+arg_0], rbx
0x180014425  push    rbp
0x180014426  push    rsi
0x180014427  push    rdi
0x180014428  push    r12
0x18001442a  push    r13
0x18001442c  push    r14
0x18001442e  push    r15
0x180014430  lea     rbp, [rsp-7]
0x180014435  sub     rsp, 0C0h
0x18001443c  mov     rax, cs:__security_cookie
0x180014443  xor     rax, rsp
0x180014446  mov     [rbp+37h+var_38], rax
0x18001444a  mov     rax, [rbp+37h+arg_20]
0x18001444e  xor     r13d, r13d
0x180014451  mov     r14, [rbp+37h+arg_28]
0x180014455  xorps   xmm0, xmm0
0x180014458  mov     r15, [rbp+37h+arg_30]
0x18001445c  xorps   xmm1, xmm1
0x18001445f  mov     r12, [rbp+37h+arg_38]
0x180014463  mov     r10d, ecx
0x180014466  xor     ecx, ecx
0x180014468  mov     dword ptr [rbp+37h+var_88], r13d
0x18001446c  mov     [rbp+37h+var_64], ecx
0x18001446f  mov     rbx, r8
0x180014472  mov     dword ptr [rbp+37h+var_60], r13d
0x180014476  mov     rsi, r9
0x180014479  mov     [rbp+37h+var_3C], ecx
0x18001447c  mov     r8d, r13d
0x18001447f  movups  [rsp+0F0h+var_BC], xmm1
0x180014484  mov     [rsp+30h], rdx
0x180014489  movups  [rbp+37h+var_9C], xmm1
0x18001448d  mov     qword ptr [rbp+37h+var_9C+0Ch], rax
0x180014491  movups  xmmword ptr [rbp+37h+var_88+4], xmm0
0x180014495  movups  [rbp+37h+var_74], xmm0
0x180014499  movups  xmmword ptr [rbp+37h+var_60+4], xmm0
0x18001449d  movups  [rbp+37h+var_4C], xmm0
0x1800144a1  movups  [rbp+37h+var_AC], xmm1
0x1800144a5  test    r10d, r10d
0x1800144a8  jz      loc_18001457F
0x1800144ae  xor     r11b, r11b
0x1800144b1  mov     r9d, r10d
0x1800144b4  mov     edi, r13d
0x1800144b7  and     r9d, 2
0x1800144bb  jz      loc_18001475B
0x1800144c1  mov     eax, r13d
0x1800144c4  cmp     eax, 5
0x1800144c7  jnb     loc_1800147B3
0x1800144cd  mov     ecx, eax
0x1800144cf  imul    rdx, rcx, 1Ch
0x1800144d3  lea     rcx, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x1800144da  cmp     dword ptr [rdx+rcx+4], 1019h
0x1800144e2  jz      short loc_1800144E8
0x1800144e4  inc     eax
0x1800144e6  jmp     short loc_1800144C4
0x1800144e8  mov     rax, [rdx+rcx+14h]
0x1800144ed  test    r9d, r9d
0x1800144f0  jz      short loc_180014502
0x1800144f2  mov     rcx, rax
0x1800144f5  mov     dword ptr [rbp+37h+var_88], eax
0x1800144f8  shr     rcx, 20h
0x1800144fc  mov     dword ptr [rbp+37h+var_88+4], ecx
0x1800144ff  test    r9d, r9d
0x180014502  setnz   r8b
0x180014506  test    r10b, 4
0x18001450a  jz      short loc_18001451B
0x18001450c  mov     dword ptr [rbp+37h+var_60], eax
0x18001450f  mov     edi, 1
0x180014514  shr     rax, 20h
0x180014518  mov     dword ptr [rbp+37h+var_60+4], eax
0x18001451b  cmp     r8d, edi
0x18001451e  jz      short loc_180014523
0x180014520  mov     r11b, 1
0x180014523  mov     edx, r10d
0x180014526  and     edx, 40h
0x180014529  jnz     loc_1800146AB
0x18001452f  test    r10b, r10b
0x180014532  js      loc_1800146AB
0x180014538  lea     r9, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18001453f  bt      r10d, 9
0x180014544  jb      loc_18001476A
0x18001454a  mov     edx, r10d
0x18001454d  and     edx, 800h
0x180014553  jnz     loc_18001470A
0x180014559  bt      r10d, 0Ch
0x18001455e  jb      loc_18001470A
0x180014564  mov     edx, r10d
0x180014567  and     edx, 4000h
0x18001456d  jnz     short loc_1800145D8
0x18001456f  bt      r10d, 0Fh
0x180014574  jb      short loc_1800145D8
0x180014576  test    r11b, r11b
0x180014579  jnz     loc_180014621
0x18001457f  lea     rax, [rbp+37h+var_88]
0x180014583  mov     qword ptr [rbp+37h+var_AC+0Ch], rbx
0x180014587  mov     rdx, r14
0x18001458a  mov     qword ptr [rbp+37h+var_BC+0Ch], rax
0x18001458e  lea     rcx, [rsp+0F0h+var_C0]
0x180014593  mov     qword ptr [rbp+37h+var_9C+4], rsi
0x180014597  mov     dword ptr [rbp+37h+var_AC+4], r13d
0x18001459b  mov     dword ptr [rbp+37h+var_BC+8], r8d
0x18001459f  call    cs:__imp_EACreateAggregateEvent
0x1800145a5  mov     ebx, eax
0x1800145a7  test    eax, eax
0x1800145a9  jnz     loc_1800147F3
0x1800145af  mov     eax, ebx
0x1800145b1  mov     rcx, [rbp+37h+var_38]
0x1800145b5  xor     rcx, rsp; StackCookie
0x1800145b8  call    __security_check_cookie
0x1800145bd  mov     rbx, [rsp+0F0h+arg_0]
0x1800145c5  add     rsp, 0C0h
0x1800145cc  pop     r15
0x1800145ce  pop     r14
0x1800145d0  pop     r13
0x1800145d2  pop     r12
0x1800145d4  pop     rdi
0x1800145d5  pop     rsi
0x1800145d6  pop     rbp
0x1800145d7  retn
0x1800145d8  mov     ecx, r13d
0x1800145db  cmp     ecx, 5
0x1800145de  jnb     loc_1800147B3
0x1800145e4  mov     eax, ecx
0x1800145e6  imul    rax, 1Ch
0x1800145ea  cmp     dword ptr [rax+r9+4], 1031h
0x1800145f3  jz      short loc_1800145F9
0x1800145f5  inc     ecx
0x1800145f7  jmp     short loc_1800145DB
0x1800145f9  mov     rax, [rax+r9+14h]
0x1800145fe  test    edx, edx
0x180014600  jz      short loc_18001460D
0x180014602  mov     ecx, r8d
0x180014605  inc     r8d
0x180014608  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x18001460d  bt      r10d, 0Fh
0x180014612  jb      loc_1800147A5
0x180014618  cmp     r8d, edi
0x18001461b  jz      loc_180014576
0x180014621  lea     rax, [rbp+37h+var_88]
0x180014625  mov     qword ptr [rbp+37h+var_AC+0Ch], rbx
0x180014629  mov     rdx, r14
0x18001462c  mov     qword ptr [rbp+37h+var_BC+0Ch], rax
0x180014630  lea     rcx, [rsp+0F0h+var_C0]
0x180014635  mov     qword ptr [rbp+37h+var_9C+4], r13
0x180014639  mov     dword ptr [rbp+37h+var_AC+4], r13d
0x18001463d  mov     dword ptr [rbp+37h+var_BC+8], r8d
0x180014641  call    cs:__imp_EACreateAggregateEvent
0x180014647  mov     ebx, eax
0x180014649  test    eax, eax
0x18001464b  jnz     loc_1800147CB
0x180014651  lea     rax, [rbp+37h+var_60]
0x180014655  mov     qword ptr [rbp+37h+var_AC+0Ch], r13
0x180014659  mov     rdx, r15
0x18001465c  mov     qword ptr [rbp+37h+var_BC+0Ch], rax
0x180014660  lea     rcx, [rsp+0F0h+var_C0]
0x180014665  mov     qword ptr [rbp+37h+var_9C+4], rsi
0x180014669  mov     dword ptr [rbp+37h+var_AC+4], r13d
0x18001466d  mov     dword ptr [rbp+37h+var_BC+8], edi
0x180014670  call    cs:__imp_EACreateAggregateEvent
0x180014676  mov     ebx, eax
0x180014678  test    eax, eax
0x18001467a  jz      loc_1800145AF
0x180014680  mov     rcx, cs:WPP_GLOBAL_Control
0x180014687  lea     rax, WPP_GLOBAL_Control
0x18001468e  cmp     rcx, rax
0x180014691  jz      loc_1800145AF
0x180014697  test    byte ptr [rcx+1Ch], 1
0x18001469b  jz      loc_1800145AF
0x1800146a1  mov     edx, 0Ch
0x1800146a6  jmp     loc_180014819
0x1800146ab  mov     ecx, r13d
0x1800146ae  lea     r9, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x1800146b5  cmp     ecx, 5
0x1800146b8  jnb     loc_1800147B3
0x1800146be  mov     eax, ecx
0x1800146c0  imul    rax, 1Ch
0x1800146c4  cmp     dword ptr [rax+r9+4], 1006h
0x1800146cd  jz      short loc_1800146D3
0x1800146cf  inc     ecx
0x1800146d1  jmp     short loc_1800146B5
0x1800146d3  mov     rax, [rax+r9+14h]
0x1800146d8  test    edx, edx
0x1800146da  jz      short loc_1800146E7
0x1800146dc  mov     ecx, r8d
0x1800146df  inc     r8d
0x1800146e2  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x1800146e7  test    r10b, r10b
0x1800146ea  jns     short loc_1800146F5
0x1800146ec  mov     ecx, edi
0x1800146ee  inc     edi
0x1800146f0  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x1800146f5  cmp     r8d, edi
0x1800146f8  movzx   r11d, r11b
0x1800146fc  mov     eax, 1
0x180014701  cmovnz  r11d, eax
0x180014705  jmp     loc_18001453F
0x18001470a  mov     ecx, r13d
0x18001470d  cmp     ecx, 5
0x180014710  jnb     loc_1800147B3
0x180014716  mov     eax, ecx
0x180014718  imul    rax, 1Ch
0x18001471c  cmp     dword ptr [rax+r9+4], 101Dh
0x180014725  jz      short loc_18001472B
0x180014727  inc     ecx
0x180014729  jmp     short loc_18001470D
0x18001472b  mov     rax, [rax+r9+14h]
0x180014730  test    edx, edx
0x180014732  jz      short loc_18001473F
0x180014734  mov     ecx, r8d
0x180014737  inc     r8d
0x18001473a  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x18001473f  bt      r10d, 0Ch
0x180014744  jb      short loc_1800147BD
0x180014746  cmp     r8d, edi
0x180014749  movzx   r11d, r11b
0x18001474d  mov     ecx, 1
0x180014752  cmovnz  r11d, ecx
0x180014756  jmp     loc_180014564
0x18001475b  test    r10b, 4
0x18001475f  jz      loc_180014523
0x180014765  jmp     loc_1800144C1
0x18001476a  mov     ecx, r13d
0x18001476d  cmp     ecx, 5
0x180014770  jnb     short loc_1800147B3
0x180014772  mov     eax, ecx
0x180014774  imul    rax, 1Ch
0x180014778  cmp     dword ptr [rax+r9+4], 1011h
0x180014781  jz      short loc_180014787
0x180014783  inc     ecx
0x180014785  jmp     short loc_18001476D
0x180014787  mov     rax, [rax+r9+14h]
0x18001478c  mov     ecx, r8d
0x18001478f  inc     r8d
0x180014792  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x180014797  mov     ecx, edi
0x180014799  inc     edi
0x18001479b  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x1800147a0  jmp     loc_18001454A
0x1800147a5  mov     ecx, edi
0x1800147a7  inc     edi
0x1800147a9  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x1800147ae  jmp     loc_180014618
0x1800147b3  mov     ebx, 490h
0x1800147b8  jmp     loc_1800145AF
0x1800147bd  mov     ecx, edi
0x1800147bf  inc     edi
0x1800147c1  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x1800147c6  jmp     loc_180014746
0x1800147cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147d2  lea     rax, WPP_GLOBAL_Control
0x1800147d9  cmp     rcx, rax
0x1800147dc  jz      loc_1800145AF
0x1800147e2  test    byte ptr [rcx+1Ch], 1
0x1800147e6  jz      loc_1800145AF
0x1800147ec  mov     edx, 0Bh
0x1800147f1  jmp     short loc_180014819
0x1800147f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147fa  lea     rax, WPP_GLOBAL_Control
0x180014801  cmp     rcx, rax
0x180014804  jz      loc_1800145AF
0x18001480a  test    byte ptr [rcx+1Ch], 1
0x18001480e  jz      loc_1800145AF
0x180014814  mov     edx, 0Dh
0x180014819  mov     rcx, [rcx+10h]
0x18001481d  lea     r8, WPP_029c709143543b8b7778781675a35e95_Traceguids
0x180014824  mov     r9, r12
0x180014827  mov     [rsp+0F0h+var_D0], ebx
0x18001482b  call    WPP_SF_Sd
0x180014830  jmp     loc_1800145AF
```
