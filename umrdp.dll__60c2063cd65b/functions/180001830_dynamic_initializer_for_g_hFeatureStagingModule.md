# _dynamic_initializer_for__g_hFeatureStagingModule__

- ea: `0x180001830`
- end: `0x180001860`
- name: `_dynamic_initializer_for__g_hFeatureStagingModule__`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c2c4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180001843`
- `KERNEL32!LoadLibraryExW` at `0x180001843`

## string_xrefs

- `0x180001836`: `api-ms-win-core-featurestaging-l1-1-0.dll`

## pseudocode

```c
int dynamic_initializer_for__g_hFeatureStagingModule__()
{
  hLibModule = LoadLibraryExW(L"api-ms-win-core-featurestaging-l1-1-0.dll", 0, 0x800u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_hFeatureStagingModule__);
}

```

## disassembly

```asm
0x180001830  sub     rsp, 28h
0x180001834  xor     edx, edx; hFile
0x180001836  lea     rcx, LibFileName; "api-ms-win-core-featurestaging-l1-1-0.d"...
0x18000183d  mov     r8d, 800h; dwFlags
0x180001843  call    cs:__imp_LoadLibraryExW
0x180001849  lea     rcx, _dynamic_atexit_destructor_for__g_hFeatureStagingModule__
0x180001850  mov     cs:hLibModule, rax
0x180001857  add     rsp, 28h
0x18000185b  jmp     atexit
```
