# CUwfConfiguration::Close(void)

- ea: `0x180006200`
- end: `0x180006232`
- name: `?Close@CUwfConfiguration@@QEAAXXZ`
- size: `50`
- prototype: `void __fastcall(CUwfConfiguration *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005a40`
- `0x180008170`
- `0x180014d30`
- `0x180017230`
- `0x180017ac4`

## callees

- `0x180006240`
- `0x18000d5f0`

## pseudocode

```c
void __fastcall CUwfConfiguration::Close(CUwfConfiguration *this)
{
  CUwfRegKey::Close((CUwfConfiguration *)((char *)this + 24));
  CUwfRegKey::Close((CUwfConfiguration *)((char *)this + 32));
  CUwfStaticConfiguration::Close((CUwfConfiguration *)((char *)this + 40));
  CUwfStaticConfiguration::Close((CUwfConfiguration *)((char *)this + 88));
}

```

## disassembly

```asm
0x180006200  push    rbx
0x180006202  sub     rsp, 20h
0x180006206  mov     rbx, rcx
0x180006209  add     rcx, 18h; this
0x18000620d  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180006212  lea     rcx, [rbx+20h]; this
0x180006216  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000621b  lea     rcx, [rbx+28h]; this
0x18000621f  call    ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
0x180006224  lea     rcx, [rbx+58h]; this
0x180006228  add     rsp, 20h
0x18000622c  pop     rbx
0x18000622d  jmp     ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
```
