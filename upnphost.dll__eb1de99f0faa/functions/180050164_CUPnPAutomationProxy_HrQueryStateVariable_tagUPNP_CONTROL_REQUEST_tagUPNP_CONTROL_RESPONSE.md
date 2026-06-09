# CUPnPAutomationProxy::HrQueryStateVariable(tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *)

- ea: `0x180050164`
- end: `0x180050646`
- name: `?HrQueryStateVariable@CUPnPAutomationProxy@@AEAAJPEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@@Z`
- size: `1250`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct tagUPNP_CONTROL_REQUEST *, struct tagUPNP_CONTROL_RESPONSE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002dcbc`

## callees

- `0x18000db4c`
- `0x18000dbc0`
- `0x180032fd4`
- `0x180035dfc`
- `0x180039388`
- `0x18003994c`
- `0x180039a84`
- `0x18003ae80`
- `0x180050164`
- `0x180050790`
- `0x1800507d0`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800502fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800502fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800502d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18005042f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800502d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18005042f`
- `OLEAUT32!__imp_VariantInit` at `0x180050202`
- `OLEAUT32!__imp_VariantInit` at `0x180050312`
- `OLEAUT32!__imp_VariantInit` at `0x180050202`
- `OLEAUT32!__imp_VariantInit` at `0x180050312`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18005031f`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18005031f`

## string_xrefs

- `0x18005037e`: `CUPnPAutomationProxy::HrQueryStateVariable(): Failed to copy result to output`

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
0x180050164  push    rbp
0x180050166  push    rbx
0x180050167  push    rsi
0x180050168  push    rdi
0x180050169  push    r12
0x18005016b  push    r14
0x18005016d  push    r15
0x18005016f  lea     rbp, [rsp-27h]
0x180050174  sub     rsp, 0F0h
0x18005017b  cmp     dword ptr [rdx+8], 1
0x18005017f  xorps   xmm0, xmm0
0x180050182  movups  [rbp+57h+var_D0], xmm0
0x180050186  mov     r12, r8
0x180050189  mov     r14, rcx
0x18005018c  movups  [rbp+57h+var_C0], xmm0
0x180050190  movups  [rbp+57h+var_B0], xmm0
0x180050194  jnz     loc_1800505F4
0x18005019a  mov     rax, [rdx+10h]
0x18005019e  mov     ecx, 8
0x1800501a3  cmp     cx, [rax]
0x1800501a6  jnz     loc_1800505F4
0x1800501ac  mov     r15, [rax+8]
0x1800501b0  mov     rcx, r14; this
0x1800501b3  mov     rdx, r15; unsigned __int16 *
0x1800501b6  call    ?LookupVariableByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_STATE_VARIABLE@@PEBG@Z; CUPnPAutomationProxy::LookupVariableByName(ushort const *)
0x1800501bb  lea     rdi, WPP_GLOBAL_Control
0x1800501c2  mov     rbx, rax
0x1800501c5  lea     rsi, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800501cc  test    rax, rax
0x1800501cf  jz      loc_180050585
0x1800501d5  xor     eax, eax
0x1800501d7  mov     [rbp+57h+var_78], 0
0x1800501df  xorps   xmm0, xmm0
0x1800501e2  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800501e6  xor     edx, edx; Val
0x1800501e8  lea     rcx, [rbp+57h+var_70]; void *
0x1800501ec  movdqu  [rbp+57h+var_88], xmm0
0x1800501f1  lea     r8d, [rax+40h]; Size
0x1800501f5  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800501f9  call    memset_0
0x1800501fe  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180050202  call    cs:__imp_VariantInit
0x180050208  mov     rcx, [r14+58h]
0x18005020c  lea     rdx, [rbp+57h+var_70]
0x180050210  mov     [rsp+120h+var_E0], 0
0x180050219  lea     r8, GUID_NULL
0x180050220  mov     [rsp+120h+var_E8], rdx
0x180050225  mov     r9d, 800h
0x18005022b  lea     rdx, [rbp+57h+pvarg]
0x18005022f  mov     rax, [rcx]
0x180050232  mov     [rsp+120h+var_F0], rdx
0x180050237  lea     rdx, [rbp+57h+var_88]
0x18005023b  mov     [rsp+120h+var_F8], rdx
0x180050240  mov     edx, [rbx+14h]
0x180050243  mov     rax, [rax+30h]
0x180050247  mov     word ptr [rsp+120h+var_100], 2
0x18005024e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050253  mov     ebx, eax
0x180050255  cmp     eax, 800706BAh
0x18005025a  jz      short loc_18005026E
0x18005025c  lea     ecx, [rax+7FF8F942h]
0x180050262  cmp     ecx, 1
0x180050265  jbe     short loc_18005026E
0x180050267  cmp     eax, 80010108h
0x18005026c  jnz     short loc_1800502A3
0x18005026e  mov     rcx, [r14+58h]
0x180050272  test    rcx, rcx
0x180050275  jz      short loc_180050297
0x180050277  mov     rax, [rcx]
0x18005027a  lea     r8, ?pBogusInterface@@3PEAXEA; void * pBogusInterface
0x180050281  lea     rdx, bogusIID
0x180050288  mov     rax, [rax]
0x18005028b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050290  cmp     eax, 80004002h
0x180050295  jz      short loc_1800502A3
0x180050297  mov     rcx, [r14+88h]; unsigned __int16 *
0x18005029e  call    ?HrUnregisterDeviceByUDN@@YAJPEAG@Z; HrUnregisterDeviceByUDN(ushort *)
0x1800502a3  test    ebx, ebx
0x1800502a5  js      loc_1800503F6
0x1800502ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800502b2  cmp     rcx, rdi
0x1800502b5  jz      short loc_1800502D1
0x1800502b7  test    byte ptr [rcx+1Ch], 40h
0x1800502bb  jz      short loc_1800502D1
0x1800502bd  mov     rcx, [rcx+10h]
0x1800502c1  mov     edx, 93h
0x1800502c6  mov     r9, r15
0x1800502c9  mov     r8, rsi
0x1800502cc  call    WPP_SF_S
0x1800502d1  lea     rcx, aQuerystatevari_0; "QueryStateVariable"
0x1800502d8  call    cs:__imp_SysAllocString
0x1800502de  mov     qword ptr [rbp+57h+var_D0], rax
0x1800502e2  test    rax, rax
0x1800502e5  jz      loc_1800503C0
0x1800502eb  mov     r14d, 1
0x1800502f1  mov     dword ptr [rbp+57h+var_D0+8], r14d
0x1800502f5  mov     dword ptr [rbp+57h+var_C0], r14d
0x1800502f9  lea     ecx, [r14+17h]; cb
0x1800502fd  call    cs:__imp_CoTaskMemAlloc
0x180050303  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180050307  mov     rbx, rax
0x18005030a  test    rax, rax
0x18005030d  jz      short loc_18005038A
0x18005030f  mov     rcx, rax; pvarg
0x180050312  call    cs:__imp_VariantInit
0x180050318  lea     rdx, [rbp+57h+pvarg]; pvargSrc
0x18005031c  mov     rcx, rbx; pvarDest
0x18005031f  call    cs:__imp_VariantCopyInd
0x180050325  mov     ebx, eax
0x180050327  test    eax, eax
0x180050329  js      short loc_18005035B
0x18005032b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050332  cmp     rcx, rdi
0x180050335  jz      loc_18005057A
0x18005033b  test    byte ptr [rcx+1Ch], 40h
0x18005033f  jz      loc_18005057A
0x180050345  mov     rcx, [rcx+10h]
0x180050349  mov     edx, 94h
0x18005034e  mov     r8, rsi
0x180050351  call    WPP_SF_
0x180050356  jmp     loc_18005057A
0x18005035b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050362  cmp     rcx, rdi
0x180050365  jz      loc_18005057A
0x18005036b  test    [rcx+1Ch], r14b
0x18005036f  jz      loc_18005057A
0x180050375  mov     edx, 95h
0x18005037a  mov     dword ptr [rsp+120h+var_100], eax
0x18005037e  lea     r9, aCupnpautomatio_68; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x180050385  jmp     loc_18005056E
0x18005038a  mov     eax, 8007000Eh
0x18005038f  mov     ebx, eax
0x180050391  mov     rcx, cs:WPP_GLOBAL_Control
0x180050398  cmp     rcx, rdi
0x18005039b  jz      loc_18005057A
0x1800503a1  test    [rcx+1Ch], r14b
0x1800503a5  jz      loc_18005057A
0x1800503ab  mov     edx, 96h
0x1800503b0  mov     dword ptr [rsp+120h+var_100], eax
0x1800503b4  lea     r9, aCupnpautomatio_78; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x1800503bb  jmp     loc_18005056E
0x1800503c0  mov     eax, 8007000Eh
0x1800503c5  mov     ebx, eax
0x1800503c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503ce  cmp     rcx, rdi
0x1800503d1  jz      loc_18005057A
0x1800503d7  test    byte ptr [rcx+1Ch], 1
0x1800503db  jz      loc_18005057A
0x1800503e1  mov     edx, 97h
0x1800503e6  mov     dword ptr [rsp+120h+var_100], eax
0x1800503ea  lea     r9, aCupnpautomatio_77; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x1800503f1  jmp     loc_18005056E
0x1800503f6  cmp     ebx, 80020009h
0x1800503fc  jnz     loc_18005054C
0x180050402  mov     rcx, cs:WPP_GLOBAL_Control
0x180050409  cmp     rcx, rdi
0x18005040c  jz      short loc_180050428
0x18005040e  test    byte ptr [rcx+1Ch], 40h
0x180050412  jz      short loc_180050428
0x180050414  mov     rcx, [rcx+10h]
0x180050418  mov     edx, 98h
0x18005041d  mov     r9, r15
0x180050420  mov     r8, rsi
0x180050423  call    WPP_SF_S
0x180050428  lea     rcx, aQuerystatevari_0; "QueryStateVariable"
0x18005042f  call    cs:__imp_SysAllocString
0x180050435  mov     qword ptr [rbp+57h+var_D0], rax
0x180050439  test    rax, rax
0x18005043c  jz      loc_180050529
0x180050442  cmp     [rbp+57h+var_40], 0
0x180050447  mov     dword ptr [rbp+57h+var_D0+8], 0
0x18005044e  jz      loc_1800504F3
0x180050454  call    ?ValidateCallerAccess@@YAJXZ; ValidateCallerAccess(void)
0x180050459  test    eax, eax
0x18005045b  js      short loc_1800504C5
0x18005045d  mov     rax, [rbp+57h+var_40]
0x180050461  lea     rcx, [rbp+57h+var_70]
0x180050465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005046a  mov     ebx, eax
0x18005046c  test    eax, eax
0x18005046e  js      short loc_180050495
0x180050470  mov     rcx, cs:WPP_GLOBAL_Control
0x180050477  cmp     rcx, rdi
0x18005047a  jz      short loc_1800504BC
0x18005047c  test    byte ptr [rcx+1Ch], 40h
0x180050480  jz      short loc_1800504BC
0x180050482  mov     rcx, [rcx+10h]
0x180050486  mov     edx, 99h
0x18005048b  mov     r8, rsi
0x18005048e  call    WPP_SF_
0x180050493  jmp     short loc_1800504F3
0x180050495  mov     rcx, cs:WPP_GLOBAL_Control
0x18005049c  cmp     rcx, rdi
0x18005049f  jz      short loc_1800504BC
0x1800504a1  test    byte ptr [rcx+1Ch], 1
0x1800504a5  jz      short loc_1800504BC
0x1800504a7  mov     edx, 9Ah
0x1800504ac  mov     dword ptr [rsp+120h+var_100], eax
0x1800504b0  lea     r9, aCupnpautomatio_55; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x1800504b7  jmp     loc_18005056E
0x1800504bc  test    eax, eax
0x1800504be  jns     short loc_1800504F3
0x1800504c0  jmp     loc_18005057A
0x1800504c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504cc  cmp     rcx, rdi
0x1800504cf  jz      short loc_1800504F3
0x1800504d1  test    byte ptr [rcx+1Ch], 1
0x1800504d5  jz      short loc_1800504F3
0x1800504d7  mov     rcx, [rcx+10h]
0x1800504db  lea     r9, aCupnpautomatio_41; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x1800504e2  mov     edx, 9Bh
0x1800504e7  mov     dword ptr [rsp+120h+var_100], eax
0x1800504eb  mov     r8, rsi
0x1800504ee  call    WPP_SF_sd
0x1800504f3  mov     rax, [rbp+57h+var_68]
0x1800504f7  lea     r9, a501; "501"
0x1800504fe  test    rax, rax
0x180050501  lea     rcx, aActionFailed; "Action Failed"
0x180050508  cmovnz  r9, rax; unsigned __int16 *
0x18005050c  mov     rax, [rbp+57h+var_60]
0x180050510  test    rax, rax
0x180050513  cmovnz  rcx, rax
0x180050517  mov     [rsp+120h+var_100], rcx; unsigned __int16 *
0x18005051c  lea     rcx, [rbp+57h+var_C0]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x180050520  call    ?HrBuildFaultResponse@@YAJPEATtagUPNP_CONTROL_RESPONSE_DATA@@PEBG111@Z; HrBuildFaultResponse(tagUPNP_CONTROL_RESPONSE_DATA *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180050525  mov     ebx, eax
0x180050527  jmp     short loc_18005057A
0x180050529  mov     eax, 8007000Eh
0x18005052e  mov     ebx, eax
0x180050530  mov     rcx, cs:WPP_GLOBAL_Control
0x180050537  cmp     rcx, rdi
0x18005053a  jz      short loc_18005057A
0x18005053c  test    byte ptr [rcx+1Ch], 1
0x180050540  jz      short loc_18005057A
0x180050542  mov     edx, 9Ch
0x180050547  jmp     loc_1800503E6
0x18005054c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050553  cmp     rcx, rdi
0x180050556  jz      short loc_18005057A
0x180050558  test    byte ptr [rcx+1Ch], 1
0x18005055c  jz      short loc_18005057A
0x18005055e  mov     edx, 9Dh
0x180050563  mov     dword ptr [rsp+120h+var_100], ebx
0x180050567  lea     r9, aCupnpautomatio_60; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x18005056e  mov     rcx, [rcx+10h]
0x180050572  mov     r8, rsi
0x180050575  call    WPP_SF_sd
0x18005057a  lea     rcx, [rbp+57h+pvarg]; VARIANT *
0x18005057e  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x180050583  jmp     short loc_1800505A3
0x180050585  lea     rax, aInvalidVar; "Invalid Var"
0x18005058c  lea     r9, a404; "404"
0x180050593  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180050598  lea     rcx, [rbp+57h+var_C0]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x18005059c  call    ?HrBuildFaultResponse@@YAJPEATtagUPNP_CONTROL_RESPONSE_DATA@@PEBG111@Z; HrBuildFaultResponse(tagUPNP_CONTROL_RESPONSE_DATA *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800505a1  mov     ebx, eax
0x1800505a3  test    ebx, ebx
0x1800505a5  js      short loc_1800505C8
0x1800505a7  movups  xmm0, [rbp+57h+var_D0]
0x1800505ab  movups  xmm1, [rbp+57h+var_C0]
0x1800505af  movups  xmmword ptr [r12], xmm0
0x1800505b4  movups  xmm0, [rbp+57h+var_B0]
0x1800505b8  movups  xmmword ptr [r12+10h], xmm1
0x1800505be  movups  xmmword ptr [r12+20h], xmm0
0x1800505c4  jz      short loc_180050632
0x1800505c6  jmp     short loc_1800505D1
0x1800505c8  lea     rdx, [rbp+57h+var_D0]; struct tagUPNP_CONTROL_RESPONSE *
0x1800505cc  call    ?FreeControlResponse@CUPnPAutomationProxy@@AEAAXPEAUtagUPNP_CONTROL_RESPONSE@@@Z; CUPnPAutomationProxy::FreeControlResponse(tagUPNP_CONTROL_RESPONSE *)
0x1800505d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800505d8  cmp     rcx, rdi
0x1800505db  jz      short loc_180050632
0x1800505dd  test    byte ptr [rcx+1Ch], 1
0x1800505e1  jz      short loc_180050632
0x1800505e3  mov     edx, 9Eh
0x1800505e8  lea     r9, aCupnpautomatio_40; "CUPnPAutomationProxy::HrQueryStateVaria"...
0x1800505ef  mov     r8, rsi
0x1800505f2  jmp     short loc_180050625
0x1800505f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800505fb  lea     rdi, WPP_GLOBAL_Control
0x180050602  mov     ebx, 80070057h
0x180050607  cmp     rcx, rdi
0x18005060a  jz      short loc_180050632
0x18005060c  test    byte ptr [rcx+1Ch], 1
0x180050610  jz      short loc_180050632
0x180050612  mov     edx, 92h
0x180050617  lea     r9, aInvalidArgumen; "Invalid arguments passed to HrQueryStat"...
0x18005061e  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180050625  mov     rcx, [rcx+10h]
0x180050629  mov     dword ptr [rsp+120h+var_100], ebx
0x18005062d  call    WPP_SF_sd
0x180050632  mov     eax, ebx
0x180050634  add     rsp, 0F0h
0x18005063b  pop     r15
0x18005063d  pop     r14
0x18005063f  pop     r12
0x180050641  pop     rdi
0x180050642  pop     rsi
0x180050643  pop     rbx
0x180050644  pop     rbp
0x180050645  retn
  ... truncated ...
```
