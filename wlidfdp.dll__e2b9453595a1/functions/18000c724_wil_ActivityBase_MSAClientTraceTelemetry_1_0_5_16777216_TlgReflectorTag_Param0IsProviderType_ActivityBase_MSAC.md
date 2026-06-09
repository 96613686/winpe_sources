# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000c724`
- end: `0x18000c753`
- name: `??1?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000c8c8`

## callees

- `0x18000c75c`
- `0x18000c8f4`
- `0x18000ed10`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  wil::details::shared_object<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(a1 + 280);
  return wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x18000c724  push    rbx
0x18000c726  sub     rsp, 20h
0x18000c72a  mov     rbx, rcx
0x18000c72d  add     rcx, 120h; this
0x18000c734  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000c739  lea     rcx, [rbx+118h]
0x18000c740  call    ?reset@?$shared_object@V?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000c745  lea     rcx, [rbx+8]
0x18000c749  add     rsp, 20h
0x18000c74d  pop     rbx
0x18000c74e  jmp     ??1?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
```
