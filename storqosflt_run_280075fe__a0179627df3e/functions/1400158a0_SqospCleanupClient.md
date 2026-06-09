# SqospCleanupClient

- ea: `0x1400158a0`
- end: `0x1400158de`
- name: `SqospCleanupClient`
- size: `62`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001ab0`
- `0x140003650`
- `0x140003940`
- `0x140015810`

## callees

- `0x140003ec0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400158cb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400158cb`

## pseudocode

```c
void __fastcall SqospCleanupClient(char *Entry)
{
  SqospFreeUnicodeString(Entry + 168);
  SqospFreeUnicodeString(Entry + 184);
  ExFreeToLookasideListEx(&Lookaside, Entry);
}

```

## disassembly

```asm
0x1400158a0  push    rbx
0x1400158a2  sub     rsp, 20h
0x1400158a6  mov     rbx, rcx
0x1400158a9  add     rcx, 0A8h
0x1400158b0  call    SqospFreeUnicodeString
0x1400158b5  lea     rcx, [rbx+0B8h]
0x1400158bc  call    SqospFreeUnicodeString
0x1400158c1  mov     rdx, rbx; Entry
0x1400158c4  lea     rcx, Lookaside; Lookaside
0x1400158cb  call    cs:__imp_ExFreeToLookasideListEx
0x1400158d2  nop     dword ptr [rax+rax+00h]
0x1400158d7  add     rsp, 20h
0x1400158db  pop     rbx
0x1400158dc  retn
```
