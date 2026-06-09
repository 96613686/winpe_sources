# winrt::impl::delegate_winrt::Windows::System::Threading::TimerElapsedHandler__lambda_9367859c34a74a1fa4fedcf4c0df6f03___::Invoke

- ea: `0x140024c70`
- end: `0x140024cec`
- name: `winrt::impl::delegate_winrt::Windows::System::Threading::TimerElapsedHandler__lambda_9367859c34a74a1fa4fedcf4c0df6f03___::Invoke`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000ccdc`
- `0x140022d64`
- `0x140024c70`
- `0x140029010`

## import_xrefs

- `USER32!PostMessageW` at `0x140024caa`
- `USER32!PostMessageW` at `0x140024caa`

## string_xrefs

- `0x140024cba`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate_winrt::Windows::System::Threading::TimerElapsedHandler__lambda_9367859c34a74a1fa4fedcf4c0df6f03___::Invoke(
        __int64 a1,
        __int64 a2)
{
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( !PostMessageW(*(HWND *)(a1 + 16), 0x401u, 0, 0) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xA1,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v3);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v6);
  return 0;
}

```

## disassembly

```asm
0x140024c70  mov     [rsp+arg_8], rbx
0x140024c75  push    rdi
0x140024c76  sub     rsp, 20h
0x140024c7a  mov     rdi, rcx
0x140024c7d  mov     [rsp+28h+arg_0], rdx
0x140024c82  test    rdx, rdx
0x140024c85  jz      short loc_140024C96
0x140024c87  mov     rax, [rdx]
0x140024c8a  mov     rcx, rdx
0x140024c8d  mov     rax, [rax+8]
0x140024c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c96  mov     rbx, [rsp+28h]
0x140024c9b  xor     r9d, r9d; lParam
0x140024c9e  xor     r8d, r8d; wParam
0x140024ca1  mov     edx, 401h; Msg
0x140024ca6  mov     rcx, [rdi+10h]; hWnd
0x140024caa  call    cs:__imp_PostMessageW
0x140024cb1  nop     dword ptr [rax+rax+00h]
0x140024cb6  test    eax, eax
0x140024cb8  jnz     short loc_140024CCE
0x140024cba  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140024cc1  mov     edx, 0A1h; void *
0x140024cc6  mov     rcx, rbx; this
0x140024cc9  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140024cce  lea     rcx, [rsp+28h+arg_0]
0x140024cd3  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024cd8  xor     eax, eax
0x140024cda  jmp     short loc_140024CE0
0x140024cdc  mov     eax, dword ptr [rsp+28h+arg_0]
0x140024ce0  mov     rbx, [rsp+28h+arg_8]
0x140024ce5  add     rsp, 20h
0x140024ce9  pop     rdi
0x140024cea  retn
```
