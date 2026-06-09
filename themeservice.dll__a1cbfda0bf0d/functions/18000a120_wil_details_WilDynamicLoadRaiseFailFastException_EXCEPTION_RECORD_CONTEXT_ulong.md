# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a120`
- end: `0x18000a178`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a120`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a14f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a14f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a13f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a13f`

## string_xrefs

- `0x18000a135`: `kernelbase.dll`

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
0x18000a120  mov     [rsp+arg_0], rbx
0x18000a125  mov     [rsp+arg_8], rsi
0x18000a12a  push    rdi
0x18000a12b  sub     rsp, 20h
0x18000a12f  mov     rsi, rcx
0x18000a132  mov     ebx, r8d
0x18000a135  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a13c  mov     rdi, rdx
0x18000a13f  call    cs:__imp_GetModuleHandleW
0x18000a145  mov     rcx, rax; hModule
0x18000a148  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a14f  call    cs:__imp_GetProcAddress
0x18000a155  test    rax, rax
0x18000a158  jz      short loc_18000A168
0x18000a15a  mov     r8d, ebx
0x18000a15d  mov     rdx, rdi
0x18000a160  mov     rcx, rsi
0x18000a163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a168  mov     rbx, [rsp+28h+arg_0]
0x18000a16d  mov     rsi, [rsp+28h+arg_8]
0x18000a172  add     rsp, 20h
0x18000a176  pop     rdi
0x18000a177  retn
```
