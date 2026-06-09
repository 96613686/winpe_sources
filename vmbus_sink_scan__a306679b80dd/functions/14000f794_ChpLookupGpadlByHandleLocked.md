# ChpLookupGpadlByHandleLocked

- ea: `0x14000f794`
- end: `0x14000f7db`
- name: `ChpLookupGpadlByHandleLocked`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000edc4`
- `0x14000eec8`
- `0x14000ef68`
- `0x14001152c`

## callees

- `0x14000f794`
- `0x140016df8`

## pseudocode

```c
__int64 __fastcall ChpLookupGpadlByHandleLocked(__int64 a1, __int64 a2, unsigned int a3, __int64 *a4)
{
  __int64 v6; // rax

  v6 = DvLookupHandleEntry(a1 + 736, a3);
  if ( !v6 || a2 && *(_QWORD *)(v6 + 56) != a2 )
    return 3221225480LL;
  *a4 = v6;
  return 0;
}

```

## disassembly

```asm
0x14000f794  mov     [rsp+arg_0], rbx
0x14000f799  push    rdi
0x14000f79a  sub     rsp, 20h
0x14000f79e  mov     rbx, rdx
0x14000f7a1  add     rcx, 2E0h
0x14000f7a8  mov     edx, r8d
0x14000f7ab  mov     rdi, r9
0x14000f7ae  call    DvLookupHandleEntry
0x14000f7b3  test    rax, rax
0x14000f7b6  jz      short loc_14000F7CA
0x14000f7b8  test    rbx, rbx
0x14000f7bb  jz      short loc_14000F7C3
0x14000f7bd  cmp     [rax+38h], rbx
0x14000f7c1  jnz     short loc_14000F7CA
0x14000f7c3  mov     [rdi], rax
0x14000f7c6  xor     eax, eax
0x14000f7c8  jmp     short loc_14000F7CF
0x14000f7ca  mov     eax, 0C0000008h
0x14000f7cf  mov     rbx, [rsp+28h+arg_0]
0x14000f7d4  add     rsp, 20h
0x14000f7d8  pop     rdi
0x14000f7d9  retn
```
