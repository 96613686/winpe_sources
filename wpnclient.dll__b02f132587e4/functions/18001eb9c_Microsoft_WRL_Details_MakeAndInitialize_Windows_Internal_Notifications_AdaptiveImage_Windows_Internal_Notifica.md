# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::AdaptiveImage,Windows::Internal::Notifications::IAdaptiveImage,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(Windows::Internal::Notifications::IAdaptiveImage * *,Microsoft::WRL::Wrappers::HString &&,Microsoft::WRL::Wrappers::HString &&,Microsoft::WRL::Wrappers::HString &&)

- ea: `0x18001eb9c`
- end: `0x18001eca5`
- name: `??$MakeAndInitialize@VAdaptiveImage@Notifications@Internal@Windows@@UIAdaptiveImage@234@VHString@Wrappers@WRL@Microsoft@@V6789@V6789@@Details@WRL@Microsoft@@YAJPEAPEAUIAdaptiveImage@Notifications@Internal@Windows@@$$QEAVHString@Wrappers@12@11@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001e1a4`

## callees

- `0x18001bf84`
- `0x18001eb9c`
- `0x180020350`
- `0x180023488`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ebff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ec1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ec3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ebff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ec1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ec3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::AdaptiveImage,Windows::Internal::Notifications::IAdaptiveImage,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(
        _QWORD *a1,
        HSTRING *a2,
        HSTRING *a3,
        HSTRING *a4)
{
  Windows::Internal::Notifications::AdaptiveImage *v8; // rax
  unsigned int v9; // edi
  HSTRING *v10; // rbx
  Windows::Internal::Notifications::AdaptiveImage *v12; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v8 = (Windows::Internal::Notifications::AdaptiveImage *)operator new(
                                                            0x60u,
                                                            (const struct std::nothrow_t *)std::nothrow);
  v12 = v8;
  if ( v8 )
  {
    v10 = (HSTRING *)Windows::Internal::Notifications::AdaptiveImage::AdaptiveImage(v8);
    v12 = 0;
    WindowsDeleteString(v10[9]);
    v10[9] = 0;
    v10[9] = *a2;
    *a2 = 0;
    WindowsDeleteString(v10[10]);
    v10[10] = 0;
    v10[10] = *a3;
    *a3 = 0;
    WindowsDeleteString(v10[11]);
    v10[11] = 0;
    v10[11] = *a4;
    *a4 = 0;
    v9 = (*(__int64 (__fastcall **)(HSTRING *, GUID *, _QWORD *))*v10)(
           v10,
           &GUID_9f589171_8551_48a0_922b_1abf11a66340,
           a1);
    (*((void (__fastcall **)(HSTRING *))*v10 + 2))(v10);
  }
  else
  {
    v9 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(&v12);
  return v9;
}

```

## disassembly

```asm
0x18001eb9c  mov     [rsp+arg_8], rbx
0x18001eba1  mov     [rsp+arg_10], rsi
0x18001eba6  push    rdi
0x18001eba7  push    r14
0x18001eba9  push    r15
0x18001ebab  sub     rsp, 20h
0x18001ebaf  mov     rsi, r9
0x18001ebb2  mov     r14, r8
0x18001ebb5  mov     r15, rdx
0x18001ebb8  mov     rdi, rcx
0x18001ebbb  mov     qword ptr [rcx], 0
0x18001ebc2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ebc9  mov     ecx, 60h ; '`'; unsigned __int64
0x18001ebce  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ebd3  mov     [rsp+38h+arg_0], rax
0x18001ebd8  test    rax, rax
0x18001ebdb  jnz     short loc_18001EBE7
0x18001ebdd  mov     edi, 8007000Eh
0x18001ebe2  jmp     loc_18001EC85
0x18001ebe7  mov     rcx, rax; this
0x18001ebea  call    ??0AdaptiveImage@Notifications@Internal@Windows@@QEAA@XZ; Windows::Internal::Notifications::AdaptiveImage::AdaptiveImage(void)
0x18001ebef  mov     rbx, rax
0x18001ebf2  mov     [rsp+38h+arg_0], 0
0x18001ebfb  mov     rcx, [rax+48h]; string
0x18001ebff  call    cs:__imp_WindowsDeleteString
0x18001ec05  mov     qword ptr [rbx+48h], 0
0x18001ec0d  mov     rcx, [r15]
0x18001ec10  mov     [rbx+48h], rcx
0x18001ec14  mov     qword ptr [r15], 0
0x18001ec1b  mov     rcx, [rbx+50h]; string
0x18001ec1f  call    cs:__imp_WindowsDeleteString
0x18001ec25  mov     qword ptr [rbx+50h], 0
0x18001ec2d  mov     rax, [r14]
0x18001ec30  mov     [rbx+50h], rax
0x18001ec34  mov     qword ptr [r14], 0
0x18001ec3b  mov     rcx, [rbx+58h]; string
0x18001ec3f  call    cs:__imp_WindowsDeleteString
0x18001ec45  mov     qword ptr [rbx+58h], 0
0x18001ec4d  mov     rax, [rsi]
0x18001ec50  mov     [rbx+58h], rax
0x18001ec54  mov     qword ptr [rsi], 0
0x18001ec5b  mov     rax, [rbx]
0x18001ec5e  mov     r8, rdi
0x18001ec61  lea     rdx, _GUID_9f589171_8551_48a0_922b_1abf11a66340
0x18001ec68  mov     rcx, rbx
0x18001ec6b  mov     rax, [rax]
0x18001ec6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec73  mov     edi, eax
0x18001ec75  mov     rcx, [rbx]
0x18001ec78  mov     rax, [rcx+10h]
0x18001ec7c  mov     rcx, rbx
0x18001ec7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec84  nop
0x18001ec85  lea     rcx, [rsp+38h+arg_0]
0x18001ec8a  call    ??1?$MakeAllocator@VCToastActivator_AppLaunch@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(void)
0x18001ec8f  mov     eax, edi
0x18001ec91  mov     rbx, [rsp+38h+arg_8]
0x18001ec96  mov     rsi, [rsp+38h+arg_10]
0x18001ec9b  add     rsp, 20h
0x18001ec9f  pop     r15
0x18001eca1  pop     r14
0x18001eca3  pop     rdi
0x18001eca4  retn
```
