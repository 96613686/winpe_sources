# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800345c0`
- end: `0x180034618`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800345c0`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800345ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800345ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800345df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800345df`

## string_xrefs

- `0x1800345d5`: `kernelbase.dll`

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
0x1800345c0  mov     [rsp+arg_0], rbx
0x1800345c5  mov     [rsp+arg_8], rsi
0x1800345ca  push    rdi
0x1800345cb  sub     rsp, 20h
0x1800345cf  mov     rsi, rcx
0x1800345d2  mov     ebx, r8d
0x1800345d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800345dc  mov     rdi, rdx
0x1800345df  call    cs:__imp_GetModuleHandleW
0x1800345e5  mov     rcx, rax; hModule
0x1800345e8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800345ef  call    cs:__imp_GetProcAddress
0x1800345f5  test    rax, rax
0x1800345f8  jz      short loc_180034608
0x1800345fa  mov     r8d, ebx
0x1800345fd  mov     rdx, rdi
0x180034600  mov     rcx, rsi
0x180034603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034608  mov     rbx, [rsp+28h+arg_0]
0x18003460d  mov     rsi, [rsp+28h+arg_8]
0x180034612  add     rsp, 20h
0x180034616  pop     rdi
0x180034617  retn
```
