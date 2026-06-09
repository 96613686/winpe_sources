# CopyTlsParameters(_TLS_PARAMETERS *,ulong,ulong,uchar,_TLS_PARAMETERS * *,ulong *)

- ea: `0x180011f40`
- end: `0x18001266e`
- name: `?CopyTlsParameters@@YAJPEAU_TLS_PARAMETERS@@KKEPEAPEAU1@PEAK@Z`
- size: `1838`
- prototype: `int(struct _TLS_PARAMETERS *, unsigned int, unsigned int, unsigned __int8, struct _TLS_PARAMETERS **, unsigned int *)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800112c0`
- `0x180011e0c`
- `0x18002adf4`
- `0x18005cf90`

## callees

- `0x180011f40`
- `0x180012680`
- `0x180012874`
- `0x1800129a0`
- `0x180014240`
- `0x180021e64`
- `0x180021eb0`
- `0x1800597b0`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001248f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800124a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800124fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001248f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800124a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800124fa`

## pseudocode

```c
__int64 __fastcall CopyTlsParameters(
        struct _TLS_PARAMETERS *a1,
        unsigned int a2,
        int a3,
        unsigned __int8 a4,
        struct _TLS_PARAMETERS **a5,
        unsigned int *a6)
{
  int v6; // r15d
  unsigned int *v7; // r12
  unsigned int v8; // edi
  struct _TLS_PARAMETERS *v9; // rsi
  unsigned int v10; // eax
  char *v11; // rax
  char *v12; // r13
  unsigned int i; // ebx
  __int64 v14; // rdx
  __int128 v15; // xmm1
  int v16; // ecx
  int v17; // eax
  unsigned int v18; // r14d
  unsigned int v19; // eax
  HLOCAL v20; // rax
  unsigned int j; // r12d
  unsigned __int8 v22; // r9
  __int64 v23; // r15
  __int64 v24; // rsi
  int v25; // r13d
  __int64 v26; // rax
  struct _UNICODE_STRING *v27; // r15
  __int128 *v28; // rcx
  unsigned int v29; // ebx
  unsigned __int64 v30; // rcx
  int v31; // eax
  char *v33; // r9
  __int64 v34; // rdx
  __int64 (__fastcall *v35)(_QWORD, __int64, __int128 *, __int64); // rax
  unsigned int v36; // eax
  __int64 v37; // rax
  WCHAR *v38; // rax
  unsigned int Length; // edx
  __int64 v40; // r13
  unsigned int v41; // eax
  unsigned int v42; // ecx
  unsigned int v43; // esi
  void *v44; // rax
  unsigned int v45; // eax
  unsigned int v46; // esi
  __int64 v47; // rcx
  unsigned int v48; // eax
  void *v49; // rax
  unsigned int k; // r15d
  __int64 v51; // rcx
  unsigned int v52; // eax
  PWSTR Buffer; // rcx
  unsigned int v56; // [rsp+40h] [rbp-A1h]
  char *v57; // [rsp+48h] [rbp-99h]
  __int64 v58; // [rsp+50h] [rbp-91h]
  struct _TLS_PARAMETERS *v59; // [rsp+58h] [rbp-89h]
  __int128 v60; // [rsp+60h] [rbp-81h] BYREF
  __int64 v61; // [rsp+70h] [rbp-71h]
  unsigned int *v62; // [rsp+78h] [rbp-69h]
  struct _TLS_PARAMETERS **v63; // [rsp+80h] [rbp-61h]
  __int128 v64; // [rsp+88h] [rbp-59h] BYREF
  __int128 v65; // [rsp+98h] [rbp-49h]
  __int64 v66; // [rsp+A8h] [rbp-39h]
  __int128 v67; // [rsp+B0h] [rbp-31h] BYREF
  __int128 v68; // [rsp+C0h] [rbp-21h]
  __int128 v69; // [rsp+D0h] [rbp-11h]

  v6 = a3;
  v7 = a6;
  v8 = a2;
  v63 = a5;
  v9 = a1;
  v62 = a6;
  v59 = a1;
  if ( !a2 )
    return 0;
  if ( !a5 || !a6 || !a1 && !a3 || a2 > 0x10 )
  {
    v29 = -2146892963;
    goto LABEL_60;
  }
  v10 = 40 * a2;
  if ( LsaTable )
    v11 = (char *)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(v10);
  else
    v11 = (char *)LocalAlloc(0x40u, v10);
  v57 = v11;
  v12 = v11;
  if ( !v11 )
  {
    v29 = -2146893056;
    goto LABEL_60;
  }
  for ( i = 0; ; ++i )
  {
    v56 = i;
    if ( i >= v8 )
    {
      v7 = v62;
      v29 = 0;
      goto LABEL_42;
    }
    v66 = 0;
    v64 = 0;
    v65 = 0;
    v14 = 40LL * i;
    v58 = v14;
    if ( a4 )
    {
      if ( v6 )
      {
        v34 = 24;
        v33 = (char *)(v6 + 24 * i);
      }
      else
      {
        v33 = (char *)v9 + v14;
        v34 = 40;
      }
      v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, char *))(LsaTable + 80))(0, v34, &v64, v33);
      if ( v29 )
        goto LABEL_59;
      i = v56;
      v14 = v58;
    }
    else
    {
      v15 = *(_OWORD *)((char *)v9 + v14 + 16);
      v64 = *(_OWORD *)((char *)v9 + v14);
      v66 = *(_QWORD *)((char *)v9 + v14 + 32);
      v65 = v15;
    }
    if ( (_DWORD)v64 )
    {
      if ( (unsigned int)v64 > 0x10 )
        goto LABEL_116;
      v44 = SPExternalAlloc((unsigned int)(16 * v64));
      v14 = v58;
      *(_QWORD *)&v12[v58 + 8] = v44;
      if ( !v44 )
      {
        v29 = -2146893056;
        goto LABEL_59;
      }
      v45 = v64;
      v46 = 0;
      *(_DWORD *)&v12[v58] = v64;
      while ( v46 < v45 )
      {
        v47 = 16LL * v46;
        if ( v6 )
          v48 = Wow64CopyUnicodeString(
                  DWORD1(v64) + 8 * v46,
                  (struct _UNICODE_STRING *)(v47 + *(_QWORD *)&v12[v14 + 8]));
        else
          v48 = CopyUnicodeString(
                  a4,
                  (struct _UNICODE_STRING *)(v47 + *((_QWORD *)&v64 + 1)),
                  (struct _UNICODE_STRING *)(v47 + *(_QWORD *)&v12[v14 + 8]));
        v29 = v48;
        if ( v48 )
          goto LABEL_59;
        v45 = v64;
        ++v46;
        v14 = v58;
      }
      i = v56;
      v9 = v59;
    }
    v16 = DWORD1(v65);
    if ( v6 )
    {
      v17 = DWORD2(v64);
      v18 = HIDWORD(v64);
    }
    else
    {
      v17 = v65;
      v18 = DWORD1(v65);
    }
    *(_DWORD *)&v12[v14 + 16] = v17;
    if ( v18 )
      break;
LABEL_38:
    if ( !v6 )
      v16 = v66;
    *(_DWORD *)&v12[v14 + 32] = v16;
  }
  if ( v18 > 0x10 )
  {
LABEL_116:
    v29 = -2146892963;
    goto LABEL_59;
  }
  v19 = 48 * v18;
  if ( LsaTable )
    v20 = (HLOCAL)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(v19);
  else
    v20 = LocalAlloc(0x40u, v19);
  v14 = v58;
  *(_QWORD *)&v12[v58 + 24] = v20;
  if ( !v20 )
  {
    v29 = -2146893056;
    goto LABEL_59;
  }
  *(_DWORD *)&v12[v58 + 20] = v18;
  for ( j = 0; ; ++j )
  {
    if ( j >= v18 )
    {
      v16 = DWORD1(v65);
      i = v56;
      v9 = v59;
      goto LABEL_38;
    }
    v22 = a4;
    v23 = *(_QWORD *)&v12[v14 + 24];
    v67 = 0;
    v68 = 0;
    v24 = 48LL * j;
    v69 = 0;
    if ( a4 )
    {
      v35 = *(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, __int64))(LsaTable + 80);
      if ( a3 )
      {
        v25 = 28 * j;
        v36 = v35(0, 28, &v67, 28 * j + (unsigned int)v65);
      }
      else
      {
        v36 = v35(0, 48, &v67, v24 + *((_QWORD *)&v65 + 1));
        v25 = 28 * j;
      }
      v29 = v36;
      if ( v36 )
        goto LABEL_58;
      v22 = a4;
    }
    else
    {
      v25 = 28 * j;
      v26 = *(_QWORD *)((char *)v59 + v14 + 24);
      v67 = *(_OWORD *)(v26 + 48LL * j);
      v68 = *(_OWORD *)(v26 + v24 + 16);
      v69 = *(_OWORD *)(v26 + v24 + 32);
    }
    v61 = v23 + v24;
    v27 = (struct _UNICODE_STRING *)(v23 + v24 + 8);
    if ( a3 )
    {
      v29 = Wow64CopyUnicodeString(v25 + (int)v65 + 4, v27);
      goto LABEL_69;
    }
    v60 = 0;
    v28 = (__int128 *)(v24 + *((_QWORD *)&v65 + 1) + 8LL);
    if ( !v28 || !v27 )
    {
      v29 = -2146892963;
      goto LABEL_69;
    }
    if ( v22 )
    {
      v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, __int64))(LsaTable + 80))(
              0,
              16,
              &v60,
              v24 + *((_QWORD *)&v65 + 1) + 8LL);
      if ( v29 )
        goto LABEL_111;
    }
    else
    {
      v29 = 0;
      v60 = *v28;
    }
    v30 = (unsigned __int64)v60 >> 16;
    if ( WORD1(v60)
      && (_WORD)v60
      && *((_QWORD *)&v60 + 1)
      && (((unsigned __int16)v60 | WORD1(v60)) & 1) == 0
      && (unsigned __int16)v60 <= WORD1(v60)
      && WORD1(v60) != 0xFFFF )
    {
      v37 = LsaTable;
      v27->Length = v60;
      v27->MaximumLength = v30;
      if ( v37 )
        v38 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(v37 + 40))((unsigned __int16)v30);
      else
        v38 = (WCHAR *)LocalAlloc(0x40u, (unsigned __int16)v30);
      v27->Buffer = v38;
      if ( !v38 )
      {
        v29 = -2146893056;
        goto LABEL_111;
      }
      if ( a4 )
      {
        v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, WCHAR *, _QWORD))(LsaTable + 80))(
                0,
                WORD1(v60),
                v38,
                *((_QWORD *)&v60 + 1));
        if ( v29 )
          goto LABEL_111;
      }
      else
      {
        memcpy_0(v38, *((const void **)&v60 + 1), v27->MaximumLength);
      }
      Length = v27->Length;
      if ( v27->Buffer[((unsigned __int64)v27->Length >> 1) - 1] )
        goto LABEL_69;
      if ( Length > 2 )
      {
        v27->Length = Length - 2;
        goto LABEL_69;
      }
    }
    v29 = -2146892963;
LABEL_111:
    Buffer = v27->Buffer;
    if ( Buffer )
    {
      SPExternalFree(Buffer);
      v27->Buffer = 0;
    }
    *(_DWORD *)&v27->Length = 0;
LABEL_69:
    if ( v29 )
      goto LABEL_58;
    v6 = a3;
    v40 = v61;
    if ( a3 )
    {
      v41 = DWORD2(v68);
      *(_DWORD *)(v61 + 44) = DWORD2(v68);
      v42 = DWORD1(v68);
    }
    else
    {
      v41 = HIDWORD(v69);
      *(_DWORD *)(v61 + 44) = HIDWORD(v69);
      v42 = DWORD2(v69);
    }
    *(_DWORD *)(v40 + 40) = v42;
    *(_DWORD *)v40 = v67;
    if ( v41 && v42 > v41 )
    {
LABEL_84:
      v29 = -2146892963;
      goto LABEL_58;
    }
    v43 = HIDWORD(v67);
    if ( !a3 )
      v43 = DWORD2(v68);
    if ( v43 )
      break;
LABEL_76:
    v12 = v57;
    v14 = v58;
  }
  if ( v43 > 0x10 )
    goto LABEL_84;
  v49 = SPExternalAlloc(16 * v43);
  *(_QWORD *)(v40 + 32) = v49;
  if ( v49 )
  {
    *(_DWORD *)(v40 + 24) = v43;
    for ( k = 0; k < v43; ++k )
    {
      v51 = 16LL * k;
      if ( a3 )
        v52 = Wow64CopyUnicodeString((unsigned int)v68 + 8 * k, (struct _UNICODE_STRING *)(v51 + *(_QWORD *)(v40 + 32)));
      else
        v52 = CopyUnicodeString(
                a4,
                (struct _UNICODE_STRING *)(v51 + v69),
                (struct _UNICODE_STRING *)(v51 + *(_QWORD *)(v40 + 32)));
      v29 = v52;
      if ( v52 )
        goto LABEL_58;
    }
    v6 = a3;
    goto LABEL_76;
  }
  v29 = -2146893056;
LABEL_58:
  v12 = v57;
LABEL_59:
  FreeTlsParameters(v12, v8);
  v7 = v62;
LABEL_60:
  v8 = 0;
  v12 = 0;
LABEL_42:
  *v63 = (struct _TLS_PARAMETERS *)v12;
  *v7 = v8;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (v31 = *((_DWORD *)WPP_GLOBAL_Control + 7), (v31 & 1) != 0) && v29 || (v31 & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids, v29, v29);
  }
  return v29;
}

```

## disassembly

```asm
0x180011f40  mov     r11, rsp
0x180011f43  push    rbp
0x180011f44  push    rsi
0x180011f45  push    rdi
0x180011f46  push    r12
0x180011f48  push    r14
0x180011f4a  push    r15
0x180011f4c  lea     rbp, [r11-4Fh]
0x180011f50  sub     rsp, 0F8h
0x180011f57  mov     rax, cs:__security_cookie
0x180011f5e  xor     rax, rsp
0x180011f61  mov     [rbp+47h+var_48], rax
0x180011f65  mov     r14, [rbp+47h+arg_20]
0x180011f69  mov     r15d, r8d
0x180011f6c  mov     r12, [rbp+47h+arg_28]
0x180011f70  mov     edi, edx
0x180011f72  mov     [rbp+47h+var_A8], r14
0x180011f76  mov     rsi, rcx
0x180011f79  mov     [rbp+47h+var_B0], r12
0x180011f7d  mov     byte ptr [rsp+120h+var_F0], r9b
0x180011f82  mov     [rsp+34h], r8d
0x180011f87  mov     qword ptr [rsp+120h+var_D0], rcx
0x180011f8c  test    edx, edx
0x180011f8e  jz      loc_180012305
0x180011f94  mov     [r11-38h], rbx
0x180011f98  mov     [r11-40h], r13
0x180011f9c  test    r14, r14
0x180011f9f  jz      loc_18001250E
0x180011fa5  test    r12, r12
0x180011fa8  jz      loc_18001250E
0x180011fae  test    rcx, rcx
0x180011fb1  jz      loc_180012505
0x180011fb7  cmp     edi, 10h
0x180011fba  ja      loc_18001250E
0x180011fc0  lea     eax, [rdx+rdx*4]
0x180011fc3  mov     rdx, cs:LsaTable
0x180011fca  shl     eax, 3
0x180011fcd  test    rdx, rdx
0x180011fd0  jz      loc_180012488
0x180011fd6  mov     ecx, eax
0x180011fd8  mov     rax, [rdx+28h]
0x180011fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fe1  mov     [rsp+120h+var_E0], rax
0x180011fe6  mov     r13, rax
0x180011fe9  test    rax, rax
0x180011fec  jz      loc_1800125C3
0x180011ff2  xor     r8d, r8d
0x180011ff5  mov     ebx, r8d
0x180011ff8  mov     dword ptr [rsp+120h+var_E8], ebx
0x180011ffc  cmp     ebx, edi
0x180011ffe  jnb     loc_1800121DA
0x180012004  movzx   r12d, byte ptr [rsp+120h+var_F0]
0x18001200a  xor     eax, eax
0x18001200c  mov     [rbp+47h+var_80], rax
0x180012010  xorps   xmm0, xmm0
0x180012013  mov     eax, ebx
0x180012015  movups  [rbp+47h+var_A0], xmm0
0x180012019  movups  [rbp+47h+var_90], xmm0
0x18001201d  lea     rcx, [rax+rax*4]
0x180012021  lea     rdx, ds:0[rcx*8]
0x180012029  mov     [rsp+120h+var_D8], rdx
0x18001202e  test    r12b, r12b
0x180012031  jnz     loc_180012241
0x180012037  movups  xmm0, xmmword ptr [rdx+rsi]
0x18001203b  movups  xmm1, xmmword ptr [rdx+rsi+10h]
0x180012040  movups  [rbp+47h+var_A0], xmm0
0x180012044  movsd   xmm0, qword ptr [rdx+rsi+20h]
0x18001204a  movsd   [rbp+47h+var_80], xmm0
0x18001204f  movups  [rbp+47h+var_90], xmm1
0x180012053  mov     ecx, dword ptr [rbp+47h+var_A0]
0x180012056  test    ecx, ecx
0x180012058  jnz     loc_1800124AD
0x18001205e  mov     ecx, dword ptr [rbp+47h+var_90+4]
0x180012061  test    r15d, r15d
0x180012064  jnz     loc_1800122F9
0x18001206a  mov     eax, dword ptr [rbp+47h+var_90]
0x18001206d  mov     r14d, ecx
0x180012070  mov     [rdx+r13+10h], eax
0x180012075  test    r14d, r14d
0x180012078  jz      loc_1800121C7
0x18001207e  cmp     r14d, 10h
0x180012082  ja      loc_180012627
0x180012088  mov     rdx, cs:LsaTable
0x18001208f  lea     eax, [r14+r14*2]
0x180012093  shl     eax, 4
0x180012096  test    rdx, rdx
0x180012099  jz      loc_1800124F3
0x18001209f  mov     ecx, eax
0x1800120a1  mov     rax, [rdx+28h]
0x1800120a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120aa  mov     rdx, [rsp+120h+var_D8]
0x1800120af  mov     [rdx+r13+18h], rax
0x1800120b4  test    rax, rax
0x1800120b7  jz      loc_18001263B
0x1800120bd  xor     r8d, r8d
0x1800120c0  mov     [rdx+r13+14h], r14d
0x1800120c5  mov     r12d, r8d
0x1800120c8  cmp     r12d, r14d
0x1800120cb  jnb     loc_1800121BB
0x1800120d1  movzx   r9d, byte ptr [rsp+120h+var_F0]
0x1800120d7  xorps   xmm0, xmm0
0x1800120da  mov     r15, [rdx+r13+18h]
0x1800120df  mov     eax, r12d
0x1800120e2  movups  [rbp+47h+var_78], xmm0
0x1800120e6  movups  [rbp+47h+var_68], xmm0
0x1800120ea  lea     rsi, [rax+rax*2]
0x1800120ee  shl     rsi, 4
0x1800120f2  movups  [rbp+47h+var_58], xmm0
0x1800120f6  test    r9b, r9b
0x1800120f9  jnz     loc_180012284
0x1800120ff  mov     rax, qword ptr [rsp+120h+var_D0]
0x180012104  imul    r13d, r12d, 1Ch
0x180012108  mov     rax, [rdx+rax+18h]
0x18001210d  movups  xmm0, xmmword ptr [rax+rsi]
0x180012111  movups  [rbp+47h+var_78], xmm0
0x180012115  movups  xmm1, xmmword ptr [rax+rsi+10h]
0x18001211a  movups  [rbp+47h+var_68], xmm1
0x18001211e  movups  xmm0, xmmword ptr [rax+rsi+20h]
0x180012123  movups  [rbp+47h+var_58], xmm0
0x180012127  cmp     dword ptr [rsp+34h], 0
0x18001212c  lea     rax, [r15+rsi]
0x180012130  mov     [rbp+47h+var_B8], rax
0x180012134  lea     r15, [rax+8]
0x180012138  jnz     loc_180012433
0x18001213e  mov     rcx, qword ptr [rbp+47h+var_90+8]
0x180012142  xorps   xmm0, xmm0
0x180012145  add     rcx, 8
0x180012149  movups  [rsp+120h+var_D0+8], xmm0
0x18001214e  add     rcx, rsi
0x180012151  jz      loc_180012602
0x180012157  test    r15, r15
0x18001215a  jz      loc_180012602
0x180012160  test    r9b, r9b
0x180012163  jnz     loc_1800122C8
0x180012169  movups  xmm0, xmmword ptr [rcx]
0x18001216c  mov     ebx, r8d
0x18001216f  movups  [rsp+120h+var_D0+8], xmm0
0x180012174  mov     rdx, qword ptr [rsp+120h+var_D0+8]
0x180012179  mov     rcx, rdx
0x18001217c  shr     rcx, 10h
0x180012180  test    cx, cx
0x180012183  jz      short loc_1800121B1
0x180012185  test    dx, dx
0x180012188  jz      short loc_1800121B1
0x18001218a  cmp     [rbp+47h+Src], 0
0x18001218f  jz      short loc_1800121B1
0x180012191  movzx   eax, cx
0x180012194  or      ax, dx
0x180012197  bt      ax, r8w
0x18001219c  jb      short loc_1800121B1
0x18001219e  cmp     dx, cx
0x1800121a1  ja      short loc_1800121B1
0x1800121a3  mov     eax, 0FFFEh
0x1800121a8  cmp     cx, ax
0x1800121ab  jbe     loc_18001232D
0x1800121b1  mov     ebx, 8009035Dh
0x1800121b6  jmp     loc_1800125E5
0x1800121bb  mov     ecx, dword ptr [rbp+47h+var_90+4]
0x1800121be  mov     ebx, dword ptr [rsp+120h+var_E8]
0x1800121c2  mov     rsi, qword ptr [rsp+120h+var_D0]
0x1800121c7  test    r15d, r15d
0x1800121ca  cmovz   ecx, dword ptr [rbp+47h+var_80]
0x1800121ce  inc     ebx
0x1800121d0  mov     [rdx+r13+20h], ecx
0x1800121d5  jmp     loc_180011FF8
0x1800121da  mov     r12, [rbp+47h+var_B0]
0x1800121de  mov     ebx, r8d
0x1800121e1  mov     r14, [rbp+47h+var_A8]
0x1800121e5  mov     [r14], r13
0x1800121e8  lea     rax, WPP_GLOBAL_Control
0x1800121ef  mov     [r12], edi
0x1800121f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121fa  mov     r13, [rsp+120h+var_38]
0x180012202  cmp     rcx, rax
0x180012205  jz      short loc_18001221A
0x180012207  mov     eax, [rcx+1Ch]
0x18001220a  test    al, 1
0x18001220c  jnz     loc_180012645
0x180012212  test    al, 4
0x180012214  jnz     loc_18001264D
0x18001221a  mov     eax, ebx
0x18001221c  mov     rbx, [rsp+0F0h]
0x180012224  mov     rcx, [rbp+47h+var_48]
0x180012228  xor     rcx, rsp; StackCookie
0x18001222b  call    __security_check_cookie
0x180012230  add     rsp, 0F8h
0x180012237  pop     r15
0x180012239  pop     r14
0x18001223b  pop     r12
0x18001223d  pop     rdi
0x18001223e  pop     rsi
0x18001223f  pop     rbp
0x180012240  retn
0x180012241  xor     ecx, ecx
0x180012243  lea     r8, [rbp+47h+var_A0]
0x180012247  test    r15d, r15d
0x18001224a  jnz     loc_18001244B
0x180012250  lea     r9, [rsi+rdx]
0x180012254  mov     edx, 28h ; '('
0x180012259  mov     rax, cs:LsaTable
0x180012260  mov     rax, [rax+50h]
0x180012264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012269  mov     ebx, eax
0x18001226b  test    eax, eax
0x18001226d  jnz     loc_180012311
0x180012273  mov     ebx, dword ptr [rsp+120h+var_E8]
0x180012277  xor     r8d, r8d
0x18001227a  mov     rdx, [rsp+120h+var_D8]
0x18001227f  jmp     loc_180012053
0x180012284  mov     rax, cs:LsaTable
0x18001228b  lea     r8, [rbp+47h+var_78]
0x18001228f  xor     ecx, ecx
0x180012291  mov     rax, [rax+50h]
0x180012295  cmp     [rsp+34h], ecx
0x180012299  jnz     loc_18001245C
0x18001229f  mov     r9, qword ptr [rbp+47h+var_90+8]
0x1800122a3  mov     edx, 30h ; '0'
0x1800122a8  add     r9, rsi
0x1800122ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b0  imul    r13d, r12d, 1Ch
0x1800122b4  mov     ebx, eax
0x1800122b6  test    eax, eax
0x1800122b8  jnz     short loc_18001230C
0x1800122ba  movzx   r9d, byte ptr [rsp+120h+var_F0]
0x1800122c0  xor     r8d, r8d
0x1800122c3  jmp     loc_180012127
0x1800122c8  mov     rax, cs:LsaTable
0x1800122cf  lea     r8, [rsp+120h+var_D0+8]
0x1800122d4  mov     r9, rcx
0x1800122d7  mov     edx, 10h
0x1800122dc  xor     ecx, ecx
0x1800122de  mov     rax, [rax+50h]
0x1800122e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122e7  mov     ebx, eax
0x1800122e9  test    eax, eax
0x1800122eb  jnz     loc_1800125E5
0x1800122f1  xor     r8d, r8d
0x1800122f4  jmp     loc_180012174
0x1800122f9  mov     eax, dword ptr [rbp+47h+var_A0+8]
0x1800122fc  mov     r14d, dword ptr [rbp+47h+var_A0+0Ch]
0x180012300  jmp     loc_180012070
0x180012305  xor     eax, eax
0x180012307  jmp     loc_180012224
0x18001230c  mov     r13, [rsp+120h+var_E0]
0x180012311  xor     r14d, r14d
0x180012314  mov     edx, edi; unsigned int
0x180012316  mov     rcx, r13; hMem
0x180012319  call    ?FreeTlsParameters@@YAXPEAU_TLS_PARAMETERS@@K@Z; FreeTlsParameters(_TLS_PARAMETERS *,ulong)
0x18001231e  mov     r12, [rbp+47h+var_B0]
0x180012322  mov     edi, r14d
0x180012325  mov     r13, r14
0x180012328  jmp     loc_1800121E1
0x18001232d  mov     rax, cs:LsaTable
0x180012334  mov     [r15], dx
0x180012338  mov     [r15+2], cx
0x18001233d  test    rax, rax
0x180012340  jz      loc_18001249A
0x180012346  mov     rax, [rax+28h]
0x18001234a  movzx   ecx, cx
0x18001234d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012352  mov     [r15+8], rax
0x180012356  mov     rcx, rax; void *
0x180012359  test    rax, rax
0x18001235c  jz      loc_1800125E0
0x180012362  cmp     byte ptr [rsp+120h+var_F0], 0
0x180012367  jnz     loc_1800123FB
0x18001236d  movzx   r8d, word ptr [r15+2]; Size
0x180012372  mov     rdx, [rbp+47h+Src]; Src
0x180012376  call    memcpy_0
0x18001237b  movzx   edx, word ptr [r15]
0x18001237f  mov     rax, [r15+8]
0x180012383  mov     ecx, edx
0x180012385  shr     rcx, 1
0x180012388  cmp     word ptr [rax+rcx*2-2], 0
0x18001238e  jnz     short loc_1800123A1
0x180012390  cmp     edx, 2
0x180012393  jbe     loc_1800121B1
0x180012399  sub     dx, 2
0x18001239d  mov     [r15], dx
0x1800123a1  test    ebx, ebx
0x1800123a3  jnz     loc_18001230C
0x1800123a9  mov     r15d, [rsp+34h]
0x1800123ae  mov     r13, [rbp+47h+var_B8]
0x1800123b2  test    r15d, r15d
0x1800123b5  jnz     short loc_180012427
0x1800123b7  mov     eax, dword ptr [rbp+47h+var_58+0Ch]
0x1800123ba  mov     [r13+2Ch], eax
0x1800123be  mov     ecx, dword ptr [rbp+47h+var_58+8]
0x1800123c1  mov     [r13+28h], ecx
0x1800123c5  mov     edx, dword ptr [rbp+47h+var_78]
0x1800123c8  mov     [r13+0], edx
0x1800123cc  test    eax, eax
0x1800123ce  jnz     loc_180012476
0x1800123d4  mov     esi, dword ptr [rbp+47h+var_78+0Ch]
0x1800123d7  test    r15d, r15d
0x1800123da  cmovz   esi, dword ptr [rbp+47h+var_68+8]
0x1800123de  test    esi, esi
0x1800123e0  jnz     loc_180012558
0x1800123e6  mov     r13, [rsp+120h+var_E0]
0x1800123eb  inc     r12d
  ... truncated ...
```
