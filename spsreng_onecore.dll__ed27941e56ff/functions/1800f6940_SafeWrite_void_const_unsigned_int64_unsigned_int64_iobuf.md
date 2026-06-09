# SafeWrite(void const *,unsigned __int64,unsigned __int64,_iobuf *)

- ea: `0x1800f6940`
- end: `0x1800f6974`
- name: `?SafeWrite@@YAJPEBX_K1PEAU_iobuf@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(const void *, unsigned __int64, unsigned __int64, struct _iobuf *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800f697c`
- `0x1800f6b10`
- `0x1800f7940`
- `0x1800f79d0`
- `0x1800f7ad0`
- `0x1800f8700`
- `0x1800f87a0`
- `0x1800f8800`
- `0x1800f8fb0`

## callees

- `0x1800f6940`
- `0x1800f6cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f694e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f694e`

## string_xrefs

- `0x1800f6959`: `Failed to write to file!`

## pseudocode

```c
__int64 __fastcall SafeWrite(const void *a1, __int64 a2, __int64 a3, struct _iobuf *a4)
{
  if ( !a3 || _o_fwrite(a1, a2, a3, a4) == a3 )
    return 0;
  WPFsmError(L"Failed to write to file!");
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800f6940  push    rbx
0x1800f6942  sub     rsp, 20h
0x1800f6946  mov     rbx, r8
0x1800f6949  test    r8, r8
0x1800f694c  jz      short loc_1800F696C
0x1800f694e  call    cs:__imp__o_fwrite
0x1800f6954  cmp     rax, rbx
0x1800f6957  jz      short loc_1800F696C
0x1800f6959  lea     rcx, aFailedToWriteT; "Failed to write to file!"
0x1800f6960  call    ?WPFsmError@@YAXPEBGZZ; WPFsmError(ushort const *,...)
0x1800f6965  mov     eax, 80004005h
0x1800f696a  jmp     short loc_1800F696E
0x1800f696c  xor     eax, eax
0x1800f696e  add     rsp, 20h
0x1800f6972  pop     rbx
0x1800f6973  retn
```
