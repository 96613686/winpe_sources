# CWerComReport::`vector deleting destructor'(uint)

- ea: `0x180009ac0`
- end: `0x180009aef`
- name: `??_ECWerComReport@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CWerComReport *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x18000917c`
- `0x180009ac0`

## pseudocode

```c
CWerComReport *__fastcall CWerComReport::`vector deleting destructor'(CWerComReport *this, char a2)
{
  CWerComReport::~CWerComReport(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009ac0  mov     [rsp+arg_0], rbx
0x180009ac5  push    rdi
0x180009ac6  sub     rsp, 20h
0x180009aca  mov     ebx, edx
0x180009acc  mov     rdi, rcx
0x180009acf  call    ??1CWerComReport@@UEAA@XZ; CWerComReport::~CWerComReport(void)
0x180009ad4  test    bl, 1
0x180009ad7  jz      short loc_180009AE1
0x180009ad9  mov     rcx, rdi; Block
0x180009adc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ae1  mov     rbx, [rsp+28h+arg_0]
0x180009ae6  mov     rax, rdi
0x180009ae9  add     rsp, 20h
0x180009aed  pop     rdi
0x180009aee  retn
```
