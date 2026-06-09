# BWCContentProviderConfiguration::`scalar deleting destructor'(uint)

- ea: `0x18000fa90`
- end: `0x18000fabf`
- name: `??_GBWCContentProviderConfiguration@@UEAAPEAXI@Z`
- size: `47`
- prototype: `BWCContentProviderConfiguration *__fastcall(BWCContentProviderConfiguration *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800010b4`
- `0x18000f9f0`
- `0x18000fa90`

## pseudocode

```c
BWCContentProviderConfiguration *__fastcall BWCContentProviderConfiguration::`scalar deleting destructor'(
        BWCContentProviderConfiguration *this,
        char a2)
{
  BWCContentProviderConfiguration::~BWCContentProviderConfiguration(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000fa90  mov     [rsp+arg_0], rbx
0x18000fa95  push    rdi
0x18000fa96  sub     rsp, 20h
0x18000fa9a  mov     ebx, edx
0x18000fa9c  mov     rdi, rcx
0x18000fa9f  call    ??1BWCContentProviderConfiguration@@UEAA@XZ; BWCContentProviderConfiguration::~BWCContentProviderConfiguration(void)
0x18000faa4  test    bl, 1
0x18000faa7  jz      short loc_18000FAB1
0x18000faa9  mov     rcx, rdi; Block
0x18000faac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fab1  mov     rbx, [rsp+28h+arg_0]
0x18000fab6  mov     rax, rdi
0x18000fab9  add     rsp, 20h
0x18000fabd  pop     rdi
0x18000fabe  retn
```
