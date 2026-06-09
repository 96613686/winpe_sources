# InitializeDLL

- ea: `0x1800018a0`
- end: `0x18000190c`
- name: `InitializeDLL`
- size: `108`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800010b8`
- `0x1800018a0`
- `0x180025010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800018d8`
- `KERNEL32!GetModuleHandleW` at `0x1800018d8`
- `KERNEL32!GetProcAddress` at `0x1800018ed`
- `KERNEL32!GetProcAddress` at `0x1800018ed`
- `RPCRT4!I_RpcAllocate` at `0x1800018bb`
- `RPCRT4!I_RpcAllocate` at `0x1800018bb`

## string_xrefs

- `0x1800018d1`: `rpcrt4.dll`

## pseudocode

```c
BOOL __stdcall InitializeDLL(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  struct _RUNTIME_IMPORT_TABLE *ModuleHandleW; // rax
  char v4; // bl

  v4 = 1;
  if ( fdwReason == 1 )
  {
    DllMainCRTStartupForGS2(hinstDLL, 1, lpReserved);
    ModuleHandleW = (struct _RUNTIME_IMPORT_TABLE *)I_RpcAllocate(0x318u);
    pRuntimeImportTable = ModuleHandleW;
    if ( ModuleHandleW
      && (ModuleHandleW = (struct _RUNTIME_IMPORT_TABLE *)GetModuleHandleW(L"rpcrt4.dll")) != 0
      && (ModuleHandleW = (struct _RUNTIME_IMPORT_TABLE *)GetProcAddress((HMODULE)ModuleHandleW, "I_RpcInitHttpImports")) != 0 )
    {
      ModuleHandleW = (struct _RUNTIME_IMPORT_TABLE *)((__int64 (__fastcall *)(struct _RUNTIME_IMPORT_TABLE *))ModuleHandleW)(pRuntimeImportTable);
    }
    else
    {
      v4 = 0;
    }
  }
  LOBYTE(ModuleHandleW) = v4;
  return (int)ModuleHandleW;
}

```

## disassembly

```asm
0x1800018a0  push    rbx
0x1800018a2  sub     rsp, 20h
0x1800018a6  mov     ebx, 1
0x1800018ab  cmp     edx, ebx
0x1800018ad  jnz     short loc_180001904
0x1800018af  mov     edx, ebx
0x1800018b1  call    _DllMainCRTStartupForGS2
0x1800018b6  mov     ecx, 318h; Size
0x1800018bb  call    cs:__imp_I_RpcAllocate
0x1800018c1  mov     cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA, rax; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800018c8  test    rax, rax
0x1800018cb  jnz     short loc_1800018D1
0x1800018cd  xor     bl, bl
0x1800018cf  jmp     short loc_180001904
0x1800018d1  lea     rcx, ModuleName; "rpcrt4.dll"
0x1800018d8  call    cs:__imp_GetModuleHandleW
0x1800018de  test    rax, rax
0x1800018e1  jz      short loc_1800018CD
0x1800018e3  lea     rdx, ProcName; "I_RpcInitHttpImports"
0x1800018ea  mov     rcx, rax; hModule
0x1800018ed  call    cs:__imp_GetProcAddress
0x1800018f3  test    rax, rax
0x1800018f6  jz      short loc_1800018CD
0x1800018f8  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800018ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001904  mov     al, bl
0x180001906  add     rsp, 20h
0x18000190a  pop     rbx
0x18000190b  retn
```
