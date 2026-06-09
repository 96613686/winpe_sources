# ReadAllocFormat4CharGlyphMapList

- ea: `0x180016f54`
- end: `0x180017327`
- name: `ReadAllocFormat4CharGlyphMapList`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001d5f8`

## callees

- `0x1800132ac`
- `0x180015190`
- `0x1800164a0`
- `0x180016f54`
- `0x180017480`
- `0x18001a6c4`
- `0x18001c94c`
- `0x18001ce6c`
- `0x18001d224`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall ReadAllocFormat4CharGlyphMapList(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        __int64 *a6,
        unsigned __int16 *a7)
{
  __int64 v8; // r14
  unsigned int CmapSubtable; // eax
  unsigned int v10; // ebx
  __int64 result; // rax
  unsigned __int16 v12; // r12
  unsigned __int16 v13; // r15
  unsigned int v14; // r13d
  __int64 v15; // rbx
  unsigned __int16 AllocCmapFormat4Ids; // di
  unsigned __int16 v17; // r9
  unsigned int v18; // eax
  unsigned __int16 v19; // dx
  unsigned __int16 v20; // dx
  unsigned __int16 v21; // r11
  __int64 v22; // r8
  unsigned __int16 *v23; // r15
  int v24; // edx
  __int64 v25; // rax
  unsigned __int16 v26; // r10
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // ax
  unsigned __int16 v29; // di
  unsigned __int16 i; // cx
  unsigned __int16 v31; // r13
  unsigned __int16 v32; // r12
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdi
  __int64 v37; // rcx
  _WORD v38[2]; // [rsp+40h] [rbp-51h] BYREF
  unsigned __int16 v39; // [rsp+44h] [rbp-4Dh] BYREF
  __int16 v40[2]; // [rsp+48h] [rbp-49h] BYREF
  int v41; // [rsp+4Ch] [rbp-45h] BYREF
  int v42; // [rsp+50h] [rbp-41h] BYREF
  __int16 v43; // [rsp+54h] [rbp-3Dh]
  int v44; // [rsp+58h] [rbp-39h]
  __int64 v45; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int16 *v46; // [rsp+68h] [rbp-29h]
  __int64 v47; // [rsp+70h] [rbp-21h] BYREF
  __int64 v48; // [rsp+78h] [rbp-19h]
  __int64 v49; // [rsp+80h] [rbp-11h] BYREF
  int v50; // [rsp+88h] [rbp-9h]
  __int16 v51; // [rsp+8Ch] [rbp-5h]

  v48 = a4;
  v43 = 0;
  *a6 = 0;
  v8 = 0;
  v46 = a7;
  v49 = 0;
  *a7 = 0;
  v50 = 0;
  v51 = 0;
  v40[0] = 0;
  v38[0] = 0;
  v41 = 0;
  v42 = 0;
  v47 = 0;
  v45 = 0;
  v44 = 0;
  v39 = 0;
  CmapSubtable = FindCmapSubtable(a1, a2, a3, v40);
  v10 = CmapSubtable;
  if ( !CmapSubtable )
    return 1006;
  result = ReadCmapLength(a1, &v42, CmapSubtable, v38);
  if ( !(_WORD)result )
  {
    if ( (_WORD)v42 != 4 )
      return 1006;
    result = ReadGeneric(a1, (__int64)&v49, 0xEu, (unsigned __int8 *)&CMAP_FORMAT4_CONTROL, v10, v38);
    if ( !(_WORD)result )
    {
      v12 = HIWORD(v49);
      v13 = HIWORD(v49) >> 1;
      v14 = v10 + v38[0];
      result = ReadAllocCmapFormat4Segs((_DWORD)a1, HIWORD(v49) >> 1, (unsigned int)&v47, v14, (__int64)&v41);
      if ( !(_WORD)result )
      {
        v15 = v47;
        if ( v41 )
        {
          AllocCmapFormat4Ids = ReadAllocCmapFormat4Ids(
                                  (_DWORD)a1,
                                  v13,
                                  v47,
                                  (unsigned int)&v45,
                                  (__int64)&v39,
                                  v14 + v41,
                                  (__int64)&v41);
          if ( AllocCmapFormat4Ids )
          {
            FreeCmapFormat4(v15, v45);
            return AllocCmapFormat4Ids;
          }
          v8 = v45;
          v31 = v39;
        }
        else
        {
          v31 = v44;
        }
        v32 = v12 >> 1;
        v29 = 0;
        for ( i = 0; i < v32; ++i )
        {
          v27 = *(_WORD *)(v15 + 8LL * i);
          if ( v27 != 0xFFFF && v27 >= *(_WORD *)(v15 + 8LL * i + 2) )
          {
            v28 = v29 + v27 - *(_WORD *)(v15 + 8LL * i + 2) + 1;
            if ( v28 < v29 )
            {
              FreeCmapFormat4(v15, v8);
              return 1006;
            }
            v29 = v28;
          }
        }
        if ( v29 )
        {
          v25 = Mem_Alloc(4LL * v29);
          *a6 = v25;
          if ( v25 )
          {
            v23 = v46;
            v26 = 0;
            v21 = 0;
            *v46 = v29;
            if ( !v32 )
            {
LABEL_27:
              v26 = 1;
              *(_WORD *)*a6 = 0;
              *(_WORD *)(*a6 + 2) = 0;
LABEL_28:
              *v23 = v26;
              FreeCmapFormat4(v15, v8);
              SortCodeList(*a6, v23);
              return 0;
            }
            v36 = v48;
            v22 = 0;
            while ( 1 )
            {
              if ( *(_WORD *)(v15 + 8 * v22) != 0xFFFF )
              {
                v17 = *(_WORD *)(v15 + 8 * v22 + 2);
                if ( *(_WORD *)(v15 + 8 * v22) >= v17 )
                  break;
              }
LABEL_17:
              ++v21;
              ++v22;
              if ( v21 >= v32 )
              {
                v23 = v46;
                if ( v26 )
                  goto LABEL_28;
                goto LABEL_27;
              }
            }
            while ( 1 )
            {
              v18 = *(unsigned __int16 *)(v15 + 8 * v22 + 6);
              if ( !(_WORD)v18 )
                break;
              v24 = v21 + v17 + (v18 >> 1) - *(unsigned __int16 *)(v15 + 8 * v22 + 2) - v32;
              if ( v24 >= 0 && v24 < v31 )
              {
                _mm_lfence();
                v19 = *(_WORD *)(v8 + 2LL * v24);
                if ( v19 )
                  goto LABEL_13;
              }
LABEL_16:
              if ( ++v17 > *(_WORD *)(v15 + 8 * v22) )
                goto LABEL_17;
            }
            v19 = v17;
LABEL_13:
            v20 = *(_WORD *)(v15 + 8 * v22 + 4) + v19;
            if ( (unsigned __int16)(v20 - 1) <= 0xFFFDu && v20 < a5 && *(_BYTE *)(v20 + v36) )
            {
              v37 = v26++;
              *(_WORD *)(*a6 + 4 * v37) = v17;
              *(_WORD *)(*a6 + 4 * v37 + 2) = v20;
            }
            goto LABEL_16;
          }
          v34 = v8;
          v35 = v15;
        }
        else
        {
          v33 = Mem_Alloc(4u);
          *a6 = v33;
          v34 = v8;
          v35 = v15;
          if ( v33 )
          {
            FreeCmapFormat4(v15, v8);
            *(_WORD *)*a6 = 0;
            *(_WORD *)(*a6 + 2) = 0;
            *v46 = 1;
            return 0;
          }
        }
        FreeCmapFormat4(v35, v34);
        return 1005;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016f54  mov     [rsp-8+arg_18], rbx
0x180016f59  push    rbp
0x180016f5a  push    rsi
0x180016f5b  push    rdi
0x180016f5c  push    r12
0x180016f5e  push    r13
0x180016f60  push    r14
0x180016f62  push    r15
0x180016f64  lea     rbp, [rsp-0Fh]
0x180016f69  sub     rsp, 0A0h
0x180016f70  mov     rax, cs:__security_cookie
0x180016f77  xor     rax, rsp
0x180016f7a  mov     [rbp+3Fh+var_40], rax
0x180016f7e  mov     rsi, [rbp+3Fh+arg_28]
0x180016f82  xor     r15d, r15d
0x180016f85  xor     eax, eax
0x180016f87  mov     [rbp+3Fh+var_58], r9
0x180016f8b  mov     rdi, rcx
0x180016f8e  mov     [rbp+3Fh+var_80+2], eax
0x180016f91  mov     rcx, [rbp+3Fh+arg_30]
0x180016f95  lea     r9, [rbp+3Fh+var_88]
0x180016f99  mov     [rsi], r15
0x180016f9c  mov     r14d, r15d
0x180016f9f  mov     [rbp+3Fh+var_68], rcx
0x180016fa3  mov     [rbp+3Fh+var_50], rax
0x180016fa7  mov     [rcx], r15w
0x180016fab  mov     rcx, rdi
0x180016fae  mov     [rbp+3Fh+var_48], eax
0x180016fb1  mov     [rbp+3Fh+var_44], ax
0x180016fb5  mov     [rbp+3Fh+var_88], r15w
0x180016fba  mov     [rbp+3Fh+var_90], r15w
0x180016fbf  mov     [rbp+3Fh+var_84], r15d
0x180016fc3  mov     [rbp+3Fh+var_80], eax
0x180016fc6  mov     [rbp+3Fh+var_60], r15
0x180016fca  mov     [rbp+3Fh+var_70], r15
0x180016fce  mov     [rbp+3Fh+var_78], eax
0x180016fd1  mov     [rbp+3Fh+var_8C], ax
0x180016fd5  call    FindCmapSubtable
0x180016fda  mov     ebx, eax
0x180016fdc  test    eax, eax
0x180016fde  jz      loc_180017297
0x180016fe4  lea     r9, [rbp+3Fh+var_90]
0x180016fe8  mov     r8d, eax
0x180016feb  lea     rdx, [rbp+3Fh+var_80]
0x180016fef  mov     rcx, rdi
0x180016ff2  call    ReadCmapLength
0x180016ff7  test    ax, ax
0x180016ffa  jnz     loc_180017203
0x180017000  lea     eax, [r15+4]
0x180017004  cmp     word ptr [rbp+3Fh+var_80], ax
0x180017008  jnz     loc_180017297
0x18001700e  lea     rax, [rbp+3Fh+var_90]
0x180017012  mov     rcx, rdi
0x180017015  mov     [rsp+0D0h+var_A8], rax
0x18001701a  lea     r8d, [r15+0Eh]
0x18001701e  lea     r9, CMAP_FORMAT4_CONTROL
0x180017025  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180017029  lea     rdx, [rbp+3Fh+var_50]
0x18001702d  call    ReadGeneric
0x180017032  test    ax, ax
0x180017035  jnz     loc_180017203
0x18001703b  movzx   r12d, word ptr [rbp+3Fh+var_50+6]
0x180017040  lea     rax, [rbp+3Fh+var_84]
0x180017044  movzx   r13d, [rbp+3Fh+var_90]
0x180017049  lea     r8, [rbp+3Fh+var_60]
0x18001704d  movzx   r15d, r12w
0x180017051  mov     [rsp+0D0h+var_B0], rax
0x180017056  shr     r15w, 1
0x18001705a  add     r13d, ebx
0x18001705d  movzx   edx, r15w
0x180017061  mov     r9d, r13d
0x180017064  mov     rcx, rdi
0x180017067  call    ReadAllocCmapFormat4Segs
0x18001706c  test    ax, ax
0x18001706f  jnz     loc_180017203
0x180017075  mov     eax, [rbp+3Fh+var_84]
0x180017078  mov     rbx, [rbp+3Fh+var_60]
0x18001707c  test    eax, eax
0x18001707e  jz      loc_18001726D
0x180017084  add     eax, r13d
0x180017087  lea     rcx, [rbp+3Fh+var_84]
0x18001708b  mov     [rsp+0D0h+var_A0], rcx
0x180017090  lea     r9, [rbp+3Fh+var_70]
0x180017094  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180017098  mov     r8, rbx
0x18001709b  lea     rax, [rbp+3Fh+var_8C]
0x18001709f  movzx   edx, r15w
0x1800170a3  mov     rcx, rdi
0x1800170a6  mov     [rsp+0D0h+var_B0], rax
0x1800170ab  call    ReadAllocCmapFormat4Ids
0x1800170b0  xor     r15d, r15d
0x1800170b3  movzx   edi, ax
0x1800170b6  test    ax, ax
0x1800170b9  jz      loc_180017262
0x1800170bf  mov     rdx, [rbp+3Fh+var_70]
0x1800170c3  mov     rcx, rbx
0x1800170c6  call    FreeCmapFormat4
0x1800170cb  movzx   eax, di
0x1800170ce  jmp     loc_180017203
0x1800170d3  cmp     [rbx+r8*8], ax
0x1800170d8  jz      short loc_180017135
0x1800170da  movzx   r9d, word ptr [rbx+r8*8+2]
0x1800170e0  cmp     [rbx+r8*8], r9w
0x1800170e5  jb      short loc_180017135
0x1800170e7  movzx   eax, word ptr [rbx+r8*8+6]
0x1800170ed  test    ax, ax
0x1800170f0  jnz     short loc_180017155
0x1800170f2  movzx   edx, r9w
0x1800170f6  add     dx, [rbx+r8*8+4]
0x1800170fc  mov     ecx, 0FFFDh
0x180017101  movzx   eax, dx
0x180017104  sub     ax, r15w
0x180017108  cmp     ax, cx
0x18001710b  ja      loc_180017320
0x180017111  xor     ecx, ecx
0x180017113  cmp     dx, [rbp+3Fh+arg_20]
0x180017117  jnb     short loc_180017125
0x180017119  movzx   eax, dx
0x18001711c  cmp     [rax+rdi], cl
0x18001711f  jnz     loc_180017308
0x180017125  add     r9w, r15w
0x180017129  cmp     r9w, [rbx+r8*8]
0x18001712e  jbe     short loc_1800170E7
0x180017130  mov     eax, 0FFFFh
0x180017135  add     r11w, r15w
0x180017139  inc     r8
0x18001713c  cmp     r11w, r12w
0x180017140  jb      short loc_1800170D3
0x180017142  mov     r15, [rbp+3Fh+var_68]
0x180017146  test    r10w, r10w
0x18001714a  jz      loc_1800171D0
0x180017150  jmp     loc_1800171E5
0x180017155  mov     edx, eax
0x180017157  xor     ecx, ecx
0x180017159  movzx   eax, word ptr [rbx+r8*8+2]
0x18001715f  shr     edx, 1
0x180017161  sub     edx, eax
0x180017163  movzx   eax, r12w
0x180017167  sub     edx, eax
0x180017169  movzx   eax, r9w
0x18001716d  add     edx, eax
0x18001716f  movzx   eax, r11w
0x180017173  add     edx, eax
0x180017175  js      short loc_180017125
0x180017177  movzx   eax, r13w
0x18001717b  cmp     edx, eax
0x18001717d  jge     short loc_180017125
0x18001717f  lfence
0x180017182  movsxd  rax, edx
0x180017185  movzx   edx, word ptr [r14+rax*2]
0x18001718a  test    dx, dx
0x18001718d  jnz     loc_1800170F6
0x180017193  jmp     short loc_180017125
0x180017195  test    di, di
0x180017198  jz      loc_1800172A1
0x18001719e  movzx   ecx, di
0x1800171a1  shl     rcx, 2; Size
0x1800171a5  call    Mem_Alloc
0x1800171aa  xor     ecx, ecx
0x1800171ac  mov     [rsi], rax
0x1800171af  test    rax, rax
0x1800171b2  jz      loc_1800172DC
0x1800171b8  mov     r15, [rbp+3Fh+var_68]
0x1800171bc  mov     r10d, ecx
0x1800171bf  mov     r11d, ecx
0x1800171c2  mov     [r15], di
0x1800171c6  cmp     cx, r12w
0x1800171ca  jb      loc_1800172F1
0x1800171d0  mov     r8, [rsi]
0x1800171d3  mov     r10d, 1
0x1800171d9  mov     [r8], cx
0x1800171dd  mov     r8, [rsi]
0x1800171e0  mov     [r8+2], cx
0x1800171e5  mov     rdx, r14
0x1800171e8  mov     [r15], r10w
0x1800171ec  mov     rcx, rbx
0x1800171ef  call    FreeCmapFormat4
0x1800171f4  mov     rcx, [rsi]
0x1800171f7  mov     rdx, r15
0x1800171fa  call    SortCodeList
0x1800171ff  xor     ecx, ecx
0x180017201  mov     eax, ecx
0x180017203  mov     rcx, [rbp+3Fh+var_40]
0x180017207  xor     rcx, rsp; StackCookie
0x18001720a  call    __security_check_cookie
0x18001720f  mov     rbx, [rsp+0D0h+arg_18]
0x180017217  add     rsp, 0A0h
0x18001721e  pop     r15
0x180017220  pop     r14
0x180017222  pop     r13
0x180017224  pop     r12
0x180017226  pop     rdi
0x180017227  pop     rsi
0x180017228  pop     rbp
0x180017229  retn
0x18001722a  cmp     cx, r12w
0x18001722e  jnb     loc_180017195
0x180017234  movzx   edx, cx
0x180017237  movzx   eax, word ptr [rbx+rdx*8]
0x18001723b  cmp     ax, r9w
0x18001723f  jz      short loc_18001725C
0x180017241  cmp     ax, [rbx+rdx*8+2]
0x180017246  jb      short loc_18001725C
0x180017248  sub     ax, [rbx+rdx*8+2]
0x18001724d  add     ax, di
0x180017250  add     ax, r8w
0x180017254  cmp     ax, di
0x180017257  jb      short loc_18001728C
0x180017259  movzx   edi, ax
0x18001725c  add     cx, r8w
0x180017260  jmp     short loc_18001722A
0x180017262  mov     r14, [rbp+3Fh+var_70]
0x180017266  movzx   r13d, [rbp+3Fh+var_8C]
0x18001726b  jmp     short loc_180017274
0x18001726d  mov     r13d, [rbp+3Fh+var_78]
0x180017271  xor     r15d, r15d
0x180017274  shr     r12w, 1
0x180017278  mov     edi, r15d
0x18001727b  mov     ecx, r15d
0x18001727e  mov     r9d, 0FFFFh
0x180017284  mov     r8d, 1
0x18001728a  jmp     short loc_18001722A
0x18001728c  mov     rdx, r14
0x18001728f  mov     rcx, rbx
0x180017292  call    FreeCmapFormat4
0x180017297  mov     eax, 3EEh
0x18001729c  jmp     loc_180017203
0x1800172a1  mov     ecx, 4; Size
0x1800172a6  call    Mem_Alloc
0x1800172ab  mov     [rsi], rax
0x1800172ae  mov     rdx, r14
0x1800172b1  mov     rcx, rbx
0x1800172b4  test    rax, rax
0x1800172b7  jz      short loc_1800172E2
0x1800172b9  call    FreeCmapFormat4
0x1800172be  mov     rcx, [rsi]
0x1800172c1  mov     [rcx], r15w
0x1800172c5  mov     rcx, [rsi]
0x1800172c8  mov     [rcx+2], r15w
0x1800172cd  mov     r15, [rbp+3Fh+var_68]
0x1800172d1  mov     word ptr [r15], 1
0x1800172d7  jmp     loc_1800171FF
0x1800172dc  mov     rdx, r14
0x1800172df  mov     rcx, rbx
0x1800172e2  call    FreeCmapFormat4
0x1800172e7  mov     eax, 3EDh
0x1800172ec  jmp     loc_180017203
0x1800172f1  mov     rdi, [rbp+3Fh+var_58]
0x1800172f5  mov     r8, rcx
0x1800172f8  mov     eax, 0FFFFh
0x1800172fd  mov     r15d, 1
0x180017303  jmp     loc_1800170D3
0x180017308  mov     rax, [rsi]
0x18001730b  movzx   ecx, r10w
0x18001730f  add     r10w, r15w
0x180017313  mov     [rax+rcx*4], r9w
0x180017318  mov     rax, [rsi]
0x18001731b  mov     [rax+rcx*4+2], dx
0x180017320  xor     ecx, ecx
0x180017322  jmp     loc_180017125
```
