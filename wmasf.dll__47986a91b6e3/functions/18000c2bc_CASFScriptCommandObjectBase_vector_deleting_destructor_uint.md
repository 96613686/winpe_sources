# CASFScriptCommandObjectBase::`vector deleting destructor'(uint)

- ea: `0x18000c2bc`
- end: `0x18000c2f0`
- name: `??_ECASFScriptCommandObjectBase@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CASFScriptCommandObjectBase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c260`

## callees

- `0x1800011c0`
- `0x18000c1d4`
- `0x18000c2bc`

## pseudocode

```c
CASFScriptCommandObjectBase *__fastcall CASFScriptCommandObjectBase::`vector deleting destructor'(
        CASFScriptCommandObjectBase *this,
        char a2)
{
  CASFScriptCommandObjectBase::~CASFScriptCommandObjectBase(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c2bc  mov     [rsp+arg_0], rbx
0x18000c2c1  push    rdi
0x18000c2c2  sub     rsp, 20h
0x18000c2c6  mov     ebx, edx
0x18000c2c8  mov     rdi, rcx
0x18000c2cb  call    ??1CASFScriptCommandObjectBase@@UEAA@XZ; CASFScriptCommandObjectBase::~CASFScriptCommandObjectBase(void)
0x18000c2d0  test    bl, 1
0x18000c2d3  jz      short loc_18000C2E2
0x18000c2d5  mov     edx, 360h
0x18000c2da  mov     rcx, rdi; Block
0x18000c2dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c2e2  mov     rbx, [rsp+28h+arg_0]
0x18000c2e7  mov     rax, rdi
0x18000c2ea  add     rsp, 20h
0x18000c2ee  pop     rdi
0x18000c2ef  retn
```
