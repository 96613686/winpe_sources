# tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)

- ea: `0x140038740`
- end: `0x1400387ac`
- name: `??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ`
- size: `108`
- prototype: `void __fastcall(tpm12class::TPMW8_ReadPublic *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032eb4`
- `0x1400387c0`

## callees

- `0x14000c5c4`
- `0x14000da40`
- `0x140038740`
- `0x140039780`

## pseudocode

```c
void __fastcall tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(tpm12class::TPMW8_ReadPublic *this)
{
  __int64 v2; // rcx

  *((_DWORD *)this + 49) = 1073741831;
  *(_QWORD *)this = &tpm12class::TPMW8_ReadPublic::`vftable';
  v2 = *((_QWORD *)this + 25);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 32LL))(v2, 1);
    *((_QWORD *)this + 25) = 0;
  }
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_ReadPublic *)((char *)this + 280));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW8_ReadPublic *)((char *)this + 208));
  tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(this);
}

```

## disassembly

```asm
0x140038740  push    rbx
0x140038742  sub     rsp, 20h
0x140038746  lea     rax, ??_7TPMW8_ReadPublic@tpm12class@@6B@; const tpm12class::TPMW8_ReadPublic::`vftable'
0x14003874d  mov     dword ptr [rcx+0C4h], 40000007h
0x140038757  mov     [rcx], rax
0x14003875a  mov     rbx, rcx
0x14003875d  mov     rcx, [rcx+0C8h]
0x140038764  test    rcx, rcx
0x140038767  jz      short loc_140038785
0x140038769  mov     rax, [rcx]
0x14003876c  mov     edx, 1
0x140038771  mov     rax, [rax+20h]
0x140038775  call    _guard_dispatch_icall
0x14003877a  mov     qword ptr [rbx+0C8h], 0
0x140038785  lea     rcx, [rbx+118h]; this
0x14003878c  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140038791  lea     rcx, [rbx+0D0h]; this
0x140038798  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003879d  mov     rcx, rbx; this
0x1400387a0  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x1400387a5  add     rsp, 20h
0x1400387a9  pop     rbx
0x1400387aa  retn
```
