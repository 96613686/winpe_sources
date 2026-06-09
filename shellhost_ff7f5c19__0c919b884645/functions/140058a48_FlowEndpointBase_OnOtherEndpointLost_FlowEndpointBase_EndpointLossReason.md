# FlowEndpointBase::OnOtherEndpointLost(FlowEndpointBase::EndpointLossReason)

- ea: `0x140058a48`
- end: `0x140058b92`
- name: `?OnOtherEndpointLost@FlowEndpointBase@@IEAAXW4EndpointLossReason@1@@Z`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14005fd30`

## callees

- `0x14004ca38`
- `0x140052bf8`
- `0x140058a48`
- `0x14005a250`
- `0x14005d1a8`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140058b2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140058b2c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x140058a8e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x140058a8e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140058ae8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140058ae8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140058b4b`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140058b4b`

## string_xrefs

- `0x140058b73`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FlowEndpointBase::OnOtherEndpointLost(__int64 a1, int a2)
{
  int v4; // edi
  HWND v5; // rcx
  void (__fastcall ***v6)(_QWORD, __int64, __int64 *); // rcx
  void (__fastcall **v7)(_QWORD, __int64, __int64 *); // rax
  HWND v8; // rcx
  DWORD WindowThreadProcessId; // eax
  __int64 *v10; // rax
  __int64 v11; // rbx
  DWORD CurrentThreadId; // eax
  int v13; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 dwProcessId; // [rsp+50h] [rbp+20h] BYREF
  int v16; // [rsp+60h] [rbp+30h] BYREF
  DWORD v17; // [rsp+64h] [rbp+34h]
  __int64 v18; // [rsp+68h] [rbp+38h] BYREF

  v4 = *(_DWORD *)(a1 + 112);
  if ( (unsigned int)(v4 - 3) > 1 )
  {
    *(_DWORD *)(a1 + 112) = 3;
    if ( a2 != 2 )
    {
      v5 = *(HWND *)(a1 + 40);
      if ( v5 )
        SendNotifyMessageW(v5, 0x401u, 2u, 0);
    }
    if ( v4 )
    {
      v6 = *(void (__fastcall ****)(_QWORD, __int64, __int64 *))(a1 + 80);
      v7 = *v6;
      dwProcessId = 0;
      (*v7)(v6, 1, &dwProcessId);
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&dwProcessId);
    }
    if ( *(_BYTE *)(a1 + 92) )
    {
      if ( !a2 )
      {
        v8 = *(HWND *)(a1 + 40);
        if ( v8 )
        {
          LODWORD(dwProcessId) = 0;
          WindowThreadProcessId = GetWindowThreadProcessId(v8, (LPDWORD)&dwProcessId);
          if ( WindowThreadProcessId )
          {
            v16 = dwProcessId;
            v17 = WindowThreadProcessId;
            v10 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(
                               &v18,
                               &v16);
            v11 = *v10;
            *v10 = 0;
            if ( v18 )
            {
              v18 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
            }
            CurrentThreadId = GetCurrentThreadId();
            v13 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v13 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1EE,
                (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
                (const char *)(unsigned int)v13,
                v11);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140058a48  mov     [rsp-18h+arg_8], rbx
0x140058a4d  push    rbp
0x140058a4e  push    rsi
0x140058a4f  push    rdi
0x140058a50  mov     rbp, rsp
0x140058a53  sub     rsp, 30h
0x140058a57  mov     esi, edx
0x140058a59  mov     rbx, rcx
0x140058a5c  mov     edi, [rcx+70h]
0x140058a5f  lea     eax, [rdi-3]
0x140058a62  cmp     eax, 1
0x140058a65  jbe     loc_140058B85
0x140058a6b  mov     dword ptr [rcx+70h], 3
0x140058a72  mov     r8d, 2; wParam
0x140058a78  cmp     edx, r8d
0x140058a7b  jz      short loc_140058A94
0x140058a7d  mov     rcx, [rcx+28h]; hWnd
0x140058a81  test    rcx, rcx
0x140058a84  jz      short loc_140058A94
0x140058a86  xor     r9d, r9d; lParam
0x140058a89  mov     edx, 401h; Msg
0x140058a8e  call    cs:__imp_SendNotifyMessageW
0x140058a94  test    edi, edi
0x140058a96  jz      short loc_140058AC2
0x140058a98  mov     rcx, [rbx+50h]
0x140058a9c  mov     rax, [rcx]
0x140058a9f  mov     [rbp+dwProcessId], 0
0x140058aa7  lea     r8, [rbp+dwProcessId]
0x140058aab  mov     edx, 1
0x140058ab0  mov     rax, [rax]
0x140058ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058ab8  nop
0x140058ab9  lea     rcx, [rbp+dwProcessId]; this
0x140058abd  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140058ac2  cmp     byte ptr [rbx+5Ch], 0
0x140058ac6  jz      loc_140058B85
0x140058acc  test    esi, esi
0x140058ace  jnz     loc_140058B85
0x140058ad4  mov     rcx, [rbx+28h]; hWnd
0x140058ad8  test    rcx, rcx
0x140058adb  jz      loc_140058B85
0x140058ae1  mov     dword ptr [rbp+dwProcessId], esi
0x140058ae4  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x140058ae8  call    cs:__imp_GetWindowThreadProcessId
0x140058aee  test    eax, eax
0x140058af0  jz      loc_140058B85
0x140058af6  mov     ecx, dword ptr [rbp+dwProcessId]
0x140058af9  mov     [rbp+arg_10], ecx
0x140058afc  mov     [rbp+arg_14], eax
0x140058aff  lea     rdx, [rbp+arg_10]
0x140058b03  lea     rcx, [rbp+arg_18]
0x140058b07  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(_lambda_b84298806a3ade5bf2f206695eab1b51_ &)
0x140058b0c  mov     rbx, [rax]
0x140058b0f  mov     qword ptr [rax], 0
0x140058b16  mov     rcx, [rbp+arg_18]
0x140058b1a  test    rcx, rcx
0x140058b1d  jz      short loc_140058B2C
0x140058b1f  mov     [rbp+arg_18], 0
0x140058b27  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x140058b2c  call    cs:__imp_GetCurrentThreadId
0x140058b32  mov     [rsp+30h+var_8], 0
0x140058b3b  mov     qword ptr [rsp+30h+var_10], rbx; int
0x140058b40  xor     r9d, r9d
0x140058b43  mov     r8d, eax
0x140058b46  xor     edx, edx
0x140058b48  lea     ecx, [rdx+3]
0x140058b4b  call    cs:__imp_SHTaskPoolQueueTask
0x140058b51  mov     edi, eax
0x140058b53  test    rbx, rbx
0x140058b56  jz      short loc_140058B68
0x140058b58  mov     rdx, [rbx]
0x140058b5b  mov     rcx, rbx
0x140058b5e  mov     rax, [rdx+10h]
0x140058b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058b67  nop
0x140058b68  test    edi, edi
0x140058b6a  jns     short loc_140058B85
0x140058b6c  mov     rcx, [rbp+18h]; this
0x140058b70  mov     r9d, edi; char *
0x140058b73  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Valu"...
0x140058b7a  mov     edx, 1EEh; void *
0x140058b7f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140058b85  mov     rbx, [rsp+30h+arg_8]
0x140058b8a  add     rsp, 30h
0x140058b8e  pop     rdi
0x140058b8f  pop     rsi
0x140058b90  pop     rbp
0x140058b91  retn
```
