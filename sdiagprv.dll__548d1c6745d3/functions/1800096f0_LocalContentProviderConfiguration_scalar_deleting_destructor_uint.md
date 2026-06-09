# LocalContentProviderConfiguration::`scalar deleting destructor'(uint)

- ea: `0x1800096f0`
- end: `0x18000971f`
- name: `??_GLocalContentProviderConfiguration@@UEAAPEAXI@Z`
- size: `47`
- prototype: `LocalContentProviderConfiguration *__fastcall(LocalContentProviderConfiguration *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800010b4`
- `0x18000969c`
- `0x1800096f0`

## pseudocode

```c
LocalContentProviderConfiguration *__fastcall LocalContentProviderConfiguration::`scalar deleting destructor'(
        LocalContentProviderConfiguration *this,
        char a2)
{
  LocalContentProviderConfiguration::~LocalContentProviderConfiguration(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800096f0  mov     [rsp+arg_0], rbx
0x1800096f5  push    rdi
0x1800096f6  sub     rsp, 20h
0x1800096fa  mov     ebx, edx
0x1800096fc  mov     rdi, rcx
0x1800096ff  call    ??1LocalContentProviderConfiguration@@UEAA@XZ; LocalContentProviderConfiguration::~LocalContentProviderConfiguration(void)
0x180009704  test    bl, 1
0x180009707  jz      short loc_180009711
0x180009709  mov     rcx, rdi; Block
0x18000970c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009711  mov     rbx, [rsp+28h+arg_0]
0x180009716  mov     rax, rdi
0x180009719  add     rsp, 20h
0x18000971d  pop     rdi
0x18000971e  retn
```
