# PollingAppDataList::GetPollingDataList(IWpnSettingsEndpoint *,__MIDL___MIDL_itf_wpnplatform_0000_0036_0001 * *)

- ea: `0x1800ede18`
- end: `0x1800ee38c`
- name: `?GetPollingDataList@PollingAppDataList@@QEAAJPEAUIWpnSettingsEndpoint@@PEAPEAU__MIDL___MIDL_itf_wpnplatform_0000_0036_0001@@@Z`
- size: `1396`
- prototype: `__int64 __fastcall(PollingAppDataList *__hidden this, struct IWpnSettingsEndpoint *, struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ed99c`

## callees

- `0x180004e38`
- `0x1800299c0`
- `0x18002ee38`
- `0x180062bf0`
- `0x1800af0a4`
- `0x1800df41c`
- `0x1800ede18`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee340`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee340`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800edf1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800edf87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800edf1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800edf87`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PollingAppDataList::GetPollingDataList(
        PollingAppDataList *this,
        struct IWpnSettingsEndpoint *a2,
        struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 **a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 *v10; // r14
  int v11; // eax
  struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 *v12; // rsi
  LPVOID v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int i; // r12d
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, __int64 *); // rbx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // r9
  __int64 j; // r8
  void *v28; // rcx
  int v30; // [rsp+20h] [rbp-38h]
  int v31; // [rsp+30h] [rbp-28h] BYREF
  __int64 v32; // [rsp+38h] [rbp-20h] BYREF
  __int64 v33; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v34[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  SIZE_T cb; // [rsp+A0h] [rbp+48h] BYREF
  int v37; // [rsp+A8h] [rbp+50h] BYREF
  struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 **v38; // [rsp+B0h] [rbp+58h]
  int v39; // [rsp+B8h] [rbp+60h] BYREF

  v38 = a3;
  v34[0] = a2;
  Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef(v34);
  v33 = 0;
  v32 = 0;
  *a3 = 0;
  cb = 0;
  if ( *((_DWORD *)this + 4) )
  {
    v10 = *(__int64 **)this;
    v11 = ULongLongMult(*((unsigned int *)this + 4), 0x70u, &cb);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v12 = (struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 *)CoTaskMemAlloc(0x10u);
      if ( v12 )
      {
        *(_DWORD *)v12 = *((_DWORD *)this + 4);
        *((_QWORD *)v12 + 1) = 0;
        v13 = CoTaskMemAlloc(cb);
        *((_QWORD *)v12 + 1) = v13;
        if ( v13 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= *((_DWORD *)this + 4) )
            {
              *v38 = v12;
              goto LABEL_53;
            }
            LODWORD(cb) = 0;
            v18 = (*(__int64 (__fastcall **)(struct IWpnSettingsEndpoint *, __int64, __int64, SIZE_T *))(*(_QWORD *)a2 + 24LL))(
                    a2,
                    v10[2],
                    128,
                    &cb);
            v6 = v18;
            if ( v18 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x893,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                (const char *)(unsigned int)v18,
                v30);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v15 = 115;
                goto LABEL_47;
              }
              goto LABEL_49;
            }
            v19 = Microsoft::WRL::ComPtr<IWpnSettingsEndpoint>::As<IWpnSettingsEndpoint2>(v34, &v33);
            v6 = v19;
            if ( v19 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x896,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                (const char *)(unsigned int)v19,
                v30);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v15 = 116;
                goto LABEL_47;
              }
              goto LABEL_49;
            }
            v20 = v33;
            v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 24LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
            v22 = v21(v20, v10[2], &v32);
            v6 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x899,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                (const char *)(unsigned int)v22,
                v30);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v15 = 117;
                goto LABEL_47;
              }
              goto LABEL_49;
            }
            v37 = 0;
            v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v32 + 32LL))(
                    v32,
                    L"s:cycle:medium",
                    &v37);
            v6 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x89D,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                (const char *)(unsigned int)v23,
                v30);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v15 = 118;
                goto LABEL_47;
              }
              goto LABEL_49;
            }
            v39 = 0;
            v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v32 + 32LL))(
                    v32,
                    L"s:cycle:wide",
                    &v39);
            v6 = v24;
            if ( v24 < 0 )
              break;
            v31 = 0;
            v25 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v32 + 32LL))(
                    v32,
                    L"s:cycle:large",
                    &v31);
            v6 = v25;
            if ( v25 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8A5,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                (const char *)(unsigned int)v25,
                v30);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v15 = 120;
LABEL_47:
                v16 = v6;
                goto LABEL_48;
              }
              goto LABEL_49;
            }
            v26 = 112LL * i;
            *(_DWORD *)(v26 + *((_QWORD *)v12 + 1) + 8) = cb;
            *(_DWORD *)(v26 + *((_QWORD *)v12 + 1) + 12) = v37;
            *(_DWORD *)(v26 + *((_QWORD *)v12 + 1) + 16) = v39;
            *(_DWORD *)(v26 + *((_QWORD *)v12 + 1) + 20) = v31;
            *(_QWORD *)(v26 + *((_QWORD *)v12 + 1)) = v10[2];
            v10[2] = 0;
            *(_QWORD *)(v26 + *((_QWORD *)v12 + 1) + 72) = v10[11];
            *(_DWORD *)(v26 + *((_QWORD *)v12 + 1) + 80) = *((_DWORD *)v10 + 24);
            *(_DWORD *)(v26 + *((_QWORD *)v12 + 1) + 24) = *((_DWORD *)v10 + 10);
            for ( j = 0; j != 5; ++j )
            {
              *(_QWORD *)(112LL * i + 32 + 8 * j + *((_QWORD *)v12 + 1)) = v10[j + 6];
              v10[j + 6] = 0;
            }
            *(_QWORD *)(*((_QWORD *)v12 + 1) + v26 + 96) = v10[14];
            *(_DWORD *)(*((_QWORD *)v12 + 1) + v26 + 104) = *((_DWORD *)v10 + 30);
            *(_QWORD *)(*((_QWORD *)v12 + 1) + v26 + 88) = v10[13];
            v10[13] = 0;
            v10 = (__int64 *)*v10;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8A1,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
            (const char *)(unsigned int)v24,
            v30);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v15 = 119;
            goto LABEL_47;
          }
        }
        else
        {
          v6 = -2147024882;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x885,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
            (const char *)0x8007000ELL,
            v30);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v15 = 114;
            v16 = 2147942414LL;
LABEL_48:
            WPP_SF_d(v14[2], v15, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v16);
          }
        }
LABEL_49:
        v28 = (void *)*((_QWORD *)v12 + 1);
        if ( v28 )
        {
          CoTaskMemFree(v28);
          *((_QWORD *)v12 + 1) = 0;
        }
        CoTaskMemFree(v12);
      }
      else
      {
        v6 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x87F,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
          (const char *)0x8007000ELL,
          v30);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v8 = 113;
          v9 = 2147942414LL;
          goto LABEL_5;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x87A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
        (const char *)(unsigned int)v11,
        v30);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 112;
        v9 = v6;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v6 = -2147023728;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x873,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
      (const char *)0x80070490LL,
      v30);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v8 = 111;
      v9 = 2147943568LL;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v9);
    }
  }
LABEL_53:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
  return v6;
}

```

## disassembly

```asm
0x1800ede18  mov     [rsp-40h+arg_10], r8
0x1800ede1d  push    rbp
0x1800ede1e  push    rbx
0x1800ede1f  push    rsi
0x1800ede20  push    rdi
0x1800ede21  push    r12
0x1800ede23  push    r13
0x1800ede25  push    r14
0x1800ede27  push    r15
0x1800ede29  mov     rbp, rsp
0x1800ede2c  sub     rsp, 58h
0x1800ede30  mov     rdi, r8
0x1800ede33  mov     r13, rdx
0x1800ede36  mov     r15, rcx
0x1800ede39  mov     [rbp+var_10], rdx
0x1800ede3d  lea     rcx, [rbp+var_10]
0x1800ede41  call    ?InternalAddRef@?$ComPtr@UIGlobalInterfaceTable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef(void)
0x1800ede46  nop
0x1800ede47  xor     eax, eax
0x1800ede49  mov     [rbp+var_18], rax
0x1800ede4d  mov     [rbp+var_20], rax
0x1800ede51  mov     [rdi], rax
0x1800ede54  xor     edi, edi
0x1800ede56  mov     [rbp+cb], rdi
0x1800ede5a  cmp     [r15+10h], edi
0x1800ede5e  jnz     short loc_1800EDEBC
0x1800ede60  mov     ebx, 80070490h
0x1800ede65  mov     rcx, [rbp+40h]; this
0x1800ede69  mov     r9d, ebx; char *
0x1800ede6c  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ede73  mov     edx, 873h; void *
0x1800ede78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ede7d  lea     rax, WPP_GLOBAL_Control
0x1800ede84  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ede8b  cmp     rcx, rax
0x1800ede8e  jz      loc_1800EE35C
0x1800ede94  test    byte ptr [rcx+1Ch], 80h
0x1800ede98  jz      loc_1800EE35C
0x1800ede9e  lea     edx, [rdi+6Fh]
0x1800edea1  mov     r9d, 80070490h
0x1800edea7  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800edeae  mov     rcx, [rcx+10h]
0x1800edeb2  call    WPP_SF_d
0x1800edeb7  jmp     loc_1800EE35C
0x1800edebc  mov     r14, [r15]
0x1800edebf  mov     ecx, [r15+10h]; unsigned __int64
0x1800edec3  lea     r8, [rbp+cb]; unsigned __int64 *
0x1800edec7  mov     esi, 70h ; 'p'
0x1800edecc  mov     edx, esi; unsigned __int64
0x1800edece  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800eded3  mov     ebx, eax
0x1800eded5  test    eax, eax
0x1800eded7  jns     short loc_1800EDF19
0x1800eded9  mov     rcx, [rbp+40h]; this
0x1800ededd  mov     r9d, eax; char *
0x1800edee0  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edee7  mov     edx, 87Ah; void *
0x1800edeec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edef1  lea     rax, WPP_GLOBAL_Control
0x1800edef8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edeff  cmp     rcx, rax
0x1800edf02  jz      loc_1800EE35C
0x1800edf08  test    byte ptr [rcx+1Ch], 80h
0x1800edf0c  jz      loc_1800EE35C
0x1800edf12  mov     edx, esi
0x1800edf14  mov     r9d, ebx
0x1800edf17  jmp     short loc_1800EDEA7
0x1800edf19  mov     ecx, 10h; cb
0x1800edf1e  call    cs:__imp_CoTaskMemAlloc
0x1800edf24  mov     rsi, rax
0x1800edf27  test    rax, rax
0x1800edf2a  jnz     short loc_1800EDF79
0x1800edf2c  mov     r9d, 8007000Eh; char *
0x1800edf32  mov     ebx, r9d
0x1800edf35  mov     rcx, [rbp+40h]; this
0x1800edf39  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edf40  mov     edx, 87Fh; void *
0x1800edf45  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edf4a  lea     rax, WPP_GLOBAL_Control
0x1800edf51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edf58  cmp     rcx, rax
0x1800edf5b  jz      loc_1800EE35C
0x1800edf61  test    byte ptr [rcx+1Ch], 80h
0x1800edf65  jz      loc_1800EE35C
0x1800edf6b  lea     edx, [rsi+71h]
0x1800edf6e  mov     r9d, 8007000Eh
0x1800edf74  jmp     loc_1800EDEA7
0x1800edf79  mov     eax, [r15+10h]
0x1800edf7d  mov     [rsi], eax
0x1800edf7f  mov     [rsi+8], rdi
0x1800edf83  mov     rcx, [rbp+cb]; cb
0x1800edf87  call    cs:__imp_CoTaskMemAlloc
0x1800edf8d  mov     [rsi+8], rax
0x1800edf91  test    rax, rax
0x1800edf94  jnz     short loc_1800EDFE5
0x1800edf96  mov     r9d, 8007000Eh; char *
0x1800edf9c  mov     ebx, r9d
0x1800edf9f  mov     rcx, [rbp+40h]; this
0x1800edfa3  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edfaa  mov     edx, 885h; void *
0x1800edfaf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edfb4  lea     rax, WPP_GLOBAL_Control
0x1800edfbb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edfc2  cmp     rcx, rax
0x1800edfc5  jz      loc_1800EE337
0x1800edfcb  test    byte ptr [rcx+1Ch], 80h
0x1800edfcf  jz      loc_1800EE337
0x1800edfd5  mov     edx, 72h ; 'r'
0x1800edfda  mov     r9d, 8007000Eh
0x1800edfe0  jmp     loc_1800EE327
0x1800edfe5  mov     r12d, edi
0x1800edfe8  cmp     r12d, [r15+10h]
0x1800edfec  jnb     loc_1800EE355
0x1800edff2  mov     dword ptr [rbp+cb], edi
0x1800edff5  mov     rax, [r13+0]
0x1800edff9  lea     r9, [rbp+cb]
0x1800edffd  mov     r8d, 80h
0x1800ee003  mov     rdx, [r14+10h]
0x1800ee007  mov     rcx, r13
0x1800ee00a  mov     rax, [rax+18h]
0x1800ee00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee013  mov     ebx, eax
0x1800ee015  test    eax, eax
0x1800ee017  js      loc_1800EE2EE
0x1800ee01d  lea     rdx, [rbp+var_18]
0x1800ee021  lea     rcx, [rbp+var_10]
0x1800ee025  call    ??$As@UIWpnSettingsEndpoint2@@@?$ComPtr@UIWpnSettingsEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnSettingsEndpoint2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnSettingsEndpoint>::As<IWpnSettingsEndpoint2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnSettingsEndpoint2>>)
0x1800ee02a  mov     ebx, eax
0x1800ee02c  test    eax, eax
0x1800ee02e  js      loc_1800EE2B6
0x1800ee034  mov     rdi, [rbp+var_18]
0x1800ee038  mov     rax, [rdi]
0x1800ee03b  mov     rbx, [rax+18h]
0x1800ee03f  lea     rcx, [rbp+var_20]
0x1800ee043  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ee048  lea     r8, [rbp+var_20]
0x1800ee04c  mov     rdx, [r14+10h]
0x1800ee050  mov     rcx, rdi
0x1800ee053  mov     rax, rbx
0x1800ee056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee05b  mov     ebx, eax
0x1800ee05d  xor     edi, edi
0x1800ee05f  test    eax, eax
0x1800ee061  js      loc_1800EE276
0x1800ee067  mov     [rbp+arg_8], edi
0x1800ee06a  mov     rcx, [rbp+var_20]
0x1800ee06e  mov     rax, [rcx]
0x1800ee071  lea     r8, [rbp+arg_8]
0x1800ee075  lea     rdx, aSCycleMedium; "s:cycle:medium"
0x1800ee07c  mov     rax, [rax+20h]
0x1800ee080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee085  mov     ebx, eax
0x1800ee087  test    eax, eax
0x1800ee089  js      loc_1800EE233
0x1800ee08f  mov     [rbp+arg_18], edi
0x1800ee092  mov     rcx, [rbp+var_20]
0x1800ee096  mov     rax, [rcx]
0x1800ee099  lea     r8, [rbp+arg_18]
0x1800ee09d  lea     rdx, aSCycleWide; "s:cycle:wide"
0x1800ee0a4  mov     rax, [rax+20h]
0x1800ee0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee0ad  mov     ebx, eax
0x1800ee0af  test    eax, eax
0x1800ee0b1  js      loc_1800EE1F0
0x1800ee0b7  mov     [rbp+var_28], edi
0x1800ee0ba  mov     rcx, [rbp+var_20]
0x1800ee0be  mov     rax, [rcx]
0x1800ee0c1  lea     r8, [rbp+var_28]
0x1800ee0c5  lea     rdx, aSCycleLarge; "s:cycle:large"
0x1800ee0cc  mov     rax, [rax+20h]
0x1800ee0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee0d5  mov     ebx, eax
0x1800ee0d7  test    eax, eax
0x1800ee0d9  js      loc_1800EE1AD
0x1800ee0df  mov     edx, r12d
0x1800ee0e2  imul    r9, rdx, 70h ; 'p'
0x1800ee0e6  mov     rcx, [rsi+8]
0x1800ee0ea  mov     eax, dword ptr [rbp+cb]
0x1800ee0ed  mov     [r9+rcx+8], eax
0x1800ee0f2  mov     rcx, [rsi+8]
0x1800ee0f6  mov     eax, [rbp+arg_8]
0x1800ee0f9  mov     [r9+rcx+0Ch], eax
0x1800ee0fe  mov     rcx, [rsi+8]
0x1800ee102  mov     eax, [rbp+arg_18]
0x1800ee105  mov     [r9+rcx+10h], eax
0x1800ee10a  mov     rcx, [rsi+8]
0x1800ee10e  mov     eax, [rbp+var_28]
0x1800ee111  mov     [r9+rcx+14h], eax
0x1800ee116  mov     rcx, [rsi+8]
0x1800ee11a  mov     rax, [r14+10h]
0x1800ee11e  mov     [r9+rcx], rax
0x1800ee122  mov     [r14+10h], rdi
0x1800ee126  mov     rcx, [rsi+8]
0x1800ee12a  mov     rax, [r14+58h]
0x1800ee12e  mov     [r9+rcx+48h], rax
0x1800ee133  mov     rcx, [rsi+8]
0x1800ee137  mov     eax, [r14+60h]
0x1800ee13b  mov     [r9+rcx+50h], eax
0x1800ee140  mov     rcx, [rsi+8]
0x1800ee144  mov     eax, [r14+28h]
0x1800ee148  mov     [r9+rcx+18h], eax
0x1800ee14d  mov     r8d, edi
0x1800ee150  imul    r10, rdx, 70h ; 'p'
0x1800ee154  add     r10, 20h ; ' '
0x1800ee158  lea     rdx, [r10+r8*8]
0x1800ee15c  mov     rcx, [rsi+8]
0x1800ee160  mov     rax, [r14+r8*8+30h]
0x1800ee165  mov     [rdx+rcx], rax
0x1800ee169  mov     [r14+r8*8+30h], rdi
0x1800ee16e  inc     r8
0x1800ee171  cmp     r8, 5
0x1800ee175  jnz     short loc_1800EE158
0x1800ee177  mov     rcx, [rsi+8]
0x1800ee17b  mov     rax, [r14+70h]
0x1800ee17f  mov     [rcx+r9+60h], rax
0x1800ee184  mov     rcx, [rsi+8]
0x1800ee188  mov     eax, [r14+78h]
0x1800ee18c  mov     [rcx+r9+68h], eax
0x1800ee191  mov     rcx, [rsi+8]
0x1800ee195  mov     rax, [r14+68h]
0x1800ee199  mov     [rcx+r9+58h], rax
0x1800ee19e  mov     [r14+68h], rdi
0x1800ee1a2  mov     r14, [r14]
0x1800ee1a5  inc     r12d
0x1800ee1a8  jmp     loc_1800EDFE8
0x1800ee1ad  mov     rcx, [rbp+40h]; this
0x1800ee1b1  mov     r9d, ebx; char *
0x1800ee1b4  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ee1bb  mov     edx, 8A5h; void *
0x1800ee1c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ee1c5  lea     rax, WPP_GLOBAL_Control
0x1800ee1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee1d3  cmp     rcx, rax
0x1800ee1d6  jz      loc_1800EE337
0x1800ee1dc  test    byte ptr [rcx+1Ch], 80h
0x1800ee1e0  jz      loc_1800EE337
0x1800ee1e6  mov     edx, 78h ; 'x'
0x1800ee1eb  jmp     loc_1800EE324
0x1800ee1f0  mov     rcx, [rbp+40h]; this
0x1800ee1f4  mov     r9d, ebx; char *
0x1800ee1f7  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ee1fe  mov     edx, 8A1h; void *
0x1800ee203  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ee208  lea     rax, WPP_GLOBAL_Control
0x1800ee20f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee216  cmp     rcx, rax
0x1800ee219  jz      loc_1800EE337
0x1800ee21f  test    byte ptr [rcx+1Ch], 80h
0x1800ee223  jz      loc_1800EE337
0x1800ee229  mov     edx, 77h ; 'w'
0x1800ee22e  jmp     loc_1800EE324
0x1800ee233  mov     rcx, [rbp+40h]; this
0x1800ee237  mov     r9d, ebx; char *
0x1800ee23a  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ee241  mov     edx, 89Dh; void *
0x1800ee246  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ee24b  lea     rax, WPP_GLOBAL_Control
0x1800ee252  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee259  cmp     rcx, rax
0x1800ee25c  jz      loc_1800EE337
0x1800ee262  test    byte ptr [rcx+1Ch], 80h
0x1800ee266  jz      loc_1800EE337
0x1800ee26c  mov     edx, 76h ; 'v'
0x1800ee271  jmp     loc_1800EE324
0x1800ee276  mov     rcx, [rbp+40h]; this
0x1800ee27a  mov     r9d, ebx; char *
0x1800ee27d  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ee284  mov     edx, 899h; void *
0x1800ee289  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ee28e  lea     rax, WPP_GLOBAL_Control
0x1800ee295  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee29c  cmp     rcx, rax
0x1800ee29f  jz      loc_1800EE337
0x1800ee2a5  test    byte ptr [rcx+1Ch], 80h
0x1800ee2a9  jz      loc_1800EE337
0x1800ee2af  mov     edx, 75h ; 'u'
0x1800ee2b4  jmp     short loc_1800EE324
0x1800ee2b6  mov     rcx, [rbp+40h]; this
0x1800ee2ba  mov     r9d, ebx; char *
0x1800ee2bd  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ee2c4  mov     edx, 896h; void *
0x1800ee2c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ee2ce  lea     rax, WPP_GLOBAL_Control
0x1800ee2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee2dc  cmp     rcx, rax
0x1800ee2df  jz      short loc_1800EE337
0x1800ee2e1  test    byte ptr [rcx+1Ch], 80h
0x1800ee2e5  jz      short loc_1800EE337
0x1800ee2e7  mov     edx, 74h ; 't'
0x1800ee2ec  jmp     short loc_1800EE324
0x1800ee2ee  mov     rcx, [rbp+40h]; this
0x1800ee2f2  mov     r9d, ebx; char *
0x1800ee2f5  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ee2fc  mov     edx, 893h; void *
0x1800ee301  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ee306  lea     rax, WPP_GLOBAL_Control
0x1800ee30d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee314  cmp     rcx, rax
0x1800ee317  jz      short loc_1800EE337
0x1800ee319  test    byte ptr [rcx+1Ch], 80h
  ... truncated ...
```
