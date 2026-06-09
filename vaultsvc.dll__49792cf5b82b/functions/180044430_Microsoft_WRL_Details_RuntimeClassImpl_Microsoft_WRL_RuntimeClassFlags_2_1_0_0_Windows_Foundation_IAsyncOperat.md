# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180044430`
- end: `0x1800444ac`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800444c0`

## callees

- `0x18002eac0`
- `0x18002f190`
- `0x180044430`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::QueryInterface(
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
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_9477622b_1340_5574_81fc_5013581f57c9) )
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
0x180044430  push    rbx
0x180044432  sub     rsp, 20h
0x180044436  mov     r10, rdx
0x180044439  mov     r9, rcx
0x18004443c  mov     qword ptr [r8], 0
0x180044443  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18004444a  mov     rcx, r10; struct _GUID *
0x18004444d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180044452  test    eax, eax
0x180044454  jnz     short loc_180044490
0x180044456  lea     rdx, _GUID_9477622b_1340_5574_81fc_5013581f57c9; struct _GUID *
0x18004445d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180044462  test    eax, eax
0x180044464  jz      short loc_18004446D
0x180044466  mov     [r8], r9
0x180044469  xor     ebx, ebx
0x18004446b  jmp     short loc_18004447F
0x18004446d  lea     rcx, [r9+8]
0x180044471  mov     rdx, r10
0x180044474  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x180044479  mov     ebx, eax
0x18004447b  test    eax, eax
0x18004447d  js      short loc_1800444A4
0x18004447f  mov     rcx, [r8]
0x180044482  mov     rax, [rcx]
0x180044485  mov     rax, [rax+8]
0x180044489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004448e  jmp     short loc_1800444A4
0x180044490  mov     [r8], r9
0x180044493  mov     rax, [r9]
0x180044496  mov     rcx, r9
0x180044499  mov     rax, [rax+8]
0x18004449d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444a2  xor     ebx, ebx
0x1800444a4  mov     eax, ebx
0x1800444a6  add     rsp, 20h
0x1800444aa  pop     rbx
0x1800444ab  retn
```
