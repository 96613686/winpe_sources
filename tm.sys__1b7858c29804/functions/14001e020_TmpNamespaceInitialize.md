# TmpNamespaceInitialize

- ea: `0x14001e020`
- end: `0x14001e087`
- name: `TmpNamespaceInitialize`
- size: `103`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140011dbc`
- `0x140014c50`
- `0x140024080`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14001e045`
- `ntoskrnl!KeInitializeMutex` at `0x14001e045`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14001e072`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14001e072`

## pseudocode

```c
__int64 __fastcall TmpNamespaceInitialize(PRTL_AVL_TABLE Table, __int16 a2, __int16 a3)
{
  LOWORD(Table[1].RestartKey) = a2;
  WORD1(Table[1].RestartKey) = a3;
  BYTE4(Table[1].RestartKey) = 0;
  KeInitializeMutex((PRKMUTEX)&Table[1], 0);
  RtlInitializeGenericTableAvl(
    Table,
    (PRTL_AVL_COMPARE_ROUTINE)TmpNamespaceCompareGuids,
    TmpNamespaceAllocateEntry,
    TmpNamespaceFreeEntry,
    0);
  return 0;
}

```

## disassembly

```asm
0x14001e020  push    rbx
0x14001e022  sub     rsp, 30h
0x14001e026  mov     [rcx+0A0h], dx
0x14001e02d  mov     rbx, rcx
0x14001e030  mov     [rcx+0A2h], r8w
0x14001e038  xor     edx, edx; Level
0x14001e03a  mov     byte ptr [rcx+0A4h], 0
0x14001e041  add     rcx, 68h ; 'h'; Mutex
0x14001e045  call    cs:__imp_KeInitializeMutex
0x14001e04c  nop     dword ptr [rax+rax+00h]
0x14001e051  lea     r9, TmpNamespaceFreeEntry; FreeRoutine
0x14001e058  mov     [rsp+38h+TableContext], 0; TableContext
0x14001e061  lea     r8, TmpNamespaceAllocateEntry; AllocateRoutine
0x14001e068  mov     rcx, rbx; Table
0x14001e06b  lea     rdx, TmpNamespaceCompareGuids; CompareRoutine
0x14001e072  call    cs:__imp_RtlInitializeGenericTableAvl
0x14001e079  nop     dword ptr [rax+rax+00h]
0x14001e07e  xor     eax, eax
0x14001e080  add     rsp, 30h
0x14001e084  pop     rbx
0x14001e085  retn
```
