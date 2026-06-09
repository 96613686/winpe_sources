# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800027f0`
- end: `0x180002848`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800027f0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000281f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000281f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000280f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000280f`

## string_xrefs

- `0x180002805`: `kernelbase.dll`

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
0x1800027f0  mov     [rsp+arg_0], rbx
0x1800027f5  mov     [rsp+arg_8], rsi
0x1800027fa  push    rdi
0x1800027fb  sub     rsp, 20h
0x1800027ff  mov     rsi, rcx
0x180002802  mov     ebx, r8d
0x180002805  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000280c  mov     rdi, rdx
0x18000280f  call    cs:__imp_GetModuleHandleW
0x180002815  mov     rcx, rax; hModule
0x180002818  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000281f  call    cs:__imp_GetProcAddress
0x180002825  test    rax, rax
0x180002828  jz      short loc_180002838
0x18000282a  mov     r8d, ebx
0x18000282d  mov     rdx, rdi
0x180002830  mov     rcx, rsi
0x180002833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002838  mov     rbx, [rsp+28h+arg_0]
0x18000283d  mov     rsi, [rsp+28h+arg_8]
0x180002842  add     rsp, 20h
0x180002846  pop     rdi
0x180002847  retn
```
