# dllmain_crt_process_attach

- ea: `0x180001358`
- end: `0x180001452`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001300`

## callees

- `0x180001358`
- `0x18000175c`
- `0x18000179c`
- `0x1800017d8`
- `0x1800018d8`
- `0x1800019ac`
- `0x180001a4c`
- `0x180001b08`
- `0x180001b30`
- `0x180001b54`
- `0x180001b64`
- `0x180001b70`
- `0x180001ec6`
- `0x180001ed2`
- `0x18000e010`

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
  ++dword_180012350;
  return 1;
}

```

## disassembly

```asm
0x180001358  push    rbx
0x18000135a  push    rsi
0x18000135b  push    rdi
0x18000135c  push    r14
0x18000135e  sub     rsp, 28h
0x180001362  mov     rsi, rdx
0x180001365  mov     r14, rcx
0x180001368  xor     ecx, ecx
0x18000136a  call    __scrt_initialize_crt
0x18000136f  test    al, al
0x180001371  jz      loc_18000143A
0x180001377  call    __scrt_acquire_startup_lock
0x18000137c  mov     bl, al
0x18000137e  mov     [rsp+48h+arg_10], al
0x180001382  mov     dil, 1
0x180001385  cmp     cs:__scrt_current_native_startup_state, 0
0x18000138c  jnz     loc_180001446
0x180001392  mov     cs:__scrt_current_native_startup_state, 1
0x18000139c  call    __scrt_dllmain_before_initialize_c
0x1800013a1  test    al, al
0x1800013a3  jz      short loc_1800013F4
0x1800013a5  call    _RTC_Initialize
0x1800013aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800013af  call    __scrt_initialize_default_local_stdio_options
0x1800013b4  lea     rdx, __xi_z; Last
0x1800013bb  lea     rcx, __xi_a; First
0x1800013c2  call    _initterm_e_0
0x1800013c7  test    eax, eax
0x1800013c9  jnz     short loc_1800013F4
0x1800013cb  call    __scrt_dllmain_after_initialize_c
0x1800013d0  test    al, al
0x1800013d2  jz      short loc_1800013F4
0x1800013d4  lea     rdx, __xc_z; Last
0x1800013db  lea     rcx, __xc_a; First
0x1800013e2  call    _initterm_0
0x1800013e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800013f1  xor     dil, dil
0x1800013f4  mov     cl, bl
0x1800013f6  call    __scrt_release_startup_lock
0x1800013fb  test    dil, dil
0x1800013fe  jnz     short loc_18000143A
0x180001400  call    __scrt_get_dyn_tls_init_callback
0x180001405  mov     rbx, rax
0x180001408  cmp     qword ptr [rax], 0
0x18000140c  jz      short loc_18000142D
0x18000140e  mov     rcx, rax
0x180001411  call    __scrt_is_nonwritable_in_current_image
0x180001416  test    al, al
0x180001418  jz      short loc_18000142D
0x18000141a  mov     r8, rsi
0x18000141d  mov     edx, 2
0x180001422  mov     rcx, r14
0x180001425  mov     rax, [rbx]
0x180001428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000142d  inc     cs:dword_180012350
0x180001433  mov     eax, 1
0x180001438  jmp     short loc_18000143C
0x18000143a  xor     eax, eax
0x18000143c  add     rsp, 28h
0x180001440  pop     r14
0x180001442  pop     rdi
0x180001443  pop     rsi
0x180001444  pop     rbx
0x180001445  retn
0x180001446  mov     ecx, 7
0x18000144b  call    __scrt_fastfail
0x18000dc8c  push    rbp
0x18000dc8e  sub     rsp, 20h
0x18000dc92  mov     rbp, rdx
0x18000dc95  mov     cl, [rbp+60h]
0x18000dc98  add     rsp, 20h
0x18000dc9c  pop     rbp
0x18000dc9d  jmp     __scrt_release_startup_lock
```
