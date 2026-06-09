# dllmain_crt_process_attach

- ea: `0x18000e328`
- end: `0x18000e422`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000e2d0`

## callees

- `0x18000e328`
- `0x18000e69c`
- `0x18000e6dc`
- `0x18000e718`
- `0x18000e818`
- `0x18000e8ec`
- `0x18000e98c`
- `0x18000eb04`
- `0x18000eb2c`
- `0x18000eb50`
- `0x18000eb60`
- `0x18000eb6c`
- `0x18000eee6`
- `0x18000eef2`
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
  ++dword_180029410;
  return 1;
}

```

## disassembly

```asm
0x18000e328  push    rbx
0x18000e32a  push    rsi
0x18000e32b  push    rdi
0x18000e32c  push    r14
0x18000e32e  sub     rsp, 28h
0x18000e332  mov     rsi, rdx
0x18000e335  mov     r14, rcx
0x18000e338  xor     ecx, ecx
0x18000e33a  call    __scrt_initialize_crt
0x18000e33f  test    al, al
0x18000e341  jz      loc_18000E40A
0x18000e347  call    __scrt_acquire_startup_lock
0x18000e34c  mov     bl, al
0x18000e34e  mov     [rsp+48h+arg_10], al
0x18000e352  mov     dil, 1
0x18000e355  cmp     cs:__scrt_current_native_startup_state, 0
0x18000e35c  jnz     loc_18000E416
0x18000e362  mov     cs:__scrt_current_native_startup_state, 1
0x18000e36c  call    __scrt_dllmain_before_initialize_c
0x18000e371  test    al, al
0x18000e373  jz      short loc_18000E3C4
0x18000e375  call    _RTC_Initialize
0x18000e37a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000e37f  call    __scrt_initialize_default_local_stdio_options
0x18000e384  lea     rdx, __xi_z; Last
0x18000e38b  lea     rcx, __xi_a; First
0x18000e392  call    _initterm_e_0
0x18000e397  test    eax, eax
0x18000e399  jnz     short loc_18000E3C4
0x18000e39b  call    __scrt_dllmain_after_initialize_c
0x18000e3a0  test    al, al
0x18000e3a2  jz      short loc_18000E3C4
0x18000e3a4  lea     rdx, __xc_z; Last
0x18000e3ab  lea     rcx, __xc_a; First
0x18000e3b2  call    _initterm_0
0x18000e3b7  mov     cs:__scrt_current_native_startup_state, 2
0x18000e3c1  xor     dil, dil
0x18000e3c4  mov     cl, bl
0x18000e3c6  call    __scrt_release_startup_lock
0x18000e3cb  test    dil, dil
0x18000e3ce  jnz     short loc_18000E40A
0x18000e3d0  call    __scrt_get_dyn_tls_init_callback
0x18000e3d5  mov     rbx, rax
0x18000e3d8  cmp     qword ptr [rax], 0
0x18000e3dc  jz      short loc_18000E3FD
0x18000e3de  mov     rcx, rax
0x18000e3e1  call    __scrt_is_nonwritable_in_current_image
0x18000e3e6  test    al, al
0x18000e3e8  jz      short loc_18000E3FD
0x18000e3ea  mov     r8, rsi
0x18000e3ed  mov     edx, 2
0x18000e3f2  mov     rcx, r14
0x18000e3f5  mov     rax, [rbx]
0x18000e3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3fd  inc     cs:dword_180029410
0x18000e403  mov     eax, 1
0x18000e408  jmp     short loc_18000E40C
0x18000e40a  xor     eax, eax
0x18000e40c  add     rsp, 28h
0x18000e410  pop     r14
0x18000e412  pop     rdi
0x18000e413  pop     rsi
0x18000e414  pop     rbx
0x18000e415  retn
0x18000e416  mov     ecx, 7
0x18000e41b  call    __scrt_fastfail
0x18001c9a6  push    rbp
0x18001c9a8  sub     rsp, 20h
0x18001c9ac  mov     rbp, rdx
0x18001c9af  mov     cl, [rbp+60h]
0x18001c9b2  add     rsp, 20h
0x18001c9b6  pop     rbp
0x18001c9b7  jmp     __scrt_release_startup_lock
```
