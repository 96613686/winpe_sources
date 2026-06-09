# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x18000b090`
- end: `0x18000b10f`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b650`

## callees

- `0x18000b090`
- `0x18000b588`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
        __int64 a1,
        const struct _GUID *a2)
{
  const struct _GUID *v2; // rcx
  _QWORD *v3; // r8
  __int64 v4; // r9
  const struct _GUID *v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // r9
  const struct _GUID *v9; // rcx
  unsigned int v10; // eax
  int IsEqualGUID; // eax
  _QWORD *v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ecx

  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000035_0000_0000_c000_000000000046) )
  {
    *v3 = v4;
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v2, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
    || (unsigned int)InlineIsEqualGUID(v6, &GUID_00000003_0000_0000_c000_000000000046) )
  {
    v10 = 0;
    *v7 = v8;
  }
  else
  {
    IsEqualGUID = InlineIsEqualGUID(v9, &GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34);
    v14 = -2147467262;
    if ( IsEqualGUID )
    {
      *v12 = v13 + 32;
      v10 = 0;
    }
    else
    {
      v10 = -2147467262;
    }
    if ( v10 == -2147467262 )
      return v14;
  }
  return v10;
}

```

## disassembly

```asm
0x18000b090  sub     rsp, 28h
0x18000b094  mov     r10, rdx
0x18000b097  mov     r9, rcx
0x18000b09a  mov     rcx, r10; struct _GUID *
0x18000b09d  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046; struct _GUID *
0x18000b0a4  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b0a9  test    eax, eax
0x18000b0ab  jz      short loc_18000B0B4
0x18000b0ad  mov     [r8], r9
0x18000b0b0  xor     eax, eax
0x18000b0b2  jmp     short loc_18000B109
0x18000b0b4  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x18000b0bb  add     r9, 8
0x18000b0bf  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b0c4  test    eax, eax
0x18000b0c6  jnz     short loc_18000B0D8
0x18000b0c8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x18000b0cf  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b0d4  test    eax, eax
0x18000b0d6  jz      short loc_18000B0DF
0x18000b0d8  xor     eax, eax
0x18000b0da  mov     [r8], r9
0x18000b0dd  jmp     short loc_18000B105
0x18000b0df  lea     rdx, _GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34; struct _GUID *
0x18000b0e6  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b0eb  mov     ecx, 80004002h
0x18000b0f0  test    eax, eax
0x18000b0f2  jz      short loc_18000B0FF
0x18000b0f4  lea     rax, [r9+20h]
0x18000b0f8  mov     [r8], rax
0x18000b0fb  xor     eax, eax
0x18000b0fd  jmp     short loc_18000B101
0x18000b0ff  mov     eax, ecx
0x18000b101  cmp     eax, ecx
0x18000b103  jz      short loc_18000B107
0x18000b105  mov     ecx, eax
0x18000b107  mov     eax, ecx
0x18000b109  add     rsp, 28h
0x18000b10d  retn
```
