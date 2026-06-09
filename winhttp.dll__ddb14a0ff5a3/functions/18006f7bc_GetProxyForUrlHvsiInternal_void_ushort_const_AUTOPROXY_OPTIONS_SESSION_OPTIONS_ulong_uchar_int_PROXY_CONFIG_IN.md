# GetProxyForUrlHvsiInternal(void *,ushort const *,_AUTOPROXY_OPTIONS *,_SESSION_OPTIONS *,ulong,uchar *,int *,_PROXY_CONFIG_INFO *,void * *)

- ea: `0x18006f7bc`
- end: `0x18006ffd3`
- name: `?GetProxyForUrlHvsiInternal@@YAJPEAXPEBGPEAU_AUTOPROXY_OPTIONS@@PEAU_SESSION_OPTIONS@@KPEAEPEAHPEAU_PROXY_CONFIG_INFO@@PEAPEAX@Z`
- size: `2071`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, const unsigned __int16 *@<rdx>, struct _AUTOPROXY_OPTIONS *@<r8>, struct _SESSION_OPTIONS *@<r9>, unsigned int, unsigned __int8 *, int *, struct _PROXY_CONFIG_INFO *, void **)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f4ec`

## callees

- `0x18000d804`
- `0x18000eebc`
- `0x18000f0e4`
- `0x1800148a4`
- `0x1800241a0`
- `0x18003ba00`
- `0x18003bc60`
- `0x1800403d4`
- `0x180041eb0`
- `0x18006f7bc`
- `0x18006ffdc`
- `0x18006fffc`
- `0x180070048`
- `0x180070138`
- `0x1800838bc`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800a4d40`
- `0x1800cf4c4`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006fb7f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006fb7f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006fd68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006fdfa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006fd68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006fdfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fb3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ffab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ffab`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18006fce7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18006fce7`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800ce526`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800ce526`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18006fb08`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18006fb08`
- `RPCRT4!RpcAsyncCancelCall` at `0x18006fda8`
- `RPCRT4!RpcAsyncCancelCall` at `0x18006fda8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18006fe10`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18006fe10`

## pseudocode

```c
__int64 __fastcall GetProxyForUrlHvsiInternal(
        void *a1,
        const unsigned __int16 *a2,
        struct _AUTOPROXY_OPTIONS *a3,
        struct _SESSION_OPTIONS *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        int *a7,
        struct _PROXY_CONFIG_INFO *a8,
        void **a9)
{
  struct tagProxyResolveUrl *v11; // rbx
  __int64 v12; // rdx
  signed int IsValid; // edi
  const struct _SESSION_OPTIONS *v14; // r8
  unsigned int CumulativeTimeout; // eax
  int v16; // eax
  int v17; // r13d
  HANDLE_OBJECT *v18; // r15
  bool v19; // sf
  int v20; // eax
  RPC_STATUS v21; // eax
  int v22; // r15d
  struct tagProxyResolveUrl *EventW; // rax
  RPCNOTIFICATION_ROUTINE *v24; // r13
  signed int LastError; // eax
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // edi
  int v29; // eax
  struct _AUTOPROXY_OPTIONS *v30; // rdi
  DWORD v31; // eax
  DWORD v32; // r15d
  unsigned int v33; // eax
  bool v34; // sf
  unsigned int v35; // eax
  unsigned int v36; // edi
  bool v37; // sf
  unsigned int v38; // eax
  struct tagProxyResolveUrl **v40; // [rsp+20h] [rbp-178h]
  DWORD dwMilliseconds; // [rsp+70h] [rbp-128h]
  int v42; // [rsp+78h] [rbp-120h] BYREF
  int v43; // [rsp+7Ch] [rbp-11Ch]
  struct _WINHTTP_AUTOPROXY_OPTIONS *v44; // [rsp+80h] [rbp-118h] BYREF
  struct tagProxyResolveUrl *v45[2]; // [rsp+88h] [rbp-110h] BYREF
  const unsigned __int16 *v46; // [rsp+98h] [rbp-100h]
  struct _AUTOPROXY_OPTIONS *v47; // [rsp+A0h] [rbp-F8h]
  _BYTE *v48; // [rsp+A8h] [rbp-F0h]
  unsigned __int8 *v49; // [rsp+B0h] [rbp-E8h]
  struct _SESSION_OPTIONS *v50; // [rsp+B8h] [rbp-E0h]
  void **v51; // [rsp+C0h] [rbp-D8h]
  int *v52; // [rsp+C8h] [rbp-D0h]
  struct tagProxyResolveUrl **v53; // [rsp+D0h] [rbp-C8h]
  HANDLE_OBJECT *v54; // [rsp+E0h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+F0h] [rbp-A8h] BYREF
  unsigned int Reply; // [rsp+160h] [rbp-38h] BYREF

  v50 = a4;
  v47 = a3;
  v46 = a2;
  v49 = a6;
  v52 = a7;
  v48 = a8;
  v51 = a9;
  Reply = 0;
  v54 = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v11 = 0;
  v45[0] = 0;
  v44 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 60, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids);
  if ( a7 )
    *a7 = 0;
  WxZeroOut<_PROXY_CONFIG_INFO>(v48);
  if ( a9 )
    *a9 = 0;
  if ( !v46 )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( !a3 )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( !v50 )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( (a5 == 0) != (v49 == 0) )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( !a7 )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( !v12 )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( !a9 )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  if ( !(unsigned int)ValidateAutoproxyOptions(a3) )
  {
    IsValid = -2147024809;
    goto LABEL_96;
  }
  CumulativeTimeout = GetCumulativeTimeout(v14);
  dwMilliseconds = CumulativeTimeout;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 61, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, CumulativeTimeout, v40);
  v16 = MapHandleToAddress(a1, (void **)&v54, 0);
  IsValid = v16;
  if ( v16 > 0 )
    IsValid = (unsigned __int16)v16 | 0x80070000;
  if ( IsValid >= 0 )
  {
    v17 = 0;
    v18 = v54;
    IsValid = HANDLE_OBJECT::IsValid(v54, 1684826455);
    if ( !IsValid )
      v17 = (*(__int64 (__fastcall **)(HANDLE_OBJECT *))(*(_QWORD *)v18 + 8LL))(v18);
    v19 = IsValid < 0;
    if ( IsValid > 0 )
    {
      IsValid = (unsigned __int16)IsValid | 0x80070000;
      v19 = IsValid < 0;
    }
    if ( !v19 )
    {
      if ( v17 != 1952804425 )
      {
        IsValid = -2147012878;
        goto LABEL_96;
      }
      if ( !GlobalDataInitialized )
      {
        IsValid = -2147012724;
        goto LABEL_96;
      }
      v20 = CheckAutoProxyServiceIsRunning(dwMilliseconds);
      IsValid = v20;
      if ( v20 > 0 )
        IsValid = (unsigned __int16)v20 | 0x80070000;
      if ( IsValid >= 0 )
      {
        v53 = (struct tagProxyResolveUrl **)g_hAPImpersonationBinding;
        IsValid = g_hAPImpersonationBinding == 0 ? 0x2F8C : 0;
        if ( !g_hAPImpersonationBinding )
          IsValid |= 0x80070000;
        if ( IsValid >= 0 )
        {
          memset_0(&pAsync, 0, sizeof(pAsync));
          v21 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
          IsValid = v21;
          if ( v21 > 0 )
            IsValid = (unsigned __int16)v21 | 0x80070000;
          if ( IsValid >= 0 )
          {
            v22 = 1;
            EventW = (struct tagProxyResolveUrl *)CreateEventW(0, 1, 0, 0);
            v24 = (RPCNOTIFICATION_ROUTINE *)EventW;
            v11 = EventW;
            v45[1] = EventW;
            if ( !EventW )
            {
              LastError = GetLastError();
              IsValid = LastError;
              if ( LastError > 0 )
                IsValid = (unsigned __int16)LastError | 0x80070000;
              if ( IsValid >= 0 )
                IsValid = -2147418113;
              goto LABEL_96;
            }
            ResetEvent(EventW);
            pAsync.NotificationType = RpcNotificationTypeEvent;
            pAsync.u.APC.NotificationRoutine = v24;
            v26 = *(_DWORD *)v47;
            v43 = 0;
            v42 = 0;
            v27 = 0;
            v28 = v26 & 8;
            if ( (v26 & 8) == 0 )
              goto LABEL_55;
            if ( (v26 & 4) != 0 )
            {
              v43 = 138;
            }
            else
            {
LABEL_55:
              v29 = QueryWinHttpLowerCaseRegKey(&v42);
              v27 = v28;
              if ( v29 >= 0 )
                v27 = (unsigned int)v42;
            }
            v40 = v45;
            IsValid = ProxyResolveUrlCreate::WithUrlEx(v27, v46, GlobalAutoProxyQueryWithFullUrl);
            if ( IsValid >= 0 )
            {
              v30 = v47;
              if ( (*(_DWORD *)v47 & 2) == 0 && *((_QWORD *)v47 + 1)
                || (*(_DWORD *)v47 & 2) != 0 && !(unsigned int)IsPACUrlConfigurationAllowedForHvsi(v47) )
              {
                v22 = 0;
              }
              IsValid = CopyAutoProxyOptions(v30, v22, &v44);
              if ( IsValid >= 0 )
              {
                *(_DWORD *)v44 |= 0x1000000u;
                v40 = v53;
                Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, &pAsync);
                v31 = WaitForSingleObjectEx(v24, dwMilliseconds, 0);
                v32 = v31;
                if ( !v31 )
                  goto LABEL_74;
                if ( (xmmword_180107A50 & 0x20) != 0 )
                  WPP_SF_d(517, 63, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, v31, v40);
                v33 = RpcAsyncCancelCall(&pAsync, 1);
                IsValid = v33;
                if ( v33 && (xmmword_180107A50 & 0x20) != 0 )
                  WPP_SF_d(517, 64, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, v33, v40);
                v34 = IsValid < 0;
                if ( IsValid > 0 )
                {
                  IsValid = (unsigned __int16)IsValid | 0x80070000;
                  v34 = IsValid < 0;
                }
                if ( !v34 )
                {
                  WaitForSingleObjectEx(v24, 0xFFFFFFFF, 0);
LABEL_74:
                  v35 = RpcAsyncCompleteCall(&pAsync, &Reply);
                  IsValid = v35;
                  if ( v35 == 1818 )
                  {
                    v36 = 12002;
                    if ( v32 != 258 )
                      v36 = 12004;
                    if ( (xmmword_180107A50 & 0x20) != 0 )
                    {
                      LODWORD(v40) = v32;
                      WPP_SF_Dd(517, 65, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, v36);
                    }
                    IsValid = v36 | 0x80070000;
                  }
                  else
                  {
                    if ( !v35 )
                      goto LABEL_86;
                    if ( (xmmword_180107A50 & 0x20) != 0 )
                      WPP_SF_d(517, 66, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, v35, v40);
                    v37 = IsValid < 0;
                    if ( IsValid > 0 )
                    {
                      IsValid = (unsigned __int16)IsValid | 0x80070000;
                      v37 = IsValid < 0;
                    }
                    if ( !v37 )
                    {
LABEL_86:
                      v38 = WX_WIN32_FROM_HR(Reply);
                      IsValid = v38;
                      if ( v38 == 12017 || v38 == -2147467260 )
                      {
                        if ( (xmmword_180107A50 & 0x20) != 0 )
                          WPP_SF_d(517, 67, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, v38, v40);
                        IsValid = -2147023174;
                      }
                      else
                      {
                        UpdateAutoProxyServiceTimeStamp();
                        if ( (xmmword_180107A60 & 0x20) != 0 )
                          WPP_SF_d(
                            1029,
                            68,
                            WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids,
                            (unsigned int)IsValid,
                            v40);
                        if ( IsValid > 0 )
                          IsValid = (unsigned __int16)IsValid | 0x80070000;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_96:
  if ( v54 )
  {
    HANDLE_OBJECT::Dereference(v54);
    v54 = 0;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 69, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids, (unsigned int)IsValid, v40);
  if ( v44 )
    FreeAutoProxyOptions(&v44);
  if ( v45[0] )
    FreeProxyResolveUrl((LPVOID **)v45);
  if ( v11 )
    CloseHandle(v11);
  return (unsigned int)IsValid;
}

```

## disassembly

```asm
0x18006f7bc  mov     r11, rsp
0x18006f7bf  push    rbx
0x18006f7c0  push    rdi
0x18006f7c1  push    r13
0x18006f7c3  push    r14
0x18006f7c5  push    r15
0x18006f7c7  sub     rsp, 170h
0x18006f7ce  mov     rax, cs:__security_cookie
0x18006f7d5  xor     rax, rsp
0x18006f7d8  mov     [rsp+198h+var_30], rax
0x18006f7e0  mov     [rsp+198h+var_E0], r9
0x18006f7e8  mov     r14, r8
0x18006f7eb  mov     [rsp+198h+var_F8], r8
0x18006f7f3  mov     [rsp+198h+var_100], rdx
0x18006f7fb  mov     rdi, rcx
0x18006f7fe  mov     rax, [rsp+198h+arg_28]
0x18006f806  mov     [rsp+198h+var_E8], rax
0x18006f80e  mov     r15, [rsp+198h+arg_30]
0x18006f816  mov     [rsp+198h+var_D0], r15
0x18006f81e  mov     rax, [rsp+198h+arg_38]
0x18006f826  mov     [rsp+198h+var_F0], rax
0x18006f82e  mov     r13, [rsp+198h+arg_40]
0x18006f836  mov     [rsp+198h+var_D8], r13
0x18006f83e  mov     [rsp+198h+var_124], 0
0x18006f846  mov     dword ptr [r11-38h], 0
0x18006f84e  mov     qword ptr [r11-0B8h], 0
0x18006f859  xor     edx, edx; Val
0x18006f85b  lea     r8d, [rdx+70h]; Size
0x18006f85f  lea     rcx, [r11-0A8h]; void *
0x18006f866  call    memset_0
0x18006f86b  xor     ebx, ebx
0x18006f86d  mov     [rsp+198h+var_110], rbx
0x18006f875  mov     [rsp+198h+var_118], rbx
0x18006f87d  test    byte ptr cs:xmmword_180107A60, 20h
0x18006f884  jz      short loc_18006F89D
0x18006f886  lea     edx, [rbx+3Ch]
0x18006f889  mov     ecx, 405h
0x18006f88e  mov     r9, rdi
0x18006f891  lea     r8, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids
0x18006f898  call    WPP_SF_q
0x18006f89d  test    r15, r15
0x18006f8a0  jz      short loc_18006F8A5
0x18006f8a2  mov     [r15], ebx
0x18006f8a5  mov     rdx, [rsp+198h+var_F0]
0x18006f8ad  mov     rcx, rdx
0x18006f8b0  call    ??$WxZeroOut@U_PROXY_CONFIG_INFO@@@@YAXPEAU_PROXY_CONFIG_INFO@@@Z; WxZeroOut<_PROXY_CONFIG_INFO>(_PROXY_CONFIG_INFO *)
0x18006f8b5  test    r13, r13
0x18006f8b8  jz      short loc_18006F8BE
0x18006f8ba  mov     [r13+0], rbx
0x18006f8be  cmp     [rsp+198h+var_100], rbx
0x18006f8c6  jnz     short loc_18006F8DA
0x18006f8c8  mov     edi, 80070057h
0x18006f8cd  mov     [rsp+198h+var_124], 8C6h
0x18006f8d5  jmp     loc_18006FF33
0x18006f8da  test    r14, r14
0x18006f8dd  jnz     short loc_18006F8F1
0x18006f8df  mov     edi, 80070057h
0x18006f8e4  mov     [rsp+198h+var_124], 8C7h
0x18006f8ec  jmp     loc_18006FF33
0x18006f8f1  mov     r8, [rsp+198h+var_E0]
0x18006f8f9  test    r8, r8
0x18006f8fc  jnz     short loc_18006F910
0x18006f8fe  mov     edi, 80070057h
0x18006f903  mov     [rsp+198h+var_124], 8C8h
0x18006f90b  jmp     loc_18006FF33
0x18006f910  xor     ecx, ecx
0x18006f912  cmp     [rsp+198h+var_E8], rcx
0x18006f91a  setz    cl
0x18006f91d  xor     eax, eax
0x18006f91f  cmp     [rsp+198h+arg_20], eax
0x18006f926  setz    al
0x18006f929  cmp     eax, ecx
0x18006f92b  jz      short loc_18006F93F
0x18006f92d  mov     edi, 80070057h
0x18006f932  mov     [rsp+198h+var_124], 8C9h
0x18006f93a  jmp     loc_18006FF33
0x18006f93f  test    r15, r15
0x18006f942  jnz     short loc_18006F956
0x18006f944  mov     edi, 80070057h
0x18006f949  mov     [rsp+198h+var_124], 8CAh
0x18006f951  jmp     loc_18006FF33
0x18006f956  test    rdx, rdx
0x18006f959  jnz     short loc_18006F96D
0x18006f95b  mov     edi, 80070057h
0x18006f960  mov     [rsp+198h+var_124], 8CBh
0x18006f968  jmp     loc_18006FF33
0x18006f96d  test    r13, r13
0x18006f970  jnz     short loc_18006F984
0x18006f972  mov     edi, 80070057h
0x18006f977  mov     [rsp+198h+var_124], 8CCh
0x18006f97f  jmp     loc_18006FF33
0x18006f984  mov     rcx, r14; struct _WINHTTP_AUTOPROXY_OPTIONS *
0x18006f987  call    ?ValidateAutoproxyOptions@@YAHPEBU_WINHTTP_AUTOPROXY_OPTIONS@@@Z; ValidateAutoproxyOptions(_WINHTTP_AUTOPROXY_OPTIONS const *)
0x18006f98c  test    eax, eax
0x18006f98e  jnz     short loc_18006F9A2
0x18006f990  mov     edi, 80070057h
0x18006f995  mov     [rsp+198h+var_124], 8CEh
0x18006f99d  jmp     loc_18006FF33
0x18006f9a2  mov     rcx, r8; struct _SESSION_OPTIONS *
0x18006f9a5  call    ?GetCumulativeTimeout@@YAKPEBU_SESSION_OPTIONS@@@Z; GetCumulativeTimeout(_SESSION_OPTIONS const *)
0x18006f9aa  mov     [rsp+198h+dwMilliseconds], eax
0x18006f9ae  test    byte ptr cs:xmmword_180107A60, 20h
0x18006f9b5  jz      short loc_18006F9D0
0x18006f9b7  mov     edx, 3Dh ; '='
0x18006f9bc  mov     ecx, 405h
0x18006f9c1  mov     r9d, eax
0x18006f9c4  lea     r8, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids
0x18006f9cb  call    WPP_SF_d
0x18006f9d0  xor     r8d, r8d; int
0x18006f9d3  lea     rdx, [rsp+198h+var_B8]; void **
0x18006f9db  mov     rcx, rdi; void *
0x18006f9de  call    ?MapHandleToAddress@@YAKPEAXPEAPEAXH@Z; MapHandleToAddress(void *,void * *,int)
0x18006f9e3  mov     edi, eax
0x18006f9e5  mov     r14d, 80070000h
0x18006f9eb  test    eax, eax
0x18006f9ed  jle     short loc_18006F9F5
0x18006f9ef  movzx   edi, ax
0x18006f9f2  or      edi, r14d
0x18006f9f5  test    edi, edi
0x18006f9f7  jns     short loc_18006FA06
0x18006f9f9  mov     [rsp+198h+var_124], 8DCh
0x18006fa01  jmp     loc_18006FF33
0x18006fa06  xor     r13d, r13d
0x18006fa09  mov     r15, [rsp+198h+var_B8]
0x18006fa11  mov     edx, 646C6957h
0x18006fa16  mov     rcx, r15
0x18006fa19  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18006fa1e  mov     edi, eax
0x18006fa20  test    eax, eax
0x18006fa22  jnz     short loc_18006FA36
0x18006fa24  mov     rax, [r15]
0x18006fa27  mov     rcx, r15
0x18006fa2a  mov     rax, [rax+8]
0x18006fa2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa33  mov     r13d, eax
0x18006fa36  test    edi, edi
0x18006fa38  jle     short loc_18006FA42
0x18006fa3a  movzx   edi, di
0x18006fa3d  or      edi, r14d
0x18006fa40  test    edi, edi
0x18006fa42  jns     short loc_18006FA51
0x18006fa44  mov     [rsp+198h+var_124], 8DEh
0x18006fa4c  jmp     loc_18006FF33
0x18006fa51  cmp     r13d, 74656E49h
0x18006fa58  jz      short loc_18006FA6C
0x18006fa5a  mov     edi, 80072EF2h
0x18006fa5f  mov     [rsp+198h+var_124], 8E1h
0x18006fa67  jmp     loc_18006FF33
0x18006fa6c  cmp     cs:?GlobalDataInitialized@@3HA, ebx; int GlobalDataInitialized
0x18006fa72  jnz     short loc_18006FA86
0x18006fa74  mov     edi, 80072F8Ch
0x18006fa79  mov     [rsp+198h+var_124], 8E4h
0x18006fa81  jmp     loc_18006FF33
0x18006fa86  mov     ecx, [rsp+198h+dwMilliseconds]; unsigned int
0x18006fa8a  call    ?CheckAutoProxyServiceIsRunning@@YAKK@Z; CheckAutoProxyServiceIsRunning(ulong)
0x18006fa8f  mov     edi, eax
0x18006fa91  test    eax, eax
0x18006fa93  jle     short loc_18006FA9B
0x18006fa95  movzx   edi, ax
0x18006fa98  or      edi, r14d
0x18006fa9b  test    edi, edi
0x18006fa9d  jns     short loc_18006FAAC
0x18006fa9f  mov     [rsp+198h+var_124], 8E6h
0x18006faa7  jmp     loc_18006FF33
0x18006faac  mov     rcx, cs:?g_hAPImpersonationBinding@@3PEAXEA; void * g_hAPImpersonationBinding
0x18006fab3  mov     [rsp+198h+var_C8], rcx
0x18006fabb  mov     rax, rcx
0x18006fabe  neg     rax
0x18006fac1  sbb     edi, edi
0x18006fac3  not     edi
0x18006fac5  and     edi, 2F8Ch
0x18006facb  mov     eax, edi
0x18006facd  or      eax, r14d
0x18006fad0  test    rcx, rcx
0x18006fad3  cmovz   edi, eax
0x18006fad6  test    edi, edi
0x18006fad8  jns     short loc_18006FAE7
0x18006fada  mov     [rsp+198h+var_124], 8ECh
0x18006fae2  jmp     loc_18006FF33
0x18006fae7  mov     edi, 70h ; 'p'
0x18006faec  mov     r8d, edi; Size
0x18006faef  xor     edx, edx; Val
0x18006faf1  lea     rcx, [rsp+198h+pAsync]; void *
0x18006faf9  call    memset_0
0x18006fafe  mov     edx, edi; Size
0x18006fb00  lea     rcx, [rsp+198h+pAsync]; pAsync
0x18006fb08  call    cs:__imp_RpcAsyncInitializeHandle
0x18006fb0e  mov     edi, eax
0x18006fb10  test    eax, eax
0x18006fb12  jle     short loc_18006FB1A
0x18006fb14  movzx   edi, ax
0x18006fb17  or      edi, r14d
0x18006fb1a  test    edi, edi
0x18006fb1c  jns     short loc_18006FB2B
0x18006fb1e  mov     [rsp+198h+var_124], 8EFh
0x18006fb26  jmp     loc_18006FF33
0x18006fb2b  xor     r9d, r9d; lpName
0x18006fb2e  xor     r8d, r8d; bInitialState
0x18006fb31  lea     r15d, [r9+1]
0x18006fb35  mov     edx, r15d; bManualReset
0x18006fb38  xor     ecx, ecx; lpEventAttributes
0x18006fb3a  call    cs:__imp_CreateEventW
0x18006fb40  mov     r13, rax
0x18006fb43  mov     rbx, rax
0x18006fb46  mov     [rsp+198h+var_108], rax
0x18006fb4e  test    rax, rax
0x18006fb51  jnz     short loc_18006FB7C
0x18006fb53  call    cs:__imp_GetLastError
0x18006fb59  mov     edi, eax
0x18006fb5b  test    eax, eax
0x18006fb5d  jle     short loc_18006FB65
0x18006fb5f  movzx   edi, ax
0x18006fb62  or      edi, r14d
0x18006fb65  mov     eax, 8000FFFFh
0x18006fb6a  test    edi, edi
0x18006fb6c  cmovns  edi, eax
0x18006fb6f  mov     [rsp+198h+var_124], 8F2h
0x18006fb77  jmp     loc_18006FF33
0x18006fb7c  mov     rcx, r13; hEvent
0x18006fb7f  call    cs:__imp_ResetEvent
0x18006fb85  mov     [rsp+198h+pAsync.NotificationType], r15d
0x18006fb8d  mov     qword ptr [rsp+198h+pAsync.u], r13
0x18006fb95  mov     rax, [rsp+198h+var_F8]
0x18006fb9d  mov     eax, [rax]
0x18006fb9f  mov     [rsp+198h+var_11C], 0
0x18006fba7  mov     [rsp+198h+var_120], 0
0x18006fbaf  xor     ecx, ecx
0x18006fbb1  mov     edi, eax
0x18006fbb3  and     edi, 8
0x18006fbb6  jz      short loc_18006FBC6
0x18006fbb8  test    al, 4
0x18006fbba  jz      short loc_18006FBC6
0x18006fbbc  mov     [rsp+198h+var_11C], 8Ah
0x18006fbc4  jmp     short loc_18006FBD9
0x18006fbc6  lea     rcx, [rsp+198h+var_120]; int *
0x18006fbcb  call    ?QueryWinHttpLowerCaseRegKey@@YAJPEAH@Z; QueryWinHttpLowerCaseRegKey(int *)
0x18006fbd0  mov     ecx, edi
0x18006fbd2  test    eax, eax
0x18006fbd4  cmovns  ecx, [rsp+198h+var_120]
0x18006fbd9  lea     rax, [rsp+198h+var_110]
0x18006fbe1  mov     [rsp+198h+var_178], rax
0x18006fbe6  mov     r8d, cs:?GlobalAutoProxyQueryWithFullUrl@@3KA; ulong GlobalAutoProxyQueryWithFullUrl
0x18006fbed  mov     rdx, [rsp+198h+var_100]
0x18006fbf5  call    ?WithUrlEx@ProxyResolveUrlCreate@@SAJHPEBGHW4ProxyResolveScheme@@PEAPEAUtagProxyResolveUrl@@@Z; ProxyResolveUrlCreate::WithUrlEx(int,ushort const *,int,ProxyResolveScheme,tagProxyResolveUrl * *)
0x18006fbfa  mov     edi, eax
0x18006fbfc  test    eax, eax
0x18006fbfe  jns     short loc_18006FC0D
0x18006fc00  mov     [rsp+198h+var_124], 8FEh
0x18006fc08  jmp     loc_18006FF33
0x18006fc0d  mov     rdi, [rsp+198h+var_F8]
0x18006fc15  mov     eax, [rdi]
0x18006fc17  and     eax, 2
0x18006fc1a  jnz     short loc_18006FC23
0x18006fc1c  cmp     qword ptr [rdi+8], 0
0x18006fc21  jnz     short loc_18006FC33
0x18006fc23  test    eax, eax
0x18006fc25  jz      short loc_18006FC36
0x18006fc27  mov     rcx, rdi; struct _AUTOPROXY_OPTIONS *
0x18006fc2a  call    ?IsPACUrlConfigurationAllowedForHvsi@@YAHPEAU_AUTOPROXY_OPTIONS@@@Z; IsPACUrlConfigurationAllowedForHvsi(_AUTOPROXY_OPTIONS *)
0x18006fc2f  test    eax, eax
0x18006fc31  jnz     short loc_18006FC36
0x18006fc33  xor     r15d, r15d
0x18006fc36  lea     r8, [rsp+198h+var_118]; struct _WINHTTP_AUTOPROXY_OPTIONS **
0x18006fc3e  mov     edx, r15d; int
0x18006fc41  mov     rcx, rdi; struct _WINHTTP_AUTOPROXY_OPTIONS *
0x18006fc44  call    ?CopyAutoProxyOptions@@YAJPEBU_WINHTTP_AUTOPROXY_OPTIONS@@HPEAPEAU1@@Z; CopyAutoProxyOptions(_WINHTTP_AUTOPROXY_OPTIONS const *,int,_WINHTTP_AUTOPROXY_OPTIONS * *)
0x18006fc49  mov     edi, eax
0x18006fc4b  test    eax, eax
0x18006fc4d  jns     short loc_18006FC5C
0x18006fc4f  mov     [rsp+198h+var_124], 912h
0x18006fc57  jmp     loc_18006FF33
0x18006fc5c  mov     rcx, [rsp+198h+var_118]
0x18006fc64  bts     dword ptr [rcx], 18h
0x18006fc68  mov     rax, [rsp+198h+var_110]
0x18006fc70  mov     rdx, [rsp+198h+var_D8]
0x18006fc78  mov     [rsp+198h+var_138], rdx
0x18006fc7d  mov     rdx, [rsp+198h+var_F0]
0x18006fc85  mov     [rsp+198h+var_140], rdx
0x18006fc8a  mov     rdx, [rsp+198h+var_D0]
0x18006fc92  mov     [rsp+198h+var_148], rdx
0x18006fc97  mov     rdx, [rsp+198h+var_E8]
0x18006fc9f  mov     [rsp+198h+var_150], rdx
0x18006fca4  mov     edx, [rsp+198h+arg_20]
0x18006fcab  mov     [rsp+198h+var_158], edx
0x18006fcaf  mov     rdx, [rsp+198h+var_E0]
0x18006fcb7  mov     [rsp+198h+var_160], rdx
0x18006fcbc  mov     [rsp+198h+var_168], rcx
0x18006fcc1  mov     [rsp+198h+var_170], rax
0x18006fcc6  mov     rax, [rsp+198h+var_C8]
0x18006fcce  mov     [rsp+198h+var_178], rax
0x18006fcd3  lea     r9, [rsp+198h+pAsync]
0x18006fcdb  xor     r8d, r8d; pReturnValue
0x18006fcde  xor     edx, edx; nProcNum
0x18006fce0  lea     rcx, pProxyInfo; pProxyInfo
0x18006fce7  call    cs:__imp_Ndr64AsyncClientCall
0x18006fced  jmp     short loc_18006FD5E
0x18006fcef  mov     edi, eax
0x18006fcf1  test    byte ptr cs:xmmword_180107A50, 20h
0x18006fcf8  jz      short loc_18006FD13
0x18006fcfa  mov     edx, 3Eh ; '>'
  ... truncated ...
```
