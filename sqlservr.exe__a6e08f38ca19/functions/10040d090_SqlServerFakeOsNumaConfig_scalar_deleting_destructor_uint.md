# SqlServerFakeOsNumaConfig::`scalar deleting destructor'(uint)

- ea: `0x10040d090`
- end: `0x10040d0d4`
- name: `??_GSqlServerFakeOsNumaConfig@@UEAAPEAXI@Z`
- size: `68`
- prototype: `void *__fastcall(SqlServerFakeOsNumaConfig *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x10040d090`

## import_xrefs

- `sqldk!??3@YAXPEAX_K@Z` at `0x10040d0c0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040d0c0`
- `sqldk!??1FakeOsNumaConfig@@UEAA@XZ` at `0x10040d0ad`
- `sqldk!??1FakeOsNumaConfig@@UEAA@XZ` at `0x10040d0ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SqlServerFakeOsNumaConfig *__fastcall SqlServerFakeOsNumaConfig::`scalar deleting destructor'(
        SqlServerFakeOsNumaConfig *this,
        char a2)
{
  FakeOsNumaConfig::~FakeOsNumaConfig(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x698u);
  return this;
}

```

## disassembly

```asm
0x10040d090  mov     [rsp+arg_0], rcx
0x10040d095  push    rdi
0x10040d096  sub     rsp, 30h
0x10040d09a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10040d0a3  mov     [rsp+38h+arg_8], rbx
0x10040d0a8  mov     ebx, edx
0x10040d0aa  mov     rdi, rcx
0x10040d0ad  call    cs:__imp_??1FakeOsNumaConfig@@UEAA@XZ; FakeOsNumaConfig::~FakeOsNumaConfig(void)
0x10040d0b3  test    bl, 1
0x10040d0b6  jz      short loc_10040D0C6
0x10040d0b8  mov     edx, 698h
0x10040d0bd  mov     rcx, rdi
0x10040d0c0  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10040d0c6  mov     rax, rdi
0x10040d0c9  mov     rbx, [rsp+38h+arg_8]
0x10040d0ce  add     rsp, 30h
0x10040d0d2  pop     rdi
0x10040d0d3  retn
```
