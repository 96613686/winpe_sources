# UbpmCreateAggEventWithConstraints

- ea: `0x180016720`
- end: `0x180016b48`
- name: `UbpmCreateAggEventWithConstraints`
- size: `1064`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015e20`
- `0x180038be8`

## callees

- `0x180016720`
- `0x18001af64`
- `0x180040260`

## import_xrefs

- `EventAggregation!EACreateAggregateEvent` at `0x18001689f`
- `EventAggregation!EACreateAggregateEvent` at `0x180016948`
- `EventAggregation!EACreateAggregateEvent` at `0x18001697d`
- `EventAggregation!EACreateAggregateEvent` at `0x18001689f`
- `EventAggregation!EACreateAggregateEvent` at `0x180016948`
- `EventAggregation!EACreateAggregateEvent` at `0x18001697d`

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
0x180016720  mov     [rsp-8+arg_0], rbx
0x180016725  push    rbp
0x180016726  push    rsi
0x180016727  push    rdi
0x180016728  push    r12
0x18001672a  push    r13
0x18001672c  push    r14
0x18001672e  push    r15
0x180016730  lea     rbp, [rsp-7]
0x180016735  sub     rsp, 0C0h
0x18001673c  mov     rax, cs:__security_cookie
0x180016743  xor     rax, rsp
0x180016746  mov     [rbp+37h+var_38], rax
0x18001674a  mov     rax, [rbp+37h+arg_20]
0x18001674e  xor     r13d, r13d
0x180016751  mov     r14, [rbp+37h+arg_28]
0x180016755  xorps   xmm0, xmm0
0x180016758  mov     r15, [rbp+37h+arg_30]
0x18001675c  xorps   xmm1, xmm1
0x18001675f  mov     r12, [rbp+37h+arg_38]
0x180016763  mov     r10d, ecx
0x180016766  xor     ecx, ecx
0x180016768  mov     dword ptr [rbp+37h+var_88], r13d
0x18001676c  mov     [rbp+37h+var_64], ecx
0x18001676f  mov     rbx, r8
0x180016772  mov     dword ptr [rbp+37h+var_60], r13d
0x180016776  mov     rsi, r9
0x180016779  mov     [rbp+37h+var_3C], ecx
0x18001677c  mov     r8d, r13d
0x18001677f  movups  [rsp+0F0h+var_BC], xmm1
0x180016784  mov     [rsp+30h], rdx
0x180016789  movups  [rbp+37h+var_9C], xmm1
0x18001678d  mov     qword ptr [rbp+37h+var_9C+0Ch], rax
0x180016791  movups  xmmword ptr [rbp+37h+var_88+4], xmm0
0x180016795  movups  [rbp+37h+var_74], xmm0
0x180016799  movups  xmmword ptr [rbp+37h+var_60+4], xmm0
0x18001679d  movups  [rbp+37h+var_4C], xmm0
0x1800167a1  movups  [rbp+37h+var_AC], xmm1
0x1800167a5  test    r10d, r10d
0x1800167a8  jz      loc_18001687F
0x1800167ae  xor     r11b, r11b
0x1800167b1  mov     r9d, r10d
0x1800167b4  mov     edi, r13d
0x1800167b7  and     r9d, 2
0x1800167bb  jz      loc_180016A6E
0x1800167c1  mov     eax, r13d
0x1800167c4  cmp     eax, 5
0x1800167c7  jnb     loc_180016AC6
0x1800167cd  mov     ecx, eax
0x1800167cf  imul    rdx, rcx, 1Ch
0x1800167d3  lea     rcx, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x1800167da  cmp     dword ptr [rdx+rcx+4], 1019h
0x1800167e2  jz      short loc_1800167E8
0x1800167e4  inc     eax
0x1800167e6  jmp     short loc_1800167C4
0x1800167e8  mov     rax, [rdx+rcx+14h]
0x1800167ed  test    r9d, r9d
0x1800167f0  jz      short loc_180016802
0x1800167f2  mov     rcx, rax
0x1800167f5  mov     dword ptr [rbp+37h+var_88], eax
0x1800167f8  shr     rcx, 20h
0x1800167fc  mov     dword ptr [rbp+37h+var_88+4], ecx
0x1800167ff  test    r9d, r9d
0x180016802  setnz   r8b
0x180016806  test    r10b, 4
0x18001680a  jz      short loc_18001681B
0x18001680c  mov     dword ptr [rbp+37h+var_60], eax
0x18001680f  mov     edi, 1
0x180016814  shr     rax, 20h
0x180016818  mov     dword ptr [rbp+37h+var_60+4], eax
0x18001681b  cmp     r8d, edi
0x18001681e  jz      short loc_180016823
0x180016820  mov     r11b, 1
0x180016823  mov     edx, r10d
0x180016826  and     edx, 40h
0x180016829  jnz     loc_1800169BE
0x18001682f  test    r10b, r10b
0x180016832  js      loc_1800169BE
0x180016838  lea     r9, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18001683f  bt      r10d, 9
0x180016844  jb      loc_180016A7D
0x18001684a  mov     edx, r10d
0x18001684d  and     edx, 800h
0x180016853  jnz     loc_180016A1D
0x180016859  bt      r10d, 0Ch
0x18001685e  jb      loc_180016A1D
0x180016864  mov     edx, r10d
0x180016867  and     edx, 4000h
0x18001686d  jnz     short loc_1800168DF
0x18001686f  bt      r10d, 0Fh
0x180016874  jb      short loc_1800168DF
0x180016876  test    r11b, r11b
0x180016879  jnz     loc_180016928
0x18001687f  lea     rax, [rbp+37h+var_88]
0x180016883  mov     qword ptr [rbp+37h+var_AC+0Ch], rbx
0x180016887  mov     rdx, r14
0x18001688a  mov     qword ptr [rbp+37h+var_BC+0Ch], rax
0x18001688e  lea     rcx, [rsp+0F0h+var_C0]
0x180016893  mov     qword ptr [rbp+37h+var_9C+4], rsi
0x180016897  mov     dword ptr [rbp+37h+var_AC+4], r13d
0x18001689b  mov     dword ptr [rbp+37h+var_BC+8], r8d
0x18001689f  call    cs:__imp_EACreateAggregateEvent
0x1800168a6  nop     dword ptr [rax+rax+00h]
0x1800168ab  mov     ebx, eax
0x1800168ad  test    eax, eax
0x1800168af  jnz     loc_180016B06
0x1800168b5  mov     eax, ebx
0x1800168b7  mov     rcx, [rbp+37h+var_38]
0x1800168bb  xor     rcx, rsp; StackCookie
0x1800168be  call    __security_check_cookie
0x1800168c3  mov     rbx, [rsp+0F0h+arg_0]
0x1800168cb  add     rsp, 0C0h
0x1800168d2  pop     r15
0x1800168d4  pop     r14
0x1800168d6  pop     r13
0x1800168d8  pop     r12
0x1800168da  pop     rdi
0x1800168db  pop     rsi
0x1800168dc  pop     rbp
0x1800168dd  retn
0x1800168df  mov     ecx, r13d
0x1800168e2  cmp     ecx, 5
0x1800168e5  jnb     loc_180016AC6
0x1800168eb  mov     eax, ecx
0x1800168ed  imul    rax, 1Ch
0x1800168f1  cmp     dword ptr [rax+r9+4], 1031h
0x1800168fa  jz      short loc_180016900
0x1800168fc  inc     ecx
0x1800168fe  jmp     short loc_1800168E2
0x180016900  mov     rax, [rax+r9+14h]
0x180016905  test    edx, edx
0x180016907  jz      short loc_180016914
0x180016909  mov     ecx, r8d
0x18001690c  inc     r8d
0x18001690f  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x180016914  bt      r10d, 0Fh
0x180016919  jb      loc_180016AB8
0x18001691f  cmp     r8d, edi
0x180016922  jz      loc_180016876
0x180016928  lea     rax, [rbp+37h+var_88]
0x18001692c  mov     qword ptr [rbp+37h+var_AC+0Ch], rbx
0x180016930  mov     rdx, r14
0x180016933  mov     qword ptr [rbp+37h+var_BC+0Ch], rax
0x180016937  lea     rcx, [rsp+0F0h+var_C0]
0x18001693c  mov     qword ptr [rbp+37h+var_9C+4], r13
0x180016940  mov     dword ptr [rbp+37h+var_AC+4], r13d
0x180016944  mov     dword ptr [rbp+37h+var_BC+8], r8d
0x180016948  call    cs:__imp_EACreateAggregateEvent
0x18001694f  nop     dword ptr [rax+rax+00h]
0x180016954  mov     ebx, eax
0x180016956  test    eax, eax
0x180016958  jnz     loc_180016ADE
0x18001695e  lea     rax, [rbp+37h+var_60]
0x180016962  mov     qword ptr [rbp+37h+var_AC+0Ch], r13
0x180016966  mov     rdx, r15
0x180016969  mov     qword ptr [rbp+37h+var_BC+0Ch], rax
0x18001696d  lea     rcx, [rsp+0F0h+var_C0]
0x180016972  mov     qword ptr [rbp+37h+var_9C+4], rsi
0x180016976  mov     dword ptr [rbp+37h+var_AC+4], r13d
0x18001697a  mov     dword ptr [rbp+37h+var_BC+8], edi
0x18001697d  call    cs:__imp_EACreateAggregateEvent
0x180016984  nop     dword ptr [rax+rax+00h]
0x180016989  mov     ebx, eax
0x18001698b  test    eax, eax
0x18001698d  jz      loc_1800168B5
0x180016993  mov     rcx, cs:WPP_GLOBAL_Control
0x18001699a  lea     rax, WPP_GLOBAL_Control
0x1800169a1  cmp     rcx, rax
0x1800169a4  jz      loc_1800168B5
0x1800169aa  test    byte ptr [rcx+1Ch], 1
0x1800169ae  jz      loc_1800168B5
0x1800169b4  mov     edx, 0Ch
0x1800169b9  jmp     loc_180016B2C
0x1800169be  mov     ecx, r13d
0x1800169c1  lea     r9, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x1800169c8  cmp     ecx, 5
0x1800169cb  jnb     loc_180016AC6
0x1800169d1  mov     eax, ecx
0x1800169d3  imul    rax, 1Ch
0x1800169d7  cmp     dword ptr [rax+r9+4], 1006h
0x1800169e0  jz      short loc_1800169E6
0x1800169e2  inc     ecx
0x1800169e4  jmp     short loc_1800169C8
0x1800169e6  mov     rax, [rax+r9+14h]
0x1800169eb  test    edx, edx
0x1800169ed  jz      short loc_1800169FA
0x1800169ef  mov     ecx, r8d
0x1800169f2  inc     r8d
0x1800169f5  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x1800169fa  test    r10b, r10b
0x1800169fd  jns     short loc_180016A08
0x1800169ff  mov     ecx, edi
0x180016a01  inc     edi
0x180016a03  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x180016a08  cmp     r8d, edi
0x180016a0b  movzx   r11d, r11b
0x180016a0f  mov     eax, 1
0x180016a14  cmovnz  r11d, eax
0x180016a18  jmp     loc_18001683F
0x180016a1d  mov     ecx, r13d
0x180016a20  cmp     ecx, 5
0x180016a23  jnb     loc_180016AC6
0x180016a29  mov     eax, ecx
0x180016a2b  imul    rax, 1Ch
0x180016a2f  cmp     dword ptr [rax+r9+4], 101Dh
0x180016a38  jz      short loc_180016A3E
0x180016a3a  inc     ecx
0x180016a3c  jmp     short loc_180016A20
0x180016a3e  mov     rax, [rax+r9+14h]
0x180016a43  test    edx, edx
0x180016a45  jz      short loc_180016A52
0x180016a47  mov     ecx, r8d
0x180016a4a  inc     r8d
0x180016a4d  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x180016a52  bt      r10d, 0Ch
0x180016a57  jb      short loc_180016AD0
0x180016a59  cmp     r8d, edi
0x180016a5c  movzx   r11d, r11b
0x180016a60  mov     ecx, 1
0x180016a65  cmovnz  r11d, ecx
0x180016a69  jmp     loc_180016864
0x180016a6e  test    r10b, 4
0x180016a72  jz      loc_180016823
0x180016a78  jmp     loc_1800167C1
0x180016a7d  mov     ecx, r13d
0x180016a80  cmp     ecx, 5
0x180016a83  jnb     short loc_180016AC6
0x180016a85  mov     eax, ecx
0x180016a87  imul    rax, 1Ch
0x180016a8b  cmp     dword ptr [rax+r9+4], 1011h
0x180016a94  jz      short loc_180016A9A
0x180016a96  inc     ecx
0x180016a98  jmp     short loc_180016A80
0x180016a9a  mov     rax, [rax+r9+14h]
0x180016a9f  mov     ecx, r8d
0x180016aa2  inc     r8d
0x180016aa5  mov     qword ptr [rbp+rcx*8+37h+var_88], rax
0x180016aaa  mov     ecx, edi
0x180016aac  inc     edi
0x180016aae  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x180016ab3  jmp     loc_18001684A
0x180016ab8  mov     ecx, edi
0x180016aba  inc     edi
0x180016abc  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x180016ac1  jmp     loc_18001691F
0x180016ac6  mov     ebx, 490h
0x180016acb  jmp     loc_1800168B5
0x180016ad0  mov     ecx, edi
0x180016ad2  inc     edi
0x180016ad4  mov     qword ptr [rbp+rcx*8+37h+var_60], rax
0x180016ad9  jmp     loc_180016A59
0x180016ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ae5  lea     rax, WPP_GLOBAL_Control
0x180016aec  cmp     rcx, rax
0x180016aef  jz      loc_1800168B5
0x180016af5  test    byte ptr [rcx+1Ch], 1
0x180016af9  jz      loc_1800168B5
0x180016aff  mov     edx, 0Bh
0x180016b04  jmp     short loc_180016B2C
0x180016b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b0d  lea     rax, WPP_GLOBAL_Control
0x180016b14  cmp     rcx, rax
0x180016b17  jz      loc_1800168B5
0x180016b1d  test    byte ptr [rcx+1Ch], 1
0x180016b21  jz      loc_1800168B5
0x180016b27  mov     edx, 0Dh
0x180016b2c  mov     rcx, [rcx+10h]
0x180016b30  lea     r8, WPP_029c709143543b8b7778781675a35e95_Traceguids
0x180016b37  mov     r9, r12
0x180016b3a  mov     [rsp+0F0h+var_D0], ebx
0x180016b3e  call    WPP_SF_Sd
0x180016b43  jmp     loc_1800168B5
```
