# ShouldFileBeCompressed

- ea: `0x1800287d0`
- end: `0x18002882d`
- name: `ShouldFileBeCompressed`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019008`

## callees

- `0x1800287d0`

## import_xrefs

- `SHLWAPI!PathFindExtensionA` at `0x1800287db`
- `SHLWAPI!PathFindExtensionA` at `0x1800287db`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180028818`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180028818`

## string_xrefs

- `0x1800287ef`: `DontCompressInPackage`

## pseudocode

```c
__int64 __fastcall ShouldFileBeCompressed(const CHAR *a1)
{
  unsigned int v1; // ebx
  const CHAR *ExtensionA; // rax

  v1 = 1;
  ExtensionA = PathFindExtensionA(a1);
  if ( ExtensionA )
    return RegGetValueA(HKEY_CLASSES_ROOT, ExtensionA, "DontCompressInPackage", 0xFFFFu, 0, 0, 0) != 0;
  return v1;
}

```

## disassembly

```asm
0x1800287d0  push    rbx
0x1800287d2  sub     rsp, 40h
0x1800287d6  mov     ebx, 1
0x1800287db  call    cs:__imp_PathFindExtensionA
0x1800287e1  test    rax, rax
0x1800287e4  jz      short loc_180028825
0x1800287e6  mov     [rsp+48h+pcbData], 0; pcbData
0x1800287ef  lea     r8, Value; "DontCompressInPackage"
0x1800287f6  mov     [rsp+48h+pvData], 0; pvData
0x1800287ff  mov     r9d, 0FFFFh; dwFlags
0x180028805  mov     rdx, rax; lpSubKey
0x180028808  mov     [rsp+48h+pdwType], 0; pdwType
0x180028811  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180028818  call    cs:__imp_RegGetValueA
0x18002881e  xor     ecx, ecx
0x180028820  test    eax, eax
0x180028822  cmovz   ebx, ecx
0x180028825  mov     eax, ebx
0x180028827  add     rsp, 40h
0x18002882b  pop     rbx
0x18002882c  retn
```
