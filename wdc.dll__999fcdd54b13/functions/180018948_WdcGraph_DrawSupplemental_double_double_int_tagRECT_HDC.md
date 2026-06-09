# WdcGraph::DrawSupplemental(double,double,int,tagRECT,HDC__ *)

- ea: `0x180018948`
- end: `0x180018bec`
- name: `?DrawSupplemental@WdcGraph@@QEAAJNNHUtagRECT@@PEAUHDC__@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(WdcGraph *__hidden this, double, double, int, struct tagRECT *, HDC hdc)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180017fa0`

## callees

- `0x180018948`
- `0x18003a3c0`
- `0x18003b0ac`
- `0x180086010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180018b95`
- `GDI32!DeleteObject` at `0x180018be1`
- `GDI32!DeleteObject` at `0x180018b95`
- `GDI32!DeleteObject` at `0x180018be1`
- `GDI32!CreatePen` at `0x180018ab9`
- `GDI32!CreatePen` at `0x180018b19`
- `GDI32!CreatePen` at `0x180018ab9`
- `GDI32!CreatePen` at `0x180018b19`
- `GDI32!SelectObject` at `0x180018ac8`
- `GDI32!SelectObject` at `0x180018b28`
- `GDI32!SelectObject` at `0x180018ac8`
- `GDI32!SelectObject` at `0x180018b28`
- `GDI32!MoveToEx` at `0x180018add`
- `GDI32!MoveToEx` at `0x180018b3d`
- `GDI32!MoveToEx` at `0x180018add`
- `GDI32!MoveToEx` at `0x180018b3d`
- `GDI32!Polyline` at `0x180018aee`
- `GDI32!Polyline` at `0x180018b4e`
- `GDI32!Polyline` at `0x180018aee`
- `GDI32!Polyline` at `0x180018b4e`

## pseudocode

```c
__int64 __fastcall WdcGraph::DrawSupplemental(
        WdcGraph *this,
        double a2,
        double a3,
        int a4,
        struct tagRECT *a5,
        HDC hdc)
{
  __int64 v6; // rsi
  int v7; // r14d
  int v10; // edi
  __int64 v11; // rbx
  double v12; // xmm2_8
  LONG right; // r10d
  LONG bottom; // r9d
  double v15; // xmm0_8
  double v16; // xmm0_8
  double v17; // xmm0_8
  double v18; // xmm0_8
  HPEN Pen; // rdi
  int v20; // ecx
  __int64 v21; // rax
  HPEN v22; // rdi
  POINT x[64]; // [rsp+30h] [rbp-248h] BYREF

  v6 = *((_QWORD *)this + 45);
  v7 = 0;
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 41) + 24LL))(
           *((_QWORD *)this + 41),
           *((unsigned int *)this + 85),
           v6,
           60);
    if ( v7 != 1 )
    {
      v10 = 60
          * (((int)((unsigned __int64)(2290649225LL * a4) >> 32) >> 5)
           + ((unsigned int)((unsigned __int64)(2290649225LL * a4) >> 32) >> 31)
           + 1)
          - a4;
      if ( v7 < 0 )
        *(_QWORD *)(v6 + 8LL * ((v10 + 1) % 60)) = 0;
      v11 = 0;
      memset_0(x, 0, sizeof(x));
      v12 = WdcGraph::m_AccValSupplemental;
      right = a5->right;
      bottom = a5->bottom;
      do
      {
        v15 = (double)(int)v11 * a2;
        v10 = (v10 + 1) % 60;
        if ( v15 <= 0.0 )
          v16 = v15 - 0.5;
        else
          v16 = v15 + 0.5;
        x[v11].x = right - (int)v16;
        v17 = a3 * *(double *)(v6 + 8LL * v10);
        if ( v17 > 0.0 )
          v18 = v17 + 0.5;
        else
          v18 = v17 - 0.5;
        x[v11].y = bottom - (int)v18 + 2;
        if ( v12 < 0.0 )
          v12 = *(double *)(v6 + 8LL * v10);
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (int)v11 < 59 );
      WdcGraph::m_AccValSupplemental = v12;
      Pen = CreatePen(0, 2, 0x400040u);
      SelectObject(hdc, Pen);
      MoveToEx(hdc, x[0].x, x[0].y, 0);
      Polyline(hdc, x, v11);
      v20 = 0;
      do
      {
        v21 = v20++;
        --x[v21].y;
      }
      while ( v20 < (int)v11 );
      if ( Pen )
        DeleteObject(Pen);
      v22 = CreatePen(0, 2, 0xFF6630u);
      SelectObject(hdc, v22);
      MoveToEx(hdc, x[0].x, x[0].y, 0);
      Polyline(hdc, x, v11);
      if ( v22 )
        DeleteObject(v22);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018948  mov     rax, rsp
0x18001894b  mov     [rax+10h], rbx
0x18001894f  mov     [rax+18h], rbp
0x180018953  push    rsi
0x180018954  push    rdi
0x180018955  push    r14
0x180018957  sub     rsp, 260h
0x18001895e  movaps  xmmword ptr [rax-28h], xmm6
0x180018962  movaps  xmmword ptr [rax-38h], xmm7
0x180018966  mov     rax, cs:__security_cookie
0x18001896d  xor     rax, rsp
0x180018970  mov     [rsp+278h+var_48], rax
0x180018978  mov     rsi, [rcx+168h]
0x18001897f  xor     r14d, r14d
0x180018982  mov     rbp, [rsp+278h+hdc]
0x18001898a  mov     ebx, r9d
0x18001898d  movaps  xmm6, xmm2
0x180018990  movaps  xmm7, xmm1
0x180018993  mov     rdx, rcx
0x180018996  test    rsi, rsi
0x180018999  jz      loc_180018B5D
0x18001899f  mov     rcx, [rcx+148h]
0x1800189a6  lea     r9d, [r14+3Ch]
0x1800189aa  mov     edx, [rdx+154h]
0x1800189b0  mov     r8, rsi
0x1800189b3  mov     rax, [rcx]
0x1800189b6  mov     rax, [rax+18h]
0x1800189ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189bf  mov     r14d, eax
0x1800189c2  cmp     eax, 1
0x1800189c5  jz      loc_180018B5D
0x1800189cb  mov     eax, 88888889h
0x1800189d0  imul    ebx
0x1800189d2  add     edx, ebx
0x1800189d4  sar     edx, 5
0x1800189d7  mov     eax, edx
0x1800189d9  shr     eax, 1Fh
0x1800189dc  inc     eax
0x1800189de  add     eax, edx
0x1800189e0  imul    edi, eax, 3Ch ; '<'
0x1800189e3  sub     edi, ebx
0x1800189e5  test    r14d, r14d
0x1800189e8  js      loc_180018BA9
0x1800189ee  xor     ebx, ebx
0x1800189f0  lea     rcx, [rsp+278h+x]; void *
0x1800189f5  xor     edx, edx; Val
0x1800189f7  mov     r8d, 200h; Size
0x1800189fd  call    memset_0
0x180018a02  mov     rax, [rsp+278h+arg_20]
0x180018a0a  xorps   xmm3, xmm3
0x180018a0d  movsd   xmm1, cs:__real@3fe0000000000000
0x180018a15  movsd   xmm2, cs:?m_AccValSupplemental@WdcGraph@@2NA; double WdcGraph::m_AccValSupplemental
0x180018a1d  mov     r10d, [rax+8]
0x180018a21  mov     r9d, [rax+0Ch]
0x180018a25  inc     edi
0x180018a27  movd    xmm0, ebx
0x180018a2b  mov     eax, 88888889h
0x180018a30  imul    edi
0x180018a32  cvtdq2pd xmm0, xmm0
0x180018a36  add     edx, edi
0x180018a38  sar     edx, 5
0x180018a3b  mov     eax, edx
0x180018a3d  mulsd   xmm0, xmm7
0x180018a41  shr     eax, 1Fh
0x180018a44  add     edx, eax
0x180018a46  imul    eax, edx, 3Ch ; '<'
0x180018a49  sub     edi, eax
0x180018a4b  comisd  xmm0, xmm3
0x180018a4f  jbe     loc_180018BA0
0x180018a55  addsd   xmm0, xmm1
0x180018a59  cvttsd2si rax, xmm0
0x180018a5e  mov     ecx, r10d
0x180018a61  movsxd  rdx, edi
0x180018a64  movaps  xmm0, xmm6
0x180018a67  sub     ecx, eax
0x180018a69  mov     [rsp+rbx*8+278h+x], ecx
0x180018a6d  mulsd   xmm0, qword ptr [rsi+rdx*8]
0x180018a72  comisd  xmm0, xmm3
0x180018a76  ja      short loc_180018A7E
0x180018a78  subsd   xmm0, xmm1
0x180018a7c  jmp     short loc_180018A82
0x180018a7e  addsd   xmm0, xmm1
0x180018a82  cvttsd2si rax, xmm0
0x180018a87  mov     ecx, r9d
0x180018a8a  sub     ecx, eax
0x180018a8c  add     ecx, 2
0x180018a8f  comisd  xmm3, xmm2
0x180018a93  mov     [rsp+rbx*8+278h+y], ecx
0x180018a97  ja      loc_180018BD4
0x180018a9d  inc     ebx
0x180018a9f  cmp     ebx, 3Bh ; ';'
0x180018aa2  jl      short loc_180018A25
0x180018aa4  mov     edx, 2; cWidth
0x180018aa9  movsd   cs:?m_AccValSupplemental@WdcGraph@@2NA, xmm2; double WdcGraph::m_AccValSupplemental
0x180018ab1  xor     ecx, ecx; iStyle
0x180018ab3  mov     r8d, 400040h; color
0x180018ab9  call    cs:__imp_CreatePen
0x180018abf  mov     rdx, rax; h
0x180018ac2  mov     rcx, rbp; hdc
0x180018ac5  mov     rdi, rax
0x180018ac8  call    cs:__imp_SelectObject
0x180018ace  mov     r8d, [rsp+278h+y]; y
0x180018ad3  xor     r9d, r9d; lppt
0x180018ad6  mov     edx, [rsp+278h+x]; x
0x180018ada  mov     rcx, rbp; hdc
0x180018add  call    cs:__imp_MoveToEx
0x180018ae3  mov     r8d, ebx; cpt
0x180018ae6  lea     rdx, [rsp+278h+x]; apt
0x180018aeb  mov     rcx, rbp; hdc
0x180018aee  call    cs:__imp_Polyline
0x180018af4  xor     ecx, ecx
0x180018af6  movsxd  rax, ecx
0x180018af9  inc     ecx
0x180018afb  dec     [rsp+rax*8+278h+y]
0x180018aff  cmp     ecx, ebx
0x180018b01  jl      short loc_180018AF6
0x180018b03  test    rdi, rdi
0x180018b06  jnz     loc_180018B92
0x180018b0c  mov     edx, 2; cWidth
0x180018b11  xor     ecx, ecx; iStyle
0x180018b13  mov     r8d, 0FF6630h; color
0x180018b19  call    cs:__imp_CreatePen
0x180018b1f  mov     rdx, rax; h
0x180018b22  mov     rcx, rbp; hdc
0x180018b25  mov     rdi, rax
0x180018b28  call    cs:__imp_SelectObject
0x180018b2e  mov     r8d, [rsp+278h+y]; y
0x180018b33  xor     r9d, r9d; lppt
0x180018b36  mov     edx, [rsp+278h+x]; x
0x180018b3a  mov     rcx, rbp; hdc
0x180018b3d  call    cs:__imp_MoveToEx
0x180018b43  mov     r8d, ebx; cpt
0x180018b46  lea     rdx, [rsp+278h+x]; apt
0x180018b4b  mov     rcx, rbp; hdc
0x180018b4e  call    cs:__imp_Polyline
0x180018b54  test    rdi, rdi
0x180018b57  jnz     loc_180018BDE
0x180018b5d  mov     eax, r14d
0x180018b60  mov     rcx, [rsp+278h+var_48]
0x180018b68  xor     rcx, rsp; StackCookie
0x180018b6b  call    __security_check_cookie
0x180018b70  lea     r11, [rsp+278h+var_18]
0x180018b78  mov     rbx, [r11+28h]
0x180018b7c  mov     rbp, [r11+30h]
0x180018b80  movaps  xmm6, xmmword ptr [r11-10h]
0x180018b85  movaps  xmm7, xmmword ptr [r11-20h]
0x180018b8a  mov     rsp, r11
0x180018b8d  pop     r14
0x180018b8f  pop     rdi
0x180018b90  pop     rsi
0x180018b91  retn
0x180018b92  mov     rcx, rdi; ho
0x180018b95  call    cs:__imp_DeleteObject
0x180018b9b  jmp     loc_180018B0C
0x180018ba0  subsd   xmm0, xmm1
0x180018ba4  jmp     loc_180018A59
0x180018ba9  lea     ecx, [rdi+1]
0x180018bac  mov     eax, 88888889h
0x180018bb1  imul    ecx
0x180018bb3  add     edx, ecx
0x180018bb5  sar     edx, 5
0x180018bb8  mov     eax, edx
0x180018bba  shr     eax, 1Fh
0x180018bbd  add     edx, eax
0x180018bbf  imul    eax, edx, 3Ch ; '<'
0x180018bc2  sub     ecx, eax
0x180018bc4  movsxd  rax, ecx
0x180018bc7  mov     qword ptr [rsi+rax*8], 0
0x180018bcf  jmp     loc_1800189EE
0x180018bd4  movsd   xmm2, qword ptr [rsi+rdx*8]
0x180018bd9  jmp     loc_180018A9D
0x180018bde  mov     rcx, rdi; ho
0x180018be1  call    cs:__imp_DeleteObject
0x180018be7  jmp     loc_180018B5D
```
