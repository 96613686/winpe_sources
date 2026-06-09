# CUPnPAutomationProxy::QueryStateVariablesByDispIds(ulong,long *,ulong *,ushort * * *,tagVARIANT * *,ushort * * *)

- ea: `0x180038580`
- end: `0x180038bc7`
- name: `?QueryStateVariablesByDispIds@CUPnPAutomationProxy@@UEAAJKPEAJPEAKPEAPEAPEAGPEAPEAUtagVARIANT@@2@Z`
- size: `1607`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, unsigned int, int *, unsigned int *, unsigned __int16 ***, struct tagVARIANT **, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000c8e0`
- `0x180013a70`
- `0x1800200f4`
- `0x1800337c4`
- `0x180038580`
- `0x18003b1cc`
- `0x18003bf14`
- `0x18003d4b0`
- `0x180053e18`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800386c3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800386c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800387a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800387b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800387a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800387b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038b1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038b1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038b3b`
- `OLEAUT32!__imp_VariantInit` at `0x18003889b`
- `OLEAUT32!__imp_VariantInit` at `0x18003889b`

## string_xrefs

- `0x180038630`: `HrIsAllowedCOMCallLocality failed !`

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
0x180038580  mov     rax, rsp
0x180038583  mov     [rax+10h], rbx
0x180038587  mov     [rax+20h], r9
0x18003858b  mov     [rax+18h], r8
0x18003858f  mov     [rax+8], rcx
0x180038593  push    rbp
0x180038594  push    rsi
0x180038595  push    rdi
0x180038596  push    r12
0x180038598  push    r13
0x18003859a  push    r14
0x18003859c  push    r15
0x18003859e  sub     rsp, 90h
0x1800385a5  mov     rax, r9
0x1800385a8  mov     rdi, r8
0x1800385ab  mov     r14d, edx
0x1800385ae  mov     rsi, rcx
0x1800385b1  test    r8, r8
0x1800385b4  jnz     short loc_1800385C0
0x1800385b6  mov     eax, 80070057h
0x1800385bb  jmp     loc_180038BAB
0x1800385c0  test    rax, rax
0x1800385c3  jz      loc_180038BA6
0x1800385c9  cmp     [rsp+0C8h+arg_20], 0
0x1800385d2  jz      loc_180038BA6
0x1800385d8  cmp     [rsp+0C8h+arg_28], 0
0x1800385e1  jz      loc_180038BA6
0x1800385e7  cmp     [rsp+0C8h+arg_30], 0
0x1800385f0  jz      loc_180038BA6
0x1800385f6  mov     ecx, 1
0x1800385fb  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180038600  mov     ebx, eax
0x180038602  test    eax, eax
0x180038604  jns     short loc_180038653
0x180038606  mov     rcx, cs:WPP_GLOBAL_Control
0x18003860d  lea     rbp, WPP_GLOBAL_Control
0x180038614  cmp     rcx, rbp
0x180038617  jz      loc_180038BA2
0x18003861d  test    byte ptr [rcx+1Ch], 1
0x180038621  jz      loc_180038B77
0x180038627  mov     edx, 15h
0x18003862c  mov     [rsp+0C8h+var_A8], eax
0x180038630  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x180038637  mov     rcx, [rcx+10h]
0x18003863b  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038642  call    WPP_SF_sd
0x180038647  mov     rcx, cs:WPP_GLOBAL_Control
0x18003864e  jmp     loc_180038B77
0x180038653  mov     eax, [rsi+50h]
0x180038656  cmp     eax, 2
0x180038659  jz      short loc_180038693
0x18003865b  mov     ebx, 8000FFFFh
0x180038660  mov     rcx, cs:WPP_GLOBAL_Control
0x180038667  lea     rbp, WPP_GLOBAL_Control
0x18003866e  cmp     rcx, rbp
0x180038671  jz      loc_180038BA2
0x180038677  test    byte ptr [rcx+1Ch], 1
0x18003867b  jz      loc_180038B77
0x180038681  mov     edx, 16h
0x180038686  mov     [rsp+0C8h+var_A8], ebx
0x18003868a  lea     r9, aQuerystatevari; "QueryStateVariablesByDispIds failed, CU"...
0x180038691  jmp     short loc_180038637
0x180038693  lea     rbp, WPP_GLOBAL_Control
0x18003869a  mov     r15d, 8007000Eh
0x1800386a0  test    r14d, r14d
0x1800386a3  jnz     loc_180038746
0x1800386a9  mov     r14d, [rsi+60h]
0x1800386ad  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800386b4  mov     eax, 4
0x1800386b9  mul     r14
0x1800386bc  cmovb   rax, rcx
0x1800386c0  mov     rcx, rax; Size
0x1800386c3  call    cs:__imp_malloc
0x1800386ca  nop     dword ptr [rax+rax+00h]
0x1800386cf  mov     rdi, rax
0x1800386d2  test    rax, rax
0x1800386d5  jz      short loc_1800386F9
0x1800386d7  xor     r8d, r8d
0x1800386da  test    r14d, r14d
0x1800386dd  jz      short loc_180038737
0x1800386df  mov     rax, [rsi+68h]
0x1800386e3  lea     rcx, [r8+r8*2]
0x1800386e7  mov     ecx, [rax+rcx*8+14h]
0x1800386eb  mov     [rdi+r8*4], ecx
0x1800386ef  inc     r8d
0x1800386f2  cmp     r8d, r14d
0x1800386f5  jb      short loc_1800386DF
0x1800386f7  jmp     short loc_180038737
0x1800386f9  mov     ebx, r15d
0x1800386fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180038703  cmp     rcx, rbp
0x180038706  jz      loc_180038B55
0x18003870c  test    byte ptr [rcx+1Ch], 1
0x180038710  jz      loc_180038B55
0x180038716  mov     rcx, [rcx+10h]
0x18003871a  lea     r9, aCupnpautomatio_53; "CUPnPAutomationProxy::QueryStateVariabl"...
0x180038721  mov     edx, 17h
0x180038726  mov     [rsp+0C8h+var_A8], r15d
0x18003872b  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038732  call    WPP_SF_sd
0x180038737  test    ebx, ebx
0x180038739  js      loc_180038B4E
0x18003873f  mov     [rsp+0C8h+var_70], rdi
0x180038744  jmp     short loc_180038753
0x180038746  mov     rax, [rsp+0C8h+arg_10]
0x18003874e  mov     [rsp+0C8h+var_70], rax
0x180038753  mov     eax, r14d
0x180038756  mov     edx, 0FFFFFFFFh
0x18003875b  lea     rcx, ds:0[rax*8]
0x180038763  cmp     rcx, rdx
0x180038766  ja      loc_180038B49
0x18003876c  lea     rbx, [rax+rax*2]
0x180038770  shl     rbx, 3
0x180038774  cmp     rbx, rdx
0x180038777  ja      loc_180038B49
0x18003877d  mov     r12d, ecx
0x180038780  xor     esi, esi
0x180038782  mov     ecx, ecx; cb
0x180038784  mov     [rsp+0C8h+Size], r12
0x180038789  call    cs:__imp_CoTaskMemAlloc
0x180038790  nop     dword ptr [rax+rax+00h]
0x180038795  mov     r15, rax
0x180038798  mov     ecx, ebx; cb
0x18003879a  mov     eax, ebx
0x18003879c  mov     [rsp+0C8h+var_60], rax
0x1800387a1  call    cs:__imp_CoTaskMemAlloc
0x1800387a8  nop     dword ptr [rax+rax+00h]
0x1800387ad  mov     ecx, r12d; cb
0x1800387b0  mov     [rsp+0C8h+var_68], rax
0x1800387b5  mov     r13, rax
0x1800387b8  call    cs:__imp_CoTaskMemAlloc
0x1800387bf  nop     dword ptr [rax+rax+00h]
0x1800387c4  mov     r12, rax
0x1800387c7  test    r15, r15
0x1800387ca  jz      loc_180038A3D
0x1800387d0  test    r13, r13
0x1800387d3  jz      loc_180038A3D
0x1800387d9  test    rax, rax
0x1800387dc  jz      loc_180038A3D
0x1800387e2  mov     r8, [rsp+0C8h+Size]; Size
0x1800387e7  xor     edx, edx; Val
0x1800387e9  mov     rcx, r15; void *
0x1800387ec  call    memset_0
0x1800387f1  mov     r8, [rsp+0C8h+var_60]; Size
0x1800387f6  xor     edx, edx; Val
0x1800387f8  mov     rcx, r13; void *
0x1800387fb  call    memset_0
0x180038800  mov     r8, [rsp+0C8h+Size]; Size
0x180038805  xor     edx, edx; Val
0x180038807  mov     rcx, r12; void *
0x18003880a  call    memset_0
0x18003880f  xor     ebx, ebx
0x180038811  cmp     esi, r14d
0x180038814  jnb     loc_180038A04
0x18003881a  mov     rax, [rsp+0C8h+var_70]
0x18003881f  mov     rcx, [rsp+0C8h+arg_0]; this
0x180038827  mov     r13d, esi
0x18003882a  inc     esi
0x18003882c  mov     edx, [rax+r13*4]; int
0x180038830  call    ?LookupVariableByDispID@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_STATE_VARIABLE@@J@Z; CUPnPAutomationProxy::LookupVariableByDispID(long)
0x180038835  mov     rbx, rax
0x180038838  test    rax, rax
0x18003883b  jz      loc_1800389FF
0x180038841  mov     rcx, [rax]; unsigned __int16 *
0x180038844  call    ?COMSzFromWsz@@YAPEAGPEBG@Z; COMSzFromWsz(ushort const *)
0x180038849  mov     [r15+r13*8], rax
0x18003884d  mov     rcx, [rbx+8]; unsigned __int16 *
0x180038851  call    ?COMSzFromWsz@@YAPEAGPEBG@Z; COMSzFromWsz(ushort const *)
0x180038856  xor     ecx, ecx
0x180038858  mov     [r12+r13*8], rax
0x18003885c  cmp     [r15+r13*8], rcx
0x180038860  jz      loc_1800389BC
0x180038866  test    rax, rax
0x180038869  jz      loc_1800389BC
0x18003886f  mov     dword ptr [rsp+0C8h+Size], ecx
0x180038873  lea     rax, ds:0[r13*2]
0x18003887b  mov     [rsp+0C8h+var_48], rcx
0x180038883  add     rax, r13
0x180038886  mov     rcx, [rsp+0C8h+var_68]
0x18003888b  xorps   xmm0, xmm0
0x18003888e  movdqu  [rsp+0C8h+var_58], xmm0
0x180038894  lea     rbx, [rcx+rax*8]
0x180038898  mov     rcx, rbx; pvarg
0x18003889b  call    cs:__imp_VariantInit
0x1800388a2  nop     dword ptr [rax+rax+00h]
0x1800388a7  mov     rax, [rsp+0C8h+arg_0]
0x1800388af  lea     rdx, [rsp+0C8h+Size]
0x1800388b4  mov     [rsp+0C8h+var_88], rdx
0x1800388b9  lea     r8, GUID_NULL
0x1800388c0  mov     [rsp+0C8h+var_90], 0
0x1800388c9  lea     rdx, [rsp+0C8h+var_58]
0x1800388ce  mov     [rsp+0C8h+var_98], rbx
0x1800388d3  mov     r9d, 800h
0x1800388d9  mov     rcx, [rax+58h]
0x1800388dd  mov     [rsp+0C8h+var_A0], rdx
0x1800388e2  mov     rdx, [rsp+0C8h+var_70]
0x1800388e7  mov     word ptr [rsp+0C8h+var_A8], 2
0x1800388ee  mov     rax, [rcx]
0x1800388f1  mov     edx, [rdx+r13*4]
0x1800388f5  mov     rax, [rax+30h]
0x1800388f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388fe  mov     ebx, eax
0x180038900  cmp     eax, 800706BAh
0x180038905  jz      short loc_180038919
0x180038907  add     eax, 7FF8F942h
0x18003890c  cmp     eax, 1
0x18003890f  jbe     short loc_180038919
0x180038911  cmp     ebx, 80010108h
0x180038917  jnz     short loc_18003895E
0x180038919  mov     rax, [rsp+0C8h+arg_0]
0x180038921  mov     rcx, [rax+58h]
0x180038925  test    rcx, rcx
0x180038928  jz      short loc_180038952
0x18003892a  mov     rax, [rcx]
0x18003892d  lea     r8, ?pBogusInterface@@3PEAXEA; void * pBogusInterface
0x180038934  lea     rdx, bogusIID
0x18003893b  mov     rax, [rax]
0x18003893e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038943  cmp     eax, 80004002h
0x180038948  jz      short loc_18003895E
0x18003894a  mov     rax, [rsp+0C8h+arg_0]
0x180038952  mov     rcx, [rax+88h]; unsigned __int16 *
0x180038959  call    ?HrUnregisterDeviceByUDN@@YAJPEAG@Z; HrUnregisterDeviceByUDN(ushort *)
0x18003895e  test    ebx, ebx
0x180038960  js      short loc_180038998
0x180038962  mov     rcx, cs:WPP_GLOBAL_Control
0x180038969  cmp     rcx, rbp
0x18003896c  jz      loc_1800389F5
0x180038972  test    byte ptr [rcx+1Ch], 40h
0x180038976  jz      short loc_1800389F5
0x180038978  mov     rax, [rsp+0C8h+var_70]
0x18003897d  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038984  mov     rcx, [rcx+10h]
0x180038988  mov     edx, 18h
0x18003898d  mov     r9d, [rax+r13*4]
0x180038991  call    WPP_SF_d
0x180038996  jmp     short loc_1800389F5
0x180038998  mov     rcx, cs:WPP_GLOBAL_Control
0x18003899f  cmp     rcx, rbp
0x1800389a2  jz      short loc_1800389F5
0x1800389a4  test    byte ptr [rcx+1Ch], 1
0x1800389a8  jz      short loc_1800389F5
0x1800389aa  mov     edx, 19h
0x1800389af  mov     [rsp+0C8h+var_A8], ebx
0x1800389b3  lea     r9, aCupnpautomatio_43; "CUPnPAutomationProxy::QueryStateVariabl"...
0x1800389ba  jmp     short loc_1800389E5
0x1800389bc  mov     eax, 8007000Eh
0x1800389c1  mov     ebx, eax
0x1800389c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800389ca  cmp     rcx, rbp
0x1800389cd  jz      short loc_1800389F5
0x1800389cf  test    byte ptr [rcx+1Ch], 1
0x1800389d3  jz      short loc_1800389F5
0x1800389d5  mov     edx, 1Ah
0x1800389da  mov     [rsp+0C8h+var_A8], eax
0x1800389de  lea     r9, aCupnpautomatio_19; "CUPnPAutomationProxy::QueryStateVariabl"...
0x1800389e5  mov     rcx, [rcx+10h]
0x1800389e9  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800389f0  call    WPP_SF_sd
0x1800389f5  test    ebx, ebx
0x1800389f7  jns     loc_180038811
0x1800389fd  jmp     short loc_180038A04
0x1800389ff  mov     ebx, 80020003h
0x180038a04  test    ebx, ebx
0x180038a06  js      short loc_180038A82
0x180038a08  mov     rax, [rsp+0C8h+arg_18]
0x180038a10  mov     rcx, [rsp+0C8h+arg_28]
0x180038a18  mov     [rax], esi
0x180038a1a  mov     rax, [rsp+0C8h+arg_20]
0x180038a22  mov     [rax], r15
0x180038a25  mov     rax, [rsp+0C8h+var_68]
0x180038a2a  mov     [rcx], rax
0x180038a2d  mov     rax, [rsp+0C8h+arg_30]
0x180038a35  mov     [rax], r12
0x180038a38  jmp     loc_180038B4E
0x180038a3d  mov     eax, 8007000Eh
0x180038a42  mov     ebx, eax
0x180038a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a4b  cmp     rcx, rbp
0x180038a4e  jz      short loc_180038A7D
0x180038a50  test    byte ptr [rcx+1Ch], 1
0x180038a54  jz      short loc_180038A7D
0x180038a56  mov     rcx, [rcx+10h]
0x180038a5a  lea     r9, aCupnpautomatio_22; "CUPnPAutomationProxy::QueryStateVariabl"...
0x180038a61  mov     edx, 1Bh
0x180038a66  mov     [rsp+0C8h+var_A8], eax
0x180038a6a  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038a71  call    WPP_SF_sd
0x180038a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a7d  test    r15, r15
0x180038a80  jz      short loc_180038AC9
0x180038a82  xor     r14d, r14d
0x180038a85  test    esi, esi
0x180038a87  jz      short loc_180038AAE
0x180038a89  mov     rcx, [r15+r14*8]; pv
0x180038a8d  test    rcx, rcx
0x180038a90  jz      short loc_180038AA6
0x180038a92  call    cs:__imp_CoTaskMemFree
0x180038a99  nop     dword ptr [rax+rax+00h]
0x180038a9e  mov     qword ptr [r15+r14*8], 0
  ... truncated ...
```
