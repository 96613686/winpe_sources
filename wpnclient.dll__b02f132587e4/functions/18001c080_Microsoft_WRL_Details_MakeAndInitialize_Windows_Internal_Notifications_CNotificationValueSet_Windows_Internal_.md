# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::CNotificationValueSet,Windows::Internal::Notifications::INotificationValueSet,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE,Windows::Internal::Notifications::IAdaptiveNotification * &>(Windows::Internal::Notifications::INotificationValueSet * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE &&,Windows::Internal::Notifications::IAdaptiveNotification * &)

- ea: `0x18001c080`
- end: `0x18001c197`
- name: `??$MakeAndInitialize@VCNotificationValueSet@Notifications@Internal@Windows@@UINotificationValueSet@234@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@W4WPN_NOTIFICATION_TYPE@234@AEAPEAUIAdaptiveNotification@234@@Details@WRL@Microsoft@@YAJPEAPEAUINotificationValueSet@Notifications@Internal@Windows@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@56@$$QEAW4WPN_NOTIFICATION_TYPE@456@AEAPEAUIAdaptiveNotification@456@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025040`

## callees

- `0x1800068f0`
- `0x180014d74`
- `0x180014fb4`
- `0x18001bf84`
- `0x18001c080`
- `0x18001c9bc`
- `0x180020350`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::CNotificationValueSet,Windows::Internal::Notifications::INotificationValueSet,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &,enum Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE,Windows::Internal::Notifications::IAdaptiveNotification * &>(
        _QWORD *a1,
        __int64 *a2,
        int *a3,
        __int64 *a4)
{
  Windows::Internal::Notifications::CNotificationValueSet *v8; // rax
  unsigned int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdi
  int v13; // ebp
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  Windows::Internal::Notifications::CNotificationValueSet *v18; // [rsp+20h] [rbp-38h] BYREF
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF

  *a1 = 0;
  v8 = (Windows::Internal::Notifications::CNotificationValueSet *)operator new(
                                                                    0xC8u,
                                                                    (const struct std::nothrow_t *)std::nothrow);
  v18 = v8;
  if ( v8 )
  {
    v10 = Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(v8);
    v19 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::Notifications::CNotificationValueSet>::Attach(&v19, v10);
    v18 = 0;
    v11 = v19;
    v12 = *a4;
    v13 = *a3;
    v14 = *a2;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v14 + 2 * v15) );
    std::wstring::_Assign<unsigned short>(v19 + 80, v14, v15);
    *(_DWORD *)(v11 + 144) = v13;
    if ( *(_QWORD *)(v11 + 160) != v12 )
    {
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v16 = *(_QWORD *)(v11 + 160);
      *(_QWORD *)(v11 + 160) = v12;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v9 = Microsoft::WRL::ComPtr<Windows::Internal::Notifications::CNotificationValueSet>::CopyTo<Windows::Internal::Notifications::INotificationValueSet>(
           &v19,
           a1);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  else
  {
    v9 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(&v18);
  return v9;
}

```

## disassembly

```asm
0x18001c080  mov     [rsp+arg_8], rbx
0x18001c085  mov     [rsp+arg_10], rbp
0x18001c08a  push    rsi
0x18001c08b  push    rdi
0x18001c08c  push    r12
0x18001c08e  push    r14
0x18001c090  push    r15
0x18001c092  sub     rsp, 30h
0x18001c096  mov     rdi, r9
0x18001c099  mov     r14, r8
0x18001c09c  mov     r15, rdx
0x18001c09f  mov     rsi, rcx
0x18001c0a2  xor     r12d, r12d
0x18001c0a5  mov     [rcx], r12
0x18001c0a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c0af  mov     ecx, 0C8h; unsigned __int64
0x18001c0b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c0b9  mov     [rsp+58h+var_38], rax
0x18001c0be  test    rax, rax
0x18001c0c1  jnz     short loc_18001C0CD
0x18001c0c3  mov     edi, 8007000Eh
0x18001c0c8  jmp     loc_18001C174
0x18001c0cd  mov     rcx, rax; this
0x18001c0d0  call    ??0CNotificationValueSet@Notifications@Internal@Windows@@QEAA@XZ; Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(void)
0x18001c0d5  mov     [rsp+58h+arg_0], r12
0x18001c0da  mov     rdx, rax
0x18001c0dd  lea     rcx, [rsp+58h+arg_0]
0x18001c0e2  call    ?Attach@?$ComPtr@VCNotificationValueSet@Notifications@Internal@Windows@@@WRL@Microsoft@@QEAAXPEAVCNotificationValueSet@Notifications@Internal@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Notifications::CNotificationValueSet>::Attach(Windows::Internal::Notifications::CNotificationValueSet *)
0x18001c0e7  mov     [rsp+58h+var_38], r12
0x18001c0ec  mov     rbx, [rsp+58h+arg_0]
0x18001c0f1  mov     rdi, [rdi]
0x18001c0f4  mov     ebp, [r14]
0x18001c0f7  mov     rdx, [r15]
0x18001c0fa  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c0fe  inc     r8
0x18001c101  cmp     [rdx+r8*2], r12w
0x18001c106  jnz     short loc_18001C0FE
0x18001c108  lea     rcx, [rbx+50h]
0x18001c10c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001c111  mov     [rbx+90h], ebp
0x18001c117  cmp     [rbx+0A0h], rdi
0x18001c11e  jz      short loc_18001C155
0x18001c120  test    rdi, rdi
0x18001c123  jz      short loc_18001C135
0x18001c125  mov     rax, [rdi]
0x18001c128  mov     rcx, rdi
0x18001c12b  mov     rax, [rax+8]
0x18001c12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c134  nop
0x18001c135  mov     rcx, [rbx+0A0h]
0x18001c13c  mov     [rbx+0A0h], rdi
0x18001c143  test    rcx, rcx
0x18001c146  jz      short loc_18001C155
0x18001c148  mov     rax, [rcx]
0x18001c14b  mov     rax, [rax+10h]
0x18001c14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c154  nop
0x18001c155  mov     rdx, rsi
0x18001c158  lea     rcx, [rsp+58h+arg_0]
0x18001c15d  call    ??$CopyTo@UINotificationValueSet@Notifications@Internal@Windows@@@?$ComPtr@VCNotificationValueSet@Notifications@Internal@Windows@@@WRL@Microsoft@@QEBAJPEAPEAUINotificationValueSet@Notifications@Internal@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Notifications::CNotificationValueSet>::CopyTo<Windows::Internal::Notifications::INotificationValueSet>(Windows::Internal::Notifications::INotificationValueSet * *)
0x18001c162  mov     edi, eax
0x18001c164  mov     rdx, [rbx]
0x18001c167  mov     rcx, rbx
0x18001c16a  mov     rax, [rdx+10h]
0x18001c16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c173  nop
0x18001c174  lea     rcx, [rsp+58h+var_38]
0x18001c179  call    ??1?$MakeAllocator@VCToastActivator_AppLaunch@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(void)
0x18001c17e  mov     eax, edi
0x18001c180  mov     rbx, [rsp+58h+arg_8]
0x18001c185  mov     rbp, [rsp+58h+arg_10]
0x18001c18a  add     rsp, 30h
0x18001c18e  pop     r15
0x18001c190  pop     r14
0x18001c192  pop     r12
0x18001c194  pop     rdi
0x18001c195  pop     rsi
0x18001c196  retn
```
