# FreeGenericBuffer

- ea: `0x14000164c`
- end: `0x1400016a5`
- name: `FreeGenericBuffer`
- size: `89`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1400016ac`
- `0x14000aad0`
- `0x14000ab5c`
- `0x14000ae50`
- `0x14000b854`
- `0x14000b908`
- `0x14000c078`
- `0x14000c1bc`

## callees

- `0x140001118`
- `0x140001168`
- `0x14000164c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001673`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001673`

## pseudocode

```c
ULONG __fastcall FreeGenericBuffer(PVOID P, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r8

  DbgTrace(3, "UevFilter.FreeGenericBuffer: Entry\n", a3);
  if ( P )
    ExFreePoolWithTag(P, 0x66766575u);
  else
    DbgTraceErr("UevFilter.FreeGenericBuffer: Invalid parameter specified\n", v4, v5);
  return DbgTrace(3, "UevFilter.FreeGenericBuffer: Exit\n", v6);
}

```

## disassembly

```asm
0x14000164c  push    rbx
0x14000164e  sub     rsp, 20h
0x140001652  mov     rbx, rcx
0x140001655  lea     rdx, aUevfilterFreeg_3; "UevFilter.FreeGenericBuffer: Entry\n"
0x14000165c  mov     ecx, 3
0x140001661  call    DbgTrace
0x140001666  test    rbx, rbx
0x140001669  jz      short loc_140001681
0x14000166b  mov     edx, 66766575h; Tag
0x140001670  mov     rcx, rbx; P
0x140001673  call    cs:__imp_ExFreePoolWithTag
0x14000167a  nop     dword ptr [rax+rax+00h]
0x14000167f  jmp     short loc_14000168D
0x140001681  lea     rcx, aUevfilterFreeg_4; "UevFilter.FreeGenericBuffer: Invalid pa"...
0x140001688  call    DbgTraceErr
0x14000168d  lea     rdx, aUevfilterFreeg_1; "UevFilter.FreeGenericBuffer: Exit\n"
0x140001694  mov     ecx, 3
0x140001699  call    DbgTrace
0x14000169e  add     rsp, 20h
0x1400016a2  pop     rbx
0x1400016a3  retn
```
