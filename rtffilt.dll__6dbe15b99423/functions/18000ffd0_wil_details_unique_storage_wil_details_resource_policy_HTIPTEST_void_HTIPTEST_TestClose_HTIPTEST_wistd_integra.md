# wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)

- ea: `0x18000ffd0`
- end: `0x180010035`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000fc3c`
- `0x18000fcd4`
- `0x18001779c`

## callees

- `0x18000ffd0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010014`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010014`

## string_xrefs

- `0x18000fff6`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v1 = *a1;
  if ( *a1 )
  {
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
      ((void (__fastcall *)(__int64))ProcAddress)(v1);
  }
}

```

## disassembly

```asm
0x18000ffd0  push    rbx
0x18000ffd2  sub     rsp, 20h
0x18000ffd6  mov     rbx, [rcx]
0x18000ffd9  test    rbx, rbx
0x18000ffdc  jz      short loc_18001002F
0x18000ffde  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000ffe5  test    rax, rax
0x18000ffe8  jnz     short loc_180010026
0x18000ffea  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000fff1  test    rax, rax
0x18000fff4  jnz     short loc_18001000A
0x18000fff6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000fffd  call    cs:__imp_GetModuleHandleW
0x180010003  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001000a  lea     rdx, aTestclose; "TestClose"
0x180010011  mov     rcx, rax; hModule
0x180010014  call    cs:__imp_GetProcAddress
0x18001001a  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180010021  test    rax, rax
0x180010024  jz      short loc_18001002F
0x180010026  mov     rcx, rbx
0x180010029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002e  nop
0x18001002f  add     rsp, 20h
0x180010033  pop     rbx
0x180010034  retn
```
