# tip_details_GetKernelBaseModuleHandle

- ea: `0x18001db40`
- end: `0x18001db69`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001aec8`
- `0x18001cbfc`
- `0x18001da38`
- `0x18001da84`
- `0x18001daf4`

## callees

- `0x18001db40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001db57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001db57`

## string_xrefs

- `0x18001db50`: `kernelbase.dll`

## pseudocode

```c
HMODULE tip_details_GetKernelBaseModuleHandle()
{
  HMODULE result; // rax

  result = (HMODULE)g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    result = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x18001db40  sub     rsp, 28h
0x18001db44  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001db4b  test    rax, rax
0x18001db4e  jnz     short loc_18001DB64
0x18001db50  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001db57  call    cs:__imp_GetModuleHandleW
0x18001db5d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001db64  add     rsp, 28h
0x18001db68  retn
```
