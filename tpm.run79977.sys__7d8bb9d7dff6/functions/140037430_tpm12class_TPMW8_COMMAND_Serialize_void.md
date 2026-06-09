# tpm12class::TPMW8_COMMAND::Serialize(void)

- ea: `0x140037430`
- end: `0x140037480`
- name: `?Serialize@TPMW8_COMMAND@tpm12class@@MEAAJXZ`
- size: `80`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140038070`
- `0x140038220`
- `0x140038570`
- `0x1400389a0`
- `0x140038b90`
- `0x140038ee0`

## callees

- `0x14000d090`
- `0x140031cd8`
- `0x140031d2c`
- `0x140037430`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Serialize(tpm12class::TPMW8_COMMAND *this)
{
  __int64 result; // rax
  unsigned __int16 v3; // dx
  unsigned int v4; // edx

  result = tpm12class::TpmDataObject::Clear(this, 0);
  if ( (int)result >= 0 )
  {
    v3 = *((_WORD *)this + 28);
    *((_BYTE *)this + 48) = 1;
    result = tpm12class::TpmDataObject::AddData(this, v3);
    if ( (int)result >= 0 )
    {
      result = tpm12class::TpmDataObject::AddData(this, *((_DWORD *)this + 15));
      if ( (int)result >= 0 )
      {
        v4 = *((_DWORD *)this + 40);
        *((_BYTE *)this + 48) = 0;
        return tpm12class::TpmDataObject::AddData(this, v4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037430  push    rbx
0x140037432  sub     rsp, 20h
0x140037436  xor     edx, edx; unsigned __int8
0x140037438  mov     rbx, rcx
0x14003743b  call    ?Clear@TpmDataObject@tpm12class@@MEAAJE@Z; tpm12class::TpmDataObject::Clear(uchar)
0x140037440  test    eax, eax
0x140037442  js      short loc_140037479
0x140037444  movzx   edx, word ptr [rbx+38h]; unsigned __int16
0x140037448  mov     rcx, rbx; this
0x14003744b  mov     byte ptr [rbx+30h], 1
0x14003744f  call    ?AddData@TpmDataObject@tpm12class@@QEAAJG@Z; tpm12class::TpmDataObject::AddData(ushort)
0x140037454  test    eax, eax
0x140037456  js      short loc_140037479
0x140037458  mov     edx, [rbx+3Ch]; unsigned int
0x14003745b  mov     rcx, rbx; this
0x14003745e  call    ?AddData@TpmDataObject@tpm12class@@QEAAJI@Z; tpm12class::TpmDataObject::AddData(uint)
0x140037463  test    eax, eax
0x140037465  js      short loc_140037479
0x140037467  mov     edx, [rbx+0A0h]; unsigned int
0x14003746d  mov     rcx, rbx; this
0x140037470  mov     byte ptr [rbx+30h], 0
0x140037474  call    ?AddData@TpmDataObject@tpm12class@@QEAAJI@Z; tpm12class::TpmDataObject::AddData(uint)
0x140037479  add     rsp, 20h
0x14003747d  pop     rbx
0x14003747e  retn
```
