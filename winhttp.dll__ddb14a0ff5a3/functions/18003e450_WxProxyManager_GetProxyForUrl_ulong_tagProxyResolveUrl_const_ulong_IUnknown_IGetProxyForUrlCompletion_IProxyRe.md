# WxProxyManager::GetProxyForUrl(ulong,tagProxyResolveUrl const *,ulong *,IUnknown *,IGetProxyForUrlCompletion *,IProxyResult * *)

- ea: `0x18003e450`
- end: `0x18003eba2`
- name: `?GetProxyForUrl@WxProxyManager@@UEAAJKPEBUtagProxyResolveUrl@@PEAKPEAUIUnknown@@PEAUIGetProxyForUrlCompletion@@PEAPEAUIProxyResult@@@Z`
- size: `1874`
- prototype: `__int64 __fastcall(WxProxyManager *__hidden this, unsigned int, const struct tagProxyResolveUrl *, unsigned int *, struct IUnknown *, struct IGetProxyForUrlCompletion *, struct IProxyResult **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bfd0`
- `0x18003e390`
- `0x18003e450`
- `0x18003f670`
- `0x1800403d4`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf008`
- `0x1800cf83c`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e5df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e6da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e7ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e5df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e6da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e7ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea7f`

## pseudocode

```c
__int64 __fastcall WxProxyManager::GetProxyForUrl(
        WxProxyManager *this,
        int a2,
        const struct tagProxyResolveUrl *a3,
        unsigned int *a4,
        struct IUnknown *a5,
        struct IGetProxyForUrlCompletion *a6,
        struct IProxyResult **a7)
{
  struct WxGetProxyContext *v10; // rbx
  int v11; // eax
  signed int v12; // r12d
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  struct tagProxyResolveUrl *v16; // rsi
  _WORD *v17; // r13
  void *v18; // r15
  __int64 v19; // r14
  size_t v20; // rdi
  void *v21; // rax
  _WORD *v22; // r8
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  _WORD *v26; // rcx
  signed int v27; // r14d
  struct WxGetProxyContext **v28; // r13
  void *v29; // r14
  struct WxGetProxyContext *v30; // rax
  __int64 v31; // rdi
  _WORD *v32; // rax
  _WORD *v33; // r13
  unsigned int v34; // eax
  __int64 v35; // r8
  struct WxGetProxyContext *v36; // rcx
  __int64 v37; // rdx
  void *v38; // rax
  _WORD *v39; // rdx
  signed int v40; // edi
  struct WxGetProxyContext *v41; // rax
  void *v42; // rdi
  size_t v43; // rcx
  _WORD *v44; // rax
  _WORD *v45; // r13
  unsigned __int64 v46; // r8
  struct WxGetProxyContext *v47; // rcx
  void *v48; // rax
  __int64 v49; // r9
  _WORD *v50; // rdx
  struct tagProxyResolveUrl *v51; // rax
  struct tagProxyResolveUrl *v52; // rcx
  int ProxyForUrl; // eax
  unsigned int v54; // edi
  struct IProxyResult *v55; // rax
  __int64 v57; // [rsp+20h] [rbp-60h]
  struct WxGetProxyContext *v58; // [rsp+30h] [rbp-50h] BYREF
  size_t v59; // [rsp+38h] [rbp-48h]
  size_t Size; // [rsp+40h] [rbp-40h]
  struct tagProxyResolveUrl *v61; // [rsp+48h] [rbp-38h] BYREF
  struct WxGetProxyContext **v62; // [rsp+50h] [rbp-30h]
  WxProxyManager *v63; // [rsp+58h] [rbp-28h]
  struct IProxyResult **v64; // [rsp+60h] [rbp-20h]
  struct IProxyResult *v65; // [rsp+68h] [rbp-18h] BYREF

  v64 = a7;
  v62 = (struct WxGetProxyContext **)a3;
  v63 = this;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 18, WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids);
  HIDWORD(v61) = 0;
  v10 = 0;
  v58 = 0;
  v65 = 0;
  if ( !a3 )
  {
    v12 = -2147024809;
    HIDWORD(v61) = 935;
LABEL_82:
    v54 = v12;
    goto LABEL_83;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_DSS(
      1029,
      19,
      (unsigned int)WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids,
      a2,
      *((_QWORD *)a3 + 1),
      *(_QWORD *)a3);
  *a7 = 0;
  v11 = WxGetProxyContext::CreateInstance(&v58);
  v10 = v58;
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( this )
      (*(void (__fastcall **)(WxProxyManager *))(*(_QWORD *)this + 8LL))(this);
    v13 = *((_QWORD *)v10 + 8);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)v10 + 8) = this;
    if ( a5 )
      ((void (__fastcall *)(struct IUnknown *))a5->lpVtbl->AddRef)(a5);
    v14 = *((_QWORD *)v10 + 11);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)v10 + 11) = a5;
    if ( a6 )
      (*(void (__fastcall **)(struct IGetProxyForUrlCompletion *))(*(_QWORD *)a6 + 8LL))(a6);
    v15 = *((_QWORD *)v10 + 9);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)v10 + 9) = a6;
    v16 = 0;
    *((_DWORD *)v10 + 25) = a2;
    *((_DWORD *)v10 + 24) = 0;
    v17 = (_WORD *)*((_QWORD *)a3 + 1);
    HIDWORD(v58) = 0;
    v61 = 0;
    if ( v17 )
    {
      if ( *(_QWORD *)a3 )
      {
        HIDWORD(v59) = 0;
        v18 = 0;
        v19 = -1;
        do
          ++v19;
        while ( v17[v19] );
        v58 = 0;
        v20 = 0;
        v59 = (unsigned int)(2 * v19 + 2);
        v21 = CoTaskMemAlloc(v59);
        Size = (size_t)v21;
        v12 = -2147024809;
        if ( !v21 )
        {
          v27 = -2147024882;
          HIDWORD(v59) = 544;
          goto LABEL_35;
        }
        memset_0(v21, 0, v59);
        v22 = (_WORD *)Size;
        v20 = Size;
        v58 = (struct WxGetProxyContext *)Size;
        v23 = v19 + 1;
        v24 = (unsigned int)(v19 + 1);
        if ( (_DWORD)v19 == -1 )
        {
          v27 = -2147024809;
          if ( !v23 )
            goto LABEL_33;
        }
        else if ( v23 <= 0x7FFFFFFFuLL )
        {
          v25 = 2147483646;
          do
          {
            if ( !v25 )
              break;
            if ( !*v17 )
              break;
            *v22++ = *v17++;
            --v25;
            --v24;
          }
          while ( v24 );
          v26 = v22 - 1;
          if ( v24 )
            v26 = v22;
          v27 = v24 == 0 ? 0x8007007A : 0;
          *v26 = 0;
LABEL_33:
          if ( v27 >= 0 )
          {
            v18 = (void *)v20;
            v58 = 0;
            v20 = 0;
            goto LABEL_35;
          }
          goto LABEL_110;
        }
        *(_WORD *)Size = 0;
        v27 = -2147024809;
LABEL_110:
        HIDWORD(v59) = 548;
LABEL_35:
        if ( v20 )
          WxCoTaskAllocator::Free((void **)&v58);
        if ( v27 < 0 )
        {
          HIDWORD(v58) = 374;
          v12 = v27;
LABEL_101:
          if ( v18 )
            CoTaskMemFree(v18);
LABEL_76:
          if ( v16 )
            FreeProxyResolveUrl(&v61);
          if ( v12 < 0 )
          {
            HIDWORD(v61) = 972;
          }
          else
          {
            ProxyForUrl = WxProxyManager::OnProcessGetProxyForUrl(v63, v10, &v65);
            v12 = ProxyForUrl;
            if ( ProxyForUrl < 0 )
            {
              HIDWORD(v61) = 978;
            }
            else
            {
              v54 = 787429;
              if ( ProxyForUrl == 787429 )
                goto LABEL_83;
              v55 = v65;
              v65 = 0;
              *v64 = v55;
            }
          }
          goto LABEL_82;
        }
        v28 = v62;
        v29 = 0;
        v30 = *v62;
        v58 = v30;
        if ( !v30 )
          goto LABEL_55;
        HIDWORD(v59) = 0;
        v31 = -1;
        do
          ++v31;
        while ( *((_WORD *)v30 + v31) );
        Size = (unsigned int)(2 * v31 + 2);
        v32 = CoTaskMemAlloc(Size);
        v33 = v32;
        if ( !v32 )
        {
          HIDWORD(Size) = 76;
          v40 = -2147024882;
          HIDWORD(v59) = 544;
LABEL_53:
          if ( v40 < 0 )
          {
            HIDWORD(v58) = 379;
            v12 = v40;
LABEL_99:
            if ( v29 )
              CoTaskMemFree(v29);
            goto LABEL_101;
          }
          v28 = v62;
LABEL_55:
          v41 = v28[2];
          v42 = 0;
          v58 = v41;
          if ( !v41 )
            goto LABEL_72;
          HIDWORD(v59) = 0;
          v43 = -1;
          do
            ++v43;
          while ( *((_WORD *)v41 + v43) );
          v59 = v43;
          Size = (unsigned int)(2 * v43 + 2);
          v44 = CoTaskMemAlloc(Size);
          v45 = v44;
          if ( !v44 )
          {
            HIDWORD(Size) = 76;
            v12 = -2147024882;
            HIDWORD(v59) = 544;
LABEL_70:
            if ( v12 < 0 )
            {
              HIDWORD(v58) = 384;
LABEL_97:
              if ( v42 )
                CoTaskMemFree(v42);
              goto LABEL_99;
            }
            v28 = v62;
LABEL_72:
            HIDWORD(Size) = 0;
            v16 = 0;
            v61 = 0;
            v51 = (struct tagProxyResolveUrl *)CoTaskMemAlloc(0x20u);
            v52 = v51;
            if ( v51 )
            {
              v61 = v51;
              *(_OWORD *)v51 = 0;
              v16 = v51;
              *((_OWORD *)v51 + 1) = 0;
              v12 = 0;
            }
            else
            {
              HIDWORD(Size) = 76;
              v12 = -2147024882;
              v52 = 0;
            }
            if ( v12 >= 0 )
            {
              *((_QWORD *)v52 + 1) = v18;
              *(_QWORD *)v16 = v29;
              *((_QWORD *)v52 + 2) = v42;
              *((_WORD *)v52 + 14) = *((_WORD *)v28 + 14);
              *((_DWORD *)v52 + 6) = *((_DWORD *)v28 + 6);
              *((_QWORD *)v10 + 10) = v16;
              v16 = 0;
              v61 = 0;
              goto LABEL_76;
            }
            HIDWORD(v58) = 387;
            goto LABEL_97;
          }
          memset_0(v44, 0, Size);
          v46 = (unsigned int)(v59 + 1);
          if ( (_DWORD)v59 != -1 )
          {
            if ( v46 <= 0x7FFFFFFF )
            {
              v47 = v58;
              v48 = v45;
              v49 = 2147483646;
              do
              {
                if ( !v49 )
                  break;
                if ( !*(_WORD *)v47 )
                  break;
                *v45 = *(_WORD *)v47;
                v47 = (struct WxGetProxyContext *)((char *)v47 + 2);
                ++v45;
                --v49;
                --v46;
              }
              while ( v46 );
              v50 = v45 - 1;
              if ( v46 )
                v50 = v45;
              v12 = v46 == 0 ? 0x8007007A : 0;
              *v50 = 0;
              goto LABEL_68;
            }
            *v45 = 0;
          }
          v48 = v45;
LABEL_68:
          if ( v12 < 0 )
          {
            HIDWORD(v59) = 548;
            if ( v48 )
              CoTaskMemFree(v48);
          }
          else
          {
            v42 = v48;
          }
          goto LABEL_70;
        }
        memset_0(v32, 0, Size);
        v34 = v31 + 1;
        v35 = (unsigned int)(v31 + 1);
        if ( (_DWORD)v31 == -1 )
        {
          v40 = -2147024809;
          if ( !v34 )
          {
LABEL_113:
            v38 = v33;
LABEL_51:
            if ( v40 < 0 )
            {
              HIDWORD(v59) = 548;
              if ( v38 )
                CoTaskMemFree(v38);
            }
            else
            {
              v29 = v38;
            }
            goto LABEL_53;
          }
        }
        else
        {
          if ( v34 <= 0x7FFFFFFFuLL )
          {
            v36 = v58;
            v37 = 2147483646;
            v38 = v33;
            do
            {
              if ( !v37 )
                break;
              if ( !*(_WORD *)v36 )
                break;
              *v33 = *(_WORD *)v36;
              v36 = (struct WxGetProxyContext *)((char *)v36 + 2);
              ++v33;
              --v37;
              --v35;
            }
            while ( v35 );
            v39 = v33 - 1;
            if ( v35 )
              v39 = v33;
            v40 = v35 == 0 ? 0x8007007A : 0;
            *v39 = 0;
            goto LABEL_51;
          }
          v40 = -2147024809;
        }
        *v33 = 0;
        goto LABEL_113;
      }
      HIDWORD(v58) = 370;
    }
    else
    {
      HIDWORD(v58) = 369;
    }
    v12 = -2147024809;
    goto LABEL_76;
  }
  HIDWORD(v61) = 948;
  v54 = v11;
LABEL_83:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 20, WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids, (unsigned int)v12, v57);
  if ( v65 )
  {
    (*(void (__fastcall **)(struct IProxyResult *))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(struct WxGetProxyContext *))(*(_QWORD *)v10 + 8LL))(v10);
  return v54;
}

```

## disassembly

```asm
0x18003e450  mov     [rsp-38h+arg_18], rbx
0x18003e455  push    rbp
0x18003e456  push    rsi
0x18003e457  push    rdi
0x18003e458  push    r12
0x18003e45a  push    r13
0x18003e45c  push    r14
0x18003e45e  push    r15
0x18003e460  mov     rbp, rsp
0x18003e463  sub     rsp, 80h
0x18003e46a  mov     rax, cs:__security_cookie
0x18003e471  xor     rax, rsp
0x18003e474  mov     [rbp+var_10], rax
0x18003e478  mov     r12, [rbp+arg_30]
0x18003e47c  mov     r15, r8
0x18003e47f  mov     rdi, [rbp+arg_20]
0x18003e483  mov     r14d, edx
0x18003e486  mov     rsi, [rbp+arg_28]
0x18003e48a  mov     r13, rcx
0x18003e48d  mov     [rbp+var_20], r12
0x18003e491  mov     [rbp+var_30], r8
0x18003e495  mov     [rbp+var_28], rcx
0x18003e499  test    byte ptr cs:xmmword_180107A60, 20h
0x18003e4a0  jnz     loc_18003EAD0
0x18003e4a6  xor     r10d, r10d
0x18003e4a9  mov     dword ptr [rbp+var_38+4], r10d
0x18003e4ad  mov     ebx, r10d
0x18003e4b0  mov     [rbp+var_50], rbx
0x18003e4b4  mov     [rbp+var_18], r10
0x18003e4b8  test    r15, r15
0x18003e4bb  jz      loc_18003E984
0x18003e4c1  test    byte ptr cs:xmmword_180107A60, 20h
0x18003e4c8  jnz     loc_18003EAEB
0x18003e4ce  lea     rcx, [rbp+var_50]; struct WxGetProxyContext **
0x18003e4d2  mov     [r12], r10
0x18003e4d6  call    ?CreateInstance@WxGetProxyContext@@SAJPEAPEAV1@@Z; WxGetProxyContext::CreateInstance(WxGetProxyContext * *)
0x18003e4db  mov     rbx, [rbp+var_50]
0x18003e4df  xor     r10d, r10d
0x18003e4e2  mov     r12d, eax
0x18003e4e5  test    eax, eax
0x18003e4e7  js      loc_18003EB1D
0x18003e4ed  test    r13, r13
0x18003e4f0  jz      short loc_18003E505
0x18003e4f2  mov     rax, [r13+0]
0x18003e4f6  mov     rcx, r13
0x18003e4f9  mov     rax, [rax+8]
0x18003e4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e502  xor     r10d, r10d
0x18003e505  mov     rcx, [rbx+40h]
0x18003e509  test    rcx, rcx
0x18003e50c  jz      short loc_18003E51D
0x18003e50e  mov     rax, [rcx]
0x18003e511  mov     rax, [rax+10h]
0x18003e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e51a  xor     r10d, r10d
0x18003e51d  mov     [rbx+40h], r13
0x18003e521  test    rdi, rdi
0x18003e524  jz      short loc_18003E538
0x18003e526  mov     rax, [rdi]
0x18003e529  mov     rcx, rdi
0x18003e52c  mov     rax, [rax+8]
0x18003e530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e535  xor     r10d, r10d
0x18003e538  mov     rcx, [rbx+58h]
0x18003e53c  test    rcx, rcx
0x18003e53f  jz      short loc_18003E550
0x18003e541  mov     rax, [rcx]
0x18003e544  mov     rax, [rax+10h]
0x18003e548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e54d  xor     r10d, r10d
0x18003e550  mov     [rbx+58h], rdi
0x18003e554  test    rsi, rsi
0x18003e557  jz      short loc_18003E56B
0x18003e559  mov     rax, [rsi]
0x18003e55c  mov     rcx, rsi
0x18003e55f  mov     rax, [rax+8]
0x18003e563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e568  xor     r10d, r10d
0x18003e56b  mov     rcx, [rbx+48h]
0x18003e56f  test    rcx, rcx
0x18003e572  jz      short loc_18003E583
0x18003e574  mov     rax, [rcx]
0x18003e577  mov     rax, [rax+10h]
0x18003e57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e580  xor     r10d, r10d
0x18003e583  mov     [rbx+48h], rsi
0x18003e587  mov     rsi, r10
0x18003e58a  mov     [rbx+64h], r14d
0x18003e58e  mov     [rbx+60h], r10d
0x18003e592  mov     r13, [r15+8]
0x18003e596  mov     dword ptr [rbp+var_50+4], r10d
0x18003e59a  mov     [rbp-38h], r10
0x18003e59e  test    r13, r13
0x18003e5a1  jz      loc_18003E993
0x18003e5a7  cmp     [r15], r10
0x18003e5aa  jz      loc_18003EB2B
0x18003e5b0  mov     [rbp+var_44], r10d
0x18003e5b4  mov     r15, r10
0x18003e5b7  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003e5bb  inc     r14
0x18003e5be  cmp     [r13+r14*2+0], r10w
0x18003e5c4  jnz     short loc_18003E5BB
0x18003e5c6  lea     eax, ds:2[r14*2]
0x18003e5ce  mov     [rbp+var_44], r10d
0x18003e5d2  mov     ecx, eax; cb
0x18003e5d4  mov     [rbp+var_50], r10
0x18003e5d8  mov     rdi, r10
0x18003e5db  mov     [rbp-48h], rax
0x18003e5df  call    cs:__imp_CoTaskMemAlloc
0x18003e5e5  xor     r10d, r10d
0x18003e5e8  mov     [rbp+Size], rax
0x18003e5ec  mov     r12d, 80070057h
0x18003e5f2  test    rax, rax
0x18003e5f5  jz      loc_18003E9E7
0x18003e5fb  mov     r8, [rbp-48h]; Size
0x18003e5ff  xor     edx, edx; Val
0x18003e601  mov     rcx, rax; void *
0x18003e604  call    memset_0
0x18003e609  mov     r8, [rbp+Size]
0x18003e60d  mov     rdi, r8
0x18003e610  mov     [rbp+var_50], r8
0x18003e614  lea     eax, [r14+1]
0x18003e618  xor     r10d, r10d
0x18003e61b  mov     edx, eax
0x18003e61d  test    eax, eax
0x18003e61f  jz      loc_18003EA8D
0x18003e625  cmp     rdx, 7FFFFFFFh
0x18003e62c  ja      loc_18003EA98
0x18003e632  mov     eax, 7FFFFFFEh
0x18003e637  test    rax, rax
0x18003e63a  jz      short loc_18003E65B
0x18003e63c  movzx   ecx, word ptr [r13+0]
0x18003e641  test    cx, cx
0x18003e644  jz      short loc_18003E65B
0x18003e646  mov     [r8], cx
0x18003e64a  add     r13, 2
0x18003e64e  add     r8, 2
0x18003e652  dec     rax
0x18003e655  sub     rdx, 1
0x18003e659  jnz     short loc_18003E637
0x18003e65b  test    rdx, rdx
0x18003e65e  lea     rcx, [r8-2]
0x18003e662  cmovnz  rcx, r8
0x18003e666  neg     rdx
0x18003e669  sbb     r14d, r14d
0x18003e66c  not     r14d
0x18003e66f  and     r14d, 8007007Ah
0x18003e676  mov     [rcx], r10w
0x18003e67a  test    r14d, r14d
0x18003e67d  js      loc_18003EA9F
0x18003e683  mov     r15, rdi
0x18003e686  mov     [rbp+var_50], r10
0x18003e68a  mov     rdi, r10
0x18003e68d  test    rdi, rdi
0x18003e690  jnz     loc_18003E9D6
0x18003e696  test    r14d, r14d
0x18003e699  js      loc_18003EA3F
0x18003e69f  mov     r13, [rbp+var_30]
0x18003e6a3  mov     r14, r10
0x18003e6a6  mov     rax, [r13+0]
0x18003e6aa  mov     [rbp+var_50], rax
0x18003e6ae  test    rax, rax
0x18003e6b1  jz      loc_18003E77F
0x18003e6b7  mov     [rbp+var_44], r10d
0x18003e6bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e6bf  inc     rdi
0x18003e6c2  cmp     [rax+rdi*2], r10w
0x18003e6c7  jnz     short loc_18003E6BF
0x18003e6c9  lea     eax, ds:2[rdi*2]
0x18003e6d0  mov     dword ptr [rbp+Size+4], r10d
0x18003e6d4  mov     ecx, eax; cb
0x18003e6d6  mov     [rbp+Size], rax
0x18003e6da  call    cs:__imp_CoTaskMemAlloc
0x18003e6e0  xor     r10d, r10d
0x18003e6e3  mov     r13, rax
0x18003e6e6  test    rax, rax
0x18003e6e9  jz      loc_18003E9BE
0x18003e6ef  mov     r8, [rbp+Size]; Size
0x18003e6f3  xor     edx, edx; Val
0x18003e6f5  mov     rcx, rax; void *
0x18003e6f8  call    memset_0
0x18003e6fd  lea     eax, [rdi+1]
0x18003e700  xor     r10d, r10d
0x18003e703  mov     r8d, eax
0x18003e706  test    eax, eax
0x18003e708  jz      loc_18003EAAB
0x18003e70e  cmp     r8, 7FFFFFFFh
0x18003e715  ja      loc_18003EB37
0x18003e71b  mov     rcx, [rbp+var_50]
0x18003e71f  mov     edx, 7FFFFFFEh
0x18003e724  mov     rax, r13
0x18003e727  test    rdx, rdx
0x18003e72a  jz      short loc_18003E74C
0x18003e72c  movzx   r9d, word ptr [rcx]
0x18003e730  test    r9w, r9w
0x18003e734  jz      short loc_18003E74C
0x18003e736  mov     [r13+0], r9w
0x18003e73b  add     rcx, 2
0x18003e73f  add     r13, 2
0x18003e743  dec     rdx
0x18003e746  sub     r8, 1
0x18003e74a  jnz     short loc_18003E727
0x18003e74c  test    r8, r8
0x18003e74f  lea     rdx, [r13-2]
0x18003e753  cmovnz  rdx, r13
0x18003e757  neg     r8
0x18003e75a  sbb     edi, edi
0x18003e75c  not     edi
0x18003e75e  and     edi, 8007007Ah
0x18003e764  mov     [rdx], r10w
0x18003e768  test    edi, edi
0x18003e76a  js      loc_18003EA6C
0x18003e770  mov     r14, rax
0x18003e773  test    edi, edi
0x18003e775  js      loc_18003EA00
0x18003e77b  mov     r13, [rbp+var_30]
0x18003e77f  mov     rax, [r13+10h]
0x18003e783  mov     rdi, r10
0x18003e786  mov     [rbp+var_50], rax
0x18003e78a  test    rax, rax
0x18003e78d  jz      loc_18003E865
0x18003e793  mov     [rbp+var_44], r10d
0x18003e797  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003e79b  inc     rcx
0x18003e79e  cmp     [rax+rcx*2], r10w
0x18003e7a3  jnz     short loc_18003E79B
0x18003e7a5  lea     eax, ds:2[rcx*2]
0x18003e7ac  mov     [rbp-48h], rcx
0x18003e7b0  mov     dword ptr [rbp+Size+4], r10d
0x18003e7b4  mov     ecx, eax; cb
0x18003e7b6  mov     [rbp+Size], rax
0x18003e7ba  call    cs:__imp_CoTaskMemAlloc
0x18003e7c0  xor     r10d, r10d
0x18003e7c3  mov     r13, rax
0x18003e7c6  test    rax, rax
0x18003e7c9  jz      loc_18003E9A5
0x18003e7cf  mov     r8, [rbp+Size]; Size
0x18003e7d3  xor     edx, edx; Val
0x18003e7d5  mov     rcx, rax; void *
0x18003e7d8  call    memset_0
0x18003e7dd  mov     rax, [rbp-48h]
0x18003e7e1  xor     r10d, r10d
0x18003e7e4  add     eax, 1
0x18003e7e7  mov     r8d, eax
0x18003e7ea  jz      loc_18003EABF
0x18003e7f0  cmp     r8, 7FFFFFFFh
0x18003e7f7  ja      loc_18003EAC3
0x18003e7fd  mov     rcx, [rbp+var_50]
0x18003e801  mov     rax, r13
0x18003e804  mov     r9d, 7FFFFFFEh
0x18003e80a  test    r9, r9
0x18003e80d  jz      short loc_18003E82D
0x18003e80f  movzx   edx, word ptr [rcx]
0x18003e812  test    dx, dx
0x18003e815  jz      short loc_18003E82D
0x18003e817  mov     [r13+0], dx
0x18003e81c  add     rcx, 2
0x18003e820  add     r13, 2
0x18003e824  dec     r9
0x18003e827  sub     r8, 1
0x18003e82b  jnz     short loc_18003E80A
0x18003e82d  test    r8, r8
0x18003e830  lea     rdx, [r13-2]
0x18003e834  cmovnz  rdx, r13
0x18003e838  neg     r8
0x18003e83b  sbb     r12d, r12d
0x18003e83e  not     r12d
0x18003e841  and     r12d, 8007007Ah
0x18003e848  mov     [rdx], r10w
0x18003e84c  test    r12d, r12d
0x18003e84f  js      loc_18003EA4B
0x18003e855  mov     rdi, rax
0x18003e858  test    r12d, r12d
0x18003e85b  js      loc_18003EB3F
0x18003e861  mov     r13, [rbp+var_30]
0x18003e865  mov     ecx, 20h ; ' '; cb
0x18003e86a  mov     dword ptr [rbp+Size+4], r10d
0x18003e86e  mov     rsi, r10
0x18003e871  mov     [rbp-38h], r10
0x18003e875  call    cs:__imp_CoTaskMemAlloc
0x18003e87b  xor     r10d, r10d
0x18003e87e  mov     rcx, rax
0x18003e881  test    rax, rax
0x18003e884  jz      loc_18003EB4B
0x18003e88a  xorps   xmm0, xmm0
0x18003e88d  mov     [rbp-38h], rax
0x18003e891  movups  xmmword ptr [rax], xmm0
0x18003e894  mov     rsi, rax
0x18003e897  movups  xmmword ptr [rax+10h], xmm0
0x18003e89b  mov     r12d, r10d
0x18003e89e  test    r12d, r12d
0x18003e8a1  js      loc_18003EB60
0x18003e8a7  mov     [rcx+8], r15
0x18003e8ab  mov     [rsi], r14
0x18003e8ae  mov     [rcx+10h], rdi
0x18003e8b2  movzx   eax, word ptr [r13+1Ch]
0x18003e8b7  mov     [rcx+1Ch], ax
0x18003e8bb  mov     eax, [r13+18h]
0x18003e8bf  mov     [rcx+18h], eax
0x18003e8c2  mov     [rbx+50h], rsi
  ... truncated ...
```
