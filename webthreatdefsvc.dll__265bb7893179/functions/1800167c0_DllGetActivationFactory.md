# DllGetActivationFactory

- ea: `0x1800167c0`
- end: `0x1800167f4`
- name: `DllGetActivationFactory`
- size: `52`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800136ac`
- `0x1800143bc`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(__int64 a1, _QWORD *a2)
{
  int v2; // eax

  *a2 = 0;
  v2 = sub_1800143BC();
  return sub_1800136AC(v2);
}

```

## disassembly

```asm
0x1800167c0  mov     [rsp+arg_0], rbx
0x1800167c5  push    rdi
0x1800167c6  sub     rsp, 20h
0x1800167ca  mov     rbx, rdx
0x1800167cd  mov     qword ptr [rdx], 0
0x1800167d4  mov     rdi, rcx
0x1800167d7  call    sub_1800143BC
0x1800167dc  mov     r9, rbx
0x1800167df  mov     r8, rdi
0x1800167e2  mov     rcx, rax; int
0x1800167e5  mov     rbx, [rsp+28h+arg_0]
0x1800167ea  add     rsp, 20h
0x1800167ee  pop     rdi
0x1800167ef  jmp     sub_1800136AC
```
