# CUwfStaticConfiguration::~CUwfStaticConfiguration(void)

- ea: `0x180005a90`
- end: `0x180005ac7`
- name: `??1CUwfStaticConfiguration@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CUwfStaticConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005a40`
- `0x180005b80`

## callees

- `0x180006240`
- `0x180008cf0`
- `0x18000d5f0`

## pseudocode

```c
void __fastcall CUwfStaticConfiguration::~CUwfStaticConfiguration(CUwfStaticConfiguration *this)
{
  *(_QWORD *)this = &CUwfStaticConfiguration::`vftable';
  CUwfStaticConfiguration::Close(this);
  CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
  CUwfRegKey::Close((CUwfStaticConfiguration *)((char *)this + 24));
  CUwfRegKey::Close((CUwfStaticConfiguration *)((char *)this + 16));
}

```

## disassembly

```asm
0x180005a90  push    rbx
0x180005a92  sub     rsp, 20h
0x180005a96  lea     rax, ??_7CUwfStaticConfiguration@@6B@; const CUwfStaticConfiguration::`vftable'
0x180005a9d  mov     rbx, rcx
0x180005aa0  mov     [rcx], rax
0x180005aa3  call    ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
0x180005aa8  mov     rcx, rbx; this
0x180005aab  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180005ab0  lea     rcx, [rbx+18h]; this
0x180005ab4  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180005ab9  lea     rcx, [rbx+10h]; this
0x180005abd  add     rsp, 20h
0x180005ac1  pop     rbx
0x180005ac2  jmp     ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
```
