# HrGenerateControlAndEventURLs(SmartComPtr<IXMLDOMNode> &)

- ea: `0x180013f08`
- end: `0x1800144dd`
- name: `?HrGenerateControlAndEventURLs@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z`
- size: `1493`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f298`

## callees

- `0x1800117bc`
- `0x1800117d0`
- `0x180013f08`
- `0x180015ab0`
- `0x180015d90`
- `0x180016f50`
- `0x18001ab90`
- `0x18002072c`
- `0x180025330`
- `0x180038324`
- `0x180038ce4`
- `0x180043124`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013f76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013f80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013f8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001407c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001414e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014260`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800142d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001433f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800143c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800143ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014453`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014471`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013f76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013f80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013f8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001407c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001414e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014260`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800142d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001433f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800143c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800143ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014453`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014471`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001403d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014109`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001428b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001403d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014109`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001428b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800140f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800140f6`

## string_xrefs

- `0x180014000`: `ddd:serviceId`
- `0x1800140e8`: `REMOVE`
- `0x180013fb2`: `ddd:serviceList/ddd:service`
- `0x180013f22`: `udhisapi.dll?control=`
- `0x18001434e`: `udhisapi.dll?event=`

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
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v34);
        goto LABEL_6;
      }
      v30 = 0;
      v3 = HrSelectNodeText((OLECHAR *)L"ddd:serviceId");
      if ( v3 >= 0 )
        break;
LABEL_35:
      free(v30);
      ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v34);
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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v31);
  free(v2);
  free(Block);
  free(v33[0]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013f08  mov     [rsp-38h+arg_0], rbx
0x180013f0d  push    rbp
0x180013f0e  push    rsi
0x180013f0f  push    rdi
0x180013f10  push    r12
0x180013f12  push    r13
0x180013f14  push    r14
0x180013f16  push    r15
0x180013f18  mov     rbp, rsp
0x180013f1b  sub     rsp, 60h
0x180013f1f  xor     r13d, r13d
0x180013f22  lea     rdx, aUdhisapiDllCon; "udhisapi.dll?control="
0x180013f29  mov     rbx, rcx
0x180013f2c  mov     [rbp+var_10], r13
0x180013f30  lea     rcx, [rbp+var_10]; this
0x180013f34  mov     [rbp+Block], r13
0x180013f38  mov     r14d, r13d
0x180013f3b  mov     [rbp+arg_8], r13
0x180013f3f  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180013f44  mov     r15d, eax
0x180013f47  test    eax, eax
0x180013f49  jns     loc_18001434E
0x180013f4f  lea     rcx, [rbp+var_20]; void *
0x180013f53  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180013f58  lea     r12, WPP_GLOBAL_Control
0x180013f5f  test    r15d, r15d
0x180013f62  jns     short loc_180013FAB
0x180013f64  jnz     loc_1800144A6
0x180013f6a  lea     rcx, [rbp+var_20]
0x180013f6e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180013f73  mov     rcx, r14; Block
0x180013f76  call    cs:__imp_free
0x180013f7c  mov     rcx, [rbp+Block]; Block
0x180013f80  call    cs:__imp_free
0x180013f86  mov     rcx, [rbp+var_10]; Block
0x180013f8a  call    cs:__imp_free
0x180013f90  mov     rbx, [rsp+60h+arg_0]
0x180013f98  mov     eax, r15d
0x180013f9b  add     rsp, 60h
0x180013f9f  pop     r15
0x180013fa1  pop     r14
0x180013fa3  pop     r13
0x180013fa5  pop     r12
0x180013fa7  pop     rdi
0x180013fa8  pop     rsi
0x180013fa9  pop     rbp
0x180013faa  retn
0x180013fab  lea     r8, [rbp+var_20]
0x180013faf  mov     rdx, rbx
0x180013fb2  lea     rcx, aDddServicelist_0; "ddd:serviceList/ddd:service"
0x180013fb9  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x180013fbe  mov     r15d, eax
0x180013fc1  test    eax, eax
0x180013fc3  jns     short loc_180013FCA
0x180013fc5  test    r15d, r15d
0x180013fc8  jmp     short loc_180013F64
0x180013fca  test    r15d, r15d
0x180013fcd  js      short loc_180013F64
0x180013fcf  lea     rcx, [rbp+arg_8]; void *
0x180013fd3  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180013fd8  mov     rcx, [rbp+var_20]
0x180013fdc  lea     rdx, [rbp+arg_8]
0x180013fe0  mov     rax, [rcx]
0x180013fe3  mov     rax, [rax+48h]
0x180013fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fec  test    eax, eax
0x180013fee  jnz     loc_180014498
0x180013ff4  lea     r8, [rbp+var_28]
0x180013ff8  mov     [rbp+var_28], r13
0x180013ffc  lea     rdx, [rbp+arg_8]
0x180014000  lea     rcx, aDddServiceid; "ddd:serviceId"
0x180014007  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18001400c  mov     r15d, eax
0x18001400f  test    eax, eax
0x180014011  js      loc_1800141F5
0x180014017  mov     [rbp+arg_10], r13
0x18001401b  mov     rsi, r13
0x18001401e  test    r14, r14
0x180014021  jz      loc_1800143C6
0x180014027  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001402b  inc     rax
0x18001402e  cmp     [r14+rax*2], r13w
0x180014033  jnz     short loc_18001402B
0x180014035  lea     r12, [rax+1]
0x180014039  lea     rcx, [r12+r12]; Size
0x18001403d  call    cs:__imp_malloc
0x180014043  mov     rdi, rax
0x180014046  test    rax, rax
0x180014049  jz      loc_1800143D3
0x18001404f  mov     rdx, r12; cchDest
0x180014052  call    StringValidateDestW
0x180014057  mov     r15d, eax
0x18001405a  test    eax, eax
0x18001405c  js      loc_1800143DB
0x180014062  mov     r9, r14; pszSrc
0x180014065  mov     rcx, rdi; pszDest
0x180014068  call    StringCopyWorkerW
0x18001406d  mov     ebx, eax
0x18001406f  mov     r15d, ebx
0x180014072  test    ebx, ebx
0x180014074  js      loc_1800143EA
0x18001407a  xor     ecx, ecx; Block
0x18001407c  call    cs:__imp_free
0x180014082  mov     rsi, rdi
0x180014085  mov     [rbp+arg_10], rdi
0x180014089  test    ebx, ebx
0x18001408b  jnz     loc_180014388
0x180014091  lea     r12, WPP_GLOBAL_Control
0x180014098  test    r15d, r15d
0x18001409b  jns     loc_18001420D
0x1800140a1  mov     [rbp+var_30], r13
0x1800140a5  mov     rdi, r13
0x1800140a8  mov     [rbp+lpString1], r13
0x1800140ac  test    r15d, r15d
0x1800140af  jns     loc_1800143F5
0x1800140b5  mov     rbx, r13
0x1800140b8  mov     [rbp+lpString1], rbx
0x1800140bc  test    r15d, r15d
0x1800140bf  js      loc_1800141C9
0x1800140c5  lea     r8, [rbp+lpString1]
0x1800140c9  lea     rdx, [rbp+arg_8]
0x1800140cd  lea     rcx, aDddEventsuburl_0; "ddd:eventSubURL"
0x1800140d4  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x1800140d9  mov     rbx, [rbp+lpString1]
0x1800140dd  mov     r15d, eax
0x1800140e0  test    eax, eax
0x1800140e2  js      loc_1800141C9
0x1800140e8  lea     rdx, aRemove; "REMOVE"
0x1800140ef  mov     [rbp+arg_10], r13
0x1800140f3  mov     rcx, rbx; lpString1
0x1800140f6  call    cs:__imp_lstrcmpiW
0x1800140fc  test    eax, eax
0x1800140fe  jz      loc_18001423D
0x180014104  mov     ecx, 16h; Size
0x180014109  call    cs:__imp_malloc
0x18001410f  mov     r12, rax
0x180014112  test    rax, rax
0x180014115  jz      loc_18001445E
0x18001411b  mov     ecx, 0Bh; pszDest
0x180014120  mov     edx, ecx; cchDest
0x180014122  call    StringValidateDestW
0x180014127  mov     r15d, eax
0x18001412a  test    eax, eax
0x18001412c  js      loc_180014469
0x180014132  lea     r9, aUpnphost; "/upnphost/"
0x180014139  mov     rcx, r12; pszDest
0x18001413c  call    StringCopyWorkerW
0x180014141  mov     r15d, eax
0x180014144  test    eax, eax
0x180014146  js      loc_18001446E
0x18001414c  xor     ecx, ecx; Block
0x18001414e  call    cs:__imp_free
0x180014154  mov     [rbp+arg_10], r12
0x180014158  test    r15d, r15d
0x18001415b  jnz     short loc_180014189
0x18001415d  mov     rdx, rdi; unsigned __int16 *
0x180014160  lea     rcx, [rbp+arg_10]; this
0x180014164  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180014169  mov     r15d, eax
0x18001416c  test    eax, eax
0x18001416e  js      short loc_1800141BF
0x180014170  lea     r8, [rbp+arg_10]
0x180014174  lea     rdx, [rbp+arg_8]
0x180014178  lea     rcx, aDddEventsuburl_0; "ddd:eventSubURL"
0x18001417f  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x180014184  mov     r15d, eax
0x180014187  jmp     short loc_1800141BF
0x180014189  mov     rcx, cs:WPP_GLOBAL_Control
0x180014190  lea     rax, WPP_GLOBAL_Control
0x180014197  cmp     rcx, rax
0x18001419a  jz      short loc_1800141BA
0x18001419c  test    byte ptr [rcx+1Ch], 1
0x1800141a0  jz      short loc_1800141BA
0x1800141a2  mov     rcx, [rcx+10h]
0x1800141a6  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800141ad  mov     edx, 0Ah
0x1800141b2  mov     r9d, r15d
0x1800141b5  call    WPP_SF_d
0x1800141ba  test    r15d, r15d
0x1800141bd  jns     short loc_18001415D
0x1800141bf  mov     rcx, [rbp+arg_10]; Block
0x1800141c3  call    cs:__imp_free
0x1800141c9  mov     rcx, rbx; Block
0x1800141cc  call    cs:__imp_free
0x1800141d2  mov     rcx, rdi; Block
0x1800141d5  call    cs:__imp_free
0x1800141db  mov     rcx, [rbp+var_30]; Block
0x1800141df  call    cs:__imp_free
0x1800141e5  mov     rcx, rsi; Block
0x1800141e8  call    cs:__imp_free
0x1800141ee  lea     r12, WPP_GLOBAL_Control
0x1800141f5  mov     rcx, [rbp+var_28]; Block
0x1800141f9  call    cs:__imp_free
0x1800141ff  lea     rcx, [rbp+arg_8]
0x180014203  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180014208  jmp     loc_180013FCA
0x18001420d  lea     rdx, asc_180060318; "+"
0x180014214  lea     rcx, [rbp+arg_10]; this
0x180014218  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18001421d  mov     r15d, eax
0x180014220  test    eax, eax
0x180014222  js      short loc_180014234
0x180014224  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180014228  lea     rcx, [rbp+arg_10]; this
0x18001422c  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180014231  mov     r15d, eax
0x180014234  mov     rsi, [rbp+arg_10]
0x180014238  jmp     loc_1800140A1
0x18001423d  lea     rdx, Format; unsigned __int16 *
0x180014244  mov     [rbp+lpString1], r13
0x180014248  lea     rcx, [rbp+lpString1]; this
0x18001424c  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180014251  mov     r15d, eax
0x180014254  test    eax, eax
0x180014256  jns     loc_18001447C
0x18001425c  mov     rcx, [rbp+lpString1]; Block
0x180014260  call    cs:__imp_free
0x180014266  jmp     loc_1800141BF
0x18001426b  mov     rdx, rsi; unsigned __int16 *
0x18001426e  lea     rcx, [rbp+lpString1]; this
0x180014272  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180014277  mov     r15d, eax
0x18001427a  test    eax, eax
0x18001427c  js      loc_180014345
0x180014282  mov     ecx, 16h; Size
0x180014287  mov     [rbp+arg_10], r13
0x18001428b  call    cs:__imp_malloc
0x180014291  mov     rbx, rax
0x180014294  test    rax, rax
0x180014297  jz      loc_180014441
0x18001429d  mov     ecx, 0Bh; pszDest
0x1800142a2  mov     edx, ecx; cchDest
0x1800142a4  call    StringValidateDestW
0x1800142a9  mov     r15d, eax
0x1800142ac  test    eax, eax
0x1800142ae  js      loc_18001444C
0x1800142b4  lea     r9, aUpnphost; "/upnphost/"
0x1800142bb  mov     rcx, rbx; pszDest
0x1800142be  call    StringCopyWorkerW
0x1800142c3  mov     r15d, eax
0x1800142c6  test    eax, eax
0x1800142c8  js      loc_180014450
0x1800142ce  xor     ecx, ecx; Block
0x1800142d0  call    cs:__imp_free
0x1800142d6  mov     [rbp+arg_10], rbx
0x1800142da  test    r15d, r15d
0x1800142dd  jnz     short loc_18001430C
0x1800142df  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800142e3  lea     rcx, [rbp+arg_10]; this
0x1800142e7  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800142ec  mov     r15d, eax
0x1800142ef  test    eax, eax
0x1800142f1  js      short loc_18001433B
0x1800142f3  lea     r8, [rbp+arg_10]
0x1800142f7  lea     rdx, [rbp+arg_8]
0x1800142fb  lea     rcx, aDddControlurl; "ddd:controlURL"
0x180014302  call    ?HrSelectAndSetNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@@Z; HrSelectAndSetNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString const &)
0x180014307  mov     r15d, eax
0x18001430a  jmp     short loc_18001433B
0x18001430c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014313  cmp     rcx, r12
0x180014316  jz      short loc_180014336
0x180014318  test    byte ptr [rcx+1Ch], 1
0x18001431c  jz      short loc_180014336
0x18001431e  mov     rcx, [rcx+10h]
0x180014322  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180014329  mov     edx, 0Ah
0x18001432e  mov     r9d, r15d
0x180014331  call    WPP_SF_d
0x180014336  test    r15d, r15d
0x180014339  jns     short loc_1800142DF
0x18001433b  mov     rcx, [rbp+arg_10]; Block
0x18001433f  call    cs:__imp_free
0x180014345  mov     rdi, [rbp+lpString1]
0x180014349  jmp     loc_1800140B5
0x18001434e  lea     rdx, aUdhisapiDllEve; "udhisapi.dll?event="
0x180014355  lea     rcx, [rbp+Block]; this
0x180014359  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18001435e  mov     r15d, eax
0x180014361  test    eax, eax
0x180014363  js      loc_180013F4F
0x180014369  lea     r8, [rbp+arg_8]
0x18001436d  mov     rdx, rbx
0x180014370  lea     rcx, aDddUdn_0; "ddd:UDN"
0x180014377  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18001437c  mov     r14, [rbp+arg_8]
0x180014380  mov     r15d, eax
0x180014383  jmp     loc_180013F4F
0x180014388  mov     rcx, cs:WPP_GLOBAL_Control
0x18001438f  lea     r12, WPP_GLOBAL_Control
0x180014396  cmp     rcx, r12
0x180014399  jz      loc_180014098
0x18001439f  test    byte ptr [rcx+1Ch], 1
0x1800143a3  jz      loc_180014098
0x1800143a9  mov     rcx, [rcx+10h]
0x1800143ad  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800143b4  mov     edx, 0Ah
0x1800143b9  mov     r9d, r15d
0x1800143bc  call    WPP_SF_d
0x1800143c1  jmp     loc_180014098
  ... truncated ...
```
