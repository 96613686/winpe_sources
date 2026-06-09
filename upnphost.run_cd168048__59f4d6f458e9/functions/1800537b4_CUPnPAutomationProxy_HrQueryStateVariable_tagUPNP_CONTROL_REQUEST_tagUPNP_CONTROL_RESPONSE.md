# CUPnPAutomationProxy::HrQueryStateVariable(tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *)

- ea: `0x1800537b4`
- end: `0x180053cbf`
- name: `?HrQueryStateVariable@CUPnPAutomationProxy@@AEAAJPEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@@Z`
- size: `1291`
- prototype: `__int64 __fastcall(unsigned __int16 **this, struct tagUPNP_CONTROL_REQUEST *, struct tagUPNP_CONTROL_RESPONSE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002f4dc`

## callees

- `0x1800200f4`
- `0x180020170`
- `0x180034ec4`
- `0x18003817c`
- `0x18003b904`
- `0x18003bf14`
- `0x18003c018`
- `0x18003d4b0`
- `0x1800537b4`
- `0x180053e18`
- `0x180053e68`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053959`
- `OLEAUT32!__imp_SysAllocString` at `0x18005392e`
- `OLEAUT32!__imp_SysAllocString` at `0x180053aa1`
- `OLEAUT32!__imp_SysAllocString` at `0x18005392e`
- `OLEAUT32!__imp_SysAllocString` at `0x180053aa1`
- `OLEAUT32!__imp_VariantInit` at `0x180053852`
- `OLEAUT32!__imp_VariantInit` at `0x180053978`
- `OLEAUT32!__imp_VariantInit` at `0x180053852`
- `OLEAUT32!__imp_VariantInit` at `0x180053978`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18005398b`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18005398b`

## string_xrefs

- `0x1800539f0`: `CUPnPAutomationProxy::HrQueryStateVariable(): Failed to copy result to output`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::HrQueryStateVariable(
        unsigned __int16 **this,
        struct tagUPNP_CONTROL_REQUEST *a2,
        struct tagUPNP_CONTROL_RESPONSE *a3)
{
  bool v3; // zf
  __int64 v6; // rax
  const unsigned __int16 *v7; // r15
  const unsigned __int16 *v8; // rdx
  struct tagUPNP_STATE_VARIABLE *v9; // rbx
  const unsigned __int16 *v10; // r8
  int v11; // eax
  int v12; // ebx
  unsigned __int16 *v13; // rcx
  VARIANTARG *v14; // rax
  VARIANT *v15; // rbx
  HRESULT v16; // eax
  STRSAFE_PCNZWCH v17; // rcx
  int v18; // edx
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r8
  int v21; // eax
  int v22; // eax
  unsigned __int16 *v23; // r9
  unsigned __int16 *v24; // rcx
  CUPnPAutomationProxy *v25; // rcx
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  STRSAFE_PCNZWCH v28; // rcx
  int v29; // edx
  const char *v30; // r9
  __int128 v32; // [rsp+50h] [rbp-79h] BYREF
  __int128 v33; // [rsp+60h] [rbp-69h] BYREF
  __int128 v34; // [rsp+70h] [rbp-59h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-49h] BYREF
  __int128 v36; // [rsp+98h] [rbp-31h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-21h]
  char v38[8]; // [rsp+B0h] [rbp-19h] BYREF
  unsigned __int16 *v39; // [rsp+B8h] [rbp-11h]
  unsigned __int16 *v40; // [rsp+C0h] [rbp-9h]
  __int64 (__fastcall *v41)(char *); // [rsp+E0h] [rbp+17h]

  v3 = *((_DWORD *)a2 + 2) == 1;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( !v3 || (v6 = *((_QWORD *)a2 + 2), *(_WORD *)v6 != 8) )
  {
    v28 = WPP_GLOBAL_Control;
    v12 = -2147024809;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v29 = 146;
      v30 = "Invalid arguments passed to HrQueryStateVariable!";
      goto LABEL_72;
    }
    return (unsigned int)v12;
  }
  v7 = *(const unsigned __int16 **)(v6 + 8);
  v9 = CUPnPAutomationProxy::LookupVariableByName((CUPnPAutomationProxy *)this, v7);
  if ( !v9 )
  {
    v12 = HrBuildFaultResponse((union tagUPNP_CONTROL_RESPONSE_DATA *)&v33, v8, v10, L"404", L"Invalid Var");
    goto LABEL_62;
  }
  v37 = 0;
  v36 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(v38, 0, 0x40u);
  VariantInit(&pvarg);
  v11 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, GUID *, __int64, __int16, __int128 *, VARIANTARG *, char *, _QWORD))(*(_QWORD *)this[11] + 48LL))(
          this[11],
          *((unsigned int *)v9 + 5),
          &GUID_NULL,
          2048,
          2,
          &v36,
          &pvarg,
          v38,
          0);
  v12 = v11;
  if ( v11 == -2147023174 || (unsigned int)(v11 + 2147023170) <= 1 || v11 == -2147417848 )
  {
    v13 = this[11];
    if ( !v13
      || (**(unsigned int (__fastcall ***)(unsigned __int16 *, __int64 *, void **))v13)(v13, bogusIID, &pBogusInterface) != -2147467262 )
    {
      HrUnregisterDeviceByUDN(this[17]);
    }
  }
  if ( v12 < 0 )
  {
    if ( v12 != -2147352567 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::HrQueryStateVariable(): PROPGET failed",
          v12);
      goto LABEL_60;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, v7);
    *(_QWORD *)&v32 = SysAllocString(L"QueryStateVariable");
    if ( !(_QWORD)v32 )
    {
      v12 = -2147024882;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v18 = 156;
      goto LABEL_29;
    }
    DWORD2(v32) = 0;
    if ( v41 )
    {
      v21 = ValidateCallerAccess();
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            155,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrQueryStateVariable(): Deferred exception info failed,  Caller has incorrect privelege",
            v21);
        goto LABEL_49;
      }
      v22 = v41(v38);
      v12 = v22;
      if ( v22 < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            154,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrQueryStateVariable(): Failed to fill in deferred exception info",
            v22);
          goto LABEL_60;
        }
      }
      else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
        goto LABEL_49;
      }
      if ( v22 < 0 )
        goto LABEL_60;
    }
LABEL_49:
    v23 = L"501";
    v24 = L"Action Failed";
    if ( v39 )
      v23 = v39;
    if ( v40 )
      v24 = v40;
    v12 = HrBuildFaultResponse((union tagUPNP_CONTROL_RESPONSE_DATA *)&v33, v19, v20, v23, v24);
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, v7);
  *(_QWORD *)&v32 = SysAllocString(L"QueryStateVariable");
  if ( (_QWORD)v32 )
  {
    DWORD2(v32) = 1;
    LODWORD(v33) = 1;
    v14 = (VARIANTARG *)CoTaskMemAlloc(0x18u);
    *((_QWORD *)&v33 + 1) = v14;
    v15 = v14;
    if ( v14 )
    {
      VariantInit(v14);
      v16 = VariantCopyInd(v15, &pvarg);
      v12 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            149,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrQueryStateVariable(): Failed to copy result to output",
            v16);
      }
      else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
      }
    }
    else
    {
      v12 = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          150,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::HrQueryStateVariable(): Failed to allocate memory for output arg",
          14);
    }
    goto LABEL_60;
  }
  v12 = -2147024882;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v18 = 151;
LABEL_29:
    WPP_SF_sd(
      *((_QWORD *)v17 + 2),
      v18,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"CUPnPAutomationProxy::HrQueryStateVariable(): Failed to allocate memory for action name",
      14);
  }
LABEL_60:
  SafeClearVariant(&pvarg);
LABEL_62:
  if ( v12 < 0 )
  {
    CUPnPAutomationProxy::FreeControlResponse(v25, (struct tagUPNP_CONTROL_RESPONSE *)&v32);
  }
  else
  {
    v26 = v33;
    *(_OWORD *)a3 = v32;
    v27 = v34;
    *((_OWORD *)a3 + 1) = v26;
    *((_OWORD *)a3 + 2) = v27;
    if ( !v12 )
      return (unsigned int)v12;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v29 = 158;
    v30 = "CUPnPAutomationProxy::HrQueryStateVariable(): Exiting";
LABEL_72:
    WPP_SF_sd(
      *((_QWORD *)v28 + 2),
      v29,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (_DWORD)v30,
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800537b4  push    rbp
0x1800537b6  push    rbx
0x1800537b7  push    rsi
0x1800537b8  push    rdi
0x1800537b9  push    r12
0x1800537bb  push    r14
0x1800537bd  push    r15
0x1800537bf  lea     rbp, [rsp-27h]
0x1800537c4  sub     rsp, 0F0h
0x1800537cb  cmp     dword ptr [rdx+8], 1
0x1800537cf  xorps   xmm0, xmm0
0x1800537d2  movups  [rbp+57h+var_D0], xmm0
0x1800537d6  mov     r12, r8
0x1800537d9  mov     r14, rcx
0x1800537dc  movups  [rbp+57h+var_C0], xmm0
0x1800537e0  movups  [rbp+57h+var_B0], xmm0
0x1800537e4  jnz     loc_180053C6C
0x1800537ea  mov     rax, [rdx+10h]
0x1800537ee  mov     ecx, 8
0x1800537f3  cmp     cx, [rax]
0x1800537f6  jnz     loc_180053C6C
0x1800537fc  mov     r15, [rax+8]
0x180053800  mov     rcx, r14; this
0x180053803  mov     rdx, r15; unsigned __int16 *
0x180053806  call    ?LookupVariableByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_STATE_VARIABLE@@PEBG@Z; CUPnPAutomationProxy::LookupVariableByName(ushort const *)
0x18005380b  lea     rdi, WPP_GLOBAL_Control
0x180053812  mov     rbx, rax
0x180053815  lea     rsi, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18005381c  test    rax, rax
0x18005381f  jz      loc_180053BFD
0x180053825  xor     eax, eax
0x180053827  mov     [rbp+57h+var_78], 0
0x18005382f  xorps   xmm0, xmm0
0x180053832  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180053836  xor     edx, edx; Val
0x180053838  lea     rcx, [rbp+57h+var_70]; void *
0x18005383c  movdqu  [rbp+57h+var_88], xmm0
0x180053841  lea     r8d, [rax+40h]; Size
0x180053845  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180053849  call    memset_0
0x18005384e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180053852  call    cs:__imp_VariantInit
0x180053859  nop     dword ptr [rax+rax+00h]
0x18005385e  mov     rcx, [r14+58h]
0x180053862  lea     rdx, [rbp+57h+var_70]
0x180053866  mov     [rsp+120h+var_E0], 0
0x18005386f  lea     r8, GUID_NULL
0x180053876  mov     [rsp+120h+var_E8], rdx
0x18005387b  mov     r9d, 800h
0x180053881  lea     rdx, [rbp+57h+pvarg]
0x180053885  mov     rax, [rcx]
0x180053888  mov     [rsp+120h+var_F0], rdx
0x18005388d  lea     rdx, [rbp+57h+var_88]
0x180053891  mov     [rsp+120h+var_F8], rdx
0x180053896  mov     edx, [rbx+14h]
0x180053899  mov     rax, [rax+30h]
0x18005389d  mov     word ptr [rsp+120h+var_100], 2
0x1800538a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538a9  mov     ebx, eax
0x1800538ab  cmp     eax, 800706BAh
0x1800538b0  jz      short loc_1800538C4
0x1800538b2  lea     ecx, [rax+7FF8F942h]
0x1800538b8  cmp     ecx, 1
0x1800538bb  jbe     short loc_1800538C4
0x1800538bd  cmp     eax, 80010108h
0x1800538c2  jnz     short loc_1800538F9
0x1800538c4  mov     rcx, [r14+58h]
0x1800538c8  test    rcx, rcx
0x1800538cb  jz      short loc_1800538ED
0x1800538cd  mov     rax, [rcx]
0x1800538d0  lea     r8, ?pBogusInterface@@3PEAXEA; void * pBogusInterface
0x1800538d7  lea     rdx, bogusIID
0x1800538de  mov     rax, [rax]
0x1800538e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538e6  cmp     eax, 80004002h
0x1800538eb  jz      short loc_1800538F9
0x1800538ed  mov     rcx, [r14+88h]; unsigned __int16 *
0x1800538f4  call    ?HrUnregisterDeviceByUDN@@YAJPEAG@Z; HrUnregisterDeviceByUDN(ushort *)
0x1800538f9  test    ebx, ebx
0x1800538fb  js      loc_180053A68
0x180053901  mov     rcx, cs:WPP_GLOBAL_Control
0x180053908  cmp     rcx, rdi
0x18005390b  jz      short loc_180053927
0x18005390d  test    byte ptr [rcx+1Ch], 40h
0x180053911  jz      short loc_180053927
0x180053913  mov     rcx, [rcx+10h]
0x180053917  mov     edx, 93h
0x18005391c  mov     r9, r15
0x18005391f  mov     r8, rsi
0x180053922  call    WPP_SF_S
0x180053927  lea     rcx, aQuerystatevari_0; "QueryStateVariable"
0x18005392e  call    cs:__imp_SysAllocString
0x180053935  nop     dword ptr [rax+rax+00h]
0x18005393a  mov     qword ptr [rbp+57h+var_D0], rax
0x18005393e  test    rax, rax
0x180053941  jz      loc_180053A32
0x180053947  mov     r14d, 1
0x18005394d  mov     dword ptr [rbp+57h+var_D0+8], r14d
0x180053951  mov     dword ptr [rbp+57h+var_C0], r14d
0x180053955  lea     ecx, [r14+17h]; cb
0x180053959  call    cs:__imp_CoTaskMemAlloc
0x180053960  nop     dword ptr [rax+rax+00h]
0x180053965  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180053969  mov     rbx, rax
0x18005396c  test    rax, rax
0x18005396f  jz      loc_1800539FC
0x180053975  mov     rcx, rax; pvarg
0x180053978  call    cs:__imp_VariantInit
0x18005397f  nop     dword ptr [rax+rax+00h]
0x180053984  lea     rdx, [rbp+57h+pvarg]; pvargSrc
0x180053988  mov     rcx, rbx; pvarDest
0x18005398b  call    cs:__imp_VariantCopyInd
0x180053992  nop     dword ptr [rax+rax+00h]
0x180053997  mov     ebx, eax
0x180053999  test    eax, eax
0x18005399b  js      short loc_1800539CD
0x18005399d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539a4  cmp     rcx, rdi
0x1800539a7  jz      loc_180053BF2
0x1800539ad  test    byte ptr [rcx+1Ch], 40h
0x1800539b1  jz      loc_180053BF2
0x1800539b7  mov     rcx, [rcx+10h]
0x1800539bb  mov     edx, 94h
0x1800539c0  mov     r8, rsi
0x1800539c3  call    WPP_SF_
0x1800539c8  jmp     loc_180053BF2
0x1800539cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539d4  cmp     rcx, rdi
0x1800539d7  jz      loc_180053BF2
0x1800539dd  test    [rcx+1Ch], r14b
0x1800539e1  jz      loc_180053BF2
0x1800539e7  mov     edx, 95h
0x1800539ec  mov     dword ptr [rsp+120h+var_100], eax
0x1800539f0  lea     r9, aCupnpautomatio_68; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x1800539f7  jmp     loc_180053BE6
0x1800539fc  mov     eax, 8007000Eh
0x180053a01  mov     ebx, eax
0x180053a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a0a  cmp     rcx, rdi
0x180053a0d  jz      loc_180053BF2
0x180053a13  test    [rcx+1Ch], r14b
0x180053a17  jz      loc_180053BF2
0x180053a1d  mov     edx, 96h
0x180053a22  mov     dword ptr [rsp+120h+var_100], eax
0x180053a26  lea     r9, aCupnpautomatio_78; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180053a2d  jmp     loc_180053BE6
0x180053a32  mov     eax, 8007000Eh
0x180053a37  mov     ebx, eax
0x180053a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a40  cmp     rcx, rdi
0x180053a43  jz      loc_180053BF2
0x180053a49  test    byte ptr [rcx+1Ch], 1
0x180053a4d  jz      loc_180053BF2
0x180053a53  mov     edx, 97h
0x180053a58  mov     dword ptr [rsp+120h+var_100], eax
0x180053a5c  lea     r9, aCupnpautomatio_77; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180053a63  jmp     loc_180053BE6
0x180053a68  cmp     ebx, 80020009h
0x180053a6e  jnz     loc_180053BC4
0x180053a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a7b  cmp     rcx, rdi
0x180053a7e  jz      short loc_180053A9A
0x180053a80  test    byte ptr [rcx+1Ch], 40h
0x180053a84  jz      short loc_180053A9A
0x180053a86  mov     rcx, [rcx+10h]
0x180053a8a  mov     edx, 98h
0x180053a8f  mov     r9, r15
0x180053a92  mov     r8, rsi
0x180053a95  call    WPP_SF_S
0x180053a9a  lea     rcx, aQuerystatevari_0; "QueryStateVariable"
0x180053aa1  call    cs:__imp_SysAllocString
0x180053aa8  nop     dword ptr [rax+rax+00h]
0x180053aad  mov     qword ptr [rbp+57h+var_D0], rax
0x180053ab1  test    rax, rax
0x180053ab4  jz      loc_180053BA1
0x180053aba  cmp     [rbp+57h+var_40], 0
0x180053abf  mov     dword ptr [rbp+57h+var_D0+8], 0
0x180053ac6  jz      loc_180053B6B
0x180053acc  call    ?ValidateCallerAccess@@YAJXZ; ValidateCallerAccess(void)
0x180053ad1  test    eax, eax
0x180053ad3  js      short loc_180053B3D
0x180053ad5  mov     rax, [rbp+57h+var_40]
0x180053ad9  lea     rcx, [rbp+57h+var_70]
0x180053add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ae2  mov     ebx, eax
0x180053ae4  test    eax, eax
0x180053ae6  js      short loc_180053B0D
0x180053ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180053aef  cmp     rcx, rdi
0x180053af2  jz      short loc_180053B34
0x180053af4  test    byte ptr [rcx+1Ch], 40h
0x180053af8  jz      short loc_180053B34
0x180053afa  mov     rcx, [rcx+10h]
0x180053afe  mov     edx, 99h
0x180053b03  mov     r8, rsi
0x180053b06  call    WPP_SF_
0x180053b0b  jmp     short loc_180053B6B
0x180053b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b14  cmp     rcx, rdi
0x180053b17  jz      short loc_180053B34
0x180053b19  test    byte ptr [rcx+1Ch], 1
0x180053b1d  jz      short loc_180053B34
0x180053b1f  mov     edx, 9Ah
0x180053b24  mov     dword ptr [rsp+120h+var_100], eax
0x180053b28  lea     r9, aCupnpautomatio_55; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180053b2f  jmp     loc_180053BE6
0x180053b34  test    eax, eax
0x180053b36  jns     short loc_180053B6B
0x180053b38  jmp     loc_180053BF2
0x180053b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b44  cmp     rcx, rdi
0x180053b47  jz      short loc_180053B6B
0x180053b49  test    byte ptr [rcx+1Ch], 1
0x180053b4d  jz      short loc_180053B6B
0x180053b4f  mov     rcx, [rcx+10h]
0x180053b53  lea     r9, aCupnpautomatio_41; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180053b5a  mov     edx, 9Bh
0x180053b5f  mov     dword ptr [rsp+120h+var_100], eax
0x180053b63  mov     r8, rsi
0x180053b66  call    WPP_SF_sd
0x180053b6b  mov     rax, [rbp+57h+var_68]
0x180053b6f  lea     r9, a501; "501"
0x180053b76  test    rax, rax
0x180053b79  lea     rcx, aActionFailed; "Action Failed"
0x180053b80  cmovnz  r9, rax; unsigned __int16 *
0x180053b84  mov     rax, [rbp+57h+var_60]
0x180053b88  test    rax, rax
0x180053b8b  cmovnz  rcx, rax
0x180053b8f  mov     [rsp+120h+var_100], rcx; unsigned __int16 *
0x180053b94  lea     rcx, [rbp+57h+var_C0]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x180053b98  call    ?HrBuildFaultResponse@@YAJPEATtagUPNP_CONTROL_RESPONSE_DATA@@PEBG111@Z; HrBuildFaultResponse(tagUPNP_CONTROL_RESPONSE_DATA *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180053b9d  mov     ebx, eax
0x180053b9f  jmp     short loc_180053BF2
0x180053ba1  mov     eax, 8007000Eh
0x180053ba6  mov     ebx, eax
0x180053ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180053baf  cmp     rcx, rdi
0x180053bb2  jz      short loc_180053BF2
0x180053bb4  test    byte ptr [rcx+1Ch], 1
0x180053bb8  jz      short loc_180053BF2
0x180053bba  mov     edx, 9Ch
0x180053bbf  jmp     loc_180053A58
0x180053bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180053bcb  cmp     rcx, rdi
0x180053bce  jz      short loc_180053BF2
0x180053bd0  test    byte ptr [rcx+1Ch], 1
0x180053bd4  jz      short loc_180053BF2
0x180053bd6  mov     edx, 9Dh
0x180053bdb  mov     dword ptr [rsp+120h+var_100], ebx
0x180053bdf  lea     r9, aCupnpautomatio_60; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180053be6  mov     rcx, [rcx+10h]
0x180053bea  mov     r8, rsi
0x180053bed  call    WPP_SF_sd
0x180053bf2  lea     rcx, [rbp+57h+pvarg]; VARIANT *
0x180053bf6  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x180053bfb  jmp     short loc_180053C1B
0x180053bfd  lea     rax, aInvalidVar; "Invalid Var"
0x180053c04  lea     r9, a404; "404"
0x180053c0b  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180053c10  lea     rcx, [rbp+57h+var_C0]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x180053c14  call    ?HrBuildFaultResponse@@YAJPEATtagUPNP_CONTROL_RESPONSE_DATA@@PEBG111@Z; HrBuildFaultResponse(tagUPNP_CONTROL_RESPONSE_DATA *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180053c19  mov     ebx, eax
0x180053c1b  test    ebx, ebx
0x180053c1d  js      short loc_180053C40
0x180053c1f  movups  xmm0, [rbp+57h+var_D0]
0x180053c23  movups  xmm1, [rbp+57h+var_C0]
0x180053c27  movups  xmmword ptr [r12], xmm0
0x180053c2c  movups  xmm0, [rbp+57h+var_B0]
0x180053c30  movups  xmmword ptr [r12+10h], xmm1
0x180053c36  movups  xmmword ptr [r12+20h], xmm0
0x180053c3c  jz      short loc_180053CAA
0x180053c3e  jmp     short loc_180053C49
0x180053c40  lea     rdx, [rbp+57h+var_D0]; struct tagUPNP_CONTROL_RESPONSE *
0x180053c44  call    ?FreeControlResponse@CUPnPAutomationProxy@@AEAAXPEAUtagUPNP_CONTROL_RESPONSE@@@Z; CUPnPAutomationProxy::FreeControlResponse(tagUPNP_CONTROL_RESPONSE *)
0x180053c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c50  cmp     rcx, rdi
0x180053c53  jz      short loc_180053CAA
0x180053c55  test    byte ptr [rcx+1Ch], 1
0x180053c59  jz      short loc_180053CAA
0x180053c5b  mov     edx, 9Eh
0x180053c60  lea     r9, aCupnpautomatio_40; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180053c67  mov     r8, rsi
0x180053c6a  jmp     short loc_180053C9D
0x180053c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c73  lea     rdi, WPP_GLOBAL_Control
0x180053c7a  mov     ebx, 80070057h
0x180053c7f  cmp     rcx, rdi
0x180053c82  jz      short loc_180053CAA
0x180053c84  test    byte ptr [rcx+1Ch], 1
0x180053c88  jz      short loc_180053CAA
0x180053c8a  mov     edx, 92h
0x180053c8f  lea     r9, aInvalidArgumen; "Invalid arguments passed to HrQueryStat"...
0x180053c96  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180053c9d  mov     rcx, [rcx+10h]
0x180053ca1  mov     dword ptr [rsp+120h+var_100], ebx
0x180053ca5  call    WPP_SF_sd
0x180053caa  mov     eax, ebx
0x180053cac  add     rsp, 0F0h
0x180053cb3  pop     r15
0x180053cb5  pop     r14
  ... truncated ...
```
