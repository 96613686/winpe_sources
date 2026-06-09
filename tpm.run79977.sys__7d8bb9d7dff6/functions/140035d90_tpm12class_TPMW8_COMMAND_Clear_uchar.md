# tpm12class::TPMW8_COMMAND::Clear(uchar)

- ea: `0x140035d90`
- end: `0x140035e6b`
- name: `?Clear@TPMW8_COMMAND@tpm12class@@MEAAJE@Z`
- size: `219`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, unsigned __int8)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140034f08`
- `0x140037f00`
- `0x1400381c0`
- `0x1400384c0`
- `0x140038800`
- `0x140038b10`
- `0x140038de0`

## callees

- `0x14000d090`
- `0x140035d90`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Clear(tpm12class::TPMW8_COMMAND *this, char a2)
{
  int v3; // edi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx

  if ( a2 )
  {
    v3 = 0;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = 0;
    *((_QWORD *)this + 23) = 0;
  }
  else
  {
    v3 = tpm12class::TpmDataObject::Clear(this, 0);
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 21);
  *((_DWORD *)this + 14) = -2147450879;
  *(_QWORD *)((char *)this + 60) = 0;
  *((_QWORD *)this + 20) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
  *(_QWORD *)((char *)this + 76) = 0;
  *((_DWORD *)this + 21) = 0;
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 21) = 0;
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
  if ( v5 )
  {
    (**v5)(v5, 1);
    *((_QWORD *)this + 22) = 0;
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 23);
  if ( v6 )
  {
    (**v6)(v6, 1);
    *((_QWORD *)this + 23) = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140035d90  mov     [rsp+arg_0], rbx
0x140035d95  mov     [rsp+arg_8], rsi
0x140035d9a  push    rdi
0x140035d9b  sub     rsp, 20h
0x140035d9f  xor     esi, esi
0x140035da1  mov     rbx, rcx
0x140035da4  test    dl, dl
0x140035da6  jz      short loc_140035DC1
0x140035da8  mov     edi, esi
0x140035daa  mov     [rcx+0A8h], rsi
0x140035db1  mov     [rcx+0B0h], rsi
0x140035db8  mov     [rcx+0B8h], rsi
0x140035dbf  jmp     short loc_140035DD2
0x140035dc1  xor     edx, edx; unsigned __int8
0x140035dc3  call    ?Clear@TpmDataObject@tpm12class@@MEAAJE@Z; tpm12class::TpmDataObject::Clear(uchar)
0x140035dc8  mov     edi, eax
0x140035dca  test    eax, eax
0x140035dcc  js      loc_140035E58
0x140035dd2  mov     rcx, [rbx+0A8h]
0x140035dd9  mov     dword ptr [rbx+38h], 80008001h
0x140035de0  mov     [rbx+3Ch], rsi
0x140035de4  mov     [rbx+0A0h], rsi
0x140035deb  mov     [rbx+44h], rsi
0x140035def  mov     [rbx+4Ch], rsi
0x140035df3  mov     [rbx+54h], esi
0x140035df6  test    rcx, rcx
0x140035df9  jz      short loc_140035E12
0x140035dfb  mov     rax, [rcx]
0x140035dfe  mov     edx, 1
0x140035e03  mov     rax, [rax]
0x140035e06  call    _guard_dispatch_icall
0x140035e0b  mov     [rbx+0A8h], rsi
0x140035e12  mov     rcx, [rbx+0B0h]
0x140035e19  test    rcx, rcx
0x140035e1c  jz      short loc_140035E35
0x140035e1e  mov     rax, [rcx]
0x140035e21  mov     edx, 1
0x140035e26  mov     rax, [rax]
0x140035e29  call    _guard_dispatch_icall
0x140035e2e  mov     [rbx+0B0h], rsi
0x140035e35  mov     rcx, [rbx+0B8h]
0x140035e3c  test    rcx, rcx
0x140035e3f  jz      short loc_140035E58
0x140035e41  mov     rax, [rcx]
0x140035e44  mov     edx, 1
0x140035e49  mov     rax, [rax]
0x140035e4c  call    _guard_dispatch_icall
0x140035e51  mov     [rbx+0B8h], rsi
0x140035e58  mov     rbx, [rsp+28h+arg_0]
0x140035e5d  mov     eax, edi
0x140035e5f  mov     rsi, [rsp+28h+arg_8]
0x140035e64  add     rsp, 20h
0x140035e68  pop     rdi
0x140035e69  retn
```
