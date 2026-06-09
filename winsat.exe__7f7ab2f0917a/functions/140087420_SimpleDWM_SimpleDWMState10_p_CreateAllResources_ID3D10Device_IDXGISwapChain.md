# SimpleDWM::SimpleDWMState10::p_CreateAllResources(ID3D10Device *,IDXGISwapChain *)

- ea: `0x140087420`
- end: `0x140087c3a`
- name: `?p_CreateAllResources@SimpleDWMState10@SimpleDWM@@QEAAJPEAUID3D10Device@@PEAUIDXGISwapChain@@@Z`
- size: `2074`
- prototype: `int(SimpleDWM::SimpleDWMState10 *__hidden this, struct ID3D10Device *, struct IDXGISwapChain *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140085fd0`

## callees

- `0x140003164`
- `0x140003611`
- `0x14003f698`
- `0x14007fa4c`
- `0x1400824ec`
- `0x140087420`
- `0x140087c40`
- `0x14008a958`
- `0x14008ac00`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14008795f`
- `KERNEL32!GetModuleHandleW` at `0x14008795f`
- `msvcrt!qsort` at `0x1400878e6`
- `msvcrt!qsort` at `0x1400878e6`
- `msvcrt!rand` at `0x14008768f`
- `msvcrt!rand` at `0x1400876ad`
- `msvcrt!rand` at `0x1400876bf`
- `msvcrt!rand` at `0x1400876d1`
- `msvcrt!rand` at `0x1400876f8`
- `msvcrt!rand` at `0x14008772b`
- `msvcrt!rand` at `0x14008773f`
- `msvcrt!rand` at `0x140087771`
- `msvcrt!rand` at `0x14008781d`
- `msvcrt!rand` at `0x140087841`
- `msvcrt!rand` at `0x14008768f`
- `msvcrt!rand` at `0x1400876ad`
- `msvcrt!rand` at `0x1400876bf`
- `msvcrt!rand` at `0x1400876d1`
- `msvcrt!rand` at `0x1400876f8`
- `msvcrt!rand` at `0x14008772b`
- `msvcrt!rand` at `0x14008773f`
- `msvcrt!rand` at `0x140087771`
- `msvcrt!rand` at `0x14008781d`
- `msvcrt!rand` at `0x140087841`
- `d3d10_1!D3D10CreateStateBlock` at `0x140087aaa`
- `d3d10_1!D3D10CreateStateBlock` at `0x140087aaa`
- `d3d10_1!D3D10StateBlockMaskEnableAll` at `0x140087a5e`
- `d3d10_1!D3D10StateBlockMaskEnableAll` at `0x140087a5e`

## string_xrefs

- `0x1400874d2`: `SimpleDWM::SimpleDWMState10::p_CreateAllResources`
- `0x140087ab6`: `Failed calling D3D10CreateStateBlock.`

## pseudocode

```c
__int64 __fastcall SimpleDWM::SimpleDWMState10::p_CreateAllResources(
        SimpleDWM::SimpleDWMState10 *this,
        struct ID3D10Device *a2,
        struct IDXGISwapChain *a3)
{
  unsigned __int64 v5; // rax
  void *v6; // rax
  HRESULT ShadersAndLayouts; // ebx
  int v8; // r13d
  unsigned int i; // r15d
  __int64 v10; // rsi
  int v11; // r12d
  int v12; // r12d
  float v13; // xmm8_4
  float v14; // xmm7_4
  float v15; // xmm6_4
  int v16; // edx
  int v17; // edx
  unsigned int v18; // eax
  int v19; // edx
  unsigned int v20; // ecx
  const wchar_t *v21; // r9
  __int64 v22; // rdx
  unsigned __int16 v23; // dx
  __int64 v24; // rcx
  __int64 j; // rcx
  struct ID3D10Device *v26; // rbx
  D3DCommon *ModuleHandleW; // rax
  HINSTANCE v28; // rdx
  __int64 v29; // rcx
  const wchar_t *v30; // r9
  __int64 v31; // rdx
  _QWORD *v32; // rsi
  const wchar_t *v33; // r9
  __int64 v34; // rdx
  struct ID3D10Texture2D **v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+30h] [rbp-D0h]
  int v38; // [rsp+34h] [rbp-CCh]
  int v39; // [rsp+38h] [rbp-C8h]
  int v40; // [rsp+3Ch] [rbp-C4h]
  int v41; // [rsp+40h] [rbp-C0h]
  int v42; // [rsp+44h] [rbp-BCh]
  _BYTE v43[8]; // [rsp+48h] [rbp-B8h] BYREF
  double v44; // [rsp+50h] [rbp-B0h]
  double v45; // [rsp+58h] [rbp-A8h]
  D3D10_STATE_BLOCK_MASK pMask; // [rsp+60h] [rbp-A0h] BYREF

  v5 = 8LL * *((unsigned int *)this + 52);
  if ( !is_mul_ok(*((unsigned int *)this + 52), 8u) )
    v5 = -1;
  v6 = operator new[](v5, (const struct std::nothrow_t *)std::nothrow);
  *((_QWORD *)this + 25) = v6;
  if ( !v6 )
  {
    D3DCommon::ERR(
      (D3DCommon *)0x6D,
      (unsigned __int16)L"m_pWindows",
      L"SimpleDWM::SimpleDWMState10::p_CreateAllResources");
    return (unsigned int)-2147024882;
  }
  memset_0(v6, 0, 8LL * *((unsigned int *)this + 52));
  v8 = *((_DWORD *)this + 30);
  v40 = *((_DWORD *)this + 29);
  v39 = *((_DWORD *)this + 31);
  v41 = *((_DWORD *)this + 32);
  for ( i = 0; i < *((_DWORD *)this + 52); ++i )
  {
    memset(&pMask, 0, 44);
    v10 = (*(__int64 (__fastcall **)(SimpleDWM::SimpleDWMState10 *))(*(_QWORD *)this + 48LL))(this);
    *(_QWORD *)(*((_QWORD *)this + 25) + 8LL * i) = v10;
    if ( !v10 )
    {
      D3DCommon::ERR((D3DCommon *)0x6D, (unsigned __int16)L"pWnd", L"SimpleDWM::SimpleDWMState10::p_CreateAllResources");
      return (unsigned int)-2147024882;
    }
    v37 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 19) + 24LL))(
            *((_QWORD *)this + 19),
            1,
            *((unsigned int *)this + 6));
    v42 = *((_DWORD *)this + 6);
    v38 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 20) + 24LL))(
            *((_QWORD *)this + 20),
            1,
            *((unsigned int *)this + 7));
    v11 = *((_DWORD *)this + 7);
    *(_DWORD *)&pMask.VS = v37;
    *(_DWORD *)&pMask.VSShaderResources[1] = v38;
    *(_DWORD *)&pMask.VSShaderResources[5] = 1;
    *(_DWORD *)&pMask.VSShaderResources[9] = 1;
    *(_DWORD *)&pMask.VSShaderResources[13] = 28;
    *(_QWORD *)&pMask.VSConstantBuffers[1] = 1;
    *(_DWORD *)&pMask.GSShaderResources[4] = 2;
    *(_DWORD *)&pMask.GSShaderResources[8] = 8;
    *(_QWORD *)&pMask.GSShaderResources[12] = 0x10000;
    ShadersAndLayouts = ((__int64 (__fastcall *)(struct ID3D10Device *, D3D10_STATE_BLOCK_MASK *, _QWORD, __int64))a2->lpVtbl->CreateTexture2D)(
                          a2,
                          &pMask,
                          0,
                          v10 + 80);
    if ( ShadersAndLayouts < 0 )
    {
      v21 = L"Failed creating 2D texture.";
      v22 = 1025;
      goto LABEL_31;
    }
    ShadersAndLayouts = ((__int64 (__fastcall *)(struct ID3D10Device *, _QWORD, _QWORD, __int64))a2->lpVtbl->CreateShaderResourceView)(
                          a2,
                          *(_QWORD *)(v10 + 80),
                          0,
                          v10 + 88);
    if ( ShadersAndLayouts < 0 )
    {
      v21 = L"Failed creating shader resource view.";
      v22 = 1032;
LABEL_31:
      Record_FailingHresult_w(
        "base\\winsat\\d3d\\simpledwmdx10.cpp",
        v22,
        (unsigned int)ShadersAndLayouts,
        v21,
        &qword_14012B318);
      v24 = 237;
      goto LABEL_57;
    }
    v12 = v11 - v38;
    v13 = (float)((float)((float)rand() / 32767.0) * 0.80000001) + 0.2;
    v14 = (float)rand() / 32767.0;
    v15 = (float)rand() / 32767.0;
    *(float *)(v10 + 64) = (float)rand() / 32767.0;
    *(float *)(v10 + 68) = v15;
    *(float *)(v10 + 72) = v14;
    *(float *)(v10 + 76) = v13;
    *(double *)(v10 + 56) = (float)((float)rand() / 32767.0) * 3.141592653589793;
    *(_DWORD *)(v10 + 12) = v37;
    *(_DWORD *)(v10 + 16) = v38;
    if ( v42 == v37 )
      v16 = 0;
    else
      v16 = rand() % (v42 - v37);
    *(_DWORD *)v10 = v16;
    if ( v12 )
      v17 = rand() % v12;
    else
      v17 = 0;
    *(_DWORD *)(v10 + 4) = v17;
    *(double *)(v10 + 24) = (double)*(int *)v10;
    *(double *)(v10 + 32) = (double)v17;
    *(float *)(v10 + 8) = (float)rand() / 32767.0;
    v18 = *(_DWORD *)(v10 + 16) * *(_DWORD *)(v10 + 12);
    v19 = 4 * v18;
    if ( v39 )
    {
      *(_WORD *)(v10 + 20) = 257;
      --v39;
LABEL_23:
      *((_DWORD *)this + 53) += v19;
      *((_DWORD *)this + 58) += v19;
      goto LABEL_27;
    }
    if ( v8 )
    {
      *(_BYTE *)(v10 + 20) = 1;
      --v8;
      goto LABEL_23;
    }
    if ( v40 )
    {
      *(_BYTE *)(v10 + 21) = 1;
      --v40;
      goto LABEL_23;
    }
    if ( v41 )
    {
      *(_BYTE *)(v10 + 22) = 1;
      --v41;
      v20 = (v18 >> 1) + v19;
      *((_DWORD *)this + 53) += v20 + v19;
      *((_DWORD *)this + 58) += v20 + v19;
    }
    else
    {
      *((_DWORD *)this + 53) += v19;
    }
LABEL_27:
    D3DCommon::UniformDistribution::UniformDistribution((D3DCommon::UniformDistribution *)v43, -0.5, 0.5);
    *(double *)(v10 + 40) = (double)rand() / 32767.0 * v45 + v44;
    *(double *)(v10 + 48) = (double)rand() / 32767.0 * v45 + v44;
    if ( D3DCommon::TickTimer::TimeExpired((SimpleDWM::SimpleDWMState10 *)((char *)this + 16)) )
      return (unsigned int)-2120548347;
  }
  qsort(*((void **)this + 25), *((unsigned int *)this + 52), 8u, anonymous_namespace_::CompareWindows);
  ShadersAndLayouts = SimpleDWM::SimpleDWMState10::p_CreateShadersAndLayouts(this, a2);
  if ( ShadersAndLayouts < 0 )
    return (unsigned int)ShadersAndLayouts;
  **((_DWORD **)this + 24) = 0;
  *(_DWORD *)(*((_QWORD *)this + 24) + 4LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 24) + 8LL) = 1065353216;
  *(_DWORD *)(*((_QWORD *)this + 24) + 12LL) = *((_DWORD *)this + 6);
  *(_DWORD *)(*((_QWORD *)this + 24) + 16LL) = *((_DWORD *)this + 7);
  for ( j = 0; j != 2; ++j )
    *(_BYTE *)(j + *((_QWORD *)this + 24) + 20) = 0;
  v26 = (struct ID3D10Device *)*((_QWORD *)this + 24);
  ModuleHandleW = (D3DCommon *)GetModuleHandleW(0);
  ShadersAndLayouts = D3DCommon::CreateTextureFromResource10(ModuleHandleW, v28, (unsigned int)a2, v26 + 10, v36);
  if ( ShadersAndLayouts < 0 )
  {
LABEL_38:
    v24 = 235;
    goto LABEL_57;
  }
  ShadersAndLayouts = ((__int64 (__fastcall *)(struct ID3D10Device *, _QWORD, _QWORD, __int64))a2->lpVtbl->CreateShaderResourceView)(
                        a2,
                        *(_QWORD *)(*((_QWORD *)this + 24) + 80LL),
                        0,
                        *((_QWORD *)this + 24) + 88LL);
  if ( ShadersAndLayouts < 0 )
  {
    Record_FailingHresult_w(
      "base\\winsat\\d3d\\simpledwmdx10.cpp",
      1145,
      (unsigned int)ShadersAndLayouts,
      L"Failed creating shader resource view.",
      &qword_14012B318);
    goto LABEL_38;
  }
  v29 = *((_QWORD *)this + 24);
  *((_DWORD *)this + 53) += 4 * *(_DWORD *)(v29 + 12) * *(_DWORD *)(v29 + 16);
  if ( !*((_BYTE *)this + 32) && (*((_BYTE *)this + 88) & 0x40) != 0 )
    *((_DWORD *)this + 53) += 4 * *(_DWORD *)(v29 + 12) * *(_DWORD *)(v29 + 16);
  *((float *)this + 54) = 2.0 / (float)*((int *)this + 6);
  *((float *)this + 55) = 2.0 / (float)*((int *)this + 7);
  memset_0(&pMask, 0, sizeof(pMask));
  ShadersAndLayouts = D3D10StateBlockMaskEnableAll(&pMask);
  if ( ShadersAndLayouts < 0 )
  {
    v30 = L"Failed calling D3D10StateBlockMaskEnableAll.";
    v31 = 1172;
    goto LABEL_46;
  }
  ShadersAndLayouts = D3D10CreateStateBlock(a2, &pMask, (ID3D10StateBlock **)this + 72);
  if ( ShadersAndLayouts >= 0 )
  {
    if ( !*((_DWORD *)this + 32) )
      return (unsigned int)ShadersAndLayouts;
    *(_DWORD *)&pMask.VS = *((_DWORD *)this + 6) >> 1;
    *(_DWORD *)&pMask.VSShaderResources[1] = *((_DWORD *)this + 7) >> 1;
    *(_DWORD *)&pMask.VSShaderResources[5] = 1;
    *(_DWORD *)&pMask.VSShaderResources[9] = 1;
    *(_DWORD *)&pMask.VSShaderResources[13] = 28;
    *(_QWORD *)&pMask.VSConstantBuffers[1] = 1;
    *(_DWORD *)&pMask.GSShaderResources[4] = 2;
    *(_QWORD *)&pMask.GSShaderResources[8] = 40;
    *(_DWORD *)pMask.GSConstantBuffers = 0;
    v32 = (_QWORD *)((char *)this + 552);
    ShadersAndLayouts = ((__int64 (__fastcall *)(struct ID3D10Device *, D3D10_STATE_BLOCK_MASK *, _QWORD, char *))a2->lpVtbl->CreateTexture2D)(
                          a2,
                          &pMask,
                          0,
                          (char *)this + 552);
    if ( ShadersAndLayouts >= 0 )
    {
      ShadersAndLayouts = ((__int64 (__fastcall *)(struct ID3D10Device *, _QWORD, _QWORD, char *))a2->lpVtbl->CreateRenderTargetView)(
                            a2,
                            *v32,
                            0,
                            (char *)this + 560);
      if ( ShadersAndLayouts >= 0 )
      {
        ShadersAndLayouts = ((__int64 (__fastcall *)(struct ID3D10Device *, _QWORD, _QWORD, char *))a2->lpVtbl->CreateShaderResourceView)(
                              a2,
                              *v32,
                              0,
                              (char *)this + 568);
        if ( ShadersAndLayouts >= 0 )
          return (unsigned int)ShadersAndLayouts;
        v33 = L"Failed creating shader resource view.";
        v34 = 1225;
      }
      else
      {
        v33 = L"Failed creating render target view.";
        v34 = 1218;
      }
    }
    else
    {
      v33 = L"Failed creating 2D texture.";
      v34 = 1211;
    }
    Record_FailingHresult_w(
      "base\\winsat\\d3d\\simpledwmdx10.cpp",
      v34,
      (unsigned int)ShadersAndLayouts,
      v33,
      &qword_14012B318);
    v24 = 240;
  }
  else
  {
    v30 = L"Failed calling D3D10CreateStateBlock.";
    v31 = 1179;
LABEL_46:
    Record_FailingHresult_w(
      "base\\winsat\\d3d\\simpledwmdx10.cpp",
      v31,
      (unsigned int)ShadersAndLayouts,
      v30,
      &qword_14012B318);
    v24 = 236;
  }
LABEL_57:
  D3DCommon::ERR((D3DCommon *)v24, v23);
  return (unsigned int)ShadersAndLayouts;
}

```

## disassembly

```asm
0x140087420  mov     rax, rsp
0x140087423  mov     [rax+18h], rbx
0x140087427  push    rbp
0x140087428  push    rsi
0x140087429  push    rdi
0x14008742a  push    r12
0x14008742c  push    r13
0x14008742e  push    r14
0x140087430  push    r15
0x140087432  lea     rbp, [rsp-60h]
0x140087437  sub     rsp, 160h
0x14008743e  movaps  xmmword ptr [rax-48h], xmm6
0x140087442  movaps  xmmword ptr [rax-58h], xmm7
0x140087446  movaps  xmmword ptr [rax-68h], xmm8
0x14008744b  movaps  xmmword ptr [rax-78h], xmm9
0x140087450  movaps  xmmword ptr [rax-88h], xmm10
0x140087458  movaps  xmmword ptr [rax-98h], xmm11
0x140087460  movaps  xmmword ptr [rax-0A8h], xmm12
0x140087468  movaps  xmmword ptr [rax-0B8h], xmm13
0x140087470  movaps  xmmword ptr [rax-0C8h], xmm14
0x140087478  movaps  xmmword ptr [rax-0D8h], xmm15
0x140087480  mov     rax, cs:__security_cookie
0x140087487  xor     rax, rsp
0x14008748a  mov     [rbp+90h+var_E0], rax
0x14008748e  mov     r14, rdx
0x140087491  mov     rdi, rcx
0x140087494  mov     edx, [rcx+0D0h]
0x14008749a  mov     eax, 8
0x14008749f  mul     rdx
0x1400874a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400874a9  cmovb   rax, rcx
0x1400874ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400874b4  mov     rcx, rax; unsigned __int64
0x1400874b7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400874bc  mov     [rdi+0C8h], rax
0x1400874c3  xor     r12d, r12d
0x1400874c6  test    rax, rax
0x1400874c9  jnz     short loc_1400874ED
0x1400874cb  lea     rdx, aMPwindows; "m_pWindows"
0x1400874d2  lea     r8, aSimpledwmSimpl_0; "SimpleDWM::SimpleDWMState10::p_CreateAl"...
0x1400874d9  mov     ecx, 6Dh ; 'm'; this
0x1400874de  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x1400874e3  mov     ebx, 8007000Eh
0x1400874e8  jmp     loc_140087BD9
0x1400874ed  mov     r8d, [rdi+0D0h]
0x1400874f4  shl     r8, 3; Size
0x1400874f8  xor     edx, edx; Val
0x1400874fa  mov     rcx, rax; void *
0x1400874fd  call    memset_0
0x140087502  mov     r13d, [rdi+78h]
0x140087506  mov     eax, [rdi+74h]
0x140087509  mov     [rsp+190h+var_154], eax
0x14008750d  mov     ecx, [rdi+7Ch]
0x140087510  mov     [rsp+190h+var_158], ecx
0x140087514  mov     eax, [rdi+80h]
0x14008751a  mov     [rsp+190h+var_150], eax
0x14008751e  mov     r15d, r12d
0x140087521  movss   xmm9, cs:__real@46fffe00
0x14008752a  movss   xmm13, cs:__real@3f4ccccd
0x140087533  movss   xmm14, cs:__real@3e4ccccd
0x14008753c  movsd   xmm15, cs:__real@400921fb54442d18
0x140087545  movsd   xmm11, cs:__real@3fe0000000000000
0x14008754e  movsd   xmm12, cs:__real@bfe0000000000000
0x140087557  movsd   xmm10, cs:__real@40dfffc000000000
0x140087560  mov     eax, [rdi+0D0h]
0x140087566  cmp     r15d, eax
0x140087569  jnb     loc_1400878CF
0x14008756f  xorps   xmm0, xmm0
0x140087572  movups  xmmword ptr [rsp+190h+pMask.VS], xmm0
0x140087577  movups  xmmword ptr [rsp+190h+pMask.VSShaderResources+0Dh], xmm0
0x14008757c  movups  xmmword ptr [rsp+190h+pMask.GSShaderResources+4], xmm0
0x140087581  mov     rax, [rdi]
0x140087584  mov     rcx, rdi
0x140087587  mov     rax, [rax+30h]
0x14008758b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087590  mov     rsi, rax
0x140087593  mov     edx, r15d
0x140087596  mov     rcx, [rdi+0C8h]
0x14008759d  mov     [rcx+rdx*8], rax
0x1400875a1  test    rax, rax
0x1400875a4  jz      loc_1400878C3
0x1400875aa  mov     rcx, [rdi+98h]
0x1400875b1  mov     rdx, [rcx]
0x1400875b4  mov     rax, [rdx+18h]
0x1400875b8  mov     r8d, [rdi+18h]
0x1400875bc  mov     edx, 1
0x1400875c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400875c6  mov     ebx, eax
0x1400875c8  mov     [rsp+190h+var_160], eax
0x1400875cc  mov     ecx, [rdi+18h]
0x1400875cf  mov     [rsp+190h+var_14C], ecx
0x1400875d3  mov     rcx, [rdi+0A0h]
0x1400875da  mov     rdx, [rcx]
0x1400875dd  mov     rax, [rdx+18h]
0x1400875e1  mov     r8d, [rdi+1Ch]
0x1400875e5  mov     edx, 1
0x1400875ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400875ef  mov     [rsp+190h+var_15C], eax
0x1400875f3  mov     r12d, [rdi+1Ch]
0x1400875f7  mov     dword ptr [rsp+190h+pMask.VS], ebx
0x1400875fb  mov     dword ptr [rsp+190h+pMask.VSShaderResources+1], eax
0x1400875ff  mov     dword ptr [rsp+190h+pMask.VSShaderResources+5], 1
0x140087607  mov     dword ptr [rsp+190h+pMask.VSShaderResources+9], 1
0x14008760f  mov     dword ptr [rsp+190h+pMask.VSShaderResources+0Dh], 1Ch
0x140087617  mov     qword ptr [rsp+190h+pMask.VSConstantBuffers+1], 1
0x140087620  mov     dword ptr [rsp+190h+pMask.GSShaderResources+4], 2
0x140087628  mov     dword ptr [rbp+90h+pMask.GSShaderResources+8], 8
0x14008762f  mov     qword ptr [rbp+90h+pMask.GSShaderResources+0Ch], 10000h
0x140087637  lea     r9, [rsi+50h]
0x14008763b  mov     rcx, [r14]
0x14008763e  mov     rax, [rcx+248h]
0x140087645  xor     r8d, r8d
0x140087648  lea     rdx, [rsp+190h+pMask]
0x14008764d  mov     rcx, r14
0x140087650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087655  mov     ebx, eax
0x140087657  test    eax, eax
0x140087659  js      loc_1400878B5
0x14008765f  mov     rax, [r14]
0x140087662  lea     r9, [rsi+58h]
0x140087666  xor     r8d, r8d
0x140087669  mov     rdx, [rsi+50h]
0x14008766d  mov     rcx, r14
0x140087670  mov     rax, [rax+258h]
0x140087677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008767c  mov     ebx, eax
0x14008767e  test    eax, eax
0x140087680  js      loc_140087884
0x140087686  mov     ebx, [rsp+190h+var_14C]
0x14008768a  sub     r12d, [rsp+190h+var_15C]
0x14008768f  call    cs:__imp_rand
0x140087695  movd    xmm8, eax
0x14008769a  cvtdq2ps xmm8, xmm8
0x14008769e  divss   xmm8, xmm9
0x1400876a3  mulss   xmm8, xmm13
0x1400876a8  addss   xmm8, xmm14
0x1400876ad  call    cs:__imp_rand
0x1400876b3  movd    xmm7, eax
0x1400876b7  cvtdq2ps xmm7, xmm7
0x1400876ba  divss   xmm7, xmm9
0x1400876bf  call    cs:__imp_rand
0x1400876c5  movd    xmm6, eax
0x1400876c9  cvtdq2ps xmm6, xmm6
0x1400876cc  divss   xmm6, xmm9
0x1400876d1  call    cs:__imp_rand
0x1400876d7  movd    xmm0, eax
0x1400876db  cvtdq2ps xmm0, xmm0
0x1400876de  divss   xmm0, xmm9
0x1400876e3  movss   dword ptr [rsi+40h], xmm0
0x1400876e8  movss   dword ptr [rsi+44h], xmm6
0x1400876ed  movss   dword ptr [rsi+48h], xmm7
0x1400876f2  movss   dword ptr [rsi+4Ch], xmm8
0x1400876f8  call    cs:__imp_rand
0x1400876fe  movd    xmm0, eax
0x140087702  cvtdq2ps xmm0, xmm0
0x140087705  divss   xmm0, xmm9
0x14008770a  cvtps2pd xmm1, xmm0
0x14008770d  mulsd   xmm1, xmm15
0x140087712  movsd   qword ptr [rsi+38h], xmm1
0x140087717  mov     eax, [rsp+190h+var_160]
0x14008771b  mov     [rsi+0Ch], eax
0x14008771e  mov     eax, [rsp+190h+var_15C]
0x140087722  mov     [rsi+10h], eax
0x140087725  sub     ebx, [rsp+190h+var_160]
0x140087729  jz      short loc_140087736
0x14008772b  call    cs:__imp_rand
0x140087731  cdq
0x140087732  idiv    ebx
0x140087734  jmp     short loc_140087738
0x140087736  xor     edx, edx
0x140087738  mov     [rsi], edx
0x14008773a  test    r12d, r12d
0x14008773d  jz      short loc_14008774E
0x14008773f  call    cs:__imp_rand
0x140087745  cdq
0x140087746  idiv    r12d
0x140087749  xor     r12d, r12d
0x14008774c  jmp     short loc_140087754
0x14008774e  xor     r12d, r12d
0x140087751  mov     edx, r12d
0x140087754  mov     [rsi+4], edx
0x140087757  movd    xmm0, dword ptr [rsi]
0x14008775b  cvtdq2pd xmm0, xmm0
0x14008775f  movsd   qword ptr [rsi+18h], xmm0
0x140087764  movd    xmm1, edx
0x140087768  cvtdq2pd xmm1, xmm1
0x14008776c  movsd   qword ptr [rsi+20h], xmm1
0x140087771  call    cs:__imp_rand
0x140087777  movd    xmm0, eax
0x14008777b  cvtdq2ps xmm0, xmm0
0x14008777e  divss   xmm0, xmm9
0x140087783  movss   dword ptr [rsi+8], xmm0
0x140087788  mov     eax, [rsi+0Ch]
0x14008778b  imul    eax, [rsi+10h]
0x14008778f  lea     edx, ds:0[rax*4]
0x140087796  mov     ebx, [rsp+190h+var_158]
0x14008779a  test    ebx, ebx
0x14008779c  jz      short loc_1400877AC
0x14008779e  mov     word ptr [rsi+14h], 101h
0x1400877a4  dec     ebx
0x1400877a6  mov     [rsp+190h+var_158], ebx
0x1400877aa  jmp     short loc_1400877CC
0x1400877ac  test    r13d, r13d
0x1400877af  jz      short loc_1400877BA
0x1400877b1  mov     byte ptr [rsi+14h], 1
0x1400877b5  dec     r13d
0x1400877b8  jmp     short loc_1400877CC
0x1400877ba  mov     ebx, [rsp+190h+var_154]
0x1400877be  test    ebx, ebx
0x1400877c0  jz      short loc_1400877DA
0x1400877c2  mov     byte ptr [rsi+15h], 1
0x1400877c6  dec     ebx
0x1400877c8  mov     [rsp+190h+var_154], ebx
0x1400877cc  add     [rdi+0D4h], edx
0x1400877d2  add     [rdi+0E8h], edx
0x1400877d8  jmp     short loc_14008780B
0x1400877da  mov     ebx, [rsp+190h+var_150]
0x1400877de  test    ebx, ebx
0x1400877e0  jz      short loc_140087805
0x1400877e2  mov     byte ptr [rsi+16h], 1
0x1400877e6  dec     ebx
0x1400877e8  mov     [rsp+190h+var_150], ebx
0x1400877ec  shr     eax, 1
0x1400877ee  lea     ecx, [rax+rdx]
0x1400877f1  lea     eax, [rcx+rdx]
0x1400877f4  add     [rdi+0D4h], eax
0x1400877fa  lea     eax, [rcx+rdx]
0x1400877fd  add     [rdi+0E8h], eax
0x140087803  jmp     short loc_14008780B
0x140087805  add     [rdi+0D4h], edx
0x14008780b  movaps  xmm2, xmm11; double
0x14008780f  movaps  xmm1, xmm12; double
0x140087813  lea     rcx, [rsp+190h+var_148]; this
0x140087818  call    ??0UniformDistribution@D3DCommon@@QEAA@NN@Z; D3DCommon::UniformDistribution::UniformDistribution(double,double)
0x14008781d  call    cs:__imp_rand
0x140087823  movd    xmm0, eax
0x140087827  cvtdq2pd xmm0, xmm0
0x14008782b  divsd   xmm0, xmm10
0x140087830  mulsd   xmm0, [rsp+190h+var_138]
0x140087836  addsd   xmm0, [rsp+190h+var_140]
0x14008783c  movsd   qword ptr [rsi+28h], xmm0
0x140087841  call    cs:__imp_rand
0x140087847  movd    xmm0, eax
0x14008784b  cvtdq2pd xmm0, xmm0
0x14008784f  divsd   xmm0, xmm10
0x140087854  mulsd   xmm0, [rsp+190h+var_138]
0x14008785a  addsd   xmm0, [rsp+190h+var_140]
0x140087860  movsd   qword ptr [rsi+30h], xmm0
0x140087865  lea     rcx, [rdi+10h]; this
0x140087869  call    ?TimeExpired@TickTimer@D3DCommon@@QEAA_NXZ; D3DCommon::TickTimer::TimeExpired(void)
0x14008786e  test    al, al
0x140087870  jnz     short loc_14008787A
0x140087872  inc     r15d
0x140087875  jmp     loc_140087560
0x14008787a  mov     ebx, 819B0005h
0x14008787f  jmp     loc_140087BD9
0x140087884  lea     r9, aFailedCreating_1; "Failed creating shader resource view."
0x14008788b  mov     edx, 408h
0x140087890  lea     rax, qword_14012B318
0x140087897  mov     r8d, ebx
0x14008789a  mov     [rsp+190h+var_170], rax
0x14008789f  lea     rcx, aBaseWinsatD3dS; "base\\winsat\\d3d\\simpledwmdx10.cpp"
0x1400878a6  call    Record_FailingHresult_w
0x1400878ab  mov     ecx, 0EDh
0x1400878b0  jmp     loc_140087BD4
0x1400878b5  lea     r9, aFailedCreating_0; "Failed creating 2D texture."
0x1400878bc  mov     edx, 401h
0x1400878c1  jmp     short loc_140087890
0x1400878c3  lea     rdx, aPwnd; "pWnd"
0x1400878ca  jmp     loc_1400874D2
0x1400878cf  mov     rdx, rax; NumOfElements
0x1400878d2  lea     r9, _anonymous_namespace___CompareWindows; CompareFunction
0x1400878d9  mov     r8d, 8; SizeOfElements
0x1400878df  mov     rcx, [rdi+0C8h]; Base
0x1400878e6  call    cs:__imp_qsort
0x1400878ec  mov     rdx, r14; struct ID3D10Device *
0x1400878ef  mov     rcx, rdi; this
0x1400878f2  call    ?p_CreateShadersAndLayouts@SimpleDWMState10@SimpleDWM@@QEAAJPEAUID3D10Device@@@Z; SimpleDWM::SimpleDWMState10::p_CreateShadersAndLayouts(ID3D10Device *)
0x1400878f7  mov     ebx, eax
0x1400878f9  test    eax, eax
0x1400878fb  js      loc_140087BD9
0x140087901  mov     rax, [rdi+0C0h]
0x140087908  mov     [rax], r12d
0x14008790b  mov     rax, [rdi+0C0h]
0x140087912  mov     [rax+4], r12d
0x140087916  mov     rax, [rdi+0C0h]
0x14008791d  mov     dword ptr [rax+8], 3F800000h
0x140087924  mov     rcx, [rdi+0C0h]
0x14008792b  mov     eax, [rdi+18h]
0x14008792e  mov     [rcx+0Ch], eax
0x140087931  mov     rcx, [rdi+0C0h]
0x140087938  mov     eax, [rdi+1Ch]
0x14008793b  mov     [rcx+10h], eax
0x14008793e  mov     rcx, r12
0x140087941  mov     rax, [rdi+0C0h]
0x140087948  mov     [rcx+rax+14h], r12b
0x14008794d  inc     rcx
0x140087950  cmp     rcx, 2
0x140087954  jnz     short loc_140087941
0x140087956  mov     rbx, [rdi+0C0h]
  ... truncated ...
```
