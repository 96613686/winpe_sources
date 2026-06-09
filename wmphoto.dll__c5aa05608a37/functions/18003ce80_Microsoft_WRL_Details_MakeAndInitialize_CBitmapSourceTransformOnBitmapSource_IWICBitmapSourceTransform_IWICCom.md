# Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(IWICBitmapSourceTransform * *,IWICComponentFactory * &,IWICBitmapToneMapper * &&)

- ea: `0x18003ce80`
- end: `0x18003d041`
- name: `??$MakeAndInitialize@VCBitmapSourceTransformOnBitmapSource@@UIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@PEAUIWICBitmapToneMapper@@@Details@WRL@Microsoft@@YAJPEAPEAUIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@$$QEAPEAUIWICBitmapToneMapper@@@Z`
- size: `449`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d950`
- `0x18003db70`

## callees

- `0x18003653c`
- `0x18003ce80`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003cede`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003cede`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 *a3)
{
  _QWORD *v6; // rdi
  LPUNKNOWN v8; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v10; // rcx
  LPUNKNOWN v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // ebx
  LPUNKNOWN ppunkMarshal; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
    return 2147942414LL;
  v6[1] = &Microsoft::WRL::FtmBase::`vftable';
  v6[4] = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v8 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v10 = v6[4];
    if ( v10 )
    {
      v6[4] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v8,
      &GUID_00000003_0000_0000_c000_000000000046,
      v6 + 4);
  }
  v11 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v11->lpVtbl->Release)(v11);
  }
  *((_DWORD *)v6 + 11) = 1;
  *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `IWICBitmapSourceTransform'};
  v6[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v6 = &CBitmapSourceTransformOnBitmapSource::`vftable'{for `IWICBitmapSourceTransform'};
  v6[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v6[6] = 0;
  v6[7] = 0;
  v12 = *a3;
  v13 = *a2;
  v14 = 0;
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 8LL))(*a2);
    v14 = v6[6];
    v15 = v6[7];
    v6[7] = v13;
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v14 = v6[6];
    }
  }
  if ( v14 != v12 )
  {
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    v16 = v6[6];
    v6[6] = v12;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v6)(v6, &GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940, a1);
  (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  return v17;
}

```

## disassembly

```asm
0x18003ce80  push    rbx
0x18003ce82  push    rbp
0x18003ce83  push    rsi
0x18003ce84  push    rdi
0x18003ce85  push    r12
0x18003ce87  push    r13
0x18003ce89  push    r14
0x18003ce8b  push    r15
0x18003ce8d  sub     rsp, 28h
0x18003ce91  mov     r14, r8
0x18003ce94  mov     r15, rdx
0x18003ce97  mov     r12, rcx
0x18003ce9a  xor     r13d, r13d
0x18003ce9d  mov     [rcx], r13
0x18003cea0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cea7  mov     ecx, 40h ; '@'; unsigned __int64
0x18003ceac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ceb1  mov     rdi, rax
0x18003ceb4  test    rax, rax
0x18003ceb7  jnz     short loc_18003CEC3
0x18003ceb9  mov     eax, 8007000Eh
0x18003cebe  jmp     loc_18003D030
0x18003cec3  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18003ceca  mov     [rdi+8], rax
0x18003cece  mov     [rdi+20h], r13
0x18003ced2  mov     [rsp+68h+ppunkMarshal], r13
0x18003ced7  lea     rdx, [rsp+68h+ppunkMarshal]; ppunkMarshal
0x18003cedc  xor     ecx, ecx; punkOuter
0x18003cede  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18003cee4  test    eax, eax
0x18003cee6  js      short loc_18003CF24
0x18003cee8  mov     rbx, [rsp+68h+ppunkMarshal]
0x18003ceed  mov     rax, [rbx]
0x18003cef0  mov     rbp, [rax]
0x18003cef3  mov     rcx, [rdi+20h]
0x18003cef7  test    rcx, rcx
0x18003cefa  jz      short loc_18003CF0D
0x18003cefc  mov     [rdi+20h], r13
0x18003cf00  mov     rdx, [rcx]
0x18003cf03  mov     rax, [rdx+10h]
0x18003cf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf0c  nop
0x18003cf0d  lea     r8, [rdi+20h]
0x18003cf11  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18003cf18  mov     rcx, rbx
0x18003cf1b  mov     rax, rbp
0x18003cf1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf23  nop
0x18003cf24  mov     rcx, [rsp+68h+ppunkMarshal]
0x18003cf29  test    rcx, rcx
0x18003cf2c  jz      short loc_18003CF40
0x18003cf2e  mov     [rsp+68h+ppunkMarshal], r13
0x18003cf33  mov     rax, [rcx]
0x18003cf36  mov     rax, [rax+10h]
0x18003cf3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf3f  nop
0x18003cf40  mov     dword ptr [rdi+2Ch], 1
0x18003cf47  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWICBitmapSourceTransform@@VFtmBase@23@@WRL@Microsoft@@6BIWICBitmapSourceTransform@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `IWICBitmapSourceTransform'}
0x18003cf4e  mov     [rdi], rax
0x18003cf51  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWICBitmapSourceTransform@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003cf58  mov     [rdi+8], rax
0x18003cf5c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003cf63  test    rcx, rcx
0x18003cf66  jz      short loc_18003CF75
0x18003cf68  mov     rax, [rcx]
0x18003cf6b  mov     rax, [rax+8]
0x18003cf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf74  nop
0x18003cf75  lea     rax, ??_7CBitmapSourceTransformOnBitmapSource@@6BIWICBitmapSourceTransform@@@; const CBitmapSourceTransformOnBitmapSource::`vftable'{for `IWICBitmapSourceTransform'}
0x18003cf7c  mov     [rdi], rax
0x18003cf7f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWICBitmapSourceTransform@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003cf86  mov     [rdi+8], rax
0x18003cf8a  mov     [rdi+30h], r13
0x18003cf8e  mov     [rdi+38h], r13
0x18003cf92  mov     rbx, [r14]
0x18003cf95  mov     rsi, [r15]
0x18003cf98  mov     rax, r13
0x18003cf9b  test    rsi, rsi
0x18003cf9e  jz      short loc_18003CFD0
0x18003cfa0  mov     rax, [rsi]
0x18003cfa3  mov     rcx, rsi
0x18003cfa6  mov     rax, [rax+8]
0x18003cfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfaf  mov     rax, [rdi+30h]
0x18003cfb3  mov     rcx, [rdi+38h]
0x18003cfb7  mov     [rdi+38h], rsi
0x18003cfbb  test    rcx, rcx
0x18003cfbe  jz      short loc_18003CFD0
0x18003cfc0  mov     rax, [rcx]
0x18003cfc3  mov     rax, [rax+10h]
0x18003cfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfcc  mov     rax, [rdi+30h]
0x18003cfd0  cmp     rax, rbx
0x18003cfd3  jz      short loc_18003D004
0x18003cfd5  test    rbx, rbx
0x18003cfd8  jz      short loc_18003CFEA
0x18003cfda  mov     rax, [rbx]
0x18003cfdd  mov     rcx, rbx
0x18003cfe0  mov     rax, [rax+8]
0x18003cfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfe9  nop
0x18003cfea  mov     rcx, [rdi+30h]
0x18003cfee  mov     [rdi+30h], rbx
0x18003cff2  test    rcx, rcx
0x18003cff5  jz      short loc_18003D004
0x18003cff7  mov     rax, [rcx]
0x18003cffa  mov     rax, [rax+10h]
0x18003cffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d003  nop
0x18003d004  mov     rax, [rdi]
0x18003d007  mov     r8, r12
0x18003d00a  lea     rdx, _GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940
0x18003d011  mov     rcx, rdi
0x18003d014  mov     rax, [rax]
0x18003d017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d01c  mov     ebx, eax
0x18003d01e  mov     rcx, [rdi]
0x18003d021  mov     rax, [rcx+10h]
0x18003d025  mov     rcx, rdi
0x18003d028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d02d  nop
0x18003d02e  mov     eax, ebx
0x18003d030  add     rsp, 28h
0x18003d034  pop     r15
0x18003d036  pop     r14
0x18003d038  pop     r13
0x18003d03a  pop     r12
0x18003d03c  pop     rdi
0x18003d03d  pop     rsi
0x18003d03e  pop     rbp
0x18003d03f  pop     rbx
0x18003d040  retn
```
