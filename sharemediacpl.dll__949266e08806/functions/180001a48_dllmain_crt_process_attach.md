# dllmain_crt_process_attach

- ea: `0x180001a48`
- end: `0x180001b42`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800019f0`

## callees

- `0x180001a48`
- `0x180001db0`
- `0x180001df0`
- `0x180001e2c`
- `0x180001f2c`
- `0x180002000`
- `0x1800020a0`
- `0x1800024ac`
- `0x1800024d4`
- `0x1800024f8`
- `0x180002508`
- `0x180002514`
- `0x180002846`
- `0x180002852`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 v6; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v8)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v5 = 0;
      }
    }
  }
  LOBYTE(v6) = v4;
  _scrt_release_startup_lock(v6);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v8 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v8)(a1, 2, a2);
  }
  ++dword_18002A490;
  return 1;
}

```

## disassembly

```asm
0x180001a48  push    rbx
0x180001a4a  push    rsi
0x180001a4b  push    rdi
0x180001a4c  push    r14
0x180001a4e  sub     rsp, 28h
0x180001a52  mov     rsi, rdx
0x180001a55  mov     r14, rcx
0x180001a58  xor     ecx, ecx
0x180001a5a  call    __scrt_initialize_crt
0x180001a5f  test    al, al
0x180001a61  jz      loc_180001B2A
0x180001a67  call    __scrt_acquire_startup_lock
0x180001a6c  mov     bl, al
0x180001a6e  mov     [rsp+48h+arg_10], al
0x180001a72  mov     dil, 1
0x180001a75  cmp     cs:__scrt_current_native_startup_state, 0
0x180001a7c  jnz     loc_180001B36
0x180001a82  mov     cs:__scrt_current_native_startup_state, 1
0x180001a8c  call    __scrt_dllmain_before_initialize_c
0x180001a91  test    al, al
0x180001a93  jz      short loc_180001AE4
0x180001a95  call    _RTC_Initialize
0x180001a9a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001a9f  call    __scrt_initialize_default_local_stdio_options
0x180001aa4  lea     rdx, __xi_z; Last
0x180001aab  lea     rcx, __xi_a; First
0x180001ab2  call    _initterm_e_0
0x180001ab7  test    eax, eax
0x180001ab9  jnz     short loc_180001AE4
0x180001abb  call    __scrt_dllmain_after_initialize_c
0x180001ac0  test    al, al
0x180001ac2  jz      short loc_180001AE4
0x180001ac4  lea     rdx, __xc_z; Last
0x180001acb  lea     rcx, __xc_a; First
0x180001ad2  call    _initterm_0
0x180001ad7  mov     cs:__scrt_current_native_startup_state, 2
0x180001ae1  xor     dil, dil
0x180001ae4  mov     cl, bl
0x180001ae6  call    __scrt_release_startup_lock
0x180001aeb  test    dil, dil
0x180001aee  jnz     short loc_180001B2A
0x180001af0  call    __scrt_get_dyn_tls_init_callback
0x180001af5  mov     rbx, rax
0x180001af8  cmp     qword ptr [rax], 0
0x180001afc  jz      short loc_180001B1D
0x180001afe  mov     rcx, rax
0x180001b01  call    __scrt_is_nonwritable_in_current_image
0x180001b06  test    al, al
0x180001b08  jz      short loc_180001B1D
0x180001b0a  mov     r8, rsi
0x180001b0d  mov     edx, 2
0x180001b12  mov     rcx, r14
0x180001b15  mov     rax, [rbx]
0x180001b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b1d  inc     cs:dword_18002A490
0x180001b23  mov     eax, 1
0x180001b28  jmp     short loc_180001B2C
0x180001b2a  xor     eax, eax
0x180001b2c  add     rsp, 28h
0x180001b30  pop     r14
0x180001b32  pop     rdi
0x180001b33  pop     rsi
0x180001b34  pop     rbx
0x180001b35  retn
0x180001b36  mov     ecx, 7
0x180001b3b  call    __scrt_fastfail
0x18001d35c  push    rbp
0x18001d35e  sub     rsp, 20h
0x18001d362  mov     rbp, rdx
0x18001d365  mov     cl, [rbp+60h]
0x18001d368  add     rsp, 20h
0x18001d36c  pop     rbp
0x18001d36d  jmp     __scrt_release_startup_lock
```
