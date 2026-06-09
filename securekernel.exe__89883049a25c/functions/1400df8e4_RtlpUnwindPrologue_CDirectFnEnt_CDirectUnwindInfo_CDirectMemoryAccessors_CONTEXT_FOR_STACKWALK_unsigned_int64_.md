# RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(unsigned __int64,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,uchar *,CDirectFnEnt *,_AMD64_UNWIND_PARAMS *)

- ea: `0x1400df8e4`
- end: `0x1400e016a`
- name: `??$RtlpUnwindPrologue@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJ_K00VCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAV0@PEAU_AMD64_UNWIND_PARAMS@@@Z`
- size: `2182`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400e1000`

## callees

- `0x14000fa40`
- `0x14002c6a8`
- `0x1400442ac`
- `0x1400de514`
- `0x1400de58c`
- `0x1400df8e4`

## pseudocode

```c
__int64 __fastcall RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        _DWORD *a4,
        __int64 a5,
        char *a6,
        _QWORD *a7,
        __int64 a8)
{
  unsigned __int64 v8; // r9
  __int64 v9; // r15
  _QWORD *v10; // r10
  unsigned __int64 v11; // r11
  __int64 v12; // rdi
  _BYTE *v13; // rbx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // r12d
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rcx
  _QWORD *v22; // r14
  __int64 v24; // rcx
  __int64 Context; // rax
  unsigned int v26; // ecx
  _QWORD *v27; // r14
  __int64 v28; // r9
  __int64 v29; // rcx
  _QWORD *v30; // r14
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  __int64 v35; // rax
  _QWORD *v36; // r15
  _QWORD *v37; // r14
  volatile void *v38; // r14
  __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  _QWORD *v41; // rdx
  char v42; // [rsp+20h] [rbp-C8h]
  int v43; // [rsp+50h] [rbp-98h]
  unsigned int v44; // [rsp+54h] [rbp-94h]
  unsigned __int64 v46; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v47; // [rsp+100h] [rbp+18h]

  v47 = a3;
  v46 = a2;
  v8 = a2;
  v9 = a8;
  v10 = (_QWORD *)a8;
  v43 = 0;
  v11 = 0x7FFFFFFF0000LL;
  while ( 2 )
  {
    v12 = 0;
    v42 = 0;
    v44 = v8 - a1 - *a4;
    v13 = (_BYTE *)(a1 + (unsigned int)a4[2]);
    while ( 1 )
    {
      v14 = (unsigned __int8)v13[2];
      if ( (unsigned int)v12 >= v14 )
        break;
      v15 = *(unsigned __int16 *)&v13[2 * v12 + 4];
      if ( v44 < (unsigned __int8)v15 )
      {
        v12 = (unsigned int)RtlpUnwindOpSlots() + (unsigned int)v12;
        v8 = v46;
        v10 = (_QWORD *)a8;
        v11 = 0x7FFFFFFF0000LL;
      }
      else
      {
        v16 = BYTE1(v15) & 0xF;
        v17 = v15 >> 12;
        if ( v16 > 5 )
        {
          v31 = v16 - 6;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( v32 )
            {
              v33 = v32 - 1;
              if ( v33 )
              {
                v34 = v33 - 1;
                if ( v34 )
                {
                  if ( v34 != 1 )
                    goto LABEL_86;
                  v35 = *(_QWORD *)(a5 + 8);
                  v36 = (_QWORD *)(v35 + 8);
                  if ( !v17 )
                    v36 = *(_QWORD **)(a5 + 8);
                  v37 = (_QWORD *)(v35 + (v17 != 0 ? 32LL : 24LL));
                  if ( v8 < v11 )
                  {
                    ProbeForRead(v36, 1u, 4u);
                    v10 = (_QWORD *)a8;
                    v11 = 0x7FFFFFFF0000LL;
                  }
                  if ( *v10
                    && ((unsigned __int64)v36 < *(_QWORD *)*v10 || (unsigned __int64)v36 > **(_QWORD **)(a8 + 8) - 8LL) )
                  {
                    return 3221225512LL;
                  }
                  if ( v46 < v11 )
                  {
                    ProbeForRead(v37, 1u, 4u);
                    v11 = 0x7FFFFFFF0000LL;
                  }
                  if ( *(_QWORD *)a8
                    && ((unsigned __int64)v37 < **(_QWORD **)a8 || (unsigned __int64)v37 > **(_QWORD **)(a8 + 8) - 8LL) )
                  {
                    return 3221225512LL;
                  }
                  v42 = 1;
                  *(_QWORD *)a5 = *v36;
                  *(_QWORD *)(a5 + 8) = *v37;
                  goto LABEL_34;
                }
                v12 = (unsigned int)(v12 + 2);
                a3 = (unsigned __int64)*(unsigned __int16 *)&v13[2 * v12 + 4] << 16;
                v38 = (volatile void *)(*(unsigned __int16 *)&v13[2 * (unsigned int)(v12 - 1) + 4] + v47 + a3);
                if ( v8 < v11 )
                {
                  ProbeForRead(v38, 1u, 4u);
                  v10 = (_QWORD *)a8;
                  v11 = 0x7FFFFFFF0000LL;
                }
              }
              else
              {
                v12 = (unsigned int)(v12 + 1);
                v38 = (volatile void *)(v47 + 16LL * *(unsigned __int16 *)&v13[2 * v12 + 4]);
                if ( v8 < v11 )
                {
                  ProbeForRead(v38, 1u, 4u);
                  v10 = (_QWORD *)a8;
                  v11 = 0x7FFFFFFF0000LL;
                }
              }
              if ( *v10
                && ((unsigned __int64)v38 < *(_QWORD *)*v10 || (unsigned __int64)v38 > **(_QWORD **)(v9 + 8) - 16LL) )
              {
                return 3221225512LL;
              }
              v39 = *(_QWORD *)(v9 + 16);
              v8 = v46;
              if ( v39 )
                *(_QWORD *)(v39 + 8LL * v17) = v38;
            }
            else
            {
              LODWORD(v12) = v12 + 2;
            }
          }
          else
          {
            LODWORD(v12) = v12 + 1;
          }
        }
        else
        {
          if ( v16 == 5 )
          {
            v12 = (unsigned int)(v12 + 2);
            v30 = (_QWORD *)(*(unsigned __int16 *)&v13[2 * (unsigned int)(v12 - 1) + 4]
                           + v47
                           + ((unsigned __int64)*(unsigned __int16 *)&v13[2 * v12 + 4] << 16));
            if ( v8 < v11 )
            {
              ProbeForRead(v30, 1u, 4u);
              v10 = (_QWORD *)a8;
            }
            if ( *v10
              && ((unsigned __int64)v30 < *(_QWORD *)*v10 || (unsigned __int64)v30 > **(_QWORD **)(v9 + 8) - 8LL) )
            {
              return 3221225512LL;
            }
            RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v17, *v30);
            goto LABEL_34;
          }
          if ( (v15 & 0xF00) == 0 )
          {
            v27 = *(_QWORD **)(a5 + 8);
            if ( v8 < v11 )
            {
              ProbeForRead(v27, 1u, 4u);
              v10 = (_QWORD *)a8;
            }
            if ( *v10
              && ((unsigned __int64)v27 < *(_QWORD *)*v10 || (unsigned __int64)v27 > **(_QWORD **)(a8 + 8) - 8LL) )
            {
              return 3221225512LL;
            }
            RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v17, *v27);
            v29 = *(_QWORD *)(v28 + 16);
            if ( v29 )
              *(_QWORD *)(v29 + 8LL * v17 + 128) = v27;
            *(_QWORD *)(a5 + 8) += 8LL;
LABEL_34:
            v8 = v46;
            goto LABEL_71;
          }
          v18 = v16 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                if ( v20 != 1 )
                  goto LABEL_86;
                LODWORD(v12) = v12 + 1;
                v21 = *(unsigned __int16 *)&v13[2 * (unsigned int)v12 + 4];
                v22 = (_QWORD *)(v47 + 8 * v21);
                if ( v8 < v11 )
                {
                  ProbeForRead((volatile void *)(v47 + 8 * v21), 1u, 4u);
                  v10 = (_QWORD *)a8;
                }
                if ( *v10
                  && ((unsigned __int64)v22 < *(_QWORD *)*v10 || (unsigned __int64)v22 > **(_QWORD **)(v9 + 8) - 8LL) )
                {
                  return 3221225512LL;
                }
                RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v17, *v22);
                v24 = *(_QWORD *)(v9 + 16);
                v8 = v46;
                if ( v24 )
                  *(_QWORD *)(v24 + 8LL * v17 + 128) = v22;
              }
              else
              {
                Context = RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v13[3] & 0xF);
                *(_QWORD *)(a5 + 8) = Context;
                a2 = 4294967280LL;
                *(_QWORD *)(a5 + 8) = Context - (v13[3] & 0xF0);
              }
            }
            else
            {
              *(_QWORD *)(a5 + 8) += 8 * v17 + 8;
            }
          }
          else
          {
            v12 = (unsigned int)(v12 + 1);
            a2 = *(unsigned __int16 *)&v13[2 * v12 + 4];
            if ( v17 )
            {
              v12 = (unsigned int)(v12 + 1);
              v26 = a2 + (*(unsigned __int16 *)&v13[2 * v12 + 4] << 16);
            }
            else
            {
              v26 = 8 * a2;
            }
            *(_QWORD *)(a5 + 8) += v26;
          }
        }
LABEL_71:
        v12 = (unsigned int)(v12 + 1);
        v9 = a8;
        v10 = (_QWORD *)a8;
      }
    }
    if ( (*v13 & 0x20) != 0 )
    {
      if ( (unsigned int)++v43 > 0x20 )
LABEL_86:
        RtlRaiseStatus(3221225727LL, a2, a3, v8);
      a4 = &v13[2 * (v14 & 1) + 4 + 2 * v14];
      continue;
    }
    break;
  }
  if ( !v42 )
  {
    if ( v8 < v11 )
    {
      ProbeForRead(*(volatile void **)(a5 + 8), 1u, 4u);
      v10 = (_QWORD *)a8;
    }
    if ( *v10 )
    {
      v40 = *(_QWORD *)(a5 + 8);
      if ( v40 < *(_QWORD *)*v10 || v40 > **(_QWORD **)(v9 + 8) - 8LL )
        return 3221225512LL;
    }
    v41 = *(_QWORD **)(a5 + 8);
    *(_QWORD *)a5 = *v41;
    *(_QWORD *)(a5 + 8) = v41 + 1;
  }
  if ( a6 )
    *a6 = v42;
  *a7 = a4;
  return 0;
}

```

## disassembly

```asm
0x1400df8e4  mov     rax, rsp
0x1400df8e7  mov     [rax+20h], r9
0x1400df8eb  mov     [rax+18h], r8
0x1400df8ef  mov     [rax+10h], rdx
0x1400df8f3  mov     [rax+8], rcx
0x1400df8f7  push    rbx
0x1400df8f8  push    rsi
0x1400df8f9  push    rdi
0x1400df8fa  push    r12
0x1400df8fc  push    r13
0x1400df8fe  push    r14
0x1400df900  push    r15
0x1400df902  sub     rsp, 0B0h
0x1400df909  mov     r9, rdx
0x1400df90c  mov     r13, [rsp+0E8h+arg_20]
0x1400df914  mov     [rsp+0E8h+var_88], r13
0x1400df919  mov     r15, [rsp+0E8h+arg_38]
0x1400df921  mov     r10, r15
0x1400df924  mov     [rsp+0E8h+var_C0], r15
0x1400df929  mov     [rsp+0E8h+var_98], 0
0x1400df931  mov     esi, 1
0x1400df936  mov     r11, 7FFFFFFF0000h
0x1400df940  xor     edi, edi
0x1400df942  mov     [rsp+0E8h+var_C8], dil
0x1400df947  mov     ecx, r9d
0x1400df94a  sub     ecx, dword ptr [rsp+0E8h+arg_0]
0x1400df951  mov     rax, [rsp+0E8h+arg_18]
0x1400df959  sub     ecx, [rax]
0x1400df95b  mov     [rsp+0E8h+var_94], ecx
0x1400df95f  mov     ebx, [rax+8]
0x1400df962  add     rbx, [rsp+0E8h+arg_0]
0x1400df96a  mov     [rsp+0E8h+var_A8], rbx
0x1400df96f  mov     [rsp+0E8h+var_C4], edi
0x1400df973  movzx   ecx, byte ptr [rbx+2]
0x1400df977  cmp     edi, ecx
0x1400df979  jnb     loc_1400E0065
0x1400df97f  movzx   ecx, word ptr [rbx+rdi*2+4]
0x1400df984  movzx   eax, cl
0x1400df987  cmp     [rsp+0E8h+var_94], eax
0x1400df98b  jb      loc_1400E0042
0x1400df991  mov     r12d, ecx
0x1400df994  shr     r12d, 8
0x1400df998  mov     eax, r12d
0x1400df99b  and     eax, 0Fh
0x1400df99e  shr     r12d, 4
0x1400df9a2  mov     dword ptr [rsp+0E8h+var_B8], r12d
0x1400df9a7  cmp     eax, 5
0x1400df9aa  ja      loc_1400DFCF2
0x1400df9b0  jz      loc_1400DFC22
0x1400df9b6  test    eax, eax
0x1400df9b8  jz      loc_1400DFB32
0x1400df9be  sub     eax, 1
0x1400df9c1  jz      loc_1400DFB06
0x1400df9c7  sub     eax, 1
0x1400df9ca  jz      loc_1400DFAF5
0x1400df9d0  sub     eax, 1
0x1400df9d3  jz      loc_1400DFACA
0x1400df9d9  cmp     eax, 1
0x1400df9dc  jnz     loc_1400E015F
0x1400df9e2  inc     edi
0x1400df9e4  mov     dword ptr [rsp+0E8h+var_90], edi
0x1400df9e8  movzx   ecx, word ptr [rbx+rdi*2+4]
0x1400df9ed  mov     rax, [rsp+0E8h+arg_10]
0x1400df9f5  lea     r14, [rax+rcx*8]
0x1400df9f9  mov     [rsp+0E8h+var_B0], r14
0x1400df9fe  cmp     r9, r11
0x1400dfa01  jnb     short loc_1400DFA31
0x1400dfa03  mov     [rsp+0E8h+var_80], 8
0x1400dfa0c  mov     [rsp+0E8h+var_80], rsi
0x1400dfa11  mov     r8d, 4; Alignment
0x1400dfa17  mov     rdx, rsi; Length
0x1400dfa1a  mov     rcx, r14; Address
0x1400dfa1d  call    ProbeForRead
0x1400dfa22  mov     r10, [rsp+0E8h+var_C0]
0x1400dfa27  mov     r11, 7FFFFFFF0000h
0x1400dfa31  mov     rax, [r10]
0x1400dfa34  test    rax, rax
0x1400dfa37  jz      short loc_1400DFA58
0x1400dfa39  cmp     r14, [rax]
0x1400dfa3c  jb      short loc_1400DFA4E
0x1400dfa3e  mov     rax, [r15+8]
0x1400dfa42  mov     rcx, [rax]
0x1400dfa45  sub     rcx, 8
0x1400dfa49  cmp     r14, rcx
0x1400dfa4c  jbe     short loc_1400DFA58
0x1400dfa4e  mov     eax, 0C0000028h
0x1400dfa53  jmp     loc_1400E014B
0x1400dfa58  xor     eax, eax
0x1400dfa5a  jmp     short loc_1400DFA8F
0x1400dfa5c  mov     esi, 1
0x1400dfa61  mov     r11, 7FFFFFFF0000h
0x1400dfa6b  mov     r13, [rsp+0E8h+arg_20]
0x1400dfa73  mov     rbx, [rsp+0E8h+var_A8]
0x1400dfa78  mov     r12d, dword ptr [rsp+0E8h+var_B8]
0x1400dfa7d  mov     r14, [rsp+0E8h+var_B0]
0x1400dfa82  mov     rdi, [rsp+0E8h+var_90]
0x1400dfa87  mov     r15, [rsp+0E8h+arg_38]
0x1400dfa8f  test    eax, eax
0x1400dfa91  js      loc_1400E014B
0x1400dfa97  mov     r8, [r14]
0x1400dfa9a  mov     edx, r12d
0x1400dfa9d  mov     rcx, r13
0x1400dfaa0  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400dfaa5  mov     rcx, [r15+10h]
0x1400dfaa9  mov     r9, [rsp+0E8h+arg_8]
0x1400dfab1  test    rcx, rcx
0x1400dfab4  jz      loc_1400E0030
0x1400dfaba  mov     eax, r12d
0x1400dfabd  mov     [rcx+rax*8+80h], r14
0x1400dfac5  jmp     loc_1400E0030
0x1400dfaca  movzx   edx, byte ptr [rbx+3]
0x1400dface  and     edx, 0Fh
0x1400dfad1  mov     rcx, r13
0x1400dfad4  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YA_KPEAU_CONTEXT_FOR_STACKWALK@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1400dfad9  mov     [r13+8], rax
0x1400dfadd  movzx   ecx, byte ptr [rbx+3]
0x1400dfae1  mov     edx, 0FFFFFFF0h
0x1400dfae6  and     rcx, rdx
0x1400dfae9  sub     rax, rcx
0x1400dfaec  mov     [r13+8], rax
0x1400dfaf0  jmp     loc_1400E0030
0x1400dfaf5  lea     ecx, ds:8[r12*8]
0x1400dfafd  add     [r13+8], rcx
0x1400dfb01  jmp     loc_1400E0030
0x1400dfb06  add     edi, esi
0x1400dfb08  movzx   edx, word ptr [rbx+rdi*2+4]
0x1400dfb0d  test    r12d, r12d
0x1400dfb10  jz      short loc_1400DFB20
0x1400dfb12  add     edi, esi
0x1400dfb14  movzx   ecx, word ptr [rbx+rdi*2+4]
0x1400dfb19  shl     ecx, 10h
0x1400dfb1c  add     ecx, edx
0x1400dfb1e  jmp     short loc_1400DFB27
0x1400dfb20  lea     ecx, ds:0[rdx*8]
0x1400dfb27  mov     eax, ecx
0x1400dfb29  add     [r13+8], rax
0x1400dfb2d  jmp     loc_1400E0030
0x1400dfb32  lea     r15, [r13+8]
0x1400dfb36  mov     [rsp+0E8h+var_A0], r15
0x1400dfb3b  mov     r14, [r15]
0x1400dfb3e  mov     [rsp+0E8h+var_B0], r14
0x1400dfb43  cmp     r9, r11
0x1400dfb46  jnb     short loc_1400DFB76
0x1400dfb48  mov     [rsp+0E8h+var_78], 8
0x1400dfb51  mov     [rsp+0E8h+var_78], rsi
0x1400dfb56  mov     r8d, 4; Alignment
0x1400dfb5c  mov     rdx, rsi; Length
0x1400dfb5f  mov     rcx, r14; Address
0x1400dfb62  call    ProbeForRead
0x1400dfb67  mov     r10, [rsp+0E8h+var_C0]
0x1400dfb6c  mov     r11, 7FFFFFFF0000h
0x1400dfb76  mov     rax, [r10]
0x1400dfb79  test    rax, rax
0x1400dfb7c  jz      short loc_1400DFBA4
0x1400dfb7e  cmp     r14, [rax]
0x1400dfb81  jb      loc_1400DFA4E
0x1400dfb87  mov     r9, [rsp+0E8h+arg_38]
0x1400dfb8f  mov     rax, [r9+8]
0x1400dfb93  mov     rcx, [rax]
0x1400dfb96  sub     rcx, 8
0x1400dfb9a  cmp     r14, rcx
0x1400dfb9d  jbe     short loc_1400DFBAC
0x1400dfb9f  jmp     loc_1400DFA4E
0x1400dfba4  mov     r9, [rsp+0E8h+arg_38]
0x1400dfbac  xor     eax, eax
0x1400dfbae  jmp     short loc_1400DFBE7
0x1400dfbb0  mov     esi, 1
0x1400dfbb5  mov     r11, 7FFFFFFF0000h
0x1400dfbbf  mov     r13, [rsp+0E8h+arg_20]
0x1400dfbc7  mov     edi, [rsp+0E8h+var_C4]
0x1400dfbcb  mov     rbx, [rsp+0E8h+var_A8]
0x1400dfbd0  mov     r12d, dword ptr [rsp+0E8h+var_B8]
0x1400dfbd5  mov     r15, [rsp+0E8h+var_A0]
0x1400dfbda  mov     r14, [rsp+0E8h+var_B0]
0x1400dfbdf  mov     r9, [rsp+0E8h+arg_38]
0x1400dfbe7  test    eax, eax
0x1400dfbe9  js      loc_1400E014B
0x1400dfbef  mov     r8, [r14]
0x1400dfbf2  mov     edx, r12d
0x1400dfbf5  mov     rcx, r13
0x1400dfbf8  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400dfbfd  mov     rcx, [r9+10h]
0x1400dfc01  test    rcx, rcx
0x1400dfc04  jz      short loc_1400DFC11
0x1400dfc06  mov     eax, r12d
0x1400dfc09  mov     [rcx+rax*8+80h], r14
0x1400dfc11  add     qword ptr [r15], 8
0x1400dfc15  mov     r9, [rsp+0E8h+arg_8]
0x1400dfc1d  jmp     loc_1400E0030
0x1400dfc22  add     edi, 2
0x1400dfc25  mov     [rsp+0E8h+var_C4], edi
0x1400dfc29  movzx   r8d, word ptr [rbx+rdi*2+4]
0x1400dfc2f  shl     r8, 10h
0x1400dfc33  lea     eax, [rdi-1]
0x1400dfc36  movzx   r14d, word ptr [rbx+rax*2+4]
0x1400dfc3c  mov     rcx, [rsp+0E8h+arg_10]
0x1400dfc44  lea     rcx, [rcx+r8]
0x1400dfc48  lea     r14, [r14+rcx]
0x1400dfc4c  mov     [rsp+0E8h+var_A0], r14
0x1400dfc51  cmp     r9, r11
0x1400dfc54  jnb     short loc_1400DFC84
0x1400dfc56  mov     [rsp+0E8h+var_70], 8
0x1400dfc5f  mov     [rsp+0E8h+var_70], rsi
0x1400dfc64  mov     r8d, 4; Alignment
0x1400dfc6a  mov     rdx, rsi; Length
0x1400dfc6d  mov     rcx, r14; Address
0x1400dfc70  call    ProbeForRead
0x1400dfc75  mov     r10, [rsp+0E8h+var_C0]
0x1400dfc7a  mov     r11, 7FFFFFFF0000h
0x1400dfc84  mov     rax, [r10]
0x1400dfc87  test    rax, rax
0x1400dfc8a  jz      short loc_1400DFCA9
0x1400dfc8c  cmp     r14, [rax]
0x1400dfc8f  jb      loc_1400DFA4E
0x1400dfc95  mov     rax, [r15+8]
0x1400dfc99  mov     rcx, [rax]
0x1400dfc9c  sub     rcx, 8
0x1400dfca0  cmp     r14, rcx
0x1400dfca3  ja      loc_1400DFA4E
0x1400dfca9  xor     eax, eax
0x1400dfcab  jmp     short loc_1400DFCD7
0x1400dfcad  mov     esi, 1
0x1400dfcb2  mov     r11, 7FFFFFFF0000h
0x1400dfcbc  mov     r13, [rsp+0E8h+arg_20]
0x1400dfcc4  mov     rbx, [rsp+0E8h+var_A8]
0x1400dfcc9  mov     r12d, dword ptr [rsp+0E8h+var_B8]
0x1400dfcce  mov     edi, [rsp+0E8h+var_C4]
0x1400dfcd2  mov     r14, [rsp+0E8h+var_A0]
0x1400dfcd7  test    eax, eax
0x1400dfcd9  js      loc_1400E014B
0x1400dfcdf  mov     r8, [r14]
0x1400dfce2  mov     edx, r12d
0x1400dfce5  mov     rcx, r13
0x1400dfce8  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400dfced  jmp     loc_1400DFC15
0x1400dfcf2  sub     eax, 6
0x1400dfcf5  jz      loc_1400E002E
0x1400dfcfb  sub     eax, 1
0x1400dfcfe  jz      loc_1400E0029
0x1400dfd04  sub     eax, 1
0x1400dfd07  jz      loc_1400DFF52
0x1400dfd0d  sub     eax, 1
0x1400dfd10  jz      loc_1400DFEAE
0x1400dfd16  cmp     eax, 1
0x1400dfd19  jnz     loc_1400E015F
0x1400dfd1f  lea     rax, [r13+8]
0x1400dfd23  mov     [rsp+0E8h+var_A0], rax
0x1400dfd28  mov     rax, [rax]
0x1400dfd2b  lea     r15, [rax+8]
0x1400dfd2f  test    r12d, r12d
0x1400dfd32  cmovz   r15, rax
0x1400dfd36  mov     [rsp+0E8h+var_B8], r15
0x1400dfd3b  neg     r12d
0x1400dfd3e  sbb     r14, r14
0x1400dfd41  and     r14d, 8
0x1400dfd45  add     r14, 18h
0x1400dfd49  add     r14, rax
0x1400dfd4c  mov     [rsp+0E8h+var_B0], r14
0x1400dfd51  cmp     r9, r11
0x1400dfd54  jnb     short loc_1400DFD8A
0x1400dfd56  mov     [rsp+0E8h+var_68], 8
0x1400dfd62  mov     [rsp+0E8h+var_68], rsi
0x1400dfd6a  mov     r8d, 4; Alignment
0x1400dfd70  mov     rdx, rsi; Length
0x1400dfd73  mov     rcx, r15; Address
0x1400dfd76  call    ProbeForRead
0x1400dfd7b  mov     r10, [rsp+0E8h+var_C0]
0x1400dfd80  mov     r11, 7FFFFFFF0000h
0x1400dfd8a  mov     rax, [r10]
0x1400dfd8d  test    rax, rax
0x1400dfd90  jz      short loc_1400DFDB7
0x1400dfd92  cmp     r15, [rax]
0x1400dfd95  jb      loc_1400DFA4E
0x1400dfd9b  mov     r9, [rsp+0E8h+arg_38]
0x1400dfda3  mov     rax, [r9+8]
0x1400dfda7  mov     rcx, [rax]
0x1400dfdaa  sub     rcx, 8
0x1400dfdae  cmp     r15, rcx
0x1400dfdb1  ja      loc_1400DFA4E
0x1400dfdb7  xor     eax, eax
0x1400dfdb9  jmp     short loc_1400DFDE5
0x1400dfdbb  mov     esi, 1
0x1400dfdc0  mov     r11, 7FFFFFFF0000h
0x1400dfdca  mov     r13, [rsp+0E8h+arg_20]
0x1400dfdd2  mov     edi, [rsp+0E8h+var_C4]
0x1400dfdd6  mov     rbx, [rsp+0E8h+var_A8]
0x1400dfddb  mov     r15, [rsp+0E8h+var_B8]
0x1400dfde0  mov     r14, [rsp+0E8h+var_B0]
0x1400dfde5  test    eax, eax
0x1400dfde7  js      loc_1400E014B
0x1400dfded  cmp     [rsp+0E8h+arg_8], r11
0x1400dfdf5  jnb     short loc_1400DFE26
0x1400dfdf7  mov     [rsp+0E8h+var_60], 8
0x1400dfe03  mov     [rsp+0E8h+var_60], rsi
0x1400dfe0b  mov     r8d, 4; Alignment
0x1400dfe11  mov     rdx, rsi; Length
0x1400dfe14  mov     rcx, r14; Address
0x1400dfe17  call    ProbeForRead
0x1400dfe1c  mov     r11, 7FFFFFFF0000h
0x1400dfe26  mov     rax, [rsp+0E8h+var_C0]
  ... truncated ...
```
