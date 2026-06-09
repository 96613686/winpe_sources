# LOG_WRITER::`scalar deleting destructor'(uint)

- ea: `0x1800023a0`
- end: `0x1800023cf`
- name: `??_GLOG_WRITER@@UEAAPEAXI@Z`
- size: `47`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800022a4`
- `0x1800023a0`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall LOG_WRITER::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  LOG_WRITER::~LOG_WRITER(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800023a0  mov     [rsp+arg_0], rbx
0x1800023a5  push    rdi
0x1800023a6  sub     rsp, 20h
0x1800023aa  mov     ebx, edx
0x1800023ac  mov     rdi, rcx
0x1800023af  call    ??1LOG_WRITER@@UEAA@XZ; LOG_WRITER::~LOG_WRITER(void)
0x1800023b4  test    bl, 1
0x1800023b7  jz      short loc_1800023C1
0x1800023b9  mov     rcx, rdi; Block
0x1800023bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800023c1  mov     rbx, [rsp+28h+arg_0]
0x1800023c6  mov     rax, rdi
0x1800023c9  add     rsp, 20h
0x1800023cd  pop     rdi
0x1800023ce  retn
```
