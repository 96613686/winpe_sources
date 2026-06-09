# tpm12class::TPMW8_NV_Read::Serialize(void)

- ea: `0x140038ee0`
- end: `0x140038f59`
- name: `?Serialize@TPMW8_NV_Read@tpm12class@@MEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_NV_Read *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140031cd8`
- `0x140035488`
- `0x14003572c`
- `0x140037430`
- `0x140038ee0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_NV_Read::Serialize(tpm12class::TPMW8_NV_Read *this)
{
  __int64 result; // rax

  result = tpm12class::TPMW8_COMMAND::Serialize(this);
  if ( (int)result >= 0 )
  {
    result = tpm12class::TPMW8_COMMAND::AddHandle(this, *((_DWORD *)this + 48), (unsigned __int8 **)this + 25);
    if ( (int)result >= 0 )
    {
      result = tpm12class::TPMW8_COMMAND::AddHandle(this, *((_DWORD *)this + 68), (unsigned __int8 **)this + 35);
      if ( (int)result >= 0 )
      {
        result = tpm12class::TPMW8_COMMAND::AddSessions(this);
        if ( (int)result >= 0 )
        {
          result = tpm12class::TpmDataObject::AddData(this, *((_WORD *)this + 176));
          if ( (int)result >= 0 )
            return tpm12class::TpmDataObject::AddData(this, *((_WORD *)this + 177));
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140038ee0  push    rbx
0x140038ee2  sub     rsp, 20h
0x140038ee6  mov     rbx, rcx
0x140038ee9  call    ?Serialize@TPMW8_COMMAND@tpm12class@@MEAAJXZ; tpm12class::TPMW8_COMMAND::Serialize(void)
0x140038eee  test    eax, eax
0x140038ef0  js      short loc_140038F52
0x140038ef2  mov     edx, [rbx+0C0h]; unsigned int
0x140038ef8  lea     r8, [rbx+0C8h]; struct tpm12class::TPMW82B_BUFFER *
0x140038eff  mov     rcx, rbx; this
0x140038f02  call    ?AddHandle@TPMW8_COMMAND@tpm12class@@QEAAJIPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::AddHandle(uint,tpm12class::TPMW82B_BUFFER *)
0x140038f07  test    eax, eax
0x140038f09  js      short loc_140038F52
0x140038f0b  mov     edx, [rbx+110h]; unsigned int
0x140038f11  lea     r8, [rbx+118h]; struct tpm12class::TPMW82B_BUFFER *
0x140038f18  mov     rcx, rbx; this
0x140038f1b  call    ?AddHandle@TPMW8_COMMAND@tpm12class@@QEAAJIPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::AddHandle(uint,tpm12class::TPMW82B_BUFFER *)
0x140038f20  test    eax, eax
0x140038f22  js      short loc_140038F52
0x140038f24  mov     rcx, rbx; this
0x140038f27  call    ?AddSessions@TPMW8_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPMW8_COMMAND::AddSessions(void)
0x140038f2c  test    eax, eax
0x140038f2e  js      short loc_140038F52
0x140038f30  movzx   edx, word ptr [rbx+160h]; unsigned __int16
0x140038f37  mov     rcx, rbx; this
0x140038f3a  call    ?AddData@TpmDataObject@tpm12class@@QEAAJG@Z; tpm12class::TpmDataObject::AddData(ushort)
0x140038f3f  test    eax, eax
0x140038f41  js      short loc_140038F52
0x140038f43  movzx   edx, word ptr [rbx+162h]; unsigned __int16
0x140038f4a  mov     rcx, rbx; this
0x140038f4d  call    ?AddData@TpmDataObject@tpm12class@@QEAAJG@Z; tpm12class::TpmDataObject::AddData(ushort)
0x140038f52  add     rsp, 20h
0x140038f56  pop     rbx
0x140038f57  retn
```
