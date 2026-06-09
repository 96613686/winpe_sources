# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180002520`
- end: `0x180002578`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002520`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000253f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000253f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000254f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000254f`

## string_xrefs

- `0x180002535`: `kernelbase.dll`

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
0x180002520  mov     [rsp+arg_0], rbx
0x180002525  mov     [rsp+arg_8], rsi
0x18000252a  push    rdi
0x18000252b  sub     rsp, 20h
0x18000252f  mov     rsi, rcx
0x180002532  mov     ebx, r8d
0x180002535  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000253c  mov     rdi, rdx
0x18000253f  call    cs:__imp_GetModuleHandleW
0x180002545  mov     rcx, rax; hModule
0x180002548  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000254f  call    cs:__imp_GetProcAddress
0x180002555  test    rax, rax
0x180002558  jz      short loc_180002568
0x18000255a  mov     r8d, ebx
0x18000255d  mov     rdx, rdi
0x180002560  mov     rcx, rsi
0x180002563  call    _guard_dispatch_icall
0x180002568  mov     rbx, [rsp+28h+arg_0]
0x18000256d  mov     rsi, [rsp+28h+arg_8]
0x180002572  add     rsp, 20h
0x180002576  pop     rdi
0x180002577  retn
```
