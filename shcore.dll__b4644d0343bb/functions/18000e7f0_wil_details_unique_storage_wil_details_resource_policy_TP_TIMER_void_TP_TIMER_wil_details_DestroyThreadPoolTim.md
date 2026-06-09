# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000e7f0`
- end: `0x18000e82e`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e6c4`
- `0x1800104ac`
- `0x180037600`

## callees

- `0x18000e7f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e813`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e826`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e826`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e81e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e81e`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000e7f0  push    rbx
0x18000e7f2  push    rbp
0x18000e7f3  push    rsi
0x18000e7f4  push    rdi
0x18000e7f5  sub     rsp, 28h
0x18000e7f9  mov     rsi, [rcx]
0x18000e7fc  mov     rbp, rdx
0x18000e7ff  mov     rdi, rcx
0x18000e802  test    rsi, rsi
0x18000e805  jnz     short loc_18000E813
0x18000e807  mov     [rdi], rbp
0x18000e80a  add     rsp, 28h
0x18000e80e  pop     rdi
0x18000e80f  pop     rsi
0x18000e810  pop     rbp
0x18000e811  pop     rbx
0x18000e812  retn
0x18000e813  call    cs:__imp_GetLastError
0x18000e819  mov     rcx, rsi; pti
0x18000e81c  mov     ebx, eax
0x18000e81e  call    cs:__imp_CloseThreadpoolTimer
0x18000e824  mov     ecx, ebx; dwErrCode
0x18000e826  call    cs:__imp_SetLastError
0x18000e82c  jmp     short loc_18000E807
```
