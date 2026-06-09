# wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)

- ea: `0x180006680`
- end: `0x1800066e5`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005950`
- `0x18000649c`

## callees

- `0x180006680`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066c4`

## string_xrefs

- `0x1800066a6`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180006680  push    rbx
0x180006682  sub     rsp, 20h
0x180006686  mov     rbx, [rcx]
0x180006689  test    rbx, rbx
0x18000668c  jz      short loc_1800066DF
0x18000668e  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180006695  test    rax, rax
0x180006698  jnz     short loc_1800066D6
0x18000669a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800066a1  test    rax, rax
0x1800066a4  jnz     short loc_1800066BA
0x1800066a6  lea     rcx, ModuleName; "kernelbase.dll"
0x1800066ad  call    cs:__imp_GetModuleHandleW
0x1800066b3  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800066ba  lea     rdx, aTestclose; "TestClose"
0x1800066c1  mov     rcx, rax; hModule
0x1800066c4  call    cs:__imp_GetProcAddress
0x1800066ca  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800066d1  test    rax, rax
0x1800066d4  jz      short loc_1800066DF
0x1800066d6  mov     rcx, rbx
0x1800066d9  call    _guard_dispatch_icall
0x1800066de  nop
0x1800066df  add     rsp, 20h
0x1800066e3  pop     rbx
0x1800066e4  retn
```
