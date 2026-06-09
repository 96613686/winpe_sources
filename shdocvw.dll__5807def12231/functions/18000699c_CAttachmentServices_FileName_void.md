# CAttachmentServices::_FileName(void)

- ea: `0x18000699c`
- end: `0x1800069b4`
- name: `?_FileName@CAttachmentServices@@AEAAPEBGXZ`
- size: `24`
- prototype: `const unsigned __int16 *__fastcall(LPCWSTR *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180010cb0`
- `0x180010dbc`
- `0x180010f64`

## callees

- `0x18000699c`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1800069a8`

## pseudocode

```c
const unsigned __int16 *__fastcall CAttachmentServices::_FileName(LPCWSTR *this)
{
  if ( this[5] )
    return PathFindFileNameW(this[5]);
  else
    return this[4];
}

```

## disassembly

```asm
0x18000699c  mov     rax, [rcx+28h]
0x1800069a0  test    rax, rax
0x1800069a3  jz      short loc_1800069AF
0x1800069a5  mov     rcx, rax
0x1800069a8  jmp     cs:__imp_PathFindFileNameW
0x1800069af  mov     rax, [rcx+20h]
0x1800069b3  retn
```
