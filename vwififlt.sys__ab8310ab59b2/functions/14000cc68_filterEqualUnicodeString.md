# filterEqualUnicodeString

- ea: `0x14000cc68`
- end: `0x14000cca1`
- name: `filterEqualUnicodeString`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000228c`
- `0x140009e70`

## callees

- `0x14000cc68`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000cc83`
- `ntoskrnl!RtlCompareMemory` at `0x14000cc83`

## pseudocode

```c
bool __fastcall filterEqualUnicodeString(const void **a1, __int64 a2)
{
  int v2; // eax

  v2 = *(unsigned __int16 *)a1;
  return (_WORD)v2 == *(_WORD *)a2 && RtlCompareMemory(a1[1], *(const void **)(a2 + 8), *(unsigned __int16 *)a1) == v2;
}

```

## disassembly

```asm
0x14000cc68  push    rbx
0x14000cc6a  sub     rsp, 20h
0x14000cc6e  movzx   eax, word ptr [rcx]
0x14000cc71  cmp     ax, [rdx]
0x14000cc74  jnz     short loc_14000CC98
0x14000cc76  mov     rdx, [rdx+8]; Source2
0x14000cc7a  mov     r8d, eax; Length
0x14000cc7d  mov     rcx, [rcx+8]; Source1
0x14000cc81  mov     ebx, eax
0x14000cc83  call    cs:__imp_RtlCompareMemory
0x14000cc8a  nop     dword ptr [rax+rax+00h]
0x14000cc8f  cmp     rax, rbx
0x14000cc92  jnz     short loc_14000CC98
0x14000cc94  mov     al, 1
0x14000cc96  jmp     short loc_14000CC9A
0x14000cc98  xor     al, al
0x14000cc9a  add     rsp, 20h
0x14000cc9e  pop     rbx
0x14000cc9f  retn
```
