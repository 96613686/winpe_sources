# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x180009fe4`
- end: `0x18000a104`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dd80`

## callees

- `0x180009fe4`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000a097`
- `KERNEL32!GetCurrentThread` at `0x18000a0d1`
- `KERNEL32!GetCurrentThread` at `0x18000a097`
- `KERNEL32!GetCurrentThread` at `0x18000a0d1`
- `KERNEL32!GetProcAddress` at `0x18000a058`
- `KERNEL32!GetProcAddress` at `0x18000a071`
- `KERNEL32!GetProcAddress` at `0x18000a058`
- `KERNEL32!GetProcAddress` at `0x18000a071`
- `KERNEL32!GetModuleHandleW` at `0x180009ff8`
- `KERNEL32!GetModuleHandleW` at `0x18000a013`
- `KERNEL32!GetModuleHandleW` at `0x18000a02e`
- `KERNEL32!GetModuleHandleW` at `0x180009ff8`
- `KERNEL32!GetModuleHandleW` at `0x18000a013`
- `KERNEL32!GetModuleHandleW` at `0x18000a02e`

## string_xrefs

- `0x18000a027`: `kernelbase.dll`
- `0x18000a00c`: `kernel32.dll`
- `0x180009ff1`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x18000a04e`: `SetThreadInformation`
- `0x18000a064`: `GetThreadInformation`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(
        __int64 a1)
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rax
  bool v4; // zf
  unsigned int (__fastcall *v5)(_QWORD, _QWORD, _QWORD, _QWORD); // rbx
  HANDLE CurrentThread; // rax
  void (__fastcall *v7)(HANDLE, _QWORD, int *, __int64); // rbx
  HANDLE v8; // rax
  int v10; // [rsp+40h] [rbp+8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  }
  if ( ModuleHandleW )
  {
    *(_QWORD *)a1 = GetProcAddress(ModuleHandleW, "SetThreadInformation");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetThreadInformation");
    v4 = *(_QWORD *)a1 == 0;
    v5 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    *(_QWORD *)(a1 + 8) = ProcAddress;
    if ( !v4 )
    {
      if ( ProcAddress )
      {
        v10 = 0;
        CurrentThread = GetCurrentThread();
        if ( v5(CurrentThread, 0, &v10, 4) )
        {
          v7 = *(void (__fastcall **)(HANDLE, _QWORD, int *, __int64))a1;
          *(_DWORD *)(a1 + 16) = v10;
          v10 = 1;
          v8 = GetCurrentThread();
          v7(v8, 0, &v10, 4);
        }
      }
    }
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180009fe4  mov     [rsp+arg_8], rbx
0x180009fe9  push    rdi
0x180009fea  sub     rsp, 30h
0x180009fee  mov     rdi, rcx
0x180009ff1  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180009ff8  call    cs:__imp_GetModuleHandleW
0x180009fff  nop     dword ptr [rax+rax+00h]
0x18000a004  mov     rbx, rax
0x18000a007  test    rax, rax
0x18000a00a  jnz     short loc_18000A03D
0x18000a00c  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18000a013  call    cs:__imp_GetModuleHandleW
0x18000a01a  nop     dword ptr [rax+rax+00h]
0x18000a01f  mov     rbx, rax
0x18000a022  test    rax, rax
0x18000a025  jnz     short loc_18000A03D
0x18000a027  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a02e  call    cs:__imp_GetModuleHandleW
0x18000a035  nop     dword ptr [rax+rax+00h]
0x18000a03a  mov     rbx, rax
0x18000a03d  test    rbx, rbx
0x18000a040  jnz     short loc_18000A04E
0x18000a042  mov     [rdi], rbx
0x18000a045  mov     [rdi+8], rbx
0x18000a049  jmp     loc_18000A0F5
0x18000a04e  lea     rdx, ProcName; "SetThreadInformation"
0x18000a055  mov     rcx, rbx; hModule
0x18000a058  call    cs:__imp_GetProcAddress
0x18000a05f  nop     dword ptr [rax+rax+00h]
0x18000a064  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x18000a06b  mov     rcx, rbx; hModule
0x18000a06e  mov     [rdi], rax
0x18000a071  call    cs:__imp_GetProcAddress
0x18000a078  nop     dword ptr [rax+rax+00h]
0x18000a07d  cmp     qword ptr [rdi], 0
0x18000a081  mov     rbx, rax
0x18000a084  mov     [rdi+8], rax
0x18000a088  jz      short loc_18000A0F5
0x18000a08a  test    rax, rax
0x18000a08d  jz      short loc_18000A0F5
0x18000a08f  mov     [rsp+38h+arg_0], 0
0x18000a097  call    cs:__imp_GetCurrentThread
0x18000a09e  nop     dword ptr [rax+rax+00h]
0x18000a0a3  mov     r9d, 4
0x18000a0a9  lea     r8, [rsp+38h+arg_0]
0x18000a0ae  mov     rcx, rax
0x18000a0b1  xor     edx, edx
0x18000a0b3  mov     rax, rbx
0x18000a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0bb  test    eax, eax
0x18000a0bd  jz      short loc_18000A0F5
0x18000a0bf  mov     eax, [rsp+38h+arg_0]
0x18000a0c3  mov     rbx, [rdi]
0x18000a0c6  mov     [rdi+10h], eax
0x18000a0c9  mov     [rsp+38h+arg_0], 1
0x18000a0d1  call    cs:__imp_GetCurrentThread
0x18000a0d8  nop     dword ptr [rax+rax+00h]
0x18000a0dd  mov     r9d, 4
0x18000a0e3  lea     r8, [rsp+38h+arg_0]
0x18000a0e8  mov     rcx, rax
0x18000a0eb  xor     edx, edx
0x18000a0ed  mov     rax, rbx
0x18000a0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f5  mov     rbx, [rsp+38h+arg_8]
0x18000a0fa  mov     rax, rdi
0x18000a0fd  add     rsp, 30h
0x18000a101  pop     rdi
0x18000a102  retn
```
