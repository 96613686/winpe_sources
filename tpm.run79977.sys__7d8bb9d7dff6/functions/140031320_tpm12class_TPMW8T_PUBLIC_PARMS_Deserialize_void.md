# tpm12class::TPMW8T_PUBLIC_PARMS::Deserialize(void)

- ea: `0x140031320`
- end: `0x140031410`
- name: `?Deserialize@TPMW8T_PUBLIC_PARMS@tpm12class@@MEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(tpm12class::TPMW8T_PUBLIC_PARMS *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14000c93c`
- `0x14000cc3c`
- `0x14000cf48`
- `0x140031320`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8T_PUBLIC_PARMS::Deserialize(tpm12class::TPMW8T_PUBLIC_PARMS *this)
{
  __int64 result; // rax
  tpm12class::TpmDataObject *v3; // rcx

  result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 28);
  if ( (int)result >= 0 )
  {
    switch ( *((_WORD *)this + 28) )
    {
      case 1:
        result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 64), this);
        if ( (int)result >= 0 )
        {
          result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 136), this);
          if ( (int)result >= 0 )
          {
            result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 100);
            if ( (int)result >= 0 )
              return tpm12class::TpmDataObject::GetData(this, (unsigned int *)this + 51);
          }
        }
        break;
      case 8:
        v3 = (tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 416);
        return tpm12class::TpmDataObject::Set(v3, this);
      case 0x23:
        result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 208), this);
        if ( (int)result >= 0 )
        {
          result = tpm12class::TpmDataObject::Set((tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 280), this);
          if ( (int)result >= 0 )
          {
            result = tpm12class::TpmDataObject::GetData(this, (unsigned __int16 *)this + 172);
            if ( (int)result >= 0 )
            {
              v3 = (tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 352);
              return tpm12class::TpmDataObject::Set(v3, this);
            }
          }
        }
        break;
      case 0x25:
        v3 = (tpm12class::TPMW8T_PUBLIC_PARMS *)((char *)this + 480);
        return tpm12class::TpmDataObject::Set(v3, this);
      default:
        return 2147942413LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140031320  mov     [rsp+arg_0], rbx
0x140031325  push    rdi
0x140031326  sub     rsp, 20h
0x14003132a  lea     rdx, [rcx+38h]; unsigned __int16 *
0x14003132e  mov     rbx, rcx
0x140031331  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x140031336  test    eax, eax
0x140031338  js      loc_140031404
0x14003133e  movzx   ecx, word ptr [rbx+38h]
0x140031342  sub     ecx, 1
0x140031345  jz      short loc_1400313BF
0x140031347  sub     ecx, 7
0x14003134a  jz      short loc_1400313B6
0x14003134c  sub     ecx, 1Bh
0x14003134f  jz      short loc_140031374
0x140031351  cmp     ecx, 2
0x140031354  jz      short loc_140031360
0x140031356  mov     eax, 8007000Dh
0x14003135b  jmp     loc_140031404
0x140031360  lea     rcx, [rbx+1E0h]; this
0x140031367  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003136a  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x14003136f  jmp     loc_140031404
0x140031374  lea     rcx, [rbx+0D0h]; this
0x14003137b  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003137e  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x140031383  test    eax, eax
0x140031385  js      short loc_140031404
0x140031387  lea     rcx, [rbx+118h]; this
0x14003138e  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140031391  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x140031396  test    eax, eax
0x140031398  js      short loc_140031404
0x14003139a  lea     rdx, [rbx+158h]; unsigned __int16 *
0x1400313a1  mov     rcx, rbx; this
0x1400313a4  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x1400313a9  test    eax, eax
0x1400313ab  js      short loc_140031404
0x1400313ad  lea     rcx, [rbx+160h]
0x1400313b4  jmp     short loc_140031367
0x1400313b6  lea     rcx, [rbx+1A0h]
0x1400313bd  jmp     short loc_140031367
0x1400313bf  lea     rcx, [rbx+40h]; this
0x1400313c3  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x1400313c6  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x1400313cb  test    eax, eax
0x1400313cd  js      short loc_140031404
0x1400313cf  lea     rcx, [rbx+88h]; this
0x1400313d6  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x1400313d9  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEAV12@@Z; tpm12class::TpmDataObject::Set(tpm12class::TpmDataObject *)
0x1400313de  test    eax, eax
0x1400313e0  js      short loc_140031404
0x1400313e2  lea     rdx, [rbx+0C8h]; unsigned __int16 *
0x1400313e9  mov     rcx, rbx; this
0x1400313ec  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x1400313f1  test    eax, eax
0x1400313f3  js      short loc_140031404
0x1400313f5  lea     rdx, [rbx+0CCh]; unsigned int *
0x1400313fc  mov     rcx, rbx; this
0x1400313ff  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAI@Z; tpm12class::TpmDataObject::GetData(uint *)
0x140031404  mov     rbx, [rsp+28h+arg_0]
0x140031409  add     rsp, 20h
0x14003140d  pop     rdi
0x14003140e  retn
```
