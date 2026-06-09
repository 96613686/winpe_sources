# NetpCloseConfigData

- ea: `0x180007a90`
- end: `0x180007ac3`
- name: `NetpCloseConfigData`
- size: `51`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800061d8`
- `0x18000743c`
- `0x180007844`
- `0x18002c5a8`
- `0x18002d1e8`

## callees

- `0x180007a90`
- `0x180007cb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007aa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007aa6`

## pseudocode

```c
__int64 __fastcall NetpCloseConfigData(HKEY *a1)
{
  if ( !a1 )
    return 87;
  RegCloseKey(*a1);
  NetpMemoryFree(a1);
  return 0;
}

```

## disassembly

```asm
0x180007a90  push    rbx
0x180007a92  sub     rsp, 20h
0x180007a96  mov     rbx, rcx
0x180007a99  test    rcx, rcx
0x180007a9c  jnz     short loc_180007AA3
0x180007a9e  lea     eax, [rcx+57h]
0x180007aa1  jmp     short loc_180007ABC
0x180007aa3  mov     rcx, [rcx]; hKey
0x180007aa6  call    cs:__imp_RegCloseKey
0x180007aad  nop     dword ptr [rax+rax+00h]
0x180007ab2  mov     rcx, rbx
0x180007ab5  call    NetpMemoryFree
0x180007aba  xor     eax, eax
0x180007abc  add     rsp, 20h
0x180007ac0  pop     rbx
0x180007ac1  retn
```
