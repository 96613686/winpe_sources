# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x18000ae00`
- end: `0x18000ae7e`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b3a0`

## callees

- `0x18000ae00`
- `0x18000b2d8`

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
0x18000ae00  sub     rsp, 28h
0x18000ae04  mov     r10, rdx
0x18000ae07  mov     r9, rcx
0x18000ae0a  mov     rcx, r10; struct _GUID *
0x18000ae0d  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046; struct _GUID *
0x18000ae14  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ae19  test    eax, eax
0x18000ae1b  jz      short loc_18000AE24
0x18000ae1d  mov     [r8], r9
0x18000ae20  xor     eax, eax
0x18000ae22  jmp     short loc_18000AE79
0x18000ae24  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x18000ae2b  add     r9, 8
0x18000ae2f  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ae34  test    eax, eax
0x18000ae36  jnz     short loc_18000AE48
0x18000ae38  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x18000ae3f  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ae44  test    eax, eax
0x18000ae46  jz      short loc_18000AE4F
0x18000ae48  xor     eax, eax
0x18000ae4a  mov     [r8], r9
0x18000ae4d  jmp     short loc_18000AE75
0x18000ae4f  lea     rdx, _GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34; struct _GUID *
0x18000ae56  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ae5b  mov     ecx, 80004002h
0x18000ae60  test    eax, eax
0x18000ae62  jz      short loc_18000AE6F
0x18000ae64  lea     rax, [r9+20h]
0x18000ae68  mov     [r8], rax
0x18000ae6b  xor     eax, eax
0x18000ae6d  jmp     short loc_18000AE71
0x18000ae6f  mov     eax, ecx
0x18000ae71  cmp     eax, ecx
0x18000ae73  jz      short loc_18000AE77
0x18000ae75  mov     ecx, eax
0x18000ae77  mov     eax, ecx
0x18000ae79  add     rsp, 28h
0x18000ae7d  retn
```
