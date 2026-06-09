# dllmain_crt_process_attach

- ea: `0x1800204a8`
- end: `0x1800205a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180020450`

## callees

- `0x1800204a8`
- `0x180020d78`
- `0x180020da0`
- `0x180020dc4`
- `0x180020e04`
- `0x180020e40`
- `0x180020f40`
- `0x180021014`
- `0x1800210b4`
- `0x180021170`
- `0x180021180`
- `0x18002118c`
- `0x1800212ae`
- `0x1800212ba`
- `0x18004c010`

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
  ++dword_18006AB10;
  return 1;
}

```

## disassembly

```asm
0x1800204a8  push    rbx
0x1800204aa  push    rsi
0x1800204ab  push    rdi
0x1800204ac  push    r14
0x1800204ae  sub     rsp, 28h
0x1800204b2  mov     rsi, rdx
0x1800204b5  mov     r14, rcx
0x1800204b8  xor     ecx, ecx
0x1800204ba  call    __scrt_initialize_crt
0x1800204bf  test    al, al
0x1800204c1  jz      loc_18002058A
0x1800204c7  call    __scrt_acquire_startup_lock
0x1800204cc  mov     bl, al
0x1800204ce  mov     [rsp+48h+arg_10], al
0x1800204d2  mov     dil, 1
0x1800204d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800204dc  jnz     loc_180020596
0x1800204e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800204ec  call    __scrt_dllmain_before_initialize_c
0x1800204f1  test    al, al
0x1800204f3  jz      short loc_180020544
0x1800204f5  call    _RTC_Initialize
0x1800204fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800204ff  call    __scrt_initialize_default_local_stdio_options
0x180020504  lea     rdx, __xi_z; Last
0x18002050b  lea     rcx, __xi_a; First
0x180020512  call    _initterm_e_0
0x180020517  test    eax, eax
0x180020519  jnz     short loc_180020544
0x18002051b  call    __scrt_dllmain_after_initialize_c
0x180020520  test    al, al
0x180020522  jz      short loc_180020544
0x180020524  lea     rdx, __xc_z; Last
0x18002052b  lea     rcx, __xc_a; First
0x180020532  call    _initterm_0
0x180020537  mov     cs:__scrt_current_native_startup_state, 2
0x180020541  xor     dil, dil
0x180020544  mov     cl, bl
0x180020546  call    __scrt_release_startup_lock
0x18002054b  test    dil, dil
0x18002054e  jnz     short loc_18002058A
0x180020550  call    __scrt_get_dyn_tls_init_callback
0x180020555  mov     rbx, rax
0x180020558  cmp     qword ptr [rax], 0
0x18002055c  jz      short loc_18002057D
0x18002055e  mov     rcx, rax
0x180020561  call    __scrt_is_nonwritable_in_current_image
0x180020566  test    al, al
0x180020568  jz      short loc_18002057D
0x18002056a  mov     r8, rsi
0x18002056d  mov     edx, 2
0x180020572  mov     rcx, r14
0x180020575  mov     rax, [rbx]
0x180020578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002057d  inc     cs:dword_18006AB10
0x180020583  mov     eax, 1
0x180020588  jmp     short loc_18002058C
0x18002058a  xor     eax, eax
0x18002058c  add     rsp, 28h
0x180020590  pop     r14
0x180020592  pop     rdi
0x180020593  pop     rsi
0x180020594  pop     rbx
0x180020595  retn
0x180020596  mov     ecx, 7
0x18002059b  call    __scrt_fastfail
0x18004a85b  push    rbp
0x18004a85d  sub     rsp, 20h
0x18004a861  mov     rbp, rdx
0x18004a864  mov     cl, [rbp+60h]
0x18004a867  add     rsp, 20h
0x18004a86b  pop     rbp
0x18004a86c  jmp     __scrt_release_startup_lock
```
