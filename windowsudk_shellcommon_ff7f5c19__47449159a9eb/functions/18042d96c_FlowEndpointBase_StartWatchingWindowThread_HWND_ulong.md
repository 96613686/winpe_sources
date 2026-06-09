# FlowEndpointBase::StartWatchingWindowThread(HWND__ *,ulong)

- ea: `0x18042d96c`
- end: `0x18042da9c`
- name: `?StartWatchingWindowThread@FlowEndpointBase@@IEAA_NPEAUHWND__@@K@Z`
- size: `304`
- prototype: `bool(FlowEndpointBase *__hidden this, HWND, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18042a0f4`
- `0x18042b8e8`

## callees

- `0x180086f44`
- `0x18008d854`
- `0x18042d96c`
- `0x1804303c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18042da20`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18042da20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18042d9e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18042d9e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18042da66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18042da66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18042da3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18042da3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18042d98a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18042d98a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18042da7e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18042da7e`

## pseudocode

```c
bool __fastcall FlowEndpointBase::StartWatchingWindowThread(FlowEndpointBase *this, HWND a2, DWORD a3)
{
  DWORD *v3; // r14
  DWORD WindowThreadProcessId; // esi
  bool v7; // bl
  DWORD v8; // ebx
  HANDLE v9; // rax
  PTP_WAIT ThreadpoolWait; // rax

  v3 = (DWORD *)((char *)this + 48);
  WindowThreadProcessId = GetWindowThreadProcessId(a2, (LPDWORD)this + 12);
  v7 = WindowThreadProcessId != 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
    && !WindowThreadProcessId
    && a3
    || (a3 = WindowThreadProcessId) != 0 )
  {
    v8 = 0x100000;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
      && !*v3 )
    {
      v8 = 1050624;
    }
    v9 = OpenThread(v8, 0, a3);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 56,
      v9);
    v7 = (unsigned __int64)(*((_QWORD *)this + 7) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    {
      if ( v7 )
      {
        if ( !*v3 )
          *v3 = GetProcessIdOfThread(*((HANDLE *)this + 7));
        goto LABEL_13;
      }
    }
    else if ( v7 )
    {
LABEL_13:
      ThreadpoolWait = CreateThreadpoolWait(
                         FlowEndpointBase::s_OtherEndpointThreadDestroyedCallback,
                         *((PVOID *)this + 1),
                         0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
        (char *)this + 64,
        ThreadpoolWait);
      v7 = *((_QWORD *)this + 8) != 0;
      goto LABEL_14;
    }
LABEL_16:
    PostMessageW(*((HWND *)this + 1), 0x401u, 1u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 56,
      0);
    return v7;
  }
LABEL_14:
  if ( !v7 )
    goto LABEL_16;
  SetThreadpoolWait(*((PTP_WAIT *)this + 8), *((HANDLE *)this + 7), 0);
  return v7;
}

```

## disassembly

```asm
0x18042d96c  push    rbx
0x18042d96e  push    rbp
0x18042d96f  push    rsi
0x18042d970  push    rdi
0x18042d971  push    r14
0x18042d973  sub     rsp, 20h
0x18042d977  mov     rax, rdx
0x18042d97a  lea     r14, [rcx+30h]
0x18042d97e  mov     rdi, rcx
0x18042d981  mov     rdx, r14; lpdwProcessId
0x18042d984  mov     rcx, rax; hWnd
0x18042d987  mov     ebp, r8d
0x18042d98a  call    cs:__imp_GetWindowThreadProcessId
0x18042d990  test    eax, eax
0x18042d992  mov     esi, eax
0x18042d994  setnz   bl
0x18042d997  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18042d99e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18042d9a3  test    al, al
0x18042d9a5  jz      short loc_18042D9AF
0x18042d9a7  test    esi, esi
0x18042d9a9  jnz     short loc_18042D9AF
0x18042d9ab  test    ebp, ebp
0x18042d9ad  jnz     short loc_18042D9B9
0x18042d9af  mov     ebp, esi
0x18042d9b1  test    esi, esi
0x18042d9b3  jz      loc_18042DA57
0x18042d9b9  mov     ebx, 100000h
0x18042d9be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18042d9c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18042d9ca  test    al, al
0x18042d9cc  jz      short loc_18042D9DA
0x18042d9ce  cmp     dword ptr [r14], 0
0x18042d9d2  mov     eax, 100800h
0x18042d9d7  cmovz   ebx, eax
0x18042d9da  mov     r8d, ebp; dwThreadId
0x18042d9dd  lea     rsi, [rdi+38h]
0x18042d9e1  xor     edx, edx; bInheritHandle
0x18042d9e3  mov     ecx, ebx; dwDesiredAccess
0x18042d9e5  call    cs:__imp_OpenThread
0x18042d9eb  mov     rdx, rax
0x18042d9ee  mov     rcx, rsi
0x18042d9f1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18042d9f6  mov     rax, [rsi]
0x18042d9f9  dec     rax
0x18042d9fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18042da00  setbe   bl
0x18042da03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18042da0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18042da0f  test    al, al
0x18042da11  jz      short loc_18042DA2B
0x18042da13  test    bl, bl
0x18042da15  jz      short loc_18042DA6E
0x18042da17  cmp     dword ptr [r14], 0
0x18042da1b  jnz     short loc_18042DA2F
0x18042da1d  mov     rcx, [rsi]; Thread
0x18042da20  call    cs:__imp_GetProcessIdOfThread
0x18042da26  mov     [r14], eax
0x18042da29  jmp     short loc_18042DA2F
0x18042da2b  test    bl, bl
0x18042da2d  jz      short loc_18042DA6E
0x18042da2f  mov     rdx, [rdi+8]; pv
0x18042da33  lea     rcx, ?s_OtherEndpointThreadDestroyedCallback@FlowEndpointBase@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18042da3a  xor     r8d, r8d; pcbe
0x18042da3d  call    cs:__imp_CreateThreadpoolWait
0x18042da43  mov     rdx, rax
0x18042da46  lea     rcx, [rdi+40h]
0x18042da4a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18042da4f  cmp     qword ptr [rdi+40h], 0
0x18042da54  setnz   bl
0x18042da57  test    bl, bl
0x18042da59  jz      short loc_18042DA6E
0x18042da5b  mov     rdx, [rdi+38h]; h
0x18042da5f  xor     r8d, r8d; pftTimeout
0x18042da62  mov     rcx, [rdi+40h]; pwa
0x18042da66  call    cs:__imp_SetThreadpoolWait
0x18042da6c  jmp     short loc_18042DA8F
0x18042da6e  mov     rcx, [rdi+8]; hWnd
0x18042da72  xor     r9d, r9d; lParam
0x18042da75  mov     edx, 401h; Msg
0x18042da7a  lea     r8d, [r9+1]; wParam
0x18042da7e  call    cs:__imp_PostMessageW
0x18042da84  xor     edx, edx
0x18042da86  lea     rcx, [rdi+38h]
0x18042da8a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18042da8f  mov     al, bl
0x18042da91  add     rsp, 20h
0x18042da95  pop     r14
0x18042da97  pop     rdi
0x18042da98  pop     rsi
0x18042da99  pop     rbp
0x18042da9a  pop     rbx
0x18042da9b  retn
```
