# tpm12class::TPMW8_NV_ReadPublic::Deserialize(void)

- ea: `0x140037f80`
- end: `0x140038065`
- name: `?Deserialize@TPMW8_NV_ReadPublic@tpm12class@@MEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_NV_ReadPublic *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000c93c`
- `0x14000cb50`
- `0x14000cf48`
- `0x140030a4c`
- `0x140032164`
- `0x1400364b0`
- `0x140037f80`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_NV_ReadPublic::Deserialize(tpm12class::TPMW8_NV_ReadPublic *this)
{
  __int64 result; // rax
  unsigned __int16 *v3; // rdi
  __int64 v4; // rcx
  tpm12class::TPMW8S_NV_PUBLIC *v5; // rax
  tpm12class::TpmDataObject *v6; // rax

  result = tpm12class::TPMW8_COMMAND::Deserialize(this);
  if ( (int)result >= 0 )
  {
    v3 = (unsigned __int16 *)((char *)this + 192);
    result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 96);
    if ( (int)result >= 0 )
    {
      v4 = *((_QWORD *)this + 25);
      if ( *v3 )
      {
        if ( v4 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, 1);
          *((_QWORD *)this + 25) = 0;
        }
        v5 = (tpm12class::TPMW8S_NV_PUBLIC *)operator new(0x98u);
        if ( v5 )
        {
          v6 = (tpm12class::TpmDataObject *)tpm12class::TPMW8S_NV_PUBLIC::TPMW8S_NV_PUBLIC(v5);
          *((_QWORD *)this + 25) = v6;
          if ( v6 )
          {
            result = tpm12class::TpmDataObject::Set(v6, this, *v3);
            if ( (int)result < 0 )
              return result;
            return tpm12class::TpmDataObject::Set((tpm12class::TPMW8_NV_ReadPublic *)((char *)this + 208), this);
          }
        }
        else
        {
          *((_QWORD *)this + 25) = 0;
        }
        return 2147942408LL;
      }
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, 1);
        *((_QWORD *)this + 25) = 0;
      }
      return tpm12class::TpmDataObject::Set((tpm12class::TPMW8_NV_ReadPublic *)((char *)this + 208), this);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037f80  mov     [rsp+arg_0], rbx
0x140037f85  mov     [rsp+arg_8], rsi
0x140037f8a  push    rdi
0x140037f8b  sub     rsp, 20h
0x140037f8f  mov     rbx, rcx
0x140037f92  call    ?Deserialize@TPMW8_COMMAND@tpm12class@@MEAAJXZ; tpm12class::TPMW8_COMMAND::Deserialize(void)
0x140037f97  xor     esi, esi
0x140037f99  test    eax, eax
0x140037f9b  js      loc_140038054
0x140037fa1  lea     rdi, [rbx+0C0h]
0x140037fa8  mov     rcx, rbx; this
0x140037fab  mov     rdx, rdi; unsigned __int16 *
0x140037fae  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x140037fb3  test    eax, eax
0x140037fb5  js      loc_140038054
0x140037fbb  mov     rcx, [rbx+0C8h]
0x140037fc2  cmp     [rdi], si
0x140037fc5  jz      short loc_140038028
0x140037fc7  test    rcx, rcx
0x140037fca  jz      short loc_140037FE2
0x140037fcc  mov     rax, [rcx]
0x140037fcf  lea     edx, [rsi+1]
0x140037fd2  mov     rax, [rax+20h]
0x140037fd6  call    _guard_dispatch_icall
0x140037fdb  mov     [rbx+0C8h], rsi
0x140037fe2  mov     ecx, 98h; unsigned __int64
0x140037fe7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140037fec  test    rax, rax
0x140037fef  jz      short loc_14003801A
0x140037ff1  mov     rcx, rax; this
0x140037ff4  call    ??0TPMW8S_NV_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8S_NV_PUBLIC::TPMW8S_NV_PUBLIC(void)
0x140037ff9  mov     [rbx+0C8h], rax
0x140038000  test    rax, rax
0x140038003  jz      short loc_140038021
0x140038005  movzx   r8d, word ptr [rdi]; unsigned __int16
0x140038009  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003800c  mov     rcx, rax; this
0x14003800f  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@G@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *,ushort)
0x140038014  test    eax, eax
0x140038016  js      short loc_140038054
0x140038018  jmp     short loc_140038045
0x14003801a  mov     [rbx+0C8h], rsi
0x140038021  mov     eax, 80070008h
0x140038026  jmp     short loc_140038054
0x140038028  test    rcx, rcx
0x14003802b  jz      short loc_140038045
0x14003802d  mov     rax, [rcx]
0x140038030  mov     edx, 1
0x140038035  mov     rax, [rax+20h]
0x140038039  call    _guard_dispatch_icall
0x14003803e  mov     [rbx+0C8h], rsi
0x140038045  lea     rcx, [rbx+0D0h]; this
0x14003804c  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003804f  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x140038054  mov     rbx, [rsp+28h+arg_0]
0x140038059  mov     rsi, [rsp+28h+arg_8]
0x14003805e  add     rsp, 20h
0x140038062  pop     rdi
0x140038063  retn
```
