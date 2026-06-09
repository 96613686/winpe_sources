# InpCancelMdlMapLocked

- ea: `0x14000862c`
- end: `0x140008661`
- name: `InpCancelMdlMapLocked`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001170`
- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x140007e30`

## callees

- `0x14000862c`
- `0x140011ed0`

## pseudocode

```c
char __fastcall InpCancelMdlMapLocked(_QWORD *a1)
{
  char result; // al

  result = 0;
  if ( *(_QWORD *)(*a1 + 2664LL) )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(*a1 + 2664LL))(*(_QWORD *)(*a1 + 2368LL), a1[178] + 16LL);
  return result;
}

```

## disassembly

```asm
0x14000862c  sub     rsp, 28h
0x140008630  mov     r8, [rcx]
0x140008633  xor     al, al
0x140008635  mov     r9, [r8+0A68h]
0x14000863c  test    r9, r9
0x14000863f  jz      short loc_14000865B
0x140008641  mov     rdx, [rcx+590h]
0x140008648  mov     rax, r9
0x14000864b  mov     rcx, [r8+940h]
0x140008652  add     rdx, 10h
0x140008656  call    _guard_dispatch_icall
0x14000865b  add     rsp, 28h
0x14000865f  retn
```
