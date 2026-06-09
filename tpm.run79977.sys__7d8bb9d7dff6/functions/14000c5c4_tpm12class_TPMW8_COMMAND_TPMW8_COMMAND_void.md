# tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)

- ea: `0x14000c5c4`
- end: `0x14000c69f`
- name: `??1TPMW8_COMMAND@tpm12class@@UEAA@XZ`
- size: `219`
- prototype: `void __fastcall(tpm12class::TPMW8_COMMAND *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140035410`
- `0x140037344`
- `0x140037e54`
- `0x140038148`
- `0x1400383e8`
- `0x140038740`
- `0x140038ac0`
- `0x140038d2c`

## callees

- `0x14000c5c4`
- `0x14000d090`
- `0x14000da40`
- `0x140039780`

## pseudocode

```c
void __fastcall tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(tpm12class::TPMW8_COMMAND *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *((_DWORD *)this + 14) = -2147450879;
  *(_QWORD *)this = &tpm12class::TPMW8_COMMAND::`vftable';
  *(_QWORD *)((char *)this + 60) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 19) = 0;
  *((_DWORD *)this + 21) = 0;
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 21);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 21) = 0;
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
  if ( v3 )
  {
    (**v3)(v3, 1);
    *((_QWORD *)this + 22) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 23);
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 23) = 0;
  }
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_COMMAND *)((char *)this + 88));
  *(_QWORD *)this = &tpm12class::TpmDataObject::`vftable';
  tpm12class::TpmDataObject::Clear(this, 0);
}

```

## disassembly

```asm
0x14000c5c4  push    rbx
0x14000c5c6  sub     rsp, 20h
0x14000c5ca  lea     rax, ??_7TPMW8_COMMAND@tpm12class@@6B@; const tpm12class::TPMW8_COMMAND::`vftable'
0x14000c5d1  mov     dword ptr [rcx+38h], 80008001h
0x14000c5d8  mov     [rcx], rax
0x14000c5db  mov     rbx, rcx
0x14000c5de  mov     qword ptr [rcx+3Ch], 0
0x14000c5e6  mov     qword ptr [rcx+0A0h], 0
0x14000c5f1  mov     dword ptr [rcx+44h], 0
0x14000c5f8  mov     dword ptr [rcx+4Ch], 0
0x14000c5ff  mov     dword ptr [rcx+54h], 0
0x14000c606  mov     rcx, [rcx+0A8h]
0x14000c60d  test    rcx, rcx
0x14000c610  jz      short loc_14000C62D
0x14000c612  mov     rax, [rcx]
0x14000c615  mov     edx, 1
0x14000c61a  mov     rax, [rax]
0x14000c61d  call    _guard_dispatch_icall
0x14000c622  mov     qword ptr [rbx+0A8h], 0
0x14000c62d  mov     rcx, [rbx+0B0h]
0x14000c634  test    rcx, rcx
0x14000c637  jz      short loc_14000C654
0x14000c639  mov     rax, [rcx]
0x14000c63c  mov     edx, 1
0x14000c641  mov     rax, [rax]
0x14000c644  call    _guard_dispatch_icall
0x14000c649  mov     qword ptr [rbx+0B0h], 0
0x14000c654  mov     rcx, [rbx+0B8h]
0x14000c65b  test    rcx, rcx
0x14000c65e  jz      short loc_14000C67B
0x14000c660  mov     rax, [rcx]
0x14000c663  mov     edx, 1
0x14000c668  mov     rax, [rax]
0x14000c66b  call    _guard_dispatch_icall
0x14000c670  mov     qword ptr [rbx+0B8h], 0
0x14000c67b  lea     rcx, [rbx+58h]; this
0x14000c67f  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14000c684  lea     rax, ??_7TpmDataObject@tpm12class@@6B@; const tpm12class::TpmDataObject::`vftable'
0x14000c68b  xor     edx, edx; unsigned __int8
0x14000c68d  mov     rcx, rbx; this
0x14000c690  mov     [rbx], rax
0x14000c693  call    ?Clear@TpmDataObject@tpm12class@@MEAAJE@Z; tpm12class::TpmDataObject::Clear(uchar)
0x14000c698  add     rsp, 20h
0x14000c69c  pop     rbx
0x14000c69d  retn
```
