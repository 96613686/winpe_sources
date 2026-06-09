# wil::details::shared_object<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)

- ea: `0x18000ed10`
- end: `0x18000ed5c`
- name: `?reset@?$shared_object@V?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000c724`
- `0x18000c978`

## callees

- `0x1800027d4`
- `0x18000c75c`
- `0x18000ed10`

## pseudocode

```c
void __fastcall wil::details::shared_object<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rdi

  v2 = *a1;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *a1;
      if ( *a1 )
      {
        wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>((__int64)(v3 + 2));
        operator delete((void *)v3);
      }
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000ed10  mov     [rsp+arg_0], rbx
0x18000ed15  push    rdi
0x18000ed16  sub     rsp, 20h
0x18000ed1a  mov     rbx, rcx
0x18000ed1d  mov     rcx, [rcx]
0x18000ed20  test    rcx, rcx
0x18000ed23  jz      short loc_18000ED51
0x18000ed25  or      eax, 0FFFFFFFFh
0x18000ed28  lock xadd [rcx], eax
0x18000ed2c  cmp     eax, 1
0x18000ed2f  jnz     short loc_18000ED4A
0x18000ed31  mov     rdi, [rbx]
0x18000ed34  test    rdi, rdi
0x18000ed37  jz      short loc_18000ED4A
0x18000ed39  lea     rcx, [rdi+8]
0x18000ed3d  call    ??1?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000ed42  mov     rcx, rdi; Block
0x18000ed45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ed4a  mov     qword ptr [rbx], 0
0x18000ed51  mov     rbx, [rsp+28h+arg_0]
0x18000ed56  add     rsp, 20h
0x18000ed5a  pop     rdi
0x18000ed5b  retn
```
