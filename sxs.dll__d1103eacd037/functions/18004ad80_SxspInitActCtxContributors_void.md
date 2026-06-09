# SxspInitActCtxContributors(void)

- ea: `0x18004ad80`
- end: `0x18004b0ee`
- name: `?SxspInitActCtxContributors@@YAHXZ`
- size: `878`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ad50`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18004ad80`
- `0x18004b0f4`
- `0x18004b140`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004add6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aefc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004af3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004af7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004afb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aff8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b037`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b076`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b0b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004add6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ae7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aefc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004af3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004af7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004afb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aff8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b037`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b076`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b0b5`

## string_xrefs

- `0x18004ae8a`: `Builtin Compatibility Info contributor`
- `0x18004af86`: `Builtin COM Type Library redirection contributor`
- `0x18004af47`: `Builtin COM ProgId redirection contributor`
- `0x18004af08`: `Builtin COM Server Redirection contributor`
- `0x18004ae49`: `Builtin DLL Redirection contributor`
- `0x18004afc5`: `Builtin COM interface redirection contributor`

## pseudocode

```c
__int64 SxspInitActCtxContributors(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rdx
  unsigned int v1; // ecx
  unsigned int v2; // r8d
  char **v3; // rcx
  const struct _GUID *v4; // rdx
  const struct _GUID *v5; // rdx
  const struct _GUID *v6; // rdx
  const struct _GUID *v7; // rdx
  const struct _GUID *v8; // rdx
  const struct _GUID *v9; // rdx
  const struct _GUID *v10; // rdx
  const struct _GUID *v11; // rdx
  const struct _GUID *v12; // rdx
  const struct _GUID *v13; // rdx
  const struct _GUID *v14; // rdx
  unsigned int v15; // ebx
  int v17; // [rsp+30h] [rbp-48h] BYREF
  int v18; // [rsp+38h] [rbp-40h] BYREF
  __int64 v19; // [rsp+40h] [rbp-38h]
  __int64 *v20; // [rsp+48h] [rbp-30h]
  __int64 v21; // [rsp+50h] [rbp-28h]
  int v22; // [rsp+58h] [rbp-20h]
  unsigned int *v23; // [rsp+60h] [rbp-18h]

  v21 = 544438355;
  v17 = 0;
  v20 = &qword_180071A90;
  v19 = 0;
  v22 = 115;
  v18 = 1;
  v23 = (unsigned int *)&v17;
  CFrame::BaseEnter((CFrame *)&v18);
  SetLastError(0);
  if ( (unsigned int)FusionpInitializeCriticalSectionCommon(v1, v0, v2) )
  {
    SetLastError(0);
    if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                         (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspAssemblyMetadataContributorCallback,
                         v4,
                         1u,
                         1u,
                         L"Builtin Assembly Metadata Contributor") )
    {
      SetLastError(0);
      if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                           (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspDllRedirectionContributorCallback,
                           v5,
                           2u,
                           1u,
                           L"Builtin DLL Redirection contributor") )
      {
        SetLastError(0);
        if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                             (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspCompatibilityInfoContributorCallback,
                             v6,
                             0xBu,
                             1u,
                             L"Builtin Compatibility Info contributor") )
        {
          SetLastError(0);
          if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                               (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspWindowClassRedirectionContributorCallback,
                               v7,
                               3u,
                               1u,
                               L"Builtin Window Class Redirection contributor") )
          {
            SetLastError(0);
            if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                 (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspComClassRedirectionContributorCallback,
                                 v8,
                                 4u,
                                 2u,
                                 L"Builtin COM Server Redirection contributor") )
            {
              SetLastError(0);
              if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                   (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspComProgIdRedirectionContributorCallback,
                                   v9,
                                   7u,
                                   1u,
                                   L"Builtin COM ProgId redirection contributor") )
              {
                SetLastError(0);
                if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                     (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspComTypeLibRedirectionContributorCallback,
                                     v10,
                                     6u,
                                     2u,
                                     L"Builtin COM Type Library redirection contributor") )
                {
                  SetLastError(0);
                  if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                       (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspComInterfaceRedirectionContributorCallback,
                                       v11,
                                       5u,
                                       2u,
                                       L"Builtin COM interface redirection contributor") )
                  {
                    SetLastError(0);
                    if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                         (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspClrInteropContributorCallback,
                                         v12,
                                         9u,
                                         2u,
                                         L"Builtin NDP surrogate data contributor") )
                    {
                      SetLastError(0);
                      if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                           (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspApplicationSettingsContributorCallback,
                                           v13,
                                           0xAu,
                                           1u,
                                           L"Builtin application settings contributor") )
                      {
                        SetLastError(0);
                        if ( (unsigned int)SxspAddBuiltinActCtxContributor(
                                             (void (*)(union _ACTCTXCTB_CALLBACK_DATA *))SxspWinrtActivatableClassContributorCallback,
                                             v14,
                                             0xCu,
                                             1u,
                                             L"Builtin WinRT ActivatableClass contributor") )
                        {
                          SetLastError(0);
                          *v23 = 1;
                          goto LABEL_27;
                        }
                        v3 = off_18007A410;
                      }
                      else
                      {
                        v3 = off_18007A430;
                      }
                    }
                    else
                    {
                      v3 = off_18007A450;
                    }
                  }
                  else
                  {
                    v3 = off_18007A470;
                  }
                }
                else
                {
                  v3 = off_18007A490;
                }
              }
              else
              {
                v3 = off_18007A4B0;
              }
            }
            else
            {
              v3 = off_18007A4D0;
            }
          }
          else
          {
            v3 = off_18007A4F0;
          }
        }
        else
        {
          v3 = off_18007A510;
        }
      }
      else
      {
        v3 = off_18007A530;
      }
    }
    else
    {
      v3 = off_18007A550;
    }
  }
  else
  {
    v3 = off_180071AB0;
  }
  *v23 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v3);
LABEL_27:
  v15 = *v23;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v18);
  return v15;
}

```

## disassembly

```asm
0x18004ad80  push    rbp
0x18004ad82  push    rbx
0x18004ad83  push    rsi
0x18004ad84  push    rdi
0x18004ad85  mov     rbp, rsp
0x18004ad88  sub     rsp, 78h
0x18004ad8c  mov     rax, cs:__security_cookie
0x18004ad93  xor     rax, rsp
0x18004ad96  mov     [rbp+var_10], rax
0x18004ad9a  xor     ebx, ebx
0x18004ad9c  mov     [rbp+var_28], 20737853h
0x18004ada4  lea     rax, qword_180071A90
0x18004adab  mov     [rbp+var_48], ebx
0x18004adae  mov     [rbp+var_30], rax
0x18004adb2  lea     rcx, [rbp+var_40]; this
0x18004adb6  lea     rax, [rbp+var_48]
0x18004adba  mov     [rbp+var_38], rbx
0x18004adbe  lea     edi, [rbx+1]
0x18004adc1  mov     [rbp+var_20], 73h ; 's'
0x18004adc8  mov     [rbp+var_40], edi
0x18004adcb  mov     [rbp+var_18], rax
0x18004adcf  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004add4  xor     ecx, ecx; dwErrCode
0x18004add6  call    cs:__imp_SetLastError
0x18004addd  nop     dword ptr [rax+rax+00h]
0x18004ade2  call    ?FusionpInitializeCriticalSectionCommon@@YAHKPEAU_RTL_CRITICAL_SECTION@@K@Z; FusionpInitializeCriticalSectionCommon(ulong,_RTL_CRITICAL_SECTION *,ulong)
0x18004ade7  test    eax, eax
0x18004ade9  jnz     short loc_18004AE02
0x18004adeb  lea     rcx, off_180071AB0; struct _CALL_SITE_INFO *
0x18004adf2  mov     rax, [rbp+var_18]
0x18004adf6  mov     [rax], ebx
0x18004adf8  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004adfd  jmp     loc_18004B0C7
0x18004ae02  xor     ecx, ecx; dwErrCode
0x18004ae04  call    cs:__imp_SetLastError
0x18004ae0b  nop     dword ptr [rax+rax+00h]
0x18004ae10  lea     rax, aBuiltinAssembl; "Builtin Assembly Metadata Contributor"
0x18004ae17  mov     r9d, edi; unsigned int
0x18004ae1a  mov     r8d, edi; unsigned int
0x18004ae1d  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004ae22  lea     rcx, ?SxspAssemblyMetadataContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004ae29  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004ae2e  test    eax, eax
0x18004ae30  jnz     short loc_18004AE3B
0x18004ae32  lea     rcx, off_18007A550; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004ae39  jmp     short loc_18004ADF2
0x18004ae3b  xor     ecx, ecx; dwErrCode
0x18004ae3d  call    cs:__imp_SetLastError
0x18004ae44  nop     dword ptr [rax+rax+00h]
0x18004ae49  lea     rax, aBuiltinDllRedi; "Builtin DLL Redirection contributor"
0x18004ae50  mov     esi, 2
0x18004ae55  mov     r8d, esi; unsigned int
0x18004ae58  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004ae5d  mov     r9d, edi; unsigned int
0x18004ae60  lea     rcx, ?SxspDllRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004ae67  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004ae6c  test    eax, eax
0x18004ae6e  jnz     short loc_18004AE7C
0x18004ae70  lea     rcx, off_18007A530; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004ae77  jmp     loc_18004ADF2
0x18004ae7c  xor     ecx, ecx; dwErrCode
0x18004ae7e  call    cs:__imp_SetLastError
0x18004ae85  nop     dword ptr [rax+rax+00h]
0x18004ae8a  lea     rax, aBuiltinCompati; "Builtin Compatibility Info contributor"
0x18004ae91  mov     r9d, edi; unsigned int
0x18004ae94  mov     r8d, 0Bh; unsigned int
0x18004ae9a  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004ae9f  lea     rcx, ?SxspCompatibilityInfoContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004aea6  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004aeab  test    eax, eax
0x18004aead  jnz     short loc_18004AEBB
0x18004aeaf  lea     rcx, off_18007A510; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004aeb6  jmp     loc_18004ADF2
0x18004aebb  xor     ecx, ecx; dwErrCode
0x18004aebd  call    cs:__imp_SetLastError
0x18004aec4  nop     dword ptr [rax+rax+00h]
0x18004aec9  lea     rax, aBuiltinWindowC; "Builtin Window Class Redirection contri"...
0x18004aed0  mov     r9d, edi; unsigned int
0x18004aed3  mov     r8d, 3; unsigned int
0x18004aed9  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004aede  lea     rcx, ?SxspWindowClassRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004aee5  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004aeea  test    eax, eax
0x18004aeec  jnz     short loc_18004AEFA
0x18004aeee  lea     rcx, off_18007A4F0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004aef5  jmp     loc_18004ADF2
0x18004aefa  xor     ecx, ecx; dwErrCode
0x18004aefc  call    cs:__imp_SetLastError
0x18004af03  nop     dword ptr [rax+rax+00h]
0x18004af08  lea     rax, aBuiltinComServ; "Builtin COM Server Redirection contribu"...
0x18004af0f  mov     r9d, esi; unsigned int
0x18004af12  mov     r8d, 4; unsigned int
0x18004af18  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004af1d  lea     rcx, ?SxspComClassRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004af24  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004af29  test    eax, eax
0x18004af2b  jnz     short loc_18004AF39
0x18004af2d  lea     rcx, off_18007A4D0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004af34  jmp     loc_18004ADF2
0x18004af39  xor     ecx, ecx; dwErrCode
0x18004af3b  call    cs:__imp_SetLastError
0x18004af42  nop     dword ptr [rax+rax+00h]
0x18004af47  lea     rax, aBuiltinComProg; "Builtin COM ProgId redirection contribu"...
0x18004af4e  mov     r9d, edi; unsigned int
0x18004af51  mov     r8d, 7; unsigned int
0x18004af57  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004af5c  lea     rcx, ?SxspComProgIdRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004af63  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004af68  test    eax, eax
0x18004af6a  jnz     short loc_18004AF78
0x18004af6c  lea     rcx, off_18007A4B0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004af73  jmp     loc_18004ADF2
0x18004af78  xor     ecx, ecx; dwErrCode
0x18004af7a  call    cs:__imp_SetLastError
0x18004af81  nop     dword ptr [rax+rax+00h]
0x18004af86  lea     rax, aBuiltinComType; "Builtin COM Type Library redirection co"...
0x18004af8d  mov     r9d, esi; unsigned int
0x18004af90  mov     r8d, 6; unsigned int
0x18004af96  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004af9b  lea     rcx, ?SxspComTypeLibRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004afa2  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004afa7  test    eax, eax
0x18004afa9  jnz     short loc_18004AFB7
0x18004afab  lea     rcx, off_18007A490; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004afb2  jmp     loc_18004ADF2
0x18004afb7  xor     ecx, ecx; dwErrCode
0x18004afb9  call    cs:__imp_SetLastError
0x18004afc0  nop     dword ptr [rax+rax+00h]
0x18004afc5  lea     rax, aBuiltinComInte; "Builtin COM interface redirection contr"...
0x18004afcc  mov     r9d, esi; unsigned int
0x18004afcf  mov     r8d, 5; unsigned int
0x18004afd5  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004afda  lea     rcx, ?SxspComInterfaceRedirectionContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004afe1  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004afe6  test    eax, eax
0x18004afe8  jnz     short loc_18004AFF6
0x18004afea  lea     rcx, off_18007A470; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004aff1  jmp     loc_18004ADF2
0x18004aff6  xor     ecx, ecx; dwErrCode
0x18004aff8  call    cs:__imp_SetLastError
0x18004afff  nop     dword ptr [rax+rax+00h]
0x18004b004  lea     rax, aBuiltinNdpSurr; "Builtin NDP surrogate data contributor"
0x18004b00b  mov     r9d, esi; unsigned int
0x18004b00e  mov     r8d, 9; unsigned int
0x18004b014  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004b019  lea     rcx, ?SxspClrInteropContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004b020  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004b025  test    eax, eax
0x18004b027  jnz     short loc_18004B035
0x18004b029  lea     rcx, off_18007A450; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004b030  jmp     loc_18004ADF2
0x18004b035  xor     ecx, ecx; dwErrCode
0x18004b037  call    cs:__imp_SetLastError
0x18004b03e  nop     dword ptr [rax+rax+00h]
0x18004b043  lea     rax, aBuiltinApplica; "Builtin application settings contributo"...
0x18004b04a  mov     r9d, edi; unsigned int
0x18004b04d  mov     r8d, 0Ah; unsigned int
0x18004b053  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004b058  lea     rcx, ?SxspApplicationSettingsContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004b05f  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004b064  test    eax, eax
0x18004b066  jnz     short loc_18004B074
0x18004b068  lea     rcx, off_18007A430; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004b06f  jmp     loc_18004ADF2
0x18004b074  xor     ecx, ecx; dwErrCode
0x18004b076  call    cs:__imp_SetLastError
0x18004b07d  nop     dword ptr [rax+rax+00h]
0x18004b082  lea     rax, aBuiltinWinrtAc; "Builtin WinRT ActivatableClass contribu"...
0x18004b089  mov     r9d, edi; unsigned int
0x18004b08c  mov     r8d, 0Ch; unsigned int
0x18004b092  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004b097  lea     rcx, ?SxspWinrtActivatableClassContributorCallback@@YAXPEAT_ACTCTXCTB_CALLBACK_DATA@@@Z; void (*)(union _ACTCTXCTB_CALLBACK_DATA *)
0x18004b09e  call    ?SxspAddBuiltinActCtxContributor@@YAHP6AXPEAT_ACTCTXCTB_CALLBACK_DATA@@@ZPEBU_GUID@@KKPEBG@Z; SxspAddBuiltinActCtxContributor(void (*)(_ACTCTXCTB_CALLBACK_DATA *),_GUID const *,ulong,ulong,ushort const *)
0x18004b0a3  test    eax, eax
0x18004b0a5  jnz     short loc_18004B0B3
0x18004b0a7  lea     rcx, off_18007A410; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004b0ae  jmp     loc_18004ADF2
0x18004b0b3  xor     ecx, ecx; dwErrCode
0x18004b0b5  call    cs:__imp_SetLastError
0x18004b0bc  nop     dword ptr [rax+rax+00h]
0x18004b0c1  mov     rax, [rbp+var_18]
0x18004b0c5  mov     [rax], edi
0x18004b0c7  mov     rax, [rbp+var_18]
0x18004b0cb  lea     rcx, [rbp+var_40]; this
0x18004b0cf  mov     ebx, [rax]
0x18004b0d1  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18004b0d6  mov     eax, ebx
0x18004b0d8  mov     rcx, [rbp+var_10]
0x18004b0dc  xor     rcx, rsp; StackCookie
0x18004b0df  call    __security_check_cookie
0x18004b0e4  add     rsp, 78h
0x18004b0e8  pop     rdi
0x18004b0e9  pop     rsi
0x18004b0ea  pop     rbx
0x18004b0eb  pop     rbp
0x18004b0ec  retn
```
