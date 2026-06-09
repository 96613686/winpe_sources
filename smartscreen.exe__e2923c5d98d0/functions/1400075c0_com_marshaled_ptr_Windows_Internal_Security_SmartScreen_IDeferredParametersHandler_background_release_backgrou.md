# com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IDeferredParametersHandler>::background_release::~background_release(void)

- ea: `0x1400075c0`
- end: `0x14000768b`
- name: `??1background_release@?$marshaled_ptr@UIDeferredParametersHandler@SmartScreen@Security@Internal@Windows@@@com@@QEAA@XZ`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140007508`
- `0x140037fe0`
- `0x140063dac`

## callees

- `0x140005e4c`
- `0x140006f80`
- `0x1400075c0`
- `0x140007694`
- `0x1400076f0`
- `0x140017738`
- `0x140025f70`
- `0x140068010`

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
0x1400075c0  mov     r11, rsp
0x1400075c3  mov     [r11+10h], rbx
0x1400075c7  push    rdi
0x1400075c8  sub     rsp, 50h
0x1400075cc  mov     rdi, rcx
0x1400075cf  mov     qword ptr [r11-38h], 0
0x1400075d7  lea     rax, [r11-38h]
0x1400075db  cmp     rax, rcx
0x1400075de  jz      short loc_1400075EE
0x1400075e0  mov     rax, [rcx]
0x1400075e3  mov     [r11-38h], rax
0x1400075e7  mov     qword ptr [rcx], 0
0x1400075ee  mov     ecx, 120h; Size
0x1400075f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400075f8  lea     rdx, [rsp+58h+var_38]
0x1400075fd  mov     rcx, rax
0x140007600  call    ??$?0V?$_Fake_no_copy_callable_adapter@V_lambda_9d7f763b99b7c374f9ee56fb1eaa22c6_@@V?$ComPtr@UIAgileReference@@@WRL@Microsoft@@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_9d7f763b99b7c374f9ee56fb1eaa22c6_@@V?$ComPtr@UIAgileReference@@@WRL@Microsoft@@@1@@Z; std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<_lambda_9d7f763b99b7c374f9ee56fb1eaa22c6_,Microsoft::WRL::ComPtr<IAgileReference>> &&)
0x140007605  mov     rbx, rax
0x140007608  mov     [rsp+58h+var_28], rax
0x14000760d  mov     [rsp+58h+var_20], 0
0x140007612  lea     rcx, [rsp+58h+var_38]; void *
0x140007617  call    ??1?$iterable@PEAUIAppxPackage@SmartScreen@Security@Internal@Windows@@@rt@windows@@QEAA@XZ; windows::rt::iterable<Windows::Internal::Security::SmartScreen::IAppxPackage *>::~iterable<Windows::Internal::Security::SmartScreen::IAppxPackage *>(void)
0x14000761c  test    rbx, rbx
0x14000761f  jnz     short loc_14000762A
0x140007621  lea     ecx, [rbx+4]
0x140007624  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14000762a  mov     [rsp+58h+var_18], 1
0x14000762f  lock inc dword ptr [rbx+8]
0x140007633  lea     rcx, [rsp+58h+var_28]
0x140007638  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x14000763d  or      eax, 0FFFFFFFFh
0x140007640  lock xadd [rbx+8], eax
0x140007645  cmp     eax, 1
0x140007648  jnz     short loc_140007679
0x14000764a  mov     rcx, [rbx+0C8h]
0x140007651  test    rcx, rcx
0x140007654  jz      short loc_140007666
0x140007656  mov     rax, [rcx]
0x140007659  mov     rdx, rbx
0x14000765c  mov     rax, [rax]
0x14000765f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007664  jmp     short loc_140007679
0x140007666  mov     rax, [rbx]
0x140007669  mov     edx, 1
0x14000766e  mov     rcx, rbx
0x140007671  mov     rax, [rax]
0x140007674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007679  mov     rcx, rdi
0x14000767c  mov     rbx, [rsp+58h+arg_8]
0x140007681  add     rsp, 50h
0x140007685  pop     rdi
0x140007686  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
