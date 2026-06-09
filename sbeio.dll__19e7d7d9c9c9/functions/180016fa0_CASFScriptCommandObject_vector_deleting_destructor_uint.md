# CASFScriptCommandObject::`vector deleting destructor'(uint)

- ea: `0x180016fa0`
- end: `0x180016fd4`
- name: `??_ECASFScriptCommandObject@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CASFScriptCommandObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001194`
- `0x180016028`
- `0x180016fa0`

## pseudocode

```c
CASFScriptCommandObject *__fastcall CASFScriptCommandObject::`vector deleting destructor'(
        CASFScriptCommandObject *this,
        char a2)
{
  CASFScriptCommandObject::~CASFScriptCommandObject(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180016fa0  mov     [rsp+arg_0], rbx
0x180016fa5  push    rdi
0x180016fa6  sub     rsp, 20h
0x180016faa  mov     ebx, edx
0x180016fac  mov     rdi, rcx
0x180016faf  call    ??1CASFScriptCommandObject@@UEAA@XZ; CASFScriptCommandObject::~CASFScriptCommandObject(void)
0x180016fb4  test    bl, 1
0x180016fb7  jz      short loc_180016FC6
0x180016fb9  mov     edx, 60h ; '`'; unsigned __int64
0x180016fbe  mov     rcx, rdi; void *
0x180016fc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016fc6  mov     rbx, [rsp+28h+arg_0]
0x180016fcb  mov     rax, rdi
0x180016fce  add     rsp, 20h
0x180016fd2  pop     rdi
0x180016fd3  retn
```
