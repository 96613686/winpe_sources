# RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)

- ea: `0x1400e1000`
- end: `0x1400e19d0`
- name: `??$RtlpxVirtualUnwind@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJK_K0VCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAXPEAU_CONTEXT@@7@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z`
- size: `2512`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400e1d20`

## callees

- `0x14002c6a8`
- `0x1400442ac`
- `0x1400de514`
- `0x1400de58c`
- `0x1400deb54`
- `0x1400df8e4`
- `0x1400e0284`
- `0x1400e0470`
- `0x1400e1000`
- `0x1400fc62c`

## pseudocode

```c
__int64 RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
        __int64 a1,
        __int64 a2,
        _BYTE *a3,
        ...)
{
  __int64 v4; // r10
  _QWORD *v5; // r12
  _QWORD *v6; // rsi
  _QWORD *v7; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned int v10; // esi
  BOOL v11; // r15d
  __int64 v12; // r13
  unsigned int v13; // r12d
  __int16 v14; // ax
  _QWORD *v15; // r12
  __int64 v16; // rax
  __int64 Context; // rax
  int v18; // r8d
  _BYTE *i; // rcx
  char v20; // dl
  int v21; // r9d
  char v22; // r8
  bool v23; // zf
  int v24; // ecx
  __int64 v25; // r8
  _QWORD *v26; // r9
  char *v27; // rsi
  char v28; // r15
  char v29; // al
  int v30; // eax
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // rcx
  __int64 v33; // rbx
  _QWORD *v34; // rax
  char v35; // al
  __int64 v36; // rax
  _QWORD **v37; // rbx
  unsigned int v38; // r15d
  _QWORD **v39; // r12
  _QWORD *v40; // rbx
  __int64 v41; // rcx
  char v42; // cl
  int v43; // edx
  _QWORD *v44; // r12
  __int64 v45; // rax
  __int64 v46; // rcx
  _QWORD *v47; // rcx
  _QWORD *v48; // rcx
  unsigned int v49; // r9d
  __int16 v50; // ax
  unsigned int v51; // r11d
  int v52; // r8d
  int v53; // edx
  unsigned int v54; // esi
  unsigned int v55; // r9d
  __int16 v56; // ax
  unsigned int v57; // [rsp+40h] [rbp-98h]
  int v58; // [rsp+40h] [rbp-98h]
  _QWORD v59[4]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v60; // [rsp+90h] [rbp-48h]
  unsigned int *v62; // [rsp+F8h] [rbp+20h] BYREF
  va_list va; // [rsp+F8h] [rbp+20h]
  _QWORD *v64; // [rsp+100h] [rbp+28h]
  _BYTE *v65; // [rsp+108h] [rbp+30h]
  _QWORD *v66; // [rsp+110h] [rbp+38h]
  __int64 *v67; // [rsp+118h] [rbp+40h]
  _QWORD *v68; // [rsp+120h] [rbp+48h]
  __int64 v69; // [rsp+128h] [rbp+50h]
  __int64 v70; // [rsp+130h] [rbp+58h]
  __int64 v71; // [rsp+138h] [rbp+60h]
  va_list va1; // [rsp+140h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v62 = va_arg(va1, unsigned int *);
  v64 = va_arg(va1, _QWORD *);
  v65 = va_arg(va1, _BYTE *);
  v66 = va_arg(va1, _QWORD *);
  v67 = va_arg(va1, __int64 *);
  v68 = va_arg(va1, _QWORD *);
  v69 = va_arg(va1, _QWORD);
  v70 = va_arg(va1, _QWORD);
  v71 = va_arg(va1, _QWORD);
  v4 = a2;
  if ( v62 )
  {
    v9 = a2 + v62[2];
    v10 = *(_BYTE *)v9 & 7;
    if ( v10 >= 3 )
      return 3221225659LL;
    if ( !v65 || *v65 )
    {
      v11 = 0;
      if ( v10 < 2 )
      {
        v11 = RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(v62, a2, a2 + v62[2]) != 0;
        v4 = a2;
      }
    }
    else
    {
      v11 = 1;
    }
    v12 = 0;
    LODWORD(v70) = 0;
    LODWORD(v68) = 0;
    LODWORD(v71) = 0;
    if ( (*(_BYTE *)(v9 + 3) & 0xF) != 0 )
    {
      v13 = (_DWORD)a3 - v4 - *v62;
      if ( v13 >= *(unsigned __int8 *)(v9 + 1) || (*(_BYTE *)v9 & 0x20) != 0 )
        goto LABEL_28;
      if ( *(_BYTE *)(v9 + 2) )
      {
        do
        {
          if ( (HIBYTE(*(_WORD *)(v9 + 2 * v12 + 4)) & 0xF) == 3 )
            break;
          v12 = (unsigned int)RtlpUnwindOpSlots() + (unsigned int)v12;
        }
        while ( (unsigned int)v12 < *(unsigned __int8 *)(v9 + 2) );
        v4 = a2;
      }
      v14 = *(_WORD *)(v9 + 2 * v12 + 4);
      LODWORD(v12) = 0;
      if ( v13 >= (unsigned __int8)v14 )
LABEL_28:
        LODWORD(v71) = 1;
    }
    v15 = v64;
    if ( (_DWORD)v71 )
    {
      Context = RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(v64, *(_BYTE *)(v9 + 3) & 0xF);
      v16 = Context - (v18 & 0xFFFFFFF0);
    }
    else
    {
      v16 = v64[1];
    }
    *v67 = v16;
    if ( v11 )
      goto LABEL_140;
    if ( v10 >= 2 )
    {
      v49 = *(unsigned __int8 *)(v9 + 2);
      if ( (_BYTE)v49 )
      {
        v50 = *(_WORD *)(v9 + 4);
        if ( (HIBYTE(v50) & 0xF) == 6 )
        {
          v51 = (unsigned __int8)v50;
          v52 = (_DWORD)a3 - v4;
          if ( (v50 & 0x1000) != 0 )
          {
            v53 = v62[1] - (unsigned __int8)v50;
            LODWORD(v12) = v52 - v53 < (unsigned int)(unsigned __int8)v50;
            LODWORD(v70) = v12;
          }
          else
          {
            v53 = 0;
          }
          if ( (_DWORD)v12 )
            goto LABEL_139;
          v54 = v49;
          if ( v49 > 1 )
          {
            v55 = 1;
            while ( 1 )
            {
              v56 = *(_WORD *)(v9 + 2LL * v55 + 4);
              if ( (HIBYTE(v56) & 0xF) != 6 )
                goto LABEL_137;
              v53 = (unsigned __int8)v56 + (HIBYTE(v56) >> 4 << 8);
              if ( !v53 )
                goto LABEL_137;
              v53 = v62[1] - v53;
              if ( v52 - v53 < v51 )
                break;
              if ( ++v55 >= v54 )
                goto LABEL_137;
            }
            LODWORD(v12) = 1;
            LODWORD(v70) = 1;
LABEL_137:
            LODWORD(v4) = a2;
          }
          if ( (_DWORD)v12 )
          {
LABEL_139:
            RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
              v4,
              (_DWORD)a3,
              v52 - v53,
              (_DWORD)v62,
              (__int64)v15,
              v69);
            goto LABEL_121;
          }
        }
      }
      goto LABEL_140;
    }
    i = a3;
    v20 = *a3;
    v57 = 0;
    if ( *a3 != 72 )
      goto LABEL_43;
    if ( a3[1] == 0x83 && a3[2] == 0xC4 )
    {
LABEL_37:
      for ( i = a3 + 4; ; i += 2 )
      {
LABEL_47:
        while ( 1 )
        {
          v20 = *i;
LABEL_48:
          if ( (v20 & 0xF8) != 0x58 )
            break;
          ++i;
        }
        if ( (v20 & 0xF0) != 0x40 || (i[1] & 0xF8) != 0x58 )
          break;
      }
      if ( v20 == -14 )
        v20 = *++i;
      if ( (unsigned __int8)(v20 + 62) <= 1u || v20 == -13 && i[1] == 0xC3 )
        goto LABEL_66;
      if ( ((v20 + 23) & 0xFD) != 0 )
      {
        if ( v20 == -1 && i[1] == 37 )
        {
          LODWORD(v70) = 1;
          LODWORD(v68) = 1;
          goto LABEL_69;
        }
        if ( (v20 & 0xF8) == 0x48 && i[1] == 0xFF )
        {
          v23 = (i[2] & 0x38) == 32;
          goto LABEL_65;
        }
      }
      else
      {
        if ( v20 == -21 )
          v30 = (char)i[1] + 2;
        else
          v30 = *(_DWORD *)(i + 1) + 5;
        v31 = (unsigned __int64)&i[v30 - v4];
        v32 = *v62;
        if ( v31 < v32 || v31 >= v62[1] )
        {
          v33 = v31 + v4;
          if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
          {
            RtlReadUCharFromUser(v31 + v4);
            v4 = a2;
          }
          v34 = (_QWORD *)RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(v59, v62, v4, v33);
          if ( !*v34 || v31 == *(_DWORD *)*v34 )
          {
            v24 = 1;
            LODWORD(v70) = 1;
            LODWORD(v68) = 1;
LABEL_68:
            if ( v24 )
            {
LABEL_69:
              v59[0] = v15;
              v25 = v69;
              v26 = (_QWORD *)v69;
              v27 = a3;
              v28 = *a3;
              if ( (*a3 & 0xF8) == 0x48 )
              {
                v29 = a3[1];
                switch ( v29 )
                {
                  case -125:
                    v15[1] += (char)a3[3];
LABEL_72:
                    v27 = a3 + 4;
LABEL_93:
                    v28 = *v27;
                    break;
                  case -127:
                    v15[1] += *(int *)(a3 + 3);
LABEL_92:
                    v27 = a3 + 7;
                    goto LABEL_93;
                  case -115:
                    v35 = a3[2] & 0xF8;
                    if ( v35 == 96 )
                    {
                      v36 = RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(v15, v57);
                      v15[1] = v36;
                      v15[1] = v36 + (char)a3[3];
                      goto LABEL_72;
                    }
                    if ( v35 == -96 )
                    {
                      v15[1] = *(int *)(a3 + 3) + RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(v15, v57);
                      goto LABEL_92;
                    }
                    break;
                }
              }
              v37 = (_QWORD **)(v15 + 1);
              while ( 1 )
              {
                if ( (v28 & 0xF8) == 0x58 )
                {
                  v38 = v28 & 7;
                  v39 = (_QWORD **)(v15 + 1);
                  v40 = *v39;
                  if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                  {
                    v59[2] = 1;
                    ProbeForRead(v40, 1u, 4u);
                    v25 = v69;
                    v26 = (_QWORD *)v69;
                  }
                  if ( *v26
                    && ((unsigned __int64)v40 < *(_QWORD *)*v26 || (unsigned __int64)v40 > **(_QWORD **)(v25 + 8) - 8LL) )
                  {
                    return 3221225512LL;
                  }
                  RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(v64, v38, *v40);
                  v25 = v69;
                  v41 = *(_QWORD *)(v69 + 16);
                  if ( v41 )
                    *(_QWORD *)(v41 + 8LL * v38 + 128) = v40;
                  ++*v39;
                  ++v27;
                  v37 = (_QWORD **)(v59[0] + 8LL);
                }
                else
                {
                  if ( (v28 & 0xF0) != 0x40 || (v42 = v27[1], (v42 & 0xF8) != 0x58) )
                  {
                    if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                    {
                      v60 = 8;
                      v47 = *v37;
                      v60 = 1;
                      ProbeForRead(v47, 1u, 4u);
                      v25 = v69;
                      v26 = (_QWORD *)v69;
                    }
                    if ( !*v26
                      || (unsigned __int64)*v37 >= *(_QWORD *)*v26
                      && (unsigned __int64)*v37 <= **(_QWORD **)(v25 + 8) - 8LL )
                    {
                      v48 = *v37;
                      *v15 = **v37;
                      *v37 = v48 + 1;
LABEL_121:
                      if ( v65 )
                        *v65 = 0;
LABEL_141:
                      if ( (_DWORD)v70 && (_DWORD)v71 )
                        *v67 = v15[1] - 8LL;
                      return 0;
                    }
                    return 3221225512LL;
                  }
                  v43 = v42 & 7;
                  v58 = v43;
                  v44 = *v37;
                  if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                  {
                    v59[3] = 1;
                    ProbeForRead(v44, 1u, 4u);
                    v43 = v58;
                    v25 = v69;
                    v26 = (_QWORD *)v69;
                  }
                  if ( *v26
                    && ((unsigned __int64)v44 < *(_QWORD *)*v26 || (unsigned __int64)v44 > **(_QWORD **)(v25 + 8) - 8LL) )
                  {
                    return 3221225512LL;
                  }
                  v45 = RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(v64, v43 | (8 * (v28 & 1u)), *v44);
                  v25 = v69;
                  v46 = *(_QWORD *)(v69 + 16);
                  if ( v46 )
                    *(_QWORD *)(v46 + 8 * v45 + 128) = v44;
                  ++*v37;
                  v27 += 2;
                }
                v28 = *v27;
                v15 = v64;
              }
            }
LABEL_140:
            result = RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
                       a2,
                       (_DWORD)a3,
                       *v67,
                       (_DWORD)v62,
                       (__int64)v15,
                       (__int64)v65,
                       (__int64)va,
                       v69);
            if ( (int)result >= 0 )
              goto LABEL_141;
            return result;
          }
        }
        else if ( v31 == v32 )
        {
          v23 = (*(_BYTE *)v9 & 0x20) == 0;
LABEL_65:
          if ( v23 )
          {
LABEL_66:
            v24 = 1;
            LODWORD(v70) = 1;
            LODWORD(v68) = 1;
            goto LABEL_68;
          }
        }
      }
      v24 = 0;
      goto LABEL_68;
    }
    if ( a3[1] != 0x81 || a3[2] != 0xC4 )
    {
LABEL_43:
      if ( (v20 & 0xFE) != 0x48 )
        goto LABEL_48;
      if ( a3[1] != 0x8D )
        goto LABEL_48;
      v21 = a3[2] & 7 | (8 * (v20 & 1));
      v57 = v21;
      if ( !v21 || v21 != (*(_BYTE *)(v9 + 3) & 0xF) )
        goto LABEL_48;
      v22 = a3[2] & 0xF8;
      if ( v22 == 96 )
        goto LABEL_37;
      if ( v22 != -96 )
        goto LABEL_48;
    }
    i = a3 + 7;
    goto LABEL_47;
  }
  v5 = v64;
  v6 = v64 + 1;
  v7 = (_QWORD *)v64[1];
  v68 = v7;
  if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
  {
    v59[1] = 1;
    ProbeForRead(v7, 1u, 4u);
  }
  if ( *(_QWORD *)v69
    && ((unsigned __int64)v7 < **(_QWORD **)v69 || (unsigned __int64)v7 > **(_QWORD **)(v69 + 8) - 8LL) )
  {
    return 3221225512LL;
  }
  if ( a3 != (_BYTE *)*v7 )
  {
    *v5 = *v7;
    *v6 += 8LL;
    *v67 = (__int64)v7;
    if ( v65 )
      *v65 = 0;
    *v66 = 0;
    return 0;
  }
  return 3221225727LL;
}

```

## disassembly

```asm
0x1400e1000  mov     rax, rsp
0x1400e1003  mov     [rax+20h], r9
0x1400e1007  mov     [rax+18h], r8
0x1400e100b  mov     [rax+10h], rdx
0x1400e100f  mov     [rax+8], ecx
0x1400e1012  push    rbx
0x1400e1013  push    rsi
0x1400e1014  push    rdi
0x1400e1015  push    r12
0x1400e1017  push    r13
0x1400e1019  push    r14
0x1400e101b  push    r15
0x1400e101d  sub     rsp, 0A0h
0x1400e1024  mov     rdi, r8
0x1400e1027  mov     r10, rdx
0x1400e102a  test    r9, r9
0x1400e102d  jnz     loc_1400E1128
0x1400e1033  mov     r12, [rsp+0D8h+arg_20]
0x1400e103b  lea     rsi, [r12+8]
0x1400e1040  mov     [rsp+0D8h+var_88], rsi
0x1400e1045  mov     rbx, [rsi]
0x1400e1048  mov     r15, rbx
0x1400e104b  mov     [rsp+0D8h+arg_40], rbx
0x1400e1053  mov     r13, 7FFFFFFF0000h
0x1400e105d  cmp     r8, r13
0x1400e1060  jnb     short loc_1400E1084
0x1400e1062  mov     [rsp+0D8h+var_60], 8
0x1400e106b  lea     r14d, [r9+1]
0x1400e106f  mov     [rsp+0D8h+var_60], r14
0x1400e1074  lea     r8d, [r9+4]; Alignment
0x1400e1078  mov     edx, r14d; Length
0x1400e107b  mov     rcx, rbx; Address
0x1400e107e  call    ProbeForRead
0x1400e1083  nop
0x1400e1084  mov     rcx, [rsp+0D8h+arg_48]
0x1400e108c  mov     rax, [rcx]
0x1400e108f  test    rax, rax
0x1400e1092  jz      short loc_1400E10B3
0x1400e1094  cmp     rbx, [rax]
0x1400e1097  jb      short loc_1400E10A9
0x1400e1099  mov     rax, [rcx+8]
0x1400e109d  mov     rcx, [rax]
0x1400e10a0  sub     rcx, 8
0x1400e10a4  cmp     rbx, rcx
0x1400e10a7  jbe     short loc_1400E10B3
0x1400e10a9  mov     eax, 0C0000028h
0x1400e10ae  jmp     loc_1400E19BC
0x1400e10b3  xor     eax, eax
0x1400e10b5  jmp     short loc_1400E10D7
0x1400e10b7  mov     r12, [rsp+0D8h+arg_20]
0x1400e10bf  mov     rdi, [rsp+0D8h+arg_10]
0x1400e10c7  mov     r15, [rsp+0D8h+arg_40]
0x1400e10cf  mov     rsi, [rsp+0D8h+var_88]
0x1400e10d4  mov     rbx, r15
0x1400e10d7  test    eax, eax
0x1400e10d9  js      loc_1400E19BC
0x1400e10df  mov     rax, [rbx]
0x1400e10e2  cmp     rdi, rax
0x1400e10e5  jnz     short loc_1400E10F1
0x1400e10e7  mov     eax, 0C00000FFh
0x1400e10ec  jmp     loc_1400E19BC
0x1400e10f1  mov     [r12], rax
0x1400e10f5  add     qword ptr [rsi], 8
0x1400e10f9  mov     rax, [rsp+0D8h+arg_38]
0x1400e1101  mov     [rax], r15
0x1400e1104  mov     rax, [rsp+0D8h+arg_28]
0x1400e110c  test    rax, rax
0x1400e110f  jz      short loc_1400E1114
0x1400e1111  mov     byte ptr [rax], 0
0x1400e1114  mov     rax, [rsp+0D8h+arg_30]
0x1400e111c  mov     qword ptr [rax], 0
0x1400e1123  jmp     loc_1400E19BA
0x1400e1128  mov     rax, [rsp+0D8h+arg_18]
0x1400e1130  mov     ebx, [rax+8]
0x1400e1133  add     rbx, rdx
0x1400e1136  movzx   esi, byte ptr [rbx]
0x1400e1139  and     esi, 7
0x1400e113c  cmp     esi, 3
0x1400e113f  jb      short loc_1400E114B
0x1400e1141  mov     eax, 0C00000BBh
0x1400e1146  jmp     loc_1400E19BC
0x1400e114b  mov     rax, [rsp+0D8h+arg_28]
0x1400e1153  test    rax, rax
0x1400e1156  jz      short loc_1400E1168
0x1400e1158  cmp     byte ptr [rax], 0
0x1400e115b  jnz     short loc_1400E1168
0x1400e115d  mov     r14d, 1
0x1400e1163  mov     r15d, r14d
0x1400e1166  jmp     short loc_1400E119A
0x1400e1168  xor     r15d, r15d
0x1400e116b  cmp     esi, 2
0x1400e116e  jnb     short loc_1400E1194
0x1400e1170  mov     r8, rbx
0x1400e1173  mov     rcx, [rsp+0D8h+arg_18]
0x1400e117b  call    ??$RtlpxTrivialFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YAKVCDirectFnEnt@@_KVCDirectUnwindInfo@@PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,CDirectUnwindInfo,_AMD64_UNWIND_PARAMS const *)
0x1400e1180  lea     r14d, [r15+1]
0x1400e1184  test    eax, eax
0x1400e1186  cmovnz  r15d, r14d
0x1400e118a  mov     r10, [rsp+0D8h+arg_8]
0x1400e1192  jmp     short loc_1400E119A
0x1400e1194  mov     r14d, 1
0x1400e119a  xor     r13d, r13d
0x1400e119d  mov     dword ptr [rsp+0D8h+arg_50], r13d
0x1400e11a5  mov     dword ptr [rsp+0D8h+arg_40], r13d
0x1400e11ad  mov     dword ptr [rsp+0D8h+arg_58], r13d
0x1400e11b5  test    byte ptr [rbx+3], 0Fh
0x1400e11b9  jz      short loc_1400E1225
0x1400e11bb  mov     r12d, edi
0x1400e11be  sub     r12d, r10d
0x1400e11c1  mov     rax, [rsp+0D8h+arg_18]
0x1400e11c9  sub     r12d, [rax]
0x1400e11cc  movzx   eax, byte ptr [rbx+1]
0x1400e11d0  cmp     r12d, eax
0x1400e11d3  jnb     short loc_1400E121D
0x1400e11d5  test    byte ptr [rbx], 20h
0x1400e11d8  jnz     short loc_1400E121D
0x1400e11da  cmp     [rbx+2], r13b
0x1400e11de  jbe     short loc_1400E120C
0x1400e11e0  movzx   ecx, word ptr [rbx+r13*2+4]
0x1400e11e6  movzx   eax, cx
0x1400e11e9  shr     ax, 8
0x1400e11ed  and     al, 0Fh
0x1400e11ef  cmp     al, 3
0x1400e11f1  jz      short loc_1400E1204
0x1400e11f3  call    RtlpUnwindOpSlots
0x1400e11f8  add     r13d, eax
0x1400e11fb  movzx   eax, byte ptr [rbx+2]
0x1400e11ff  cmp     r13d, eax
0x1400e1202  jb      short loc_1400E11E0
0x1400e1204  mov     r10, [rsp+0D8h+arg_8]
0x1400e120c  movzx   eax, word ptr [rbx+r13*2+4]
0x1400e1212  movzx   ecx, al
0x1400e1215  xor     r13d, r13d
0x1400e1218  cmp     r12d, ecx
0x1400e121b  jb      short loc_1400E1225
0x1400e121d  mov     dword ptr [rsp+0D8h+arg_58], r14d
0x1400e1225  mov     r12, [rsp+0D8h+arg_20]
0x1400e122d  cmp     dword ptr [rsp+0D8h+arg_58], 0
0x1400e1235  jnz     short loc_1400E123E
0x1400e1237  mov     rax, [r12+8]
0x1400e123c  jmp     short loc_1400E125C
0x1400e123e  movzx   r8d, byte ptr [rbx+3]
0x1400e1243  mov     edx, r8d
0x1400e1246  and     edx, 0Fh
0x1400e1249  mov     rcx, r12
0x1400e124c  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YA_KPEAU_CONTEXT_FOR_STACKWALK@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1400e1251  mov     ecx, 0FFFFFFF0h
0x1400e1256  and     r8, rcx
0x1400e1259  sub     rax, r8
0x1400e125c  mov     rcx, [rsp+0D8h+arg_38]
0x1400e1264  mov     [rcx], rax
0x1400e1267  test    r15d, r15d
0x1400e126a  jnz     loc_1400E193F
0x1400e1270  cmp     esi, 2
0x1400e1273  jnb     loc_1400E183A
0x1400e1279  mov     rcx, rdi
0x1400e127c  movzx   edx, byte ptr [rdi]
0x1400e127f  mov     [rsp+0D8h+var_98], r15d
0x1400e1284  cmp     dl, 48h ; 'H'
0x1400e1287  jnz     short loc_1400E12AC
0x1400e1289  cmp     byte ptr [rdi+1], 83h
0x1400e128d  jnz     short loc_1400E129B
0x1400e128f  cmp     byte ptr [rdi+2], 0C4h
0x1400e1293  jnz     short loc_1400E129B
0x1400e1295  lea     rcx, [rdi+4]
0x1400e1299  jmp     short loc_1400E12F9
0x1400e129b  cmp     dl, 48h ; 'H'
0x1400e129e  jnz     short loc_1400E12AC
0x1400e12a0  cmp     byte ptr [rdi+1], 81h
0x1400e12a4  jnz     short loc_1400E12AC
0x1400e12a6  cmp     byte ptr [rdi+2], 0C4h
0x1400e12aa  jz      short loc_1400E12F5
0x1400e12ac  mov     al, dl
0x1400e12ae  and     al, 0FEh
0x1400e12b0  cmp     al, 48h ; 'H'
0x1400e12b2  jnz     short loc_1400E12FB
0x1400e12b4  cmp     byte ptr [rdi+1], 8Dh
0x1400e12b8  jnz     short loc_1400E12FB
0x1400e12ba  movzx   r8d, byte ptr [rdi+2]
0x1400e12bf  mov     r9d, edx
0x1400e12c2  and     r9d, r14d
0x1400e12c5  shl     r9d, 3
0x1400e12c9  mov     eax, r8d
0x1400e12cc  and     eax, 7
0x1400e12cf  or      r9d, eax
0x1400e12d2  mov     [rsp+0D8h+var_98], r9d
0x1400e12d7  jz      short loc_1400E12FB
0x1400e12d9  movzx   eax, byte ptr [rbx+3]
0x1400e12dd  and     eax, 0Fh
0x1400e12e0  cmp     r9d, eax
0x1400e12e3  jnz     short loc_1400E12FB
0x1400e12e5  and     r8b, 0F8h
0x1400e12e9  cmp     r8b, 60h ; '`'
0x1400e12ed  jz      short loc_1400E1295
0x1400e12ef  cmp     r8b, 0A0h
0x1400e12f3  jnz     short loc_1400E12FB
0x1400e12f5  lea     rcx, [rdi+7]
0x1400e12f9  mov     dl, [rcx]
0x1400e12fb  mov     al, dl
0x1400e12fd  and     al, 0F8h
0x1400e12ff  cmp     al, 58h ; 'X'
0x1400e1301  jnz     short loc_1400E1308
0x1400e1303  add     rcx, r14
0x1400e1306  jmp     short loc_1400E12F9
0x1400e1308  mov     al, dl
0x1400e130a  and     al, 0F0h
0x1400e130c  cmp     al, 40h ; '@'
0x1400e130e  jnz     short loc_1400E131F
0x1400e1310  mov     al, [rcx+1]
0x1400e1313  and     al, 0F8h
0x1400e1315  cmp     al, 58h ; 'X'
0x1400e1317  jnz     short loc_1400E131F
0x1400e1319  add     rcx, 2
0x1400e131d  jmp     short loc_1400E12F9
0x1400e131f  cmp     dl, 0F2h
0x1400e1322  jnz     short loc_1400E1329
0x1400e1324  add     rcx, r14
0x1400e1327  mov     dl, [rcx]
0x1400e1329  lea     eax, [rdx+3Eh]
0x1400e132c  cmp     al, r14b
0x1400e132f  jbe     short loc_1400E1386
0x1400e1331  cmp     dl, 0F3h
0x1400e1334  jnz     short loc_1400E133C
0x1400e1336  cmp     byte ptr [rcx+1], 0C3h
0x1400e133a  jz      short loc_1400E1386
0x1400e133c  lea     eax, [rdx+17h]
0x1400e133f  test    al, 0FDh
0x1400e1341  jz      loc_1400E140A
0x1400e1347  cmp     dl, 0FFh
0x1400e134a  jnz     short loc_1400E136F
0x1400e134c  cmp     byte ptr [rcx+1], 25h ; '%'
0x1400e1350  jnz     short loc_1400E136F
0x1400e1352  mov     ecx, r14d
0x1400e1355  mov     dword ptr [rsp+0D8h+arg_50], ecx
0x1400e135c  mov     dword ptr [rsp+0D8h+arg_40], ecx
0x1400e1363  mov     r13, 7FFFFFFF0000h
0x1400e136d  jmp     short loc_1400E13B7
0x1400e136f  and     dl, 0F8h
0x1400e1372  cmp     dl, 48h ; 'H'
0x1400e1375  jnz     short loc_1400E13A3
0x1400e1377  cmp     byte ptr [rcx+1], 0FFh
0x1400e137b  jnz     short loc_1400E13A3
0x1400e137d  mov     al, [rcx+2]
0x1400e1380  and     al, 38h
0x1400e1382  cmp     al, 20h ; ' '
0x1400e1384  jnz     short loc_1400E13A3
0x1400e1386  mov     ecx, r14d
0x1400e1389  mov     dword ptr [rsp+0D8h+arg_50], ecx
0x1400e1390  mov     dword ptr [rsp+0D8h+arg_40], ecx
0x1400e1397  mov     r13, 7FFFFFFF0000h
0x1400e13a1  jmp     short loc_1400E13AF
0x1400e13a3  mov     r13, 7FFFFFFF0000h
0x1400e13ad  xor     ecx, ecx
0x1400e13af  test    ecx, ecx
0x1400e13b1  jz      loc_1400E193F
0x1400e13b7  mov     [rsp+0D8h+var_68], r12
0x1400e13bc  mov     r8, [rsp+0D8h+arg_48]
0x1400e13c4  mov     r9, r8
0x1400e13c7  mov     [rsp+0D8h+var_78], r8
0x1400e13cc  mov     rsi, rdi
0x1400e13cf  mov     [rsp+0D8h+var_90], rdi
0x1400e13d4  mov     r15b, [rdi]
0x1400e13d7  mov     byte ptr [rsp+0D8h+arg_0], r15b
0x1400e13df  mov     al, r15b
0x1400e13e2  and     al, 0F8h
0x1400e13e4  cmp     al, 48h ; 'H'
0x1400e13e6  jnz     loc_1400E1527
0x1400e13ec  mov     al, [rdi+1]
0x1400e13ef  cmp     al, 83h
0x1400e13f1  jnz     loc_1400E14B8
0x1400e13f7  movsx   rax, byte ptr [rdi+3]
0x1400e13fc  add     [r12+8], rax
0x1400e1401  lea     rsi, [rdi+4]
0x1400e1405  jmp     loc_1400E1517
0x1400e140a  mov     r8, rcx
0x1400e140d  sub     r8, r10
0x1400e1410  cmp     dl, 0EBh
0x1400e1413  jnz     short loc_1400E141E
0x1400e1415  movsx   eax, byte ptr [rcx+1]
0x1400e1419  add     eax, 2
0x1400e141c  jmp     short loc_1400E1424
0x1400e141e  mov     eax, [rcx+1]
0x1400e1421  add     eax, 5
0x1400e1424  movsxd  rsi, eax
0x1400e1427  add     rsi, r8
0x1400e142a  mov     r9, [rsp+0D8h+arg_18]
0x1400e1432  mov     ecx, [r9]
0x1400e1435  cmp     rsi, rcx
0x1400e1438  jb      short loc_1400E1454
0x1400e143a  mov     eax, [r9+4]
0x1400e143e  cmp     rsi, rax
0x1400e1441  jnb     short loc_1400E1454
0x1400e1443  cmp     rsi, rcx
0x1400e1446  jnz     loc_1400E13A3
0x1400e144c  test    byte ptr [rbx], 20h
0x1400e144f  jmp     loc_1400E1384
0x1400e1454  mov     r13, 7FFFFFFF0000h
0x1400e145e  lea     rbx, [rsi+r10]
0x1400e1462  cmp     rdi, r13
0x1400e1465  jnb     short loc_1400E1477
  ... truncated ...
```
