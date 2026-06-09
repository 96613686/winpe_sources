# CRowset::CompareDataTypes(ushort,uchar *,uchar *,unsigned __int64,unsigned __int64,ulong,int *)

- ea: `0x383a0c470`
- end: `0x383a0cae1`
- name: `?CompareDataTypes@CRowset@@QEAAJGPEAE0_K1KPEAH@Z`
- size: `1649`
- prototype: `__int64 __usercall@<rax>(CRowset *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int8 *@<r8>, unsigned __int8 *@<r9>, unsigned __int64 cchCount1, unsigned __int64, unsigned int, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x383a0b0e0`
- `0x383a0baf0`
- `0x383a0cbd0`

## callees

- `0x3838434c0`
- `0x38385b340`
- `0x3839976c0`
- `0x383a0ac20`
- `0x383a0baf0`
- `0x383a0c380`
- `0x383a0c470`
- `0x383ade2bc`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x383a0c848`
- `KERNEL32!CompareStringA` at `0x383a0c848`
- `KERNEL32!CompareStringW` at `0x383a0c895`
- `KERNEL32!CompareStringW` at `0x383a0c895`

## pseudocode

```c
__int64 __fastcall CRowset::CompareDataTypes(
        CRowset *this,
        __int16 a2,
        char *a3,
        struct tagTIMESTAMP_STRUCT *lpString2,
        unsigned __int64 cchCount1,
        unsigned __int64 cchCount2,
        unsigned int a7,
        int *a8)
{
  __int16 v8; // bx
  struct tagTIMESTAMP_STRUCT *v9; // rsi
  char *v10; // rdi
  unsigned __int16 v12; // r14
  int v13; // r13d
  SQLSMALLINT year; // ax
  __int16 v15; // cx
  bool v16; // sf
  bool v17; // of
  __int64 v18; // rax
  int v20; // eax
  unsigned __int8 month; // al
  unsigned __int8 v22; // r15
  int v23; // eax
  int v24; // edx
  _BYTE *v25; // rcx
  bool v26; // cf
  DWORD v27; // edx
  int v28; // eax
  DWORD v29; // edx
  bool v30; // cf
  SQLUSMALLINT v31; // dx
  int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // edx
  unsigned int v35; // eax
  unsigned int v36; // ecx
  bool v37; // cf
  int v38; // ecx
  unsigned int v39; // edx
  unsigned int v40; // r8d
  unsigned int v41; // ecx
  unsigned int v42; // edx
  unsigned int v43; // [rsp+80h] [rbp-39h] BYREF
  __int16 v44; // [rsp+84h] [rbp-35h] BYREF
  struct tagTIMESTAMP_STRUCT v45; // [rsp+88h] [rbp-31h] BYREF
  __int16 v46; // [rsp+98h] [rbp-21h]
  char v47; // [rsp+9Ah] [rbp-1Fh]
  struct tagTIMESTAMP_STRUCT v48; // [rsp+A0h] [rbp-19h] BYREF

  v8 = 0;
  v9 = lpString2;
  v10 = a3;
  v12 = 0;
  v44 = 0;
  LOWORD(v43) = 0;
  v13 = 0;
  switch ( a2 )
  {
    case 2:
      year = lpString2->year;
      v15 = *(_WORD *)a3;
      v12 = *(_WORD *)a3 == lpString2->year;
      if ( *(_WORD *)a3 == lpString2->year )
        goto LABEL_78;
      v17 = __OFSUB__(v15, year);
      v16 = (__int16)(v15 - year) < 0;
      goto LABEL_4;
    case 3:
      goto LABEL_14;
    case 4:
      if ( *(float *)a3 == *(float *)&lpString2->year )
        goto LABEL_49;
      v12 = 0;
      v8 = *(float *)&lpString2->year > *(float *)a3;
      goto LABEL_78;
    case 5:
      if ( *(double *)a3 == *(double *)&lpString2->year )
        goto LABEL_49;
      v12 = 0;
      v8 = *(double *)&lpString2->year > *(double *)a3;
      goto LABEL_78;
    case 6:
      if ( cchCount2 == 8 )
      {
        v18 = *(_QWORD *)&lpString2->year;
        v12 = *(_QWORD *)a3 == *(_QWORD *)&lpString2->year;
        if ( *(_QWORD *)a3 != *(_QWORD *)&lpString2->year )
        {
          v17 = __OFSUB__(*(_DWORD *)a3, (_DWORD)v18);
          v16 = *(_DWORD *)a3 - (int)v18 < 0;
          if ( *(_DWORD *)a3 == (_DWORD)v18 )
            LOBYTE(v8) = *((_DWORD *)a3 + 1) == *(_DWORD *)&lpString2->day;
          else
LABEL_4:
            LOBYTE(v8) = v16 ^ v17;
        }
      }
      else if ( cchCount2 == 4 )
      {
LABEL_14:
        v12 = *(_DWORD *)a3 == *(_DWORD *)&lpString2->year;
        if ( *(_DWORD *)a3 != *(_DWORD *)&lpString2->year )
          LOBYTE(v8) = *(_DWORD *)a3 < *(_DWORD *)&lpString2->year;
      }
      goto LABEL_78;
    case 11:
      v12 = *a3 == LOBYTE(lpString2->year);
      goto LABEL_78;
    case 12:
    case 144:
      return CRowset::CompareSSVariants(this, (struct SSVARIANT *)a3, (struct SSVARIANT *)lpString2, a7, a8);
    case 14:
    case 131:
      LODWORD(lpString2) = LOBYTE(lpString2->year);
      *(_QWORD *)&v48.year = 0;
      v43 = 0;
      *(_QWORD *)&v45.year = 0;
      *(_QWORD *)&v45.minute = 0;
      v46 = 0;
      v47 = 0;
      if ( *a3 == (_BYTE)lpString2 && a3[1] == HIBYTE(v9->year) )
        goto LABEL_26;
      v20 = CDataSource::DataConvert(
              *(CDataSource **)(*((_QWORD *)this + 8) + 832LL),
              0x83u,
              131,
              19,
              (unsigned __int64 *)&v48,
              (VARIANTARG *)a3,
              (char *)&v45,
              0x13u,
              0,
              (unsigned __int8 *)&v43,
              (char)lpString2,
              HIBYTE(v9->year),
              0,
              0xFFFFFFFF,
              0xFFFFFFFF,
              0x40u);
      v13 = v20;
      if ( v20 >= 0 )
      {
        v10 = (char *)&v45;
      }
      else
      {
        if ( v20 != -2147217833
          || (v13 = CDataSource::DataConvert(
                      *(CDataSource **)(*((_QWORD *)this + 8) + 832LL),
                      0x83u,
                      131,
                      19,
                      (unsigned __int64 *)&v48,
                      (VARIANTARG *)v9,
                      (char *)&v45,
                      0x13u,
                      0,
                      (unsigned __int8 *)&v43,
                      *v10,
                      v10[1],
                      0,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      0x40u),
              v13 < 0) )
        {
LABEL_23:
          *a8 = 0;
          return 1;
        }
        v9 = &v45;
      }
LABEL_26:
      month = v9->month;
      v22 = v10[2];
      if ( v22 != month )
      {
        LOBYTE(v8) = v22 > month;
        goto LABEL_78;
      }
      v23 = memcmp(v10, v9, 0x13u);
      v12 = v23 == 0;
      if ( !v23 )
        goto LABEL_78;
      v24 = 15;
      lpString2 = (struct tagTIMESTAMP_STRUCT *)(-3LL - (_QWORD)v10);
      v25 = v10 + 18;
      break;
    case 17:
      v12 = *a3 == LOBYTE(lpString2->year);
      if ( *a3 == LOBYTE(lpString2->year) )
        goto LABEL_78;
      v26 = (unsigned __int8)*a3 < LOBYTE(lpString2->year);
      goto LABEL_38;
    case 20:
      v12 = *(_QWORD *)a3 == *(_QWORD *)&lpString2->year;
      if ( *(_QWORD *)a3 != *(_QWORD *)&lpString2->year )
        LOBYTE(v8) = *(_QWORD *)a3 < *(_QWORD *)&lpString2->year;
      goto LABEL_78;
    case 72:
      v12 = *(_QWORD *)a3 == *(_QWORD *)&lpString2->year && *((_QWORD *)a3 + 1) == *(_QWORD *)&lpString2->minute;
      goto LABEL_78;
    case 129:
      v27 = 196608;
      if ( (a7 & 0x1000) == 0 )
        v27 = 196609;
      v28 = CompareStringA(0x400u, v27, a3, cchCount1, (PCNZCH)lpString2, cchCount2);
      if ( v28 != 2 )
        goto LABEL_44;
      goto LABEL_49;
    case 130:
    case 141:
      v29 = 196608;
      if ( (a7 & 0x1000) == 0 )
        v29 = 196609;
      v28 = CompareStringW(
              0x400u,
              v29,
              (PCNZWCH)a3,
              (unsigned __int64)(int)cchCount1 >> 1,
              (PCNZWCH)lpString2,
              (unsigned __int64)(int)cchCount2 >> 1);
      if ( v28 == 2 )
      {
LABEL_49:
        v12 = 1;
      }
      else
      {
LABEL_44:
        if ( v28 == 1 )
LABEL_45:
          v8 = 1;
      }
      goto LABEL_78;
    case 133:
      v30 = *(_DWORD *)a3 < *(_DWORD *)&lpString2->year;
      if ( *(_DWORD *)a3 == *(_DWORD *)&lpString2->year
        && (v31 = *((_WORD *)a3 + 2), v30 = v31 < lpString2->day, v31 == lpString2->day) )
      {
        v32 = 0;
      }
      else
      {
        v32 = -v30 - (v30 - 1);
      }
      v12 = v32 == 0;
      if ( v32 )
        LOBYTE(v8) = *((unsigned __int16 *)a3 + 2)
                   + 31 * ((unsigned int)*((unsigned __int16 *)a3 + 1) + 12 * *(__int16 *)a3) < lpString2->day
                                                                                              + 31
                                                                                              * ((unsigned int)lpString2->month
                                                                                               + 12 * lpString2->year);
      goto LABEL_78;
    case 135:
      CompareDBTIMESTAMPS(
        (const struct tagDBTIMESTAMP *)a3,
        (const struct tagDBTIMESTAMP *)lpString2,
        &v44,
        (__int16 *)&v43);
      v12 = v44;
      v8 = v43;
      goto LABEL_78;
    case 145:
      v33 = *((unsigned __int16 *)a3 + 2) + 60 * (*((unsigned __int16 *)a3 + 1) + 60 * *(unsigned __int16 *)a3);
      v34 = lpString2->day + 60 * (lpString2->month + 60 * (unsigned __int16)lpString2->year);
      v26 = v33 < v34;
      if ( v33 == v34 && (v35 = *(_DWORD *)&lpString2->minute, v36 = *((_DWORD *)a3 + 2), v26 = v36 < v35, v36 == v35) )
        v12 = 1;
      else
LABEL_38:
        LOBYTE(v8) = v26;
      goto LABEL_78;
    case 146:
      if ( ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)a3, &v45)
        || ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)v9, &v48) )
      {
        goto LABEL_23;
      }
      v37 = *(_QWORD *)&v45.year < *(_QWORD *)&v48.year;
      if ( *(_QWORD *)&v45.year == *(_QWORD *)&v48.year
        && (v37 = *(_QWORD *)&v45.minute < *(_QWORD *)&v48.minute, *(_QWORD *)&v45.minute == *(_QWORD *)&v48.minute) )
      {
        v38 = 0;
      }
      else
      {
        v38 = -v37 - (v37 - 1);
      }
      v12 = v38 == 0;
      if ( !v38 )
        goto LABEL_78;
      v39 = v45.day + 31 * (v45.month + 12 * v45.year);
      v40 = v48.day + 31 * (v48.month + 12 * v48.year);
      if ( v39 < v40 )
        goto LABEL_45;
      if ( v39 > v40 )
        goto LABEL_78;
      v41 = v45.second + 60 * (v45.minute + 60 * v45.hour);
      v42 = v48.second + 60 * (v48.minute + 60 * v48.hour);
      if ( v41 < v42 )
        goto LABEL_45;
      if ( v41 <= v42 && v45.fraction < v48.fraction )
        v8 = 1;
      goto LABEL_78;
    default:
      v13 = -2147217881;
      goto LABEL_78;
  }
  while ( *v25 == v25[(char *)v9 - v10] )
  {
    --v25;
    --v24;
    if ( (__int64)lpString2 + (__int64)v25 < 0 )
      goto LABEL_33;
  }
  LOBYTE(v8) = (unsigned __int8)v10[v24 + 3] < *((_BYTE *)&v9->month + v24 + 1);
LABEL_33:
  if ( !v22 )
    v8 ^= 1u;
LABEL_78:
  *a8 = CRowset::AnalyzeComparison((CRowset *)v12, v8, a7, (unsigned int)lpString2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x383a0c470  mov     [rsp-8+arg_8], rbx
0x383a0c475  push    rbp
0x383a0c476  push    rsi
0x383a0c477  push    rdi
0x383a0c478  push    r12
0x383a0c47a  push    r13
0x383a0c47c  push    r14
0x383a0c47e  push    r15
0x383a0c480  lea     rbp, [rsp-7]
0x383a0c485  sub     rsp, 0C0h
0x383a0c48c  mov     rax, cs:__security_cookie
0x383a0c493  xor     rax, rsp
0x383a0c496  mov     [rbp+37h+var_40], rax
0x383a0c49a  mov     r12, [rbp+37h+arg_38]
0x383a0c49e  xor     ebx, ebx
0x383a0c4a0  movzx   eax, dx
0x383a0c4a3  mov     edx, [rbp+37h+arg_30]
0x383a0c4a6  add     eax, 0FFFFFFFEh; switch 145 cases
0x383a0c4a9  mov     rsi, r9
0x383a0c4ac  mov     rdi, r8
0x383a0c4af  mov     r15, rcx
0x383a0c4b2  movzx   r14d, bx
0x383a0c4b6  mov     [rbp+37h+var_6C], bx
0x383a0c4ba  mov     word ptr [rbp+37h+var_70], bx
0x383a0c4be  mov     r13d, ebx
0x383a0c4c1  cmp     eax, 90h
0x383a0c4c6  ja      def_383A0C4E9; jumptable 0000000383A0C4E9 default case, cases 7-10,13,15,16,18,19,21-71,73-128,132,134,136-140,142,143
0x383a0c4cc  lea     r8, cs:383800000h
0x383a0c4d3  cdqe
0x383a0c4d5  movzx   eax, ds:(byte_383A0CB2C - 383800000h)[r8+rax]
0x383a0c4de  mov     ecx, ds:(jpt_383A0C4E9 - 383800000h)[r8+rax*4]
0x383a0c4e6  add     rcx, r8
0x383a0c4e9  jmp     rcx; switch jump
0x383a0c4eb  movzx   eax, word ptr [r9]; jumptable 0000000383A0C4E9 case 2
0x383a0c4ef  movzx   ecx, word ptr [rdi]
0x383a0c4f2  mov     r14d, ebx
0x383a0c4f5  cmp     cx, ax
0x383a0c4f8  setz    r14b
0x383a0c4fc  test    r14w, r14w
0x383a0c500  jnz     loc_383A0CAA3
0x383a0c506  cmp     cx, ax
0x383a0c509  setl    bl
0x383a0c50c  jmp     loc_383A0CAA3
0x383a0c511  movss   xmm0, dword ptr [rdi]; jumptable 0000000383A0C4E9 case 4
0x383a0c515  movss   xmm1, dword ptr [r9]
0x383a0c51a  ucomiss xmm0, xmm1
0x383a0c51d  jp      short loc_383A0C525
0x383a0c51f  jz      loc_383A0C8A0
0x383a0c525  comiss  xmm1, xmm0
0x383a0c528  movzx   r14d, bx
0x383a0c52c  jbe     loc_383A0CAA3
0x383a0c532  mov     ebx, 1
0x383a0c537  jmp     loc_383A0CAA3
0x383a0c53c  movsd   xmm0, qword ptr [rdi]; jumptable 0000000383A0C4E9 case 5
0x383a0c540  movsd   xmm1, qword ptr [r9]
0x383a0c545  ucomisd xmm0, xmm1
0x383a0c549  jp      short loc_383A0C551
0x383a0c54b  jz      loc_383A0C8A0
0x383a0c551  comisd  xmm1, xmm0
0x383a0c555  movzx   r14d, bx
0x383a0c559  jbe     loc_383A0CAA3
0x383a0c55f  mov     ebx, 1
0x383a0c564  jmp     loc_383A0CAA3
0x383a0c569  mov     rax, [rbp+37h+arg_28]; jumptable 0000000383A0C4E9 case 6
0x383a0c56d  cmp     rax, 8
0x383a0c571  jnz     short loc_383A0C5A4
0x383a0c573  mov     rax, [r9]
0x383a0c576  mov     ecx, ebx
0x383a0c578  cmp     [rdi], rax
0x383a0c57b  setz    cl
0x383a0c57e  movzx   r14d, cx
0x383a0c582  test    cx, cx
0x383a0c585  jnz     loc_383A0CAA3
0x383a0c58b  mov     ecx, [rdi]
0x383a0c58d  cmp     ecx, eax
0x383a0c58f  jnz     loc_383A0C509
0x383a0c595  mov     eax, [r9+4]
0x383a0c599  cmp     [rdi+4], eax
0x383a0c59c  setz    bl
0x383a0c59f  jmp     loc_383A0CAA3
0x383a0c5a4  cmp     rax, 4
0x383a0c5a8  jnz     loc_383A0CAA3
0x383a0c5ae  mov     ecx, [r9]; jumptable 0000000383A0C4E9 case 3
0x383a0c5b1  mov     edx, [rdi]
0x383a0c5b3  mov     eax, ebx
0x383a0c5b5  cmp     edx, ecx
0x383a0c5b7  setz    al
0x383a0c5ba  movzx   r14d, ax
0x383a0c5be  test    ax, ax
0x383a0c5c1  jnz     loc_383A0CAA3
0x383a0c5c7  cmp     edx, ecx
0x383a0c5c9  setl    bl
0x383a0c5cc  jmp     loc_383A0CAA3
0x383a0c5d1  movzx   eax, byte ptr [r9]; jumptable 0000000383A0C4E9 case 11
0x383a0c5d5  mov     ecx, ebx
0x383a0c5d7  cmp     [rdi], al
0x383a0c5d9  setz    cl
0x383a0c5dc  movzx   r14d, cx
0x383a0c5e0  jmp     loc_383A0CAA3
0x383a0c5e5  mov     r9d, edx; jumptable 0000000383A0C4E9 cases 12,144
0x383a0c5e8  mov     r8, rsi; struct SSVARIANT *
0x383a0c5eb  mov     rcx, r15; this
0x383a0c5ee  mov     rdx, rdi; struct SSVARIANT *
0x383a0c5f1  mov     [rsp+0F0h+lpString2], r12; int *
0x383a0c5f6  call    ?CompareSSVariants@CRowset@@QEAAJPEAUSSVARIANT@@0KPEAH@Z; CRowset::CompareSSVariants(SSVARIANT *,SSVARIANT *,ulong,int *)
0x383a0c5fb  jmp     loc_383A0CABA
0x383a0c600  movzx   r9d, byte ptr [r9]; jumptable 0000000383A0C4E9 cases 14,131
0x383a0c604  xor     eax, eax
0x383a0c606  mov     qword ptr [rbp+37h+var_50.year], rbx
0x383a0c60a  mov     [rbp+37h+var_70], ebx
0x383a0c60d  mov     qword ptr [rbp+37h+var_68.year], rax
0x383a0c611  mov     qword ptr [rbp+37h+var_68.minute], rax
0x383a0c615  mov     [rbp+37h+var_58], ax
0x383a0c619  mov     [rbp+37h+var_56], al
0x383a0c61c  cmp     [rdi], r9b
0x383a0c61f  jnz     short loc_383A0C62E
0x383a0c621  movzx   eax, byte ptr [rsi+1]
0x383a0c625  cmp     [rdi+1], al
0x383a0c628  jz      loc_383A0C747
0x383a0c62e  mov     rax, [r15+40h]
0x383a0c632  mov     [rsp+0F0h+var_78], 40h ; '@'; unsigned int
0x383a0c63a  mov     [rsp+0F0h+CodePage], 0FFFFFFFFh; CodePage
0x383a0c642  mov     rcx, [rax+340h]; this
0x383a0c649  movzx   eax, byte ptr [rsi+1]
0x383a0c64d  mov     [rsp+0F0h+var_88], 0FFFFFFFFh; UINT
0x383a0c655  mov     [rsp+0F0h+var_90], rbx; enum ECONVERSIONERROR *
0x383a0c65a  mov     [rsp+0F0h+var_98], al; char
0x383a0c65e  mov     [rsp+0F0h+var_A0], r9b; char
0x383a0c663  mov     edx, 83h; unsigned __int16
0x383a0c668  lea     rax, [rbp+37h+var_70]
0x383a0c66c  mov     [rsp+0F0h+var_A8], rax; unsigned int *
0x383a0c671  mov     [rsp+0F0h+var_B0], ebx; unsigned int
0x383a0c675  mov     [rsp+0F0h+var_B8], 13h; unsigned __int64
0x383a0c67e  lea     rax, [rbp+37h+var_68]
0x383a0c682  lea     r9d, [rdx-70h]; unsigned __int64
0x383a0c686  mov     r8d, edx; unsigned __int16
0x383a0c689  mov     [rsp+0F0h+var_C0], rax; void *
0x383a0c68e  lea     rax, [rbp+37h+var_50]
0x383a0c692  mov     qword ptr [rsp+0F0h+cchCount2], rdi; void *
0x383a0c697  mov     [rsp+0F0h+lpString2], rax; unsigned __int64 *
0x383a0c69c  call    ?DataConvert@CDataSource@@QEAAJGG_KPEA_KPEAX20KPEAKEEPEAW4ECONVERSIONERROR@@IIK@Z; CDataSource::DataConvert(ushort,ushort,unsigned __int64,unsigned __int64 *,void *,void *,unsigned __int64,ulong,ulong *,uchar,uchar,ECONVERSIONERROR *,uint,uint,ulong)
0x383a0c6a1  mov     r13d, eax
0x383a0c6a4  test    eax, eax
0x383a0c6a6  jns     loc_383A0C743
0x383a0c6ac  cmp     eax, 80040E57h
0x383a0c6b1  jnz     short loc_383A0C72F
0x383a0c6b3  mov     rax, [r15+40h]
0x383a0c6b7  mov     [rsp+0F0h+var_78], 40h ; '@'; unsigned int
0x383a0c6bf  mov     [rsp+0F0h+CodePage], 0FFFFFFFFh; CodePage
0x383a0c6c7  mov     rcx, [rax+340h]; this
0x383a0c6ce  movzx   eax, byte ptr [rdi+1]
0x383a0c6d2  mov     [rsp+0F0h+var_88], 0FFFFFFFFh; UINT
0x383a0c6da  mov     [rsp+0F0h+var_90], rbx; enum ECONVERSIONERROR *
0x383a0c6df  mov     [rsp+0F0h+var_98], al; char
0x383a0c6e3  movzx   eax, byte ptr [rdi]
0x383a0c6e6  mov     [rsp+0F0h+var_A0], al; char
0x383a0c6ea  mov     edx, 83h; unsigned __int16
0x383a0c6ef  lea     rax, [rbp+37h+var_70]
0x383a0c6f3  mov     [rsp+0F0h+var_A8], rax; unsigned int *
0x383a0c6f8  mov     [rsp+0F0h+var_B0], ebx; unsigned int
0x383a0c6fc  mov     [rsp+0F0h+var_B8], 13h; unsigned __int64
0x383a0c705  lea     rax, [rbp+37h+var_68]
0x383a0c709  lea     r9d, [rdx-70h]; unsigned __int64
0x383a0c70d  mov     r8d, edx; unsigned __int16
0x383a0c710  mov     [rsp+0F0h+var_C0], rax; void *
0x383a0c715  lea     rax, [rbp+37h+var_50]
0x383a0c719  mov     qword ptr [rsp+0F0h+cchCount2], rsi; void *
0x383a0c71e  mov     [rsp+0F0h+lpString2], rax; unsigned __int64 *
0x383a0c723  call    ?DataConvert@CDataSource@@QEAAJGG_KPEA_KPEAX20KPEAKEEPEAW4ECONVERSIONERROR@@IIK@Z; CDataSource::DataConvert(ushort,ushort,unsigned __int64,unsigned __int64 *,void *,void *,unsigned __int64,ulong,ulong *,uchar,uchar,ECONVERSIONERROR *,uint,uint,ulong)
0x383a0c728  mov     r13d, eax
0x383a0c72b  test    eax, eax
0x383a0c72d  jns     short loc_383A0C73D
0x383a0c72f  mov     [r12], ebx
0x383a0c733  mov     eax, 1
0x383a0c738  jmp     loc_383A0CABA
0x383a0c73d  lea     rsi, [rbp+37h+var_68]
0x383a0c741  jmp     short loc_383A0C747
0x383a0c743  lea     rdi, [rbp+37h+var_68]
0x383a0c747  movzx   eax, byte ptr [rsi+2]
0x383a0c74b  movzx   r15d, byte ptr [rdi+2]
0x383a0c750  cmp     r15b, al
0x383a0c753  jnz     short loc_383A0C7CD
0x383a0c755  mov     r8d, 13h; Size
0x383a0c75b  mov     rdx, rsi; Buf2
0x383a0c75e  mov     rcx, rdi; Buf1
0x383a0c761  call    memcmp
0x383a0c766  mov     ecx, ebx
0x383a0c768  test    eax, eax
0x383a0c76a  setz    cl
0x383a0c76d  movzx   r14d, cx
0x383a0c771  test    cx, cx
0x383a0c774  jnz     loc_383A0CAA3
0x383a0c77a  mov     r8, rsi
0x383a0c77d  mov     r9, 0FFFFFFFFFFFFFFFDh
0x383a0c784  mov     edx, 0Fh
0x383a0c789  sub     r8, rdi
0x383a0c78c  sub     r9, rdi
0x383a0c78f  lea     rcx, [rdi+12h]
0x383a0c793  movzx   eax, byte ptr [r8+rcx]
0x383a0c798  cmp     [rcx], al
0x383a0c79a  jnz     short loc_383A0C7AC
0x383a0c79c  dec     rcx
0x383a0c79f  dec     edx
0x383a0c7a1  lea     rax, [rcx+r9]
0x383a0c7a5  test    rax, rax
0x383a0c7a8  jns     short loc_383A0C793
0x383a0c7aa  jmp     short loc_383A0C7BB
0x383a0c7ac  movsxd  rcx, edx
0x383a0c7af  movzx   eax, byte ptr [rcx+rsi+3]
0x383a0c7b4  cmp     [rcx+rdi+3], al
0x383a0c7b8  setb    bl
0x383a0c7bb  test    r15b, r15b
0x383a0c7be  jnz     loc_383A0CAA3
0x383a0c7c4  xor     bx, 1
0x383a0c7c8  jmp     loc_383A0CAA3
0x383a0c7cd  setnbe  bl
0x383a0c7d0  jmp     loc_383A0CAA3
0x383a0c7d5  movzx   ecx, byte ptr [r9]; jumptable 0000000383A0C4E9 case 17
0x383a0c7d9  movzx   edx, byte ptr [rdi]
0x383a0c7dc  mov     eax, ebx
0x383a0c7de  cmp     dl, cl
0x383a0c7e0  setz    al
0x383a0c7e3  movzx   r14d, ax
0x383a0c7e7  test    ax, ax
0x383a0c7ea  jnz     loc_383A0CAA3
0x383a0c7f0  cmp     dl, cl
0x383a0c7f2  setb    bl
0x383a0c7f5  jmp     loc_383A0CAA3
0x383a0c7fa  mov     rcx, [r9]; jumptable 0000000383A0C4E9 case 20
0x383a0c7fd  mov     rdx, [rdi]
0x383a0c800  mov     eax, ebx
0x383a0c802  cmp     rdx, rcx
0x383a0c805  setz    al
0x383a0c808  movzx   r14d, ax
0x383a0c80c  test    ax, ax
0x383a0c80f  jnz     loc_383A0CAA3
0x383a0c815  cmp     rdx, rcx
0x383a0c818  setl    bl
0x383a0c81b  jmp     loc_383A0CAA3
0x383a0c820  mov     eax, dword ptr [rbp+37h+arg_28]; jumptable 0000000383A0C4E9 case 129
0x383a0c823  bt      edx, 0Ch
0x383a0c827  mov     r8, rdi; lpString1
0x383a0c82a  mov     [rsp+0F0h+cchCount2], eax; cchCount2
0x383a0c82e  mov     [rsp+0F0h+lpString2], r9; lpString2
0x383a0c833  mov     r9d, dword ptr [rbp+37h+cchCount1]; cchCount1
0x383a0c837  mov     ecx, 400h; Locale
0x383a0c83c  mov     edx, 30000h
0x383a0c841  jb      short loc_383A0C848
0x383a0c843  mov     edx, 30001h; dwCmpFlags
0x383a0c848  call    cs:__imp_CompareStringA
0x383a0c84e  cmp     eax, 2
0x383a0c851  jz      short loc_383A0C8A0
0x383a0c853  cmp     eax, 1
0x383a0c856  jnz     loc_383A0CAA3
0x383a0c85c  mov     ebx, 1
0x383a0c861  jmp     loc_383A0CAA3
0x383a0c866  movsxd  rax, dword ptr [rbp+37h+arg_28]; jumptable 0000000383A0C4E9 cases 130,141
0x383a0c86a  movsxd  r9, dword ptr [rbp+37h+cchCount1]
0x383a0c86e  mov     r8, rdi; lpString1
0x383a0c871  shr     rax, 1
0x383a0c874  shr     r9, 1; cchCount1
0x383a0c877  bt      edx, 0Ch
0x383a0c87b  mov     [rsp+0F0h+cchCount2], eax; cchCount2
0x383a0c87f  mov     [rsp+0F0h+lpString2], rsi; lpString2
0x383a0c884  mov     ecx, 400h; Locale
0x383a0c889  mov     edx, 30000h
0x383a0c88e  jb      short loc_383A0C895
0x383a0c890  mov     edx, 30001h; dwCmpFlags
0x383a0c895  call    cs:__imp_CompareStringW
0x383a0c89b  cmp     eax, 2
0x383a0c89e  jnz     short loc_383A0C853
0x383a0c8a0  mov     r14d, 1
0x383a0c8a6  jmp     loc_383A0CAA3
0x383a0c8ab  mov     edx, [rdi]; jumptable 0000000383A0C4E9 case 133
0x383a0c8ad  cmp     edx, [r9]
0x383a0c8b0  jnz     short loc_383A0C8C1
0x383a0c8b2  movzx   edx, word ptr [rdi+4]
0x383a0c8b6  cmp     dx, [r9+4]
0x383a0c8bb  jnz     short loc_383A0C8C1
0x383a0c8bd  mov     ecx, ebx
0x383a0c8bf  jmp     short loc_383A0C8C6
0x383a0c8c1  sbb     ecx, ecx
0x383a0c8c3  sbb     ecx, 0FFFFFFFFh
0x383a0c8c6  mov     eax, ebx
0x383a0c8c8  test    ecx, ecx
0x383a0c8ca  setz    al
0x383a0c8cd  movzx   r14d, ax
0x383a0c8d1  test    ax, ax
0x383a0c8d4  jnz     loc_383A0CAA3
0x383a0c8da  movsx   eax, word ptr [r9]
0x383a0c8de  lea     ecx, [rax+rax*2]
0x383a0c8e1  movzx   eax, word ptr [r9+2]
0x383a0c8e6  lea     r8d, [rax+rcx*4]
0x383a0c8ea  movzx   eax, word ptr [r9+4]
0x383a0c8ef  imul    r8d, 1Fh
0x383a0c8f3  add     r8d, eax
0x383a0c8f6  movsx   eax, word ptr [rdi]
0x383a0c8f9  lea     ecx, [rax+rax*2]
0x383a0c8fc  movzx   eax, word ptr [rdi+2]
0x383a0c900  lea     edx, [rax+rcx*4]
  ... truncated ...
```
