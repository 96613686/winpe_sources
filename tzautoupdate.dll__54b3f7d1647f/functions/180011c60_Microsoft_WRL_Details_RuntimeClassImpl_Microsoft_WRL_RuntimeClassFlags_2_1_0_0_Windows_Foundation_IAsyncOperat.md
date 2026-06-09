# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011c60`
- end: `0x180011cb6`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006814`
- `0x180011c60`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9

  v3 = 0;
  *a3 = 0;
  if ( InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || InlineIsEqualGUID(v4, &GUID_7668a704_244e_5e12_8dcb_92a3299eba26) )
  {
    *v5 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  else
  {
    return (unsigned int)-2147467262;
  }
  return v3;
}

```

## disassembly

```asm
0x180011c60  push    rbx
0x180011c62  sub     rsp, 20h
0x180011c66  mov     r10, rdx
0x180011c69  mov     r9, rcx
0x180011c6c  xor     ebx, ebx
0x180011c6e  mov     [r8], rbx
0x180011c71  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180011c78  mov     rcx, r10; struct _GUID *
0x180011c7b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180011c80  test    eax, eax
0x180011c82  jnz     short loc_180011C9B
0x180011c84  lea     rdx, _GUID_7668a704_244e_5e12_8dcb_92a3299eba26; struct _GUID *
0x180011c8b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180011c90  test    eax, eax
0x180011c92  jnz     short loc_180011C9B
0x180011c94  mov     ebx, 80004002h
0x180011c99  jmp     short loc_180011CAE
0x180011c9b  mov     [r8], r9
0x180011c9e  mov     rax, [r9]
0x180011ca1  mov     rcx, r9
0x180011ca4  mov     rax, [rax+8]
0x180011ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cad  nop
0x180011cae  mov     eax, ebx
0x180011cb0  add     rsp, 20h
0x180011cb4  pop     rbx
0x180011cb5  retn
```
