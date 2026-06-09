# dllmain_crt_process_attach

- ea: `0x180001b98`
- end: `0x180001c92`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001b40`

## callees

- `0x180001b98`
- `0x180001fb4`
- `0x180001ff4`
- `0x180002030`
- `0x180002130`
- `0x180002204`
- `0x1800022a4`
- `0x180002534`
- `0x18000255c`
- `0x180002580`
- `0x180002590`
- `0x18000259c`
- `0x180002956`
- `0x180002962`
- `0x180037010`

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
  ++dword_1800485D0;
  return 1;
}

```

## disassembly

```asm
0x180001b98  push    rbx
0x180001b9a  push    rsi
0x180001b9b  push    rdi
0x180001b9c  push    r14
0x180001b9e  sub     rsp, 28h
0x180001ba2  mov     rsi, rdx
0x180001ba5  mov     r14, rcx
0x180001ba8  xor     ecx, ecx
0x180001baa  call    __scrt_initialize_crt
0x180001baf  test    al, al
0x180001bb1  jz      loc_180001C7A
0x180001bb7  call    __scrt_acquire_startup_lock
0x180001bbc  mov     bl, al
0x180001bbe  mov     [rsp+48h+arg_10], al
0x180001bc2  mov     dil, 1
0x180001bc5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001bcc  jnz     loc_180001C86
0x180001bd2  mov     cs:__scrt_current_native_startup_state, 1
0x180001bdc  call    __scrt_dllmain_before_initialize_c
0x180001be1  test    al, al
0x180001be3  jz      short loc_180001C34
0x180001be5  call    _RTC_Initialize
0x180001bea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001bef  call    __scrt_initialize_default_local_stdio_options
0x180001bf4  lea     rdx, __xi_z; Last
0x180001bfb  lea     rcx, __xi_a; First
0x180001c02  call    _initterm_e_0
0x180001c07  test    eax, eax
0x180001c09  jnz     short loc_180001C34
0x180001c0b  call    __scrt_dllmain_after_initialize_c
0x180001c10  test    al, al
0x180001c12  jz      short loc_180001C34
0x180001c14  lea     rdx, __xc_z; Last
0x180001c1b  lea     rcx, __xc_a; First
0x180001c22  call    _initterm_0
0x180001c27  mov     cs:__scrt_current_native_startup_state, 2
0x180001c31  xor     dil, dil
0x180001c34  mov     cl, bl
0x180001c36  call    __scrt_release_startup_lock
0x180001c3b  test    dil, dil
0x180001c3e  jnz     short loc_180001C7A
0x180001c40  call    __scrt_get_dyn_tls_init_callback
0x180001c45  mov     rbx, rax
0x180001c48  cmp     qword ptr [rax], 0
0x180001c4c  jz      short loc_180001C6D
0x180001c4e  mov     rcx, rax
0x180001c51  call    __scrt_is_nonwritable_in_current_image
0x180001c56  test    al, al
0x180001c58  jz      short loc_180001C6D
0x180001c5a  mov     r8, rsi
0x180001c5d  mov     edx, 2
0x180001c62  mov     rcx, r14
0x180001c65  mov     rax, [rbx]
0x180001c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6d  inc     cs:dword_1800485D0
0x180001c73  mov     eax, 1
0x180001c78  jmp     short loc_180001C7C
0x180001c7a  xor     eax, eax
0x180001c7c  add     rsp, 28h
0x180001c80  pop     r14
0x180001c82  pop     rdi
0x180001c83  pop     rsi
0x180001c84  pop     rbx
0x180001c85  retn
0x180001c86  mov     ecx, 7
0x180001c8b  call    __scrt_fastfail
0x180034b9c  push    rbp
0x180034b9e  sub     rsp, 20h
0x180034ba2  mov     rbp, rdx
0x180034ba5  mov     cl, [rbp+60h]
0x180034ba8  add     rsp, 20h
0x180034bac  pop     rbp
0x180034bad  jmp     __scrt_release_startup_lock
```
