# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18000e2f0`
- end: `0x18000e31f`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `47`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800023f4`
- `0x18000e2a0`
- `0x18000e2f0`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e2f0  mov     [rsp+arg_0], rbx
0x18000e2f5  push    rdi
0x18000e2f6  sub     rsp, 20h
0x18000e2fa  mov     ebx, edx
0x18000e2fc  mov     rdi, rcx
0x18000e2ff  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18000e304  test    bl, 1
0x18000e307  jz      short loc_18000E311
0x18000e309  mov     rcx, rdi; Block
0x18000e30c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e311  mov     rbx, [rsp+28h+arg_0]
0x18000e316  mov     rax, rdi
0x18000e319  add     rsp, 20h
0x18000e31d  pop     rdi
0x18000e31e  retn
```
