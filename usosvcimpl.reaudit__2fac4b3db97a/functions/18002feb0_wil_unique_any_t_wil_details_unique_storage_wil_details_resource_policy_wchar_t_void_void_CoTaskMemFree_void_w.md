# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)

- ea: `0x18002feb0`
- end: `0x18002ff20`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `112`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fc94`
- `0x18002ff28`
- `0x18003825c`
- `0x1800390b4`
- `0x180080dd0`

## callees

- `0x18002feb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fedf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fedf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fef2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002feea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002feea`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v4; // rbp
  void *v5; // r14
  DWORD LastError; // ebx

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v4);
      SetLastError(LastError);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18002feb0  mov     rax, rsp
0x18002feb3  mov     [rax+8], rbx
0x18002feb7  mov     [rax+10h], rbp
0x18002febb  mov     [rax+18h], rsi
0x18002febf  mov     [rax+20h], rdi
0x18002fec3  push    r14
0x18002fec5  sub     rsp, 20h
0x18002fec9  mov     rsi, rdx
0x18002fecc  mov     rdi, rcx
0x18002fecf  cmp     rcx, rdx
0x18002fed2  jz      short loc_18002FF02
0x18002fed4  mov     rbp, [rcx]
0x18002fed7  mov     r14, [rdx]
0x18002feda  test    rbp, rbp
0x18002fedd  jz      short loc_18002FEF8
0x18002fedf  call    cs:__imp_GetLastError
0x18002fee5  mov     rcx, rbp; pv
0x18002fee8  mov     ebx, eax
0x18002feea  call    cs:__imp_CoTaskMemFree
0x18002fef0  mov     ecx, ebx; dwErrCode
0x18002fef2  call    cs:__imp_SetLastError
0x18002fef8  mov     [rdi], r14
0x18002fefb  mov     qword ptr [rsi], 0
0x18002ff02  mov     rbx, [rsp+28h+arg_0]
0x18002ff07  mov     rax, rdi
0x18002ff0a  mov     rdi, [rsp+28h+arg_18]
0x18002ff0f  mov     rbp, [rsp+28h+arg_8]
0x18002ff14  mov     rsi, [rsp+28h+arg_10]
0x18002ff19  add     rsp, 20h
0x18002ff1d  pop     r14
0x18002ff1f  retn
```
