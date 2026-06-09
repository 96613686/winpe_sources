# EncodeOneField(ushort const *,STRU *)

- ea: `0x180002c20`
- end: `0x180002c7c`
- name: `?EncodeOneField@@YAJPEBGPEAVSTRU@@@Z`
- size: `92`
- prototype: `int __fastcall(const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002c84`

## callees

- `0x180002c20`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002c3f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002c4e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002c3f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002c4e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002c5e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002c5e`
- `iisutil!?Escape@STRU@@QEAAJXZ` at `0x180002c6b`
- `iisutil!?Escape@STRU@@QEAAJXZ` at `0x180002c6b`

## pseudocode

```c
int __fastcall EncodeOneField(const unsigned __int16 *a1, struct STRU *a2)
{
  int result; // eax

  if ( !a1 )
    return STRU::Copy(a2, L"0");
  result = STRU::Copy(a2, L"1");
  if ( result >= 0 )
  {
    result = STRU::Append(a2, a1);
    if ( result >= 0 )
      return STRU::Escape(a2);
  }
  return result;
}

```

## disassembly

```asm
0x180002c20  mov     [rsp+arg_0], rbx
0x180002c25  push    rdi
0x180002c26  sub     rsp, 20h
0x180002c2a  mov     rdi, rcx
0x180002c2d  test    rcx, rcx
0x180002c30  mov     rcx, rdx
0x180002c33  mov     rbx, rdx
0x180002c36  jnz     short loc_180002C47
0x180002c38  lea     rdx, a0; "0"
0x180002c3f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002c45  jmp     short loc_180002C71
0x180002c47  lea     rdx, a1; "1"
0x180002c4e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002c54  test    eax, eax
0x180002c56  js      short loc_180002C71
0x180002c58  mov     rdx, rdi
0x180002c5b  mov     rcx, rbx
0x180002c5e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002c64  test    eax, eax
0x180002c66  js      short loc_180002C71
0x180002c68  mov     rcx, rbx
0x180002c6b  call    cs:__imp_?Escape@STRU@@QEAAJXZ; STRU::Escape(void)
0x180002c71  mov     rbx, [rsp+28h+arg_0]
0x180002c76  add     rsp, 20h
0x180002c7a  pop     rdi
0x180002c7b  retn
```
