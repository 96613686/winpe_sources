# tpm12class::TPMW8_NV_Read::TPMW8_NV_Read(void)

- ea: `0x140038c38`
- end: `0x140038d24`
- name: `??0TPMW8_NV_Read@tpm12class@@QEAA@XZ`
- size: `236`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_NV_Read *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033154`

## callees

- `0x140034f08`
- `0x140038de0`

## pseudocode

```c
tpm12class::TPMW8_NV_Read *__fastcall tpm12class::TPMW8_NV_Read::TPMW8_NV_Read(tpm12class::TPMW8_NV_Read *this)
{
  tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(this);
  *(_QWORD *)this = &tpm12class::TPMW8_NV_Read::`vftable';
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 25) = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)this + 128) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_BYTE *)this + 328) = 0;
  *((_QWORD *)this + 35) = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)this + 168) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_BYTE *)this + 408) = 0;
  *((_QWORD *)this + 45) = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)this + 208) = 0;
  *((_QWORD *)this + 53) = 0;
  tpm12class::TPMW8_NV_Read::Clear(this, 1);
  return this;
}

```

## disassembly

```asm
0x140038c38  push    rbx
0x140038c3a  sub     rsp, 20h
0x140038c3e  mov     rbx, rcx
0x140038c41  call    ??0TPMW8_COMMAND@tpm12class@@QEAA@XZ; tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(void)
0x140038c46  xor     edx, edx
0x140038c48  lea     rcx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x140038c4f  lea     rax, ??_7TPMW8_NV_Read@tpm12class@@6B@; const tpm12class::TPMW8_NV_Read::`vftable'
0x140038c56  mov     [rbx], rax
0x140038c59  mov     [rbx+0D0h], rdx
0x140038c60  mov     [rbx+0D8h], rdx
0x140038c67  mov     [rbx+0E0h], edx
0x140038c6d  mov     [rbx+0E8h], rdx
0x140038c74  mov     [rbx+0F0h], rdx
0x140038c7b  mov     [rbx+0F8h], dl
0x140038c81  mov     [rbx+0C8h], rcx
0x140038c88  mov     [rbx+100h], dx
0x140038c8f  mov     [rbx+108h], rdx
0x140038c96  mov     [rbx+120h], rdx
0x140038c9d  mov     [rbx+128h], rdx
0x140038ca4  mov     [rbx+130h], edx
0x140038caa  mov     [rbx+138h], rdx
0x140038cb1  mov     [rbx+140h], rdx
0x140038cb8  mov     [rbx+148h], dl
0x140038cbe  mov     [rbx+118h], rcx
0x140038cc5  mov     [rbx+150h], dx
0x140038ccc  mov     [rbx+158h], rdx
0x140038cd3  mov     [rbx+170h], rdx
0x140038cda  mov     [rbx+178h], rdx
0x140038ce1  mov     [rbx+180h], edx
0x140038ce7  mov     [rbx+188h], rdx
0x140038cee  mov     [rbx+190h], rdx
0x140038cf5  mov     [rbx+198h], dl
0x140038cfb  mov     [rbx+168h], rcx
0x140038d02  mov     rcx, rbx; this
0x140038d05  mov     [rbx+1A0h], dx
0x140038d0c  mov     [rbx+1A8h], rdx
0x140038d13  mov     dl, 1; unsigned __int8
0x140038d15  call    ?Clear@TPMW8_NV_Read@tpm12class@@MEAAJE@Z; tpm12class::TPMW8_NV_Read::Clear(uchar)
0x140038d1a  mov     rax, rbx
0x140038d1d  add     rsp, 20h
0x140038d21  pop     rbx
0x140038d22  retn
```
