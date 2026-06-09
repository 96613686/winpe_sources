# CLightDismissClientStore::Register(LIGHT_DISMISS_POLICY,ILightDismissNotification *,ulong *)

- ea: `0x180017eb0`
- end: `0x1800184a5`
- name: `?Register@CLightDismissClientStore@@UEAAJULIGHT_DISMISS_POLICY@@PEAUILightDismissNotification@@PEAK@Z`
- size: `1525`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800169b8`
- `0x180016c10`
- `0x180017980`
- `0x180017eb0`
- `0x1800184ac`
- `0x180018548`
- `0x180018630`
- `0x180018d68`
- `0x180018dcc`
- `0x180018e10`
- `0x180018e84`
- `0x180018f44`
- `0x180019008`
- `0x180019218`
- `0x180027d58`
- `0x1800328a0`
- `0x1800361f4`
- `0x180036350`
- `0x18003636c`
- `0x18003d244`
- `0x18003f298`
- `0x1800403f0`
- `0x180046a30`
- `0x18004abc8`
- `0x18004d98c`
- `0x180054130`
- `0x180059b4c`
- `0x180083f00`
- `0x180084540`
- `0x1800845a4`
- `0x1800846a8`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018265`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180018265`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800182fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800182fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001839c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001839c`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180018338`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180018338`
- `USER32!GetPropW` at `0x18001811f`
- `USER32!GetPropW` at `0x18001811f`
- `USER32!GetWindow` at `0x180018101`
- `USER32!GetWindow` at `0x180018101`
- `USER32!DestroyWindow` at `0x180018406`
- `USER32!DestroyWindow` at `0x180018406`
- `USER32!GetWindowThreadProcessId` at `0x180017fc4`
- `USER32!GetWindowThreadProcessId` at `0x18001823a`
- `USER32!GetWindowThreadProcessId` at `0x180017fc4`
- `USER32!GetWindowThreadProcessId` at `0x18001823a`

## pseudocode

```c
__int64 __fastcall CLightDismissClientStore::Register(__int64 a1, int *a2, __int64 a3, _DWORD *a4)
{
  int v8; // edx
  char *v9; // rax
  char *v10; // rdi
  __int64 v11; // rcx
  int v12; // r15d
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  int v15; // ecx
  int CallingProcessId; // ebx
  HWND *v17; // rbx
  __int64 i; // rbx
  HWND v19; // rbx
  CLightDismissClientStore *v20; // rcx
  HWND Window; // r13
  unsigned __int64 v22; // rbx
  _QWORD *v23; // r15
  CLightDismissClientStore::CLIENT_INFO *v24; // r14
  struct CLightDismissClientStore::CLIENT_INFO *NodeInChain; // rax
  struct CLightDismissClientStore::CLIENT_INFO *v26; // r14
  __int64 v27; // rbx
  unsigned int v28; // edx
  struct CLightDismissClientStore::CLIENT_INFO **v29; // rax
  __int64 v30; // rdx
  char v31; // r14
  unsigned __int64 v32; // r15
  DWORD ProcessId; // eax
  DWORD v34; // r8d
  __int64 v35; // rdx
  __int64 v36; // rcx
  HANDLE v37; // rax
  void *v38; // r15
  __int64 v39; // r13
  __int64 v40; // rdx
  __int64 *v41; // rdx
  int v42; // eax
  DWORD dwProcessId[2]; // [rsp+30h] [rbp-D0h] BYREF
  HWND *v45; // [rsp+38h] [rbp-C8h]
  _DWORD *v46; // [rsp+40h] [rbp-C0h]
  _QWORD *v47; // [rsp+48h] [rbp-B8h]
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h]
  _DWORD *v50; // [rsp+60h] [rbp-A0h]
  void **v51; // [rsp+70h] [rbp-90h] BYREF
  char v52[272]; // [rsp+78h] [rbp-88h] BYREF
  char v53[8]; // [rsp+188h] [rbp+88h] BYREF
  char v54[48]; // [rsp+190h] [rbp+90h] BYREF

  v50 = a4;
  *a4 = 0;
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v51,
    "LightDismissRegister");
  v8 = *(_DWORD *)(a1 + 152);
  v51 = &LightDismissFrameworkTelemetry::LightDismissRegister::`vftable';
  LightDismissFrameworkTelemetry::LightDismissRegister::StartActivity(
    (LightDismissFrameworkTelemetry::LightDismissRegister *)&v51,
    v8);
  if ( !*(_DWORD *)(a1 + 152) )
  {
    CallingProcessId = 0;
    *a4 = 1;
    goto LABEL_81;
  }
  v9 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    CallingProcessId = -2147024882;
    goto LABEL_81;
  }
  v11 = *((_QWORD *)a2 + 1);
  v12 = *a2;
  *((_QWORD *)v9 + 4) = 0;
  *(_DWORD *)v9 = v12;
  v49 = v11;
  v45 = (HWND *)(v9 + 8);
  *((_QWORD *)v9 + 1) = v11;
  if ( *((_QWORD *)v9 + 4) != a3 )
  {
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    v13 = *((_QWORD *)v10 + 4);
    *((_QWORD *)v10 + 4) = a3;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *((_DWORD *)v10 + 4) = ++*(_DWORD *)(a1 + 48);
  v46 = v10 + 16;
  if ( GetWindowThreadProcessId(*v45, (LPDWORD)v10 + 5) )
  {
    CallingProcessId = anonymous_namespace_::GetCallingProcessId(v10 + 24);
    if ( CallingProcessId >= 0 )
    {
      v17 = v45;
      if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
        McTemplateU0pdd_EventWriteTransfer(v15, (_DWORD)v14, (unsigned int)*v45, *((_DWORD *)v10 + 5), v12);
      LightDismissFrameworkTelemetry::LightDismissRegister::StartFlags<unsigned long &>(&v51, a2);
      *((_QWORD *)v10 + 6) = 0;
      *(_QWORD *)dwProcessId = v10 + 48;
      *((_QWORD *)v10 + 7) = 0;
      *(_DWORD *)(a1 + 24) = 5;
      *(_DWORD *)(a1 + 164) = 0;
      v47 = v10 + 56;
      if ( (*(_DWORD *)v10 & 4) != 0 )
      {
        for ( i = *(_QWORD *)(a1 + 96);
              (int)--i >= 0;
              CLightDismissClientStore::_FilterChain(
                (CLightDismissClientStore *)a1,
                *(struct CLightDismissClientStore::CLIENT_INFO **)(*(_QWORD *)(a1 + 88) + 8 * i),
                4u,
                0) )
        {
          ;
        }
        CLightDismissClientStore::_UpdateOverlayRegion((CLightDismissClientStore *)a1);
        CLightDismissClientStore::_DismissClients((CLightDismissClientStore *)a1);
        v17 = v45;
      }
      else if ( (*(_DWORD *)v10 & 8) != 0 )
      {
        CLightDismissClientStore::_HandleDialog((CLightDismissClientStore *)a1, *v17);
      }
      else if ( anonymous_namespace_::GetOwner(*v17) )
      {
        *(_DWORD *)(a1 + 24) = 2;
        CLightDismissClientStore::DismissAllInactiveClients((CLightDismissClientStore *)a1, *v17);
      }
      if ( (*(_DWORD *)v10 & 0x100) != 0 )
        *(_DWORD *)(a1 + 164) = 1;
      if ( (*(_DWORD *)v10 & 0x1000) != 0 )
        *(_DWORD *)(a1 + 168) = 18;
      else
        *(_DWORD *)(a1 + 168) = (*(_DWORD *)v10 & 0x200) != 0 ? 6 : 3;
      *(_DWORD *)(a1 + 156) = (*(_DWORD *)v10 >> 10) & 1;
      v19 = *v17;
      Window = GetWindow(v19, 4u);
      if ( !Window )
        Window = (HWND)GetPropW(v19, L"Shell_Logical_Owner_Window_Prop");
      v22 = 0;
      v23 = (_QWORD *)(a1 + 88);
      while ( 1 )
      {
        v24 = (CLightDismissClientStore::CLIENT_INFO *)v10;
        if ( v22 >= *(_QWORD *)(a1 + 96) )
          break;
        v23 = (_QWORD *)(a1 + 88);
        NodeInChain = CLightDismissClientStore::_GetNodeInChain(
                        v20,
                        *(struct CLightDismissClientStore::CLIENT_INFO **)(*(_QWORD *)(a1 + 88) + 8 * v22),
                        Window);
        v26 = NodeInChain;
        if ( NodeInChain )
        {
          v27 = *((_QWORD *)NodeInChain + 7);
          v48 = v27;
          if ( v27 )
          {
            if ( *(HWND *)(v27 + 8) == *v45 )
            {
              *v46 = *(_DWORD *)(v27 + 16);
              *v47 = *(_QWORD *)(v27 + 56);
              CTSimpleArray<CLightDismissClientStore::CLIENT_INFO *,4294967294,CTPolicyCoTaskMem<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardCompareHelper<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardMergeHelper<CLightDismissClientStore::CLIENT_INFO *>>::Remove(
                a1 + 88,
                &v48);
              CLightDismissClientStore::CLIENT_INFO::`scalar deleting destructor'(
                (CLightDismissClientStore::CLIENT_INFO *)v27,
                v28);
            }
            else
            {
              *(_DWORD *)(a1 + 24) = 5;
              CLightDismissClientStore::_RemoveChain(
                (CLightDismissClientStore *)a1,
                (struct CLightDismissClientStore::CLIENT_INFO *)v27);
            }
          }
          v29 = *(struct CLightDismissClientStore::CLIENT_INFO ***)dwProcessId;
          *((_QWORD *)v26 + 7) = v10;
          *v29 = v26;
          goto LABEL_43;
        }
        ++v22;
      }
      if ( **(_QWORD **)dwProcessId )
        goto LABEL_43;
      v30 = v23[1];
      CallingProcessId = 0;
      if ( v30 != v23[3]
        || (CallingProcessId = CTSimpleArray<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>>::_EnsureCapacity(
                                 v23,
                                 v30 + 1),
            CallingProcessId >= 0) )
      {
        v14 = (_QWORD *)(*v23 + 8 * v23[1]++);
        if ( !v14 )
          goto LABEL_43;
        *v14 = v10;
      }
      if ( CallingProcessId < 0 )
        goto LABEL_72;
LABEL_43:
      CallingProcessId = CLightDismissClientStore::_CreateMessageWindow((CLightDismissClientStore *)a1);
      if ( CallingProcessId < 0 )
        goto LABEL_67;
      CallingProcessId = 0;
      dwProcessId[0] = 0;
      GetWindowThreadProcessId(*v45, dwProcessId);
      v31 = 0;
      v32 = 0;
      if ( *(_QWORD *)(a1 + 64) )
      {
        do
        {
          ProcessId = GetProcessId(*(HANDLE *)(*(_QWORD *)(a1 + 56) + 16 * v32 + 8));
          v34 = dwProcessId[0];
          if ( ProcessId == dwProcessId[0] )
            v31 = 1;
          ++v32;
        }
        while ( v32 < *(_QWORD *)(a1 + 64) );
        if ( v31 )
          goto LABEL_49;
      }
      else
      {
        v34 = dwProcessId[0];
      }
      v37 = OpenProcess(0x101000u, 0, v34);
      v38 = v37;
      if ( v37 )
      {
        v39 = RegisterWaitForSingleObjectEx(v37, anonymous_namespace_::WaitCallback, dwProcessId[0], 0xFFFFFFFFLL, 24);
        if ( v39 )
        {
          v40 = *(_QWORD *)(a1 + 64);
          if ( v40 != *(_QWORD *)(a1 + 80)
            || (CallingProcessId = CTSimpleArray<SmartXmlnsDefinition,4294967294,CTPolicyCoTaskMem<SmartXmlnsDefinition>,CSimpleArrayStandardCompareHelper<SmartXmlnsDefinition>,CSimpleArrayStandardMergeHelper<SmartXmlnsDefinition>>::_EnsureCapacity(
                                     a1 + 56,
                                     v40 + 1),
                CallingProcessId >= 0) )
          {
            ++*(_QWORD *)(a1 + 64);
            v41 = (__int64 *)(16LL * *(_QWORD *)(a1 + 64) + *(_QWORD *)(a1 + 56) - 16LL);
            if ( v41 )
            {
              *v41 = v39;
              v41[1] = (__int64)v38;
            }
          }
        }
        else
        {
          CallingProcessId = ResultFromKnownLastError();
        }
        if ( CallingProcessId < 0 )
        {
          CloseHandle(v38);
          goto LABEL_67;
        }
LABEL_50:
        CallingProcessId = CLightDismissClientStore::_CreateIMEWinEventHook((CLightDismissClientStore *)a1);
        if ( CallingProcessId >= 0 )
        {
          CallingProcessId = CLightDismissClientStore::_UpdateOverlayRegion((CLightDismissClientStore *)a1);
          if ( CallingProcessId >= 0 )
          {
            if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
              McTemplateU0p_EventWriteTransfer(v36, v35, v49);
            *v50 = *(_DWORD *)(a1 + 48);
            if ( (*v10 & 2) != 0 )
              CLightDismissClientStore::_HandleNewFocusLostObject(
                (CLightDismissClientStore *)a1,
                (struct CLightDismissClientStore::CLIENT_INFO *)v10);
            goto LABEL_78;
          }
        }
LABEL_67:
        if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(
            &MICROSOFT_WINDOWSUIIMMERSIVE_PUBLISHER_Context,
            Popup_LightDismiss_Failure,
            (unsigned int)CallingProcessId);
        v42 = 10;
        if ( CallingProcessId != -2147023496 )
          v42 = 1;
        *(_DWORD *)(a1 + 24) = v42;
        CLightDismissClientStore::_RemoveChain(
          (CLightDismissClientStore *)a1,
          (struct CLightDismissClientStore::CLIENT_INFO *)v10);
        v24 = 0;
LABEL_72:
        if ( v24 )
          goto LABEL_76;
        goto LABEL_77;
      }
      CallingProcessId = ResultFromKnownLastError();
LABEL_49:
      if ( CallingProcessId < 0 )
        goto LABEL_67;
      goto LABEL_50;
    }
  }
  else
  {
    CallingProcessId = -2147024809;
  }
  v24 = (CLightDismissClientStore::CLIENT_INFO *)v10;
LABEL_76:
  CLightDismissClientStore::CLIENT_INFO::`scalar deleting destructor'(v24, (unsigned int)v14);
LABEL_77:
  DestroyWindow(*(HWND *)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
LABEL_78:
  CLightDismissClientStore::_DismissClients((CLightDismissClientStore *)a1);
LABEL_81:
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v51,
    (unsigned int)CallingProcessId);
  v51 = &LightDismissFrameworkTelemetry::LightDismissRegister::`vftable';
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v51);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v54);
  wil::details::shared_object<wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v53);
  wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(v52);
  return (unsigned int)CallingProcessId;
}

```

## disassembly

```asm
0x180017eb0  mov     [rsp-8+arg_10], rbx
0x180017eb5  push    rbp
0x180017eb6  push    rsi
0x180017eb7  push    rdi
0x180017eb8  push    r12
0x180017eba  push    r13
0x180017ebc  push    r14
0x180017ebe  push    r15
0x180017ec0  lea     rbp, [rsp-0D0h]
0x180017ec8  sub     rsp, 1D0h
0x180017ecf  mov     rax, cs:__security_cookie
0x180017ed6  xor     rax, rsp
0x180017ed9  mov     [rbp+100h+var_40], rax
0x180017ee0  mov     r14, rdx
0x180017ee3  mov     [rsp+200h+var_1A0], r9
0x180017ee8  mov     rsi, rcx
0x180017eeb  lea     rdx, aLightdismissre; "LightDismissRegister"
0x180017ef2  xor     r12d, r12d
0x180017ef5  lea     rcx, [rsp+200h+var_190]
0x180017efa  mov     [r9], r12d
0x180017efd  mov     rdi, r9
0x180017f00  mov     rbx, r8
0x180017f03  call    ??0?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017f08  mov     edx, [rsi+98h]; int
0x180017f0e  lea     rax, ??_7LightDismissRegister@LightDismissFrameworkTelemetry@@6B@; const LightDismissFrameworkTelemetry::LightDismissRegister::`vftable'
0x180017f15  lea     rcx, [rsp+200h+var_190]; this
0x180017f1a  mov     [rsp+200h+var_190], rax
0x180017f1f  call    ?StartActivity@LightDismissRegister@LightDismissFrameworkTelemetry@@QEAAXH@Z; LightDismissFrameworkTelemetry::LightDismissRegister::StartActivity(int)
0x180017f24  cmp     [rsi+98h], r12d
0x180017f2b  jz      loc_18001842B
0x180017f31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017f38  lea     ecx, [r12+40h]; unsigned __int64
0x180017f3d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017f42  mov     rdi, rax
0x180017f45  test    rax, rax
0x180017f48  jz      loc_180018424
0x180017f4e  mov     rcx, [r14+8]
0x180017f52  mov     r15d, [r14]
0x180017f55  mov     [rax+20h], r12
0x180017f59  mov     [rax], r15d
0x180017f5c  add     rax, 8
0x180017f60  mov     [rsp+200h+var_1A8], rcx
0x180017f65  mov     [rsp+200h+var_1C8], rax
0x180017f6a  mov     [rax], rcx
0x180017f6d  cmp     [rdi+20h], rbx
0x180017f71  jz      short loc_180017FA0
0x180017f73  test    rbx, rbx
0x180017f76  jz      short loc_180017F87
0x180017f78  mov     rax, [rbx]
0x180017f7b  mov     rcx, rbx
0x180017f7e  mov     rax, [rax+8]
0x180017f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f87  mov     rcx, [rdi+20h]
0x180017f8b  mov     [rdi+20h], rbx
0x180017f8f  test    rcx, rcx
0x180017f92  jz      short loc_180017FA0
0x180017f94  mov     rax, [rcx]
0x180017f97  mov     rax, [rax+10h]
0x180017f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fa0  lea     rcx, [rdi+10h]
0x180017fa4  mov     r12d, 1
0x180017faa  add     [rsi+30h], r12d
0x180017fae  lea     rdx, [rdi+14h]; lpdwProcessId
0x180017fb2  mov     eax, [rsi+30h]
0x180017fb5  mov     [rcx], eax
0x180017fb7  mov     rax, [rsp+200h+var_1C8]
0x180017fbc  mov     [rsp+200h+var_1C0], rcx
0x180017fc1  mov     rcx, [rax]; hWnd
0x180017fc4  call    cs:__imp_GetWindowThreadProcessId
0x180017fcb  nop     dword ptr [rax+rax+00h]
0x180017fd0  test    eax, eax
0x180017fd2  jz      loc_1800183F2
0x180017fd8  lea     rcx, [rdi+18h]
0x180017fdc  call    _anonymous_namespace___GetCallingProcessId
0x180017fe1  mov     ebx, eax
0x180017fe3  test    eax, eax
0x180017fe5  js      loc_1800183F7
0x180017feb  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, r12b
0x180017ff2  mov     rbx, [rsp+200h+var_1C8]
0x180017ff7  jz      short loc_18001800A
0x180017ff9  mov     r9d, [rdi+14h]
0x180017ffd  mov     r8, [rbx]
0x180018000  mov     [rsp+200h+var_1E0], r15d
0x180018005  call    McTemplateU0pdd_EventWriteTransfer
0x18001800a  mov     rdx, r14
0x18001800d  lea     rcx, [rsp+200h+var_190]
0x180018012  call    ??$StartFlags@AEAK@LightDismissRegister@LightDismissFrameworkTelemetry@@QEAAXAEAK@Z; LightDismissFrameworkTelemetry::LightDismissRegister::StartFlags<ulong &>(ulong &)
0x180018017  xor     r14d, r14d
0x18001801a  lea     rax, [rdi+30h]
0x18001801e  mov     [rax], r14
0x180018021  mov     qword ptr [rsp+200h+dwProcessId], rax
0x180018026  lea     rax, [rdi+38h]
0x18001802a  mov     [rax], r14
0x18001802d  mov     dword ptr [rsi+18h], 5
0x180018034  lea     r15d, [r14+4]
0x180018038  mov     [rsi+0A4h], r14d
0x18001803f  mov     [rsp+200h+var_1B8], rax
0x180018044  mov     eax, [rdi]
0x180018046  test    r15b, al
0x180018049  jz      short loc_180018082
0x18001804b  mov     rbx, [rsi+60h]
0x18001804f  jmp     short loc_180018064
0x180018051  mov     rdx, [rsi+58h]
0x180018055  xor     r9d, r9d; unsigned int
0x180018058  mov     r8d, r15d; unsigned int
0x18001805b  mov     rdx, [rdx+rbx*8]; struct CLightDismissClientStore::CLIENT_INFO *
0x18001805f  call    ?_FilterChain@CLightDismissClientStore@@AEAAXPEAUCLIENT_INFO@1@KK@Z; CLightDismissClientStore::_FilterChain(CLightDismissClientStore::CLIENT_INFO *,ulong,ulong)
0x180018064  sub     rbx, r12
0x180018067  mov     rcx, rsi; this
0x18001806a  test    ebx, ebx
0x18001806c  jns     short loc_180018051
0x18001806e  call    ?_UpdateOverlayRegion@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_UpdateOverlayRegion(void)
0x180018073  mov     rcx, rsi; this
0x180018076  call    ?_DismissClients@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_DismissClients(void)
0x18001807b  mov     rbx, [rsp+200h+var_1C8]
0x180018080  jmp     short loc_1800180B2
0x180018082  test    al, 8
0x180018084  jz      short loc_180018093
0x180018086  mov     rdx, [rbx]; HWND
0x180018089  mov     rcx, rsi; this
0x18001808c  call    ?_HandleDialog@CLightDismissClientStore@@AEAAXPEAUHWND__@@@Z; CLightDismissClientStore::_HandleDialog(HWND__ *)
0x180018091  jmp     short loc_1800180B2
0x180018093  mov     rcx, [rbx]; hWnd
0x180018096  call    _anonymous_namespace___GetOwner
0x18001809b  test    rax, rax
0x18001809e  jz      short loc_1800180B2
0x1800180a0  mov     dword ptr [rsi+18h], 2
0x1800180a7  mov     rcx, rsi; this
0x1800180aa  mov     rdx, [rbx]; HWND
0x1800180ad  call    ?DismissAllInactiveClients@CLightDismissClientStore@@IEAAJPEAUHWND__@@@Z; CLightDismissClientStore::DismissAllInactiveClients(HWND__ *)
0x1800180b2  test    dword ptr [rdi], 100h
0x1800180b8  jz      short loc_1800180C1
0x1800180ba  mov     [rsi+0A4h], r12d
0x1800180c1  mov     eax, [rdi]
0x1800180c3  bt      eax, 0Ch
0x1800180c7  jnb     short loc_1800180D5
0x1800180c9  mov     dword ptr [rsi+0A8h], 12h
0x1800180d3  jmp     short loc_1800180EA
0x1800180d5  and     eax, 200h
0x1800180da  neg     eax
0x1800180dc  sbb     eax, eax
0x1800180de  and     eax, 3
0x1800180e1  add     eax, 3
0x1800180e4  mov     [rsi+0A8h], eax
0x1800180ea  mov     eax, [rdi]
0x1800180ec  mov     edx, r15d; uCmd
0x1800180ef  shr     eax, 0Ah
0x1800180f2  and     eax, r12d
0x1800180f5  mov     [rsi+9Ch], eax
0x1800180fb  mov     rbx, [rbx]
0x1800180fe  mov     rcx, rbx; hWnd
0x180018101  call    cs:__imp_GetWindow
0x180018108  nop     dword ptr [rax+rax+00h]
0x18001810d  mov     r13, rax
0x180018110  test    rax, rax
0x180018113  jnz     short loc_18001812E
0x180018115  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x18001811c  mov     rcx, rbx; hWnd
0x18001811f  call    cs:__imp_GetPropW
0x180018126  nop     dword ptr [rax+rax+00h]
0x18001812b  mov     r13, rax
0x18001812e  mov     rbx, r14
0x180018131  lea     r15, [rsi+58h]
0x180018135  mov     r14, rdi
0x180018138  cmp     rbx, [rsi+60h]
0x18001813c  jnb     loc_1800181CB
0x180018142  lea     r15, [rsi+58h]
0x180018146  mov     r8, r13; HWND
0x180018149  mov     rdx, [r15]
0x18001814c  mov     rdx, [rdx+rbx*8]; struct CLightDismissClientStore::CLIENT_INFO *
0x180018150  call    ?_GetNodeInChain@CLightDismissClientStore@@AEBAPEAUCLIENT_INFO@1@PEAU21@PEAUHWND__@@@Z; CLightDismissClientStore::_GetNodeInChain(CLightDismissClientStore::CLIENT_INFO *,HWND__ *)
0x180018155  mov     r14, rax
0x180018158  test    rax, rax
0x18001815b  jnz     short loc_180018162
0x18001815d  add     rbx, r12
0x180018160  jmp     short loc_180018135
0x180018162  mov     rbx, [rax+38h]
0x180018166  mov     [rsp+200h+var_1B0], rbx
0x18001816b  test    rbx, rbx
0x18001816e  jz      short loc_1800181BD
0x180018170  mov     rax, [rsp+200h+var_1C8]
0x180018175  mov     rax, [rax]
0x180018178  cmp     [rbx+8], rax
0x18001817c  jnz     short loc_1800181AB
0x18001817e  mov     eax, [rbx+10h]
0x180018181  lea     rdx, [rsp+200h+var_1B0]
0x180018186  mov     rcx, [rsp+200h+var_1C0]
0x18001818b  mov     [rcx], eax
0x18001818d  mov     rcx, [rsp+200h+var_1B8]
0x180018192  mov     rax, [rbx+38h]
0x180018196  mov     [rcx], rax
0x180018199  mov     rcx, r15
0x18001819c  call    ?Remove@?$CTSimpleArray@PEAUCLIENT_INFO@CLightDismissClientStore@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUCLIENT_INFO@CLightDismissClientStore@@@@V?$CSimpleArrayStandardCompareHelper@PEAUCLIENT_INFO@CLightDismissClientStore@@@@V?$CSimpleArrayStandardMergeHelper@PEAUCLIENT_INFO@CLightDismissClientStore@@@@@@QEAAJAEBQEAUCLIENT_INFO@CLightDismissClientStore@@PEA_K@Z; CTSimpleArray<CLightDismissClientStore::CLIENT_INFO *,4294967294,CTPolicyCoTaskMem<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardCompareHelper<CLightDismissClientStore::CLIENT_INFO *>,CSimpleArrayStandardMergeHelper<CLightDismissClientStore::CLIENT_INFO *>>::Remove(CLightDismissClientStore::CLIENT_INFO * const &,unsigned __int64 *)
0x1800181a1  mov     rcx, rbx; this
0x1800181a4  call    ??_GCLIENT_INFO@CLightDismissClientStore@@QEAAPEAXI@Z; CLightDismissClientStore::CLIENT_INFO::`scalar deleting destructor'(uint)
0x1800181a9  jmp     short loc_1800181BD
0x1800181ab  mov     rdx, rbx; struct CLightDismissClientStore::CLIENT_INFO *
0x1800181ae  mov     dword ptr [rsi+18h], 5
0x1800181b5  mov     rcx, rsi; this
0x1800181b8  call    ?_RemoveChain@CLightDismissClientStore@@AEAAJPEAUCLIENT_INFO@1@@Z; CLightDismissClientStore::_RemoveChain(CLightDismissClientStore::CLIENT_INFO *)
0x1800181bd  mov     rax, qword ptr [rsp+200h+dwProcessId]
0x1800181c2  mov     [r14+38h], rdi
0x1800181c6  mov     [rax], r14
0x1800181c9  jmp     short loc_180018215
0x1800181cb  mov     rax, qword ptr [rsp+200h+dwProcessId]
0x1800181d0  cmp     qword ptr [rax], 0
0x1800181d4  jnz     short loc_180018215
0x1800181d6  mov     rdx, [r15+8]
0x1800181da  xor     ebx, ebx
0x1800181dc  cmp     rdx, [r15+18h]
0x1800181e0  jnz     short loc_1800181F3
0x1800181e2  inc     rdx
0x1800181e5  mov     rcx, r15
0x1800181e8  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Markup::IXamlMetadataProvider>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800181ed  mov     ebx, eax
0x1800181ef  test    eax, eax
0x1800181f1  js      short loc_18001820D
0x1800181f3  add     [r15+8], r12
0x1800181f7  mov     rdx, [r15+8]
0x1800181fb  mov     rax, [r15]
0x1800181fe  dec     rdx
0x180018201  lea     rdx, [rax+rdx*8]
0x180018205  test    rdx, rdx
0x180018208  jz      short loc_180018215
0x18001820a  mov     [rdx], rdi
0x18001820d  test    ebx, ebx
0x18001820f  js      loc_1800183EB
0x180018215  mov     rcx, rsi; this
0x180018218  call    ?_CreateMessageWindow@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_CreateMessageWindow(void)
0x18001821d  mov     ebx, eax
0x18001821f  test    eax, eax
0x180018221  js      loc_1800183A8
0x180018227  mov     rax, [rsp+200h+var_1C8]
0x18001822c  lea     rdx, [rsp+200h+dwProcessId]; lpdwProcessId
0x180018231  xor     ebx, ebx
0x180018233  mov     [rsp+200h+dwProcessId], ebx
0x180018237  mov     rcx, [rax]; hWnd
0x18001823a  call    cs:__imp_GetWindowThreadProcessId
0x180018241  nop     dword ptr [rax+rax+00h]
0x180018246  xor     r14b, r14b
0x180018249  xor     r15d, r15d
0x18001824c  cmp     [rsi+40h], rbx
0x180018250  jbe     loc_1800182F1
0x180018256  mov     rax, [rsi+38h]
0x18001825a  mov     rcx, r15
0x18001825d  add     rcx, rcx
0x180018260  mov     rcx, [rax+rcx*8+8]; Process
0x180018265  call    cs:__imp_GetProcessId
0x18001826c  nop     dword ptr [rax+rax+00h]
0x180018271  mov     r8d, [rsp+200h+dwProcessId]
0x180018276  cmp     eax, r8d
0x180018279  movzx   r14d, r14b
0x18001827d  cmovz   r14d, r12d
0x180018281  add     r15, r12
0x180018284  cmp     r15, [rsi+40h]
0x180018288  jb      short loc_180018256
0x18001828a  test    r14b, r14b
0x18001828d  jz      short loc_1800182F6
0x18001828f  test    ebx, ebx
0x180018291  js      loc_1800183A8
0x180018297  mov     rcx, rsi; this
0x18001829a  call    ?_CreateIMEWinEventHook@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_CreateIMEWinEventHook(void)
0x18001829f  mov     ebx, eax
0x1800182a1  test    eax, eax
0x1800182a3  js      loc_1800183A8
0x1800182a9  mov     rcx, rsi; this
0x1800182ac  call    ?_UpdateOverlayRegion@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_UpdateOverlayRegion(void)
0x1800182b1  mov     ebx, eax
0x1800182b3  test    eax, eax
0x1800182b5  js      loc_1800183A8
0x1800182bb  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, r12b
0x1800182c2  jz      short loc_1800182CE
0x1800182c4  mov     r8, [rsp+200h+var_1A8]
0x1800182c9  call    McTemplateU0p_EventWriteTransfer
0x1800182ce  mov     rcx, [rsp+200h+var_1A0]
0x1800182d3  mov     eax, [rsi+30h]
0x1800182d6  mov     [rcx], eax
0x1800182d8  test    byte ptr [rdi], 2
0x1800182db  jz      loc_18001841A
0x1800182e1  mov     rdx, rdi; struct CLightDismissClientStore::CLIENT_INFO *
0x1800182e4  mov     rcx, rsi; this
0x1800182e7  call    ?_HandleNewFocusLostObject@CLightDismissClientStore@@AEAAXPEAUCLIENT_INFO@1@@Z; CLightDismissClientStore::_HandleNewFocusLostObject(CLightDismissClientStore::CLIENT_INFO *)
0x1800182ec  jmp     loc_18001841A
0x1800182f1  mov     r8d, [rsp+200h+dwProcessId]; dwProcessId
0x1800182f6  xor     edx, edx; bInheritHandle
0x1800182f8  mov     ecx, 101000h; dwDesiredAccess
0x1800182fd  call    cs:__imp_OpenProcess
0x180018304  nop     dword ptr [rax+rax+00h]
0x180018309  mov     r15, rax
0x18001830c  test    rax, rax
0x18001830f  jnz     short loc_18001831D
0x180018311  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180018316  mov     ebx, eax
0x180018318  jmp     loc_18001828F
0x18001831d  mov     r8d, [rsp+200h+dwProcessId]
0x180018322  lea     rdx, _anonymous_namespace___WaitCallback
0x180018329  or      r9d, 0FFFFFFFFh
0x18001832d  mov     [rsp+200h+var_1E0], 18h
0x180018335  mov     rcx, r15
0x180018338  call    cs:__imp_RegisterWaitForSingleObjectEx
  ... truncated ...
```
