# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>(void)

- ea: `0x18006a160`
- end: `0x18006a232`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UINotificationDataPackage@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `210`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006a238`

## callees

- `0x18000ba54`
- `0x18006a160`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18006a19d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18006a19d`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v5; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  LPUNKNOWN v9; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  a1[3] = &Microsoft::WRL::FtmBase::`vftable';
  v5 = a1 + 6;
  a1[6] = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal, a2, a3, a4);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v9 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5, v6, v7, v8);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v9,
      &GUID_00000003_0000_0000_c000_000000000046,
      v5);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal, v6, v7, v8);
  a1[8] = 1;
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `IInspectable'};
  a1[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationDataPackage,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  a1[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x18006a160  push    rbx
0x18006a162  push    rsi
0x18006a163  push    rdi
0x18006a164  push    r14
0x18006a166  sub     rsp, 28h
0x18006a16a  mov     rsi, rcx
0x18006a16d  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18006a174  mov     [rcx+18h], rax
0x18006a178  lea     r14, [rcx+30h]
0x18006a17c  mov     qword ptr [r14], 0
0x18006a183  mov     [rsp+48h+ppunkMarshal], 0
0x18006a18c  lea     rcx, [rsp+48h+ppunkMarshal]
0x18006a191  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a196  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18006a19b  xor     ecx, ecx; punkOuter
0x18006a19d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18006a1a3  test    eax, eax
0x18006a1a5  js      short loc_18006A1D0
0x18006a1a7  mov     rbx, [rsp+48h+ppunkMarshal]
0x18006a1ac  mov     rax, [rbx]
0x18006a1af  mov     rdi, [rax]
0x18006a1b2  mov     rcx, r14
0x18006a1b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a1ba  mov     r8, r14
0x18006a1bd  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18006a1c4  mov     rcx, rbx
0x18006a1c7  mov     rax, rdi
0x18006a1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1cf  nop
0x18006a1d0  lea     rcx, [rsp+48h+ppunkMarshal]
0x18006a1d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a1da  mov     qword ptr [rsi+40h], 1
0x18006a1e2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UINotificationDataPackage@@VFtmBase@23@@WRL@Microsoft@@6BIInspectable@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `IInspectable'}
0x18006a1e9  mov     [rsi], rax
0x18006a1ec  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UINotificationDataPackage@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UINotificationDataPackage@@UIWeakReferenceSource@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationDataPackage,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x18006a1f3  mov     [rsi+8], rax
0x18006a1f7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UINotificationDataPackage@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18006a1fe  mov     [rsi+10h], rax
0x18006a202  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UINotificationDataPackage@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,INotificationDataPackage,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006a209  mov     [rsi+18h], rax
0x18006a20d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18006a214  test    rcx, rcx
0x18006a217  jz      short loc_18006A225
0x18006a219  mov     rax, [rcx]
0x18006a21c  mov     rax, [rax+8]
0x18006a220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a225  mov     rax, rsi
0x18006a228  add     rsp, 28h
0x18006a22c  pop     r14
0x18006a22e  pop     rdi
0x18006a22f  pop     rsi
0x18006a230  pop     rbx
0x18006a231  retn
```
