# tip_details_GetKernelBaseModuleHandle

- ea: `0x14000a2d4`
- end: `0x14000a2fd`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14004b8d8`
- `0x14004b924`
- `0x14005d6fc`
- `0x14005d9cc`
- `0x14005f760`

## callees

- `0x14000a2d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a2eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a2eb`

## string_xrefs

- `0x14000a2e4`: `kernelbase.dll`

## pseudocode

```c
HMODULE tip_details_GetKernelBaseModuleHandle()
{
  HMODULE result; // rax

  result = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    result = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = result;
  }
  return result;
}

```

## disassembly

```asm
0x14000a2d4  sub     rsp, 28h
0x14000a2d8  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14000a2df  test    rax, rax
0x14000a2e2  jnz     short loc_14000A2F8
0x14000a2e4  lea     rcx, ModuleName; "kernelbase.dll"
0x14000a2eb  call    cs:__imp_GetModuleHandleW
0x14000a2f1  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14000a2f8  add     rsp, 28h
0x14000a2fc  retn
```
