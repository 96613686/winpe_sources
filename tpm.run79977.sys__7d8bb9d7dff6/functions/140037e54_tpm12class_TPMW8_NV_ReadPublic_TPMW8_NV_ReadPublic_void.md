# tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic(void)

- ea: `0x140037e54`
- end: `0x140037eb4`
- name: `??1TPMW8_NV_ReadPublic@tpm12class@@UEAA@XZ`
- size: `96`
- prototype: `void __fastcall(tpm12class::TPMW8_NV_ReadPublic *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140033154`
- `0x140037ec0`

## callees

- `0x14000c5c4`
- `0x14000da40`
- `0x140037e54`
- `0x140039780`

## pseudocode

```c
void __fastcall tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic(tpm12class::TPMW8_NV_ReadPublic *this)
{
  __int64 v2; // rcx

  *((_DWORD *)this + 49) = 0;
  *(_QWORD *)this = &tpm12class::TPMW8_NV_ReadPublic::`vftable';
  v2 = *((_QWORD *)this + 25);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 32LL))(v2, 1);
    *((_QWORD *)this + 25) = 0;
  }
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_NV_ReadPublic *)((char *)this + 208));
  tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(this);
}

```

## disassembly

```asm
0x140037e54  push    rbx
0x140037e56  sub     rsp, 20h
0x140037e5a  lea     rax, ??_7TPMW8_NV_ReadPublic@tpm12class@@6B@; const tpm12class::TPMW8_NV_ReadPublic::`vftable'
0x140037e61  mov     dword ptr [rcx+0C4h], 0
0x140037e6b  mov     [rcx], rax
0x140037e6e  mov     rbx, rcx
0x140037e71  mov     rcx, [rcx+0C8h]
0x140037e78  test    rcx, rcx
0x140037e7b  jz      short loc_140037E99
0x140037e7d  mov     rax, [rcx]
0x140037e80  mov     edx, 1
0x140037e85  mov     rax, [rax+20h]
0x140037e89  call    _guard_dispatch_icall
0x140037e8e  mov     qword ptr [rbx+0C8h], 0
0x140037e99  lea     rcx, [rbx+0D0h]; this
0x140037ea0  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140037ea5  mov     rcx, rbx; this
0x140037ea8  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x140037ead  add     rsp, 20h
0x140037eb1  pop     rbx
0x140037eb2  retn
```
