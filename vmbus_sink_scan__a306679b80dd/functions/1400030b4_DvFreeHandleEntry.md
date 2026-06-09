# DvFreeHandleEntry

- ea: `0x1400030b4`
- end: `0x1400030f3`
- name: `DvFreeHandleEntry`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400019c0`
- `0x140002c50`
- `0x140002f04`
- `0x1400030fc`
- `0x14000f90c`
- `0x140015c50`

## callees

- `0x1400030b4`
- `0x140016e58`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400030e1`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400030e1`

## pseudocode

```c
BOOLEAN __fastcall DvFreeHandleEntry(__int64 a1, __int64 a2)
{
  struct _RTL_AVL_TABLE *v3; // rcx
  int Buffer; // [rsp+20h] [rbp-18h] BYREF
  __int64 v5; // [rsp+24h] [rbp-14h]

  v5 = 0;
  if ( (unsigned int)a2 < *(_DWORD *)(a1 + 8) )
    return DvpPushFreeEntries(*(_QWORD *)a1, a2, *(_QWORD *)a1 + 8LL * (unsigned int)a2);
  v3 = *(struct _RTL_AVL_TABLE **)(a1 + 40);
  Buffer = a2;
  return RtlDeleteElementGenericTableAvl(v3, &Buffer);
}

```

## disassembly

```asm
0x1400030b4  sub     rsp, 38h
0x1400030b8  xor     eax, eax
0x1400030ba  mov     [rsp+38h+var_14], rax
0x1400030bf  cmp     edx, [rcx+8]
0x1400030c2  jnb     short loc_1400030D4
0x1400030c4  mov     rcx, [rcx]
0x1400030c7  mov     eax, edx
0x1400030c9  lea     r8, [rcx+rax*8]
0x1400030cd  call    DvpPushFreeEntries
0x1400030d2  jmp     short loc_1400030ED
0x1400030d4  mov     rcx, [rcx+28h]; Table
0x1400030d8  mov     [rsp+38h+Buffer], edx
0x1400030dc  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1400030e1  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400030e8  nop     dword ptr [rax+rax+00h]
0x1400030ed  add     rsp, 38h
0x1400030f1  retn
```
