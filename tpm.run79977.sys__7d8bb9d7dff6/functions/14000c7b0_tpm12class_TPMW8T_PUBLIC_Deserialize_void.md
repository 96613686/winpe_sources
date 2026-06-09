# tpm12class::TPMW8T_PUBLIC::Deserialize(void)

- ea: `0x14000c7b0`
- end: `0x14000c933`
- name: `?Deserialize@TPMW8T_PUBLIC@tpm12class@@MEAAJXZ`
- size: `387`
- prototype: `__int64 __fastcall(tpm12class::TPMW8T_PUBLIC *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14000c7b0`
- `0x14000c93c`
- `0x14000cc3c`
- `0x14000cf48`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8T_PUBLIC::Deserialize(tpm12class::TPMW8T_PUBLIC *this)
{
  __int64 result; // rax
  tpm12class::TpmDataObject *v3; // rcx
  tpm12class::TpmDataObject *v4; // rcx

  result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 28);
  if ( (int)result >= 0 )
  {
    result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 29);
    if ( (int)result >= 0 )
    {
      result = tpm12class::TpmDataObject::GetData(this, (unsigned int *)this + 15);
      if ( (int)result >= 0 )
      {
        result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 64), this);
        if ( (int)result >= 0 )
        {
          switch ( *((_WORD *)this + 28) )
          {
            case 1:
              result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 136), this);
              if ( (int)result >= 0 )
              {
                result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 208), this);
                if ( (int)result >= 0 )
                {
                  result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 136);
                  if ( (int)result >= 0 )
                  {
                    result = tpm12class::TpmDataObject::GetData(this, (unsigned int *)this + 69);
                    goto LABEL_23;
                  }
                }
              }
              break;
            case 8:
              v3 = (tpm12class::TPMW8T_PUBLIC *)((char *)this + 632);
LABEL_11:
              result = tpm12class::TpmDataObject::Set(v3, this);
LABEL_23:
              if ( (int)result < 0 )
                return result;
              v4 = (tpm12class::TPMW8T_PUBLIC *)((char *)this + 760);
              return tpm12class::TpmDataObject::Set(v4, this);
            case 0x23:
              result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 280), this);
              if ( (int)result >= 0 )
              {
                result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 352), this);
                if ( (int)result >= 0 )
                {
                  result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 208);
                  if ( (int)result >= 0 )
                  {
                    result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 424), this);
                    if ( (int)result >= 0 )
                    {
                      result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC *)((char *)this + 488), this);
                      if ( (int)result >= 0 )
                      {
                        v4 = (tpm12class::TPMW8T_PUBLIC *)((char *)this + 560);
                        return tpm12class::TpmDataObject::Set(v4, this);
                      }
                    }
                  }
                }
              }
              break;
            case 0x25:
              v3 = (tpm12class::TPMW8T_PUBLIC *)((char *)this + 696);
              goto LABEL_11;
            default:
              return 2147942413LL;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c7b0  mov     [rsp+arg_0], rbx
0x14000c7b5  push    rdi
0x14000c7b6  sub     rsp, 20h
0x14000c7ba  lea     rdx, [rcx+38h]; unsigned __int16 *
0x14000c7be  mov     rbx, rcx
0x14000c7c1  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x14000c7c6  test    eax, eax
0x14000c7c8  js      loc_14000C927
0x14000c7ce  lea     rdx, [rbx+3Ah]; unsigned __int16 *
0x14000c7d2  mov     rcx, rbx; this
0x14000c7d5  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x14000c7da  test    eax, eax
0x14000c7dc  js      loc_14000C927
0x14000c7e2  lea     rdx, [rbx+3Ch]; unsigned int *
0x14000c7e6  mov     rcx, rbx; this
0x14000c7e9  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAI@Z; tpm12class::TpmDataObject::GetData(uint *)
0x14000c7ee  test    eax, eax
0x14000c7f0  js      loc_14000C927
0x14000c7f6  lea     rcx, [rbx+40h]; this
0x14000c7fa  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c7fd  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c802  test    eax, eax
0x14000c804  js      loc_14000C927
0x14000c80a  movzx   ecx, word ptr [rbx+38h]
0x14000c80e  sub     ecx, 1
0x14000c811  jz      loc_14000C8CC
0x14000c817  sub     ecx, 7
0x14000c81a  jz      loc_14000C8C0
0x14000c820  sub     ecx, 1Bh
0x14000c823  jz      short loc_14000C848
0x14000c825  cmp     ecx, 2
0x14000c828  jz      short loc_14000C834
0x14000c82a  mov     eax, 8007000Dh
0x14000c82f  jmp     loc_14000C927
0x14000c834  lea     rcx, [rbx+2B8h]; this
0x14000c83b  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c83e  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c843  jmp     loc_14000C914
0x14000c848  lea     rcx, [rbx+118h]; this
0x14000c84f  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c852  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c857  test    eax, eax
0x14000c859  js      loc_14000C927
0x14000c85f  lea     rcx, [rbx+160h]; this
0x14000c866  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c869  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c86e  test    eax, eax
0x14000c870  js      loc_14000C927
0x14000c876  lea     rdx, [rbx+1A0h]; unsigned __int16 *
0x14000c87d  mov     rcx, rbx; this
0x14000c880  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x14000c885  test    eax, eax
0x14000c887  js      loc_14000C927
0x14000c88d  lea     rcx, [rbx+1A8h]; this
0x14000c894  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c897  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c89c  test    eax, eax
0x14000c89e  js      loc_14000C927
0x14000c8a4  lea     rdi, [rbx+1E8h]
0x14000c8ab  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c8ae  mov     rcx, rdi; this
0x14000c8b1  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c8b6  test    eax, eax
0x14000c8b8  js      short loc_14000C927
0x14000c8ba  lea     rcx, [rdi+48h]
0x14000c8be  jmp     short loc_14000C91F
0x14000c8c0  lea     rcx, [rbx+278h]
0x14000c8c7  jmp     loc_14000C83B
0x14000c8cc  lea     rcx, [rbx+88h]; this
0x14000c8d3  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c8d6  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c8db  test    eax, eax
0x14000c8dd  js      short loc_14000C927
0x14000c8df  lea     rcx, [rbx+0D0h]; this
0x14000c8e6  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c8e9  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c8ee  test    eax, eax
0x14000c8f0  js      short loc_14000C927
0x14000c8f2  lea     rdx, [rbx+110h]; unsigned __int16 *
0x14000c8f9  mov     rcx, rbx; this
0x14000c8fc  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x14000c901  test    eax, eax
0x14000c903  js      short loc_14000C927
0x14000c905  lea     rdx, [rbx+114h]; unsigned int *
0x14000c90c  mov     rcx, rbx; this
0x14000c90f  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAI@Z; tpm12class::TpmDataObject::GetData(uint *)
0x14000c914  test    eax, eax
0x14000c916  js      short loc_14000C927
0x14000c918  lea     rcx, [rbx+2F8h]; this
0x14000c91f  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14000c922  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14000c927  mov     rbx, [rsp+28h+arg_0]
0x14000c92c  add     rsp, 20h
0x14000c930  pop     rdi
0x14000c931  retn
```
