# attachISWrite

- ea: `0x180032aa4`
- end: `0x180032af4`
- name: `attachISWrite`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001024`
- `0x180007400`

## callees

- `0x180045010`

## pseudocode

```c
__int64 __fastcall attachISWrite(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  (*(void (__fastcall **)(__int64, __int64))(a2 + 96))(a2, a1 + 40);
  *(_QWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 16) = a1 - 0x2000;
  *(_QWORD *)(a1 + 24) = a1 - 0x2000;
  result = 0;
  *(_DWORD *)(a1 + 12) = -8193;
  *(_QWORD *)(a1 + 32) = a2;
  return result;
}

```

## disassembly

```asm
0x180032aa4  mov     [rsp+arg_0], rbx
0x180032aa9  push    rdi
0x180032aaa  sub     rsp, 20h
0x180032aae  mov     rdi, rdx
0x180032ab1  mov     rbx, rcx
0x180032ab4  lea     rdx, [rcx+28h]
0x180032ab8  mov     rcx, rdi
0x180032abb  mov     rax, [rdi+60h]
0x180032abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ac4  lea     rax, [rbx-2000h]
0x180032acb  mov     qword ptr [rbx+4], 0
0x180032ad3  mov     [rbx+10h], rax
0x180032ad7  mov     [rbx+18h], rax
0x180032adb  xor     eax, eax
0x180032add  mov     dword ptr [rbx+0Ch], 0FFFFDFFFh
0x180032ae4  mov     [rbx+20h], rdi
0x180032ae8  mov     rbx, [rsp+28h+arg_0]
0x180032aed  add     rsp, 20h
0x180032af1  pop     rdi
0x180032af2  retn
```
