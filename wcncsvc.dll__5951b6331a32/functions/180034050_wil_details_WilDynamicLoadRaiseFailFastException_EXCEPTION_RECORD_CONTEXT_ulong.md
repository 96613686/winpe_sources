# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180034050`
- end: `0x1800340a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180034050`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003407f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003407f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003406f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003406f`

## string_xrefs

- `0x180034065`: `kernelbase.dll`

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
0x180034050  mov     [rsp+arg_0], rbx
0x180034055  mov     [rsp+arg_8], rsi
0x18003405a  push    rdi
0x18003405b  sub     rsp, 20h
0x18003405f  mov     rsi, rcx
0x180034062  mov     ebx, r8d
0x180034065  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003406c  mov     rdi, rdx
0x18003406f  call    cs:__imp_GetModuleHandleW
0x180034075  mov     rcx, rax; hModule
0x180034078  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18003407f  call    cs:__imp_GetProcAddress
0x180034085  test    rax, rax
0x180034088  jz      short loc_180034098
0x18003408a  mov     r8d, ebx
0x18003408d  mov     rdx, rdi
0x180034090  mov     rcx, rsi
0x180034093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034098  mov     rbx, [rsp+28h+arg_0]
0x18003409d  mov     rsi, [rsp+28h+arg_8]
0x1800340a2  add     rsp, 20h
0x1800340a6  pop     rdi
0x1800340a7  retn
```
