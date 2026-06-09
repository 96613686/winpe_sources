# InstanceContextDestroy

- ea: `0x140003d5c`
- end: `0x140003dc7`
- name: `InstanceContextDestroy`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a70`
- `0x14000b720`
- `0x1400298f0`
- `0x14002c0a0`

## callees

- `0x140003d5c`
- `0x14000ebc0`
- `0x14000fe8c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003d76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003d76`

## pseudocode

```c
void __fastcall InstanceContextDestroy(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 296);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x73756256u);
    *(_QWORD *)(a1 + 296) = 0;
  }
  if ( *(_QWORD *)(a1 + 288) )
  {
    ChCleanupGpadls();
    ChDereferenceChannelInternal(*(_QWORD *)(a1 + 288), 40, 260);
    *(_QWORD *)(a1 + 288) = 0;
  }
}

```

## disassembly

```asm
0x140003d5c  push    rbx
0x140003d5e  sub     rsp, 20h
0x140003d62  mov     rbx, rcx
0x140003d65  mov     rcx, [rcx+128h]; P
0x140003d6c  test    rcx, rcx
0x140003d6f  jz      short loc_140003D8D
0x140003d71  mov     edx, 73756256h; Tag
0x140003d76  call    cs:__imp_ExFreePoolWithTag
0x140003d7d  nop     dword ptr [rax+rax+00h]
0x140003d82  mov     qword ptr [rbx+128h], 0
0x140003d8d  mov     rcx, [rbx+120h]
0x140003d94  test    rcx, rcx
0x140003d97  jz      short loc_140003DC0
0x140003d99  call    ChCleanupGpadls
0x140003d9e  mov     rcx, [rbx+120h]
0x140003da5  mov     edx, 28h ; '('
0x140003daa  mov     r8d, 104h
0x140003db0  call    ChDereferenceChannelInternal
0x140003db5  mov     qword ptr [rbx+120h], 0
0x140003dc0  add     rsp, 20h
0x140003dc4  pop     rbx
0x140003dc5  retn
```
