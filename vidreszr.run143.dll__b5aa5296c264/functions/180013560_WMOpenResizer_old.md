# WMOpenResizer_old

- ea: `0x180013560`
- end: `0x1800139f5`
- name: `WMOpenResizer_old`
- size: `1173`
- prototype: `__int64 __fastcall(__int128 *, WMSDKRESIZER **, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012e30`

## callees

- `0x180001974`
- `0x1800019b4`
- `0x18000e690`
- `0x180011930`
- `0x180011ab0`
- `0x180011b40`
- `0x180013560`

## pseudocode

```c
__int64 __fastcall WMOpenResizer_old(__int128 *a1, WMSDKRESIZER **a2, int a3, int a4, int a5)
{
  __int64 result; // rax
  int v10; // ebx
  bool v11; // zf
  __int16 v12; // bp
  bool v13; // zf
  WMSDKRESIZER *v14; // rax
  WMSDKRESIZER *v15; // rbx
  _OWORD *v16; // rax
  unsigned int v17; // edx
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  __int64 v21; // r9
  int v22; // edx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  bool v27; // zf
  WMSDKRESIZER *v28; // rax
  WMSDKRESIZER *v29; // rax
  WMSDKRESIZER *v30; // rdi
  _OWORD *v31; // rax
  unsigned int v32; // edx
  char *v33; // r14
  _OWORD *v34; // rcx
  __int128 *v35; // rax
  __int64 v36; // rdx
  __int128 v37; // xmm0
  _OWORD *v38; // rax
  _OWORD *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  int v42; // eax
  __int64 v43; // r9
  int v44; // eax
  unsigned int v45; // ecx

  if ( !a2 )
    return 1;
  if ( !a1 )
    goto LABEL_36;
  v10 = *((_DWORD *)a1 + 4);
  switch ( v10 )
  {
    case 0:
    case 3:
    case 1448433985:
      break;
    case 844715353:
    case 1498831189:
    case 842150992:
    case 909193814:
      v11 = (a3 & 1) == 0;
LABEL_20:
      if ( !v11 )
        goto LABEL_36;
      break;
    case 1448433993:
    case 842094169:
    case 808596553:
      v11 = (((unsigned __int8)a4 | (unsigned __int8)a3) & 1) == 0;
      goto LABEL_20;
    case 961893977:
      if ( a3 % 4 )
        goto LABEL_36;
      if ( a4 % 4 )
      {
        result = 1;
        *a2 = 0;
        return result;
      }
      break;
  }
  v12 = *((_WORD *)a1 + 7);
  if ( !a5 )
  {
    switch ( v10 )
    {
      case 0:
        v27 = ((v12 - 8) & 0xFFE7) == 0;
LABEL_64:
        if ( !v27 )
          goto LABEL_36;
        goto LABEL_65;
      case 3:
        if ( (unsigned __int16)(v12 - 15) > 1u )
          goto LABEL_36;
LABEL_65:
        v28 = (WMSDKRESIZER *)operator new(0x458u);
        if ( !v28 )
          goto LABEL_36;
        v29 = WMSDKRESIZER::WMSDKRESIZER(v28, a5);
        v30 = v29;
        if ( !v29 )
          goto LABEL_36;
        if ( !v10 && v12 == 8 )
        {
          v31 = operator new[](0x428u);
          *((_QWORD *)v30 + 1) = v31;
          v33 = (char *)v30 + 8;
          v34 = v31;
          if ( v31 )
          {
            v35 = a1;
            v36 = 8;
            do
            {
              v34 += 8;
              v37 = *v35;
              v35 += 8;
              *(v34 - 8) = v37;
              *(v34 - 7) = *(v35 - 7);
              *(v34 - 6) = *(v35 - 6);
              *(v34 - 5) = *(v35 - 5);
              *(v34 - 4) = *(v35 - 4);
              *(v34 - 3) = *(v35 - 3);
              *(v34 - 2) = *(v35 - 2);
              *(v34 - 1) = *(v35 - 1);
              --v36;
            }
            while ( v36 );
            *v34 = *v35;
            v34[1] = v35[1];
            *((_QWORD *)v34 + 4) = *((_QWORD *)v35 + 4);
            goto LABEL_79;
          }
LABEL_77:
          WMSDKRESIZER::`scalar deleting destructor'(v30, v32);
          result = 1;
          *a2 = 0;
          return result;
        }
        v33 = (char *)v29 + 8;
        if ( v10 == 3 )
        {
          v38 = operator new[](0x34u);
          *(_QWORD *)v33 = v38;
          if ( !v38 )
            goto LABEL_77;
          *v38 = *a1;
          v38[1] = a1[1];
          v38[2] = a1[2];
          *((_DWORD *)v38 + 12) = *((_DWORD *)a1 + 12);
        }
        else
        {
          v39 = operator new[](0x28u);
          *(_QWORD *)v33 = v39;
          if ( !v39 )
            goto LABEL_77;
          *v39 = *a1;
          v39[1] = a1[1];
          *((_QWORD *)v39 + 4) = *((_QWORD *)a1 + 4);
        }
LABEL_79:
        v40 = *(_QWORD *)v33;
        v41 = -*(_DWORD *)(*(_QWORD *)v33 + 8LL);
        if ( *(int *)(*(_QWORD *)v33 + 8LL) > 0 )
          v41 = *(_DWORD *)(v40 + 8);
        *(_DWORD *)(v40 + 8) = v41;
        if ( !*(_DWORD *)(*(_QWORD *)v33 + 20LL) )
        {
          v42 = WMSDKRESIZER::BMPSize(v30, *((_DWORD *)a1 + 1), *((_DWORD *)a1 + 2));
          *(_DWORD *)(v43 + 20) = v42;
        }
        v44 = CMSMtoN::Init((WMSDKRESIZER *)((char *)v30 + 72), *((_DWORD *)a1 + 1), *((_DWORD *)a1 + 2), a3, a4);
        v45 = 0;
        *((_DWORD *)v30 + 10) = a3;
        *((_DWORD *)v30 + 11) = a4;
        *((_QWORD *)v30 + 4) = -1;
        if ( !v44 )
          v45 = -2147467259;
        *((_DWORD *)v30 + 270) = a5;
        result = v45;
        *a2 = v30;
        return result;
      case 844715353:
        goto LABEL_65;
    }
LABEL_55:
    if ( v10 == 1498831189
      || v10 == 961893977
      || v10 == 1448433993
      || v10 == 842094169
      || v10 == 808596553
      || v10 == 1448433985
      || v10 == 842150992 )
    {
      goto LABEL_65;
    }
    v27 = v10 == 909193814;
    goto LABEL_64;
  }
  if ( v10 == 808596553 || v10 == 1448433993 )
    goto LABEL_55;
  if ( v10 )
  {
    if ( v10 == 1498831189 || v10 == 844715353 || v10 == 842094169 || v10 == 1448433985 )
      goto LABEL_32;
    v13 = v10 == 842150992;
  }
  else
  {
    v13 = v12 == 32;
  }
  if ( !v13 )
  {
LABEL_36:
    result = 1;
    *a2 = 0;
    return result;
  }
LABEL_32:
  v14 = (WMSDKRESIZER *)operator new(0x458u);
  if ( !v14 )
    goto LABEL_36;
  v15 = WMSDKRESIZER::WMSDKRESIZER(v14, 0);
  if ( !v15 )
    goto LABEL_36;
  v16 = operator new[](0x28u);
  *((_QWORD *)v15 + 1) = v16;
  if ( !v16 )
  {
    WMSDKRESIZER::`scalar deleting destructor'(v15, v17);
    goto LABEL_36;
  }
  *v16 = *a1;
  v16[1] = a1[1];
  *((_QWORD *)v16 + 4) = *((_QWORD *)a1 + 4);
  v18 = *((_QWORD *)v15 + 1);
  v19 = -*(_DWORD *)(v18 + 8);
  if ( *(int *)(v18 + 8) > 0 )
    v19 = *(_DWORD *)(v18 + 8);
  *(_DWORD *)(v18 + 8) = v19;
  if ( !*(_DWORD *)(*((_QWORD *)v15 + 1) + 20LL) )
  {
    v20 = WMSDKRESIZER::BMPSize(v15, *((_DWORD *)a1 + 1), *((_DWORD *)a1 + 2));
    *(_DWORD *)(v21 + 20) = v20;
  }
  v22 = *((_DWORD *)a1 + 2);
  v23 = -*((_DWORD *)a1 + 1);
  if ( *((int *)a1 + 1) > 0 )
    v23 = *((_DWORD *)a1 + 1);
  *((_DWORD *)v15 + 246) = v23;
  v24 = -v22;
  if ( v22 > 0 )
    v24 = v22;
  *((_DWORD *)v15 + 247) = v24;
  v25 = -a3;
  if ( a3 > 0 )
    v25 = a3;
  *((_DWORD *)v15 + 248) = v25;
  v26 = -a4;
  if ( a4 > 0 )
    v26 = a4;
  *((_DWORD *)v15 + 249) = v26;
  result = 0;
  *((_DWORD *)v15 + 10) = a3;
  *((_DWORD *)v15 + 11) = a4;
  *((_QWORD *)v15 + 4) = -1;
  *((_DWORD *)v15 + 270) = a5;
  *a2 = v15;
  return result;
}

```

## disassembly

```asm
0x180013560  mov     [rsp+arg_18], r9d
0x180013565  push    rsi
0x180013566  push    rdi
0x180013567  push    r12
0x180013569  push    r15
0x18001356b  sub     rsp, 38h
0x18001356f  mov     edi, r9d
0x180013572  mov     r12d, r8d
0x180013575  mov     r15, rdx
0x180013578  mov     rsi, rcx
0x18001357b  test    rdx, rdx
0x18001357e  jnz     short loc_180013590
0x180013580  mov     eax, 1
0x180013585  add     rsp, 38h
0x180013589  pop     r15
0x18001358b  pop     r12
0x18001358d  pop     rdi
0x18001358e  pop     rsi
0x18001358f  retn
0x180013590  mov     [rsp+58h+arg_0], rbx
0x180013595  mov     [rsp+58h+arg_8], rbp
0x18001359a  mov     [rsp+58h+arg_10], r13
0x18001359f  test    rsi, rsi
0x1800135a2  jz      loc_1800136F5
0x1800135a8  mov     ebx, [rcx+10h]
0x1800135ab  test    ebx, ebx
0x1800135ad  jz      loc_18001365A
0x1800135b3  cmp     ebx, 3
0x1800135b6  jz      loc_18001365A
0x1800135bc  cmp     ebx, 56555941h
0x1800135c2  jz      loc_18001365A
0x1800135c8  cmp     ebx, 32595559h
0x1800135ce  jz      short loc_18001364D
0x1800135d0  cmp     ebx, 59565955h
0x1800135d6  jz      short loc_18001364D
0x1800135d8  cmp     ebx, 32323450h
0x1800135de  jz      short loc_18001364D
0x1800135e0  cmp     ebx, 36313256h
0x1800135e6  jz      short loc_18001364D
0x1800135e8  cmp     ebx, 56555949h
0x1800135ee  jz      short loc_180013644
0x1800135f0  cmp     ebx, 32315659h
0x1800135f6  jz      short loc_180013644
0x1800135f8  cmp     ebx, 30323449h
0x1800135fe  jz      short loc_180013644
0x180013600  cmp     ebx, 39555659h
0x180013606  jnz     short loc_18001365A
0x180013608  mov     eax, r12d
0x18001360b  and     eax, 80000003h
0x180013610  jge     short loc_180013619
0x180013612  dec     eax
0x180013614  or      eax, 0FFFFFFFCh
0x180013617  inc     eax
0x180013619  test    eax, eax
0x18001361b  jnz     loc_1800136F5
0x180013621  mov     eax, edi
0x180013623  and     eax, 80000003h
0x180013628  jge     short loc_180013631
0x18001362a  dec     eax
0x18001362c  or      eax, 0FFFFFFFCh
0x18001362f  inc     eax
0x180013631  test    eax, eax
0x180013633  jz      short loc_18001365A
0x180013635  xor     ecx, ecx
0x180013637  mov     eax, 1
0x18001363c  mov     [r15], rcx
0x18001363f  jmp     loc_1800139DB
0x180013644  mov     eax, r12d
0x180013647  or      eax, edi
0x180013649  test    al, 1
0x18001364b  jmp     short loc_180013654
0x18001364d  test    r12d, 1
0x180013654  jnz     loc_1800136F5
0x18001365a  mov     r13d, [rsp+58h+arg_20]
0x180013662  movzx   ebp, word ptr [rcx+0Eh]
0x180013666  test    r13d, r13d
0x180013669  jz      loc_1800137A5
0x18001366f  cmp     ebx, 30323449h
0x180013675  jz      loc_1800137C5
0x18001367b  cmp     ebx, 56555949h
0x180013681  jz      loc_1800137C5
0x180013687  test    ebx, ebx
0x180013689  jnz     short loc_180013691
0x18001368b  cmp     bp, 20h ; ' '
0x18001368f  jmp     short loc_1800136B7
0x180013691  cmp     ebx, 59565955h
0x180013697  jz      short loc_1800136B9
0x180013699  cmp     ebx, 32595559h
0x18001369f  jz      short loc_1800136B9
0x1800136a1  cmp     ebx, 32315659h
0x1800136a7  jz      short loc_1800136B9
0x1800136a9  cmp     ebx, 56555941h
0x1800136af  jz      short loc_1800136B9
0x1800136b1  cmp     ebx, 32323450h
0x1800136b7  jnz     short loc_1800136F5
0x1800136b9  mov     ecx, 458h; Size
0x1800136be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800136c3  test    rax, rax
0x1800136c6  jz      short loc_1800136F5
0x1800136c8  xor     edx, edx; int
0x1800136ca  mov     rcx, rax; this
0x1800136cd  call    ??0WMSDKRESIZER@@QEAA@J@Z; WMSDKRESIZER::WMSDKRESIZER(long)
0x1800136d2  mov     rbx, rax
0x1800136d5  test    rax, rax
0x1800136d8  jz      short loc_1800136F5
0x1800136da  mov     ecx, 28h ; '('; unsigned __int64
0x1800136df  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800136e4  mov     [rbx+8], rax
0x1800136e8  test    rax, rax
0x1800136eb  jnz     short loc_180013704
0x1800136ed  mov     rcx, rbx; this
0x1800136f0  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x1800136f5  xor     ecx, ecx
0x1800136f7  mov     eax, 1
0x1800136fc  mov     [r15], rcx
0x1800136ff  jmp     loc_1800139DB
0x180013704  movups  xmm0, xmmword ptr [rsi]
0x180013707  movups  xmmword ptr [rax], xmm0
0x18001370a  movups  xmm1, xmmword ptr [rsi+10h]
0x18001370e  movups  xmmword ptr [rax+10h], xmm1
0x180013712  movsd   xmm0, qword ptr [rsi+20h]
0x180013717  movsd   qword ptr [rax+20h], xmm0
0x18001371c  mov     rdx, [rbx+8]
0x180013720  mov     eax, [rdx+8]
0x180013723  neg     eax
0x180013725  cmovs   eax, [rdx+8]
0x180013729  mov     [rdx+8], eax
0x18001372c  mov     r9, [rbx+8]
0x180013730  cmp     dword ptr [r9+14h], 0
0x180013735  jnz     short loc_18001374A
0x180013737  mov     edx, [rsi+4]; int
0x18001373a  mov     rcx, rbx; this
0x18001373d  mov     r8d, [rsi+8]; int
0x180013741  call    ?BMPSize@WMSDKRESIZER@@QEAAJJJ@Z; WMSDKRESIZER::BMPSize(long,long)
0x180013746  mov     [r9+14h], eax
0x18001374a  mov     edx, [rsi+8]
0x18001374d  mov     eax, [rsi+4]
0x180013750  neg     eax
0x180013752  cmovs   eax, [rsi+4]
0x180013756  mov     [rbx+3D8h], eax
0x18001375c  mov     eax, edx
0x18001375e  neg     eax
0x180013760  cmovs   eax, edx
0x180013763  mov     [rbx+3DCh], eax
0x180013769  mov     eax, r12d
0x18001376c  neg     eax
0x18001376e  cmovs   eax, r12d
0x180013772  mov     [rbx+3E0h], eax
0x180013778  mov     eax, edi
0x18001377a  neg     eax
0x18001377c  cmovs   eax, edi
0x18001377f  mov     [rbx+3E4h], eax
0x180013785  xor     eax, eax
0x180013787  mov     [rbx+28h], r12d
0x18001378b  mov     [rbx+2Ch], edi
0x18001378e  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180013796  mov     [rbx+438h], r13d
0x18001379d  mov     [r15], rbx
0x1800137a0  jmp     loc_1800139DB
0x1800137a5  test    ebx, ebx
0x1800137a7  jz      short loc_180013805
0x1800137a9  cmp     ebx, 3
0x1800137ac  jnz     short loc_1800137BD
0x1800137ae  lea     eax, [rbp-0Fh]
0x1800137b1  cmp     ax, 1
0x1800137b5  ja      loc_1800136F5
0x1800137bb  jmp     short loc_180013816
0x1800137bd  cmp     ebx, 32595559h
0x1800137c3  jz      short loc_180013816
0x1800137c5  cmp     ebx, 59565955h
0x1800137cb  jz      short loc_180013816
0x1800137cd  cmp     ebx, 39555659h
0x1800137d3  jz      short loc_180013816
0x1800137d5  cmp     ebx, 56555949h
0x1800137db  jz      short loc_180013816
0x1800137dd  cmp     ebx, 32315659h
0x1800137e3  jz      short loc_180013816
0x1800137e5  cmp     ebx, 30323449h
0x1800137eb  jz      short loc_180013816
0x1800137ed  cmp     ebx, 56555941h
0x1800137f3  jz      short loc_180013816
0x1800137f5  cmp     ebx, 32323450h
0x1800137fb  jz      short loc_180013816
0x1800137fd  cmp     ebx, 36313256h
0x180013803  jmp     short loc_180013810
0x180013805  lea     eax, [rbp-8]
0x180013808  mov     ecx, 0FFE7h
0x18001380d  test    cx, ax
0x180013810  jnz     loc_1800136F5
0x180013816  mov     ecx, 458h; Size
0x18001381b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013820  test    rax, rax
0x180013823  jz      loc_1800136F5
0x180013829  mov     edx, r13d; int
0x18001382c  mov     rcx, rax; this
0x18001382f  call    ??0WMSDKRESIZER@@QEAA@J@Z; WMSDKRESIZER::WMSDKRESIZER(long)
0x180013834  mov     rdi, rax
0x180013837  test    rax, rax
0x18001383a  jz      loc_1800136F5
0x180013840  mov     [rsp+58h+var_28], r14
0x180013845  test    ebx, ebx
0x180013847  jnz     loc_1800138EB
0x18001384d  cmp     bp, 8
0x180013851  jnz     loc_1800138EB
0x180013857  mov     ecx, 428h; unsigned __int64
0x18001385c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013861  mov     [rdi+8], rax
0x180013865  lea     r14, [rdi+8]
0x180013869  mov     rcx, rax
0x18001386c  test    rax, rax
0x18001386f  jz      loc_180013939
0x180013875  mov     rax, rsi
0x180013878  mov     edx, 8
0x18001387d  nop     dword ptr [rax]
0x180013880  lea     rcx, [rcx+80h]
0x180013887  movups  xmm0, xmmword ptr [rax]
0x18001388a  lea     rax, [rax+80h]
0x180013891  movups  xmmword ptr [rcx-80h], xmm0
0x180013895  movups  xmm1, xmmword ptr [rax-70h]
0x180013899  movups  xmmword ptr [rcx-70h], xmm1
0x18001389d  movups  xmm0, xmmword ptr [rax-60h]
0x1800138a1  movups  xmmword ptr [rcx-60h], xmm0
0x1800138a5  movups  xmm1, xmmword ptr [rax-50h]
0x1800138a9  movups  xmmword ptr [rcx-50h], xmm1
0x1800138ad  movups  xmm0, xmmword ptr [rax-40h]
0x1800138b1  movups  xmmword ptr [rcx-40h], xmm0
0x1800138b5  movups  xmm1, xmmword ptr [rax-30h]
0x1800138b9  movups  xmmword ptr [rcx-30h], xmm1
0x1800138bd  movups  xmm0, xmmword ptr [rax-20h]
0x1800138c1  movups  xmmword ptr [rcx-20h], xmm0
0x1800138c5  movups  xmm1, xmmword ptr [rax-10h]
0x1800138c9  movups  xmmword ptr [rcx-10h], xmm1
0x1800138cd  sub     rdx, 1
0x1800138d1  jnz     short loc_180013880
0x1800138d3  movups  xmm0, xmmword ptr [rax]
0x1800138d6  movups  xmmword ptr [rcx], xmm0
0x1800138d9  movups  xmm1, xmmword ptr [rax+10h]
0x1800138dd  movups  xmmword ptr [rcx+10h], xmm1
0x1800138e1  mov     rax, [rax+20h]
0x1800138e5  mov     [rcx+20h], rax
0x1800138e9  jmp     short loc_180013968
0x1800138eb  lea     r14, [rax+8]
0x1800138ef  cmp     ebx, 3
0x1800138f2  jnz     short loc_180013927
0x1800138f4  mov     ecx, 34h ; '4'; unsigned __int64
0x1800138f9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800138fe  mov     [r14], rax
0x180013901  mov     rcx, rax
0x180013904  test    rax, rax
0x180013907  jz      short loc_180013939
0x180013909  movups  xmm0, xmmword ptr [rsi]
0x18001390c  movups  xmmword ptr [rax], xmm0
0x18001390f  movups  xmm1, xmmword ptr [rsi+10h]
0x180013913  movups  xmmword ptr [rax+10h], xmm1
0x180013917  movups  xmm0, xmmword ptr [rsi+20h]
0x18001391b  movups  xmmword ptr [rax+20h], xmm0
0x18001391f  mov     eax, [rsi+30h]
0x180013922  mov     [rcx+30h], eax
0x180013925  jmp     short loc_180013968
0x180013927  mov     ecx, 28h ; '('; unsigned __int64
0x18001392c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013931  mov     [r14], rax
0x180013934  test    rax, rax
0x180013937  jnz     short loc_180013950
0x180013939  mov     rcx, rdi; this
0x18001393c  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x180013941  xor     ecx, ecx
0x180013943  mov     eax, 1
0x180013948  mov     [r15], rcx
0x18001394b  jmp     loc_1800139D6
0x180013950  movups  xmm0, xmmword ptr [rsi]
0x180013953  movups  xmmword ptr [rax], xmm0
0x180013956  movups  xmm1, xmmword ptr [rsi+10h]
0x18001395a  movups  xmmword ptr [rax+10h], xmm1
0x18001395e  movsd   xmm0, qword ptr [rsi+20h]
0x180013963  movsd   qword ptr [rax+20h], xmm0
0x180013968  mov     rdx, [r14]
0x18001396b  mov     eax, [rdx+8]
0x18001396e  neg     eax
0x180013970  cmovs   eax, [rdx+8]
0x180013974  mov     [rdx+8], eax
0x180013977  mov     r9, [r14]
0x18001397a  cmp     dword ptr [r9+14h], 0
0x18001397f  jnz     short loc_180013994
0x180013981  mov     edx, [rsi+4]; int
0x180013984  mov     rcx, rdi; this
0x180013987  mov     r8d, [rsi+8]; int
0x18001398b  call    ?BMPSize@WMSDKRESIZER@@QEAAJJJ@Z; WMSDKRESIZER::BMPSize(long,long)
0x180013990  mov     [r9+14h], eax
0x180013994  mov     ebx, [rsp+58h+arg_18]
0x180013998  lea     rcx, [rdi+48h]; this
0x18001399c  mov     r8d, [rsi+8]; int
0x1800139a0  mov     r9d, r12d; int
0x1800139a3  mov     edx, [rsi+4]; int
0x1800139a6  mov     [rsp+58h+var_38], ebx; int
0x1800139aa  call    ?Init@CMSMtoN@@UEAAHHHHH@Z; CMSMtoN::Init(int,int,int,int)
0x1800139af  xor     ecx, ecx
0x1800139b1  mov     [rdi+28h], r12d
0x1800139b5  test    eax, eax
0x1800139b7  mov     [rdi+2Ch], ebx
  ... truncated ...
```
