# tpm12class::TPMW8_COMMAND::Get(uchar *,uint,uint *)

- ea: `0x140036c34`
- end: `0x140036cab`
- name: `?Get@TPMW8_COMMAND@tpm12class@@QEAAJPEAEIPEAI@Z`
- size: `119`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400367d8`

## callees

- `0x14000d090`
- `0x140031f7c`
- `0x140036c34`
- `0x140039780`

## pseudocode

```c
int __fastcall tpm12class::TPMW8_COMMAND::Get(
        tpm12class::TPMW8_COMMAND *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  int result; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx

  result = tpm12class::TpmDataObject::Clear(this, 0);
  if ( result >= 0 )
  {
    LOBYTE(v9) = 1;
    result = (*(__int64 (__fastcall **)(tpm12class::TPMW8_COMMAND *, __int64))(*(_QWORD *)this + 16LL))(this, v9);
    if ( result >= 0 )
    {
      result = (**(__int64 (__fastcall ***)(tpm12class::TPMW8_COMMAND *))this)(this);
      if ( result >= 0 )
      {
        LOBYTE(v10) = 1;
        result = (*(__int64 (__fastcall **)(tpm12class::TPMW8_COMMAND *, __int64))(*(_QWORD *)this + 40LL))(this, v10);
        if ( result >= 0 )
          return tpm12class::TpmDataObject::GetDataBuffer(this, a2, a3, a4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140036c34  push    rbx
0x140036c36  push    rbp
0x140036c37  push    rsi
0x140036c38  push    rdi
0x140036c39  sub     rsp, 28h
0x140036c3d  mov     rbp, rdx
0x140036c40  mov     rdi, r9
0x140036c43  xor     edx, edx; unsigned __int8
0x140036c45  mov     esi, r8d
0x140036c48  mov     rbx, rcx
0x140036c4b  call    ?Clear@TpmDataObject@tpm12class@@MEAAJE@Z; tpm12class::TpmDataObject::Clear(uchar)
0x140036c50  test    eax, eax
0x140036c52  js      short loc_140036CA1
0x140036c54  mov     rax, [rbx]
0x140036c57  mov     dl, 1
0x140036c59  mov     rcx, rbx
0x140036c5c  mov     rax, [rax+10h]
0x140036c60  call    _guard_dispatch_icall
0x140036c65  test    eax, eax
0x140036c67  js      short loc_140036CA1
0x140036c69  mov     rax, [rbx]
0x140036c6c  mov     rcx, rbx
0x140036c6f  mov     rax, [rax]
0x140036c72  call    _guard_dispatch_icall
0x140036c77  test    eax, eax
0x140036c79  js      short loc_140036CA1
0x140036c7b  mov     rax, [rbx]
0x140036c7e  mov     dl, 1
0x140036c80  mov     rcx, rbx
0x140036c83  mov     rax, [rax+28h]
0x140036c87  call    _guard_dispatch_icall
0x140036c8c  test    eax, eax
0x140036c8e  js      short loc_140036CA1
0x140036c90  mov     r9, rdi; unsigned int *
0x140036c93  mov     r8d, esi; unsigned int
0x140036c96  mov     rdx, rbp; unsigned __int8 *
0x140036c99  mov     rcx, rbx; this
0x140036c9c  call    ?GetDataBuffer@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::GetDataBuffer(uchar *,uint,uint *)
0x140036ca1  add     rsp, 28h
0x140036ca5  pop     rdi
0x140036ca6  pop     rsi
0x140036ca7  pop     rbp
0x140036ca8  pop     rbx
0x140036ca9  retn
```
