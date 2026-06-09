# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180004cf0`
- end: `0x180004d48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004cf0`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d1f`

## string_xrefs

- `0x180004d05`: `kernelbase.dll`

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
0x180004cf0  mov     [rsp+arg_0], rbx
0x180004cf5  mov     [rsp+arg_8], rsi
0x180004cfa  push    rdi
0x180004cfb  sub     rsp, 20h
0x180004cff  mov     rsi, rcx
0x180004d02  mov     ebx, r8d
0x180004d05  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004d0c  mov     rdi, rdx
0x180004d0f  call    cs:__imp_GetModuleHandleW
0x180004d15  mov     rcx, rax; hModule
0x180004d18  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180004d1f  call    cs:__imp_GetProcAddress
0x180004d25  test    rax, rax
0x180004d28  jz      short loc_180004D38
0x180004d2a  mov     r8d, ebx
0x180004d2d  mov     rdx, rdi
0x180004d30  mov     rcx, rsi
0x180004d33  call    _guard_dispatch_icall
0x180004d38  mov     rbx, [rsp+28h+arg_0]
0x180004d3d  mov     rsi, [rsp+28h+arg_8]
0x180004d42  add     rsp, 20h
0x180004d46  pop     rdi
0x180004d47  retn
```
