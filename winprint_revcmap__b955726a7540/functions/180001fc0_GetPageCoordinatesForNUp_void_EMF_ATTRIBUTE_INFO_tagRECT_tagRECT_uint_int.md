# GetPageCoordinatesForNUp(void *,_EMF_ATTRIBUTE_INFO *,tagRECT *,tagRECT *,uint,int *)

- ea: `0x180001fc0`
- end: `0x1800023e7`
- name: `?GetPageCoordinatesForNUp@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@PEAUtagRECT@@2IPEAH@Z`
- size: `1063`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, struct _EMF_ATTRIBUTE_INFO *@<rdx>, struct tagRECT *@<r8>, struct tagRECT *@<r9>, unsigned int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800017d0`
- `0x180001d60`

## callees

- `0x180001fc0`
- `0x180006280`
- `0x180006470`
- `0x180006554`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x1800022d7`
- `GDI32!GetDeviceCaps` at `0x1800022e7`
- `GDI32!GetDeviceCaps` at `0x1800022d7`
- `GDI32!GetDeviceCaps` at `0x1800022e7`

## pseudocode

```c
__int64 __fastcall GetPageCoordinatesForNUp(
        HDC hdc,
        struct _EMF_ATTRIBUTE_INFO *a2,
        struct tagRECT *a3,
        struct tagRECT *a4,
        unsigned int a5,
        int *a6)
{
  int *v6; // rsi
  unsigned int v9; // edx
  __int64 result; // rax
  int v13; // r13d
  unsigned int v14; // r15d
  int v15; // r12d
  int v16; // r11d
  unsigned int v17; // r10d
  int v18; // r12d
  int v19; // eax
  int v20; // r15d
  char RotatePageCoordinate; // al
  int v22; // r8d
  int v23; // ecx
  int v24; // edx
  double v25; // xmm1_8
  int v26; // eax
  int v27; // ecx
  double v28; // xmm1_8
  LONG v29; // r10d
  int v30; // eax
  double v31; // xmm7_8
  double v32; // xmm6_8
  int v33; // edx
  int v34; // ecx
  int v35; // r15d
  int DeviceCaps; // ebx
  int v37; // eax
  LONG right; // edx
  LONG top; // r10d
  double v40; // xmm3_8
  double v41; // xmm5_8
  double v42; // xmm1_8
  double v43; // xmm4_8
  double v44; // xmm7_8
  double v45; // xmm0_8
  double v46; // xmm2_8
  double v47; // xmm1_8
  int v48; // eax
  double v49; // xmm2_8
  double v50; // xmm0_8
  LONG v51; // ecx
  unsigned int v52; // [rsp+30h] [rbp-68h]
  int v53; // [rsp+34h] [rbp-64h]
  unsigned int v54; // [rsp+38h] [rbp-60h]
  int v55; // [rsp+3Ch] [rbp-5Ch]
  int v56; // [rsp+40h] [rbp-58h] BYREF
  int v57; // [rsp+44h] [rbp-54h]
  int v58; // [rsp+A8h] [rbp+10h] BYREF

  v6 = a6;
  v9 = *((_DWORD *)a2 + 8);
  *a6 = 0;
  if ( v9 == 1 )
  {
    *(_QWORD *)&a3->left = 0;
    a3->bottom = *((_DWORD *)a2 + 6);
    a3->right = *((_DWORD *)a2 + 5);
    return 1;
  }
  v13 = *((_DWORD *)a2 + 3);
  if ( !v13 )
    return 0;
  v55 = *((_DWORD *)a2 + 4);
  if ( !v55 )
    return 0;
  v14 = *((_DWORD *)a2 + 6) - 1;
  v15 = *((_DWORD *)a2 + 5) - 1;
  v54 = v14;
  v53 = v15;
  CNupLayout::CNupLayout((CNupLayout *)&v56, v9, v15 > (int)v14);
  if ( !v57 || !v56 )
    return 0;
  v17 = *((_DWORD *)a2 + 15);
  v52 = a5 - 1;
  v18 = v15 / (unsigned int)v57;
  v19 = v14 / v56;
  v20 = v14 / v56;
  if ( v13 < v16 )
  {
    if ( v18 >= v20 )
      goto LABEL_9;
  }
  else if ( v18 < v19 )
  {
LABEL_9:
    *v6 = 1;
    LODWORD(a6) = 0;
    v58 = 0;
    RotatePageCoordinate = CNupLayout::GetRotatePageCoordinate(&v56, v52, v17, &a6, &v58);
    v22 = 1;
    goto LABEL_10;
  }
  *v6 = 0;
  LODWORD(a6) = 0;
  v58 = 0;
  RotatePageCoordinate = CNupLayout::GetPageCoordinate(&v56, v52, v17, &a6, &v58);
  v22 = 0;
LABEL_10:
  if ( !RotatePageCoordinate )
    return 0;
  v23 = (int)a6;
  v24 = *((_DWORD *)a2 + 10);
  v25 = (double)v57;
  a3->left = (int)((double)((int)a6 * v53) / (double)v57);
  v26 = v53 * (v23 + 1);
  v27 = v58;
  a3->right = (int)((double)v26 / v25);
  v28 = (double)v56;
  v29 = (int)((double)(int)(v27 * v54) / (double)v56);
  a3->top = v29;
  a3->bottom = (int)((double)(int)(v54 * (v27 + 1)) / v28);
  if ( !v24 && a4 )
  {
    a4->top = v29;
    a4->bottom = a3->bottom - 1;
    a4->left = a3->left;
    a4->right = a3->right - 1;
  }
  v30 = v18;
  if ( v22 )
  {
    v30 = v20;
    v20 = v18;
  }
  v31 = (double)v13;
  v32 = (double)v55;
  v33 = (int)((double)v13 / (double)v55 * (double)v20);
  if ( v33 < v30 )
  {
    v35 = 0;
    v34 = v30 - v33;
  }
  else
  {
    v34 = 0;
    v35 = v20 - (int)(v32 / v31 * (double)v30);
  }
  if ( v22 )
  {
    if ( v34 )
    {
      a3->bottom -= v34 / 2;
      a3->top += v34 / 2;
    }
    else
    {
      a3->right -= v35 / 2;
      a3->left += v35 / 2;
    }
  }
  else if ( v34 )
  {
    a3->left += v34 / 2;
    a3->right -= v34 / 2;
  }
  else
  {
    a3->top += v35 / 2;
    a3->bottom -= v35 / 2;
  }
  DeviceCaps = GetDeviceCaps(hdc, 112);
  v37 = GetDeviceCaps(hdc, 113);
  right = a3->right;
  top = a3->top;
  v40 = (double)DeviceCaps / v31;
  v41 = (double)(v13 - v53 - DeviceCaps) / v31;
  v42 = (double)(a3->bottom - top);
  v43 = (double)v37 / v32;
  v44 = (double)(int)(v55 - v54 - v37) / v32;
  v45 = v42;
  v46 = (double)(right - a3->left);
  if ( *v6 )
  {
    v47 = v42 * v41;
    v48 = (int)(v45 * v40);
    v49 = v46 * v43;
    v50 = (double)(a3->right - a3->left) * v44;
  }
  else
  {
    v47 = v42 * v43;
    v48 = (int)(v45 * v44);
    v49 = v46 * v40;
    v50 = (double)(a3->right - a3->left) * v41;
  }
  v51 = a3->bottom - v48;
  a3->left += (int)v49;
  result = 1;
  a3->right = right - (int)v50;
  a3->top = top + (int)v47;
  a3->bottom = v51;
  return result;
}

```

## disassembly

```asm
0x180001fc0  push    rbx
0x180001fc2  push    rbp
0x180001fc3  push    rsi
0x180001fc4  push    rdi
0x180001fc5  push    r14
0x180001fc7  sub     rsp, 70h
0x180001fcb  mov     rsi, [rsp+98h+arg_28]
0x180001fd3  xor     eax, eax
0x180001fd5  mov     rbx, rdx
0x180001fd8  mov     r14, r9
0x180001fdb  mov     edx, [rdx+20h]; unsigned int
0x180001fde  mov     rdi, r8
0x180001fe1  mov     rbp, rcx
0x180001fe4  mov     [rsi], eax
0x180001fe6  cmp     edx, 1
0x180001fe9  jnz     short loc_180002009
0x180001feb  mov     [r8], rax
0x180001fee  mov     eax, [rbx+18h]
0x180001ff1  mov     [r8+0Ch], eax
0x180001ff5  mov     eax, [rbx+14h]
0x180001ff8  mov     [r8+8], eax
0x180001ffc  mov     eax, edx
0x180001ffe  add     rsp, 70h
0x180002002  pop     r14
0x180002004  pop     rdi
0x180002005  pop     rsi
0x180002006  pop     rbp
0x180002007  pop     rbx
0x180002008  retn
0x180002009  mov     [rsp+98h+arg_0], r12
0x180002011  mov     [rsp+98h+arg_10], r13
0x180002019  mov     r13d, [rbx+0Ch]
0x18000201d  mov     [rsp+98h+arg_18], r15
0x180002025  test    r13d, r13d
0x180002028  jz      loc_1800023C2
0x18000202e  mov     r11d, [rbx+10h]
0x180002032  mov     [rsp+98h+var_5C], r11d
0x180002037  test    r11d, r11d
0x18000203a  jz      loc_1800023C2
0x180002040  mov     r15d, [rbx+18h]
0x180002044  lea     rcx, [rsp+98h+var_58]; this
0x180002049  mov     r12d, [rbx+14h]
0x18000204d  dec     r15d
0x180002050  dec     r12d
0x180002053  mov     [rsp+98h+var_60], r15d
0x180002058  cmp     r12d, r15d
0x18000205b  mov     [rsp+98h+var_64], r12d
0x180002060  setnle  r8b; bool
0x180002064  call    ??0CNupLayout@@QEAA@I_N@Z; CNupLayout::CNupLayout(uint,bool)
0x180002069  mov     r8d, [rsp+98h+var_54]
0x18000206e  cmp     r8d, 1
0x180002072  jb      loc_1800023C2
0x180002078  mov     ecx, [rsp+98h+var_58]
0x18000207c  cmp     ecx, 1
0x18000207f  jb      loc_1800023C2
0x180002085  mov     eax, [rsp+98h+arg_20]
0x18000208c  xor     edx, edx
0x18000208e  mov     r10d, [rbx+3Ch]
0x180002092  dec     eax
0x180002094  mov     [rsp+98h+var_68], eax
0x180002098  mov     eax, r12d
0x18000209b  div     r8d
0x18000209e  xor     edx, edx
0x1800020a0  mov     r12d, eax
0x1800020a3  mov     eax, r15d
0x1800020a6  div     ecx
0x1800020a8  mov     r15d, eax
0x1800020ab  cmp     r13d, r11d
0x1800020ae  jl      loc_18000222E
0x1800020b4  cmp     r12d, eax
0x1800020b7  jge     loc_180002237
0x1800020bd  mov     edx, [rsp+98h+var_68]
0x1800020c1  lea     rax, [rsp+98h+arg_8]
0x1800020c9  lea     r9, [rsp+98h+arg_28]
0x1800020d1  mov     [rsp+98h+var_78], rax
0x1800020d6  mov     r8d, r10d
0x1800020d9  mov     dword ptr [rsi], 1
0x1800020df  lea     rcx, [rsp+98h+var_58]
0x1800020e4  mov     dword ptr [rsp+98h+arg_28], 0
0x1800020ef  mov     [rsp+98h+arg_8], 0
0x1800020fa  call    ?GetRotatePageCoordinate@CNupLayout@@QEBA_NIW4_ENupDirection@@PEAI1@Z; CNupLayout::GetRotatePageCoordinate(uint,_ENupDirection,uint *,uint *)
0x1800020ff  mov     r8d, 1
0x180002105  test    al, al
0x180002107  jz      loc_1800023C2
0x18000210d  mov     eax, [rsp+98h+var_54]
0x180002111  xorps   xmm0, xmm0
0x180002114  mov     ecx, dword ptr [rsp+98h+arg_28]
0x18000211b  xorps   xmm1, xmm1
0x18000211e  mov     edx, [rbx+28h]
0x180002121  movaps  [rsp+98h+var_38], xmm6
0x180002126  cvtsi2sd xmm1, rax
0x18000212b  mov     eax, [rsp+98h+var_64]
0x18000212f  imul    eax, ecx
0x180002132  movaps  [rsp+98h+var_48], xmm7
0x180002137  cvtsi2sd xmm0, rax
0x18000213c  divsd   xmm0, xmm1
0x180002140  cvttsd2si eax, xmm0
0x180002144  xorps   xmm0, xmm0
0x180002147  mov     [rdi], eax
0x180002149  lea     eax, [rcx+1]
0x18000214c  imul    eax, [rsp+98h+var_64]
0x180002151  mov     ecx, [rsp+98h+arg_8]
0x180002158  cvtsi2sd xmm0, rax
0x18000215d  divsd   xmm0, xmm1
0x180002161  xorps   xmm1, xmm1
0x180002164  cvttsd2si eax, xmm0
0x180002168  xorps   xmm0, xmm0
0x18000216b  mov     [rdi+8], eax
0x18000216e  mov     eax, [rsp+98h+var_58]
0x180002172  cvtsi2sd xmm1, rax
0x180002177  mov     eax, [rsp+98h+var_60]
0x18000217b  imul    eax, ecx
0x18000217e  cvtsi2sd xmm0, rax
0x180002183  lea     eax, [rcx+1]
0x180002186  imul    eax, [rsp+98h+var_60]
0x18000218b  divsd   xmm0, xmm1
0x18000218f  cvttsd2si r10d, xmm0
0x180002194  xorps   xmm0, xmm0
0x180002197  mov     [rdi+4], r10d
0x18000219b  cvtsi2sd xmm0, rax
0x1800021a0  divsd   xmm0, xmm1
0x1800021a4  cvttsd2si eax, xmm0
0x1800021a8  mov     [rdi+0Ch], eax
0x1800021ab  test    edx, edx
0x1800021ad  jnz     short loc_1800021CF
0x1800021af  test    r14, r14
0x1800021b2  jz      short loc_1800021CF
0x1800021b4  mov     [r14+4], r10d
0x1800021b8  mov     eax, [rdi+0Ch]
0x1800021bb  dec     eax
0x1800021bd  mov     [r14+0Ch], eax
0x1800021c1  mov     eax, [rdi]
0x1800021c3  mov     [r14], eax
0x1800021c6  mov     eax, [rdi+8]
0x1800021c9  dec     eax
0x1800021cb  mov     [r14+8], eax
0x1800021cf  mov     eax, r12d
0x1800021d2  test    r8d, r8d
0x1800021d5  jz      short loc_1800021DD
0x1800021d7  mov     eax, r15d
0x1800021da  mov     r15d, r12d
0x1800021dd  mov     r14d, [rsp+98h+var_5C]
0x1800021e2  movd    xmm7, r13d
0x1800021e7  cvtdq2pd xmm7, xmm7
0x1800021eb  movd    xmm6, r14d
0x1800021f0  cvtdq2pd xmm6, xmm6
0x1800021f4  movaps  xmm1, xmm7
0x1800021f7  movd    xmm0, r15d
0x1800021fc  divsd   xmm1, xmm6
0x180002200  cvtdq2pd xmm0, xmm0
0x180002204  mulsd   xmm1, xmm0
0x180002208  cvttsd2si edx, xmm1
0x18000220c  cmp     edx, eax
0x18000220e  jl      short loc_180002281
0x180002210  movaps  xmm1, xmm6
0x180002213  movd    xmm0, eax
0x180002217  divsd   xmm1, xmm7
0x18000221b  xor     ecx, ecx
0x18000221d  cvtdq2pd xmm0, xmm0
0x180002221  mulsd   xmm1, xmm0
0x180002225  cvttsd2si eax, xmm1
0x180002229  sub     r15d, eax
0x18000222c  jmp     short loc_180002288
0x18000222e  cmp     r12d, r15d
0x180002231  jge     loc_1800020BD
0x180002237  mov     edx, [rsp+98h+var_68]
0x18000223b  lea     rax, [rsp+98h+arg_8]
0x180002243  lea     r9, [rsp+98h+arg_28]
0x18000224b  mov     [rsp+98h+var_78], rax
0x180002250  mov     r8d, r10d
0x180002253  mov     dword ptr [rsi], 0
0x180002259  lea     rcx, [rsp+98h+var_58]
0x18000225e  mov     dword ptr [rsp+98h+arg_28], 0
0x180002269  mov     [rsp+98h+arg_8], 0
0x180002274  call    ?GetPageCoordinate@CNupLayout@@QEBA_NIW4_ENupDirection@@PEAI1@Z; CNupLayout::GetPageCoordinate(uint,_ENupDirection,uint *,uint *)
0x180002279  xor     r8d, r8d
0x18000227c  jmp     loc_180002105
0x180002281  xor     r15d, r15d
0x180002284  mov     ecx, eax
0x180002286  sub     ecx, edx
0x180002288  test    r8d, r8d
0x18000228b  jz      short loc_1800022AF
0x18000228d  test    ecx, ecx
0x18000228f  jz      short loc_1800022A0
0x180002291  mov     eax, ecx
0x180002293  cdq
0x180002294  sub     eax, edx
0x180002296  sar     eax, 1
0x180002298  sub     [rdi+0Ch], eax
0x18000229b  add     [rdi+4], eax
0x18000229e  jmp     short loc_1800022CF
0x1800022a0  mov     eax, r15d
0x1800022a3  cdq
0x1800022a4  sub     eax, edx
0x1800022a6  sar     eax, 1
0x1800022a8  sub     [rdi+8], eax
0x1800022ab  add     [rdi], eax
0x1800022ad  jmp     short loc_1800022CF
0x1800022af  test    ecx, ecx
0x1800022b1  jz      short loc_1800022C1
0x1800022b3  mov     eax, ecx
0x1800022b5  cdq
0x1800022b6  sub     eax, edx
0x1800022b8  sar     eax, 1
0x1800022ba  add     [rdi], eax
0x1800022bc  sub     [rdi+8], eax
0x1800022bf  jmp     short loc_1800022CF
0x1800022c1  mov     eax, r15d
0x1800022c4  cdq
0x1800022c5  sub     eax, edx
0x1800022c7  sar     eax, 1
0x1800022c9  add     [rdi+4], eax
0x1800022cc  sub     [rdi+0Ch], eax
0x1800022cf  mov     edx, 70h ; 'p'; index
0x1800022d4  mov     rcx, rbp; hdc
0x1800022d7  call    cs:__imp_GetDeviceCaps
0x1800022dd  mov     edx, 71h ; 'q'; index
0x1800022e2  mov     rcx, rbp; hdc
0x1800022e5  mov     ebx, eax
0x1800022e7  call    cs:__imp_GetDeviceCaps
0x1800022ed  sub     r13d, [rsp+98h+var_64]
0x1800022f2  sub     r14d, [rsp+98h+var_60]
0x1800022f7  sub     r13d, ebx
0x1800022fa  mov     edx, [rdi+8]
0x1800022fd  sub     r14d, eax
0x180002300  mov     r9d, [rdi]
0x180002303  mov     ecx, [rdi+0Ch]
0x180002306  mov     r10d, [rdi+4]
0x18000230a  movd    xmm4, eax
0x18000230e  mov     eax, edx
0x180002310  sub     eax, r9d
0x180002313  movd    xmm3, ebx
0x180002317  movd    xmm5, r13d
0x18000231c  cvtdq2pd xmm3, xmm3
0x180002320  movd    xmm2, eax
0x180002324  mov     eax, ecx
0x180002326  divsd   xmm3, xmm7
0x18000232a  sub     eax, r10d
0x18000232d  cmp     dword ptr [rsi], 0
0x180002330  cvtdq2pd xmm5, xmm5
0x180002334  movd    xmm1, eax
0x180002338  divsd   xmm5, xmm7
0x18000233c  movd    xmm7, r14d
0x180002341  cvtdq2pd xmm4, xmm4
0x180002345  cvtdq2pd xmm7, xmm7
0x180002349  cvtdq2pd xmm1, xmm1
0x18000234d  divsd   xmm4, xmm6
0x180002351  divsd   xmm7, xmm6
0x180002355  movaps  xmm6, [rsp+98h+var_38]
0x18000235a  movaps  xmm0, xmm1
0x18000235d  cvtdq2pd xmm2, xmm2
0x180002361  jz      short loc_18000237C
0x180002363  mulsd   xmm0, xmm3
0x180002367  mulsd   xmm1, xmm5
0x18000236b  cvttsd2si eax, xmm0
0x18000236f  movaps  xmm0, xmm2
0x180002372  mulsd   xmm2, xmm4
0x180002376  mulsd   xmm0, xmm7
0x18000237a  jmp     short loc_180002393
0x18000237c  mulsd   xmm0, xmm7
0x180002380  mulsd   xmm1, xmm4
0x180002384  cvttsd2si eax, xmm0
0x180002388  movaps  xmm0, xmm2
0x18000238b  mulsd   xmm2, xmm3
0x18000238f  mulsd   xmm0, xmm5
0x180002393  sub     ecx, eax
0x180002395  cvttsd2si eax, xmm0
0x180002399  cvttsd2si r8d, xmm1
0x18000239e  sub     edx, eax
0x1800023a0  cvttsd2si eax, xmm2
0x1800023a4  add     r8d, r10d
0x1800023a7  add     eax, r9d
0x1800023aa  mov     [rdi], eax
0x1800023ac  mov     eax, 1
0x1800023b1  mov     [rdi+8], edx
0x1800023b4  mov     [rdi+4], r8d
0x1800023b8  mov     [rdi+0Ch], ecx
0x1800023bb  movaps  xmm7, [rsp+98h+var_48]
0x1800023c0  jmp     short loc_1800023C4
0x1800023c2  xor     eax, eax
0x1800023c4  mov     r13, [rsp+98h+arg_10]
0x1800023cc  mov     r12, [rsp+98h+arg_0]
0x1800023d4  mov     r15, [rsp+98h+arg_18]
0x1800023dc  add     rsp, 70h
0x1800023e0  pop     r14
0x1800023e2  pop     rdi
0x1800023e3  pop     rsi
0x1800023e4  pop     rbp
0x1800023e5  pop     rbx
0x1800023e6  retn
```
