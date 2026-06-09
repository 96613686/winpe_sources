# WapAuthInitializeSecurityContextWrapper

- ea: `0x1800687a0`
- end: `0x180068cf1`
- name: `WapAuthInitializeSecurityContextWrapper`
- size: `1361`
- prototype: `__int64 __fastcall(__int64, __int64, struct _SecHandle *, unsigned int, SEC_WCHAR **, _BYTE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800685e0`
- `0x18006d780`

## callees

- `0x180013820`
- `0x1800391c0`
- `0x180065334`
- `0x1800687a0`
- `0x180068cf8`
- `0x180068f1c`
- `0x18006b7b8`
- `0x18006d73c`
- `0x1800722f0`
- `0x18008d2d0`
- `0x180091678`
- `0x1800971ec`

## import_xrefs

- `SspiCli!InitializeSecurityContextW` at `0x180068b22`
- `SspiCli!InitializeSecurityContextW` at `0x180068b22`
- `SspiCli!SeciFreeCallContext` at `0x180068cae`
- `SspiCli!SeciFreeCallContext` at `0x180068cae`
- `SspiCli!SeciAllocateAndSetCallTarget` at `0x180068a92`
- `SspiCli!SeciAllocateAndSetCallTarget` at `0x180068a92`
- `SspiCli!DeleteSecurityContext` at `0x180068a06`
- `SspiCli!DeleteSecurityContext` at `0x180068b74`
- `SspiCli!DeleteSecurityContext` at `0x180068a06`
- `SspiCli!DeleteSecurityContext` at `0x180068b74`

## pseudocode

```c
__int64 __fastcall WapAuthInitializeSecurityContextWrapper(
        __int64 a1,
        __int64 a2,
        struct _SecHandle *a3,
        unsigned int a4,
        SEC_WCHAR **a5,
        _BYTE *a6)
{
  __int64 v6; // r15
  __int64 v8; // rax
  unsigned int Spn; // ebx
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 Heap; // r13
  void *v13; // r14
  int v14; // edi
  unsigned int v15; // eax
  unsigned __int64 v16; // rax
  int v18; // ebx
  unsigned int v19; // ebx
  __int64 v20; // rax
  int *v21; // rdx
  unsigned int v22; // ecx
  __int64 v23; // rax
  struct _SecBufferDesc *v24; // rdx
  _QWORD *v25; // r15
  _WORD *v26; // rdi
  __int64 v27; // r8
  unsigned int v28; // eax
  SECURITY_STATUS v29; // eax
  SECURITY_STATUS v30; // r12d
  size_t v31; // rdi
  __int64 v32; // rcx
  const char *v33; // r15
  __int64 v34; // rbx
  size_t v35; // rdx
  __int64 v36; // rax
  unsigned __int64 v37; // rcx
  __int64 v38; // rcx
  char v40[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  PCtxtHandle phContext; // [rsp+90h] [rbp-70h]
  SEC_WCHAR **v47; // [rsp+98h] [rbp-68h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  PSecBufferDesc pInput; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  _BYTE *v52; // [rsp+C0h] [rbp-40h]
  __int128 v53; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v54; // [rsp+D8h] [rbp-28h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int fContextReq; // [rsp+F8h] [rbp-8h] BYREF
  int v57; // [rsp+FCh] [rbp-4h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+100h] [rbp+0h] BYREF
  int v59; // [rsp+108h] [rbp+8h] BYREF
  int v60; // [rsp+10Ch] [rbp+Ch]
  _QWORD v61[3]; // [rsp+110h] [rbp+10h]

  v51 = a1;
  v6 = 0;
  phContext = a3;
  v42 = 0;
  v44 = 0;
  v40[0] = 0;
  v57 = 0;
  v8 = *(int *)(a1 + 16);
  *a5 = 0;
  *a6 = 0;
  v47 = a5;
  v52 = a6;
  ptsExpiry.QuadPart = 0;
  fContextReq = 0;
  v45 = 0;
  pOutput = 0;
  v53 = 0;
  v54 = 0;
  if ( a4 > 0x100000 )
    return 87;
  Spn = 0;
  v49 = *(_QWORD *)(a1 + 24);
  if ( !v49 )
    return Spn;
  v10 = *(_QWORD *)(a1 + 48);
  v11 = 48 * v8;
  Heap = 0;
  v48 = v11;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( (*((_BYTE *)&WaAuthSchemeProperties[4] + v11) & 2) != 0 )
  {
    fContextReq = 2;
    v15 = 2;
  }
  if ( *(_BYTE *)(a2 + 48) )
  {
    v15 |= 1u;
    fContextReq = v15;
  }
  if ( *(_BYTE *)(a2 + 105) )
    fContextReq = v15 | 0x1000000;
  if ( !a4 )
    goto LABEL_16;
  v16 = (unsigned __int64)a4 >> 2;
  v18 = 3 * v16;
  v43 = 3 * v16;
  if ( (a4 & 3) != 0 )
  {
    Spn = 87;
    goto LABEL_76;
  }
  Heap = WxAllocateHeapEx(v11, 3 * v16);
  if ( Heap )
  {
    Spn = WaBase64ToBinary((_DWORD)phContext, a4, Heap, v18, (__int64)&v43);
    if ( Spn )
    {
LABEL_70:
      v42 = Heap;
      WxFreeHeapEx(&v42);
LABEL_71:
      if ( !v6 )
      {
LABEL_73:
        if ( v13 )
        {
          v42 = (__int64)v13;
          WxFreeHeapEx(&v42);
        }
        v6 = v45;
        goto LABEL_76;
      }
LABEL_72:
      v42 = v6;
      WxFreeHeapEx(&v42);
      goto LABEL_73;
    }
    v14 = v43;
    v11 = v48;
LABEL_16:
    v19 = *(_DWORD *)((char *)&WaAuthSchemeProperties[4] + v11 + 4);
    pOutput.ulVersion = 0;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)&v53;
    v20 = WxAllocateHeapEx(v11, v19);
    v41 = v20;
    v6 = v20;
    if ( !v20 )
    {
      Spn = 8;
      goto LABEL_69;
    }
    v21 = *(int **)(a2 + 144);
    v22 = 0;
    *((_QWORD *)&v53 + 1) = v20;
    *((_QWORD *)&v54 + 1) = &v59;
    *(_QWORD *)&v53 = v19 | 0x200000000LL;
    *(_QWORD *)&v54 = 0;
    if ( v21 )
    {
      v60 = 14;
      v22 = 1;
      v61[0] = *((_QWORD *)v21 + 1);
      v59 = *v21;
      DWORD1(v54) = 1;
    }
    if ( Heap )
    {
      v23 = 2LL * v22++;
      DWORD1(v54) = v22;
      *(&v60 + 2 * v23) = 2;
      v61[v23] = Heap;
      *(&v59 + 2 * v23) = v14;
    }
    v24 = (struct _SecBufferDesc *)&v54;
    if ( !v22 )
      v24 = 0;
    pInput = v24;
    Spn = WaAuthGenerateSpn(a2, v47, v40);
    if ( Spn )
    {
LABEL_69:
      if ( !Heap )
        goto LABEL_71;
      goto LABEL_70;
    }
    phContext = 0;
    if ( !v40[0] )
      fContextReq |= 0x20000000u;
    v25 = (_QWORD *)(v10 + 48);
    if ( *(_QWORD *)(v10 + 48) != -1 && *(_QWORD *)(v10 + 56) != -1 )
    {
      if ( !Heap )
      {
        DeleteSecurityContext((PCtxtHandle)(v10 + 48));
        *v25 = -1;
        v6 = v41;
        *(_QWORD *)(v10 + 56) = -1;
        *(_BYTE *)(v10 + 44) = 0;
        goto LABEL_72;
      }
      phContext = (PCtxtHandle)(v10 + 48);
    }
    v26 = (_WORD *)(a2 + 168);
    if ( *(_WORD *)(a2 + 168) == 2 )
    {
      v43 = 16;
    }
    else if ( *v26 == 23 )
    {
      v43 = 28;
    }
    else
    {
      v26 = 0;
      v43 = 0;
    }
    v27 = *(_QWORD *)(a2 + 128);
    if ( !v27 )
    {
      Spn = WapAuthGetHostName(a2, &v45);
      if ( Spn )
        goto LABEL_68;
      v27 = v45;
    }
    v28 = SeciAllocateAndSetCallTarget(v26, (unsigned int)v43, v27, &v57);
    if ( v28 )
    {
      if ( (xmmword_1800AD710 & 8) != 0 )
        WPP_SF_d(515, 18, WPP_05612d2d46af3ad8812821a8d7ec1cab_Traceguids, v28);
      Spn = 5;
      goto LABEL_68;
    }
    v29 = InitializeSecurityContextW(
            (PCredHandle)(v49 + 24),
            phContext,
            *v47,
            fContextReq,
            0,
            0x10u,
            pInput,
            0,
            (PCtxtHandle)(v10 + 48),
            &pOutput,
            &fContextReq,
            &ptsExpiry);
    *(_DWORD *)(v10 + 40) = v29;
    v30 = v29;
    if ( v29 >= 0 )
    {
      v31 = 5;
      if ( *(_DWORD *)(v51 + 16) == 5 )
      {
        Spn = WapAuthSspResolveSubScheme(v10);
        if ( Spn )
          goto LABEL_68;
      }
      if ( v30 )
      {
        if ( v30 == 590610 )
          *(_BYTE *)(v10 + 44) = 1;
      }
      else
      {
        if ( (fContextReq & 2) != 0 )
          *v52 = 1;
        DeleteSecurityContext((PCtxtHandle)(v10 + 48));
        *(_BYTE *)(v10 + 44) = 0;
        *(_QWORD *)(v10 + 56) = -1;
        *v25 = -1;
      }
      if ( (_DWORD)v53 )
      {
        Spn = WaBinaryToBase64Length((unsigned int)v53, &v44);
        if ( Spn )
          goto LABEL_68;
        if ( *(_BYTE *)(v10 + 64) )
        {
          v33 = "Nego2";
        }
        else
        {
          v31 = *(__int64 *)((char *)&WaAuthSchemeProperties[1] + v48);
          v33 = *(const char **)((char *)WaAuthSchemeProperties + v48);
        }
        v34 = v44;
        v35 = v31 + v44 + 1;
        if ( v35 < v44 )
        {
          Spn = 534;
          goto LABEL_68;
        }
        v36 = WxAllocateHeapEx(v32, v35);
        v13 = (void *)v36;
        if ( !v36 )
        {
          Spn = 8;
          goto LABEL_68;
        }
        Spn = WapBinaryToBase64(0, DWORD2(v53), v53, (int)v31 + (int)v36 + 1, v34, (__int64)&v44);
        if ( Spn )
          goto LABEL_68;
        memcpy_0(v13, v33, v31);
        v37 = v44 + 1;
        *((_BYTE *)v13 + v31) = 32;
        v38 = v31 + v37;
      }
      else
      {
        v38 = v42;
      }
      *(_QWORD *)(v10 + 24) = v13;
      v13 = 0;
      *(_QWORD *)(v10 + 32) = v38;
      goto LABEL_68;
    }
    Spn = v29;
LABEL_68:
    v6 = v41;
    goto LABEL_69;
  }
  Spn = 8;
LABEL_76:
  if ( v57 )
    SeciFreeCallContext();
  if ( v6 )
  {
    v42 = v6;
    WxFreeHeapEx(&v42);
  }
  return Spn;
}

```

## disassembly

```asm
0x1800687a0  push    rbp
0x1800687a2  push    rbx
0x1800687a3  push    rsi
0x1800687a4  push    rdi
0x1800687a5  push    r12
0x1800687a7  push    r13
0x1800687a9  push    r14
0x1800687ab  push    r15
0x1800687ad  lea     rbp, [rsp-38h]
0x1800687b2  sub     rsp, 138h
0x1800687b9  mov     rax, cs:__security_cookie
0x1800687c0  xor     rax, rsp
0x1800687c3  mov     [rbp+70h+var_48], rax
0x1800687c7  xor     eax, eax
0x1800687c9  mov     [rbp+70h+var_B8], rcx
0x1800687cd  xor     r15d, r15d
0x1800687d0  mov     [rbp+70h+phContext], r8
0x1800687d4  mov     r8, [rbp+70h+arg_28]
0x1800687db  xorps   xmm0, xmm0
0x1800687de  mov     [rsp+170h+var_100], rax
0x1800687e3  mov     r12, rdx
0x1800687e6  mov     [rbp+70h+var_F0], rax
0x1800687ea  mov     rdx, rcx
0x1800687ed  mov     rcx, [rbp+70h+arg_20]
0x1800687f4  xorps   xmm1, xmm1
0x1800687f7  mov     [rsp+170h+var_110], al
0x1800687fb  mov     [rbp+70h+var_74], eax
0x1800687fe  movsxd  rax, dword ptr [rdx+10h]
0x180068802  mov     [rcx], r15
0x180068805  mov     [r8], r15b
0x180068808  mov     [rbp+70h+var_D8], rcx
0x18006880c  mov     [rbp+70h+var_B0], r8
0x180068810  mov     qword ptr [rbp+70h+var_70], 0
0x180068818  mov     [rbp+70h+fContextReq], 0
0x18006881f  mov     [rbp+70h+var_E8], r15
0x180068823  movups  xmmword ptr [rbp+70h+var_88.ulVersion], xmm0
0x180068827  movups  [rbp+70h+var_A8], xmm1
0x18006882b  movups  [rbp+70h+var_98], xmm0
0x18006882f  cmp     r9d, 100000h
0x180068836  jbe     short loc_180068841
0x180068838  lea     ebx, [r15+57h]
0x18006883c  jmp     loc_180068CCE
0x180068841  mov     rcx, [rdx+18h]
0x180068845  xor     ebx, ebx
0x180068847  mov     [rbp+70h+var_C8], rcx
0x18006884b  test    rcx, rcx
0x18006884e  jz      loc_180068CCE
0x180068854  mov     rsi, [rdx+30h]
0x180068858  lea     rcx, [rax+rax*2]
0x18006885c  shl     rcx, 4
0x180068860  lea     r8, WaAuthSchemeProperties
0x180068867  xor     r13d, r13d
0x18006886a  mov     [rbp+70h+var_D0], rcx
0x18006886e  xor     r14d, r14d
0x180068871  lea     edx, [rbx+2]
0x180068874  xor     edi, edi
0x180068876  xor     eax, eax
0x180068878  test    [rcx+r8+20h], dl
0x18006887d  jz      short loc_180068884
0x18006887f  mov     [rbp+70h+fContextReq], edx
0x180068882  mov     eax, edx
0x180068884  cmp     [r12+30h], bl
0x180068889  jz      short loc_180068891
0x18006888b  or      eax, 1
0x18006888e  mov     [rbp+70h+fContextReq], eax
0x180068891  cmp     [r12+69h], bl
0x180068896  jz      short loc_18006889F
0x180068898  bts     eax, 18h
0x18006889c  mov     [rbp+70h+fContextReq], eax
0x18006889f  test    r9d, r9d
0x1800688a2  jz      short loc_18006890E
0x1800688a4  mov     eax, r9d
0x1800688a7  shr     rax, 2
0x1800688ab  mov     edi, r9d
0x1800688ae  lea     rbx, [rax+rax*2]
0x1800688b2  mov     [rsp+170h+var_F8], rbx
0x1800688b7  test    r9b, 3
0x1800688bb  jnz     loc_180068942
0x1800688c1  mov     rdx, rbx
0x1800688c4  call    WxAllocateHeapEx
0x1800688c9  mov     r13, rax
0x1800688cc  test    rax, rax
0x1800688cf  jnz     short loc_1800688D9
0x1800688d1  lea     ebx, [rax+8]
0x1800688d4  jmp     loc_180068CA8
0x1800688d9  mov     rcx, [rbp+70h+phContext]
0x1800688dd  lea     rax, [rsp+170h+var_F8]
0x1800688e2  mov     r9, rbx
0x1800688e5  mov     qword ptr [rsp+170h+Reserved1], rax
0x1800688ea  mov     r8, r13
0x1800688ed  mov     rdx, rdi
0x1800688f0  call    WaBase64ToBinary
0x1800688f5  mov     ebx, eax
0x1800688f7  test    eax, eax
0x1800688f9  jnz     loc_180068C6D
0x1800688ff  mov     edi, dword ptr [rsp+170h+var_F8]
0x180068903  lea     r8, WaAuthSchemeProperties
0x18006890a  mov     rcx, [rbp+70h+var_D0]
0x18006890e  mov     ebx, [rcx+r8+24h]
0x180068913  lea     rax, [rbp+70h+var_A8]
0x180068917  mov     edx, ebx
0x180068919  mov     [rbp+70h+var_88.ulVersion], r14d
0x18006891d  mov     [rbp+70h+var_88.cBuffers], 1
0x180068924  mov     [rbp+70h+var_88.pBuffers], rax
0x180068928  call    WxAllocateHeapEx
0x18006892d  mov     [rsp+170h+var_108], rax
0x180068932  mov     r15, rax
0x180068935  test    rax, rax
0x180068938  jnz     short loc_18006894C
0x18006893a  lea     ebx, [rax+8]
0x18006893d  jmp     loc_180068C68
0x180068942  mov     ebx, 57h ; 'W'
0x180068947  jmp     loc_180068CA8
0x18006894c  mov     rdx, [r12+90h]
0x180068954  xor     ecx, ecx
0x180068956  mov     qword ptr [rbp+70h+var_A8+8], rax
0x18006895a  lea     rax, [rbp+70h+var_68]
0x18006895e  mov     qword ptr [rbp+70h+var_98+8], rax
0x180068962  mov     r8d, 2
0x180068968  mov     dword ptr [rbp+70h+var_A8+4], r8d
0x18006896c  mov     dword ptr [rbp+70h+var_A8], ebx
0x18006896f  mov     qword ptr [rbp+70h+var_98], r14
0x180068973  test    rdx, rdx
0x180068976  jz      short loc_180068993
0x180068978  mov     [rbp+70h+var_64], 0Eh
0x18006897f  lea     ecx, [r8-1]
0x180068983  mov     rax, [rdx+8]
0x180068987  mov     [rbp+70h+var_60], rax
0x18006898b  mov     eax, [rdx]
0x18006898d  mov     [rbp+70h+var_68], eax
0x180068990  mov     dword ptr [rbp+70h+var_98+4], ecx
0x180068993  test    r13, r13
0x180068996  jz      short loc_1800689B0
0x180068998  mov     eax, ecx
0x18006899a  add     rax, rax
0x18006899d  inc     ecx
0x18006899f  mov     dword ptr [rbp+70h+var_98+4], ecx
0x1800689a2  mov     [rbp+rax*8+70h+var_64], r8d
0x1800689a7  mov     [rbp+rax*8+70h+var_60], r13
0x1800689ac  mov     [rbp+rax*8+70h+var_68], edi
0x1800689b0  xor     eax, eax
0x1800689b2  lea     rdx, [rbp+70h+var_98]
0x1800689b6  test    ecx, ecx
0x1800689b8  lea     r8, [rsp+170h+var_110]
0x1800689bd  mov     rcx, r12
0x1800689c0  cmovz   rdx, rax
0x1800689c4  mov     [rbp+70h+var_C0], rdx
0x1800689c8  mov     rdx, [rbp+70h+var_D8]
0x1800689cc  call    WaAuthGenerateSpn
0x1800689d1  mov     ebx, eax
0x1800689d3  test    eax, eax
0x1800689d5  jnz     loc_180068C68
0x1800689db  mov     [rbp+70h+phContext], r14
0x1800689df  cmp     [rsp+170h+var_110], r14b
0x1800689e4  jnz     short loc_1800689EB
0x1800689e6  bts     [rbp+70h+fContextReq], 1Dh
0x1800689eb  lea     r15, [rsi+30h]
0x1800689ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800689f3  cmp     [r15], rdi
0x1800689f6  jz      short loc_180068A2B
0x1800689f8  cmp     [rsi+38h], rdi
0x1800689fc  jz      short loc_180068A2B
0x1800689fe  test    r13, r13
0x180068a01  jnz     short loc_180068A27
0x180068a03  mov     rcx, r15; phContext
0x180068a06  call    cs:__imp_DeleteSecurityContext
0x180068a0d  nop     dword ptr [rax+rax+00h]
0x180068a12  mov     [r15], rdi
0x180068a15  mov     r15, [rsp+170h+var_108]
0x180068a1a  mov     [rsi+38h], rdi
0x180068a1e  mov     [rsi+2Ch], r14b
0x180068a22  jmp     loc_180068C81
0x180068a27  mov     [rbp+70h+phContext], r15
0x180068a2b  lea     rdi, [r12+0A8h]
0x180068a33  mov     eax, 2
0x180068a38  cmp     [rdi], ax
0x180068a3b  jnz     short loc_180068A48
0x180068a3d  mov     [rsp+170h+var_F8], 10h
0x180068a46  jmp     short loc_180068A60
0x180068a48  cmp     word ptr [rdi], 17h
0x180068a4c  jnz     short loc_180068A59
0x180068a4e  mov     [rsp+170h+var_F8], 1Ch
0x180068a57  jmp     short loc_180068A60
0x180068a59  xor     edi, edi
0x180068a5b  mov     [rsp+170h+var_F8], rdi
0x180068a60  mov     r8, [r12+80h]
0x180068a68  test    r8, r8
0x180068a6b  jnz     short loc_180068A87
0x180068a6d  lea     rdx, [rbp+70h+var_E8]
0x180068a71  mov     rcx, r12
0x180068a74  call    WapAuthGetHostName
0x180068a79  mov     ebx, eax
0x180068a7b  test    eax, eax
0x180068a7d  jnz     loc_180068C63
0x180068a83  mov     r8, [rbp+70h+var_E8]
0x180068a87  mov     edx, dword ptr [rsp+170h+var_F8]
0x180068a8b  lea     r9, [rbp+70h+var_74]
0x180068a8f  mov     rcx, rdi
0x180068a92  call    cs:__imp_SeciAllocateAndSetCallTarget
0x180068a99  nop     dword ptr [rax+rax+00h]
0x180068a9e  test    eax, eax
0x180068aa0  jz      short loc_180068AD0
0x180068aa2  mov     ebx, 8
0x180068aa7  test    byte ptr cs:xmmword_1800AD710, bl
0x180068aad  jz      short loc_180068AC6
0x180068aaf  lea     edx, [rbx+0Ah]
0x180068ab2  mov     ecx, 203h
0x180068ab7  mov     r9d, eax
0x180068aba  lea     r8, WPP_05612d2d46af3ad8812821a8d7ec1cab_Traceguids
0x180068ac1  call    WPP_SF_d
0x180068ac6  mov     ebx, 5
0x180068acb  jmp     loc_180068C63
0x180068ad0  mov     rcx, [rbp+70h+var_C8]
0x180068ad4  lea     rax, [rbp+70h+var_70]
0x180068ad8  mov     r9d, [rbp+70h+fContextReq]; fContextReq
0x180068adc  add     rcx, 18h; phCredential
0x180068ae0  mov     rdx, [rbp+70h+phContext]; phContext
0x180068ae4  mov     [rsp+170h+ptsExpiry], rax; ptsExpiry
0x180068ae9  lea     rax, [rbp+70h+fContextReq]
0x180068aed  mov     [rsp+170h+pfContextAttr], rax; pfContextAttr
0x180068af2  lea     rax, [rbp+70h+var_88]
0x180068af6  mov     [rsp+170h+pOutput], rax; pOutput
0x180068afb  mov     rax, [rbp+70h+var_C0]
0x180068aff  mov     [rsp+170h+phNewContext], r15; phNewContext
0x180068b04  mov     [rsp+170h+Reserved2], r14d; Reserved2
0x180068b09  mov     [rsp+170h+pInput], rax; pInput
0x180068b0e  mov     rax, [rbp+70h+var_D8]
0x180068b12  mov     [rsp+170h+TargetDataRep], 10h; TargetDataRep
0x180068b1a  mov     [rsp+170h+Reserved1], r14d; Reserved1
0x180068b1f  mov     r8, [rax]; pszTargetName
0x180068b22  call    cs:__imp_InitializeSecurityContextW
0x180068b29  nop     dword ptr [rax+rax+00h]
0x180068b2e  mov     [rsi+28h], eax
0x180068b31  mov     r12d, eax
0x180068b34  test    eax, eax
0x180068b36  jns     short loc_180068B3F
0x180068b38  mov     ebx, eax
0x180068b3a  jmp     loc_180068C63
0x180068b3f  mov     rax, [rbp+70h+var_B8]
0x180068b43  mov     edi, 5
0x180068b48  cmp     [rax+10h], edi
0x180068b4b  jnz     short loc_180068B5F
0x180068b4d  mov     rcx, rsi
0x180068b50  call    WapAuthSspResolveSubScheme
0x180068b55  mov     ebx, eax
0x180068b57  test    eax, eax
0x180068b59  jnz     loc_180068C63
0x180068b5f  test    r12d, r12d
0x180068b62  jnz     short loc_180068B91
0x180068b64  test    byte ptr [rbp+70h+fContextReq], 2
0x180068b68  jz      short loc_180068B71
0x180068b6a  mov     rax, [rbp+70h+var_B0]
0x180068b6e  mov     byte ptr [rax], 1
0x180068b71  mov     rcx, r15; phContext
0x180068b74  call    cs:__imp_DeleteSecurityContext
0x180068b7b  nop     dword ptr [rax+rax+00h]
0x180068b80  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068b84  mov     [rsi+2Ch], r14b
0x180068b88  mov     [rsi+38h], rax
0x180068b8c  mov     [r15], rax
0x180068b8f  jmp     short loc_180068B9E
0x180068b91  cmp     r12d, 90312h
0x180068b98  jnz     short loc_180068B9E
0x180068b9a  mov     byte ptr [rsi+2Ch], 1
0x180068b9e  mov     eax, dword ptr [rbp+70h+var_A8]
0x180068ba1  test    eax, eax
0x180068ba3  jz      loc_180068C53
0x180068ba9  mov     ecx, eax
0x180068bab  lea     rdx, [rbp+70h+var_F0]
0x180068baf  call    WaBinaryToBase64Length
0x180068bb4  mov     ebx, eax
0x180068bb6  test    eax, eax
0x180068bb8  jnz     loc_180068C63
0x180068bbe  cmp     [rsi+40h], r14b
0x180068bc2  jz      short loc_180068BCD
0x180068bc4  lea     r15, Src; "Nego2"
0x180068bcb  jmp     short loc_180068BE1
0x180068bcd  mov     r15, [rbp+70h+var_D0]
0x180068bd1  lea     rax, WaAuthSchemeProperties
0x180068bd8  mov     rdi, [r15+rax+8]
0x180068bdd  mov     r15, [r15+rax]
0x180068be1  mov     rbx, [rbp+70h+var_F0]
0x180068be5  lea     rdx, [rbx+1]
0x180068be9  add     rdx, rdi
0x180068bec  cmp     rdx, rbx
0x180068bef  jnb     short loc_180068BF8
0x180068bf1  mov     ebx, 216h
0x180068bf6  jmp     short loc_180068C63
0x180068bf8  call    WxAllocateHeapEx
0x180068bfd  mov     r14, rax
0x180068c00  test    rax, rax
0x180068c03  jnz     short loc_180068C0A
0x180068c05  lea     ebx, [rax+8]
0x180068c08  jmp     short loc_180068C63
0x180068c0a  mov     r8d, dword ptr [rbp+70h+var_A8]
0x180068c0e  lea     r9, [rax+1]
0x180068c12  mov     rdx, qword ptr [rbp+70h+var_A8+8]
0x180068c16  lea     rax, [rbp+70h+var_F0]
0x180068c1a  mov     qword ptr [rsp+170h+TargetDataRep], rax
0x180068c1f  add     r9, rdi
  ... truncated ...
```
