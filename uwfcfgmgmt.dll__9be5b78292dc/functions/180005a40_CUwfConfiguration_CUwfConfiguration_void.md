# CUwfConfiguration::~CUwfConfiguration(void)

- ea: `0x180005a40`
- end: `0x180005a81`
- name: `??1CUwfConfiguration@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CUwfConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005b00`
- `0x180014b40`

## callees

- `0x180005a90`
- `0x180006200`
- `0x18000d5f0`

## pseudocode

```c
void __fastcall CUwfConfiguration::~CUwfConfiguration(CUwfConfiguration *this)
{
  *(_QWORD *)this = &CUwfConfiguration::`vftable';
  CUwfConfiguration::Close(this);
  CUwfStaticConfiguration::~CUwfStaticConfiguration((CUwfConfiguration *)((char *)this + 88));
  CUwfStaticConfiguration::~CUwfStaticConfiguration((CUwfConfiguration *)((char *)this + 40));
  CUwfRegKey::Close((CUwfConfiguration *)((char *)this + 32));
  CUwfRegKey::Close((CUwfConfiguration *)((char *)this + 24));
}

```

## disassembly

```asm
0x180005a40  push    rbx
0x180005a42  sub     rsp, 20h
0x180005a46  lea     rax, ??_7CUwfConfiguration@@6B@; const CUwfConfiguration::`vftable'
0x180005a4d  mov     rbx, rcx
0x180005a50  mov     [rcx], rax
0x180005a53  call    ?Close@CUwfConfiguration@@QEAAXXZ; CUwfConfiguration::Close(void)
0x180005a58  lea     rcx, [rbx+58h]; this
0x180005a5c  call    ??1CUwfStaticConfiguration@@UEAA@XZ; CUwfStaticConfiguration::~CUwfStaticConfiguration(void)
0x180005a61  lea     rcx, [rbx+28h]; this
0x180005a65  call    ??1CUwfStaticConfiguration@@UEAA@XZ; CUwfStaticConfiguration::~CUwfStaticConfiguration(void)
0x180005a6a  lea     rcx, [rbx+20h]; this
0x180005a6e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180005a73  lea     rcx, [rbx+18h]; this
0x180005a77  add     rsp, 20h
0x180005a7b  pop     rbx
0x180005a7c  jmp     ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
```
