# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)

- ea: `0x1800dcfac`
- end: `0x1800dd006`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(void ***)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f0984`
- `0x1800f09de`

## callees

- `0x1800dcfac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcfd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dcfe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dcfe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcfe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcfe0`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        void ***a1)
{
  void **v1; // rdi
  void **v2; // rsi
  void *v3; // rbp
  DWORD LastError; // ebx

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = *a1;
    v2 = a1[1];
    v3 = **a1;
    if ( v3 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v3);
      SetLastError(LastError);
    }
    *v1 = v2;
  }
}

```

## disassembly

```asm
0x1800dcfac  mov     [rsp+arg_0], rbx
0x1800dcfb1  mov     [rsp+arg_8], rbp
0x1800dcfb6  mov     [rsp+arg_10], rsi
0x1800dcfbb  push    rdi
0x1800dcfbc  sub     rsp, 20h
0x1800dcfc0  cmp     byte ptr [rcx+10h], 0
0x1800dcfc4  jz      short loc_1800DCFF1
0x1800dcfc6  mov     rdi, [rcx]
0x1800dcfc9  mov     rsi, [rcx+8]
0x1800dcfcd  mov     rbp, [rdi]
0x1800dcfd0  test    rbp, rbp
0x1800dcfd3  jz      short loc_1800DCFEE
0x1800dcfd5  call    cs:__imp_GetLastError
0x1800dcfdb  mov     rcx, rbp; pv
0x1800dcfde  mov     ebx, eax
0x1800dcfe0  call    cs:__imp_CoTaskMemFree
0x1800dcfe6  mov     ecx, ebx; dwErrCode
0x1800dcfe8  call    cs:__imp_SetLastError
0x1800dcfee  mov     [rdi], rsi
0x1800dcff1  mov     rbx, [rsp+28h+arg_0]
0x1800dcff6  mov     rbp, [rsp+28h+arg_8]
0x1800dcffb  mov     rsi, [rsp+28h+arg_10]
0x1800dd000  add     rsp, 20h
0x1800dd004  pop     rdi
0x1800dd005  retn
```
