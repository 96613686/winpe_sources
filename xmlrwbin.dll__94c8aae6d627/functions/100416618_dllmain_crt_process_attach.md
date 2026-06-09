# dllmain_crt_process_attach

- ea: `0x100416618`
- end: `0x10041672e`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1004165c0`

## callees

- `0x100416618`
- `0x100416cb8`
- `0x100416d00`
- `0x100416d24`
- `0x100416d64`
- `0x100416da0`
- `0x100416ec4`
- `0x100416fa8`
- `0x100417048`
- `0x100417104`
- `0x100417124`
- `0x100417278`
- `0x100419f08`
- `0x100419f50`
- `0x100424580`

## pseudocode

```c
__int64 dllmain_crt_process_attach()
{
  char v0; // bl
  char v1; // di
  __int64 v2; // rcx
  _QWORD *dyn_tls_init_callback; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v0 = _scrt_acquire_startup_lock();
  v1 = 1;
  if ( _scrt_current_native_startup_state )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x10041672ELL);
  }
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v1 = 0;
      }
    }
  }
  LOBYTE(v2) = v0;
  _scrt_release_startup_lock(v2);
  if ( v1 )
    return 0;
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback();
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
  }
  ++dword_100434CD4;
  return 1;
}

```

## disassembly

```asm
0x100416618  mov     [rsp+arg_0], rbx
0x10041661d  mov     [rsp+arg_8], rsi
0x100416622  mov     [rsp+arg_18], rdi
0x100416627  push    r14
0x100416629  sub     rsp, 20h
0x10041662d  mov     rsi, rdx
0x100416630  mov     r14, rcx
0x100416633  xor     ecx, ecx
0x100416635  call    __scrt_initialize_crt
0x10041663a  test    al, al
0x10041663c  jz      loc_10041670A
0x100416642  call    __scrt_acquire_startup_lock
0x100416647  mov     bl, al
0x100416649  mov     [rsp+28h+arg_10], al
0x10041664d  mov     dil, 1
0x100416650  cmp     cs:__scrt_current_native_startup_state, 0
0x100416657  jnz     loc_100416722
0x10041665d  mov     cs:__scrt_current_native_startup_state, 1
0x100416667  call    __scrt_dllmain_before_initialize_c
0x10041666c  test    al, al
0x10041666e  jz      short loc_1004166BF
0x100416670  call    _RTC_Initialize
0x100416675  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x10041667a  call    __scrt_initialize_default_local_stdio_options
0x10041667f  lea     rdx, __xi_z; Last
0x100416686  lea     rcx, __xi_a; First
0x10041668d  call    _initterm_e
0x100416692  test    eax, eax
0x100416694  jnz     short loc_1004166BF
0x100416696  call    __scrt_dllmain_after_initialize_c
0x10041669b  test    al, al
0x10041669d  jz      short loc_1004166BF
0x10041669f  lea     rdx, __xc_z; Last
0x1004166a6  lea     rcx, __xc_a; First
0x1004166ad  call    _initterm
0x1004166b2  mov     cs:__scrt_current_native_startup_state, 2
0x1004166bc  xor     dil, dil
0x1004166bf  mov     cl, bl
0x1004166c1  call    __scrt_release_startup_lock
0x1004166c6  test    dil, dil
0x1004166c9  jnz     short loc_10041670A
0x1004166cb  call    __scrt_get_dyn_tls_init_callback
0x1004166d0  mov     rbx, rax
0x1004166d3  cmp     qword ptr [rax], 0
0x1004166d7  jz      short loc_1004166FD
0x1004166d9  mov     rcx, rax
0x1004166dc  call    __scrt_is_nonwritable_in_current_image
0x1004166e1  test    al, al
0x1004166e3  jz      short loc_1004166FD
0x1004166e5  mov     r8, rsi
0x1004166e8  mov     edx, 2
0x1004166ed  mov     rcx, r14
0x1004166f0  mov     rax, [rbx]
0x1004166f3  mov     r9, cs:__guard_dispatch_icall_fptr
0x1004166fa  call    r9 ; _guard_dispatch_icall_nop
0x1004166fd  inc     cs:dword_100434CD4
0x100416703  mov     eax, 1
0x100416708  jmp     short loc_10041670C
0x10041670a  xor     eax, eax
0x10041670c  mov     rbx, [rsp+28h+arg_0]
0x100416711  mov     rsi, [rsp+28h+arg_8]
0x100416716  mov     rdi, [rsp+28h+arg_18]
0x10041671b  add     rsp, 20h
0x10041671f  pop     r14
0x100416721  retn
0x100416722  mov     ecx, 7
0x100416727  call    __scrt_fastfail
0x10041672c  nop
0x10041672d  int     3; Trap to Debugger
0x100425070  push    rbp
0x100425072  sub     rsp, 20h
0x100425076  mov     rbp, rdx
0x100425079  mov     cl, [rbp+40h]
0x10042507c  add     rsp, 20h
0x100425080  pop     rbp
0x100425081  jmp     __scrt_release_startup_lock
```
