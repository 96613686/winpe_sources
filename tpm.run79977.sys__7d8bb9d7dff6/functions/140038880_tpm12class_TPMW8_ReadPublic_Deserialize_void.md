# tpm12class::TPMW8_ReadPublic::Deserialize(void)

- ea: `0x140038880`
- end: `0x140038995`
- name: `?Deserialize@TPMW8_ReadPublic@tpm12class@@MEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_ReadPublic *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000c93c`
- `0x14000cb50`
- `0x14000cf48`
- `0x14000dbf4`
- `0x140032164`
- `0x1400364b0`
- `0x140036cb4`
- `0x140038880`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_ReadPublic::Deserialize(tpm12class::TPMW8_ReadPublic *this)
{
  __int64 result; // rax
  unsigned __int16 *v3; // rdi
  __int64 v4; // rcx
  tpm12class::TPMW8T_PUBLIC *v5; // rax
  tpm12class::TpmDataObject *v6; // rax

  result = tpm12class::TPMW8_COMMAND::Deserialize(this);
  if ( (int)result >= 0 )
  {
    if ( *((_WORD *)this + 29) == 0x8001
      || (result = tpm12class::TPMW8_COMMAND::GetParameterSize(this), (int)result >= 0) )
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
          v5 = (tpm12class::TPMW8T_PUBLIC *)operator new(0x340u);
          if ( v5 )
          {
            v6 = (tpm12class::TpmDataObject *)tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(v5);
            *((_QWORD *)this + 25) = v6;
            if ( v6 )
            {
              result = tpm12class::TpmDataObject::Set(v6, this, *v3);
              if ( (int)result < 0 )
                return result;
              goto LABEL_16;
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
LABEL_16:
        result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8_ReadPublic *)((char *)this + 208), this);
        if ( (int)result >= 0 )
          return tpm12class::TpmDataObject::Set((tpm12class::TPMW8_ReadPublic *)((char *)this + 280), this);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140038880  mov     [rsp+arg_0], rbx
0x140038885  mov     [rsp+arg_8], rsi
0x14003888a  push    rdi
0x14003888b  sub     rsp, 20h
0x14003888f  mov     rbx, rcx
0x140038892  call    ?Deserialize@TPMW8_COMMAND@tpm12class@@MEAAJXZ; tpm12class::TPMW8_COMMAND::Deserialize(void)
0x140038897  xor     esi, esi
0x140038899  test    eax, eax
0x14003889b  js      loc_140038984
0x1400388a1  mov     eax, 8001h
0x1400388a6  cmp     [rbx+3Ah], ax
0x1400388aa  jz      short loc_1400388BC
0x1400388ac  mov     rcx, rbx; this
0x1400388af  call    ?GetParameterSize@TPMW8_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPMW8_COMMAND::GetParameterSize(void)
0x1400388b4  test    eax, eax
0x1400388b6  js      loc_140038984
0x1400388bc  lea     rdi, [rbx+0C0h]
0x1400388c3  mov     rcx, rbx; this
0x1400388c6  mov     rdx, rdi; unsigned __int16 *
0x1400388c9  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x1400388ce  test    eax, eax
0x1400388d0  js      loc_140038984
0x1400388d6  mov     rcx, [rbx+0C8h]
0x1400388dd  cmp     [rdi], si
0x1400388e0  jz      short loc_140038945
0x1400388e2  test    rcx, rcx
0x1400388e5  jz      short loc_1400388FF
0x1400388e7  mov     rax, [rcx]
0x1400388ea  mov     edx, 1
0x1400388ef  mov     rax, [rax+20h]
0x1400388f3  call    _guard_dispatch_icall
0x1400388f8  mov     [rbx+0C8h], rsi
0x1400388ff  mov     ecx, 340h; unsigned __int64
0x140038904  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140038909  test    rax, rax
0x14003890c  jz      short loc_140038937
0x14003890e  mov     rcx, rax; this
0x140038911  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x140038916  mov     [rbx+0C8h], rax
0x14003891d  test    rax, rax
0x140038920  jz      short loc_14003893E
0x140038922  movzx   r8d, word ptr [rdi]; unsigned __int16
0x140038926  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140038929  mov     rcx, rax; this
0x14003892c  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@G@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *,ushort)
0x140038931  test    eax, eax
0x140038933  js      short loc_140038984
0x140038935  jmp     short loc_140038962
0x140038937  mov     [rbx+0C8h], rsi
0x14003893e  mov     eax, 80070008h
0x140038943  jmp     short loc_140038984
0x140038945  test    rcx, rcx
0x140038948  jz      short loc_140038962
0x14003894a  mov     rax, [rcx]
0x14003894d  mov     edx, 1
0x140038952  mov     rax, [rax+20h]
0x140038956  call    _guard_dispatch_icall
0x14003895b  mov     [rbx+0C8h], rsi
0x140038962  lea     rcx, [rbx+0D0h]; this
0x140038969  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003896c  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x140038971  test    eax, eax
0x140038973  js      short loc_140038984
0x140038975  lea     rcx, [rbx+118h]; this
0x14003897c  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003897f  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x140038984  mov     rbx, [rsp+28h+arg_0]
0x140038989  mov     rsi, [rsp+28h+arg_8]
0x14003898e  add     rsp, 20h
0x140038992  pop     rdi
0x140038993  retn
```
