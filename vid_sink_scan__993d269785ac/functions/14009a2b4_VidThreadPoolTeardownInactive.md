# VidThreadPoolTeardownInactive

- ea: `0x14009a2b4`
- end: `0x14009a31e`
- name: `VidThreadPoolTeardownInactive`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009ea4`
- `0x14000f690`

## callees

- `0x14009a2b4`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009a2dd`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009a2dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009a2f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009a2f2`
- `ntoskrnl!ExQueryDepthSList` at `0x14009a2c5`
- `ntoskrnl!ExQueryDepthSList` at `0x14009a301`
- `ntoskrnl!ExQueryDepthSList` at `0x14009a2c5`
- `ntoskrnl!ExQueryDepthSList` at `0x14009a301`

## pseudocode

```c
USHORT __fastcall VidThreadPoolTeardownInactive(union _SLIST_HEADER *a1)
{
  USHORT DepthSList; // di
  union _SLIST_HEADER *v3; // rbx
  PSLIST_ENTRY v4; // rax
  USHORT result; // ax

  DepthSList = ExQueryDepthSList(a1 + 5);
  v3 = a1 + 6;
  while ( 1 )
  {
    result = ExQueryDepthSList(v3);
    if ( DepthSList == result )
      break;
    v4 = ExpInterlockedPopEntrySList(v3);
    ExFreePoolWithTag(&v4[-4], 0x72446456u);
  }
  return result;
}

```

## disassembly

```asm
0x14009a2b4  mov     [rsp+arg_0], rbx
0x14009a2b9  push    rdi
0x14009a2ba  sub     rsp, 20h
0x14009a2be  mov     rbx, rcx
0x14009a2c1  add     rcx, 50h ; 'P'; SListHead
0x14009a2c5  call    cs:__imp_ExQueryDepthSList
0x14009a2cc  nop     dword ptr [rax+rax+00h]
0x14009a2d1  movzx   edi, ax
0x14009a2d4  add     rbx, 60h ; '`'
0x14009a2d8  jmp     short loc_14009A2FE
0x14009a2da  mov     rcx, rbx; ListHead
0x14009a2dd  call    cs:__imp_ExpInterlockedPopEntrySList
0x14009a2e4  nop     dword ptr [rax+rax+00h]
0x14009a2e9  mov     edx, 72446456h; Tag
0x14009a2ee  lea     rcx, [rax-40h]; P
0x14009a2f2  call    cs:__imp_ExFreePoolWithTag
0x14009a2f9  nop     dword ptr [rax+rax+00h]
0x14009a2fe  mov     rcx, rbx; SListHead
0x14009a301  call    cs:__imp_ExQueryDepthSList
0x14009a308  nop     dword ptr [rax+rax+00h]
0x14009a30d  cmp     di, ax
0x14009a310  jnz     short loc_14009A2DA
0x14009a312  mov     rbx, [rsp+28h+arg_0]
0x14009a317  add     rsp, 20h
0x14009a31b  pop     rdi
0x14009a31c  retn
```
