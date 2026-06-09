# dllmain_crt_process_attach

- ea: `0x1800012d8`
- end: `0x1800013d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x1800012d8`
- `0x1800016d0`
- `0x1800016f8`
- `0x18000171c`
- `0x18000175c`
- `0x180001798`
- `0x180001898`
- `0x18000196c`
- `0x180001a0c`
- `0x180001ac8`
- `0x180001ad8`
- `0x180001ae4`
- `0x180001e36`
- `0x180001e42`
- `0x18002b010`

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
  ++dword_180032290;
  return 1;
}

```

## disassembly

```asm
0x1800012d8  push    rbx
0x1800012da  push    rsi
0x1800012db  push    rdi
0x1800012dc  push    r14
0x1800012de  sub     rsp, 28h
0x1800012e2  mov     rsi, rdx
0x1800012e5  mov     r14, rcx
0x1800012e8  xor     ecx, ecx
0x1800012ea  call    __scrt_initialize_crt
0x1800012ef  test    al, al
0x1800012f1  jz      loc_1800013BA
0x1800012f7  call    __scrt_acquire_startup_lock
0x1800012fc  mov     bl, al
0x1800012fe  mov     [rsp+48h+arg_10], al
0x180001302  mov     dil, 1
0x180001305  cmp     cs:__scrt_current_native_startup_state, 0
0x18000130c  jnz     loc_1800013C6
0x180001312  mov     cs:__scrt_current_native_startup_state, 1
0x18000131c  call    __scrt_dllmain_before_initialize_c
0x180001321  test    al, al
0x180001323  jz      short loc_180001374
0x180001325  call    _RTC_Initialize
0x18000132a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000132f  call    __scrt_initialize_default_local_stdio_options
0x180001334  lea     rdx, __xi_z; Last
0x18000133b  lea     rcx, __xi_a; First
0x180001342  call    _initterm_e_0
0x180001347  test    eax, eax
0x180001349  jnz     short loc_180001374
0x18000134b  call    __scrt_dllmain_after_initialize_c
0x180001350  test    al, al
0x180001352  jz      short loc_180001374
0x180001354  lea     rdx, __xc_z; Last
0x18000135b  lea     rcx, __xc_a; First
0x180001362  call    _initterm_0
0x180001367  mov     cs:__scrt_current_native_startup_state, 2
0x180001371  xor     dil, dil
0x180001374  mov     cl, bl
0x180001376  call    __scrt_release_startup_lock
0x18000137b  test    dil, dil
0x18000137e  jnz     short loc_1800013BA
0x180001380  call    __scrt_get_dyn_tls_init_callback
0x180001385  mov     rbx, rax
0x180001388  cmp     qword ptr [rax], 0
0x18000138c  jz      short loc_1800013AD
0x18000138e  mov     rcx, rax
0x180001391  call    __scrt_is_nonwritable_in_current_image
0x180001396  test    al, al
0x180001398  jz      short loc_1800013AD
0x18000139a  mov     r8, rsi
0x18000139d  mov     edx, 2
0x1800013a2  mov     rcx, r14
0x1800013a5  mov     rax, [rbx]
0x1800013a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ad  inc     cs:dword_180032290
0x1800013b3  mov     eax, 1
0x1800013b8  jmp     short loc_1800013BC
0x1800013ba  xor     eax, eax
0x1800013bc  add     rsp, 28h
0x1800013c0  pop     r14
0x1800013c2  pop     rdi
0x1800013c3  pop     rsi
0x1800013c4  pop     rbx
0x1800013c5  retn
0x1800013c6  mov     ecx, 7
0x1800013cb  call    __scrt_fastfail
0x18002a0fc  push    rbp
0x18002a0fe  sub     rsp, 20h
0x18002a102  mov     rbp, rdx
0x18002a105  mov     cl, [rbp+60h]
0x18002a108  add     rsp, 20h
0x18002a10c  pop     rbp
0x18002a10d  jmp     __scrt_release_startup_lock
```
