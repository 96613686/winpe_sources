# Microsoft::WRL::Details::MakeAndInitialize<DefaultHumanProvider,IHrtfAnthropometricsProvider,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHrtfAnthropometricsProvider>>)

- ea: `0x18000a3d0`
- end: `0x18000a4cc`
- name: `??$MakeAndInitialize@VDefaultHumanProvider@@UIHrtfAnthropometricsProvider@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIHrtfAnthropometricsProvider@@@WRL@Microsoft@@@012@@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800042fc`

## callees

- `0x180002d78`
- `0x18000a3d0`
- `0x18000b240`
- `0x18000b2c0`
- `0x18000e3f4`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<DefaultHumanProvider,IHrtfAnthropometricsProvider,>(
        __int64 *a1)
{
  __int64 v2; // rcx
  DefaultHumanProvider *v3; // rax
  DefaultHumanProvider *v4; // rdi
  int Interface; // esi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = (DefaultHumanProvider *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 3) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHrtfAnthropometricsProvider>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v4 = &DefaultHumanProvider::`vftable';
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    Interface = DefaultHumanProvider::RuntimeClassInitialize(v4);
    if ( Interface >= 0 )
      Interface = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHrtfAnthropometricsProvider>::QueryInterface(
                    v4,
                    &GUID_ea5d8790_507f_4df9_b65a_47534ad6ab42,
                    a1);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHrtfAnthropometricsProvider>::Release(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000a3d0  mov     [rsp+arg_10], rbx
0x18000a3d5  mov     [rsp+arg_18], rsi
0x18000a3da  push    rdi
0x18000a3db  sub     rsp, 20h
0x18000a3df  mov     rbx, rcx
0x18000a3e2  mov     rcx, [rcx]
0x18000a3e5  test    rcx, rcx
0x18000a3e8  jz      short loc_18000A3FE
0x18000a3ea  mov     qword ptr [rbx], 0
0x18000a3f1  mov     rax, [rcx]
0x18000a3f4  mov     rax, [rax+10h]
0x18000a3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3fd  nop
0x18000a3fe  mov     qword ptr [rbx], 0
0x18000a405  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a40c  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000a411  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a416  mov     rdi, rax
0x18000a419  mov     [rsp+28h+arg_0], rax
0x18000a41e  test    rax, rax
0x18000a421  jnz     short loc_18000A42D
0x18000a423  mov     esi, 8007000Eh
0x18000a428  jmp     loc_18000A4BA
0x18000a42d  mov     dword ptr [rax+0Ch], 1
0x18000a434  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHrtfAnthropometricsProvider@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHrtfAnthropometricsProvider>::`vftable'
0x18000a43b  mov     [rdi], rax
0x18000a43e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a445  test    rcx, rcx
0x18000a448  jz      short loc_18000A457
0x18000a44a  mov     rax, [rcx]
0x18000a44d  mov     rax, [rax+8]
0x18000a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a456  nop
0x18000a457  lea     rax, ??_7DefaultHumanProvider@@6B@; const DefaultHumanProvider::`vftable'
0x18000a45e  mov     [rdi], rax
0x18000a461  mov     qword ptr [rdi+10h], 0
0x18000a469  mov     qword ptr [rdi+18h], 0
0x18000a471  mov     qword ptr [rdi+20h], 0
0x18000a479  mov     qword ptr [rdi+28h], 0
0x18000a481  mov     [rsp+28h+arg_8], rdi
0x18000a486  mov     [rsp+28h+arg_0], 0
0x18000a48f  mov     rcx, rdi; this
0x18000a492  call    ?RuntimeClassInitialize@DefaultHumanProvider@@QEAAJXZ; DefaultHumanProvider::RuntimeClassInitialize(void)
0x18000a497  mov     esi, eax
0x18000a499  test    eax, eax
0x18000a49b  js      short loc_18000A4B1
0x18000a49d  mov     r8, rbx
0x18000a4a0  lea     rdx, _GUID_ea5d8790_507f_4df9_b65a_47534ad6ab42
0x18000a4a7  mov     rcx, rdi
0x18000a4aa  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHrtfAnthropometricsProvider@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHrtfAnthropometricsProvider>::QueryInterface(_GUID const &,void * *)
0x18000a4af  mov     esi, eax
0x18000a4b1  mov     rcx, rdi
0x18000a4b4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHrtfAnthropometricsProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHrtfAnthropometricsProvider>::Release(void)
0x18000a4b9  nop
0x18000a4ba  mov     eax, esi
0x18000a4bc  mov     rbx, [rsp+28h+arg_10]
0x18000a4c1  mov     rsi, [rsp+28h+arg_18]
0x18000a4c6  add     rsp, 20h
0x18000a4ca  pop     rdi
0x18000a4cb  retn
```
