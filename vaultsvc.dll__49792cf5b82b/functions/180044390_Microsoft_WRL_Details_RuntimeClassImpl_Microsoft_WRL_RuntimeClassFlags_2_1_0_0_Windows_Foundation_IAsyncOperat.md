# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180044390`
- end: `0x18004440c`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044420`

## callees

- `0x18002eac0`
- `0x18002f190`
- `0x180044390`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  _QWORD *v6; // r8
  __int64 v7; // r9
  __int64 v8; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_4bd6f1e5_ca89_5240_8f3d_7f1b54ae90a7) )
  {
    *v6 = v7;
    CanCastTo = 0;
LABEL_5:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                v7 + 8,
                v8);
  if ( CanCastTo >= 0 )
    goto LABEL_5;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180044390  push    rbx
0x180044392  sub     rsp, 20h
0x180044396  mov     r10, rdx
0x180044399  mov     r9, rcx
0x18004439c  mov     qword ptr [r8], 0
0x1800443a3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1800443aa  mov     rcx, r10; struct _GUID *
0x1800443ad  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800443b2  test    eax, eax
0x1800443b4  jnz     short loc_1800443F0
0x1800443b6  lea     rdx, _GUID_4bd6f1e5_ca89_5240_8f3d_7f1b54ae90a7; struct _GUID *
0x1800443bd  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800443c2  test    eax, eax
0x1800443c4  jz      short loc_1800443CD
0x1800443c6  mov     [r8], r9
0x1800443c9  xor     ebx, ebx
0x1800443cb  jmp     short loc_1800443DF
0x1800443cd  lea     rcx, [r9+8]
0x1800443d1  mov     rdx, r10
0x1800443d4  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x1800443d9  mov     ebx, eax
0x1800443db  test    eax, eax
0x1800443dd  js      short loc_180044404
0x1800443df  mov     rcx, [r8]
0x1800443e2  mov     rax, [rcx]
0x1800443e5  mov     rax, [rax+8]
0x1800443e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443ee  jmp     short loc_180044404
0x1800443f0  mov     [r8], r9
0x1800443f3  mov     rax, [r9]
0x1800443f6  mov     rcx, r9
0x1800443f9  mov     rax, [rax+8]
0x1800443fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044402  xor     ebx, ebx
0x180044404  mov     eax, ebx
0x180044406  add     rsp, 20h
0x18004440a  pop     rbx
0x18004440b  retn
```
