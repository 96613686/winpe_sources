# CUxThemeFile::DeleteStockBitmap(HBITMAP__ *)

- ea: `0x18000f67c`
- end: `0x18000f6f9`
- name: `?DeleteStockBitmap@CUxThemeFile@@CAXPEAUHBITMAP__@@@Z`
- size: `125`
- prototype: `void __fastcall(HBITMAP)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f3d8`

## callees

- `0x18000f67c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f6ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f6c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f6ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f6c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f695`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f695`

## string_xrefs

- `0x18000f68e`: `GDI32.DLL`
- `0x18000f6b3`: `DeleteObject`

## pseudocode

```c
void __fastcall CUxThemeFile::DeleteStockBitmap(HBITMAP a1)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rbx
  FARPROC v5; // rdi
  __int64 v6; // rax

  ModuleHandleW = GetModuleHandleW(L"GDI32.DLL");
  v3 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "ClearBitmapAttributes");
    v5 = GetProcAddress(v3, "DeleteObject");
    v6 = ((__int64 (__fastcall *)(HBITMAP, __int64))ProcAddress)(a1, 1);
    if ( v6 )
      ((void (__fastcall *)(__int64))v5)(v6);
  }
}

```

## disassembly

```asm
0x18000f67c  mov     [rsp+arg_0], rbx
0x18000f681  mov     [rsp+arg_8], rsi
0x18000f686  push    rdi
0x18000f687  sub     rsp, 20h
0x18000f68b  mov     rsi, rcx
0x18000f68e  lea     rcx, aGdi32Dll; "GDI32.DLL"
0x18000f695  call    cs:__imp_GetModuleHandleW
0x18000f69b  mov     rdi, rax
0x18000f69e  test    rax, rax
0x18000f6a1  jz      short loc_18000F6E9
0x18000f6a3  lea     rdx, aClearbitmapatt; "ClearBitmapAttributes"
0x18000f6aa  mov     rcx, rax; hModule
0x18000f6ad  call    cs:__imp_GetProcAddress
0x18000f6b3  lea     rdx, aDeleteobject; "DeleteObject"
0x18000f6ba  mov     rcx, rdi; hModule
0x18000f6bd  mov     rbx, rax
0x18000f6c0  call    cs:__imp_GetProcAddress
0x18000f6c6  mov     edx, 1
0x18000f6cb  mov     rcx, rsi
0x18000f6ce  mov     rdi, rax
0x18000f6d1  mov     rax, rbx
0x18000f6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d9  test    rax, rax
0x18000f6dc  jz      short loc_18000F6E9
0x18000f6de  mov     rcx, rax
0x18000f6e1  mov     rax, rdi
0x18000f6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6e9  mov     rbx, [rsp+28h+arg_0]
0x18000f6ee  mov     rsi, [rsp+28h+arg_8]
0x18000f6f3  add     rsp, 20h
0x18000f6f7  pop     rdi
0x18000f6f8  retn
```
