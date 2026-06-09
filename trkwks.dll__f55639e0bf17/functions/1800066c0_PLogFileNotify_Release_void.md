# PLogFileNotify::Release(void)

- ea: `0x1800066c0`
- end: `0x1800066f4`
- name: `?Release@PLogFileNotify@@QEAAKXZ`
- size: `52`
- prototype: `__int64 __fastcall(PLogFileNotify *this)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180001494`
- `0x180001500`
- `0x180001588`
- `0x180001b64`
- `0x180002488`
- `0x180004ac0`
- `0x180005590`
- `0x180005660`
- `0x1800073a0`
- `0x18000747c`
- `0x180007c08`
- `0x1800090c8`
- `0x18000b5b0`
- `0x18000bd24`
- `0x18000c968`
- `0x18000d318`
- `0x18000d4dc`
- `0x18000d5e4`
- `0x18000f744`

## callees

- `0x1800066c0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall PLogFileNotify::Release(PLogFileNotify *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (**(void (__fastcall ***)(PLogFileNotify *, __int64))this)(this, 1);
  return v1;
}

```

## disassembly

```asm
0x1800066c0  push    rbx
0x1800066c2  sub     rsp, 20h
0x1800066c6  mov     ebx, 0FFFFFFFFh
0x1800066cb  lock xadd [rcx+8], ebx
0x1800066d0  sub     ebx, 1
0x1800066d3  jz      short loc_1800066DD
0x1800066d5  mov     eax, ebx
0x1800066d7  add     rsp, 20h
0x1800066db  pop     rbx
0x1800066dc  retn
0x1800066dd  test    rcx, rcx
0x1800066e0  jz      short loc_1800066D5
0x1800066e2  mov     rax, [rcx]
0x1800066e5  mov     edx, 1
0x1800066ea  mov     rax, [rax]
0x1800066ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f2  jmp     short loc_1800066D5
```
