# VerCharNextA(char const *)

- ea: `0x180001d60`
- end: `0x180001d95`
- name: `?VerCharNextA@@YAPEADPEBD@Z`
- size: `53`
- prototype: `char *__fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002898`

## callees

- `0x180001d60`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x180001d77`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x180001d77`
- `ntdll!NlsMbCodePageTag` at `0x180001d66`

## pseudocode

```c
BYTE *__fastcall VerCharNextA(BYTE *a1)
{
  BYTE *v1; // rbx
  BYTE *result; // rax

  v1 = a1;
  if ( NlsMbCodePageTag && IsDBCSLeadByte(*a1) )
    ++v1;
  result = v1 + 1;
  if ( !*v1 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x180001d60  push    rbx
0x180001d62  sub     rsp, 20h
0x180001d66  mov     rax, cs:NlsMbCodePageTag
0x180001d6d  mov     rbx, rcx
0x180001d70  cmp     byte ptr [rax], 0
0x180001d73  jz      short loc_180001D84
0x180001d75  mov     cl, [rcx]; TestChar
0x180001d77  call    cs:__imp_IsDBCSLeadByte
0x180001d7d  test    eax, eax
0x180001d7f  jz      short loc_180001D84
0x180001d81  inc     rbx
0x180001d84  cmp     byte ptr [rbx], 0
0x180001d87  lea     rax, [rbx+1]
0x180001d8b  cmovz   rax, rbx
0x180001d8f  add     rsp, 20h
0x180001d93  pop     rbx
0x180001d94  retn
```
