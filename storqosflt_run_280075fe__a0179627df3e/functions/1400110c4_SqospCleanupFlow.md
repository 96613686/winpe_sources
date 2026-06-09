# SqospCleanupFlow

- ea: `0x1400110c4`
- end: `0x140011111`
- name: `SqospCleanupFlow`
- size: `77`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140004a8c`
- `0x140004b3c`

## callees

- `0x140003ec0`
- `0x1400110c4`

## import_xrefs

- `ntoskrnl!PcwCloseInstance` at `0x1400110dd`
- `ntoskrnl!PcwCloseInstance` at `0x1400110dd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400110f9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400110f9`

## pseudocode

```c
void __fastcall SqospCleanupFlow(_QWORD *Entry, __int64 a2)
{
  struct _PCW_INSTANCE *v4; // rcx

  v4 = (struct _PCW_INSTANCE *)Entry[2];
  if ( v4 )
    PcwCloseInstance(v4);
  SqospFreeUnicodeString(Entry + 7);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(a2 + 48), Entry);
}

```

## disassembly

```asm
0x1400110c4  mov     [rsp+arg_0], rbx
0x1400110c9  push    rdi
0x1400110ca  sub     rsp, 20h
0x1400110ce  mov     rbx, rcx
0x1400110d1  mov     rdi, rdx
0x1400110d4  mov     rcx, [rcx+10h]; Instance
0x1400110d8  test    rcx, rcx
0x1400110db  jz      short loc_1400110E9
0x1400110dd  call    cs:__imp_PcwCloseInstance
0x1400110e4  nop     dword ptr [rax+rax+00h]
0x1400110e9  lea     rcx, [rbx+38h]
0x1400110ed  call    SqospFreeUnicodeString
0x1400110f2  lea     rcx, [rdi+30h]; Lookaside
0x1400110f6  mov     rdx, rbx; Entry
0x1400110f9  call    cs:__imp_ExFreeToLookasideListEx
0x140011100  nop     dword ptr [rax+rax+00h]
0x140011105  mov     rbx, [rsp+28h+arg_0]
0x14001110a  add     rsp, 20h
0x14001110e  pop     rdi
0x14001110f  retn
```
