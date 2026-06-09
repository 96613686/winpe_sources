# MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties(void)

- ea: `0x18000c8c8`
- end: `0x18000c8ed`
- name: `??1QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000cec8`

## callees

- `0x18000c724`
- `0x18000c978`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  *(_QWORD *)this = &MSAClientTraceTelemetry::QueryWlidsvcProperties::`vftable';
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x18000c8c8  push    rbx
0x18000c8ca  sub     rsp, 20h
0x18000c8ce  lea     rax, ??_7QueryWlidsvcProperties@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::QueryWlidsvcProperties::`vftable'
0x18000c8d5  mov     rbx, rcx
0x18000c8d8  mov     [rcx], rax
0x18000c8db  call    ?Destroy@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000c8e0  mov     rcx, rbx
0x18000c8e3  add     rsp, 20h
0x18000c8e7  pop     rbx
0x18000c8e8  jmp     ??1?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
