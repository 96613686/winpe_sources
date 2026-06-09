# tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)

- ea: `0x140038688`
- end: `0x140038737`
- name: `??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ`
- size: `175`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_ReadPublic *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140032eb4`

## callees

- `0x140034f08`
- `0x140038800`

## pseudocode

```c
tpm12class::TPMW8_ReadPublic *__fastcall tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(
        tpm12class::TPMW8_ReadPublic *this)
{
  tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(this);
  *(_QWORD *)this = &tpm12class::TPMW8_ReadPublic::`vftable';
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_BYTE *)this + 256) = 0;
  *((_QWORD *)this + 26) = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)this + 132) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_BYTE *)this + 328) = 0;
  *((_QWORD *)this + 35) = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)this + 168) = 0;
  *((_QWORD *)this + 43) = 0;
  tpm12class::TPMW8_ReadPublic::Clear(this, 1u);
  return this;
}

```

## disassembly

```asm
0x140038688  push    rbx
0x14003868a  sub     rsp, 20h
0x14003868e  mov     rbx, rcx
0x140038691  call    ??0TPMW8_COMMAND@tpm12class@@QEAA@XZ; tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(void)
0x140038696  xor     edx, edx
0x140038698  lea     rcx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x14003869f  lea     rax, ??_7TPMW8_ReadPublic@tpm12class@@6B@; const tpm12class::TPMW8_ReadPublic::`vftable'
0x1400386a6  mov     [rbx], rax
0x1400386a9  mov     [rbx+0D8h], rdx
0x1400386b0  mov     [rbx+0E0h], rdx
0x1400386b7  mov     [rbx+0E8h], edx
0x1400386bd  mov     [rbx+0F0h], rdx
0x1400386c4  mov     [rbx+0F8h], rdx
0x1400386cb  mov     [rbx+100h], dl
0x1400386d1  mov     [rbx+0D0h], rcx
0x1400386d8  mov     [rbx+108h], dx
0x1400386df  mov     [rbx+110h], rdx
0x1400386e6  mov     [rbx+120h], rdx
0x1400386ed  mov     [rbx+128h], rdx
0x1400386f4  mov     [rbx+130h], edx
0x1400386fa  mov     [rbx+138h], rdx
0x140038701  mov     [rbx+140h], rdx
0x140038708  mov     [rbx+148h], dl
0x14003870e  mov     [rbx+118h], rcx
0x140038715  mov     rcx, rbx; this
0x140038718  mov     [rbx+150h], dx
0x14003871f  mov     [rbx+158h], rdx
0x140038726  mov     dl, 1; unsigned __int8
0x140038728  call    ?Clear@TPMW8_ReadPublic@tpm12class@@MEAAJE@Z; tpm12class::TPMW8_ReadPublic::Clear(uchar)
0x14003872d  mov     rax, rbx
0x140038730  add     rsp, 20h
0x140038734  pop     rbx
0x140038735  retn
```
