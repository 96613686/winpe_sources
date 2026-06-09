# DLNACommon::IsWakeOnLANEnabled(void)

- ea: `0x1400981d4`
- end: `0x1400988a9`
- name: `?IsWakeOnLANEnabled@DLNACommon@@YAHXZ`
- size: `1749`
- prototype: `__int64 __fastcall(DLNACommon *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14004f2e0`

## callees

- `0x1400028cc`
- `0x14003ca4c`
- `0x14003f17c`
- `0x140047798`
- `0x14004a500`
- `0x14004a834`
- `0x14005480c`
- `0x1400981d4`
- `0x1400988b0`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14009829c`
- `OLEAUT32!__imp_SysAllocString` at `0x140098418`
- `OLEAUT32!__imp_SysAllocString` at `0x140098428`
- `OLEAUT32!__imp_SysAllocString` at `0x14009829c`
- `OLEAUT32!__imp_SysAllocString` at `0x140098418`
- `OLEAUT32!__imp_SysAllocString` at `0x140098428`
- `OLEAUT32!__imp_SysFreeString` at `0x14009837c`
- `OLEAUT32!__imp_SysFreeString` at `0x140098503`
- `OLEAUT32!__imp_SysFreeString` at `0x14009850c`
- `OLEAUT32!__imp_SysFreeString` at `0x14009837c`
- `OLEAUT32!__imp_SysFreeString` at `0x140098503`
- `OLEAUT32!__imp_SysFreeString` at `0x14009850c`
- `OLEAUT32!__imp_VariantInit` at `0x14009857c`
- `OLEAUT32!__imp_VariantInit` at `0x140098671`
- `OLEAUT32!__imp_VariantInit` at `0x140098767`
- `OLEAUT32!__imp_VariantInit` at `0x14009857c`
- `OLEAUT32!__imp_VariantInit` at `0x140098671`
- `OLEAUT32!__imp_VariantInit` at `0x140098767`
- `OLEAUT32!__imp_VariantClear` at `0x140098801`
- `OLEAUT32!__imp_VariantClear` at `0x140098814`
- `OLEAUT32!__imp_VariantClear` at `0x140098827`
- `OLEAUT32!__imp_VariantClear` at `0x140098801`
- `OLEAUT32!__imp_VariantClear` at `0x140098814`
- `OLEAUT32!__imp_VariantClear` at `0x140098827`
- `ole32!CoCreateInstance` at `0x140098224`
- `ole32!CoCreateInstance` at `0x140098224`
- `ole32!CoSetProxyBlanket` at `0x1400983b9`
- `ole32!CoSetProxyBlanket` at `0x1400983b9`

## pseudocode

```c
__int64 __fastcall DLNACommon::IsWakeOnLANEnabled(DLNACommon *this)
{
  unsigned int v1; // r15d
  HRESULT v2; // eax
  int v3; // ebx
  PVOID *v4; // r10
  OLECHAR *v5; // rsi
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // rbx
  int v8; // eax
  HRESULT v9; // eax
  OLECHAR *v10; // r14
  BSTR v11; // rax
  OLECHAR *v12; // rsi
  IUnknown *v13; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  int v15; // eax
  int v16; // eax
  int v17; // edi
  int v18; // eax
  int v19; // edi
  int v20; // eax
  int v21; // edi
  int v22; // eax
  int v23; // edi
  int v24; // eax
  int v25; // edi
  __int64 v27; // [rsp+50h] [rbp-39h] BYREF
  __int64 v28; // [rsp+58h] [rbp-31h] BYREF
  __int64 v29; // [rsp+60h] [rbp-29h] BYREF
  VARIANTARG v30; // [rsp+68h] [rbp-21h] BYREF
  VARIANTARG v31; // [rsp+80h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp+Fh] BYREF
  int v33; // [rsp+F0h] [rbp+67h] BYREF
  IUnknown *pProxy; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v35; // [rsp+100h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = 0;
  ppv = 0;
  pProxy = 0;
  v35 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v2 = CoCreateInstance(
         &GUID_4590f811_1d3a_11d0_891f_00aa004b2e24,
         0,
         1u,
         &GUID_dc12a687_737f_11cf_884d_00aa004b2e24,
         &ppv);
  v3 = v2;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v2 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
      (unsigned int)v2,
      ppv);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 >= 0 )
  {
    v5 = SysAllocString(L"ROOT\\WMI");
    if ( v5 )
    {
      v6 = ppv;
      v7 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
      v8 = v7(v6, v5, 0, 0, 0, 0, 0, 0, &pProxy);
      v3 = v8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
          (unsigned int)v8,
          pProxy);
      }
      SysFreeString(v5);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( v3 < 0 )
        goto LABEL_33;
      v9 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 3u, 3u, 0, 0);
      v3 = v9;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v9 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
          (unsigned int)v9,
          pProxy);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 < 0 )
        goto LABEL_33;
      v10 = SysAllocString(L"WQL");
      v11 = SysAllocString(L"SELECT * FROM MSNdis_PMCapabilities");
      v12 = v11;
      if ( v10 && v11 )
      {
        v13 = pProxy;
        Release = pProxy->lpVtbl[6].Release;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        v3 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))Release)(
               v13,
               v10,
               v12,
               48,
               0,
               &v35);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v3 >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_dSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v10, (__int64)v12, v35);
        }
      }
      else
      {
        v3 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids);
        }
      }
      SysFreeString(v10);
      SysFreeString(v12);
    }
    else
    {
      v3 = -2147024882;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_33;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_33:
  while ( v3 >= 0 && !v1 )
  {
    v29 = 0;
    v33 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v35 + 32LL))(
            v35,
            0xFFFFFFFFLL,
            1,
            &v29,
            &v33);
    v3 = v15;
    if ( !v33 || v15 < 0 )
    {
      ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v29);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      break;
    }
    VariantInit(&pvarg);
    v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v29 + 32LL))(
            v29,
            L"PMCapabilitiesParam",
            0,
            &pvarg,
            0,
            0);
    v17 = v16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v16 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
        (unsigned int)v16);
    }
    if ( v17 >= 0 && pvarg.vt == 13 )
    {
      v28 = 0;
      v18 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
              pvarg.llVal,
              &GUID_dc12a681_737f_11cf_884d_00aa004b2e24,
              &v28);
      v19 = v18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v18 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
          (unsigned int)v18,
          v28);
      }
      if ( v19 >= 0 )
      {
        VariantInit(&v31);
        v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v28 + 32LL))(
                v28,
                L"WakeOnMagicPacket",
                0,
                &v31,
                0,
                0);
        v21 = v20;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v20 >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
            (unsigned int)v20);
        }
        if ( v21 >= 0 && v31.vt == 13 )
        {
          v27 = 0;
          v22 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))v31.llVal)(
                  v31.llVal,
                  &GUID_dc12a681_737f_11cf_884d_00aa004b2e24,
                  &v27);
          v23 = v22;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v22 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
              (unsigned int)v22,
              v27);
          }
          if ( v23 >= 0 )
          {
            VariantInit(&v30);
            v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v27 + 32LL))(
                    v27,
                    L"NdisPMCapabilityState",
                    0,
                    &v30,
                    0,
                    0);
            v25 = v24;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v24 >> 31) & 0xFFFFFFFD) + 5 )
            {
              WPP_SF_DDd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids,
                (unsigned int)v24,
                v30.vt,
                v30.lVal);
            }
            if ( v25 >= 0 && v30.vt == 3 && v30.lVal == 2 )
              v1 = 1;
            VariantClear(&v30);
          }
          ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v27);
        }
        VariantClear(&v31);
      }
      ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v28);
    }
    VariantClear(&pvarg);
    ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v29);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_d(v4[2], 21, &WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids, v1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v1;
}

```

## disassembly

```asm
0x1400981d4  push    rbp
0x1400981d6  push    rbx
0x1400981d7  push    rsi
0x1400981d8  push    rdi
0x1400981d9  push    r12
0x1400981db  push    r14
0x1400981dd  push    r15
0x1400981df  lea     rbp, [rsp-27h]
0x1400981e4  sub     rsp, 0B0h
0x1400981eb  xor     r12d, r12d
0x1400981ee  lea     rcx, [rbp+57h+arg_18]
0x1400981f2  mov     r15d, r12d
0x1400981f5  mov     [rbp+57h+arg_18], r12
0x1400981f9  mov     [rbp+57h+pProxy], r12
0x1400981fd  mov     [rbp+57h+arg_10], r12
0x140098201  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140098206  lea     rax, [rbp+57h+arg_18]
0x14009820a  xor     edx, edx; pUnkOuter
0x14009820c  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x140098213  mov     [rsp+0E0h+ppv], rax; ppv
0x140098218  lea     r8d, [r12+1]; dwClsContext
0x14009821d  lea     rcx, _GUID_4590f811_1d3a_11d0_891f_00aa004b2e24; rclsid
0x140098224  call    cs:__imp_CoCreateInstance
0x14009822a  mov     ebx, eax
0x14009822c  mov     r10, cs:WPP_GLOBAL_Control
0x140098233  lea     rdi, WPP_GLOBAL_Control
0x14009823a  lea     r14, WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids
0x140098241  cmp     r10, rdi
0x140098244  jz      short loc_140098285
0x140098246  test    byte ptr [r10+1Ch], 20h
0x14009824b  jz      short loc_140098285
0x14009824d  mov     edx, eax
0x14009824f  movzx   eax, byte ptr [r10+19h]
0x140098254  sar     edx, 1Fh
0x140098257  and     edx, 0FFFFFFFDh
0x14009825a  add     edx, 5
0x14009825d  cmp     eax, edx
0x14009825f  jb      short loc_140098285
0x140098261  mov     rax, [rbp+57h+arg_18]
0x140098265  lea     edx, [r12+0Ah]
0x14009826a  mov     rcx, [r10+10h]
0x14009826e  mov     r9d, ebx
0x140098271  mov     r8, r14
0x140098274  mov     [rsp+0E0h+ppv], rax
0x140098279  call    WPP_SF_dq
0x14009827e  mov     r10, cs:WPP_GLOBAL_Control
0x140098285  mov     eax, 3
0x14009828a  lea     esi, [rax+0Ah]
0x14009828d  test    ebx, ebx
0x14009828f  js      loc_140098520
0x140098295  lea     rcx, aRootWmi; "ROOT\\WMI"
0x14009829c  call    cs:__imp_SysAllocString
0x1400982a2  mov     rsi, rax
0x1400982a5  test    rax, rax
0x1400982a8  jnz     short loc_1400982E9
0x1400982aa  mov     ebx, 8007000Eh
0x1400982af  mov     r10, cs:WPP_GLOBAL_Control
0x1400982b6  cmp     r10, rdi
0x1400982b9  jz      loc_140098520
0x1400982bf  test    byte ptr [r10+1Ch], 20h
0x1400982c4  jz      loc_140098520
0x1400982ca  cmp     byte ptr [r10+19h], 4
0x1400982cf  jb      loc_140098520
0x1400982d5  mov     rcx, [r10+10h]
0x1400982d9  lea     edx, [rax+0Bh]
0x1400982dc  mov     r8, r14
0x1400982df  call    WPP_SF_
0x1400982e4  jmp     loc_140098519
0x1400982e9  mov     rdi, [rbp+57h+arg_18]
0x1400982ed  lea     rcx, [rbp+57h+pProxy]
0x1400982f1  mov     rax, [rdi]
0x1400982f4  mov     rbx, [rax+18h]
0x1400982f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400982fd  lea     rax, [rbp+57h+pProxy]
0x140098301  xor     r9d, r9d
0x140098304  mov     [rsp+0E0h+var_A0], rax
0x140098309  xor     r8d, r8d
0x14009830c  mov     qword ptr [rsp+0E0h+dwCapabilities], r12
0x140098311  mov     rdx, rsi
0x140098314  mov     [rsp+0E0h+pAuthInfo], r12
0x140098319  mov     rcx, rdi
0x14009831c  mov     [rsp+0E0h+dwImpLevel], r12d
0x140098321  mov     rax, rbx
0x140098324  mov     [rsp+0E0h+ppv], r12
0x140098329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009832e  mov     ebx, eax
0x140098330  mov     rcx, cs:WPP_GLOBAL_Control
0x140098337  lea     rdi, WPP_GLOBAL_Control
0x14009833e  cmp     rcx, rdi
0x140098341  jz      short loc_140098379
0x140098343  test    byte ptr [rcx+1Ch], 20h
0x140098347  jz      short loc_140098379
0x140098349  mov     edx, eax
0x14009834b  movzx   eax, byte ptr [rcx+19h]
0x14009834f  sar     edx, 1Fh
0x140098352  and     edx, 0FFFFFFFDh
0x140098355  add     edx, 5
0x140098358  cmp     eax, edx
0x14009835a  jb      short loc_140098379
0x14009835c  mov     rax, [rbp+57h+pProxy]
0x140098360  mov     edx, 0Ch
0x140098365  mov     rcx, [rcx+10h]
0x140098369  mov     r9d, ebx
0x14009836c  mov     r8, r14
0x14009836f  mov     [rsp+0E0h+ppv], rax
0x140098374  call    WPP_SF_dq
0x140098379  mov     rcx, rsi; bstrString
0x14009837c  call    cs:__imp_SysFreeString
0x140098382  mov     r10, cs:WPP_GLOBAL_Control
0x140098389  mov     esi, 0Dh
0x14009838e  lea     eax, [rsi-0Ah]
0x140098391  test    ebx, ebx
0x140098393  js      loc_140098520
0x140098399  mov     rcx, [rbp+57h+pProxy]; pProxy
0x14009839d  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1400983a1  mov     [rsp+0E0h+dwCapabilities], r12d; dwCapabilities
0x1400983a6  xor     r8d, r8d; dwAuthzSvc
0x1400983a9  mov     [rsp+0E0h+pAuthInfo], r12; pAuthInfo
0x1400983ae  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1400983b1  mov     [rsp+0E0h+dwImpLevel], eax; dwImpLevel
0x1400983b5  mov     dword ptr [rsp+0E0h+ppv], eax; dwAuthnLevel
0x1400983b9  call    cs:__imp_CoSetProxyBlanket
0x1400983bf  mov     ebx, eax
0x1400983c1  mov     r10, cs:WPP_GLOBAL_Control
0x1400983c8  cmp     r10, rdi
0x1400983cb  jz      short loc_140098409
0x1400983cd  test    byte ptr [r10+1Ch], 20h
0x1400983d2  jz      short loc_140098409
0x1400983d4  mov     ecx, eax
0x1400983d6  movzx   eax, byte ptr [r10+19h]
0x1400983db  sar     ecx, 1Fh
0x1400983de  and     ecx, 0FFFFFFFDh
0x1400983e1  add     ecx, 5
0x1400983e4  cmp     eax, ecx
0x1400983e6  jb      short loc_140098409
0x1400983e8  mov     rax, [rbp+57h+pProxy]
0x1400983ec  mov     edx, esi
0x1400983ee  mov     rcx, [r10+10h]
0x1400983f2  mov     r9d, ebx
0x1400983f5  mov     r8, r14
0x1400983f8  mov     [rsp+0E0h+ppv], rax
0x1400983fd  call    WPP_SF_dq
0x140098402  mov     r10, cs:WPP_GLOBAL_Control
0x140098409  test    ebx, ebx
0x14009840b  js      loc_140098520
0x140098411  lea     rcx, aWql; "WQL"
0x140098418  call    cs:__imp_SysAllocString
0x14009841e  lea     rcx, aSelectFromMsnd; "SELECT * FROM MSNdis_PMCapabilities"
0x140098425  mov     r14, rax
0x140098428  call    cs:__imp_SysAllocString
0x14009842e  mov     rsi, rax
0x140098431  test    r14, r14
0x140098434  jz      loc_1400984CE
0x14009843a  test    rax, rax
0x14009843d  jz      loc_1400984CE
0x140098443  mov     rdi, [rbp+57h+pProxy]
0x140098447  lea     rcx, [rbp+57h+arg_10]
0x14009844b  mov     rax, [rdi]
0x14009844e  mov     rbx, [rax+0A0h]
0x140098455  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14009845a  lea     rax, [rbp+57h+arg_10]
0x14009845e  mov     r9d, 30h ; '0'
0x140098464  mov     qword ptr [rsp+0E0h+dwImpLevel], rax
0x140098469  mov     r8, rsi
0x14009846c  mov     rax, rbx
0x14009846f  mov     [rsp+0E0h+ppv], r12
0x140098474  mov     rdx, r14
0x140098477  mov     rcx, rdi
0x14009847a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009847f  mov     ebx, eax
0x140098481  mov     rcx, cs:WPP_GLOBAL_Control
0x140098488  lea     rax, WPP_GLOBAL_Control
0x14009848f  cmp     rcx, rax
0x140098492  jz      short loc_140098500
0x140098494  test    byte ptr [rcx+1Ch], 20h
0x140098498  jz      short loc_140098500
0x14009849a  movzx   eax, byte ptr [rcx+19h]
0x14009849e  mov     edx, ebx
0x1400984a0  sar     edx, 1Fh
0x1400984a3  and     edx, 0FFFFFFFDh
0x1400984a6  add     edx, 5
0x1400984a9  cmp     eax, edx
0x1400984ab  jb      short loc_140098500
0x1400984ad  mov     rax, [rbp+57h+arg_10]
0x1400984b1  mov     r9d, ebx
0x1400984b4  mov     rcx, [rcx+10h]; LoggerHandle
0x1400984b8  mov     [rsp+0E0h+pAuthInfo], rax; char
0x1400984bd  mov     qword ptr [rsp+0E0h+dwImpLevel], rsi; __int64
0x1400984c2  mov     [rsp+0E0h+ppv], r14; __int64
0x1400984c7  call    WPP_SF_dSSq
0x1400984cc  jmp     short loc_140098500
0x1400984ce  mov     ebx, 8007000Eh
0x1400984d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400984da  cmp     rcx, rdi
0x1400984dd  jz      short loc_140098500
0x1400984df  test    byte ptr [rcx+1Ch], 20h
0x1400984e3  jz      short loc_140098500
0x1400984e5  cmp     byte ptr [rcx+19h], 4
0x1400984e9  jb      short loc_140098500
0x1400984eb  mov     rcx, [rcx+10h]
0x1400984ef  lea     r8, WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids
0x1400984f6  mov     edx, 0Eh
0x1400984fb  call    WPP_SF_
0x140098500  mov     rcx, r14; bstrString
0x140098503  call    cs:__imp_SysFreeString
0x140098509  mov     rcx, rsi; bstrString
0x14009850c  call    cs:__imp_SysFreeString
0x140098512  lea     r14, WPP_ac3db4e4b2a23bcd2b19abe0af0f9a59_Traceguids
0x140098519  mov     r10, cs:WPP_GLOBAL_Control
0x140098520  lea     rsi, WPP_GLOBAL_Control
0x140098527  test    ebx, ebx
0x140098529  js      loc_140098852
0x14009852f  test    r15d, r15d
0x140098532  jnz     loc_140098852
0x140098538  mov     rcx, [rbp+57h+arg_10]
0x14009853c  lea     rdx, [rbp+57h+arg_0]
0x140098540  mov     [rbp+57h+var_80], r12
0x140098544  lea     r9, [rbp+57h+var_80]
0x140098548  mov     [rbp+57h+arg_0], r12d
0x14009854c  lea     r8d, [r15+1]
0x140098550  mov     [rsp+0E0h+ppv], rdx
0x140098555  or      edx, 0FFFFFFFFh
0x140098558  mov     rax, [rcx]
0x14009855b  mov     rax, [rax+20h]
0x14009855f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098564  mov     ebx, eax
0x140098566  cmp     [rbp+57h+arg_0], r12d
0x14009856a  jz      loc_140098842
0x140098570  test    eax, eax
0x140098572  js      loc_140098842
0x140098578  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14009857c  call    cs:__imp_VariantInit
0x140098582  mov     rcx, [rbp+57h+var_80]
0x140098586  lea     r9, [rbp+57h+pvarg]
0x14009858a  mov     qword ptr [rsp+0E0h+dwImpLevel], r12
0x14009858f  lea     rdx, aPmcapabilities; "PMCapabilitiesParam"
0x140098596  xor     r8d, r8d
0x140098599  mov     [rsp+0E0h+ppv], r12
0x14009859e  mov     rax, [rcx]
0x1400985a1  mov     rax, [rax+20h]
0x1400985a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400985aa  mov     edi, eax
0x1400985ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400985b3  cmp     rcx, rsi
0x1400985b6  jz      short loc_1400985EC
0x1400985b8  test    byte ptr [rcx+1Ch], 20h
0x1400985bc  jz      short loc_1400985EC
0x1400985be  mov     edx, eax
0x1400985c0  movzx   eax, byte ptr [rcx+19h]
0x1400985c4  sar     edx, 1Fh
0x1400985c7  and     edx, 0FFFFFFFDh
0x1400985ca  add     edx, 5
0x1400985cd  cmp     eax, edx
0x1400985cf  jb      short loc_1400985EC
0x1400985d1  movzx   eax, word ptr [rbp+57h+pvarg]
0x1400985d5  lea     edx, [r15+10h]
0x1400985d9  mov     rcx, [rcx+10h]
0x1400985dd  mov     r9d, edi
0x1400985e0  mov     r8, r14
0x1400985e3  mov     dword ptr [rsp+0E0h+ppv], eax
0x1400985e7  call    WPP_SF_Dd
0x1400985ec  test    edi, edi
0x1400985ee  js      loc_140098823
0x1400985f4  mov     eax, 0Dh
0x1400985f9  cmp     ax, word ptr [rbp+57h+pvarg]
0x1400985fd  jnz     loc_140098823
0x140098603  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x140098607  lea     r8, [rbp+57h+var_88]
0x14009860b  mov     [rbp+57h+var_88], r12
0x14009860f  lea     rdx, _GUID_dc12a681_737f_11cf_884d_00aa004b2e24
0x140098616  mov     rax, [rcx]
0x140098619  mov     rax, [rax]
0x14009861c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098621  mov     edi, eax
0x140098623  mov     rcx, cs:WPP_GLOBAL_Control
0x14009862a  cmp     rcx, rsi
0x14009862d  jz      short loc_140098665
0x14009862f  test    byte ptr [rcx+1Ch], 20h
0x140098633  jz      short loc_140098665
0x140098635  mov     edx, eax
0x140098637  movzx   eax, byte ptr [rcx+19h]
0x14009863b  sar     edx, 1Fh
0x14009863e  and     edx, 0FFFFFFFDh
0x140098641  add     edx, 5
0x140098644  cmp     eax, edx
0x140098646  jb      short loc_140098665
0x140098648  mov     rax, [rbp+57h+var_88]
0x14009864c  mov     edx, 11h
0x140098651  mov     rcx, [rcx+10h]
0x140098655  mov     r9d, edi
0x140098658  mov     r8, r14
0x14009865b  mov     [rsp+0E0h+ppv], rax
0x140098660  call    WPP_SF_dq
0x140098665  test    edi, edi
0x140098667  js      loc_14009881A
0x14009866d  lea     rcx, [rbp+57h+var_60]; pvarg
0x140098671  call    cs:__imp_VariantInit
0x140098677  mov     rcx, [rbp+57h+var_88]
0x14009867b  lea     r9, [rbp+57h+var_60]
0x14009867f  mov     qword ptr [rsp+0E0h+dwImpLevel], r12
  ... truncated ...
```
