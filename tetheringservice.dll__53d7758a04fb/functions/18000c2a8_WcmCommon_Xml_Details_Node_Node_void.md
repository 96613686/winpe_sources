# WcmCommon::Xml::Details::Node::~Node(void)

- ea: `0x18000c2a8`
- end: `0x18000c2c6`
- name: `??1Node@Details@Xml@WcmCommon@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(WcmCommon::Xml::Details::Node *__hidden this)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`
- `0x180031b67`
- `0x180031b9d`
- `0x180031baf`
- `0x180031e4e`
- `0x180031ec4`
- `0x180031ed6`
- `0x180031f0e`
- `0x180031f32`
- `0x180031f7a`
- `0x180031f8c`
- `0x180031fd4`
- `0x18003242f`
- `0x180032464`
- `0x180032490`
- `0x1800324bc`
- `0x1800325ac`
- `0x180032610`
- `0x180032645`

## callees

- `0x18000c2a8`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::Xml::Details::Node::~Node(WcmCommon::Xml::Details::Node *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000c2a8  sub     rsp, 28h
0x18000c2ac  mov     rcx, [rcx]
0x18000c2af  test    rcx, rcx
0x18000c2b2  jz      short loc_18000C2C1
0x18000c2b4  mov     rax, [rcx]
0x18000c2b7  mov     rax, [rax+10h]
0x18000c2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c0  nop
0x18000c2c1  add     rsp, 28h
0x18000c2c5  retn
```
