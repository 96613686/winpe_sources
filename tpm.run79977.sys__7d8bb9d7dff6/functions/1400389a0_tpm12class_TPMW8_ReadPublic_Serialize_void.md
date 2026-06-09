# tpm12class::TPMW8_ReadPublic::Serialize(void)

- ea: `0x1400389a0`
- end: `0x1400389fe`
- name: `?Serialize@TPMW8_ReadPublic@tpm12class@@MEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_ReadPublic *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140031d2c`
- `0x140035488`
- `0x14003572c`
- `0x140037430`
- `0x1400389a0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_ReadPublic::Serialize(unsigned __int8 **this)
{
  __int64 result; // rax
  unsigned int v3; // edx

  result = tpm12class::TPMW8_COMMAND::Serialize((tpm12class::TPMW8_COMMAND *)this);
  if ( (int)result >= 0 )
  {
    v3 = *((_DWORD *)this + 49);
    if ( *((_WORD *)this + 132) )
      result = tpm12class::TPMW8_COMMAND::AddHandle((tpm12class::TPMW8_COMMAND *)this, v3, this + 26);
    else
      result = tpm12class::TpmDataObject::AddData((tpm12class::TpmDataObject *)this, v3);
    if ( (int)result >= 0 && *((_WORD *)this + 28) != 0x8001 )
      return tpm12class::TPMW8_COMMAND::AddSessions((tpm12class::TPMW8_COMMAND *)this);
  }
  return result;
}

```

## disassembly

```asm
0x1400389a0  mov     [rsp+arg_0], rbx
0x1400389a5  push    rdi
0x1400389a6  sub     rsp, 20h
0x1400389aa  mov     rbx, rcx
0x1400389ad  call    ?Serialize@TPMW8_COMMAND@tpm12class@@MEAAJXZ; tpm12class::TPMW8_COMMAND::Serialize(void)
0x1400389b2  xor     edi, edi
0x1400389b4  test    eax, eax
0x1400389b6  js      short loc_1400389F2
0x1400389b8  mov     edx, [rbx+0C4h]; unsigned int
0x1400389be  lea     r8, [rbx+0D0h]; struct tpm12class::TPMW82B_BUFFER *
0x1400389c5  mov     rcx, rbx; this
0x1400389c8  cmp     [r8+38h], di
0x1400389cd  jnz     short loc_1400389D6
0x1400389cf  call    ?AddData@TpmDataObject@tpm12class@@QEAAJI@Z; tpm12class::TpmDataObject::AddData(uint)
0x1400389d4  jmp     short loc_1400389DB
0x1400389d6  call    ?AddHandle@TPMW8_COMMAND@tpm12class@@QEAAJIPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::AddHandle(uint,tpm12class::TPMW82B_BUFFER *)
0x1400389db  test    eax, eax
0x1400389dd  js      short loc_1400389F2
0x1400389df  mov     ecx, 8001h
0x1400389e4  cmp     [rbx+38h], cx
0x1400389e8  jz      short loc_1400389F2
0x1400389ea  mov     rcx, rbx; this
0x1400389ed  call    ?AddSessions@TPMW8_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPMW8_COMMAND::AddSessions(void)
0x1400389f2  mov     rbx, [rsp+28h+arg_0]
0x1400389f7  add     rsp, 20h
0x1400389fb  pop     rdi
0x1400389fc  retn
```
