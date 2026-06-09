# CConfigServiceProvider2Impl::`vector deleting destructor'(uint)

- ea: `0x180019480`
- end: `0x1800194b0`
- name: `??_ECConfigServiceProvider2Impl@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CConfigServiceProvider2Impl *__fastcall(CConfigServiceProvider2Impl *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18001943c`
- `0x180019480`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001949c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001949c`

## pseudocode

```c
CConfigServiceProvider2Impl *__fastcall CConfigServiceProvider2Impl::`vector deleting destructor'(
        CConfigServiceProvider2Impl *this,
        char a2)
{
  CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180019480  mov     [rsp+arg_0], rbx
0x180019485  push    rdi
0x180019486  sub     rsp, 20h
0x18001948a  mov     ebx, edx
0x18001948c  mov     rdi, rcx
0x18001948f  call    ??1CConfigServiceProvider2Impl@@UEAA@XZ; CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)
0x180019494  test    bl, 1
0x180019497  jz      short loc_1800194A2
0x180019499  mov     rcx, rdi
0x18001949c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800194a2  mov     rbx, [rsp+28h+arg_0]
0x1800194a7  mov     rax, rdi
0x1800194aa  add     rsp, 20h
0x1800194ae  pop     rdi
0x1800194af  retn
```
