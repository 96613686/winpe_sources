# dllmain_crt_process_attach

- ea: `0x18000d698`
- end: `0x18000d792`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000d640`

## callees

- `0x18000d698`
- `0x18000da0c`
- `0x18000da4c`
- `0x18000da88`
- `0x18000db88`
- `0x18000dc5c`
- `0x18000dcfc`
- `0x18000de74`
- `0x18000de9c`
- `0x18000dec0`
- `0x18000ded0`
- `0x18000dedc`
- `0x18000e236`
- `0x18000e242`
- `0x18001c010`

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
  ++dword_180028310;
  return 1;
}

```

## disassembly

```asm
0x18000d698  push    rbx
0x18000d69a  push    rsi
0x18000d69b  push    rdi
0x18000d69c  push    r14
0x18000d69e  sub     rsp, 28h
0x18000d6a2  mov     rsi, rdx
0x18000d6a5  mov     r14, rcx
0x18000d6a8  xor     ecx, ecx
0x18000d6aa  call    __scrt_initialize_crt
0x18000d6af  test    al, al
0x18000d6b1  jz      loc_18000D77A
0x18000d6b7  call    __scrt_acquire_startup_lock
0x18000d6bc  mov     bl, al
0x18000d6be  mov     [rsp+48h+arg_10], al
0x18000d6c2  mov     dil, 1
0x18000d6c5  cmp     cs:__scrt_current_native_startup_state, 0
0x18000d6cc  jnz     loc_18000D786
0x18000d6d2  mov     cs:__scrt_current_native_startup_state, 1
0x18000d6dc  call    __scrt_dllmain_before_initialize_c
0x18000d6e1  test    al, al
0x18000d6e3  jz      short loc_18000D734
0x18000d6e5  call    _RTC_Initialize
0x18000d6ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000d6ef  call    __scrt_initialize_default_local_stdio_options
0x18000d6f4  lea     rdx, __xi_z; Last
0x18000d6fb  lea     rcx, __xi_a; First
0x18000d702  call    _initterm_e_0
0x18000d707  test    eax, eax
0x18000d709  jnz     short loc_18000D734
0x18000d70b  call    __scrt_dllmain_after_initialize_c
0x18000d710  test    al, al
0x18000d712  jz      short loc_18000D734
0x18000d714  lea     rdx, __xc_z; Last
0x18000d71b  lea     rcx, __xc_a; First
0x18000d722  call    _initterm_0
0x18000d727  mov     cs:__scrt_current_native_startup_state, 2
0x18000d731  xor     dil, dil
0x18000d734  mov     cl, bl
0x18000d736  call    __scrt_release_startup_lock
0x18000d73b  test    dil, dil
0x18000d73e  jnz     short loc_18000D77A
0x18000d740  call    __scrt_get_dyn_tls_init_callback
0x18000d745  mov     rbx, rax
0x18000d748  cmp     qword ptr [rax], 0
0x18000d74c  jz      short loc_18000D76D
0x18000d74e  mov     rcx, rax
0x18000d751  call    __scrt_is_nonwritable_in_current_image
0x18000d756  test    al, al
0x18000d758  jz      short loc_18000D76D
0x18000d75a  mov     r8, rsi
0x18000d75d  mov     edx, 2
0x18000d762  mov     rcx, r14
0x18000d765  mov     rax, [rbx]
0x18000d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d76d  inc     cs:dword_180028310
0x18000d773  mov     eax, 1
0x18000d778  jmp     short loc_18000D77C
0x18000d77a  xor     eax, eax
0x18000d77c  add     rsp, 28h
0x18000d780  pop     r14
0x18000d782  pop     rdi
0x18000d783  pop     rsi
0x18000d784  pop     rbx
0x18000d785  retn
0x18000d786  mov     ecx, 7
0x18000d78b  call    __scrt_fastfail
0x18001ae44  push    rbp
0x18001ae46  sub     rsp, 20h
0x18001ae4a  mov     rbp, rdx
0x18001ae4d  mov     cl, [rbp+60h]
0x18001ae50  add     rsp, 20h
0x18001ae54  pop     rbp
0x18001ae55  jmp     __scrt_release_startup_lock
```
