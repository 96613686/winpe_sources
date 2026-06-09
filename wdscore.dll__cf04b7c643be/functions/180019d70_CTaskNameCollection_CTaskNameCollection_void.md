# CTaskNameCollection::~CTaskNameCollection(void)

- ea: `0x180019d70`
- end: `0x180019dbc`
- name: `??1CTaskNameCollection@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CTaskNameCollection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180019e68`

## callees

- `0x18000f200`
- `0x180019d70`
- `0x180019dc4`
- `0x180019e90`
- `0x18001ab98`

## pseudocode

```c
void __fastcall CTaskNameCollection::~CTaskNameCollection(CTaskNameCollection *this)
{
  CBuffer *v2; // rbx
  CTaskNameHolder *v3; // rax
  unsigned int v4; // edx

  v2 = (CTaskNameCollection *)((char *)this + 16);
  while ( 1 )
  {
    v3 = (CTaskNameHolder *)CStack<CTaskNameHolder *>::Pop(v2);
    if ( !v3 )
      break;
    CTaskNameHolder::`scalar deleting destructor'(v3, v4);
  }
  CBuffer::~CBuffer(v2);
  CTaskNameHolder::~CTaskNameHolder(this);
}

```

## disassembly

```asm
0x180019d70  push    rdi
0x180019d72  sub     rsp, 30h
0x180019d76  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180019d7f  mov     [rsp+38h+arg_0], rbx
0x180019d84  mov     rdi, rcx
0x180019d87  lea     rbx, [rcx+10h]
0x180019d8b  jmp     short loc_180019D95
0x180019d8d  mov     rcx, rax; this
0x180019d90  call    ??_GCTaskNameHolder@@QEAAPEAXI@Z; CTaskNameHolder::`scalar deleting destructor'(uint)
0x180019d95  mov     rcx, rbx
0x180019d98  call    ?Pop@?$CStack@PEAVCTaskNameHolder@@@@QEAAPEAVCTaskNameHolder@@XZ; CStack<CTaskNameHolder *>::Pop(void)
0x180019d9d  test    rax, rax
0x180019da0  jnz     short loc_180019D8D
0x180019da2  mov     rcx, rbx; this
0x180019da5  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180019daa  mov     rcx, rdi; this
0x180019dad  mov     rbx, [rsp+38h+arg_0]
0x180019db2  add     rsp, 30h
0x180019db6  pop     rdi
0x180019db7  jmp     ??1CTaskNameHolder@@QEAA@XZ; CTaskNameHolder::~CTaskNameHolder(void)
```
