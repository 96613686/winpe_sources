# SetThreadName(ushort const *)

- ea: `0x18001308c`
- end: `0x1800130e2`
- name: `?SetThreadName@@YAXPEBG@Z`
- size: `86`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010560`
- `0x1800106d0`

## callees

- `0x18001308c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800130a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800130a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800130c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800130c3`

## string_xrefs

- `0x180013099`: `kernel32.dll`
- `0x1800130ab`: `SetThreadDescription`

## pseudocode

```c
void __fastcall SetThreadName(const unsigned __int16 *a1)
{
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rbx
  HANDLE CurrentThread; // rax

  ModuleHandleA = GetModuleHandleA("kernel32.dll");
  if ( ModuleHandleA )
  {
    ProcAddress = GetProcAddress(ModuleHandleA, "SetThreadDescription");
    if ( ProcAddress )
    {
      CurrentThread = GetCurrentThread();
      ((void (__fastcall *)(HANDLE, const unsigned __int16 *))ProcAddress)(CurrentThread, a1);
    }
  }
}

```

## disassembly

```asm
0x18001308c  mov     [rsp+arg_0], rbx
0x180013091  push    rdi
0x180013092  sub     rsp, 20h
0x180013096  mov     rdi, rcx
0x180013099  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800130a0  call    cs:__imp_GetModuleHandleA
0x1800130a6  test    rax, rax
0x1800130a9  jz      short loc_1800130D7
0x1800130ab  lea     rdx, aSetthreaddescr; "SetThreadDescription"
0x1800130b2  mov     rcx, rax; hModule
0x1800130b5  call    cs:__imp_GetProcAddress
0x1800130bb  mov     rbx, rax
0x1800130be  test    rax, rax
0x1800130c1  jz      short loc_1800130D7
0x1800130c3  call    cs:__imp_GetCurrentThread
0x1800130c9  mov     rcx, rax
0x1800130cc  mov     rdx, rdi
0x1800130cf  mov     rax, rbx
0x1800130d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130d7  mov     rbx, [rsp+28h+arg_0]
0x1800130dc  add     rsp, 20h
0x1800130e0  pop     rdi
0x1800130e1  retn
```
