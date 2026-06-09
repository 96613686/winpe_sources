# WcmCommon::Xml::Details::Document::~Document(void)

- ea: `0x180028e00`
- end: `0x180028e6e`
- name: `??1Document@Details@Xml@WcmCommon@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(WcmCommon::Xml::Details::Document *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`
- `0x180028d20`
- `0x1800298e0`
- `0x180032248`

## callees

- `0x180028e00`
- `0x180033010`

## pseudocode

```c
void __fastcall WcmCommon::Xml::Details::Document::~Document(WcmCommon::Xml::Details::Document *this)
{
  volatile signed __int32 *v2; // rbx

  v2 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180028e00  mov     [rsp+arg_0], rbx
0x180028e05  push    rdi
0x180028e06  sub     rsp, 20h
0x180028e0a  mov     rdi, rcx
0x180028e0d  mov     rbx, [rcx+10h]
0x180028e11  test    rbx, rbx
0x180028e14  jz      short loc_180028E4E
0x180028e16  or      eax, 0FFFFFFFFh
0x180028e19  lock xadd [rbx+8], eax
0x180028e1e  cmp     eax, 1
0x180028e21  jnz     short loc_180028E4E
0x180028e23  mov     rax, [rbx]
0x180028e26  mov     rcx, rbx
0x180028e29  mov     rax, [rax]
0x180028e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e31  or      eax, 0FFFFFFFFh
0x180028e34  lock xadd [rbx+0Ch], eax
0x180028e39  cmp     eax, 1
0x180028e3c  jnz     short loc_180028E4E
0x180028e3e  mov     rax, [rbx]
0x180028e41  mov     rcx, rbx
0x180028e44  mov     rax, [rax+8]
0x180028e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e4d  nop
0x180028e4e  mov     rcx, [rdi]
0x180028e51  test    rcx, rcx
0x180028e54  jz      short loc_180028E63
0x180028e56  mov     rax, [rcx]
0x180028e59  mov     rax, [rax+10h]
0x180028e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e62  nop
0x180028e63  mov     rbx, [rsp+28h+arg_0]
0x180028e68  add     rsp, 20h
0x180028e6c  pop     rdi
0x180028e6d  retn
```
