# dllmain_crt_process_attach

- ea: `0x1800023b8`
- end: `0x1800024b2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002360`

## callees

- `0x1800023b8`
- `0x1800026f4`
- `0x180002734`
- `0x180002770`
- `0x180002870`
- `0x180002944`
- `0x1800029e4`
- `0x180002c6c`
- `0x180002c94`
- `0x180002cb8`
- `0x180002cc8`
- `0x180002cd4`
- `0x180003086`
- `0x180003092`
- `0x18000f010`

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
  ++dword_180015430;
  return 1;
}

```

## disassembly

```asm
0x1800023b8  push    rbx
0x1800023ba  push    rsi
0x1800023bb  push    rdi
0x1800023bc  push    r14
0x1800023be  sub     rsp, 28h
0x1800023c2  mov     rsi, rdx
0x1800023c5  mov     r14, rcx
0x1800023c8  xor     ecx, ecx
0x1800023ca  call    __scrt_initialize_crt
0x1800023cf  test    al, al
0x1800023d1  jz      loc_18000249A
0x1800023d7  call    __scrt_acquire_startup_lock
0x1800023dc  mov     bl, al
0x1800023de  mov     [rsp+48h+arg_10], al
0x1800023e2  mov     dil, 1
0x1800023e5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800023ec  jnz     loc_1800024A6
0x1800023f2  mov     cs:__scrt_current_native_startup_state, 1
0x1800023fc  call    __scrt_dllmain_before_initialize_c
0x180002401  test    al, al
0x180002403  jz      short loc_180002454
0x180002405  call    _RTC_Initialize
0x18000240a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000240f  call    __scrt_initialize_default_local_stdio_options
0x180002414  lea     rdx, __xi_z; Last
0x18000241b  lea     rcx, __xi_a; First
0x180002422  call    _initterm_e_0
0x180002427  test    eax, eax
0x180002429  jnz     short loc_180002454
0x18000242b  call    __scrt_dllmain_after_initialize_c
0x180002430  test    al, al
0x180002432  jz      short loc_180002454
0x180002434  lea     rdx, __xc_z; Last
0x18000243b  lea     rcx, __xc_a; First
0x180002442  call    _initterm_0
0x180002447  mov     cs:__scrt_current_native_startup_state, 2
0x180002451  xor     dil, dil
0x180002454  mov     cl, bl
0x180002456  call    __scrt_release_startup_lock
0x18000245b  test    dil, dil
0x18000245e  jnz     short loc_18000249A
0x180002460  call    __scrt_get_dyn_tls_init_callback
0x180002465  mov     rbx, rax
0x180002468  cmp     qword ptr [rax], 0
0x18000246c  jz      short loc_18000248D
0x18000246e  mov     rcx, rax
0x180002471  call    __scrt_is_nonwritable_in_current_image
0x180002476  test    al, al
0x180002478  jz      short loc_18000248D
0x18000247a  mov     r8, rsi
0x18000247d  mov     edx, 2
0x180002482  mov     rcx, r14
0x180002485  mov     rax, [rbx]
0x180002488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000248d  inc     cs:dword_180015430
0x180002493  mov     eax, 1
0x180002498  jmp     short loc_18000249C
0x18000249a  xor     eax, eax
0x18000249c  add     rsp, 28h
0x1800024a0  pop     r14
0x1800024a2  pop     rdi
0x1800024a3  pop     rsi
0x1800024a4  pop     rbx
0x1800024a5  retn
0x1800024a6  mov     ecx, 7
0x1800024ab  call    __scrt_fastfail
0x18000e4dc  push    rbp
0x18000e4de  sub     rsp, 20h
0x18000e4e2  mov     rbp, rdx
0x18000e4e5  mov     cl, [rbp+60h]
0x18000e4e8  add     rsp, 20h
0x18000e4ec  pop     rbp
0x18000e4ed  jmp     __scrt_release_startup_lock
```
