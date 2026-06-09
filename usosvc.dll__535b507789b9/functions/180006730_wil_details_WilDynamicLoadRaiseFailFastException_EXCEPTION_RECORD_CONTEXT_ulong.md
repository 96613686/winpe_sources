# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006730`
- end: `0x180006788`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006730`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000674f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000674f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000675f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000675f`

## string_xrefs

- `0x180006745`: `kernelbase.dll`

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
0x180006730  mov     [rsp+arg_0], rbx
0x180006735  mov     [rsp+arg_8], rsi
0x18000673a  push    rdi
0x18000673b  sub     rsp, 20h
0x18000673f  mov     rsi, rcx
0x180006742  mov     ebx, r8d
0x180006745  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000674c  mov     rdi, rdx
0x18000674f  call    cs:__imp_GetModuleHandleW
0x180006755  mov     rcx, rax; hModule
0x180006758  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000675f  call    cs:__imp_GetProcAddress
0x180006765  test    rax, rax
0x180006768  jz      short loc_180006778
0x18000676a  mov     r8d, ebx
0x18000676d  mov     rdx, rdi
0x180006770  mov     rcx, rsi
0x180006773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006778  mov     rbx, [rsp+28h+arg_0]
0x18000677d  mov     rsi, [rsp+28h+arg_8]
0x180006782  add     rsp, 20h
0x180006786  pop     rdi
0x180006787  retn
```
