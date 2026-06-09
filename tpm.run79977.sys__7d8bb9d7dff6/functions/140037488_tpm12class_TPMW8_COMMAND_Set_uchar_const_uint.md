# tpm12class::TPMW8_COMMAND::Set(uchar const *,uint)

- ea: `0x140037488`
- end: `0x1400374ef`
- name: `?Set@TPMW8_COMMAND@tpm12class@@QEAAJPEBEI@Z`
- size: `103`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400367d8`
- `0x140038b54`

## callees

- `0x140032254`
- `0x140037488`
- `0x140039780`

## pseudocode

```c
int __fastcall tpm12class::TPMW8_COMMAND::Set(
        tpm12class::TPMW8_COMMAND *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  int result; // eax

  if ( !a3 )
    return 0;
  if ( !a2 )
    return -2147024809;
  result = tpm12class::TpmDataObject::SetDataBuffer(this, a2, a3);
  if ( result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(tpm12class::TPMW8_COMMAND *))(*(_QWORD *)this + 8LL))(this);
    if ( result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(tpm12class::TPMW8_COMMAND *, _QWORD))(*(_QWORD *)this + 40LL))(this, 0);
      if ( result >= 0 )
        return (*(__int64 (__fastcall **)(tpm12class::TPMW8_COMMAND *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037488  push    rbx
0x14003748a  sub     rsp, 20h
0x14003748e  mov     rbx, rcx
0x140037491  test    r8d, r8d
0x140037494  jnz     short loc_14003749A
0x140037496  xor     eax, eax
0x140037498  jmp     short loc_1400374E8
0x14003749a  test    rdx, rdx
0x14003749d  jnz     short loc_1400374A6
0x14003749f  mov     eax, 80070057h
0x1400374a4  jmp     short loc_1400374E8
0x1400374a6  call    ?SetDataBuffer@TpmDataObject@tpm12class@@QEAAJPEBEI@Z; tpm12class::TpmDataObject::SetDataBuffer(uchar const *,uint)
0x1400374ab  test    eax, eax
0x1400374ad  js      short loc_1400374E8
0x1400374af  mov     rax, [rbx]
0x1400374b2  mov     rcx, rbx
0x1400374b5  mov     rax, [rax+8]
0x1400374b9  call    _guard_dispatch_icall
0x1400374be  test    eax, eax
0x1400374c0  js      short loc_1400374E8
0x1400374c2  mov     rax, [rbx]
0x1400374c5  xor     edx, edx
0x1400374c7  mov     rcx, rbx
0x1400374ca  mov     rax, [rax+28h]
0x1400374ce  call    _guard_dispatch_icall
0x1400374d3  test    eax, eax
0x1400374d5  js      short loc_1400374E8
0x1400374d7  mov     rax, [rbx]
0x1400374da  xor     edx, edx
0x1400374dc  mov     rcx, rbx
0x1400374df  mov     rax, [rax+10h]
0x1400374e3  call    _guard_dispatch_icall
0x1400374e8  add     rsp, 20h
0x1400374ec  pop     rbx
0x1400374ed  retn
```
