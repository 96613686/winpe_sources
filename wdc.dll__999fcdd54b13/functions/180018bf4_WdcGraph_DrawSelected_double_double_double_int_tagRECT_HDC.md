# WdcGraph::DrawSelected(double,double,double,int,tagRECT,HDC__ *)

- ea: `0x180018bf4`
- end: `0x180018ebd`
- name: `?DrawSelected@WdcGraph@@QEAAJNNNHUtagRECT@@PEAUHDC__@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(WdcGraph *__hidden this, double, double, double, int, struct tagRECT *, HDC hdc)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017fa0`

## callees

- `0x18000b854`
- `0x180015100`
- `0x180018bf4`
- `0x18003a3c0`
- `0x18003b0ac`
- `0x180086010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180018e7d`
- `GDI32!DeleteObject` at `0x180018e7d`
- `GDI32!CreatePen` at `0x180018e3a`
- `GDI32!CreatePen` at `0x180018e3a`
- `GDI32!SelectObject` at `0x180018e49`
- `GDI32!SelectObject` at `0x180018e49`
- `GDI32!MoveToEx` at `0x180018e5e`
- `GDI32!MoveToEx` at `0x180018e5e`
- `GDI32!Polyline` at `0x180018e6f`
- `GDI32!Polyline` at `0x180018e6f`

## pseudocode

```c
__int64 __fastcall WdcGraph::DrawSelected(
        WdcGraph *this,
        double a2,
        double a3,
        double a4,
        int a5,
        struct tagRECT *a6,
        HDC hdc)
{
  double *v7; // rsi
  int v8; // edi
  double v9; // xmm7_8
  int v11; // r8d
  int v12; // r14d
  int v13; // edx
  int v14; // eax
  __int64 v15; // rbp
  double v16; // xmm2_8
  LONG right; // r10d
  LONG bottom; // r9d
  double v19; // xmm0_8
  double v20; // xmm0_8
  double v21; // xmm0_8
  double v22; // xmm0_8
  HPEN Pen; // rbx
  __int64 v25; // [rsp+20h] [rbp-2A8h]
  POINT x[64]; // [rsp+40h] [rbp-288h] BYREF

  v7 = (double *)*((_QWORD *)this + 46);
  v8 = 0;
  v9 = a3;
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, double *, __int64))(**((_QWORD **)this + 41) + 24LL))(
           *((_QWORD *)this + 41),
           *((unsigned int *)this + 86),
           v7,
           60);
    if ( v8 != 1 )
    {
      v12 = 60
          * (((int)((unsigned __int64)(2290649225LL * a5) >> 32) >> 5)
           + ((unsigned int)((unsigned __int64)(2290649225LL * a5) >> 32) >> 31)
           + 1)
          - a5;
      if ( v8 < 0 )
        v7[(v12 + 1) % 60] = 0.0;
      if ( a3 == 0.0 )
      {
        v13 = *((_DWORD *)this + 98);
        if ( v13 > 1 )
        {
          v14 = WdcGraph::DataAutoScale(
                  (WdcGraph *)((char *)this + 396),
                  v7,
                  v11,
                  *((const struct _WDC_SCALE **)this + 48),
                  v13,
                  *((_DWORD *)this + 100),
                  (int *)this + 99,
                  (unsigned int *)this + 94);
          v8 = v14;
          if ( v14 < 0 )
          {
            LODWORD(v25) = v14;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\graph.cpp",
              "WdcGraph::DrawSelected",
              0,
              L"FAILURE: 0x%08x",
              v25);
            return (unsigned int)v8;
          }
        }
        v9 = *(double *)(32LL * *((int *)this + 99) + *((_QWORD *)this + 48));
      }
      v15 = 0;
      memset_0(x, 0, sizeof(x));
      v16 = WdcGraph::m_AccValSelected;
      right = a6->right;
      bottom = a6->bottom;
      do
      {
        v19 = (double)(int)v15 * a2;
        v12 = (v12 + 1) % 60;
        if ( v19 <= 0.0 )
          v20 = v19 - 0.5;
        else
          v20 = v19 + 0.5;
        x[v15].x = right - (int)v20;
        v21 = v9 * v7[v12] * a4;
        if ( v21 <= 0.0 )
          v22 = v21 - 0.5;
        else
          v22 = v21 + 0.5;
        x[v15].y = bottom - (int)v22 + 2;
        if ( v16 < 0.0 )
          v16 = v7[v12];
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (int)v15 < 59 );
      WdcGraph::m_AccValSelected = v16;
      Pen = CreatePen(0, 2, 0x884FFu);
      SelectObject(hdc, Pen);
      MoveToEx(hdc, x[0].x, x[0].y, 0);
      Polyline(hdc, x, v15);
      if ( Pen )
        DeleteObject(Pen);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018bf4  mov     rax, rsp
0x180018bf7  push    rbx
0x180018bf8  push    rbp
0x180018bf9  push    rsi
0x180018bfa  push    rdi
0x180018bfb  push    r14
0x180018bfd  push    r15
0x180018bff  sub     rsp, 298h
0x180018c06  movaps  xmmword ptr [rax-48h], xmm6
0x180018c0a  movaps  xmmword ptr [rax-58h], xmm7
0x180018c0e  movaps  xmmword ptr [rax-68h], xmm8
0x180018c13  movaps  xmmword ptr [rax-78h], xmm9
0x180018c18  mov     rax, cs:__security_cookie
0x180018c1f  xor     rax, rsp
0x180018c22  mov     [rsp+2C8h+var_88], rax
0x180018c2a  mov     rsi, [rcx+170h]
0x180018c31  xor     edi, edi
0x180018c33  mov     r15, [rsp+2C8h+hdc]
0x180018c3b  movaps  xmm8, xmm3
0x180018c3f  movaps  xmm7, xmm2
0x180018c42  movaps  xmm9, xmm1
0x180018c46  mov     rbx, rcx
0x180018c49  test    rsi, rsi
0x180018c4c  jz      loc_180018E83
0x180018c52  mov     rcx, [rcx+148h]
0x180018c59  lea     r9d, [rdi+3Ch]
0x180018c5d  mov     edx, [rbx+158h]
0x180018c63  mov     r8, rsi
0x180018c66  mov     rax, [rcx]
0x180018c69  mov     rax, [rax+18h]
0x180018c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c72  mov     edi, eax
0x180018c74  cmp     eax, 1
0x180018c77  jz      loc_180018E83
0x180018c7d  mov     ecx, [rsp+2C8h+arg_20]
0x180018c84  mov     eax, 88888889h
0x180018c89  imul    ecx
0x180018c8b  add     edx, ecx
0x180018c8d  sar     edx, 5
0x180018c90  mov     eax, edx
0x180018c92  shr     eax, 1Fh
0x180018c95  inc     eax
0x180018c97  add     eax, edx
0x180018c99  imul    r14d, eax, 3Ch ; '<'
0x180018c9d  sub     r14d, ecx
0x180018ca0  test    edi, edi
0x180018ca2  jns     short loc_180018CCB
0x180018ca4  lea     ecx, [r14+1]
0x180018ca8  mov     eax, 88888889h
0x180018cad  imul    ecx
0x180018caf  add     edx, ecx
0x180018cb1  sar     edx, 5
0x180018cb4  mov     eax, edx
0x180018cb6  shr     eax, 1Fh
0x180018cb9  add     edx, eax
0x180018cbb  imul    eax, edx, 3Ch ; '<'
0x180018cbe  sub     ecx, eax
0x180018cc0  movsxd  rax, ecx
0x180018cc3  mov     qword ptr [rsi+rax*8], 0
0x180018ccb  xorps   xmm6, xmm6
0x180018cce  ucomisd xmm6, xmm7
0x180018cd2  jp      loc_180018D61
0x180018cd8  jnz     loc_180018D61
0x180018cde  mov     edx, [rbx+188h]
0x180018ce4  cmp     edx, 1
0x180018ce7  jle     short loc_180018D4A
0x180018ce9  mov     r9, [rbx+180h]; struct _WDC_SCALE *
0x180018cf0  lea     rax, [rbx+178h]
0x180018cf7  mov     [rsp+2C8h+var_290], rax; unsigned int *
0x180018cfc  lea     rcx, [rbx+18Ch]; this
0x180018d03  mov     eax, [rbx+190h]
0x180018d09  mov     [rsp+2C8h+var_298], rcx; int *
0x180018d0e  mov     [rsp+2C8h+var_2A0], eax; int
0x180018d12  mov     dword ptr [rsp+2C8h+var_2A8], edx; int
0x180018d16  mov     rdx, rsi; double *
0x180018d19  call    ?DataAutoScale@WdcGraph@@QEAAJPEANHPEBU_WDC_SCALE@@HHPEAHPEAK@Z; WdcGraph::DataAutoScale(double *,int,_WDC_SCALE const *,int,int,int *,ulong *)
0x180018d1e  mov     edi, eax
0x180018d20  test    eax, eax
0x180018d22  jns     short loc_180018D4A
0x180018d24  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180018d2b  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x180018d2f  xor     r8d, r8d; int
0x180018d32  lea     rdx, aWdcgraphDrawse; "WdcGraph::DrawSelected"
0x180018d39  lea     rcx, aBaseDiagnosisP_49; "base\\diagnosis\\pdui\\perfmon\\mon\\gr"...
0x180018d40  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180018d45  jmp     loc_180018E83
0x180018d4a  movsxd  rcx, dword ptr [rbx+18Ch]
0x180018d51  mov     rax, [rbx+180h]
0x180018d58  shl     rcx, 5
0x180018d5c  movsd   xmm7, qword ptr [rcx+rax]
0x180018d61  xor     ebp, ebp
0x180018d63  lea     rcx, [rsp+2C8h+x]; void *
0x180018d68  xor     edx, edx; Val
0x180018d6a  mov     r8d, 200h; Size
0x180018d70  call    memset_0
0x180018d75  mov     rax, [rsp+2C8h+arg_28]
0x180018d7d  movsd   xmm1, cs:__real@3fe0000000000000
0x180018d85  movsd   xmm2, cs:?m_AccValSelected@WdcGraph@@2NA; double WdcGraph::m_AccValSelected
0x180018d8d  mov     r10d, [rax+8]
0x180018d91  mov     r9d, [rax+0Ch]
0x180018d95  inc     r14d
0x180018d98  movd    xmm0, ebp
0x180018d9c  mov     eax, 88888889h
0x180018da1  imul    r14d
0x180018da4  cvtdq2pd xmm0, xmm0
0x180018da8  add     edx, r14d
0x180018dab  sar     edx, 5
0x180018dae  mov     eax, edx
0x180018db0  mulsd   xmm0, xmm9
0x180018db5  shr     eax, 1Fh
0x180018db8  add     edx, eax
0x180018dba  imul    eax, edx, 3Ch ; '<'
0x180018dbd  sub     r14d, eax
0x180018dc0  comisd  xmm0, xmm6
0x180018dc4  jbe     short loc_180018DCC
0x180018dc6  addsd   xmm0, xmm1
0x180018dca  jmp     short loc_180018DD0
0x180018dcc  subsd   xmm0, xmm1
0x180018dd0  cvttsd2si rax, xmm0
0x180018dd5  mov     ecx, r10d
0x180018dd8  movsxd  rdx, r14d
0x180018ddb  movaps  xmm0, xmm7
0x180018dde  sub     ecx, eax
0x180018de0  mov     [rsp+rbp*8+2C8h+x], ecx
0x180018de4  mulsd   xmm0, qword ptr [rsi+rdx*8]
0x180018de9  mulsd   xmm0, xmm8
0x180018dee  comisd  xmm0, xmm6
0x180018df2  jbe     short loc_180018DFA
0x180018df4  addsd   xmm0, xmm1
0x180018df8  jmp     short loc_180018DFE
0x180018dfa  subsd   xmm0, xmm1
0x180018dfe  cvttsd2si rax, xmm0
0x180018e03  mov     ecx, r9d
0x180018e06  sub     ecx, eax
0x180018e08  add     ecx, 2
0x180018e0b  comisd  xmm6, xmm2
0x180018e0f  mov     [rsp+rbp*8+2C8h+y], ecx
0x180018e13  jbe     short loc_180018E1A
0x180018e15  movsd   xmm2, qword ptr [rsi+rdx*8]
0x180018e1a  inc     ebp
0x180018e1c  cmp     ebp, 3Bh ; ';'
0x180018e1f  jl      loc_180018D95
0x180018e25  mov     edx, 2; cWidth
0x180018e2a  movsd   cs:?m_AccValSelected@WdcGraph@@2NA, xmm2; double WdcGraph::m_AccValSelected
0x180018e32  xor     ecx, ecx; iStyle
0x180018e34  mov     r8d, 884FFh; color
0x180018e3a  call    cs:__imp_CreatePen
0x180018e40  mov     rdx, rax; h
0x180018e43  mov     rcx, r15; hdc
0x180018e46  mov     rbx, rax
0x180018e49  call    cs:__imp_SelectObject
0x180018e4f  mov     r8d, [rsp+2C8h+y]; y
0x180018e54  xor     r9d, r9d; lppt
0x180018e57  mov     edx, [rsp+2C8h+x]; x
0x180018e5b  mov     rcx, r15; hdc
0x180018e5e  call    cs:__imp_MoveToEx
0x180018e64  mov     r8d, ebp; cpt
0x180018e67  lea     rdx, [rsp+2C8h+x]; apt
0x180018e6c  mov     rcx, r15; hdc
0x180018e6f  call    cs:__imp_Polyline
0x180018e75  test    rbx, rbx
0x180018e78  jz      short loc_180018E83
0x180018e7a  mov     rcx, rbx; ho
0x180018e7d  call    cs:__imp_DeleteObject
0x180018e83  mov     eax, edi
0x180018e85  mov     rcx, [rsp+2C8h+var_88]
0x180018e8d  xor     rcx, rsp; StackCookie
0x180018e90  call    __security_check_cookie
0x180018e95  lea     r11, [rsp+2C8h+var_30]
0x180018e9d  movaps  xmm6, xmmword ptr [r11-18h]
0x180018ea2  movaps  xmm7, xmmword ptr [r11-28h]
0x180018ea7  movaps  xmm8, xmmword ptr [r11-38h]
0x180018eac  movaps  xmm9, xmmword ptr [r11-48h]
0x180018eb1  mov     rsp, r11
0x180018eb4  pop     r15
0x180018eb6  pop     r14
0x180018eb8  pop     rdi
0x180018eb9  pop     rsi
0x180018eba  pop     rbp
0x180018ebb  pop     rbx
0x180018ebc  retn
```
