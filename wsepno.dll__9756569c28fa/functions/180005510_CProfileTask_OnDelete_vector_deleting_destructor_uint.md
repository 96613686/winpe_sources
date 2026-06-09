# CProfileTask_OnDelete::`vector deleting destructor'(uint)

- ea: `0x180005510`
- end: `0x180005544`
- name: `??_ECProfileTask_OnDelete@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CProfileTask_OnDelete *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001794`
- `0x180004d60`
- `0x180005510`

## pseudocode

```c
CProfileTask_OnDelete *__fastcall CProfileTask_OnDelete::`vector deleting destructor'(
        CProfileTask_OnDelete *this,
        char a2)
{
  CProfileTask_OnDelete::~CProfileTask_OnDelete(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005510  mov     [rsp+arg_0], rbx
0x180005515  push    rdi
0x180005516  sub     rsp, 20h
0x18000551a  mov     ebx, edx
0x18000551c  mov     rdi, rcx
0x18000551f  call    ??1CProfileTask_OnDelete@@UEAA@XZ; CProfileTask_OnDelete::~CProfileTask_OnDelete(void)
0x180005524  test    bl, 1
0x180005527  jz      short loc_180005536
0x180005529  mov     edx, 20h ; ' '
0x18000552e  mov     rcx, rdi; Block
0x180005531  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005536  mov     rbx, [rsp+28h+arg_0]
0x18000553b  mov     rax, rdi
0x18000553e  add     rsp, 20h
0x180005542  pop     rdi
0x180005543  retn
```
