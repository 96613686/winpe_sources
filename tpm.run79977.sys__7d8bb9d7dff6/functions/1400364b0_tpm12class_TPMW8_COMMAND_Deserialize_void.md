# tpm12class::TPMW8_COMMAND::Deserialize(void)

- ea: `0x1400364b0`
- end: `0x14003652d`
- name: `?Deserialize@TPMW8_COMMAND@tpm12class@@MEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140037f80`
- `0x140038200`
- `0x140038520`
- `0x140038880`
- `0x140038ea0`

## callees

- `0x14000c93c`
- `0x14000cc3c`
- `0x14000cd28`
- `0x1400364b0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Deserialize(tpm12class::TPMW8_COMMAND *this)
{
  __int64 result; // rax
  _DWORD *v3; // rdi

  *((_BYTE *)this + 48) = 1;
  result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 29);
  if ( (int)result >= 0 )
  {
    result = tpm12class::TpmDataObject::GetData(this, (unsigned int *)this + 16);
    if ( (int)result >= 0 )
    {
      v3 = (_DWORD *)((char *)this + 164);
      *((_BYTE *)this + 48) = 0;
      result = tpm12class::TpmDataObject::GetData(this, (unsigned int *)this + 41);
      if ( (int)result >= 0 )
      {
        result = anonymous_namespace_::AddDataToBuffer_unsigned_int_(
                   *((unsigned int *)this + 40),
                   (char *)this + 32,
                   (char *)this + 40,
                   (char *)this + 44);
        if ( (int)result >= 0 )
        {
          if ( *v3 )
            return (unsigned int)(unsigned __int16)*v3 - 2144862208;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400364b0  mov     [rsp+arg_0], rbx
0x1400364b5  push    rdi
0x1400364b6  sub     rsp, 20h
0x1400364ba  lea     rdx, [rcx+3Ah]; unsigned __int16 *
0x1400364be  mov     byte ptr [rcx+30h], 1
0x1400364c2  mov     rbx, rcx
0x1400364c5  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x1400364ca  test    eax, eax
0x1400364cc  js      short loc_140036521
0x1400364ce  lea     rdx, [rbx+40h]; unsigned int *
0x1400364d2  mov     rcx, rbx; this
0x1400364d5  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAI@Z; tpm12class::TpmDataObject::GetData(uint *)
0x1400364da  test    eax, eax
0x1400364dc  js      short loc_140036521
0x1400364de  lea     rdi, [rbx+0A4h]
0x1400364e5  mov     byte ptr [rbx+30h], 0
0x1400364e9  mov     rdx, rdi; unsigned int *
0x1400364ec  mov     rcx, rbx; this
0x1400364ef  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAI@Z; tpm12class::TpmDataObject::GetData(uint *)
0x1400364f4  test    eax, eax
0x1400364f6  js      short loc_140036521
0x1400364f8  mov     ecx, [rbx+0A0h]
0x1400364fe  lea     r9, [rbx+2Ch]
0x140036502  lea     r8, [rbx+28h]
0x140036506  lea     rdx, [rbx+20h]
0x14003650a  call    _anonymous_namespace___AddDataToBuffer_unsigned_int_
0x14003650f  test    eax, eax
0x140036511  js      short loc_140036521
0x140036513  mov     ecx, [rdi]
0x140036515  test    ecx, ecx
0x140036517  jz      short loc_140036521
0x140036519  movzx   eax, cx
0x14003651c  sub     eax, 7FD80000h
0x140036521  mov     rbx, [rsp+28h+arg_0]
0x140036526  add     rsp, 20h
0x14003652a  pop     rdi
0x14003652b  retn
```
