# dllmain_crt_process_attach

- ea: `0x180006308`
- end: `0x180006402`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800062b0`

## callees

- `0x180006308`
- `0x180006700`
- `0x180006728`
- `0x18000674c`
- `0x18000678c`
- `0x1800067c8`
- `0x1800068c8`
- `0x18000699c`
- `0x180006a3c`
- `0x180006a98`
- `0x180006aa8`
- `0x180006ab4`
- `0x180006e26`
- `0x180006e32`
- `0x180018010`

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
  ++dword_180027110;
  return 1;
}

```

## disassembly

```asm
0x180006308  push    rbx
0x18000630a  push    rsi
0x18000630b  push    rdi
0x18000630c  push    r14
0x18000630e  sub     rsp, 28h
0x180006312  mov     rsi, rdx
0x180006315  mov     r14, rcx
0x180006318  xor     ecx, ecx
0x18000631a  call    __scrt_initialize_crt
0x18000631f  test    al, al
0x180006321  jz      loc_1800063EA
0x180006327  call    __scrt_acquire_startup_lock
0x18000632c  mov     bl, al
0x18000632e  mov     [rsp+48h+arg_10], al
0x180006332  mov     dil, 1
0x180006335  cmp     cs:__scrt_current_native_startup_state, 0
0x18000633c  jnz     loc_1800063F6
0x180006342  mov     cs:__scrt_current_native_startup_state, 1
0x18000634c  call    __scrt_dllmain_before_initialize_c
0x180006351  test    al, al
0x180006353  jz      short loc_1800063A4
0x180006355  call    _RTC_Initialize
0x18000635a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000635f  call    __scrt_initialize_default_local_stdio_options
0x180006364  lea     rdx, __xi_z; Last
0x18000636b  lea     rcx, __xi_a; First
0x180006372  call    _initterm_e_0
0x180006377  test    eax, eax
0x180006379  jnz     short loc_1800063A4
0x18000637b  call    __scrt_dllmain_after_initialize_c
0x180006380  test    al, al
0x180006382  jz      short loc_1800063A4
0x180006384  lea     rdx, __xc_z; Last
0x18000638b  lea     rcx, __xc_a; First
0x180006392  call    _initterm_0
0x180006397  mov     cs:__scrt_current_native_startup_state, 2
0x1800063a1  xor     dil, dil
0x1800063a4  mov     cl, bl
0x1800063a6  call    __scrt_release_startup_lock
0x1800063ab  test    dil, dil
0x1800063ae  jnz     short loc_1800063EA
0x1800063b0  call    __scrt_get_dyn_tls_init_callback
0x1800063b5  mov     rbx, rax
0x1800063b8  cmp     qword ptr [rax], 0
0x1800063bc  jz      short loc_1800063DD
0x1800063be  mov     rcx, rax
0x1800063c1  call    __scrt_is_nonwritable_in_current_image
0x1800063c6  test    al, al
0x1800063c8  jz      short loc_1800063DD
0x1800063ca  mov     r8, rsi
0x1800063cd  mov     edx, 2
0x1800063d2  mov     rcx, r14
0x1800063d5  mov     rax, [rbx]
0x1800063d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063dd  inc     cs:dword_180027110
0x1800063e3  mov     eax, 1
0x1800063e8  jmp     short loc_1800063EC
0x1800063ea  xor     eax, eax
0x1800063ec  add     rsp, 28h
0x1800063f0  pop     r14
0x1800063f2  pop     rdi
0x1800063f3  pop     rsi
0x1800063f4  pop     rbx
0x1800063f5  retn
0x1800063f6  mov     ecx, 7
0x1800063fb  call    __scrt_fastfail
0x180017d12  push    rbp
0x180017d14  sub     rsp, 20h
0x180017d18  mov     rbp, rdx
0x180017d1b  mov     cl, [rbp+60h]
0x180017d1e  add     rsp, 20h
0x180017d22  pop     rbp
0x180017d23  jmp     __scrt_release_startup_lock
```
