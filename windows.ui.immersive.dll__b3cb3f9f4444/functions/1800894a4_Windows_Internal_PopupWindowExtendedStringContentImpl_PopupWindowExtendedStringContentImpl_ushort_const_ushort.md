# Windows::Internal::PopupWindowExtendedStringContentImpl::PopupWindowExtendedStringContentImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800894a4`
- end: `0x18008967a`
- name: `??0PopupWindowExtendedStringContentImpl@Internal@Windows@@QEAA@PEBG0000@Z`
- size: `470`
- prototype: `__int64 __fastcall(Windows::Internal::PopupWindowExtendedStringContentImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a1d8`

## callees

- `0x18000b5b8`
- `0x1800893d4`
- `0x1800894a4`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008953f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800895b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800895d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800895f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008961e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008953f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800895b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800895d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800895f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008961e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089649`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
Windows::Internal::PopupWindowExtendedStringContentImpl *__fastcall Windows::Internal::PopupWindowExtendedStringContentImpl::PopupWindowExtendedStringContentImpl(
        Windows::Internal::PopupWindowExtendedStringContentImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  LPVOID *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx

  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      0);
  *(_QWORD *)this = &Windows::Internal::PopupWindowExtendedStringContentImpl::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v9 = (LPVOID *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 9) = 0;
  CoTaskMemFree(0);
  *((_QWORD *)this + 4) = 0;
  CoTaskMemFree(*((LPVOID *)this + 5));
  *((_QWORD *)this + 5) = 0;
  CoTaskMemFree(*((LPVOID *)this + 6));
  *((_QWORD *)this + 6) = 0;
  CoTaskMemFree(*((LPVOID *)this + 7));
  *((_QWORD *)this + 7) = 0;
  CoTaskMemFree(*((LPVOID *)this + 9));
  *((_QWORD *)this + 9) = 0;
  if ( a2 )
  {
    CoTaskMemFree(*((LPVOID *)this + 4));
    _AllocString<CTCoAllocPolicy>(v11, v10, a2, (_QWORD *)this + 4);
  }
  if ( a3 )
  {
    CoTaskMemFree(*((LPVOID *)this + 5));
    _AllocString<CTCoAllocPolicy>(v13, v12, a3, (_QWORD *)this + 5);
  }
  if ( a4 )
  {
    CoTaskMemFree(*v9);
    _AllocString<CTCoAllocPolicy>(v15, v14, a4, v9);
  }
  if ( a5 )
  {
    CoTaskMemFree(*((LPVOID *)this + 7));
    _AllocString<CTCoAllocPolicy>(v17, v16, a5, (_QWORD *)this + 7);
  }
  if ( a6 )
  {
    *((_BYTE *)this + 64) = 1;
    CoTaskMemFree(*((LPVOID *)this + 9));
    _AllocString<CTCoAllocPolicy>(v19, v18, a6, (_QWORD *)this + 9);
  }
  return this;
}

```

## disassembly

```asm
0x1800894a4  mov     [rsp+arg_10], rbx
0x1800894a9  mov     [rsp+arg_8], rdx
0x1800894ae  mov     [rsp+arg_0], rcx
0x1800894b3  push    rbp
0x1800894b4  push    rsi
0x1800894b5  push    rdi
0x1800894b6  push    r12
0x1800894b8  push    r13
0x1800894ba  push    r14
0x1800894bc  push    r15
0x1800894be  sub     rsp, 20h
0x1800894c2  mov     r12, r9
0x1800894c5  mov     r13, r8
0x1800894c8  mov     rbx, rcx
0x1800894cb  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIPopupWindowImplDUIContent@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>(void)
0x1800894d0  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIPopupWindowExtendedStringContent@Internal@Windows@@@WRL@Microsoft@@6BIPopupWindowExtendedStringContent@Internal@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'}
0x1800894d7  mov     [rbx], rcx
0x1800894da  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIPopupWindowExtendedStringContent@Internal@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x1800894e1  mov     [rbx+8], rax
0x1800894e5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800894ec  xor     edx, edx
0x1800894ee  test    rcx, rcx
0x1800894f1  jz      short loc_180089501
0x1800894f3  mov     rax, [rcx]
0x1800894f6  mov     rax, [rax+8]
0x1800894fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894ff  xor     edx, edx
0x180089501  lea     rax, ??_7PopupWindowExtendedStringContentImpl@Internal@Windows@@6BIPopupWindowExtendedStringContent@12@@; const Windows::Internal::PopupWindowExtendedStringContentImpl::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'}
0x180089508  mov     [rbx], rax
0x18008950b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIPopupWindowExtendedStringContent@Internal@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180089512  mov     [rbx+8], rax
0x180089516  lea     rbp, [rbx+20h]
0x18008951a  mov     [rbp+0], rdx
0x18008951e  lea     r15, [rbx+28h]
0x180089522  mov     [r15], rdx
0x180089525  lea     rdi, [rbx+30h]
0x180089529  mov     [rdi], rdx
0x18008952c  lea     r14, [rbx+38h]
0x180089530  mov     [r14], rdx
0x180089533  mov     [rbx+40h], dl
0x180089536  lea     rsi, [rbx+48h]
0x18008953a  mov     [rsi], rdx
0x18008953d  xor     ecx, ecx; pv
0x18008953f  call    cs:__imp_CoTaskMemFree
0x180089546  nop     dword ptr [rax+rax+00h]
0x18008954b  mov     qword ptr [rbp+0], 0
0x180089553  mov     rcx, [r15]; pv
0x180089556  call    cs:__imp_CoTaskMemFree
0x18008955d  nop     dword ptr [rax+rax+00h]
0x180089562  mov     qword ptr [r15], 0
0x180089569  mov     rcx, [rdi]; pv
0x18008956c  call    cs:__imp_CoTaskMemFree
0x180089573  nop     dword ptr [rax+rax+00h]
0x180089578  mov     qword ptr [rdi], 0
0x18008957f  mov     rcx, [r14]; pv
0x180089582  call    cs:__imp_CoTaskMemFree
0x180089589  nop     dword ptr [rax+rax+00h]
0x18008958e  mov     qword ptr [r14], 0
0x180089595  mov     rcx, [rsi]; pv
0x180089598  call    cs:__imp_CoTaskMemFree
0x18008959f  nop     dword ptr [rax+rax+00h]
0x1800895a4  mov     qword ptr [rsi], 0
0x1800895ab  cmp     [rsp+58h+arg_8], 0
0x1800895b1  jz      short loc_1800895D0
0x1800895b3  mov     rcx, [rbp+0]; pv
0x1800895b7  call    cs:__imp_CoTaskMemFree
0x1800895be  nop     dword ptr [rax+rax+00h]
0x1800895c3  mov     r9, rbp
0x1800895c6  mov     r8, [rsp+58h+arg_8]
0x1800895cb  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800895d0  test    r13, r13
0x1800895d3  jz      short loc_1800895EF
0x1800895d5  mov     rcx, [r15]; pv
0x1800895d8  call    cs:__imp_CoTaskMemFree
0x1800895df  nop     dword ptr [rax+rax+00h]
0x1800895e4  mov     r9, r15
0x1800895e7  mov     r8, r13
0x1800895ea  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800895ef  test    r12, r12
0x1800895f2  jz      short loc_18008960E
0x1800895f4  mov     rcx, [rdi]; pv
0x1800895f7  call    cs:__imp_CoTaskMemFree
0x1800895fe  nop     dword ptr [rax+rax+00h]
0x180089603  mov     r9, rdi
0x180089606  mov     r8, r12
0x180089609  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18008960e  mov     rdi, [rsp+58h+arg_20]
0x180089616  test    rdi, rdi
0x180089619  jz      short loc_180089635
0x18008961b  mov     rcx, [r14]; pv
0x18008961e  call    cs:__imp_CoTaskMemFree
0x180089625  nop     dword ptr [rax+rax+00h]
0x18008962a  mov     r9, r14
0x18008962d  mov     r8, rdi
0x180089630  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180089635  mov     rdi, [rsp+58h+arg_28]
0x18008963d  test    rdi, rdi
0x180089640  jz      short loc_180089661
0x180089642  mov     byte ptr [rbx+40h], 1
0x180089646  mov     rcx, [rsi]; pv
0x180089649  call    cs:__imp_CoTaskMemFree
0x180089650  nop     dword ptr [rax+rax+00h]
0x180089655  mov     r9, rsi
0x180089658  mov     r8, rdi
0x18008965b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180089660  nop
0x180089661  mov     rax, rbx
0x180089664  mov     rbx, [rsp+58h+arg_10]
0x180089669  add     rsp, 20h
0x18008966d  pop     r15
0x18008966f  pop     r14
0x180089671  pop     r13
0x180089673  pop     r12
0x180089675  pop     rdi
0x180089676  pop     rsi
0x180089677  pop     rbp
0x180089678  retn
```
