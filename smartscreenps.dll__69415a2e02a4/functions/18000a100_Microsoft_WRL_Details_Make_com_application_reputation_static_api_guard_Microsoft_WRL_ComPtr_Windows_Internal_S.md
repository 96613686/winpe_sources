# Microsoft::WRL::Details::Make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)

- ea: `0x18000a100`
- end: `0x18000a209`
- name: `??$Make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@12@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@12@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a7e0`

## callees

- `0x1800019d0`
- `0x18000a100`
- `0x18000a89c`
- `0x18000a98c`
- `0x18000ab0c`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 *__fastcall Microsoft::WRL::Details::Make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  void *v6; // rax
  void *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdi
  _QWORD v11[5]; // [rsp+30h] [rbp-71h] BYREF
  _BYTE v12[64]; // [rsp+58h] [rbp-49h] BYREF
  _BYTE v13[80]; // [rsp+98h] [rbp-9h] BYREF
  __int64 v14; // [rsp+120h] [rbp+7Fh] BYREF

  *a1 = 0;
  v6 = operator new(0x100u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v11[0] = v6;
  v11[1] = v6;
  if ( v6 )
  {
    v11[2] = v6;
    v11[3] = &v14;
    v8 = *a3;
    v14 = v8;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v11[4] = v12;
    std::function<void (void)>::function<void (void)>(v12, a2);
    std::function<void (void)>::function<void (void)>(v13, a2 + 64);
    v13[64] = *(_BYTE *)(a2 + 128);
    v9 = com::application_reputation_static::application_reputation_static(v7, v12, &v14);
    if ( *a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v9;
    v11[0] = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>(v11);
  return a1;
}

```

## disassembly

```asm
0x18000a100  mov     rax, rsp
0x18000a103  mov     [rax+10h], rbx
0x18000a107  mov     [rax+18h], rsi
0x18000a10b  mov     [rax+8], rcx
0x18000a10f  push    rbp
0x18000a110  push    rdi
0x18000a111  push    r14
0x18000a113  lea     rbp, [rax-5Fh]
0x18000a117  sub     rsp, 0E0h
0x18000a11e  mov     rsi, r8
0x18000a121  mov     r14, rdx
0x18000a124  mov     rbx, rcx
0x18000a127  mov     [rbp+57h+var_D0], 0
0x18000a12e  mov     qword ptr [rcx], 0
0x18000a135  mov     [rbp+57h+var_D0], 1
0x18000a13c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a143  mov     ecx, 100h; unsigned __int64
0x18000a148  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a14d  mov     rdi, rax
0x18000a150  mov     [rbp+57h+var_C8], rax
0x18000a154  mov     [rbp+57h+var_C0], rax
0x18000a158  test    rax, rax
0x18000a15b  jz      loc_18000A1E4
0x18000a161  mov     [rbp+57h+var_B8], rax
0x18000a165  lea     rax, [rbp+57h+arg_18]
0x18000a169  mov     [rbp+57h+var_B0], rax
0x18000a16d  mov     rcx, [rsi]
0x18000a170  mov     [rbp+57h+arg_18], rcx
0x18000a174  test    rcx, rcx
0x18000a177  jz      short loc_18000A186
0x18000a179  mov     rax, [rcx]
0x18000a17c  mov     rax, [rax+8]
0x18000a180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a185  nop
0x18000a186  lea     rax, [rbp+57h+var_A0]
0x18000a18a  mov     [rbp+57h+var_A8], rax
0x18000a18e  mov     rdx, r14
0x18000a191  lea     rcx, [rbp+57h+var_A0]
0x18000a195  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18000a19a  nop
0x18000a19b  lea     rdx, [r14+40h]
0x18000a19f  lea     rcx, [rbp+57h+var_60]
0x18000a1a3  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18000a1a8  mov     al, [r14+80h]
0x18000a1af  mov     [rbp+57h+var_20], al
0x18000a1b2  lea     r8, [rbp+57h+arg_18]
0x18000a1b6  lea     rdx, [rbp+57h+var_A0]
0x18000a1ba  mov     rcx, rdi
0x18000a1bd  call    ??0application_reputation_static@com@@QEAA@Vapi_guard@@V?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@Z; com::application_reputation_static::application_reputation_static(api_guard,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService>)
0x18000a1c2  mov     rdi, rax
0x18000a1c5  mov     rcx, [rbx]
0x18000a1c8  test    rcx, rcx
0x18000a1cb  jz      short loc_18000A1D9
0x18000a1cd  mov     rdx, [rcx]
0x18000a1d0  mov     rax, [rdx+10h]
0x18000a1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d9  mov     [rbx], rdi
0x18000a1dc  mov     [rbp+57h+var_C8], 0
0x18000a1e4  lea     rcx, [rbp+57h+var_C8]
0x18000a1e8  call    ??1?$MakeAllocator@Vapplication_reputation_static@com@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>(void)
0x18000a1ed  mov     rax, rbx
0x18000a1f0  lea     r11, [rsp+0F0h+var_10]
0x18000a1f8  mov     rbx, [r11+28h]
0x18000a1fc  mov     rsi, [r11+30h]
0x18000a200  mov     rsp, r11
0x18000a203  pop     r14
0x18000a205  pop     rdi
0x18000a206  pop     rbp
0x18000a207  retn
```
