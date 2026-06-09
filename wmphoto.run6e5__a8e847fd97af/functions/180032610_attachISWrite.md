# attachISWrite

- ea: `0x180032610`
- end: `0x18003265f`
- name: `attachISWrite`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001024`
- `0x180007340`

## callees

- `0x180044010`

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
0x180032610  mov     [rsp+arg_0], rbx
0x180032615  push    rdi
0x180032616  sub     rsp, 20h
0x18003261a  mov     rdi, rdx
0x18003261d  mov     rbx, rcx
0x180032620  lea     rdx, [rcx+28h]
0x180032624  mov     rcx, rdi
0x180032627  mov     rax, [rdi+60h]
0x18003262b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032630  lea     rax, [rbx-2000h]
0x180032637  mov     qword ptr [rbx+4], 0
0x18003263f  mov     [rbx+10h], rax
0x180032643  mov     [rbx+18h], rax
0x180032647  xor     eax, eax
0x180032649  mov     dword ptr [rbx+0Ch], 0FFFFDFFFh
0x180032650  mov     [rbx+20h], rdi
0x180032654  mov     rbx, [rsp+28h+arg_0]
0x180032659  add     rsp, 20h
0x18003265d  pop     rdi
0x18003265e  retn
```
