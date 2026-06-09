# MTX_mem_Create

- ea: `0x18001d1cc`
- end: `0x18001d21e`
- name: `MTX_mem_Create`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eb94`
- `0x18001a414`

## callees

- `0x18001d1cc`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall MTX_mem_Create(__int64 (__fastcall *a1)(__int64), __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = a1(304);
  if ( result )
  {
    *(_QWORD *)result = 0;
    *(_QWORD *)(result + 8) = 0;
    *(_DWORD *)(result + 16) = 0;
    *(_QWORD *)(result + 24) = a1;
    *(_QWORD *)(result + 32) = a2;
    *(_QWORD *)(result + 40) = a3;
  }
  return result;
}

```

## disassembly

```asm
0x18001d1cc  mov     [rsp+arg_0], rbx
0x18001d1d1  mov     [rsp+arg_8], rsi
0x18001d1d6  push    rdi
0x18001d1d7  sub     rsp, 20h
0x18001d1db  mov     rbx, rcx
0x18001d1de  mov     rdi, r8
0x18001d1e1  mov     rax, rbx
0x18001d1e4  mov     ecx, 130h
0x18001d1e9  mov     rsi, rdx
0x18001d1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1f1  xor     ecx, ecx
0x18001d1f3  test    rax, rax
0x18001d1f6  jz      short loc_18001D20E
0x18001d1f8  mov     [rax], rcx
0x18001d1fb  mov     [rax+8], rcx
0x18001d1ff  mov     [rax+10h], ecx
0x18001d202  mov     [rax+18h], rbx
0x18001d206  mov     [rax+20h], rsi
0x18001d20a  mov     [rax+28h], rdi
0x18001d20e  mov     rbx, [rsp+28h+arg_0]
0x18001d213  mov     rsi, [rsp+28h+arg_8]
0x18001d218  add     rsp, 20h
0x18001d21c  pop     rdi
0x18001d21d  retn
```
