# CAttachmentServices::_GetType(void)

- ea: `0x180006844`
- end: `0x18000686e`
- name: `?_GetType@CAttachmentServices@@AEAAPEBGXZ`
- size: `42`
- prototype: `const unsigned __int16 *__fastcall(LPCWSTR *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180010dbc`
- `0x180010e3c`
- `0x180010f64`
- `0x180011148`

## callees

- `0x180006844`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180006867`
- `SHLWAPI!PathFindFileNameW` at `0x180006854`
- `SHLWAPI!PathFindFileNameW` at `0x180006854`

## pseudocode

```c
const unsigned __int16 *__fastcall CAttachmentServices::_GetType(LPCWSTR *this)
{
  const WCHAR *FileNameW; // rax

  if ( this[5] )
    FileNameW = PathFindFileNameW(this[5]);
  else
    FileNameW = this[4];
  return PathFindExtensionW(FileNameW);
}

```

## disassembly

```asm
0x180006844  sub     rsp, 28h
0x180006848  mov     rax, [rcx+28h]
0x18000684c  test    rax, rax
0x18000684f  jz      short loc_18000685C
0x180006851  mov     rcx, rax; pszPath
0x180006854  call    cs:__imp_PathFindFileNameW
0x18000685a  jmp     short loc_180006860
0x18000685c  mov     rax, [rcx+20h]
0x180006860  mov     rcx, rax
0x180006863  add     rsp, 28h
0x180006867  jmp     cs:__imp_PathFindExtensionW
```
