# dllmain_crt_process_attach

- ea: `0x18001fbe8`
- end: `0x18001fce2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001fb90`

## callees

- `0x18001fbe8`
- `0x18001ff24`
- `0x18001ff64`
- `0x18001ffa0`
- `0x1800200a0`
- `0x180020174`
- `0x180020214`
- `0x18002073c`
- `0x180020764`
- `0x180020788`
- `0x180020798`
- `0x1800207a4`
- `0x180020c06`
- `0x180020c12`
- `0x180032010`

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
  ++dword_1800443F0;
  return 1;
}

```

## disassembly

```asm
0x18001fbe8  push    rbx
0x18001fbea  push    rsi
0x18001fbeb  push    rdi
0x18001fbec  push    r14
0x18001fbee  sub     rsp, 28h
0x18001fbf2  mov     rsi, rdx
0x18001fbf5  mov     r14, rcx
0x18001fbf8  xor     ecx, ecx
0x18001fbfa  call    __scrt_initialize_crt
0x18001fbff  test    al, al
0x18001fc01  jz      loc_18001FCCA
0x18001fc07  call    __scrt_acquire_startup_lock
0x18001fc0c  mov     bl, al
0x18001fc0e  mov     [rsp+48h+arg_10], al
0x18001fc12  mov     dil, 1
0x18001fc15  cmp     cs:__scrt_current_native_startup_state, 0
0x18001fc1c  jnz     loc_18001FCD6
0x18001fc22  mov     cs:__scrt_current_native_startup_state, 1
0x18001fc2c  call    __scrt_dllmain_before_initialize_c
0x18001fc31  test    al, al
0x18001fc33  jz      short loc_18001FC84
0x18001fc35  call    _RTC_Initialize
0x18001fc3a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001fc3f  call    __scrt_initialize_default_local_stdio_options
0x18001fc44  lea     rdx, __xi_z; Last
0x18001fc4b  lea     rcx, __xi_a; First
0x18001fc52  call    _initterm_e_0
0x18001fc57  test    eax, eax
0x18001fc59  jnz     short loc_18001FC84
0x18001fc5b  call    __scrt_dllmain_after_initialize_c
0x18001fc60  test    al, al
0x18001fc62  jz      short loc_18001FC84
0x18001fc64  lea     rdx, __xc_z; Last
0x18001fc6b  lea     rcx, __xc_a; First
0x18001fc72  call    _initterm_0
0x18001fc77  mov     cs:__scrt_current_native_startup_state, 2
0x18001fc81  xor     dil, dil
0x18001fc84  mov     cl, bl
0x18001fc86  call    __scrt_release_startup_lock
0x18001fc8b  test    dil, dil
0x18001fc8e  jnz     short loc_18001FCCA
0x18001fc90  call    __scrt_get_dyn_tls_init_callback
0x18001fc95  mov     rbx, rax
0x18001fc98  cmp     qword ptr [rax], 0
0x18001fc9c  jz      short loc_18001FCBD
0x18001fc9e  mov     rcx, rax
0x18001fca1  call    __scrt_is_nonwritable_in_current_image
0x18001fca6  test    al, al
0x18001fca8  jz      short loc_18001FCBD
0x18001fcaa  mov     r8, rsi
0x18001fcad  mov     edx, 2
0x18001fcb2  mov     rcx, r14
0x18001fcb5  mov     rax, [rbx]
0x18001fcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcbd  inc     cs:dword_1800443F0
0x18001fcc3  mov     eax, 1
0x18001fcc8  jmp     short loc_18001FCCC
0x18001fcca  xor     eax, eax
0x18001fccc  add     rsp, 28h
0x18001fcd0  pop     r14
0x18001fcd2  pop     rdi
0x18001fcd3  pop     rsi
0x18001fcd4  pop     rbx
0x18001fcd5  retn
0x18001fcd6  mov     ecx, 7
0x18001fcdb  call    __scrt_fastfail
0x18003179c  push    rbp
0x18003179e  sub     rsp, 20h
0x1800317a2  mov     rbp, rdx
0x1800317a5  mov     cl, [rbp+60h]
0x1800317a8  add     rsp, 20h
0x1800317ac  pop     rbp
0x1800317ad  jmp     __scrt_release_startup_lock
```
