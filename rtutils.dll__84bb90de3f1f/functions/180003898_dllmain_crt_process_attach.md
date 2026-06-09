# dllmain_crt_process_attach

- ea: `0x180003898`
- end: `0x180003992`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003840`

## callees

- `0x180003898`
- `0x180003cbc`
- `0x180003ce4`
- `0x180003d08`
- `0x180003d48`
- `0x180003d84`
- `0x180003e84`
- `0x180003f58`
- `0x180003ff8`
- `0x180004054`
- `0x180004064`
- `0x180004070`
- `0x1800043c6`
- `0x1800043d2`
- `0x18000b010`

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
  ++dword_180010110;
  return 1;
}

```

## disassembly

```asm
0x180003898  push    rbx
0x18000389a  push    rsi
0x18000389b  push    rdi
0x18000389c  push    r14
0x18000389e  sub     rsp, 28h
0x1800038a2  mov     rsi, rdx
0x1800038a5  mov     r14, rcx
0x1800038a8  xor     ecx, ecx
0x1800038aa  call    __scrt_initialize_crt
0x1800038af  test    al, al
0x1800038b1  jz      loc_18000397A
0x1800038b7  call    __scrt_acquire_startup_lock
0x1800038bc  mov     bl, al
0x1800038be  mov     [rsp+48h+arg_10], al
0x1800038c2  mov     dil, 1
0x1800038c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800038cc  jnz     loc_180003986
0x1800038d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800038dc  call    __scrt_dllmain_before_initialize_c
0x1800038e1  test    al, al
0x1800038e3  jz      short loc_180003934
0x1800038e5  call    _RTC_Initialize
0x1800038ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800038ef  call    __scrt_initialize_default_local_stdio_options
0x1800038f4  lea     rdx, __xi_z; Last
0x1800038fb  lea     rcx, __xi_a; First
0x180003902  call    _initterm_e_0
0x180003907  test    eax, eax
0x180003909  jnz     short loc_180003934
0x18000390b  call    __scrt_dllmain_after_initialize_c
0x180003910  test    al, al
0x180003912  jz      short loc_180003934
0x180003914  lea     rdx, __xc_z; Last
0x18000391b  lea     rcx, __xc_a; First
0x180003922  call    _initterm_0
0x180003927  mov     cs:__scrt_current_native_startup_state, 2
0x180003931  xor     dil, dil
0x180003934  mov     cl, bl
0x180003936  call    __scrt_release_startup_lock
0x18000393b  test    dil, dil
0x18000393e  jnz     short loc_18000397A
0x180003940  call    __scrt_get_dyn_tls_init_callback
0x180003945  mov     rbx, rax
0x180003948  cmp     qword ptr [rax], 0
0x18000394c  jz      short loc_18000396D
0x18000394e  mov     rcx, rax
0x180003951  call    __scrt_is_nonwritable_in_current_image
0x180003956  test    al, al
0x180003958  jz      short loc_18000396D
0x18000395a  mov     r8, rsi
0x18000395d  mov     edx, 2
0x180003962  mov     rcx, r14
0x180003965  mov     rax, [rbx]
0x180003968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000396d  inc     cs:dword_180010110
0x180003973  mov     eax, 1
0x180003978  jmp     short loc_18000397C
0x18000397a  xor     eax, eax
0x18000397c  add     rsp, 28h
0x180003980  pop     r14
0x180003982  pop     rdi
0x180003983  pop     rsi
0x180003984  pop     rbx
0x180003985  retn
0x180003986  mov     ecx, 7
0x18000398b  call    __scrt_fastfail
0x18000a7dc  push    rbp
0x18000a7de  sub     rsp, 20h
0x18000a7e2  mov     rbp, rdx
0x18000a7e5  mov     cl, [rbp+60h]
0x18000a7e8  add     rsp, 20h
0x18000a7ec  pop     rbp
0x18000a7ed  jmp     __scrt_release_startup_lock
```
