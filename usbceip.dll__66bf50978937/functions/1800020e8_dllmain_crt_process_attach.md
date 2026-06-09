# dllmain_crt_process_attach

- ea: `0x1800020e8`
- end: `0x1800021e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002090`

## callees

- `0x1800020e8`
- `0x18000256c`
- `0x180002594`
- `0x1800025b8`
- `0x1800025f8`
- `0x180002634`
- `0x180002734`
- `0x180002808`
- `0x1800028a8`
- `0x180002964`
- `0x180002974`
- `0x180002980`
- `0x180002d66`
- `0x180002d72`
- `0x180011010`

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
  ++dword_18001C3B0;
  return 1;
}

```

## disassembly

```asm
0x1800020e8  push    rbx
0x1800020ea  push    rsi
0x1800020eb  push    rdi
0x1800020ec  push    r14
0x1800020ee  sub     rsp, 28h
0x1800020f2  mov     rsi, rdx
0x1800020f5  mov     r14, rcx
0x1800020f8  xor     ecx, ecx
0x1800020fa  call    __scrt_initialize_crt
0x1800020ff  test    al, al
0x180002101  jz      loc_1800021CA
0x180002107  call    __scrt_acquire_startup_lock
0x18000210c  mov     bl, al
0x18000210e  mov     [rsp+48h+arg_10], al
0x180002112  mov     dil, 1
0x180002115  cmp     cs:__scrt_current_native_startup_state, 0
0x18000211c  jnz     loc_1800021D6
0x180002122  mov     cs:__scrt_current_native_startup_state, 1
0x18000212c  call    __scrt_dllmain_before_initialize_c
0x180002131  test    al, al
0x180002133  jz      short loc_180002184
0x180002135  call    _RTC_Initialize
0x18000213a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000213f  call    __scrt_initialize_default_local_stdio_options
0x180002144  lea     rdx, __xi_z; Last
0x18000214b  lea     rcx, __xi_a; First
0x180002152  call    _initterm_e_0
0x180002157  test    eax, eax
0x180002159  jnz     short loc_180002184
0x18000215b  call    __scrt_dllmain_after_initialize_c
0x180002160  test    al, al
0x180002162  jz      short loc_180002184
0x180002164  lea     rdx, __xc_z; Last
0x18000216b  lea     rcx, __xc_a; First
0x180002172  call    _initterm_0
0x180002177  mov     cs:__scrt_current_native_startup_state, 2
0x180002181  xor     dil, dil
0x180002184  mov     cl, bl
0x180002186  call    __scrt_release_startup_lock
0x18000218b  test    dil, dil
0x18000218e  jnz     short loc_1800021CA
0x180002190  call    __scrt_get_dyn_tls_init_callback
0x180002195  mov     rbx, rax
0x180002198  cmp     qword ptr [rax], 0
0x18000219c  jz      short loc_1800021BD
0x18000219e  mov     rcx, rax
0x1800021a1  call    __scrt_is_nonwritable_in_current_image
0x1800021a6  test    al, al
0x1800021a8  jz      short loc_1800021BD
0x1800021aa  mov     r8, rsi
0x1800021ad  mov     edx, 2
0x1800021b2  mov     rcx, r14
0x1800021b5  mov     rax, [rbx]
0x1800021b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021bd  inc     cs:dword_18001C3B0
0x1800021c3  mov     eax, 1
0x1800021c8  jmp     short loc_1800021CC
0x1800021ca  xor     eax, eax
0x1800021cc  add     rsp, 28h
0x1800021d0  pop     r14
0x1800021d2  pop     rdi
0x1800021d3  pop     rsi
0x1800021d4  pop     rbx
0x1800021d5  retn
0x1800021d6  mov     ecx, 7
0x1800021db  call    __scrt_fastfail
0x18000ff2c  push    rbp
0x18000ff2e  sub     rsp, 20h
0x18000ff32  mov     rbp, rdx
0x18000ff35  mov     cl, [rbp+60h]
0x18000ff38  add     rsp, 20h
0x18000ff3c  pop     rbp
0x18000ff3d  jmp     __scrt_release_startup_lock
```
