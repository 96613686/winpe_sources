# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)

- ea: `0x18000d67c`
- end: `0x18000d6d5`
- name: `?SetStopResult@?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z`
- size: `89`
- prototype: `bool __fastcall(__int64, int, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000c978`
- `0x18000d88c`

## callees

- `0x1800033b4`
- `0x180009348`
- `0x18000d67c`

## pseudocode

```c
bool __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        __int64 a1,
        int a2,
        _DWORD *a3)
{
  int v3; // eax
  const struct wil::FailureInfo *v4; // rdx
  int v5; // eax
  _BYTE v7[168]; // [rsp+20h] [rbp-A8h] BYREF

  v3 = *(_DWORD *)(a1 + 248);
  if ( v3 < 1 )
  {
    memset_0(v7, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v7, v4);
  }
  if ( *(int *)(a1 + 72) < 0 )
    a2 = *(_DWORD *)(a1 + 72);
  else
    *(_DWORD *)(a1 + 72) = a2;
  if ( a3 )
    *a3 = a2;
  v5 = v3 - 1;
  *(_DWORD *)(a1 + 248) = v5;
  return v5 == 0;
}

```

## disassembly

```asm
0x18000d67c  sub     rsp, 0C8h
0x18000d683  mov     eax, [rcx+0F8h]
0x18000d689  cmp     eax, 1
0x18000d68c  jge     short loc_18000D6AB
0x18000d68e  xor     edx, edx; Val
0x18000d690  mov     r8d, 98h; Size
0x18000d696  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000d69b  call    memset_0
0x18000d6a0  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000d6a5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d6ab  cmp     dword ptr [rcx+48h], 0
0x18000d6af  jl      short loc_18000D6B6
0x18000d6b1  mov     [rcx+48h], edx
0x18000d6b4  jmp     short loc_18000D6B9
0x18000d6b6  mov     edx, [rcx+48h]
0x18000d6b9  test    r8, r8
0x18000d6bc  jz      short loc_18000D6C1
0x18000d6be  mov     [r8], edx
0x18000d6c1  sub     eax, 1
0x18000d6c4  mov     [rcx+0F8h], eax
0x18000d6ca  setz    al
0x18000d6cd  add     rsp, 0C8h
0x18000d6d4  retn
```
