# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x18000dad8`
- end: `0x18000db6f`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800143b0`

## callees

- `0x18000dad8`
- `0x180013ab4`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  const struct _GUID *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9
  const struct _GUID *v10; // rcx
  _QWORD *v11; // r8
  __int64 v12; // r10

  v3 = 0;
  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v4, &GUID_09870533_f7cb_569c_b797_dcb48debd709) )
    {
      *v8 = v9;
    }
    else
    {
      if ( !(unsigned int)InlineIsEqualGUID(v7, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
        && !(unsigned int)InlineIsEqualGUID(v10, &GUID_00000003_0000_0000_c000_000000000046) )
      {
        return (unsigned int)-2147467262;
      }
      v9 = v12;
      *v11 = v12;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    return v3;
  }
  *v5 = v6;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x18000dad8  push    rbx
0x18000dada  sub     rsp, 20h
0x18000dade  mov     r11, rdx
0x18000dae1  mov     r9, rcx
0x18000dae4  xor     ebx, ebx
0x18000dae6  mov     [r8], rbx
0x18000dae9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000daf0  mov     rcx, r11; struct _GUID *
0x18000daf3  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000daf8  test    eax, eax
0x18000dafa  jnz     short loc_18000DB55
0x18000dafc  lea     rdx, _GUID_09870533_f7cb_569c_b797_dcb48debd709; struct _GUID *
0x18000db03  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000db08  test    eax, eax
0x18000db0a  jz      short loc_18000DB11
0x18000db0c  mov     [r8], r9
0x18000db0f  jmp     short loc_18000DB3B
0x18000db11  lea     r10, [r9+8]
0x18000db15  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x18000db1c  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000db21  test    eax, eax
0x18000db23  jnz     short loc_18000DB35
0x18000db25  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x18000db2c  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000db31  test    eax, eax
0x18000db33  jz      short loc_18000DB4C
0x18000db35  mov     r9, r10
0x18000db38  mov     [r8], r10
0x18000db3b  mov     rax, [r9]
0x18000db3e  mov     rcx, r9
0x18000db41  mov     rax, [rax+8]
0x18000db45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db4a  jmp     short loc_18000DB51
0x18000db4c  mov     ebx, 80004002h
0x18000db51  mov     eax, ebx
0x18000db53  jmp     short loc_18000DB69
0x18000db55  mov     [r8], r9
0x18000db58  mov     rax, [r9]
0x18000db5b  mov     rcx, r9
0x18000db5e  mov     rax, [rax+8]
0x18000db62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db67  xor     eax, eax
0x18000db69  add     rsp, 20h
0x18000db6d  pop     rbx
0x18000db6e  retn
```
