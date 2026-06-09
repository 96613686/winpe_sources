# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<OSDeploymentInformationFactory,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1400116e0`
- end: `0x1400117bb`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VOSDeploymentInformationFactory@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400116e0`
- `0x14001ad2c`
- `0x1400206e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<OSDeploymentInformationFactory,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[3] = 1;
  v7[5] = 4;
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<OSDeploymentInformationFactory,0>::`vftable';
  ((void (__fastcall *)(_DWORD *))Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v7);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  v8[5] = *a1;
  v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v8)(v8, a3, a4);
  v10 = v9;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    if ( v9 < 0 )
    {
      v8[5] &= 0xFFFFFFFA;
    }
    else if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
    else
    {
      v8 = 0;
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v10;
}

```

## disassembly

```asm
0x1400116e0  mov     [rsp+arg_8], rbx
0x1400116e5  push    rbp
0x1400116e6  push    rsi
0x1400116e7  push    rdi
0x1400116e8  sub     rsp, 20h
0x1400116ec  mov     rbp, r9
0x1400116ef  mov     rdi, r8
0x1400116f2  mov     rsi, rcx
0x1400116f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400116fc  mov     ecx, 18h; unsigned __int64
0x140011701  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011706  mov     rbx, rax
0x140011709  test    rax, rax
0x14001170c  jz      loc_1400117A9
0x140011712  mov     dword ptr [rax+0Ch], 1
0x140011719  mov     dword ptr [rax+14h], 4
0x140011720  lea     rax, ??_7?$SimpleClassFactory@VOSDeploymentInformationFactory@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<OSDeploymentInformationFactory,0>::`vftable'
0x140011727  mov     [rbx], rax
0x14001172a  mov     rcx, rbx
0x14001172d  mov     rax, cs:off_1400241C8
0x140011734  call    _guard_dispatch_icall
0x140011739  nop
0x14001173a  mov     rax, [rbx]
0x14001173d  mov     rcx, rbx
0x140011740  mov     rax, [rax+10h]
0x140011744  call    _guard_dispatch_icall
0x140011749  nop
0x14001174a  mov     eax, [rsi]
0x14001174c  mov     [rbx+14h], eax
0x14001174f  mov     rax, [rbx]
0x140011752  mov     r8, rbp
0x140011755  mov     rdx, rdi
0x140011758  mov     rcx, rbx
0x14001175b  mov     rax, [rax]
0x14001175e  call    _guard_dispatch_icall
0x140011763  mov     edi, eax
0x140011765  test    byte ptr [rsi], 1
0x140011768  jz      short loc_140011790
0x14001176a  test    eax, eax
0x14001176c  js      short loc_14001178C
0x14001176e  test    byte ptr [rsi], 4
0x140011771  jz      short loc_140011788
0x140011773  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14001177a  mov     rax, [rcx]
0x14001177d  mov     rax, [rax+8]
0x140011781  call    _guard_dispatch_icall
0x140011786  jmp     short loc_140011790
0x140011788  xor     ebx, ebx
0x14001178a  jmp     short loc_140011790
0x14001178c  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x140011790  test    rbx, rbx
0x140011793  jz      short loc_1400117A5
0x140011795  mov     rax, [rbx]
0x140011798  mov     rcx, rbx
0x14001179b  mov     rax, [rax+10h]
0x14001179f  call    _guard_dispatch_icall
0x1400117a4  nop
0x1400117a5  mov     eax, edi
0x1400117a7  jmp     short loc_1400117AE
0x1400117a9  mov     eax, 8007000Eh
0x1400117ae  mov     rbx, [rsp+38h+arg_8]
0x1400117b3  add     rsp, 20h
0x1400117b7  pop     rdi
0x1400117b8  pop     rsi
0x1400117b9  pop     rbp
0x1400117ba  retn
```
