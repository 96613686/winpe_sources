# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180036a40`
- end: `0x180036aa5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180036a40`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036a75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036a75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036a5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036a5f`

## string_xrefs

- `0x180036a55`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x180036a40  mov     [rsp+arg_0], rbx
0x180036a45  mov     [rsp+arg_8], rsi
0x180036a4a  push    rdi
0x180036a4b  sub     rsp, 20h
0x180036a4f  mov     rsi, rcx
0x180036a52  mov     ebx, r8d
0x180036a55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180036a5c  mov     rdi, rdx
0x180036a5f  call    cs:__imp_GetModuleHandleW
0x180036a66  nop     dword ptr [rax+rax+00h]
0x180036a6b  mov     rcx, rax; hModule
0x180036a6e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180036a75  call    cs:__imp_GetProcAddress
0x180036a7c  nop     dword ptr [rax+rax+00h]
0x180036a81  test    rax, rax
0x180036a84  jz      short loc_180036A94
0x180036a86  mov     r8d, ebx
0x180036a89  mov     rdx, rdi
0x180036a8c  mov     rcx, rsi
0x180036a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a94  mov     rbx, [rsp+28h+arg_0]
0x180036a99  mov     rsi, [rsp+28h+arg_8]
0x180036a9e  add     rsp, 20h
0x180036aa2  pop     rdi
0x180036aa3  retn
```
