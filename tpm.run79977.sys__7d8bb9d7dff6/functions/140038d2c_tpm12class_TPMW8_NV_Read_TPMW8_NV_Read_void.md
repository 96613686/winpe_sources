# tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read(void)

- ea: `0x140038d2c`
- end: `0x140038d8b`
- name: `??1TPMW8_NV_Read@tpm12class@@UEAA@XZ`
- size: `95`
- prototype: `void __fastcall(tpm12class::TPMW8_NV_Read *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033154`
- `0x140038da0`

## callees

- `0x14000c5c4`
- `0x14000da40`

## pseudocode

```c
void __fastcall tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read(tpm12class::TPMW8_NV_Read *this)
{
  *(_QWORD *)this = &tpm12class::TPMW8_NV_Read::`vftable';
  *((_DWORD *)this + 48) = 1073741831;
  *((_DWORD *)this + 68) = 1073741831;
  *((_DWORD *)this + 88) = 0;
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_NV_Read *)((char *)this + 360));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_NV_Read *)((char *)this + 280));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_NV_Read *)((char *)this + 200));
  tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(this);
}

```

## disassembly

```asm
0x140038d2c  push    rbx
0x140038d2e  sub     rsp, 20h
0x140038d32  lea     rax, ??_7TPMW8_NV_Read@tpm12class@@6B@; const tpm12class::TPMW8_NV_Read::`vftable'
0x140038d39  mov     rbx, rcx
0x140038d3c  mov     [rcx], rax
0x140038d3f  mov     eax, 40000007h
0x140038d44  mov     [rcx+0C0h], eax
0x140038d4a  mov     [rcx+110h], eax
0x140038d50  xor     eax, eax
0x140038d52  mov     [rcx+160h], eax
0x140038d58  add     rcx, 168h; this
0x140038d5f  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140038d64  lea     rcx, [rbx+118h]; this
0x140038d6b  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140038d70  lea     rcx, [rbx+0C8h]; this
0x140038d77  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140038d7c  mov     rcx, rbx; this
0x140038d7f  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x140038d84  add     rsp, 20h
0x140038d88  pop     rbx
0x140038d89  retn
```
