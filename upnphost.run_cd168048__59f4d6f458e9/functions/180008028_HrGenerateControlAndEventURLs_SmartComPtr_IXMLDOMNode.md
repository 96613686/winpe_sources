# HrGenerateControlAndEventURLs(SmartComPtr<IXMLDOMNode> &)

- ea: `0x180008028`
- end: `0x180008682`
- name: `?HrGenerateControlAndEventURLs@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z`
- size: `1626`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030ba4`

## callees

- `0x180003e08`
- `0x1800056d8`
- `0x1800056f0`
- `0x180008028`
- `0x180009d50`
- `0x18000a060`
- `0x18000b2c8`
- `0x18000f8a0`
- `0x18002a030`
- `0x18003a798`
- `0x18003b1cc`
- `0x180045b90`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008096`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800081b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008299`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008314`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008323`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008332`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008342`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008351`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008368`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800083d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008451`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800084c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008555`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008580`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800085ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008610`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008096`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800081b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008299`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008314`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008323`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008332`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008342`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008351`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008368`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800083d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008451`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800084c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008555`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008580`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800085ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008610`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008170`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000824e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008406`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008170`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000824e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008406`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008235`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008235`

## string_xrefs

- `0x180008133`: `ddd:serviceId`
- `0x180008227`: `REMOVE`
- `0x1800080e5`: `ddd:serviceList/ddd:service`
- `0x180008042`: `udhisapi.dll?control=`
- `0x1800084db`: `udhisapi.dll?event=`

## pseudocode

```c
__int64 __fastcall HrGenerateControlAndEventURLs(__int64 a1)
{
  wchar_t *v2; // r14
  HRESULT v3; // r15d
  bool v4; // zf
  void *v6; // rsi
  __int64 v7; // rax
  size_t v8; // r12
  const wchar_t *v9; // rcx
  _WORD *v10; // rdi
  size_t v11; // r8
  HRESULT v12; // eax
  size_t v13; // rdx
  size_t *v14; // r8
  HRESULT v15; // ebx
  unsigned __int16 *v16; // rdi
  WCHAR *v17; // rbx
  int v18; // eax
  size_t v19; // r8
  wchar_t *v20; // r12
  size_t v21; // rdx
  size_t *v22; // r8
  wchar_t *v23; // rbx
  size_t v24; // r8
  size_t v25; // rdx
  size_t *v26; // r8
  HRESULT v27; // eax
  size_t v28; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v29; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-28h]
  __int64 v31; // [rsp+40h] [rbp-20h] BYREF
  void *Block; // [rsp+48h] [rbp-18h] BYREF
  void *v33[2]; // [rsp+50h] [rbp-10h] BYREF
  wchar_t *v34; // [rsp+A8h] [rbp+48h] BYREF
  void *v35; // [rsp+B0h] [rbp+50h] BYREF
  LPCWSTR lpString1; // [rsp+B8h] [rbp+58h] BYREF

  v33[0] = 0;
  Block = 0;
  v2 = 0;
  v34 = 0;
  v3 = CUString::HrAssign((CUString *)v33, L"udhisapi.dll?control=");
  if ( v3 >= 0 )
  {
    v3 = CUString::HrAssign((CUString *)&Block, L"udhisapi.dll?event=");
    if ( v3 >= 0 )
    {
      v27 = HrSelectNodeText((OLECHAR *)L"ddd:UDN");
      v2 = v34;
      v3 = v27;
    }
  }
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v31);
  v4 = v3 == 0;
  if ( v3 >= 0 )
  {
    v3 = HrSelectNodes(L"ddd:serviceList/ddd:service", a1, &v31);
    if ( v3 < 0 )
    {
LABEL_6:
      v4 = v3 == 0;
      goto LABEL_3;
    }
    while ( 1 )
    {
      v4 = v3 == 0;
      if ( v3 < 0 )
        goto LABEL_3;
      SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v34);
      if ( (*(unsigned int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v31 + 72LL))(v31, &v34) )
      {
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v34);
        goto LABEL_6;
      }
      v30 = 0;
      v3 = HrSelectNodeText((OLECHAR *)L"ddd:serviceId");
      if ( v3 >= 0 )
        break;
LABEL_35:
      free(v30);
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v34);
    }
    v35 = 0;
    v6 = 0;
    if ( !v2 )
    {
      free(0);
LABEL_36:
      v3 = CUString::HrAppend((CUString *)&v35, L"+");
      if ( v3 >= 0 )
        v3 = CUString::HrAppend((CUString *)&v35, v30);
      v6 = v35;
LABEL_19:
      v29 = 0;
      v16 = 0;
      lpString1 = 0;
      if ( v3 < 0
        || (v3 = CUString::HrAssign((CUString *)&v29, (const struct CUString *)v33), v3 < 0)
        || (v3 = CUString::HrAppend((CUString *)&v29, (const unsigned __int16 *)v6), v3 < 0) )
      {
LABEL_20:
        v17 = 0;
        lpString1 = 0;
        if ( v3 < 0 )
          goto LABEL_34;
        v18 = HrSelectNodeText((OLECHAR *)L"ddd:eventSubURL");
        v17 = (WCHAR *)lpString1;
        v3 = v18;
        if ( v18 < 0 )
          goto LABEL_34;
        v35 = 0;
        if ( !lstrcmpiW(lpString1, L"REMOVE") )
        {
          lpString1 = 0;
          v3 = CUString::HrAssign((CUString *)&lpString1, &Format);
          if ( v3 >= 0 )
            v3 = HrSelectAndSetNodeText((OLECHAR *)L"ddd:eventSubURL");
          free((void *)lpString1);
          goto LABEL_33;
        }
        v20 = (wchar_t *)malloc(0x16u);
        if ( v20 )
        {
          v3 = StringValidateDestW((STRSAFE_PCNZWCH)0xB, 0xBu, v19);
          if ( v3 < 0 )
          {
            *v20 = 0;
          }
          else
          {
            v3 = StringCopyWorkerW(v20, v21, v22, L"/upnphost/", v28);
            if ( v3 >= 0 )
            {
              free(0);
              v35 = v20;
              if ( !v3 )
              {
LABEL_27:
                v3 = CUString::HrAppend((CUString *)&v35, v16);
                if ( v3 >= 0 )
                  v3 = HrSelectAndSetNodeText((OLECHAR *)L"ddd:eventSubURL");
LABEL_33:
                free(v35);
LABEL_34:
                free(v17);
                free(v16);
                free(v29);
                free(v6);
                goto LABEL_35;
              }
LABEL_29:
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
                  (unsigned int)v3);
              if ( v3 < 0 )
                goto LABEL_33;
              goto LABEL_27;
            }
          }
          free(v20);
          goto LABEL_29;
        }
        v3 = -2147024882;
        goto LABEL_29;
      }
      v3 = CUString::HrAssign((CUString *)&lpString1, (const struct CUString *)&Block);
      if ( v3 < 0 || (v3 = CUString::HrAppend((CUString *)&lpString1, (const unsigned __int16 *)v6), v3 < 0) )
      {
LABEL_54:
        v16 = (unsigned __int16 *)lpString1;
        goto LABEL_20;
      }
      v35 = 0;
      v23 = (wchar_t *)malloc(0x16u);
      if ( v23 )
      {
        v3 = StringValidateDestW((STRSAFE_PCNZWCH)0xB, 0xBu, v24);
        if ( v3 < 0 )
        {
          *v23 = 0;
        }
        else
        {
          v3 = StringCopyWorkerW(v23, v25, v26, L"/upnphost/", v28);
          if ( v3 >= 0 )
          {
            free(0);
            v35 = v23;
            if ( !v3 )
            {
LABEL_47:
              v3 = CUString::HrAppend((CUString *)&v35, v29);
              if ( v3 >= 0 )
                v3 = HrSelectAndSetNodeText((OLECHAR *)L"ddd:controlURL");
LABEL_53:
              free(v35);
              goto LABEL_54;
            }
LABEL_49:
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
                (unsigned int)v3);
            if ( v3 < 0 )
              goto LABEL_53;
            goto LABEL_47;
          }
        }
        free(v23);
        goto LABEL_49;
      }
      v3 = -2147024882;
      goto LABEL_49;
    }
    v7 = -1;
    do
      ++v7;
    while ( v2[v7] );
    v8 = v7 + 1;
    v10 = malloc(2 * (v7 + 1));
    if ( !v10 )
    {
      v3 = -2147024882;
LABEL_57:
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
          (unsigned int)v3);
LABEL_18:
      if ( v3 < 0 )
        goto LABEL_19;
      goto LABEL_36;
    }
    v12 = StringValidateDestW(v9, v8, v11);
    v3 = v12;
    if ( v12 < 0 )
    {
      v15 = v12;
      if ( v8 )
      {
        *v10 = 0;
LABEL_64:
        free(v10);
        goto LABEL_57;
      }
    }
    else
    {
      v15 = StringCopyWorkerW(v10, v13, v14, v2, v28);
    }
    v3 = v15;
    if ( v15 >= 0 )
    {
      free(0);
      v6 = v10;
      v35 = v10;
      if ( !v15 )
        goto LABEL_18;
      goto LABEL_57;
    }
    goto LABEL_64;
  }
LABEL_3:
  if ( !v4 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v3);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v31);
  free(v2);
  free(Block);
  free(v33[0]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008028  mov     [rsp-38h+arg_0], rbx
0x18000802d  push    rbp
0x18000802e  push    rsi
0x18000802f  push    rdi
0x180008030  push    r12
0x180008032  push    r13
0x180008034  push    r14
0x180008036  push    r15
0x180008038  mov     rbp, rsp
0x18000803b  sub     rsp, 60h
0x18000803f  xor     r13d, r13d
0x180008042  lea     rdx, aUdhisapiDllCon; "udhisapi.dll?control="
0x180008049  mov     rbx, rcx
0x18000804c  mov     [rbp+var_10], r13
0x180008050  lea     rcx, [rbp+var_10]; this
0x180008054  mov     [rbp+Block], r13
0x180008058  mov     r14d, r13d
0x18000805b  mov     [rbp+arg_8], r13
0x18000805f  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180008064  mov     r15d, eax
0x180008067  test    eax, eax
0x180008069  jns     loc_1800084DB
0x18000806f  lea     rcx, [rbp+var_20]; void *
0x180008073  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180008078  lea     r12, WPP_GLOBAL_Control
0x18000807f  test    r15d, r15d
0x180008082  jns     short loc_1800080DE
0x180008084  jnz     loc_18000864B
0x18000808a  lea     rcx, [rbp+var_20]
0x18000808e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180008093  mov     rcx, r14; Block
0x180008096  call    cs:__imp_free
0x18000809d  nop     dword ptr [rax+rax+00h]
0x1800080a2  mov     rcx, [rbp+Block]; Block
0x1800080a6  call    cs:__imp_free
0x1800080ad  nop     dword ptr [rax+rax+00h]
0x1800080b2  mov     rcx, [rbp+var_10]; Block
0x1800080b6  call    cs:__imp_free
0x1800080bd  nop     dword ptr [rax+rax+00h]
0x1800080c2  mov     rbx, [rsp+60h+arg_0]
0x1800080ca  mov     eax, r15d
0x1800080cd  add     rsp, 60h
0x1800080d1  pop     r15
0x1800080d3  pop     r14
0x1800080d5  pop     r13
0x1800080d7  pop     r12
0x1800080d9  pop     rdi
0x1800080da  pop     rsi
0x1800080db  pop     rbp
0x1800080dc  retn
0x1800080de  lea     r8, [rbp+var_20]
0x1800080e2  mov     rdx, rbx
0x1800080e5  lea     rcx, aDddServicelist_0; "ddd:serviceList/ddd:service"
0x1800080ec  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x1800080f1  mov     r15d, eax
0x1800080f4  test    eax, eax
0x1800080f6  jns     short loc_1800080FD
0x1800080f8  test    r15d, r15d
0x1800080fb  jmp     short loc_180008084
0x1800080fd  test    r15d, r15d
0x180008100  js      short loc_180008084
0x180008102  lea     rcx, [rbp+arg_8]; void *
0x180008106  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000810b  mov     rcx, [rbp+var_20]
0x18000810f  lea     rdx, [rbp+arg_8]
0x180008113  mov     rax, [rcx]
0x180008116  mov     rax, [rax+48h]
0x18000811a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811f  test    eax, eax
0x180008121  jnz     loc_18000863D
0x180008127  lea     r8, [rbp+var_28]
0x18000812b  mov     [rbp+var_28], r13
0x18000812f  lea     rdx, [rbp+arg_8]
0x180008133  lea     rcx, aDddServiceid; "ddd:serviceId"
0x18000813a  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000813f  mov     r15d, eax
0x180008142  test    eax, eax
0x180008144  js      loc_180008364
0x18000814a  mov     [rbp+arg_10], r13
0x18000814e  mov     rsi, r13
0x180008151  test    r14, r14
0x180008154  jz      loc_180008553
0x18000815a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000815e  inc     rax
0x180008161  cmp     [r14+rax*2], r13w
0x180008166  jnz     short loc_18000815E
0x180008168  lea     r12, [rax+1]
0x18000816c  lea     rcx, [r12+r12]; Size
0x180008170  call    cs:__imp_malloc
0x180008177  nop     dword ptr [rax+rax+00h]
0x18000817c  mov     rdi, rax
0x18000817f  test    rax, rax
0x180008182  jz      loc_180008566
0x180008188  mov     rdx, r12; cchDest
0x18000818b  call    StringValidateDestW
0x180008190  mov     r15d, eax
0x180008193  test    eax, eax
0x180008195  js      loc_18000856E
0x18000819b  mov     r9, r14; pszSrc
0x18000819e  mov     rcx, rdi; pszDest
0x1800081a1  call    StringCopyWorkerW
0x1800081a6  mov     ebx, eax
0x1800081a8  mov     r15d, ebx
0x1800081ab  test    ebx, ebx
0x1800081ad  js      loc_18000857D
0x1800081b3  xor     ecx, ecx; Block
0x1800081b5  call    cs:__imp_free
0x1800081bc  nop     dword ptr [rax+rax+00h]
0x1800081c1  mov     rsi, rdi
0x1800081c4  mov     [rbp+arg_10], rdi
0x1800081c8  test    ebx, ebx
0x1800081ca  jnz     loc_180008515
0x1800081d0  lea     r12, WPP_GLOBAL_Control
0x1800081d7  test    r15d, r15d
0x1800081da  jns     loc_180008382
0x1800081e0  mov     [rbp+var_30], r13
0x1800081e4  mov     rdi, r13
0x1800081e7  mov     [rbp+lpString1], r13
0x1800081eb  test    r15d, r15d
0x1800081ee  jns     loc_18000858E
0x1800081f4  mov     rbx, r13
0x1800081f7  mov     [rbp+lpString1], rbx
0x1800081fb  test    r15d, r15d
0x1800081fe  js      loc_180008320
0x180008204  lea     r8, [rbp+lpString1]
0x180008208  lea     rdx, [rbp+arg_8]
0x18000820c  lea     rcx, aDddEventsuburl_0; "ddd:eventSubURL"
0x180008213  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x180008218  mov     rbx, [rbp+lpString1]
0x18000821c  mov     r15d, eax
0x18000821f  test    eax, eax
0x180008221  js      loc_180008320
0x180008227  lea     rdx, aRemove; "REMOVE"
0x18000822e  mov     [rbp+arg_10], r13
0x180008232  mov     rcx, rbx; lpString1
0x180008235  call    cs:__imp_lstrcmpiW
0x18000823c  nop     dword ptr [rax+rax+00h]
0x180008241  test    eax, eax
0x180008243  jz      loc_1800083B2
0x180008249  mov     ecx, 16h; Size
0x18000824e  call    cs:__imp_malloc
0x180008255  nop     dword ptr [rax+rax+00h]
0x18000825a  mov     r12, rax
0x18000825d  test    rax, rax
0x180008260  jz      loc_1800085FD
0x180008266  mov     ecx, 0Bh; pszDest
0x18000826b  mov     edx, ecx; cchDest
0x18000826d  call    StringValidateDestW
0x180008272  mov     r15d, eax
0x180008275  test    eax, eax
0x180008277  js      loc_180008608
0x18000827d  lea     r9, aUpnphost; "/upnphost/"
0x180008284  mov     rcx, r12; pszDest
0x180008287  call    StringCopyWorkerW
0x18000828c  mov     r15d, eax
0x18000828f  test    eax, eax
0x180008291  js      loc_18000860D
0x180008297  xor     ecx, ecx; Block
0x180008299  call    cs:__imp_free
0x1800082a0  nop     dword ptr [rax+rax+00h]
0x1800082a5  mov     [rbp+arg_10], r12
0x1800082a9  test    r15d, r15d
0x1800082ac  jnz     short loc_1800082DA
0x1800082ae  mov     rdx, rdi; unsigned __int16 *
0x1800082b1  lea     rcx, [rbp+arg_10]; this
0x1800082b5  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800082ba  mov     r15d, eax
0x1800082bd  test    eax, eax
0x1800082bf  js      short loc_180008310
0x1800082c1  lea     r8, [rbp+arg_10]
0x1800082c5  lea     rdx, [rbp+arg_8]
0x1800082c9  lea     rcx, aDddEventsuburl_0; "ddd:eventSubURL"
0x1800082d0  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x1800082d5  mov     r15d, eax
0x1800082d8  jmp     short loc_180008310
0x1800082da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082e1  lea     rax, WPP_GLOBAL_Control
0x1800082e8  cmp     rcx, rax
0x1800082eb  jz      short loc_18000830B
0x1800082ed  test    byte ptr [rcx+1Ch], 1
0x1800082f1  jz      short loc_18000830B
0x1800082f3  mov     rcx, [rcx+10h]
0x1800082f7  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800082fe  mov     edx, 0Ah
0x180008303  mov     r9d, r15d
0x180008306  call    WPP_SF_d
0x18000830b  test    r15d, r15d
0x18000830e  jns     short loc_1800082AE
0x180008310  mov     rcx, [rbp+arg_10]; Block
0x180008314  call    cs:__imp_free
0x18000831b  nop     dword ptr [rax+rax+00h]
0x180008320  mov     rcx, rbx; Block
0x180008323  call    cs:__imp_free
0x18000832a  nop     dword ptr [rax+rax+00h]
0x18000832f  mov     rcx, rdi; Block
0x180008332  call    cs:__imp_free
0x180008339  nop     dword ptr [rax+rax+00h]
0x18000833e  mov     rcx, [rbp+var_30]; Block
0x180008342  call    cs:__imp_free
0x180008349  nop     dword ptr [rax+rax+00h]
0x18000834e  mov     rcx, rsi; Block
0x180008351  call    cs:__imp_free
0x180008358  nop     dword ptr [rax+rax+00h]
0x18000835d  lea     r12, WPP_GLOBAL_Control
0x180008364  mov     rcx, [rbp+var_28]; Block
0x180008368  call    cs:__imp_free
0x18000836f  nop     dword ptr [rax+rax+00h]
0x180008374  lea     rcx, [rbp+arg_8]
0x180008378  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000837d  jmp     loc_1800080FD
0x180008382  lea     rdx, asc_180063AD8; "+"
0x180008389  lea     rcx, [rbp+arg_10]; this
0x18000838d  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180008392  mov     r15d, eax
0x180008395  test    eax, eax
0x180008397  js      short loc_1800083A9
0x180008399  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18000839d  lea     rcx, [rbp+arg_10]; this
0x1800083a1  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800083a6  mov     r15d, eax
0x1800083a9  mov     rsi, [rbp+arg_10]
0x1800083ad  jmp     loc_1800081E0
0x1800083b2  lea     rdx, Format; unsigned __int16 *
0x1800083b9  mov     [rbp+lpString1], r13
0x1800083bd  lea     rcx, [rbp+lpString1]; this
0x1800083c1  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x1800083c6  mov     r15d, eax
0x1800083c9  test    eax, eax
0x1800083cb  jns     loc_180008621
0x1800083d1  mov     rcx, [rbp+lpString1]; Block
0x1800083d5  call    cs:__imp_free
0x1800083dc  nop     dword ptr [rax+rax+00h]
0x1800083e1  jmp     loc_180008310
0x1800083e6  mov     rdx, rsi; unsigned __int16 *
0x1800083e9  lea     rcx, [rbp+lpString1]; this
0x1800083ed  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800083f2  mov     r15d, eax
0x1800083f5  test    eax, eax
0x1800083f7  js      loc_1800084D2
0x1800083fd  mov     ecx, 16h; Size
0x180008402  mov     [rbp+arg_10], r13
0x180008406  call    cs:__imp_malloc
0x18000840d  nop     dword ptr [rax+rax+00h]
0x180008412  mov     rbx, rax
0x180008415  test    rax, rax
0x180008418  jz      loc_1800085DA
0x18000841e  mov     ecx, 0Bh; pszDest
0x180008423  mov     edx, ecx; cchDest
0x180008425  call    StringValidateDestW
0x18000842a  mov     r15d, eax
0x18000842d  test    eax, eax
0x18000842f  js      loc_1800085E5
0x180008435  lea     r9, aUpnphost; "/upnphost/"
0x18000843c  mov     rcx, rbx; pszDest
0x18000843f  call    StringCopyWorkerW
0x180008444  mov     r15d, eax
0x180008447  test    eax, eax
0x180008449  js      loc_1800085E9
0x18000844f  xor     ecx, ecx; Block
0x180008451  call    cs:__imp_free
0x180008458  nop     dword ptr [rax+rax+00h]
0x18000845d  mov     [rbp+arg_10], rbx
0x180008461  test    r15d, r15d
0x180008464  jnz     short loc_180008493
0x180008466  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18000846a  lea     rcx, [rbp+arg_10]; this
0x18000846e  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180008473  mov     r15d, eax
0x180008476  test    eax, eax
0x180008478  js      short loc_1800084C2
0x18000847a  lea     r8, [rbp+arg_10]
0x18000847e  lea     rdx, [rbp+arg_8]
0x180008482  lea     rcx, aDddControlurl; "ddd:controlURL"
0x180008489  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x18000848e  mov     r15d, eax
0x180008491  jmp     short loc_1800084C2
0x180008493  mov     rcx, cs:WPP_GLOBAL_Control
0x18000849a  cmp     rcx, r12
0x18000849d  jz      short loc_1800084BD
0x18000849f  test    byte ptr [rcx+1Ch], 1
0x1800084a3  jz      short loc_1800084BD
0x1800084a5  mov     rcx, [rcx+10h]
0x1800084a9  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800084b0  mov     edx, 0Ah
0x1800084b5  mov     r9d, r15d
0x1800084b8  call    WPP_SF_d
0x1800084bd  test    r15d, r15d
0x1800084c0  jns     short loc_180008466
0x1800084c2  mov     rcx, [rbp+arg_10]; Block
0x1800084c6  call    cs:__imp_free
0x1800084cd  nop     dword ptr [rax+rax+00h]
0x1800084d2  mov     rdi, [rbp+lpString1]
0x1800084d6  jmp     loc_1800081F4
0x1800084db  lea     rdx, aUdhisapiDllEve; "udhisapi.dll?event="
0x1800084e2  lea     rcx, [rbp+Block]; this
0x1800084e6  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x1800084eb  mov     r15d, eax
0x1800084ee  test    eax, eax
0x1800084f0  js      loc_18000806F
0x1800084f6  lea     r8, [rbp+arg_8]
  ... truncated ...
```
