# PplCreateLookasideList

- ea: `0x14000d8c8`
- end: `0x14000d90d`
- name: `PplCreateLookasideList`
- size: `69`
- prototype: `__int64 __fastcall(int, int, int, int, int, SIZE_T, ULONG, int, ULONG)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001a078`
- `0x14001b1fc`
- `0x14002e780`

## callees

- `0x14000d984`

## import_xrefs

- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14000d8d1`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14000d8d1`

## pseudocode

```c
_DWORD *__fastcall PplCreateLookasideList(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        SIZE_T a6,
        ULONG a7,
        int a8,
        ULONG a9)
{
  ULONG MaximumProcessorCount; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v14; // [rsp+20h] [rbp-38h]
  int v15; // [rsp+28h] [rbp-30h]
  int v16; // [rsp+40h] [rbp-18h]

  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  return PplpCreateLookasideListEx(MaximumProcessorCount, v10, v11, v12, v14, v15, a6, a7, v16, a9);
}

```

## disassembly

```asm
0x14000d8c8  sub     rsp, 58h
0x14000d8cc  mov     ecx, 0FFFFh; GroupNumber
0x14000d8d1  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14000d8d8  nop     dword ptr [rax+rax+00h]
0x14000d8dd  mov     ecx, eax; int
0x14000d8df  mov     eax, [rsp+58h+arg_40]
0x14000d8e6  mov     [rsp+58h+var_10], eax; ULONG
0x14000d8ea  mov     eax, [rsp+58h+arg_30]
0x14000d8f1  mov     [rsp+58h+var_20], eax; ULONG
0x14000d8f5  mov     rax, [rsp+58h+arg_28]
0x14000d8fd  mov     [rsp+58h+var_28], rax; SIZE_T
0x14000d902  call    PplpCreateLookasideListEx
0x14000d907  add     rsp, 58h
0x14000d90b  retn
```
