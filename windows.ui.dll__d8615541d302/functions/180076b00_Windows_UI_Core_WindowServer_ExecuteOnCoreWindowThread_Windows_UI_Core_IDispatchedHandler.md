# Windows::UI::Core::WindowServer::ExecuteOnCoreWindowThread(Windows::UI::Core::IDispatchedHandler *)

- ea: `0x180076b00`
- end: `0x180076cc3`
- name: `?ExecuteOnCoreWindowThread@WindowServer@Core@UI@Windows@@UEAAJPEAUIDispatchedHandler@234@@Z`
- size: `451`
- prototype: `int(Windows::UI::Core::WindowServer *__hidden this, struct Windows::UI::Core::IDispatchedHandler *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180033a50`
- `0x1800581b8`
- `0x180076b00`
- `0x18007d970`
- `0x18007e824`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076b65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076b65`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsGUIThread` at `0x180076b8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsGUIThread` at `0x180076b8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180076ba7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180076ba7`

## string_xrefs

- `0x180076b4c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180076bd7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180076c43`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180076c74`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::ExecuteOnCoreWindowThread(
        Windows::UI::Core::WindowServer *this,
        __int64 (__fastcall ***a2)(struct Windows::UI::Core::IDispatchedHandler *, GUID *, __int64 *))
{
  __int64 (__fastcall **v2)(struct Windows::UI::Core::IDispatchedHandler *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(struct Windows::UI::Core::IDispatchedHandler *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int LastError; // ebx
  unsigned int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  wil *v13; // rbx
  int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  int v17; // r9d
  int v18; // edi
  const char *v19; // r9
  int v21; // [rsp+20h] [rbp-30h]
  _QWORD v22[2]; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+40h] [rbp-10h]
  int v24; // [rsp+44h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  wil *v26; // [rsp+78h] [rbp+28h] BYREF
  __int64 v27; // [rsp+80h] [rbp+30h] BYREF

  v2 = *a2;
  v27 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
  v6 = v5((struct Windows::UI::Core::IDispatchedHandler *)a2, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, &v27);
  LastError = v6;
  if ( v6 >= 0 )
  {
    if ( GetCurrentThreadId() == *((_DWORD *)this + 38) )
    {
      v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::UI::Core::IDispatchedHandler *, GUID *, __int64 *)))(*a2)[3])(a2);
LABEL_5:
      LastError = v8;
      goto LABEL_19;
    }
    if ( IsGUIThread(0) )
    {
      v8 = SendMessageW(*((HWND *)this + 405), 0x723u, 0, (LPARAM)a2);
      goto LABEL_5;
    }
    v26 = 0;
    v9 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           &v26,
           1);
    LastError = v9;
    if ( v9 >= 0 )
    {
      v12 = *((_QWORD *)this + 18);
      v13 = v26;
      v24 = 0;
      v22[0] = a2;
      v22[1] = v26;
      v23 = -2147418113;
      v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(void *), _QWORD *, __int64))(**(_QWORD **)(v12 + 768)
                                                                                                 + 152LL))(
              *(_QWORD *)(v12 + 768),
              Windows::UI::Core::WindowServer::InvokeOnCoreWindowCallback,
              v22,
              3);
      v18 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1317,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)(unsigned int)v14,
          v21);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
        LastError = v18;
        goto LABEL_19;
      }
      if ( !wil::handle_wait(v13, v15, v16, v17) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1319,
                      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
                      v19);
        goto LABEL_11;
      }
      LastError = v23;
      if ( v23 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
        LastError = 0;
        goto LABEL_19;
      }
      v10 = (unsigned int)v23;
      v11 = 4891;
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 4874;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)v10,
      v21);
LABEL_11:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12E6,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
    (const char *)(unsigned int)v6,
    v21);
LABEL_19:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
  return LastError;
}

```

## disassembly

```asm
0x180076b00  mov     [rsp-18h+arg_0], rbx
0x180076b05  push    rbp
0x180076b06  push    rsi
0x180076b07  push    rdi
0x180076b08  mov     rbp, rsp
0x180076b0b  sub     rsp, 50h
0x180076b0f  mov     rax, [rdx]
0x180076b12  mov     rsi, rcx
0x180076b15  lea     rcx, [rbp+arg_10]
0x180076b19  mov     [rbp+arg_10], 0
0x180076b21  mov     rdi, rdx
0x180076b24  mov     rbx, [rax]
0x180076b27  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180076b2c  lea     r8, [rbp+arg_10]
0x180076b30  mov     rcx, rdi
0x180076b33  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180076b3a  mov     rax, rbx
0x180076b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b42  mov     ebx, eax
0x180076b44  test    eax, eax
0x180076b46  jns     short loc_180076B65
0x180076b48  mov     rcx, [rbp+18h]; this
0x180076b4c  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180076b53  mov     r9d, eax; char *
0x180076b56  mov     edx, 12E6h; void *
0x180076b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076b60  jmp     loc_180076CAB
0x180076b65  call    cs:__imp_GetCurrentThreadId
0x180076b6b  cmp     eax, [rsi+98h]
0x180076b71  jnz     short loc_180076B89
0x180076b73  mov     rax, [rdi]
0x180076b76  mov     rcx, rdi
0x180076b79  mov     rax, [rax+18h]
0x180076b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b82  mov     ebx, eax
0x180076b84  jmp     loc_180076CAB
0x180076b89  xor     ecx, ecx; bConvert
0x180076b8b  call    cs:__imp_IsGUIThread
0x180076b91  test    eax, eax
0x180076b93  jz      short loc_180076BAF
0x180076b95  mov     rcx, [rsi+0CA8h]; hWnd
0x180076b9c  mov     r9, rdi; lParam
0x180076b9f  xor     r8d, r8d; wParam
0x180076ba2  mov     edx, 723h; Msg
0x180076ba7  call    cs:__imp_SendMessageW
0x180076bad  jmp     short loc_180076B82
0x180076baf  mov     edx, 1
0x180076bb4  mov     [rbp+arg_8], 0
0x180076bbc  lea     rcx, [rbp+arg_8]
0x180076bc0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180076bc5  mov     ebx, eax
0x180076bc7  test    eax, eax
0x180076bc9  jns     short loc_180076BF1
0x180076bcb  mov     r9d, eax; char *
0x180076bce  mov     edx, 130Ah; void *
0x180076bd3  mov     rcx, [rbp+18h]; this
0x180076bd7  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180076bde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076be3  lea     rcx, [rbp+arg_8]
0x180076be7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180076bec  jmp     loc_180076CAB
0x180076bf1  mov     rax, [rsi+90h]
0x180076bf8  lea     r8, [rbp+var_20]
0x180076bfc  mov     rbx, [rbp+arg_8]
0x180076c00  lea     rdx, ?InvokeOnCoreWindowCallback@WindowServer@Core@UI@Windows@@CAJPEAX@Z; Windows::UI::Core::WindowServer::InvokeOnCoreWindowCallback(void *)
0x180076c07  mov     [rbp+var_C], 0
0x180076c0e  mov     r9d, 3
0x180076c14  mov     [rbp+var_20], rdi
0x180076c18  mov     [rbp+var_18], rbx
0x180076c1c  mov     [rbp+var_10], 8000FFFFh
0x180076c23  mov     rcx, [rax+300h]
0x180076c2a  mov     rax, [rcx]
0x180076c2d  mov     rax, [rax+98h]
0x180076c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c39  mov     edi, eax
0x180076c3b  test    eax, eax
0x180076c3d  jns     short loc_180076C64
0x180076c3f  mov     rcx, [rbp+18h]; this
0x180076c43  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180076c4a  mov     r9d, eax; char *
0x180076c4d  mov     edx, 1317h; void *
0x180076c52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076c57  lea     rcx, [rbp+arg_8]
0x180076c5b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180076c60  mov     ebx, edi
0x180076c62  jmp     short loc_180076CAB
0x180076c64  mov     rcx, rbx; this
0x180076c67  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180076c6c  test    al, al
0x180076c6e  jnz     short loc_180076C8C
0x180076c70  mov     rcx, [rbp+18h]; this
0x180076c74  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180076c7b  mov     edx, 1319h; void *
0x180076c80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180076c85  mov     ebx, eax
0x180076c87  jmp     loc_180076BE3
0x180076c8c  mov     ebx, [rbp+var_10]
0x180076c8f  test    ebx, ebx
0x180076c91  jns     short loc_180076CA0
0x180076c93  mov     r9d, ebx
0x180076c96  mov     edx, 131Bh
0x180076c9b  jmp     loc_180076BD3
0x180076ca0  lea     rcx, [rbp+arg_8]
0x180076ca4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180076ca9  xor     ebx, ebx
0x180076cab  lea     rcx, [rbp+arg_10]
0x180076caf  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180076cb4  mov     eax, ebx
0x180076cb6  mov     rbx, [rsp+50h+arg_0]
0x180076cbb  add     rsp, 50h
0x180076cbf  pop     rdi
0x180076cc0  pop     rsi
0x180076cc1  pop     rbp
0x180076cc2  retn
```
