# dllmain_crt_process_attach

- ea: `0x180001b18`
- end: `0x180001c12`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001ac0`

## callees

- `0x180001b18`
- `0x180001ef8`
- `0x180001f38`
- `0x180001f74`
- `0x180002074`
- `0x180002148`
- `0x1800021e8`
- `0x1800023c4`
- `0x1800023ec`
- `0x180002410`
- `0x180002420`
- `0x18000242c`
- `0x180002786`
- `0x180002792`
- `0x18001b010`

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
  ++dword_180023510;
  return 1;
}

```

## disassembly

```asm
0x180001b18  push    rbx
0x180001b1a  push    rsi
0x180001b1b  push    rdi
0x180001b1c  push    r14
0x180001b1e  sub     rsp, 28h
0x180001b22  mov     rsi, rdx
0x180001b25  mov     r14, rcx
0x180001b28  xor     ecx, ecx
0x180001b2a  call    __scrt_initialize_crt
0x180001b2f  test    al, al
0x180001b31  jz      loc_180001BFA
0x180001b37  call    __scrt_acquire_startup_lock
0x180001b3c  mov     bl, al
0x180001b3e  mov     [rsp+48h+arg_10], al
0x180001b42  mov     dil, 1
0x180001b45  cmp     cs:__scrt_current_native_startup_state, 0
0x180001b4c  jnz     loc_180001C06
0x180001b52  mov     cs:__scrt_current_native_startup_state, 1
0x180001b5c  call    __scrt_dllmain_before_initialize_c
0x180001b61  test    al, al
0x180001b63  jz      short loc_180001BB4
0x180001b65  call    _RTC_Initialize
0x180001b6a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001b6f  call    __scrt_initialize_default_local_stdio_options
0x180001b74  lea     rdx, __xi_z; Last
0x180001b7b  lea     rcx, __xi_a; First
0x180001b82  call    _initterm_e_0
0x180001b87  test    eax, eax
0x180001b89  jnz     short loc_180001BB4
0x180001b8b  call    __scrt_dllmain_after_initialize_c
0x180001b90  test    al, al
0x180001b92  jz      short loc_180001BB4
0x180001b94  lea     rdx, __xc_z; Last
0x180001b9b  lea     rcx, __xc_a; First
0x180001ba2  call    _initterm_0
0x180001ba7  mov     cs:__scrt_current_native_startup_state, 2
0x180001bb1  xor     dil, dil
0x180001bb4  mov     cl, bl
0x180001bb6  call    __scrt_release_startup_lock
0x180001bbb  test    dil, dil
0x180001bbe  jnz     short loc_180001BFA
0x180001bc0  call    __scrt_get_dyn_tls_init_callback
0x180001bc5  mov     rbx, rax
0x180001bc8  cmp     qword ptr [rax], 0
0x180001bcc  jz      short loc_180001BED
0x180001bce  mov     rcx, rax
0x180001bd1  call    __scrt_is_nonwritable_in_current_image
0x180001bd6  test    al, al
0x180001bd8  jz      short loc_180001BED
0x180001bda  mov     r8, rsi
0x180001bdd  mov     edx, 2
0x180001be2  mov     rcx, r14
0x180001be5  mov     rax, [rbx]
0x180001be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bed  inc     cs:dword_180023510
0x180001bf3  mov     eax, 1
0x180001bf8  jmp     short loc_180001BFC
0x180001bfa  xor     eax, eax
0x180001bfc  add     rsp, 28h
0x180001c00  pop     r14
0x180001c02  pop     rdi
0x180001c03  pop     rsi
0x180001c04  pop     rbx
0x180001c05  retn
0x180001c06  mov     ecx, 7
0x180001c0b  call    __scrt_fastfail
0x18001993c  push    rbp
0x18001993e  sub     rsp, 20h
0x180019942  mov     rbp, rdx
0x180019945  mov     cl, [rbp+60h]
0x180019948  add     rsp, 20h
0x18001994c  pop     rbp
0x18001994d  jmp     __scrt_release_startup_lock
```
