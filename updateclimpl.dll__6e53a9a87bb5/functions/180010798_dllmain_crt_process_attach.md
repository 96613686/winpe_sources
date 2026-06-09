# dllmain_crt_process_attach

- ea: `0x180010798`
- end: `0x1800108a9`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180010740`

## callees

- `0x180010340`
- `0x180010380`
- `0x1800103bc`
- `0x1800104e0`
- `0x1800105b4`
- `0x180010654`
- `0x180010798`
- `0x180010f40`
- `0x180011178`
- `0x1800111b0`
- `0x1800111d4`
- `0x1800111e4`
- `0x1800144c6`
- `0x1800144d2`
- `0x1800148e0`

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
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1800108A9LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( _scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( _scrt_dllmain_after_initialize_c() )
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
  ++dword_18001F884;
  return 1;
}

```

## disassembly

```asm
0x180010798  mov     [rsp+arg_0], rbx
0x18001079d  mov     [rsp+arg_8], rsi
0x1800107a2  mov     [rsp+arg_18], rdi
0x1800107a7  push    r14
0x1800107a9  sub     rsp, 20h
0x1800107ad  mov     rsi, rdx
0x1800107b0  mov     r14, rcx
0x1800107b3  xor     ecx, ecx
0x1800107b5  call    __scrt_initialize_crt
0x1800107ba  test    al, al
0x1800107bc  jz      loc_180010885
0x1800107c2  call    __scrt_acquire_startup_lock
0x1800107c7  mov     bl, al
0x1800107c9  mov     [rsp+28h+arg_10], al
0x1800107cd  mov     dil, 1
0x1800107d0  cmp     cs:__scrt_current_native_startup_state, 0
0x1800107d7  jnz     loc_18001089D
0x1800107dd  mov     cs:__scrt_current_native_startup_state, 1
0x1800107e7  call    __scrt_dllmain_before_initialize_c
0x1800107ec  test    al, al
0x1800107ee  jz      short loc_18001083F
0x1800107f0  call    _RTC_Initialize
0x1800107f5  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800107fa  call    __scrt_initialize_default_local_stdio_options
0x1800107ff  lea     rdx, __xi_z; Last
0x180010806  lea     rcx, __xi_a; First
0x18001080d  call    _initterm_e_0
0x180010812  test    eax, eax
0x180010814  jnz     short loc_18001083F
0x180010816  call    __scrt_dllmain_after_initialize_c
0x18001081b  test    al, al
0x18001081d  jz      short loc_18001083F
0x18001081f  lea     rdx, __xc_z; Last
0x180010826  lea     rcx, __xc_a; First
0x18001082d  call    _initterm_0
0x180010832  mov     cs:__scrt_current_native_startup_state, 2
0x18001083c  xor     dil, dil
0x18001083f  mov     cl, bl
0x180010841  call    __scrt_release_startup_lock
0x180010846  test    dil, dil
0x180010849  jnz     short loc_180010885
0x18001084b  call    __scrt_get_dyn_tls_init_callback
0x180010850  mov     rbx, rax
0x180010853  cmp     qword ptr [rax], 0
0x180010857  jz      short loc_180010878
0x180010859  mov     rcx, rax
0x18001085c  call    __scrt_is_nonwritable_in_current_image
0x180010861  test    al, al
0x180010863  jz      short loc_180010878
0x180010865  mov     r8, rsi
0x180010868  mov     edx, 2
0x18001086d  mov     rcx, r14
0x180010870  mov     rax, [rbx]
0x180010873  call    _guard_dispatch_icall
0x180010878  inc     cs:dword_18001F884
0x18001087e  mov     eax, 1
0x180010883  jmp     short loc_180010887
0x180010885  xor     eax, eax
0x180010887  mov     rbx, [rsp+28h+arg_0]
0x18001088c  mov     rsi, [rsp+28h+arg_8]
0x180010891  mov     rdi, [rsp+28h+arg_18]
0x180010896  add     rsp, 20h
0x18001089a  pop     r14
0x18001089c  retn
0x18001089d  mov     ecx, 7
0x1800108a2  call    __scrt_fastfail
0x1800108a7  nop
0x1800108a8  int     3; Trap to Debugger
0x180015e9f  push    rbp
0x180015ea1  sub     rsp, 20h
0x180015ea5  mov     rbp, rdx
0x180015ea8  mov     cl, [rbp+40h]
0x180015eab  add     rsp, 20h
0x180015eaf  pop     rbp
0x180015eb0  jmp     __scrt_release_startup_lock
```
