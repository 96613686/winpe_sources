# SafeRead(void *,unsigned __int64,unsigned __int64,_iobuf *)

- ea: `0x1800f6904`
- end: `0x1800f6938`
- name: `?SafeRead@@YAJPEAX_K1PEAU_iobuf@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *, size_t, size_t, struct _iobuf *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800f596c`
- `0x1800f5b90`
- `0x1800f7420`
- `0x1800f7570`
- `0x1800f76e0`
- `0x1800f7ecc`
- `0x1800f7fb0`
- `0x1800f8110`
- `0x1800f8c10`

## callees

- `0x1800f6904`
- `0x1800f6cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f6912`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f6912`

## string_xrefs

- `0x1800f691d`: `Failed to read from file!`

## pseudocode

```c
__int64 __fastcall SafeRead(void *a1, size_t a2, size_t a3, struct _iobuf *a4)
{
  if ( !a3 || fread(a1, a2, a3, a4) == a3 )
    return 0;
  WPFsmError(L"Failed to read from file!");
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800f6904  push    rbx
0x1800f6906  sub     rsp, 20h
0x1800f690a  mov     rbx, r8
0x1800f690d  test    r8, r8
0x1800f6910  jz      short loc_1800F6930
0x1800f6912  call    cs:__imp_fread
0x1800f6918  cmp     rax, rbx
0x1800f691b  jz      short loc_1800F6930
0x1800f691d  lea     rcx, aFailedToReadFr; "Failed to read from file!"
0x1800f6924  call    ?WPFsmError@@YAXPEBGZZ; WPFsmError(ushort const *,...)
0x1800f6929  mov     eax, 80004005h
0x1800f692e  jmp     short loc_1800F6932
0x1800f6930  xor     eax, eax
0x1800f6932  add     rsp, 20h
0x1800f6936  pop     rbx
0x1800f6937  retn
```
