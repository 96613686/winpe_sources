# FlowEndpointBase::OnOtherEndpointLost(FlowEndpointBase::EndpointLossReason)

- ea: `0x18013a68c`
- end: `0x18013a7d6`
- name: `?OnOtherEndpointLost@FlowEndpointBase@@IEAAXW4EndpointLossReason@1@@Z`
- size: `330`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18042a0f4`
- `0x180431c10`
- `0x180431c80`

## callees

- `0x18000b428`
- `0x18007dd20`
- `0x1800e488c`
- `0x18013a68c`
- `0x180421db0`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013a770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013a770`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x18013a6d2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x18013a6d2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18013a72c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18013a72c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18013a78f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18013a78f`

## string_xrefs

- `0x18013a7b7`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

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
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&dwProcessId);
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
              wil::details::in1diag3::Throw_Hr(
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
0x18013a68c  mov     [rsp-18h+arg_8], rbx
0x18013a691  push    rbp
0x18013a692  push    rsi
0x18013a693  push    rdi
0x18013a694  mov     rbp, rsp
0x18013a697  sub     rsp, 30h
0x18013a69b  mov     esi, edx
0x18013a69d  mov     rbx, rcx
0x18013a6a0  mov     edi, [rcx+70h]
0x18013a6a3  lea     eax, [rdi-3]
0x18013a6a6  cmp     eax, 1
0x18013a6a9  jbe     loc_18013A7C9
0x18013a6af  mov     dword ptr [rcx+70h], 3
0x18013a6b6  mov     r8d, 2; wParam
0x18013a6bc  cmp     edx, r8d
0x18013a6bf  jz      short loc_18013A6D8
0x18013a6c1  mov     rcx, [rcx+28h]; hWnd
0x18013a6c5  test    rcx, rcx
0x18013a6c8  jz      short loc_18013A6D8
0x18013a6ca  xor     r9d, r9d; lParam
0x18013a6cd  mov     edx, 401h; Msg
0x18013a6d2  call    cs:__imp_SendNotifyMessageW
0x18013a6d8  test    edi, edi
0x18013a6da  jz      short loc_18013A706
0x18013a6dc  mov     rcx, [rbx+50h]
0x18013a6e0  mov     rax, [rcx]
0x18013a6e3  mov     [rbp+dwProcessId], 0
0x18013a6eb  lea     r8, [rbp+dwProcessId]
0x18013a6ef  mov     edx, 1
0x18013a6f4  mov     rax, [rax]
0x18013a6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013a6fc  nop
0x18013a6fd  lea     rcx, [rbp+dwProcessId]; this
0x18013a701  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x18013a706  cmp     byte ptr [rbx+5Ch], 0
0x18013a70a  jz      loc_18013A7C9
0x18013a710  test    esi, esi
0x18013a712  jnz     loc_18013A7C9
0x18013a718  mov     rcx, [rbx+28h]; hWnd
0x18013a71c  test    rcx, rcx
0x18013a71f  jz      loc_18013A7C9
0x18013a725  mov     dword ptr [rbp+dwProcessId], esi
0x18013a728  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18013a72c  call    cs:__imp_GetWindowThreadProcessId
0x18013a732  test    eax, eax
0x18013a734  jz      loc_18013A7C9
0x18013a73a  mov     ecx, dword ptr [rbp+dwProcessId]
0x18013a73d  mov     [rbp+arg_10], ecx
0x18013a740  mov     [rbp+arg_14], eax
0x18013a743  lea     rdx, [rbp+arg_10]
0x18013a747  lea     rcx, [rbp+arg_18]
0x18013a74b  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(_lambda_b84298806a3ade5bf2f206695eab1b51_ &)
0x18013a750  mov     rbx, [rax]
0x18013a753  mov     qword ptr [rax], 0
0x18013a75a  mov     rcx, [rbp+arg_18]
0x18013a75e  test    rcx, rcx
0x18013a761  jz      short loc_18013A770
0x18013a763  mov     [rbp+arg_18], 0
0x18013a76b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18013a770  call    cs:__imp_GetCurrentThreadId
0x18013a776  mov     [rsp+30h+var_8], 0
0x18013a77f  mov     qword ptr [rsp+30h+var_10], rbx; int
0x18013a784  xor     r9d, r9d
0x18013a787  mov     r8d, eax
0x18013a78a  xor     edx, edx
0x18013a78c  lea     ecx, [rdx+3]
0x18013a78f  call    cs:__imp_SHTaskPoolQueueTask
0x18013a795  mov     edi, eax
0x18013a797  test    rbx, rbx
0x18013a79a  jz      short loc_18013A7AC
0x18013a79c  mov     rdx, [rbx]
0x18013a79f  mov     rcx, rbx
0x18013a7a2  mov     rax, [rdx+10h]
0x18013a7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013a7ab  nop
0x18013a7ac  test    edi, edi
0x18013a7ae  jns     short loc_18013A7C9
0x18013a7b0  mov     rcx, [rbp+18h]; this
0x18013a7b4  mov     r9d, edi; char *
0x18013a7b7  lea     r8, aShellcommonInt_12; "shellcommon\\internal\\shell\\inc\\Valu"...
0x18013a7be  mov     edx, 1EEh; void *
0x18013a7c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013a7c9  mov     rbx, [rsp+30h+arg_8]
0x18013a7ce  add     rsp, 30h
0x18013a7d2  pop     rdi
0x18013a7d3  pop     rsi
0x18013a7d4  pop     rbp
0x18013a7d5  retn
```
