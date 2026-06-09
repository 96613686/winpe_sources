# LoadFveapi(void)

- ea: `0x180020154`
- end: `0x180020193`
- name: `?LoadFveapi@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `63`
- prototype: `HMODULE *__fastcall(HMODULE *)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001fdb4`
- `0x18001ff70`
- `0x180020040`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020178`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020178`

## string_xrefs

- `0x180020171`: `FVEAPI.DLL`

## pseudocode

```c
HMODULE *__fastcall LoadFveapi(HMODULE *a1)
{
  *a1 = LoadLibraryExW(L"FVEAPI.DLL", 0, 0x800u);
  return a1;
}

```

## disassembly

```asm
0x180020154  mov     [rsp+arg_0], rcx
0x180020159  push    rbx
0x18002015a  sub     rsp, 30h
0x18002015e  mov     rbx, rcx
0x180020161  mov     [rsp+38h+var_18], 0
0x180020169  xor     edx, edx; hFile
0x18002016b  mov     r8d, 800h; dwFlags
0x180020171  lea     rcx, aFveapiDll; "FVEAPI.DLL"
0x180020178  call    cs:__imp_LoadLibraryExW
0x18002017e  mov     [rbx], rax
0x180020181  mov     [rsp+38h+var_18], 1
0x180020189  mov     rax, rbx
0x18002018c  add     rsp, 30h
0x180020190  pop     rbx
0x180020191  retn
```
