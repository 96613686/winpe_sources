# wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)

- ea: `0x180039e00`
- end: `0x180039e77`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800392c8`
- `0x180039648`

## callees

- `0x180039e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039e5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039e5e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180039e41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180039e41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039e2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039e2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180039e50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180039e50`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
        struct _TP_WAIT **a1,
        struct _TP_WAIT *a2)
{
  struct _TP_WAIT *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180039e00  push    rbx
0x180039e02  push    rbp
0x180039e03  push    rsi
0x180039e04  push    rdi
0x180039e05  sub     rsp, 28h
0x180039e09  mov     rsi, [rcx]
0x180039e0c  mov     rbp, rdx
0x180039e0f  mov     rdi, rcx
0x180039e12  test    rsi, rsi
0x180039e15  jz      short loc_180039E6A
0x180039e17  call    cs:__imp_GetLastError
0x180039e1e  nop     dword ptr [rax+rax+00h]
0x180039e23  xor     r8d, r8d; pftTimeout
0x180039e26  xor     edx, edx; h
0x180039e28  mov     rcx, rsi; pwa
0x180039e2b  mov     ebx, eax
0x180039e2d  call    cs:__imp_SetThreadpoolWait
0x180039e34  nop     dword ptr [rax+rax+00h]
0x180039e39  mov     edx, 1; fCancelPendingCallbacks
0x180039e3e  mov     rcx, rsi; pwa
0x180039e41  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180039e48  nop     dword ptr [rax+rax+00h]
0x180039e4d  mov     rcx, rsi; pwa
0x180039e50  call    cs:__imp_CloseThreadpoolWait
0x180039e57  nop     dword ptr [rax+rax+00h]
0x180039e5c  mov     ecx, ebx; dwErrCode
0x180039e5e  call    cs:__imp_SetLastError
0x180039e65  nop     dword ptr [rax+rax+00h]
0x180039e6a  mov     [rdi], rbp
0x180039e6d  add     rsp, 28h
0x180039e71  pop     rdi
0x180039e72  pop     rsi
0x180039e73  pop     rbp
0x180039e74  pop     rbx
0x180039e75  retn
```
