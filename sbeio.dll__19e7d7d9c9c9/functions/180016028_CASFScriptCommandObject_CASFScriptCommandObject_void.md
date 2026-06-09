# CASFScriptCommandObject::~CASFScriptCommandObject(void)

- ea: `0x180016028`
- end: `0x180016050`
- name: `??1CASFScriptCommandObject@@UEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CASFScriptCommandObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016fa0`

## callees

- `0x1800181fc`

## pseudocode

```c
void __fastcall CASFScriptCommandObject::~CASFScriptCommandObject(CASFScriptCommandObject *this)
{
  *(_QWORD *)this = &CASFScriptCommandObject::`vftable';
  CASFScriptCommandObject::Clear(this);
  *(_QWORD *)this = &CPersistentObject::`vftable';
}

```

## disassembly

```asm
0x180016028  push    rbx
0x18001602a  sub     rsp, 20h
0x18001602e  lea     rax, ??_7CASFScriptCommandObject@@6B@; const CASFScriptCommandObject::`vftable'
0x180016035  mov     rbx, rcx
0x180016038  mov     [rcx], rax
0x18001603b  call    ?Clear@CASFScriptCommandObject@@QEAAXXZ; CASFScriptCommandObject::Clear(void)
0x180016040  lea     rax, ??_7CPersistentObject@@6B@; const CPersistentObject::`vftable'
0x180016047  mov     [rbx], rax
0x18001604a  add     rsp, 20h
0x18001604e  pop     rbx
0x18001604f  retn
```
