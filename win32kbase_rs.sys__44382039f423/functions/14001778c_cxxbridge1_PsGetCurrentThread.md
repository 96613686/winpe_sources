# cxxbridge1$PsGetCurrentThread

- ea: `0x14001778c`
- end: `0x1400177a4`
- name: `cxxbridge1$PsGetCurrentThread`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400101f0`

## callees

- `0x140017580`

## pseudocode

```c
PETHREAD __fastcall cxxbridge1_PsGetCurrentThread(PETHREAD *a1)
{
  PETHREAD result; // rax

  result = PsGetCurrentThread();
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x14001778c  push    rbx
0x14001778e  sub     rsp, 20h
0x140017792  mov     rbx, rcx
0x140017795  call    PsGetCurrentThread
0x14001779a  mov     [rbx], rax
0x14001779d  add     rsp, 20h
0x1400177a1  pop     rbx
0x1400177a2  retn
```
