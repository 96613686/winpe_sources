# ComTaskHost::`vector deleting destructor'(uint)

- ea: `0x140006090`
- end: `0x1400060c3`
- name: `??_EComTaskHost@@UEAAPEAXI@Z`
- size: `51`
- prototype: `ComTaskHost *__fastcall(ComTaskHost *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140006090`
- `0x1400060d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400060bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400060bb`

## pseudocode

```c
ComTaskHost *__fastcall ComTaskHost::`vector deleting destructor'(ComTaskHost *this, char a2)
{
  ComTaskHost::~ComTaskHost(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140006090  mov     [rsp+arg_0], rbx
0x140006095  push    rdi
0x140006096  sub     rsp, 20h
0x14000609a  mov     edi, edx
0x14000609c  mov     rbx, rcx
0x14000609f  call    ??1ComTaskHost@@UEAA@XZ; ComTaskHost::~ComTaskHost(void)
0x1400060a4  test    dil, 1
0x1400060a8  jnz     short loc_1400060B8
0x1400060aa  mov     rax, rbx
0x1400060ad  mov     rbx, [rsp+28h+arg_0]
0x1400060b2  add     rsp, 20h
0x1400060b6  pop     rdi
0x1400060b7  retn
0x1400060b8  mov     rcx, rbx
0x1400060bb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400060c1  jmp     short loc_1400060AA
```
