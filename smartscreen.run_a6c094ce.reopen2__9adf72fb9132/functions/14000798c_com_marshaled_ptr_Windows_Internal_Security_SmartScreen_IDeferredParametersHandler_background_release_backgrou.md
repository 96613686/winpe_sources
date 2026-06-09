# com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IDeferredParametersHandler>::background_release::~background_release(void)

- ea: `0x14000798c`
- end: `0x140007a57`
- name: `??1background_release@?$marshaled_ptr@UIDeferredParametersHandler@SmartScreen@Security@Internal@Windows@@@com@@QEAA@XZ`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400078d0`
- `0x140039560`
- `0x140065a6d`

## callees

- `0x1400061cc`
- `0x1400073e0`
- `0x14000798c`
- `0x140007a60`
- `0x140007ac0`
- `0x14001773c`
- `0x1400270f0`
- `0x14006a010`

## pseudocode

```c
__int64 __fastcall com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IDeferredParametersHandler>::background_release::~background_release(
        __int64 *a1)
{
  void *v2; // rax
  __int64 v3; // rbx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  __int64 v6[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  char v8; // [rsp+38h] [rbp-20h]
  char v9; // [rsp+40h] [rbp-18h]

  v6[0] = 0;
  if ( v6 != a1 )
  {
    v6[0] = *a1;
    *a1 = 0;
  }
  v2 = operator new(0x120u);
  v3 = std::_Task_async_state<void>::_Task_async_state<void>(v2, v6);
  v7 = v3;
  v8 = 0;
  windows::rt::iterable<Windows::Internal::Security::SmartScreen::IAppxPackage *>::~iterable<Windows::Internal::Security::SmartScreen::IAppxPackage *>(v6);
  if ( !v3 )
    std::_Throw_future_error2(4);
  v9 = 1;
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  std::_State_manager<int>::~_State_manager<int>(&v7);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
  {
    v4 = *(void (__fastcall ****)(_QWORD, __int64))(v3 + 200);
    if ( v4 )
      (**v4)(v4, v3);
    else
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x14000798c  mov     r11, rsp
0x14000798f  mov     [r11+10h], rbx
0x140007993  push    rdi
0x140007994  sub     rsp, 50h
0x140007998  mov     rdi, rcx
0x14000799b  mov     qword ptr [r11-38h], 0
0x1400079a3  lea     rax, [r11-38h]
0x1400079a7  cmp     rax, rcx
0x1400079aa  jz      short loc_1400079BA
0x1400079ac  mov     rax, [rcx]
0x1400079af  mov     [r11-38h], rax
0x1400079b3  mov     qword ptr [rcx], 0
0x1400079ba  mov     ecx, 120h; Size
0x1400079bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400079c4  lea     rdx, [rsp+58h+var_38]
0x1400079c9  mov     rcx, rax
0x1400079cc  call    ??$?0V?$_Fake_no_copy_callable_adapter@V_lambda_9d7f763b99b7c374f9ee56fb1eaa22c6_@@V?$ComPtr@UIAgileReference@@@WRL@Microsoft@@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_9d7f763b99b7c374f9ee56fb1eaa22c6_@@V?$ComPtr@UIAgileReference@@@WRL@Microsoft@@@1@@Z; std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<_lambda_9d7f763b99b7c374f9ee56fb1eaa22c6_,Microsoft::WRL::ComPtr<IAgileReference>> &&)
0x1400079d1  mov     rbx, rax
0x1400079d4  mov     [rsp+58h+var_28], rax
0x1400079d9  mov     [rsp+58h+var_20], 0
0x1400079de  lea     rcx, [rsp+58h+var_38]; void *
0x1400079e3  call    ??1?$iterable@PEAUIAppxPackage@SmartScreen@Security@Internal@Windows@@@rt@windows@@QEAA@XZ; windows::rt::iterable<Windows::Internal::Security::SmartScreen::IAppxPackage *>::~iterable<Windows::Internal::Security::SmartScreen::IAppxPackage *>(void)
0x1400079e8  test    rbx, rbx
0x1400079eb  jnz     short loc_1400079F6
0x1400079ed  lea     ecx, [rbx+4]
0x1400079f0  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1400079f6  mov     [rsp+58h+var_18], 1
0x1400079fb  lock inc dword ptr [rbx+8]
0x1400079ff  lea     rcx, [rsp+58h+var_28]
0x140007a04  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x140007a09  or      eax, 0FFFFFFFFh
0x140007a0c  lock xadd [rbx+8], eax
0x140007a11  cmp     eax, 1
0x140007a14  jnz     short loc_140007A45
0x140007a16  mov     rcx, [rbx+0C8h]
0x140007a1d  test    rcx, rcx
0x140007a20  jz      short loc_140007A32
0x140007a22  mov     rax, [rcx]
0x140007a25  mov     rdx, rbx
0x140007a28  mov     rax, [rax]
0x140007a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a30  jmp     short loc_140007A45
0x140007a32  mov     rax, [rbx]
0x140007a35  mov     edx, 1
0x140007a3a  mov     rcx, rbx
0x140007a3d  mov     rax, [rax]
0x140007a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a45  mov     rcx, rdi
0x140007a48  mov     rbx, [rsp+58h+arg_8]
0x140007a4d  add     rsp, 50h
0x140007a51  pop     rdi
0x140007a52  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
