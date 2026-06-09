# tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(void)

- ea: `0x140034f08`
- end: `0x140034f7c`
- name: `??0TPMW8_COMMAND@tpm12class@@QEAA@XZ`
- size: `116`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140037ddc`
- `0x140038108`
- `0x1400382b0`
- `0x140038688`
- `0x140038a84`
- `0x140038c38`

## callees

- `0x140035d90`

## pseudocode

```c
tpm12class::TPMW8_COMMAND *__fastcall tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(tpm12class::TPMW8_COMMAND *this)
{
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_BYTE *)this + 48) = 0;
  *(_QWORD *)this = &tpm12class::TPMW8_COMMAND::`vftable';
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_BYTE *)this + 136) = 0;
  *((_WORD *)this + 72) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 11) = &tpm12class::TPMW82B_BUFFER::`vftable';
  tpm12class::TPMW8_COMMAND::Clear(this, 1);
  return this;
}

```

## disassembly

```asm
0x140034f08  push    rbx
0x140034f0a  sub     rsp, 20h
0x140034f0e  mov     rbx, rcx
0x140034f11  lea     rax, ??_7TPMW8_COMMAND@tpm12class@@6B@; const tpm12class::TPMW8_COMMAND::`vftable'
0x140034f18  xor     ecx, ecx
0x140034f1a  mov     dl, 1; unsigned __int8
0x140034f1c  mov     [rbx+8], rcx
0x140034f20  mov     [rbx+10h], rcx
0x140034f24  mov     [rbx+18h], ecx
0x140034f27  mov     [rbx+20h], rcx
0x140034f2b  mov     [rbx+28h], rcx
0x140034f2f  mov     [rbx+30h], cl
0x140034f32  mov     [rbx], rax
0x140034f35  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x140034f3c  mov     [rbx+60h], rcx
0x140034f40  mov     [rbx+68h], rcx
0x140034f44  mov     [rbx+70h], ecx
0x140034f47  mov     [rbx+78h], rcx
0x140034f4b  mov     [rbx+80h], rcx
0x140034f52  mov     [rbx+88h], cl
0x140034f58  mov     [rbx+90h], cx
0x140034f5f  mov     [rbx+98h], rcx
0x140034f66  mov     rcx, rbx; this
0x140034f69  mov     [rbx+58h], rax
0x140034f6d  call    ?Clear@TPMW8_COMMAND@tpm12class@@MEAAJE@Z; tpm12class::TPMW8_COMMAND::Clear(uchar)
0x140034f72  mov     rax, rbx
0x140034f75  add     rsp, 20h
0x140034f79  pop     rbx
0x140034f7a  retn
```
