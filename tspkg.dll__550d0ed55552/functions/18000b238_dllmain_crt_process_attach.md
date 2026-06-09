# dllmain_crt_process_attach

- ea: `0x18000b238`
- end: `0x18000b332`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000b1e0`

## callees

- `0x18000b238`
- `0x18000b574`
- `0x18000b5b4`
- `0x18000b5f0`
- `0x18000b6f0`
- `0x18000b7c4`
- `0x18000b864`
- `0x18000ba48`
- `0x18000ba70`
- `0x18000ba94`
- `0x18000baa4`
- `0x18000bab0`
- `0x18000c05c`
- `0x18000c068`
- `0x18001d010`

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
  ++dword_180025410;
  return 1;
}

```

## disassembly

```asm
0x18000b238  push    rbx
0x18000b23a  push    rsi
0x18000b23b  push    rdi
0x18000b23c  push    r14
0x18000b23e  sub     rsp, 28h
0x18000b242  mov     rsi, rdx
0x18000b245  mov     r14, rcx
0x18000b248  xor     ecx, ecx
0x18000b24a  call    __scrt_initialize_crt
0x18000b24f  test    al, al
0x18000b251  jz      loc_18000B31A
0x18000b257  call    __scrt_acquire_startup_lock
0x18000b25c  mov     bl, al
0x18000b25e  mov     [rsp+48h+arg_10], al
0x18000b262  mov     dil, 1
0x18000b265  cmp     cs:__scrt_current_native_startup_state, 0
0x18000b26c  jnz     loc_18000B326
0x18000b272  mov     cs:__scrt_current_native_startup_state, 1
0x18000b27c  call    __scrt_dllmain_before_initialize_c
0x18000b281  test    al, al
0x18000b283  jz      short loc_18000B2D4
0x18000b285  call    _RTC_Initialize
0x18000b28a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000b28f  call    __scrt_initialize_default_local_stdio_options
0x18000b294  lea     rdx, __xi_z; Last
0x18000b29b  lea     rcx, __xi_a; First
0x18000b2a2  call    _initterm_e_0
0x18000b2a7  test    eax, eax
0x18000b2a9  jnz     short loc_18000B2D4
0x18000b2ab  call    __scrt_dllmain_after_initialize_c
0x18000b2b0  test    al, al
0x18000b2b2  jz      short loc_18000B2D4
0x18000b2b4  lea     rdx, __xc_z; Last
0x18000b2bb  lea     rcx, __xc_a; First
0x18000b2c2  call    _initterm_0
0x18000b2c7  mov     cs:__scrt_current_native_startup_state, 2
0x18000b2d1  xor     dil, dil
0x18000b2d4  mov     cl, bl
0x18000b2d6  call    __scrt_release_startup_lock
0x18000b2db  test    dil, dil
0x18000b2de  jnz     short loc_18000B31A
0x18000b2e0  call    __scrt_get_dyn_tls_init_callback
0x18000b2e5  mov     rbx, rax
0x18000b2e8  cmp     qword ptr [rax], 0
0x18000b2ec  jz      short loc_18000B30D
0x18000b2ee  mov     rcx, rax
0x18000b2f1  call    __scrt_is_nonwritable_in_current_image
0x18000b2f6  test    al, al
0x18000b2f8  jz      short loc_18000B30D
0x18000b2fa  mov     r8, rsi
0x18000b2fd  mov     edx, 2
0x18000b302  mov     rcx, r14
0x18000b305  mov     rax, [rbx]
0x18000b308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30d  inc     cs:dword_180025410
0x18000b313  mov     eax, 1
0x18000b318  jmp     short loc_18000B31C
0x18000b31a  xor     eax, eax
0x18000b31c  add     rsp, 28h
0x18000b320  pop     r14
0x18000b322  pop     rdi
0x18000b323  pop     rsi
0x18000b324  pop     rbx
0x18000b325  retn
0x18000b326  mov     ecx, 7
0x18000b32b  call    __scrt_fastfail
0x18001c6bc  push    rbp
0x18001c6be  sub     rsp, 20h
0x18001c6c2  mov     rbp, rdx
0x18001c6c5  mov     cl, [rbp+60h]
0x18001c6c8  add     rsp, 20h
0x18001c6cc  pop     rbp
0x18001c6cd  jmp     __scrt_release_startup_lock
```
