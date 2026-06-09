# CUPnPAutomationProxy::QueryStateVariablesByDispIds(ulong,long *,ulong *,ushort * * *,tagVARIANT * *,ushort * * *)

- ea: `0x1800361d0`
- end: `0x1800367da`
- name: `?QueryStateVariablesByDispIds@CUPnPAutomationProxy@@UEAAJKPEAJPEAKPEAPEAPEAGPEAPEAUtagVARIANT@@2@Z`
- size: `1546`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, unsigned int, int *, unsigned int *, unsigned __int16 ***, struct tagVARIANT **, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x180018738`
- `0x18001e9bc`
- `0x180031a90`
- `0x1800361d0`
- `0x180038ce4`
- `0x18003994c`
- `0x18003ae80`
- `0x180050790`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036313`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800363d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800363e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800363f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800363d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800363e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800363f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003671a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003673c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003671a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003673c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036755`
- `OLEAUT32!__imp_VariantInit` at `0x1800364d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800364d3`

## string_xrefs

- `0x180036280`: `HrIsAllowedCOMCallLocality failed !`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::QueryStateVariablesByDispIds(
        CUPnPAutomationProxy *this,
        unsigned int a2,
        int *a3,
        unsigned int *a4,
        unsigned __int16 ***a5,
        struct tagVARIANT **a6,
        unsigned __int16 ***a7)
{
  int *v7; // rdi
  int IsAllowedCOMCallLocality; // eax
  int v12; // ebx
  STRSAFE_PCNZWCH v13; // rcx
  __int64 i; // r8
  unsigned __int64 v15; // rcx
  unsigned int v16; // ebx
  unsigned int v17; // esi
  void *v18; // r15
  VARIANT *v19; // r13
  LPVOID v20; // rax
  void *v21; // r12
  __int64 v22; // r13
  const unsigned __int16 **v23; // rax
  const unsigned __int16 **v24; // rbx
  unsigned __int16 *v25; // rax
  VARIANTARG *v26; // rbx
  int v27; // eax
  CUPnPAutomationProxy *v28; // rax
  unsigned int (__fastcall ***v29)(_QWORD, __int64 *, void **); // rcx
  __int64 j; // r14
  void *v31; // rcx
  __int64 k; // r14
  __int64 m; // r14
  void *v34; // rcx
  int v35; // [rsp+20h] [rbp-A8h]
  size_t Size; // [rsp+50h] [rbp-78h] BYREF
  int *v37; // [rsp+58h] [rbp-70h]
  struct tagVARIANT *v38; // [rsp+60h] [rbp-68h]
  size_t v39; // [rsp+68h] [rbp-60h]
  __int128 v40; // [rsp+70h] [rbp-58h] BYREF
  __int64 v41; // [rsp+80h] [rbp-48h]

  v7 = a3;
  if ( !a3 )
    return 2147942487LL;
  if ( !a4 || !a5 || !a6 || !a7 )
    return 2147500035LL;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  v12 = IsAllowedCOMCallLocality;
  if ( IsAllowedCOMCallLocality < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return (unsigned int)v12;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_84;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"HrIsAllowedCOMCallLocality failed !",
      IsAllowedCOMCallLocality);
    goto LABEL_11;
  }
  if ( *((_DWORD *)this + 20) != 2 )
  {
    v12 = -2147418113;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return (unsigned int)v12;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_84;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"QueryStateVariablesByDispIds failed, CUPnPAutomationProxy is not initialized!",
      255);
LABEL_11:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_84;
  }
  if ( a2 )
  {
    v37 = a3;
  }
  else
  {
    a2 = *((_DWORD *)this + 24);
    v7 = (int *)malloc(saturated_mul(a2, 4u));
    if ( v7 )
    {
      for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
        v7[i] = *(_DWORD *)(*((_QWORD *)this + 13) + 24 * i + 20);
    }
    else
    {
      v12 = -2147024882;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_80;
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
        (unsigned int)"CUPnPAutomationProxy::QueryStateVariablesByDispIds(): Could not allocate array of dispids",
        14);
    }
    if ( v12 < 0 )
      goto LABEL_79;
    v37 = v7;
  }
  v15 = 8LL * a2;
  if ( v15 > 0xFFFFFFFF || (v16 = 24 * a2, 24 * (unsigned __int64)a2 > 0xFFFFFFFF) )
  {
    v12 = -2147024362;
    goto LABEL_79;
  }
  v17 = 0;
  Size = (unsigned int)v15;
  v18 = CoTaskMemAlloc((unsigned int)v15);
  v39 = v16;
  v38 = (struct tagVARIANT *)CoTaskMemAlloc(v16);
  v19 = v38;
  v20 = CoTaskMemAlloc(8 * a2);
  v21 = v20;
  if ( !v18 || !v38 || !v20 )
  {
    v12 = -2147024882;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
        (unsigned int)"CUPnPAutomationProxy::QueryStateVariablesByDispIds(): Could not allocate output arrays",
        14);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v18 )
      goto LABEL_63;
    goto LABEL_68;
  }
  memset_0(v18, 0, Size);
  memset_0(v38, 0, v39);
  memset_0(v21, 0, Size);
  v12 = 0;
  while ( v17 < a2 )
  {
    v22 = v17++;
    v23 = (const unsigned __int16 **)CUPnPAutomationProxy::LookupVariableByDispID(this, v37[v22]);
    v24 = v23;
    if ( !v23 )
    {
      v12 = -2147352573;
      break;
    }
    *((_QWORD *)v18 + v22) = COMSzFromWsz(*v23);
    v25 = COMSzFromWsz(v24[1]);
    *((_QWORD *)v21 + v22) = v25;
    if ( !*((_QWORD *)v18 + v22) || !v25 )
    {
      v12 = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::QueryStateVariablesByDispIds(): Could not allocate name/data type strings",
          14);
      goto LABEL_54;
    }
    LODWORD(Size) = 0;
    v41 = 0;
    v40 = 0;
    v26 = &v38[v22];
    VariantInit(v26);
    LOWORD(v35) = 2;
    v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, int, __int128 *, VARIANTARG *, _QWORD, size_t *))(**((_QWORD **)this + 11) + 48LL))(
            *((_QWORD *)this + 11),
            (unsigned int)v37[v22],
            &GUID_NULL,
            2048,
            v35,
            &v40,
            v26,
            0,
            &Size);
    v12 = v27;
    if ( v27 == -2147023174 || (unsigned int)(v27 + 2147023170) <= 1 || v27 == -2147417848 )
    {
      v28 = this;
      v29 = (unsigned int (__fastcall ***)(_QWORD, __int64 *, void **))*((_QWORD *)this + 11);
      if ( v29 )
      {
        if ( (**v29)(v29, bogusIID, &pBogusInterface) == -2147467262 )
          goto LABEL_44;
        v28 = this;
      }
      HrUnregisterDeviceByUDN(*((unsigned __int16 **)v28 + 17));
    }
LABEL_44:
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::QueryStateVariablesByDispIds(): IDispatch::Invoke failed",
          v12);
    }
    else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
        (unsigned int)v37[v22]);
    }
LABEL_54:
    if ( v12 < 0 )
      break;
  }
  if ( v12 >= 0 )
  {
    *a4 = v17;
    *a5 = (unsigned __int16 **)v18;
    *a6 = v38;
    *a7 = (unsigned __int16 **)v21;
    goto LABEL_79;
  }
LABEL_63:
  for ( j = 0; (unsigned int)j < v17; j = (unsigned int)(j + 1) )
  {
    v31 = (void *)*((_QWORD *)v18 + j);
    if ( v31 )
    {
      CoTaskMemFree(v31);
      *((_QWORD *)v18 + j) = 0;
    }
  }
  CoTaskMemFree(v18);
  v13 = WPP_GLOBAL_Control;
  v19 = v38;
LABEL_68:
  if ( v19 )
  {
    for ( k = 0; (unsigned int)k < v17; k = (unsigned int)(k + 1) )
      SafeClearVariant(&v19[k]);
    CoTaskMemFree(v19);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v21 )
  {
    for ( m = 0; (unsigned int)m < v17; m = (unsigned int)(m + 1) )
    {
      v34 = (void *)*((_QWORD *)v21 + m);
      if ( v34 )
      {
        CoTaskMemFree(v34);
        *((_QWORD *)v21 + m) = 0;
      }
    }
    CoTaskMemFree(v21);
LABEL_79:
    v13 = WPP_GLOBAL_Control;
  }
LABEL_80:
  if ( v7 != a3 && v7 )
  {
    operator delete(v7);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
LABEL_84:
    if ( v13 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v13[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)v13 + 2),
        28,
        (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
        (unsigned int)"CUPnPAutomationProxy::QueryStateVariablesByDispIds(): Exiting",
        v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800361d0  mov     rax, rsp
0x1800361d3  mov     [rax+10h], rbx
0x1800361d7  mov     [rax+20h], r9
0x1800361db  mov     [rax+18h], r8
0x1800361df  mov     [rax+8], rcx
0x1800361e3  push    rbp
0x1800361e4  push    rsi
0x1800361e5  push    rdi
0x1800361e6  push    r12
0x1800361e8  push    r13
0x1800361ea  push    r14
0x1800361ec  push    r15
0x1800361ee  sub     rsp, 90h
0x1800361f5  mov     rax, r9
0x1800361f8  mov     rdi, r8
0x1800361fb  mov     r14d, edx
0x1800361fe  mov     rsi, rcx
0x180036201  test    r8, r8
0x180036204  jnz     short loc_180036210
0x180036206  mov     eax, 80070057h
0x18003620b  jmp     loc_1800367BF
0x180036210  test    rax, rax
0x180036213  jz      loc_1800367BA
0x180036219  cmp     [rsp+0C8h+arg_20], 0
0x180036222  jz      loc_1800367BA
0x180036228  cmp     [rsp+0C8h+arg_28], 0
0x180036231  jz      loc_1800367BA
0x180036237  cmp     [rsp+0C8h+arg_30], 0
0x180036240  jz      loc_1800367BA
0x180036246  mov     ecx, 1
0x18003624b  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180036250  mov     ebx, eax
0x180036252  test    eax, eax
0x180036254  jns     short loc_1800362A3
0x180036256  mov     rcx, cs:WPP_GLOBAL_Control
0x18003625d  lea     rbp, WPP_GLOBAL_Control
0x180036264  cmp     rcx, rbp
0x180036267  jz      loc_1800367B6
0x18003626d  test    byte ptr [rcx+1Ch], 1
0x180036271  jz      loc_18003678B
0x180036277  mov     edx, 15h
0x18003627c  mov     [rsp+0C8h+var_A8], eax
0x180036280  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x180036287  mov     rcx, [rcx+10h]
0x18003628b  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180036292  call    WPP_SF_sd
0x180036297  mov     rcx, cs:WPP_GLOBAL_Control
0x18003629e  jmp     loc_18003678B
0x1800362a3  mov     eax, [rsi+50h]
0x1800362a6  cmp     eax, 2
0x1800362a9  jz      short loc_1800362E3
0x1800362ab  mov     ebx, 8000FFFFh
0x1800362b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362b7  lea     rbp, WPP_GLOBAL_Control
0x1800362be  cmp     rcx, rbp
0x1800362c1  jz      loc_1800367B6
0x1800362c7  test    byte ptr [rcx+1Ch], 1
0x1800362cb  jz      loc_18003678B
0x1800362d1  mov     edx, 16h
0x1800362d6  mov     [rsp+0C8h+var_A8], ebx
0x1800362da  lea     r9, aQuerystatevari; "QueryStateVariablesByDispIds failed, CU"...
0x1800362e1  jmp     short loc_180036287
0x1800362e3  lea     rbp, WPP_GLOBAL_Control
0x1800362ea  mov     r15d, 8007000Eh
0x1800362f0  test    r14d, r14d
0x1800362f3  jnz     loc_180036390
0x1800362f9  mov     r14d, [rsi+60h]
0x1800362fd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180036304  mov     eax, 4
0x180036309  mul     r14
0x18003630c  cmovb   rax, rcx
0x180036310  mov     rcx, rax; Size
0x180036313  call    cs:__imp_malloc
0x180036319  mov     rdi, rax
0x18003631c  test    rax, rax
0x18003631f  jz      short loc_180036343
0x180036321  xor     r8d, r8d
0x180036324  test    r14d, r14d
0x180036327  jz      short loc_180036381
0x180036329  mov     rax, [rsi+68h]
0x18003632d  lea     rcx, [r8+r8*2]
0x180036331  mov     ecx, [rax+rcx*8+14h]
0x180036335  mov     [rdi+r8*4], ecx
0x180036339  inc     r8d
0x18003633c  cmp     r8d, r14d
0x18003633f  jb      short loc_180036329
0x180036341  jmp     short loc_180036381
0x180036343  mov     ebx, r15d
0x180036346  mov     rcx, cs:WPP_GLOBAL_Control
0x18003634d  cmp     rcx, rbp
0x180036350  jz      loc_180036769
0x180036356  test    byte ptr [rcx+1Ch], 1
0x18003635a  jz      loc_180036769
0x180036360  mov     rcx, [rcx+10h]
0x180036364  lea     r9, aCupnpautomatio_53; "CUPnPAutomationProxy::QueryStateVariabl"...
0x18003636b  mov     edx, 17h
0x180036370  mov     [rsp+0C8h+var_A8], r15d
0x180036375  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18003637c  call    WPP_SF_sd
0x180036381  test    ebx, ebx
0x180036383  js      loc_180036762
0x180036389  mov     [rsp+0C8h+var_70], rdi
0x18003638e  jmp     short loc_18003639D
0x180036390  mov     rax, [rsp+0C8h+arg_10]
0x180036398  mov     [rsp+0C8h+var_70], rax
0x18003639d  mov     eax, r14d
0x1800363a0  mov     edx, 0FFFFFFFFh
0x1800363a5  lea     rcx, ds:0[rax*8]
0x1800363ad  cmp     rcx, rdx
0x1800363b0  ja      loc_18003675D
0x1800363b6  lea     rbx, [rax+rax*2]
0x1800363ba  shl     rbx, 3
0x1800363be  cmp     rbx, rdx
0x1800363c1  ja      loc_18003675D
0x1800363c7  mov     r12d, ecx
0x1800363ca  xor     esi, esi
0x1800363cc  mov     ecx, ecx; cb
0x1800363ce  mov     [rsp+0C8h+Size], r12
0x1800363d3  call    cs:__imp_CoTaskMemAlloc
0x1800363d9  mov     r15, rax
0x1800363dc  mov     ecx, ebx; cb
0x1800363de  mov     eax, ebx
0x1800363e0  mov     [rsp+0C8h+var_60], rax
0x1800363e5  call    cs:__imp_CoTaskMemAlloc
0x1800363eb  mov     ecx, r12d; cb
0x1800363ee  mov     [rsp+0C8h+var_68], rax
0x1800363f3  mov     r13, rax
0x1800363f6  call    cs:__imp_CoTaskMemAlloc
0x1800363fc  mov     r12, rax
0x1800363ff  test    r15, r15
0x180036402  jz      loc_18003666F
0x180036408  test    r13, r13
0x18003640b  jz      loc_18003666F
0x180036411  test    rax, rax
0x180036414  jz      loc_18003666F
0x18003641a  mov     r8, [rsp+0C8h+Size]; Size
0x18003641f  xor     edx, edx; Val
0x180036421  mov     rcx, r15; void *
0x180036424  call    memset_0
0x180036429  mov     r8, [rsp+0C8h+var_60]; Size
0x18003642e  xor     edx, edx; Val
0x180036430  mov     rcx, r13; void *
0x180036433  call    memset_0
0x180036438  mov     r8, [rsp+0C8h+Size]; Size
0x18003643d  xor     edx, edx; Val
0x18003643f  mov     rcx, r12; void *
0x180036442  call    memset_0
0x180036447  xor     ebx, ebx
0x180036449  cmp     esi, r14d
0x18003644c  jnb     loc_180036636
0x180036452  mov     rax, [rsp+0C8h+var_70]
0x180036457  mov     rcx, [rsp+0C8h+arg_0]; this
0x18003645f  mov     r13d, esi
0x180036462  inc     esi
0x180036464  mov     edx, [rax+r13*4]; int
0x180036468  call    ?LookupVariableByDispID@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_STATE_VARIABLE@@J@Z; CUPnPAutomationProxy::LookupVariableByDispID(long)
0x18003646d  mov     rbx, rax
0x180036470  test    rax, rax
0x180036473  jz      loc_180036631
0x180036479  mov     rcx, [rax]; unsigned __int16 *
0x18003647c  call    ?COMSzFromWsz@@YAPEAGPEBG@Z; COMSzFromWsz(ushort const *)
0x180036481  mov     [r15+r13*8], rax
0x180036485  mov     rcx, [rbx+8]; unsigned __int16 *
0x180036489  call    ?COMSzFromWsz@@YAPEAGPEBG@Z; COMSzFromWsz(ushort const *)
0x18003648e  xor     ecx, ecx
0x180036490  mov     [r12+r13*8], rax
0x180036494  cmp     [r15+r13*8], rcx
0x180036498  jz      loc_1800365EE
0x18003649e  test    rax, rax
0x1800364a1  jz      loc_1800365EE
0x1800364a7  mov     dword ptr [rsp+0C8h+Size], ecx
0x1800364ab  lea     rax, ds:0[r13*2]
0x1800364b3  mov     [rsp+0C8h+var_48], rcx
0x1800364bb  add     rax, r13
0x1800364be  mov     rcx, [rsp+0C8h+var_68]
0x1800364c3  xorps   xmm0, xmm0
0x1800364c6  movdqu  [rsp+0C8h+var_58], xmm0
0x1800364cc  lea     rbx, [rcx+rax*8]
0x1800364d0  mov     rcx, rbx; pvarg
0x1800364d3  call    cs:__imp_VariantInit
0x1800364d9  mov     rax, [rsp+0C8h+arg_0]
0x1800364e1  lea     rdx, [rsp+0C8h+Size]
0x1800364e6  mov     [rsp+0C8h+var_88], rdx
0x1800364eb  lea     r8, GUID_NULL
0x1800364f2  mov     [rsp+0C8h+var_90], 0
0x1800364fb  lea     rdx, [rsp+0C8h+var_58]
0x180036500  mov     [rsp+0C8h+var_98], rbx
0x180036505  mov     r9d, 800h
0x18003650b  mov     rcx, [rax+58h]
0x18003650f  mov     [rsp+0C8h+var_A0], rdx
0x180036514  mov     rdx, [rsp+0C8h+var_70]
0x180036519  mov     word ptr [rsp+0C8h+var_A8], 2
0x180036520  mov     rax, [rcx]
0x180036523  mov     edx, [rdx+r13*4]
0x180036527  mov     rax, [rax+30h]
0x18003652b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036530  mov     ebx, eax
0x180036532  cmp     eax, 800706BAh
0x180036537  jz      short loc_18003654B
0x180036539  add     eax, 7FF8F942h
0x18003653e  cmp     eax, 1
0x180036541  jbe     short loc_18003654B
0x180036543  cmp     ebx, 80010108h
0x180036549  jnz     short loc_180036590
0x18003654b  mov     rax, [rsp+0C8h+arg_0]
0x180036553  mov     rcx, [rax+58h]
0x180036557  test    rcx, rcx
0x18003655a  jz      short loc_180036584
0x18003655c  mov     rax, [rcx]
0x18003655f  lea     r8, ?pBogusInterface@@3PEAXEA; void * pBogusInterface
0x180036566  lea     rdx, bogusIID
0x18003656d  mov     rax, [rax]
0x180036570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036575  cmp     eax, 80004002h
0x18003657a  jz      short loc_180036590
0x18003657c  mov     rax, [rsp+0C8h+arg_0]
0x180036584  mov     rcx, [rax+88h]; unsigned __int16 *
0x18003658b  call    ?HrUnregisterDeviceByUDN@@YAJPEAG@Z; HrUnregisterDeviceByUDN(ushort *)
0x180036590  test    ebx, ebx
0x180036592  js      short loc_1800365CA
0x180036594  mov     rcx, cs:WPP_GLOBAL_Control
0x18003659b  cmp     rcx, rbp
0x18003659e  jz      loc_180036627
0x1800365a4  test    byte ptr [rcx+1Ch], 40h
0x1800365a8  jz      short loc_180036627
0x1800365aa  mov     rax, [rsp+0C8h+var_70]
0x1800365af  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800365b6  mov     rcx, [rcx+10h]
0x1800365ba  mov     edx, 18h
0x1800365bf  mov     r9d, [rax+r13*4]
0x1800365c3  call    WPP_SF_d
0x1800365c8  jmp     short loc_180036627
0x1800365ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365d1  cmp     rcx, rbp
0x1800365d4  jz      short loc_180036627
0x1800365d6  test    byte ptr [rcx+1Ch], 1
0x1800365da  jz      short loc_180036627
0x1800365dc  mov     edx, 19h
0x1800365e1  mov     [rsp+0C8h+var_A8], ebx
0x1800365e5  lea     r9, aCupnpautomatio_43; "CUPnPAutomationProxy::QueryStateVariabl"...
0x1800365ec  jmp     short loc_180036617
0x1800365ee  mov     eax, 8007000Eh
0x1800365f3  mov     ebx, eax
0x1800365f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365fc  cmp     rcx, rbp
0x1800365ff  jz      short loc_180036627
0x180036601  test    byte ptr [rcx+1Ch], 1
0x180036605  jz      short loc_180036627
0x180036607  mov     edx, 1Ah
0x18003660c  mov     [rsp+0C8h+var_A8], eax
0x180036610  lea     r9, aCupnpautomatio_19; "CUPnPAutomationProxy::QueryStateVariabl"...
0x180036617  mov     rcx, [rcx+10h]
0x18003661b  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180036622  call    WPP_SF_sd
0x180036627  test    ebx, ebx
0x180036629  jns     loc_180036449
0x18003662f  jmp     short loc_180036636
0x180036631  mov     ebx, 80020003h
0x180036636  test    ebx, ebx
0x180036638  js      short loc_1800366B4
0x18003663a  mov     rax, [rsp+0C8h+arg_18]
0x180036642  mov     rcx, [rsp+0C8h+arg_28]
0x18003664a  mov     [rax], esi
0x18003664c  mov     rax, [rsp+0C8h+arg_20]
0x180036654  mov     [rax], r15
0x180036657  mov     rax, [rsp+0C8h+var_68]
0x18003665c  mov     [rcx], rax
0x18003665f  mov     rax, [rsp+0C8h+arg_30]
0x180036667  mov     [rax], r12
0x18003666a  jmp     loc_180036762
0x18003666f  mov     eax, 8007000Eh
0x180036674  mov     ebx, eax
0x180036676  mov     rcx, cs:WPP_GLOBAL_Control
0x18003667d  cmp     rcx, rbp
0x180036680  jz      short loc_1800366AF
0x180036682  test    byte ptr [rcx+1Ch], 1
0x180036686  jz      short loc_1800366AF
0x180036688  mov     rcx, [rcx+10h]
0x18003668c  lea     r9, aCupnpautomatio_22; "CUPnPAutomationProxy::QueryStateVariabl"...
0x180036693  mov     edx, 1Bh
0x180036698  mov     [rsp+0C8h+var_A8], eax
0x18003669c  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800366a3  call    WPP_SF_sd
0x1800366a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366af  test    r15, r15
0x1800366b2  jz      short loc_1800366EF
0x1800366b4  xor     r14d, r14d
0x1800366b7  test    esi, esi
0x1800366b9  jz      short loc_1800366DA
0x1800366bb  mov     rcx, [r15+r14*8]; pv
0x1800366bf  test    rcx, rcx
0x1800366c2  jz      short loc_1800366D2
0x1800366c4  call    cs:__imp_CoTaskMemFree
0x1800366ca  mov     qword ptr [r15+r14*8], 0
0x1800366d2  inc     r14d
0x1800366d5  cmp     r14d, esi
0x1800366d8  jb      short loc_1800366BB
0x1800366da  mov     rcx, r15; pv
0x1800366dd  call    cs:__imp_CoTaskMemFree
0x1800366e3  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
