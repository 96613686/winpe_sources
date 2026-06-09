# wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000cfc0`
- end: `0x18000d031`
- name: `??1?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000d1cc`

## callees

- `0x18000cf4c`
- `0x18000cfc0`
- `0x18000d14c`
- `0x180010334`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  volatile signed __int32 *v2; // rcx
  char *v3; // rdi

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v2 = *(volatile signed __int32 **)(a1 + 280);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *(char **)(a1 + 280);
      if ( v3 )
      {
        wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3, 0x110u);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x18000cfc0  mov     [rsp+arg_0], rbx
0x18000cfc5  push    rdi
0x18000cfc6  sub     rsp, 20h
0x18000cfca  mov     rbx, rcx
0x18000cfcd  add     rcx, 120h; this
0x18000cfd4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000cfd9  mov     rcx, [rbx+118h]
0x18000cfe0  test    rcx, rcx
0x18000cfe3  jz      short loc_18000D01E
0x18000cfe5  or      eax, 0FFFFFFFFh
0x18000cfe8  lock xadd [rcx], eax
0x18000cfec  cmp     eax, 1
0x18000cfef  jnz     short loc_18000D013
0x18000cff1  mov     rdi, [rbx+118h]
0x18000cff8  test    rdi, rdi
0x18000cffb  jz      short loc_18000D013
0x18000cffd  lea     rcx, [rdi+8]
0x18000d001  call    ??1?$ActivityData@VTelemetry4UpdateCli@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000d006  mov     edx, 110h; unsigned __int64
0x18000d00b  mov     rcx, rdi; void *
0x18000d00e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d013  mov     qword ptr [rbx+118h], 0
0x18000d01e  lea     rcx, [rbx+8]
0x18000d022  mov     rbx, [rsp+28h+arg_0]
0x18000d027  add     rsp, 20h
0x18000d02b  pop     rdi
0x18000d02c  jmp     ??1?$ActivityData@VTelemetry4UpdateCli@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(void)
```
