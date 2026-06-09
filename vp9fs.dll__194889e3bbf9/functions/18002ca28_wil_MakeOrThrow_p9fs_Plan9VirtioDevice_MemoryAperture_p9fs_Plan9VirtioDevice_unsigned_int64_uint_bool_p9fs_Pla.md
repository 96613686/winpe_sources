# wil::MakeOrThrow<p9fs::Plan9VirtioDevice::MemoryAperture,p9fs::Plan9VirtioDevice &,unsigned __int64 &,uint,bool>(p9fs::Plan9VirtioDevice &,unsigned __int64 &,uint &&,bool &&)

- ea: `0x18002ca28`
- end: `0x18002cb8d`
- name: `??$MakeOrThrow@VMemoryAperture@Plan9VirtioDevice@p9fs@@AEAV23@AEA_KI_N@wil@@YA?AV?$ComPtr@VMemoryAperture@Plan9VirtioDevice@p9fs@@@WRL@Microsoft@@AEAVPlan9VirtioDevice@p9fs@@AEA_K$$QEAI$$QEA_N@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002db40`

## callees

- `0x180004120`
- `0x18000456c`
- `0x180004590`
- `0x18001c75c`
- `0x180028738`
- `0x18002ca28`
- `0x180034010`

## import_xrefs

- `vmdevicehost!HdvCreateGuestMemoryAperture` at `0x18002cafd`
- `vmdevicehost!HdvCreateGuestMemoryAperture` at `0x18002cafd`

## string_xrefs

- `0x18002cb7b`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall wil::MakeOrThrow<p9fs::Plan9VirtioDevice::MemoryAperture,p9fs::Plan9VirtioDevice &,unsigned __int64 &,unsigned int,bool>(
        _QWORD *a1,
        __int64 a2,
        UINT64 *a3,
        UINT32 *a4,
        unsigned __int8 *a5)
{
  _QWORD *v9; // rax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  _QWORD *v13; // rbx
  int v14; // esi
  UINT32 v15; // ebp
  UINT64 v16; // r14
  HRESULT v17; // eax
  int mappedAddress; // [rsp+20h] [rbp-88h]
  PVOID v20; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a1 = 0;
  v9 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v13 = v9;
  if ( v9 )
  {
    v14 = *a5;
    v15 = *a4;
    v16 = *a3;
    *((_DWORD *)v9 + 3) = 1;
    *v9 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v13 = &p9fs::Plan9VirtioDevice::MemoryAperture::`vftable';
    v13[2] = a2;
    v20 = 0;
    v17 = HdvCreateGuestMemoryAperture(*(HDV_DEVICE *)(a2 + 32), v16, v15, v14, &v20);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
        (const char *)(unsigned int)v17,
        mappedAddress);
    v13[3] = v20;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v13;
    v13 = 0;
  }
  if ( v13 )
    operator delete(v13);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v10, v11, v12);
  return a1;
}

```

## disassembly

```asm
0x18002ca28  push    rbx
0x18002ca2a  push    rbp
0x18002ca2b  push    rsi
0x18002ca2c  push    rdi
0x18002ca2d  push    r14
0x18002ca2f  push    r15
0x18002ca31  sub     rsp, 78h
0x18002ca35  mov     rax, cs:__security_cookie
0x18002ca3c  xor     rax, rsp
0x18002ca3f  mov     [rsp+0A8h+var_48], rax
0x18002ca44  mov     rbp, r9
0x18002ca47  mov     r14, r8
0x18002ca4a  mov     r15, rdx
0x18002ca4d  mov     rdi, rcx
0x18002ca50  mov     [rsp+0A8h+var_70], rcx
0x18002ca55  mov     rsi, [rsp+0A8h+arg_20]
0x18002ca5d  mov     [rsp+0A8h+var_78], 0
0x18002ca65  xor     eax, eax
0x18002ca67  mov     [rcx], rax
0x18002ca6a  mov     [rsp+0A8h+var_78], 2
0x18002ca72  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ca79  lea     ecx, [rax+20h]; unsigned __int64
0x18002ca7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ca81  mov     rbx, rax
0x18002ca84  mov     [rsp+0A8h+var_68], rax
0x18002ca89  mov     [rsp+0A8h+var_60], rax
0x18002ca8e  test    rax, rax
0x18002ca91  jz      loc_18002CB31
0x18002ca97  mov     [rsp+0A8h+var_58], rax
0x18002ca9c  movzx   esi, byte ptr [rsi]
0x18002ca9f  mov     ebp, [rbp+0]
0x18002caa2  mov     r14, [r14]
0x18002caa5  mov     dword ptr [rax+0Ch], 1
0x18002caac  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18002cab3  mov     [rbx], rax
0x18002cab6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002cabd  test    rcx, rcx
0x18002cac0  jz      short loc_18002CACF
0x18002cac2  mov     rax, [rcx]
0x18002cac5  mov     rax, [rax+8]
0x18002cac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cace  nop
0x18002cacf  lea     rax, ??_7MemoryAperture@Plan9VirtioDevice@p9fs@@6B@; const p9fs::Plan9VirtioDevice::MemoryAperture::`vftable'
0x18002cad6  mov     [rbx], rax
0x18002cad9  mov     [rbx+10h], r15
0x18002cadd  mov     [rsp+0A8h+var_50], 0
0x18002cae6  mov     r9d, esi; writeProtected
0x18002cae9  lea     rax, [rsp+0A8h+var_50]
0x18002caee  mov     qword ptr [rsp+0A8h+mappedAddress], rax; int
0x18002caf3  mov     r8d, ebp; byteCount
0x18002caf6  mov     rdx, r14; guestPhysicalAddress
0x18002caf9  mov     rcx, [r15+20h]; requestor
0x18002cafd  call    cs:__imp_HdvCreateGuestMemoryAperture
0x18002cb03  mov     rcx, [rsp+0A8h]; this
0x18002cb0b  test    eax, eax
0x18002cb0d  js      short loc_18002CB78
0x18002cb0f  mov     rax, [rsp+0A8h+var_50]
0x18002cb14  mov     [rbx+18h], rax
0x18002cb18  mov     rcx, [rdi]
0x18002cb1b  test    rcx, rcx
0x18002cb1e  jz      short loc_18002CB2C
0x18002cb20  mov     rax, [rcx]
0x18002cb23  mov     rax, [rax+10h]
0x18002cb27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb2c  mov     [rdi], rbx
0x18002cb2f  xor     ebx, ebx
0x18002cb31  test    rbx, rbx
0x18002cb34  jz      short loc_18002CB3F
0x18002cb36  mov     rcx, rbx; Block
0x18002cb39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cb3e  nop
0x18002cb3f  mov     [rsp+0A8h+var_78], 1
0x18002cb47  cmp     qword ptr [rdi], 0
0x18002cb4b  jz      short loc_18002CB6A
0x18002cb4d  mov     rax, rdi
0x18002cb50  mov     rcx, [rsp+0A8h+var_48]
0x18002cb55  xor     rcx, rsp; StackCookie
0x18002cb58  call    __security_check_cookie
0x18002cb5d  add     rsp, 78h
0x18002cb61  pop     r15
0x18002cb63  pop     r14
0x18002cb65  pop     rdi
0x18002cb66  pop     rsi
0x18002cb67  pop     rbp
0x18002cb68  pop     rbx
0x18002cb69  retn
0x18002cb6a  mov     rcx, [rsp+0A8h]; this
0x18002cb72  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002cb78  mov     r9d, eax; char *
0x18002cb7b  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002cb82  mov     edx, 75h ; 'u'; void *
0x18002cb87  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
