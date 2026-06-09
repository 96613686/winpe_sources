# CProfileTask_OnMigrate::`vector deleting destructor'(uint)

- ea: `0x180005550`
- end: `0x180005584`
- name: `??_ECProfileTask_OnMigrate@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CProfileTask_OnMigrate *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001794`
- `0x180004dac`
- `0x180005550`

## pseudocode

```c
CProfileTask_OnMigrate *__fastcall CProfileTask_OnMigrate::`vector deleting destructor'(
        CProfileTask_OnMigrate *this,
        char a2)
{
  CProfileTask_OnMigrate::~CProfileTask_OnMigrate(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005550  mov     [rsp+arg_0], rbx
0x180005555  push    rdi
0x180005556  sub     rsp, 20h
0x18000555a  mov     ebx, edx
0x18000555c  mov     rdi, rcx
0x18000555f  call    ??1CProfileTask_OnMigrate@@UEAA@XZ; CProfileTask_OnMigrate::~CProfileTask_OnMigrate(void)
0x180005564  test    bl, 1
0x180005567  jz      short loc_180005576
0x180005569  mov     edx, 20h ; ' '
0x18000556e  mov     rcx, rdi; Block
0x180005571  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005576  mov     rbx, [rsp+28h+arg_0]
0x18000557b  mov     rax, rdi
0x18000557e  add     rsp, 20h
0x180005582  pop     rdi
0x180005583  retn
```
