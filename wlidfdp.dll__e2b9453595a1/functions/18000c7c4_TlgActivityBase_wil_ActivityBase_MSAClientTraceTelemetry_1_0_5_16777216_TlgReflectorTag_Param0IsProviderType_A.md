# _TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>(void)

- ea: `0x18000c7c4`
- end: `0x18000c7fe`
- name: `??1?$_TlgActivityBase@V?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0A@$04@@IEAA@XZ`
- size: `58`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000c75c`

## callees

- `0x18000c6cc`
- `0x18000c7c4`
- `0x18000ce9c`

## pseudocode

```c
void __fastcall _TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>(
        _DWORD *a1)
{
  unsigned int *v2; // rax

  if ( *a1 == 1 )
  {
    *a1 = 2;
    v2 = (unsigned int *)wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::Provider();
    _tlgWriteActivityAutoStop<0,5>(v2, (__int64)(a1 + 2));
  }
  *a1 = 3;
}

```

## disassembly

```asm
0x18000c7c4  mov     [rsp+arg_0], rbx
0x18000c7c9  push    rdi
0x18000c7ca  sub     rsp, 20h
0x18000c7ce  cmp     dword ptr [rcx], 1
0x18000c7d1  mov     rdi, rcx
0x18000c7d4  jnz     short loc_18000C7ED
0x18000c7d6  mov     dword ptr [rcx], 2
0x18000c7dc  call    ?Provider@?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::Provider(void)
0x18000c7e1  mov     rcx, rax
0x18000c7e4  lea     rdx, [rdi+8]
0x18000c7e8  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x18000c7ed  mov     rbx, [rsp+28h+arg_0]
0x18000c7f2  mov     dword ptr [rdi], 3
0x18000c7f8  add     rsp, 20h
0x18000c7fc  pop     rdi
0x18000c7fd  retn
```
