# RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(unsigned __int64,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT *,uchar *,CDirectFnEnt *,_AMD64_UNWIND_PARAMS *)

- ea: `0x1400df038`
- end: `0x1400df8dd`
- name: `??$RtlpUnwindPrologue@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJ_K00VCDirectFnEnt@@PEAU_CONTEXT@@PEAEPEAV0@PEAU_AMD64_UNWIND_PARAMS@@@Z`
- size: `2213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400e04c8`

## callees

- `0x14000fa40`
- `0x14002c6a8`
- `0x1400442ac`
- `0x1400de4dc`
- `0x1400de54c`
- `0x1400df038`

## pseudocode

```c
__int64 __fastcall RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5,
        char *a6,
        _QWORD *a7,
        __int64 a8)
{
  unsigned __int64 v8; // r9
  __int64 v9; // r12
  _QWORD *v10; // r10
  __int64 v11; // rdi
  _BYTE *v12; // rbx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // r13d
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rcx
  _QWORD *v21; // r14
  __int64 v23; // rcx
  __int64 Context; // rax
  unsigned int v25; // ecx
  _QWORD *v26; // r14
  __int64 v27; // rcx
  _QWORD *v28; // r14
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rax
  _QWORD *v34; // r12
  _QWORD *v35; // r14
  _QWORD *v36; // r14
  __int64 v37; // rax
  unsigned __int64 v38; // rdx
  _QWORD *v39; // rcx
  char v40; // [rsp+20h] [rbp-B8h]
  int v41; // [rsp+50h] [rbp-88h]
  unsigned int v42; // [rsp+54h] [rbp-84h]
  unsigned __int64 v44; // [rsp+E8h] [rbp+10h]
  __int64 v45; // [rsp+F0h] [rbp+18h]

  v45 = a3;
  v44 = a2;
  v8 = a2;
  v9 = a8;
  v10 = (_QWORD *)a8;
  v41 = 0;
  while ( 2 )
  {
    v11 = 0;
    v40 = 0;
    v42 = v8 - a1 - *a4;
    v12 = (_BYTE *)(a1 + (unsigned int)a4[2]);
    while ( 1 )
    {
      v13 = (unsigned __int8)v12[2];
      if ( (unsigned int)v11 >= v13 )
        break;
      v14 = *(unsigned __int16 *)&v12[2 * v11 + 4];
      if ( v42 < (unsigned __int8)v14 )
      {
        v11 = (unsigned int)RtlpUnwindOpSlots() + (unsigned int)v11;
        v8 = v44;
        v10 = (_QWORD *)a8;
      }
      else
      {
        v15 = BYTE1(v14) & 0xF;
        v16 = v14 >> 12;
        if ( v15 > 5 )
        {
          v29 = v15 - 6;
          if ( !v29 )
          {
            LODWORD(v11) = v11 + 1;
            goto LABEL_71;
          }
          v30 = v29 - 1;
          if ( !v30 )
          {
            LODWORD(v11) = v11 + 2;
            goto LABEL_71;
          }
          v31 = v30 - 1;
          if ( !v31 )
          {
            v11 = (unsigned int)(v11 + 1);
            v36 = (_QWORD *)(v45 + 16LL * *(unsigned __int16 *)&v12[2 * v11 + 4]);
            if ( v8 < 0x7FFFFFFF0000LL )
            {
              ProbeForRead(v36, 1u, 4u);
              v10 = (_QWORD *)a8;
            }
            goto LABEL_64;
          }
          v32 = v31 - 1;
          if ( !v32 )
          {
            v11 = (unsigned int)(v11 + 2);
            v36 = (_QWORD *)(*(unsigned __int16 *)&v12[2 * (unsigned int)(v11 - 1) + 4]
                           + v45
                           + ((unsigned __int64)*(unsigned __int16 *)&v12[2 * v11 + 4] << 16));
            if ( v8 < 0x7FFFFFFF0000LL )
            {
              ProbeForRead(v36, 1u, 4u);
              v10 = (_QWORD *)a8;
            }
LABEL_64:
            if ( *v10
              && ((unsigned __int64)v36 < *(_QWORD *)*v10 || (unsigned __int64)v36 > **(_QWORD **)(v9 + 8) - 16LL) )
            {
              return 3221225512LL;
            }
            a2 = v36[1];
            a3 = v16;
            *(_QWORD *)(a5 + 16 * (v16 + 26LL)) = *v36;
            *(_QWORD *)(a5 + 16LL * v16 + 424) = a2;
            v37 = *(_QWORD *)(v9 + 16);
            v8 = v44;
            if ( v37 )
              *(_QWORD *)(v37 + 8LL * v16) = v36;
            goto LABEL_71;
          }
          if ( v32 != 1 )
            goto LABEL_86;
          v33 = *(_QWORD *)(a5 + 152);
          v34 = (_QWORD *)(v33 + 8);
          if ( !v16 )
            v34 = *(_QWORD **)(a5 + 152);
          v35 = (_QWORD *)(v33 + (v16 != 0 ? 32LL : 24LL));
          if ( v8 < 0x7FFFFFFF0000LL )
          {
            ProbeForRead(v34, 1u, 4u);
            v10 = (_QWORD *)a8;
          }
          if ( *v10 && ((unsigned __int64)v34 < *(_QWORD *)*v10 || (unsigned __int64)v34 > **(_QWORD **)(a8 + 8) - 8LL) )
            return 3221225512LL;
          if ( v44 < 0x7FFFFFFF0000LL )
            ProbeForRead(v35, 1u, 4u);
          if ( *(_QWORD *)a8
            && ((unsigned __int64)v35 < **(_QWORD **)a8 || (unsigned __int64)v35 > **(_QWORD **)(a8 + 8) - 8LL) )
          {
            return 3221225512LL;
          }
          v40 = 1;
          *(_QWORD *)(a5 + 248) = *v34;
          *(_QWORD *)(a5 + 152) = *v35;
          v8 = v44;
        }
        else
        {
          if ( v15 == 5 )
          {
            v11 = (unsigned int)(v11 + 2);
            v28 = (_QWORD *)(*(unsigned __int16 *)&v12[2 * (unsigned int)(v11 - 1) + 4]
                           + v45
                           + ((unsigned __int64)*(unsigned __int16 *)&v12[2 * v11 + 4] << 16));
            if ( v8 < 0x7FFFFFFF0000LL )
            {
              ProbeForRead(v28, 1u, 4u);
              v10 = (_QWORD *)a8;
            }
            if ( *v10
              && ((unsigned __int64)v28 < *(_QWORD *)*v10 || (unsigned __int64)v28 > **(_QWORD **)(v9 + 8) - 8LL) )
            {
              return 3221225512LL;
            }
            RtlpAmd64SetContextGp<_CONTEXT *>(a5, v16, *v28);
            goto LABEL_34;
          }
          if ( (v14 & 0xF00) == 0 )
          {
            v26 = *(_QWORD **)(a5 + 152);
            if ( v8 < 0x7FFFFFFF0000LL )
            {
              ProbeForRead(v26, 1u, 4u);
              v10 = (_QWORD *)a8;
            }
            if ( *v10
              && ((unsigned __int64)v26 < *(_QWORD *)*v10 || (unsigned __int64)v26 > **(_QWORD **)(a8 + 8) - 8LL) )
            {
              return 3221225512LL;
            }
            RtlpAmd64SetContextGp<_CONTEXT *>(a5, v16, *v26);
            v27 = *(_QWORD *)(a8 + 16);
            if ( v27 )
              *(_QWORD *)(v27 + 8LL * v16 + 128) = v26;
            *(_QWORD *)(a5 + 152) += 8LL;
            goto LABEL_34;
          }
          v17 = v15 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( !v18 )
            {
              *(_QWORD *)(a5 + 152) += 8 * v16 + 8;
              goto LABEL_71;
            }
            v19 = v18 - 1;
            if ( !v19 )
            {
              Context = RtlpAmd64GetContextGp<_CONTEXT *>(a5, v12[3] & 0xF);
              *(_QWORD *)(a5 + 152) = Context;
              a2 = 4294967280LL;
              *(_QWORD *)(a5 + 152) = Context - (v12[3] & 0xF0);
LABEL_34:
              v8 = v44;
              goto LABEL_71;
            }
            if ( v19 != 1 )
              goto LABEL_86;
            LODWORD(v11) = v11 + 1;
            v20 = *(unsigned __int16 *)&v12[2 * (unsigned int)v11 + 4];
            v21 = (_QWORD *)(v45 + 8 * v20);
            if ( v8 < 0x7FFFFFFF0000LL )
            {
              ProbeForRead((volatile void *)(v45 + 8 * v20), 1u, 4u);
              v10 = (_QWORD *)a8;
            }
            if ( *v10
              && ((unsigned __int64)v21 < *(_QWORD *)*v10 || (unsigned __int64)v21 > **(_QWORD **)(v9 + 8) - 8LL) )
            {
              return 3221225512LL;
            }
            RtlpAmd64SetContextGp<_CONTEXT *>(a5, v16, *v21);
            v23 = *(_QWORD *)(v9 + 16);
            v8 = v44;
            if ( v23 )
              *(_QWORD *)(v23 + 8LL * v16 + 128) = v21;
          }
          else
          {
            v11 = (unsigned int)(v11 + 1);
            a2 = *(unsigned __int16 *)&v12[2 * v11 + 4];
            if ( v16 )
            {
              v11 = (unsigned int)(v11 + 1);
              v25 = a2 + (*(unsigned __int16 *)&v12[2 * v11 + 4] << 16);
            }
            else
            {
              v25 = 8 * a2;
            }
            *(_QWORD *)(a5 + 152) += v25;
          }
        }
LABEL_71:
        v11 = (unsigned int)(v11 + 1);
        v9 = a8;
        v10 = (_QWORD *)a8;
      }
    }
    if ( (*v12 & 0x20) != 0 )
    {
      if ( (unsigned int)++v41 > 0x20 )
LABEL_86:
        RtlRaiseStatus(3221225727LL, a2, a3, v8);
      a4 = &v12[2 * (v13 & 1) + 4 + 2 * v13];
      continue;
    }
    break;
  }
  if ( !v40 )
  {
    if ( v8 < 0x7FFFFFFF0000LL )
    {
      ProbeForRead(*(volatile void **)(a5 + 152), 1u, 4u);
      v10 = (_QWORD *)a8;
    }
    if ( *v10 )
    {
      v38 = *(_QWORD *)(a5 + 152);
      if ( v38 < *(_QWORD *)*v10 || v38 > **(_QWORD **)(v9 + 8) - 8LL )
        return 3221225512LL;
    }
    v39 = *(_QWORD **)(a5 + 152);
    *(_QWORD *)(a5 + 248) = *v39;
    *(_QWORD *)(a5 + 152) = v39 + 1;
  }
  if ( a6 )
    *a6 = v40;
  *a7 = a4;
  return 0;
}

```

## disassembly

```asm
0x1400df038  mov     rax, rsp
0x1400df03b  mov     [rax+20h], r9
0x1400df03f  mov     [rax+18h], r8
0x1400df043  mov     [rax+10h], rdx
0x1400df047  mov     [rax+8], rcx
0x1400df04b  push    rbx
0x1400df04c  push    rsi
0x1400df04d  push    rdi
0x1400df04e  push    r12
0x1400df050  push    r13
0x1400df052  push    r14
0x1400df054  push    r15
0x1400df056  sub     rsp, 0A0h
0x1400df05d  mov     r9, rdx
0x1400df060  mov     r12, [rsp+0D8h+arg_38]
0x1400df068  mov     r10, r12
0x1400df06b  mov     [rsp+0D8h+var_B0], r12
0x1400df070  mov     [rsp+0D8h+var_88], 0
0x1400df078  mov     r11, 7FFFFFFF0000h
0x1400df082  mov     r15d, 1
0x1400df088  mov     rsi, [rsp+0D8h+arg_20]
0x1400df090  xor     edi, edi
0x1400df092  mov     [rsp+0D8h+var_B8], dil
0x1400df097  mov     ecx, r9d
0x1400df09a  sub     ecx, dword ptr [rsp+0D8h+arg_0]
0x1400df0a1  mov     rax, [rsp+0D8h+arg_18]
0x1400df0a9  sub     ecx, [rax]
0x1400df0ab  mov     [rsp+0D8h+var_84], ecx
0x1400df0af  mov     ebx, [rax+8]
0x1400df0b2  add     rbx, [rsp+0D8h+arg_0]
0x1400df0ba  mov     [rsp+0D8h+var_98], rbx
0x1400df0bf  mov     [rsp+0D8h+var_B4], edi
0x1400df0c3  movzx   ecx, byte ptr [rbx+2]
0x1400df0c7  cmp     edi, ecx
0x1400df0c9  jnb     loc_1400DF7CA
0x1400df0cf  movzx   ecx, word ptr [rbx+rdi*2+4]
0x1400df0d4  movzx   eax, cl
0x1400df0d7  cmp     [rsp+0D8h+var_84], eax
0x1400df0db  jb      loc_1400DF7A7
0x1400df0e1  mov     r13d, ecx
0x1400df0e4  shr     r13d, 8
0x1400df0e8  mov     eax, r13d
0x1400df0eb  and     eax, 0Fh
0x1400df0ee  shr     r13d, 4
0x1400df0f2  mov     dword ptr [rsp+0D8h+var_A8], r13d
0x1400df0f7  cmp     eax, 5
0x1400df0fa  ja      loc_1400DF42A
0x1400df100  jz      loc_1400DF36C
0x1400df106  test    eax, eax
0x1400df108  jz      loc_1400DF289
0x1400df10e  sub     eax, 1
0x1400df111  jz      loc_1400DF258
0x1400df117  sub     eax, 1
0x1400df11a  jz      loc_1400DF244
0x1400df120  sub     eax, 1
0x1400df123  jz      loc_1400DF213
0x1400df129  cmp     eax, 1
0x1400df12c  jnz     loc_1400DF8D2
0x1400df132  inc     edi
0x1400df134  mov     dword ptr [rsp+0D8h+var_80], edi
0x1400df138  movzx   ecx, word ptr [rbx+rdi*2+4]
0x1400df13d  mov     rax, [rsp+0D8h+arg_10]
0x1400df145  lea     r14, [rax+rcx*8]
0x1400df149  mov     [rsp+0D8h+var_A0], r14
0x1400df14e  cmp     r9, r11
0x1400df151  jnb     short loc_1400DF177
0x1400df153  mov     [rsp+0D8h+var_78], 8
0x1400df15c  mov     [rsp+0D8h+var_78], r15
0x1400df161  mov     r8d, 4; Alignment
0x1400df167  mov     rdx, r15; Length
0x1400df16a  mov     rcx, r14; Address
0x1400df16d  call    ProbeForRead
0x1400df172  mov     r10, [rsp+0D8h+var_B0]
0x1400df177  mov     rax, [r10]
0x1400df17a  test    rax, rax
0x1400df17d  jz      short loc_1400DF19F
0x1400df17f  cmp     r14, [rax]
0x1400df182  jb      short loc_1400DF195
0x1400df184  mov     rax, [r12+8]
0x1400df189  mov     rcx, [rax]
0x1400df18c  sub     rcx, 8
0x1400df190  cmp     r14, rcx
0x1400df193  jbe     short loc_1400DF19F
0x1400df195  mov     eax, 0C0000028h
0x1400df19a  jmp     loc_1400DF8BE
0x1400df19f  xor     eax, eax
0x1400df1a1  jmp     short loc_1400DF1CD
0x1400df1a3  mov     r15d, 1
0x1400df1a9  mov     rsi, [rsp+0D8h+arg_20]
0x1400df1b1  mov     rbx, [rsp+0D8h+var_98]
0x1400df1b6  mov     r13d, dword ptr [rsp+0D8h+var_A8]
0x1400df1bb  mov     r14, [rsp+0D8h+var_A0]
0x1400df1c0  mov     rdi, [rsp+0D8h+var_80]
0x1400df1c5  mov     r12, [rsp+0D8h+arg_38]
0x1400df1cd  test    eax, eax
0x1400df1cf  js      loc_1400DF8BE
0x1400df1d5  mov     r8, [r14]
0x1400df1d8  mov     edx, r13d
0x1400df1db  mov     rcx, rsi
0x1400df1de  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400df1e3  mov     rcx, [r12+10h]
0x1400df1e8  mov     r9, [rsp+0D8h+arg_8]
0x1400df1f0  mov     r11, 7FFFFFFF0000h
0x1400df1fa  test    rcx, rcx
0x1400df1fd  jz      loc_1400DF794
0x1400df203  mov     eax, r13d
0x1400df206  mov     [rcx+rax*8+80h], r14
0x1400df20e  jmp     loc_1400DF794
0x1400df213  movzx   edx, byte ptr [rbx+3]
0x1400df217  and     edx, 0Fh
0x1400df21a  mov     rcx, rsi
0x1400df21d  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT@@@@YA_KPEAU_CONTEXT@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT *>(_CONTEXT *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1400df222  mov     [rsi+98h], rax
0x1400df229  movzx   ecx, byte ptr [rbx+3]
0x1400df22d  mov     edx, 0FFFFFFF0h
0x1400df232  and     rcx, rdx
0x1400df235  sub     rax, rcx
0x1400df238  mov     [rsi+98h], rax
0x1400df23f  jmp     loc_1400DF355
0x1400df244  lea     ecx, ds:8[r13*8]
0x1400df24c  add     [rsi+98h], rcx
0x1400df253  jmp     loc_1400DF794
0x1400df258  add     edi, r15d
0x1400df25b  movzx   edx, word ptr [rbx+rdi*2+4]
0x1400df260  test    r13d, r13d
0x1400df263  jz      short loc_1400DF274
0x1400df265  add     edi, r15d
0x1400df268  movzx   ecx, word ptr [rbx+rdi*2+4]
0x1400df26d  shl     ecx, 10h
0x1400df270  add     ecx, edx
0x1400df272  jmp     short loc_1400DF27B
0x1400df274  lea     ecx, ds:0[rdx*8]
0x1400df27b  mov     eax, ecx
0x1400df27d  add     [rsi+98h], rax
0x1400df284  jmp     loc_1400DF794
0x1400df289  lea     r12, [rsi+98h]
0x1400df290  mov     [rsp+0D8h+var_90], r12
0x1400df295  mov     r14, [r12]
0x1400df299  mov     [rsp+0D8h+var_A0], r14
0x1400df29e  cmp     r9, r11
0x1400df2a1  jnb     short loc_1400DF2C7
0x1400df2a3  mov     [rsp+0D8h+var_70], 8
0x1400df2ac  mov     [rsp+0D8h+var_70], r15
0x1400df2b1  mov     r8d, 4; Alignment
0x1400df2b7  mov     rdx, r15; Length
0x1400df2ba  mov     rcx, r14; Address
0x1400df2bd  call    ProbeForRead
0x1400df2c2  mov     r10, [rsp+0D8h+var_B0]
0x1400df2c7  mov     rax, [r10]
0x1400df2ca  test    rax, rax
0x1400df2cd  jz      short loc_1400DF2F4
0x1400df2cf  cmp     r14, [rax]
0x1400df2d2  jb      loc_1400DF195
0x1400df2d8  mov     rax, [rsp+0D8h+arg_38]
0x1400df2e0  mov     rax, [rax+8]
0x1400df2e4  mov     rcx, [rax]
0x1400df2e7  sub     rcx, 8
0x1400df2eb  cmp     r14, rcx
0x1400df2ee  ja      loc_1400DF195
0x1400df2f4  xor     eax, eax
0x1400df2f6  jmp     short loc_1400DF31E
0x1400df2f8  mov     r15d, 1
0x1400df2fe  mov     rsi, [rsp+0D8h+arg_20]
0x1400df306  mov     edi, [rsp+0D8h+var_B4]
0x1400df30a  mov     rbx, [rsp+0D8h+var_98]
0x1400df30f  mov     r13d, dword ptr [rsp+0D8h+var_A8]
0x1400df314  mov     r12, [rsp+0D8h+var_90]
0x1400df319  mov     r14, [rsp+0D8h+var_A0]
0x1400df31e  test    eax, eax
0x1400df320  js      loc_1400DF8BE
0x1400df326  mov     r8, [r14]
0x1400df329  mov     edx, r13d
0x1400df32c  mov     rcx, rsi
0x1400df32f  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400df334  mov     rax, [rsp+0D8h+arg_38]
0x1400df33c  mov     rcx, [rax+10h]
0x1400df340  test    rcx, rcx
0x1400df343  jz      short loc_1400DF350
0x1400df345  mov     eax, r13d
0x1400df348  mov     [rcx+rax*8+80h], r14
0x1400df350  add     qword ptr [r12], 8
0x1400df355  mov     r9, [rsp+0D8h+arg_8]
0x1400df35d  mov     r11, 7FFFFFFF0000h
0x1400df367  jmp     loc_1400DF794
0x1400df36c  add     edi, 2
0x1400df36f  mov     [rsp+0D8h+var_B4], edi
0x1400df373  movzx   r8d, word ptr [rbx+rdi*2+4]
0x1400df379  shl     r8, 10h
0x1400df37d  lea     eax, [rdi-1]
0x1400df380  movzx   r14d, word ptr [rbx+rax*2+4]
0x1400df386  mov     rcx, [rsp+0D8h+arg_10]
0x1400df38e  lea     rcx, [rcx+r8]
0x1400df392  lea     r14, [r14+rcx]
0x1400df396  mov     [rsp+0D8h+var_90], r14
0x1400df39b  cmp     r9, r11
0x1400df39e  jnb     short loc_1400DF3C4
0x1400df3a0  mov     [rsp+0D8h+var_68], 8
0x1400df3a9  mov     [rsp+0D8h+var_68], r15
0x1400df3ae  mov     r8d, 4; Alignment
0x1400df3b4  mov     rdx, r15; Length
0x1400df3b7  mov     rcx, r14; Address
0x1400df3ba  call    ProbeForRead
0x1400df3bf  mov     r10, [rsp+0D8h+var_B0]
0x1400df3c4  mov     rax, [r10]
0x1400df3c7  test    rax, rax
0x1400df3ca  jz      short loc_1400DF3EA
0x1400df3cc  cmp     r14, [rax]
0x1400df3cf  jb      loc_1400DF195
0x1400df3d5  mov     rax, [r12+8]
0x1400df3da  mov     rcx, [rax]
0x1400df3dd  sub     rcx, 8
0x1400df3e1  cmp     r14, rcx
0x1400df3e4  ja      loc_1400DF195
0x1400df3ea  xor     eax, eax
0x1400df3ec  jmp     short loc_1400DF40F
0x1400df3ee  mov     r15d, 1
0x1400df3f4  mov     rsi, [rsp+0D8h+arg_20]
0x1400df3fc  mov     rbx, [rsp+0D8h+var_98]
0x1400df401  mov     r13d, dword ptr [rsp+0D8h+var_A8]
0x1400df406  mov     edi, [rsp+0D8h+var_B4]
0x1400df40a  mov     r14, [rsp+0D8h+var_90]
0x1400df40f  test    eax, eax
0x1400df411  js      loc_1400DF8BE
0x1400df417  mov     r8, [r14]
0x1400df41a  mov     edx, r13d
0x1400df41d  mov     rcx, rsi
0x1400df420  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400df425  jmp     loc_1400DF355
0x1400df42a  sub     eax, 6
0x1400df42d  jz      loc_1400DF791
0x1400df433  sub     eax, 1
0x1400df436  jz      loc_1400DF78C
0x1400df43c  sub     eax, 1
0x1400df43f  jz      loc_1400DF692
0x1400df445  sub     eax, 1
0x1400df448  jz      loc_1400DF5ED
0x1400df44e  cmp     eax, 1
0x1400df451  jnz     loc_1400DF8D2
0x1400df457  lea     rax, [rsi+98h]
0x1400df45e  mov     [rsp+0D8h+var_90], rax
0x1400df463  mov     rax, [rax]
0x1400df466  lea     r12, [rax+8]
0x1400df46a  test    r13d, r13d
0x1400df46d  cmovz   r12, rax
0x1400df471  mov     [rsp+0D8h+var_A8], r12
0x1400df476  neg     r13d
0x1400df479  sbb     r14, r14
0x1400df47c  and     r14d, 8
0x1400df480  add     r14, 18h
0x1400df484  add     r14, rax
0x1400df487  mov     [rsp+0D8h+var_A0], r14
0x1400df48c  cmp     r9, r11
0x1400df48f  jnb     short loc_1400DF4BF
0x1400df491  mov     [rsp+0D8h+var_60], 8
0x1400df49a  mov     [rsp+0D8h+var_60], r15
0x1400df49f  mov     r8d, 4; Alignment
0x1400df4a5  mov     rdx, r15; Length
0x1400df4a8  mov     rcx, r12; Address
0x1400df4ab  call    ProbeForRead
0x1400df4b0  mov     r10, [rsp+0D8h+var_B0]
0x1400df4b5  mov     r11, 7FFFFFFF0000h
0x1400df4bf  mov     rax, [r10]
0x1400df4c2  test    rax, rax
0x1400df4c5  jz      short loc_1400DF4EC
0x1400df4c7  cmp     r12, [rax]
0x1400df4ca  jb      loc_1400DF195
0x1400df4d0  mov     rax, [rsp+0D8h+arg_38]
0x1400df4d8  mov     rax, [rax+8]
0x1400df4dc  mov     rcx, [rax]
0x1400df4df  sub     rcx, 8
0x1400df4e3  cmp     r12, rcx
0x1400df4e6  ja      loc_1400DF195
0x1400df4ec  xor     eax, eax
0x1400df4ee  jmp     short loc_1400DF51B
0x1400df4f0  mov     r11, 7FFFFFFF0000h
0x1400df4fa  mov     r15d, 1
0x1400df500  mov     rsi, [rsp+0D8h+arg_20]
0x1400df508  mov     edi, [rsp+0D8h+var_B4]
0x1400df50c  mov     rbx, [rsp+0D8h+var_98]
0x1400df511  mov     r12, [rsp+0D8h+var_A8]
0x1400df516  mov     r14, [rsp+0D8h+var_A0]
0x1400df51b  test    eax, eax
0x1400df51d  js      loc_1400DF8BE
0x1400df523  cmp     [rsp+0D8h+arg_8], r11
0x1400df52b  jnb     short loc_1400DF55C
0x1400df52d  mov     [rsp+0D8h+var_58], 8
0x1400df539  mov     [rsp+0D8h+var_58], r15
0x1400df541  mov     r8d, 4; Alignment
0x1400df547  mov     rdx, r15; Length
0x1400df54a  mov     rcx, r14; Address
0x1400df54d  call    ProbeForRead
0x1400df552  mov     r11, 7FFFFFFF0000h
0x1400df55c  mov     rax, [rsp+0D8h+var_B0]
0x1400df561  mov     rax, [rax]
0x1400df564  test    rax, rax
0x1400df567  jz      short loc_1400DF58E
0x1400df569  cmp     r14, [rax]
0x1400df56c  jb      loc_1400DF195
0x1400df572  mov     rax, [rsp+0D8h+arg_38]
0x1400df57a  mov     rax, [rax+8]
  ... truncated ...
```
