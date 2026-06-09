# dllmain_crt_process_attach

- ea: `0x180024738`
- end: `0x180024832`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800246e0`

## callees

- `0x180024738`
- `0x180024aac`
- `0x180024aec`
- `0x180024b28`
- `0x180024c28`
- `0x180024cfc`
- `0x180024d9c`
- `0x180025058`
- `0x180025080`
- `0x1800250a4`
- `0x1800250b4`
- `0x1800250c0`
- `0x180025416`
- `0x180025422`
- `0x18003c010`

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
  ++dword_18004B290;
  return 1;
}

```

## disassembly

```asm
0x180024738  push    rbx
0x18002473a  push    rsi
0x18002473b  push    rdi
0x18002473c  push    r14
0x18002473e  sub     rsp, 28h
0x180024742  mov     rsi, rdx
0x180024745  mov     r14, rcx
0x180024748  xor     ecx, ecx
0x18002474a  call    __scrt_initialize_crt
0x18002474f  test    al, al
0x180024751  jz      loc_18002481A
0x180024757  call    __scrt_acquire_startup_lock
0x18002475c  mov     bl, al
0x18002475e  mov     [rsp+48h+arg_10], al
0x180024762  mov     dil, 1
0x180024765  cmp     cs:__scrt_current_native_startup_state, 0
0x18002476c  jnz     loc_180024826
0x180024772  mov     cs:__scrt_current_native_startup_state, 1
0x18002477c  call    __scrt_dllmain_before_initialize_c
0x180024781  test    al, al
0x180024783  jz      short loc_1800247D4
0x180024785  call    _RTC_Initialize
0x18002478a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18002478f  call    __scrt_initialize_default_local_stdio_options
0x180024794  lea     rdx, __xi_z; Last
0x18002479b  lea     rcx, __xi_a; First
0x1800247a2  call    _initterm_e_0
0x1800247a7  test    eax, eax
0x1800247a9  jnz     short loc_1800247D4
0x1800247ab  call    __scrt_dllmain_after_initialize_c
0x1800247b0  test    al, al
0x1800247b2  jz      short loc_1800247D4
0x1800247b4  lea     rdx, __xc_z; Last
0x1800247bb  lea     rcx, __xc_a; First
0x1800247c2  call    _initterm_0
0x1800247c7  mov     cs:__scrt_current_native_startup_state, 2
0x1800247d1  xor     dil, dil
0x1800247d4  mov     cl, bl
0x1800247d6  call    __scrt_release_startup_lock
0x1800247db  test    dil, dil
0x1800247de  jnz     short loc_18002481A
0x1800247e0  call    __scrt_get_dyn_tls_init_callback
0x1800247e5  mov     rbx, rax
0x1800247e8  cmp     qword ptr [rax], 0
0x1800247ec  jz      short loc_18002480D
0x1800247ee  mov     rcx, rax
0x1800247f1  call    __scrt_is_nonwritable_in_current_image
0x1800247f6  test    al, al
0x1800247f8  jz      short loc_18002480D
0x1800247fa  mov     r8, rsi
0x1800247fd  mov     edx, 2
0x180024802  mov     rcx, r14
0x180024805  mov     rax, [rbx]
0x180024808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002480d  inc     cs:dword_18004B290
0x180024813  mov     eax, 1
0x180024818  jmp     short loc_18002481C
0x18002481a  xor     eax, eax
0x18002481c  add     rsp, 28h
0x180024820  pop     r14
0x180024822  pop     rdi
0x180024823  pop     rsi
0x180024824  pop     rbx
0x180024825  retn
0x180024826  mov     ecx, 7
0x18002482b  call    __scrt_fastfail
0x18003a807  push    rbp
0x18003a809  sub     rsp, 20h
0x18003a80d  mov     rbp, rdx
0x18003a810  mov     cl, [rbp+60h]
0x18003a813  add     rsp, 20h
0x18003a817  pop     rbp
0x18003a818  jmp     __scrt_release_startup_lock
```
