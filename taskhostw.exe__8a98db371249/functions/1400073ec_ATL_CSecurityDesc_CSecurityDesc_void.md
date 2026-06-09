# ATL::CSecurityDesc::~CSecurityDesc(void)

- ea: `0x1400073ec`
- end: `0x1400073fb`
- name: `??1CSecurityDesc@ATL@@UEAA@XZ`
- size: `15`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000aaa0`

## callees

- `0x140002ce0`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::~CSecurityDesc(ATL::CSecurityDesc *this)
{
  *(_QWORD *)this = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear(this);
}

```

## disassembly

```asm
0x1400073ec  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1400073f3  mov     [rcx], rax
0x1400073f6  jmp     ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
```
