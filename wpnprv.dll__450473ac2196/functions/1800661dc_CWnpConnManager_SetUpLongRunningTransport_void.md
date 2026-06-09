# CWnpConnManager::SetUpLongRunningTransport(void)

- ea: `0x1800661dc`
- end: `0x1800665ec`
- name: `?SetUpLongRunningTransport@CWnpConnManager@@AEAAJXZ`
- size: `1040`
- prototype: `__int64 __fastcall(CWnpConnManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180063cb0`

## callees

- `0x180007440`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x1800661dc`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006629b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066371`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006629b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066358`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800662b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800662b0`

## pseudocode

```c
__int64 __fastcall CWnpConnManager::SetUpLongRunningTransport(CWnpConnManager *this)
{
  PVOID v2; // rcx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(__int64, PVOID, __int64, _QWORD); // rsi
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v14; // [rsp+20h] [rbp-39h]
  int v15[2]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h] BYREF
  __int64 *v17; // [rsp+40h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
  }
  if ( !*((_BYTE *)this + 212) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  if ( *((_QWORD *)this + 28) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  *(_QWORD *)v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Networking.Sockets.ControlChannelTrigger",
         0x30u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(
                        hstringHeader.Reserved.Reserved1,
                        &GUID_da4b7cf0_8d71_446f_88c3_b95184a2d6cd,
                        &v16);
  v4 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = *((_DWORD *)this + 54);
    v8 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _QWORD))(*(_QWORD *)v16 + 56LL);
    if ( WindowsCreateStringReference(
           L"WNS Data Connection",
           0x13u,
           (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
           (HSTRING *)&hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v9 = v8(v16, hstringHeader.Reserved.Reserved1, 20, v7);
    v4 = v9;
    if ( v9 >= 0 )
    {
      v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 **))v15)(
              *(_QWORD *)v15,
              &GUID_8d470579_96e4_412d_ad40_d9defb35ce86,
              &v17);
      v4 = v10;
      if ( v10 >= 0 )
      {
        v11 = *v17;
        *(GUID *)&hstringHeader.Reserved.Reserved1 = CLSID_NcbBackgroundTask;
        v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, HSTRING_HEADER *))(v11 + 48))(v17, 1, &hstringHeader);
        v4 = v12;
        if ( v12 >= 0 )
        {
          *((_QWORD *)this + 28) = *(_QWORD *)v15;
          *(_QWORD *)v15 = 0;
          goto LABEL_47;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            97,
            &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
            (unsigned int)v12);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E4,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
          (const char *)v4,
          (int)v15);
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v6 = 98;
          goto LABEL_19;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
            (unsigned int)v10);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
          (const char *)v4,
          (int)v15);
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v6 = 96;
          goto LABEL_19;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          93,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          (unsigned int)v9);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)v4,
        (int)v15);
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v6 = 94;
        goto LABEL_19;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
        (unsigned int)ActivationFactory);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
      (const char *)v4,
      v14);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 92;
LABEL_19:
      WPP_SF_d(v5[2], v6, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v4);
LABEL_47:
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v16 = 0;
  }
  if ( *(_QWORD *)v15 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 16LL))(*(_QWORD *)v15);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    *(_QWORD *)v15 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v17 = 0;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 99, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800661dc  push    rbp
0x1800661de  push    rbx
0x1800661df  push    rsi
0x1800661e0  push    rdi
0x1800661e1  push    r12
0x1800661e3  push    r15
0x1800661e5  lea     rbp, [rsp-2Fh]
0x1800661ea  sub     rsp, 88h
0x1800661f1  mov     rax, cs:__security_cookie
0x1800661f8  xor     rax, rsp
0x1800661fb  mov     [rbp+57h+var_40], rax
0x1800661ff  mov     rdi, rcx
0x180066202  mov     rcx, cs:WPP_GLOBAL_Control
0x180066209  lea     r15, WPP_GLOBAL_Control
0x180066210  lea     r12, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180066217  cmp     rcx, r15
0x18006621a  jz      short loc_180066239
0x18006621c  test    byte ptr [rcx+1Ch], 4
0x180066220  jz      short loc_180066239
0x180066222  cmp     byte ptr [rcx+19h], 6
0x180066226  jb      short loc_180066239
0x180066228  mov     rcx, [rcx+10h]
0x18006622c  mov     edx, 5Ah ; 'Z'
0x180066231  mov     r8, r12
0x180066234  call    WPP_SF_
0x180066239  cmp     byte ptr [rdi+0D4h], 0
0x180066240  jnz     short loc_180066247
0x180066242  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180066247  cmp     qword ptr [rdi+0E0h], 0
0x18006624f  jz      short loc_180066256
0x180066251  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180066256  lea     r9, [rbp+57h+hstringHeader]; string
0x18006625a  mov     qword ptr [rbp+57h+var_80], 0
0x180066262  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180066266  mov     [rbp+57h+var_70], 0
0x18006626e  mov     edx, 30h ; '0'; length
0x180066273  mov     [rbp+57h+var_78], 0
0x18006627b  lea     rcx, ?RuntimeClass_Windows_Networking_Sockets_ControlChannelTrigger@@3QBGB; "Windows.Networking.Sockets.ControlChann"...
0x180066282  call    cs:__imp_WindowsCreateStringReference
0x180066288  test    eax, eax
0x18006628a  jns     short loc_1800662A1
0x18006628c  xor     r9d, r9d; lpArguments
0x18006628f  xor     r8d, r8d; nNumberOfArguments
0x180066292  mov     ecx, 0C000000Dh; dwExceptionCode
0x180066297  lea     edx, [r9+1]; dwExceptionFlags
0x18006629b  call    cs:__imp_RaiseException
0x1800662a1  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800662a5  lea     r8, [rbp+57h+var_78]
0x1800662a9  lea     rdx, _GUID_da4b7cf0_8d71_446f_88c3_b95184a2d6cd
0x1800662b0  call    cs:__imp_RoGetActivationFactory
0x1800662b6  mov     ebx, eax
0x1800662b8  test    eax, eax
0x1800662ba  jns     short loc_180066333
0x1800662bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800662c3  cmp     rcx, r15
0x1800662c6  jz      short loc_1800662E8
0x1800662c8  test    byte ptr [rcx+1Ch], 4
0x1800662cc  jz      short loc_1800662E8
0x1800662ce  cmp     byte ptr [rcx+19h], 2
0x1800662d2  jb      short loc_1800662E8
0x1800662d4  mov     rcx, [rcx+10h]
0x1800662d8  mov     edx, 5Bh ; '['
0x1800662dd  mov     r9d, eax
0x1800662e0  mov     r8, r12
0x1800662e3  call    WPP_SF_d
0x1800662e8  mov     rcx, [rbp+5Fh]; this
0x1800662ec  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800662f3  mov     r9d, ebx; char *
0x1800662f6  mov     edx, 2D2h; void *
0x1800662fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180066300  mov     rcx, cs:WPP_GLOBAL_Control
0x180066307  cmp     rcx, r15
0x18006630a  jz      loc_180066534
0x180066310  test    byte ptr [rcx+1Ch], 80h
0x180066314  jz      loc_180066534
0x18006631a  mov     edx, 5Ch ; '\'
0x18006631f  mov     rcx, [rcx+10h]
0x180066323  mov     r9d, ebx
0x180066326  mov     r8, r12
0x180066329  call    WPP_SF_d
0x18006632e  jmp     loc_18006652D
0x180066333  mov     rax, [rbp+57h+var_78]
0x180066337  lea     r9, [rbp+57h+hstringHeader]; string
0x18006633b  mov     ebx, [rdi+0D8h]
0x180066341  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180066345  lea     rcx, ?g_WnpChannelId@@3QBGB; "WNS Data Connection"
0x18006634c  mov     rdx, [rax]
0x18006634f  mov     rsi, [rdx+38h]
0x180066353  mov     edx, 13h; length
0x180066358  call    cs:__imp_WindowsCreateStringReference
0x18006635e  test    eax, eax
0x180066360  jns     short loc_180066377
0x180066362  xor     r9d, r9d; lpArguments
0x180066365  xor     r8d, r8d; nNumberOfArguments
0x180066368  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006636d  lea     edx, [r9+1]; dwExceptionFlags
0x180066371  call    cs:__imp_RaiseException
0x180066377  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18006637b  lea     rax, [rbp+57h+var_80]
0x18006637f  mov     rcx, [rbp+57h+var_78]
0x180066383  mov     r9d, ebx
0x180066386  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18006638b  mov     r8d, 14h
0x180066391  mov     rax, rsi
0x180066394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066399  mov     ebx, eax
0x18006639b  test    eax, eax
0x18006639d  jns     short loc_180066407
0x18006639f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663a6  cmp     rcx, r15
0x1800663a9  jz      short loc_1800663CB
0x1800663ab  test    byte ptr [rcx+1Ch], 4
0x1800663af  jz      short loc_1800663CB
0x1800663b1  cmp     byte ptr [rcx+19h], 2
0x1800663b5  jb      short loc_1800663CB
0x1800663b7  mov     rcx, [rcx+10h]
0x1800663bb  mov     edx, 5Dh ; ']'
0x1800663c0  mov     r9d, eax
0x1800663c3  mov     r8, r12
0x1800663c6  call    WPP_SF_d
0x1800663cb  mov     rcx, [rbp+5Fh]; this
0x1800663cf  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800663d6  mov     r9d, ebx; char *
0x1800663d9  mov     edx, 2DBh; void *
0x1800663de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800663e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663ea  cmp     rcx, r15
0x1800663ed  jz      loc_180066534
0x1800663f3  test    byte ptr [rcx+1Ch], 80h
0x1800663f7  jz      loc_180066534
0x1800663fd  mov     edx, 5Eh ; '^'
0x180066402  jmp     loc_18006631F
0x180066407  mov     rcx, qword ptr [rbp+57h+var_80]
0x18006640b  lea     r8, [rbp+57h+var_70]
0x18006640f  lea     rdx, _GUID_8d470579_96e4_412d_ad40_d9defb35ce86
0x180066416  mov     rax, [rcx]
0x180066419  mov     rax, [rax]
0x18006641c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066421  mov     ebx, eax
0x180066423  test    eax, eax
0x180066425  jns     short loc_18006648F
0x180066427  mov     rcx, cs:WPP_GLOBAL_Control
0x18006642e  cmp     rcx, r15
0x180066431  jz      short loc_180066453
0x180066433  test    byte ptr [rcx+1Ch], 4
0x180066437  jz      short loc_180066453
0x180066439  cmp     byte ptr [rcx+19h], 2
0x18006643d  jb      short loc_180066453
0x18006643f  mov     rcx, [rcx+10h]
0x180066443  mov     edx, 5Fh ; '_'
0x180066448  mov     r9d, eax
0x18006644b  mov     r8, r12
0x18006644e  call    WPP_SF_d
0x180066453  mov     rcx, [rbp+5Fh]; this
0x180066457  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006645e  mov     r9d, ebx; char *
0x180066461  mov     edx, 2E0h; void *
0x180066466  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006646b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066472  cmp     rcx, r15
0x180066475  jz      loc_180066534
0x18006647b  test    byte ptr [rcx+1Ch], 80h
0x18006647f  jz      loc_180066534
0x180066485  mov     edx, 60h ; '`'
0x18006648a  jmp     loc_18006631F
0x18006648f  mov     rcx, [rbp+57h+var_70]
0x180066493  lea     r8, [rbp+57h+hstringHeader]
0x180066497  movups  xmm0, xmmword ptr cs:CLSID_NcbBackgroundTask.Data1
0x18006649e  mov     edx, 1
0x1800664a3  mov     rax, [rcx]
0x1800664a6  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800664ab  mov     rax, [rax+30h]
0x1800664af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664b4  mov     ebx, eax
0x1800664b6  test    eax, eax
0x1800664b8  jns     short loc_18006651A
0x1800664ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800664c1  cmp     rcx, r15
0x1800664c4  jz      short loc_1800664E6
0x1800664c6  test    byte ptr [rcx+1Ch], 4
0x1800664ca  jz      short loc_1800664E6
0x1800664cc  cmp     byte ptr [rcx+19h], 2
0x1800664d0  jb      short loc_1800664E6
0x1800664d2  mov     rcx, [rcx+10h]
0x1800664d6  mov     edx, 61h ; 'a'
0x1800664db  mov     r9d, eax
0x1800664de  mov     r8, r12
0x1800664e1  call    WPP_SF_d
0x1800664e6  mov     rcx, [rbp+5Fh]; this
0x1800664ea  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800664f1  mov     r9d, ebx; char *
0x1800664f4  mov     edx, 2E4h; void *
0x1800664f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800664fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180066505  cmp     rcx, r15
0x180066508  jz      short loc_180066534
0x18006650a  test    byte ptr [rcx+1Ch], 80h
0x18006650e  jz      short loc_180066534
0x180066510  mov     edx, 62h ; 'b'
0x180066515  jmp     loc_18006631F
0x18006651a  mov     rax, qword ptr [rbp+57h+var_80]
0x18006651e  mov     [rdi+0E0h], rax
0x180066525  mov     qword ptr [rbp+57h+var_80], 0
0x18006652d  mov     rcx, cs:WPP_GLOBAL_Control
0x180066534  mov     rdx, [rbp+57h+var_78]
0x180066538  test    rdx, rdx
0x18006653b  jz      short loc_18006655B
0x18006653d  mov     rax, [rdx]
0x180066540  mov     rcx, rdx
0x180066543  mov     rax, [rax+10h]
0x180066547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006654c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066553  mov     [rbp+57h+var_78], 0
0x18006655b  mov     rdx, qword ptr [rbp+57h+var_80]
0x18006655f  test    rdx, rdx
0x180066562  jz      short loc_180066582
0x180066564  mov     rax, [rdx]
0x180066567  mov     rcx, rdx
0x18006656a  mov     rax, [rax+10h]
0x18006656e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066573  mov     rcx, cs:WPP_GLOBAL_Control
0x18006657a  mov     qword ptr [rbp+57h+var_80], 0
0x180066582  mov     rdx, [rbp+57h+var_70]
0x180066586  test    rdx, rdx
0x180066589  jz      short loc_1800665A9
0x18006658b  mov     rax, [rdx]
0x18006658e  mov     rcx, rdx
0x180066591  mov     rax, [rax+10h]
0x180066595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006659a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800665a1  mov     [rbp+57h+var_70], 0
0x1800665a9  cmp     rcx, r15
0x1800665ac  jz      short loc_1800665CE
0x1800665ae  test    byte ptr [rcx+1Ch], 4
0x1800665b2  jz      short loc_1800665CE
0x1800665b4  cmp     byte ptr [rcx+19h], 6
0x1800665b8  jb      short loc_1800665CE
0x1800665ba  mov     rcx, [rcx+10h]
0x1800665be  mov     edx, 63h ; 'c'
0x1800665c3  mov     r9d, ebx
0x1800665c6  mov     r8, r12
0x1800665c9  call    WPP_SF_d
0x1800665ce  mov     eax, ebx
0x1800665d0  mov     rcx, [rbp+57h+var_40]
0x1800665d4  xor     rcx, rsp; StackCookie
0x1800665d7  call    __security_check_cookie
0x1800665dc  add     rsp, 88h
0x1800665e3  pop     r15
0x1800665e5  pop     r12
0x1800665e7  pop     rdi
0x1800665e8  pop     rsi
0x1800665e9  pop     rbx
0x1800665ea  pop     rbp
0x1800665eb  retn
```
