# wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)

- ea: `0x1800065e0`
- end: `0x18000667a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000649c`
- `0x18000d988`

## callees

- `0x1800065e0`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006629`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006629`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006640`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000665c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000665c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006602`

## string_xrefs

- `0x180006622`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rdi
  DWORD LastError; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_6;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_6:
      ((void (__fastcall *)(__int64))ProcAddress)(v4);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800065e0  mov     [rsp+arg_0], rbx
0x1800065e5  mov     [rsp+arg_8], rbp
0x1800065ea  mov     [rsp+arg_10], rsi
0x1800065ef  push    rdi
0x1800065f0  sub     rsp, 20h
0x1800065f4  mov     rsi, rdx
0x1800065f7  mov     rbx, rcx
0x1800065fa  mov     rdi, [rcx]
0x1800065fd  test    rdi, rdi
0x180006600  jz      short loc_180006662
0x180006602  call    cs:__imp_GetLastError
0x180006608  mov     ebp, eax
0x18000660a  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180006611  test    rax, rax
0x180006614  jnz     short loc_180006652
0x180006616  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000661d  test    rax, rax
0x180006620  jnz     short loc_180006636
0x180006622  lea     rcx, ModuleName; "kernelbase.dll"
0x180006629  call    cs:__imp_GetModuleHandleW
0x18000662f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180006636  lea     rdx, aTestclose; "TestClose"
0x18000663d  mov     rcx, rax; hModule
0x180006640  call    cs:__imp_GetProcAddress
0x180006646  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000664d  test    rax, rax
0x180006650  jz      short loc_18000665A
0x180006652  mov     rcx, rdi
0x180006655  call    _guard_dispatch_icall
0x18000665a  mov     ecx, ebp; dwErrCode
0x18000665c  call    cs:__imp_SetLastError
0x180006662  mov     [rbx], rsi
0x180006665  mov     rbx, [rsp+28h+arg_0]
0x18000666a  mov     rbp, [rsp+28h+arg_8]
0x18000666f  mov     rsi, [rsp+28h+arg_10]
0x180006674  add     rsp, 20h
0x180006678  pop     rdi
0x180006679  retn
```
