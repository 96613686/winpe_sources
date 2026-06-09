# dllmain_crt_process_attach

- ea: `0x180005368`
- end: `0x180005462`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180005310`

## callees

- `0x180005368`
- `0x1800056a4`
- `0x1800056e4`
- `0x180005720`
- `0x180005820`
- `0x1800058f4`
- `0x180005994`
- `0x180005b38`
- `0x180005b60`
- `0x180005b84`
- `0x180005b94`
- `0x180005ba0`
- `0x180005f06`
- `0x180005f12`
- `0x180017010`

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
  ++dword_180022370;
  return 1;
}

```

## disassembly

```asm
0x180005368  push    rbx
0x18000536a  push    rsi
0x18000536b  push    rdi
0x18000536c  push    r14
0x18000536e  sub     rsp, 28h
0x180005372  mov     rsi, rdx
0x180005375  mov     r14, rcx
0x180005378  xor     ecx, ecx
0x18000537a  call    __scrt_initialize_crt
0x18000537f  test    al, al
0x180005381  jz      loc_18000544A
0x180005387  call    __scrt_acquire_startup_lock
0x18000538c  mov     bl, al
0x18000538e  mov     [rsp+48h+arg_10], al
0x180005392  mov     dil, 1
0x180005395  cmp     cs:__scrt_current_native_startup_state, 0
0x18000539c  jnz     loc_180005456
0x1800053a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800053ac  call    __scrt_dllmain_before_initialize_c
0x1800053b1  test    al, al
0x1800053b3  jz      short loc_180005404
0x1800053b5  call    _RTC_Initialize
0x1800053ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800053bf  call    __scrt_initialize_default_local_stdio_options
0x1800053c4  lea     rdx, __xi_z; Last
0x1800053cb  lea     rcx, __xi_a; First
0x1800053d2  call    _initterm_e_0
0x1800053d7  test    eax, eax
0x1800053d9  jnz     short loc_180005404
0x1800053db  call    __scrt_dllmain_after_initialize_c
0x1800053e0  test    al, al
0x1800053e2  jz      short loc_180005404
0x1800053e4  lea     rdx, __xc_z; Last
0x1800053eb  lea     rcx, __xc_a; First
0x1800053f2  call    _initterm_0
0x1800053f7  mov     cs:__scrt_current_native_startup_state, 2
0x180005401  xor     dil, dil
0x180005404  mov     cl, bl
0x180005406  call    __scrt_release_startup_lock
0x18000540b  test    dil, dil
0x18000540e  jnz     short loc_18000544A
0x180005410  call    __scrt_get_dyn_tls_init_callback
0x180005415  mov     rbx, rax
0x180005418  cmp     qword ptr [rax], 0
0x18000541c  jz      short loc_18000543D
0x18000541e  mov     rcx, rax
0x180005421  call    __scrt_is_nonwritable_in_current_image
0x180005426  test    al, al
0x180005428  jz      short loc_18000543D
0x18000542a  mov     r8, rsi
0x18000542d  mov     edx, 2
0x180005432  mov     rcx, r14
0x180005435  mov     rax, [rbx]
0x180005438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543d  inc     cs:dword_180022370
0x180005443  mov     eax, 1
0x180005448  jmp     short loc_18000544C
0x18000544a  xor     eax, eax
0x18000544c  add     rsp, 28h
0x180005450  pop     r14
0x180005452  pop     rdi
0x180005453  pop     rsi
0x180005454  pop     rbx
0x180005455  retn
0x180005456  mov     ecx, 7
0x18000545b  call    __scrt_fastfail
0x180016ae0  push    rbp
0x180016ae2  sub     rsp, 20h
0x180016ae6  mov     rbp, rdx
0x180016ae9  mov     cl, [rbp+60h]
0x180016aec  add     rsp, 20h
0x180016af0  pop     rbp
0x180016af1  jmp     __scrt_release_startup_lock
```
