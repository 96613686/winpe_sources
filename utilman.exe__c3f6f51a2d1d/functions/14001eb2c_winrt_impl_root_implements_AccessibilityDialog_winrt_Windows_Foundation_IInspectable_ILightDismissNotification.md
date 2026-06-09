# winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak<AccessibilityDialog>(void)

- ea: `0x14001eb2c`
- end: `0x14001ebc4`
- name: `??$get_weak@VAccessibilityDialog@@@?$root_implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@impl@winrt@@IEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002309c`

## callees

- `0x140002fac`
- `0x1400044e0`
- `0x140009ee0`
- `0x14000f914`
- `0x140010fb4`
- `0x14001eb2c`
- `0x140029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak<AccessibilityDialog>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 weak_ref; // rax
  unsigned int v4; // eax
  int pExceptionObject; // [rsp+28h] [rbp-20h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]
  char v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  weak_ref = winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::make_weak_ref(a1);
  if ( !weak_ref )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v9 = weak_ref;
  *a2 = 0;
  pExceptionObject = 0;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)weak_ref + 24LL))(weak_ref, a2);
  winrt::check_hresult(&v8, v4, &pExceptionObject);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x14001eb2c  mov     [rsp+arg_8], rdx
0x14001eb31  push    rbx
0x14001eb32  sub     rsp, 40h
0x14001eb36  mov     rbx, rdx
0x14001eb39  mov     [rsp+48h+var_28], 0
0x14001eb41  call    ?make_weak_ref@?$root_implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::make_weak_ref(void)
0x14001eb46  mov     rcx, rax
0x14001eb49  test    rax, rax
0x14001eb4c  jz      short loc_14001EBA8
0x14001eb4e  mov     [rsp+48h+arg_18], rax
0x14001eb53  mov     qword ptr [rbx], 0
0x14001eb5a  mov     [rsp+48h+var_28], 1
0x14001eb62  mov     [rsp+48h+pExceptionObject], 0
0x14001eb6a  xorps   xmm0, xmm0
0x14001eb6d  movdqu  [rsp+48h+var_18], xmm0
0x14001eb73  mov     rax, [rax]
0x14001eb76  mov     rdx, rbx
0x14001eb79  mov     rax, [rax+18h]
0x14001eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eb82  lea     r8, [rsp+48h+pExceptionObject]
0x14001eb87  mov     edx, eax
0x14001eb89  lea     rcx, [rsp+48h+arg_10]
0x14001eb8e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14001eb93  nop
0x14001eb94  lea     rcx, [rsp+48h+arg_18]
0x14001eb99  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001eb9e  mov     rax, rbx
0x14001eba1  add     rsp, 40h
0x14001eba5  pop     rbx
0x14001eba6  retn
0x14001eba8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14001ebad  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x14001ebb2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14001ebb9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001ebbe  call    _CxxThrowException_0
```
