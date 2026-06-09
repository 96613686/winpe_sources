# dllmain_crt_process_attach

- ea: `0x18000c678`
- end: `0x18000c772`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000c620`

## callees

- `0x18000c678`
- `0x18000caa0`
- `0x18000cae0`
- `0x18000cb1c`
- `0x18000cc1c`
- `0x18000ccf0`
- `0x18000cd90`
- `0x18000cfbc`
- `0x18000cfe4`
- `0x18000d008`
- `0x18000d018`
- `0x18000d024`
- `0x18000d356`
- `0x18000d362`
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
  ++dword_180025A70;
  return 1;
}

```

## disassembly

```asm
0x18000c678  push    rbx
0x18000c67a  push    rsi
0x18000c67b  push    rdi
0x18000c67c  push    r14
0x18000c67e  sub     rsp, 28h
0x18000c682  mov     rsi, rdx
0x18000c685  mov     r14, rcx
0x18000c688  xor     ecx, ecx
0x18000c68a  call    __scrt_initialize_crt
0x18000c68f  test    al, al
0x18000c691  jz      loc_18000C75A
0x18000c697  call    __scrt_acquire_startup_lock
0x18000c69c  mov     bl, al
0x18000c69e  mov     [rsp+48h+arg_10], al
0x18000c6a2  mov     dil, 1
0x18000c6a5  cmp     cs:__scrt_current_native_startup_state, 0
0x18000c6ac  jnz     loc_18000C766
0x18000c6b2  mov     cs:__scrt_current_native_startup_state, 1
0x18000c6bc  call    __scrt_dllmain_before_initialize_c
0x18000c6c1  test    al, al
0x18000c6c3  jz      short loc_18000C714
0x18000c6c5  call    _RTC_Initialize
0x18000c6ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000c6cf  call    __scrt_initialize_default_local_stdio_options
0x18000c6d4  lea     rdx, __xi_z; Last
0x18000c6db  lea     rcx, __xi_a; First
0x18000c6e2  call    _initterm_e_0
0x18000c6e7  test    eax, eax
0x18000c6e9  jnz     short loc_18000C714
0x18000c6eb  call    __scrt_dllmain_after_initialize_c
0x18000c6f0  test    al, al
0x18000c6f2  jz      short loc_18000C714
0x18000c6f4  lea     rdx, __xc_z; Last
0x18000c6fb  lea     rcx, __xc_a; First
0x18000c702  call    _initterm_0
0x18000c707  mov     cs:__scrt_current_native_startup_state, 2
0x18000c711  xor     dil, dil
0x18000c714  mov     cl, bl
0x18000c716  call    __scrt_release_startup_lock
0x18000c71b  test    dil, dil
0x18000c71e  jnz     short loc_18000C75A
0x18000c720  call    __scrt_get_dyn_tls_init_callback
0x18000c725  mov     rbx, rax
0x18000c728  cmp     qword ptr [rax], 0
0x18000c72c  jz      short loc_18000C74D
0x18000c72e  mov     rcx, rax
0x18000c731  call    __scrt_is_nonwritable_in_current_image
0x18000c736  test    al, al
0x18000c738  jz      short loc_18000C74D
0x18000c73a  mov     r8, rsi
0x18000c73d  mov     edx, 2
0x18000c742  mov     rcx, r14
0x18000c745  mov     rax, [rbx]
0x18000c748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c74d  inc     cs:dword_180025A70
0x18000c753  mov     eax, 1
0x18000c758  jmp     short loc_18000C75C
0x18000c75a  xor     eax, eax
0x18000c75c  add     rsp, 28h
0x18000c760  pop     r14
0x18000c762  pop     rdi
0x18000c763  pop     rsi
0x18000c764  pop     rbx
0x18000c765  retn
0x18000c766  mov     ecx, 7
0x18000c76b  call    __scrt_fastfail
0x18001aa71  push    rbp
0x18001aa73  sub     rsp, 20h
0x18001aa77  mov     rbp, rdx
0x18001aa7a  mov     cl, [rbp+60h]
0x18001aa7d  add     rsp, 20h
0x18001aa81  pop     rbp
0x18001aa82  jmp     __scrt_release_startup_lock
```
