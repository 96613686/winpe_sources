# dllmain_crt_process_attach

- ea: `0x180042c98`
- end: `0x180042da9`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180042c40`

## callees

- `0x1800427f4`
- `0x180042834`
- `0x180042870`
- `0x180042994`
- `0x180042a68`
- `0x180042b08`
- `0x180042c98`
- `0x1800437a4`
- `0x1800439d8`
- `0x180043a00`
- `0x180043a24`
- `0x180043a34`
- `0x180047640`
- `0x18004764c`
- `0x180047a30`

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
    JUMPOUT(0x180042DA9LL);
  }
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
  ++dword_180062C84;
  return 1;
}

```

## disassembly

```asm
0x180042c98  mov     [rsp+arg_0], rbx
0x180042c9d  mov     [rsp+arg_8], rsi
0x180042ca2  mov     [rsp+arg_18], rdi
0x180042ca7  push    r14
0x180042ca9  sub     rsp, 20h
0x180042cad  mov     rsi, rdx
0x180042cb0  mov     r14, rcx
0x180042cb3  xor     ecx, ecx
0x180042cb5  call    __scrt_initialize_crt
0x180042cba  test    al, al
0x180042cbc  jz      loc_180042D85
0x180042cc2  call    __scrt_acquire_startup_lock
0x180042cc7  mov     bl, al
0x180042cc9  mov     [rsp+28h+arg_10], al
0x180042ccd  mov     dil, 1
0x180042cd0  cmp     cs:__scrt_current_native_startup_state, 0
0x180042cd7  jnz     loc_180042D9D
0x180042cdd  mov     cs:__scrt_current_native_startup_state, 1
0x180042ce7  call    __scrt_dllmain_before_initialize_c
0x180042cec  test    al, al
0x180042cee  jz      short loc_180042D3F
0x180042cf0  call    _RTC_Initialize
0x180042cf5  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180042cfa  call    __scrt_initialize_default_local_stdio_options
0x180042cff  lea     rdx, __xi_z; Last
0x180042d06  lea     rcx, __xi_a; First
0x180042d0d  call    _initterm_e_0
0x180042d12  test    eax, eax
0x180042d14  jnz     short loc_180042D3F
0x180042d16  call    __scrt_dllmain_after_initialize_c
0x180042d1b  test    al, al
0x180042d1d  jz      short loc_180042D3F
0x180042d1f  lea     rdx, __xc_z; Last
0x180042d26  lea     rcx, __xc_a; First
0x180042d2d  call    _initterm_0
0x180042d32  mov     cs:__scrt_current_native_startup_state, 2
0x180042d3c  xor     dil, dil
0x180042d3f  mov     cl, bl
0x180042d41  call    __scrt_release_startup_lock
0x180042d46  test    dil, dil
0x180042d49  jnz     short loc_180042D85
0x180042d4b  call    __scrt_get_dyn_tls_init_callback
0x180042d50  mov     rbx, rax
0x180042d53  cmp     qword ptr [rax], 0
0x180042d57  jz      short loc_180042D78
0x180042d59  mov     rcx, rax
0x180042d5c  call    __scrt_is_nonwritable_in_current_image
0x180042d61  test    al, al
0x180042d63  jz      short loc_180042D78
0x180042d65  mov     r8, rsi
0x180042d68  mov     edx, 2
0x180042d6d  mov     rcx, r14
0x180042d70  mov     rax, [rbx]
0x180042d73  call    _guard_dispatch_icall
0x180042d78  inc     cs:dword_180062C84
0x180042d7e  mov     eax, 1
0x180042d83  jmp     short loc_180042D87
0x180042d85  xor     eax, eax
0x180042d87  mov     rbx, [rsp+28h+arg_0]
0x180042d8c  mov     rsi, [rsp+28h+arg_8]
0x180042d91  mov     rdi, [rsp+28h+arg_18]
0x180042d96  add     rsp, 20h
0x180042d9a  pop     r14
0x180042d9c  retn
0x180042d9d  mov     ecx, 7
0x180042da2  call    __scrt_fastfail
0x180042da7  nop
0x180042da8  int     3; Trap to Debugger
0x18004d315  push    rbp
0x18004d317  sub     rsp, 20h
0x18004d31b  mov     rbp, rdx
0x18004d31e  mov     cl, [rbp+40h]
0x18004d321  add     rsp, 20h
0x18004d325  pop     rbp
0x18004d326  jmp     __scrt_release_startup_lock
```
