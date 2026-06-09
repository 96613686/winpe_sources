# __scrt_common_main_seh

- ea: `0x140021940`
- end: `0x140021abb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140021ad0`

## callees

- `0x140021940`
- `0x140021b5c`
- `0x140021b9c`
- `0x140021c70`
- `0x140021d10`
- `0x140021d3c`
- `0x140021f00`
- `0x140021f10`
- `0x140021f20`
- `0x140021f38`
- `0x140022366`
- `0x140022372`
- `0x14002237e`
- `0x14002238a`
- `0x1400223ba`
- `0x1400223c6`
- `0x14002241a`
- `0x14002244a`
- `0x140022456`
- `0x140022498`
- `0x1400224c8`
- `0x140023de0`
- `0x140034010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // si
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v10; // rbx
  wchar_t **v11; // rbx
  int *v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = 0;
  v2 = _scrt_acquire_startup_lock(v0);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
    v1 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v2;
  _scrt_release_startup_lock(v3);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v8)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v7);
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  get_initial_wide_environment();
  v11 = *_p___wargv();
  v12 = _p___argc();
  v13 = wmain(*v12, (const wchar_t **)v11);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
    o_exit_0(v13);
  if ( !v1 )
    o__cexit_0(v15);
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v13;
}

```

## disassembly

```asm
0x140021940  mov     [rsp+arg_0], rbx
0x140021945  mov     [rsp+arg_8], rsi
0x14002194a  push    rdi
0x14002194b  sub     rsp, 30h
0x14002194f  mov     ecx, 1
0x140021954  call    __scrt_initialize_crt
0x140021959  test    al, al
0x14002195b  jz      loc_140021A96
0x140021961  xor     sil, sil
0x140021964  mov     [rsp+38h+var_18], sil
0x140021969  call    __scrt_acquire_startup_lock
0x14002196e  mov     bl, al
0x140021970  mov     ecx, cs:__scrt_current_native_startup_state
0x140021976  cmp     ecx, 1
0x140021979  jz      loc_140021AA1
0x14002197f  test    ecx, ecx
0x140021981  jnz     short loc_1400219CD
0x140021983  mov     cs:__scrt_current_native_startup_state, 1
0x14002198d  lea     rdx, __xi_z; Last
0x140021994  lea     rcx, __xi_a; First
0x14002199b  call    _initterm_e_0
0x1400219a0  test    eax, eax
0x1400219a2  jz      short loc_1400219AE
0x1400219a4  mov     eax, 0FFh
0x1400219a9  jmp     loc_140021A86
0x1400219ae  lea     rdx, __xc_z; Last
0x1400219b5  lea     rcx, __xc_a; First
0x1400219bc  call    _initterm_0
0x1400219c1  mov     cs:__scrt_current_native_startup_state, 2
0x1400219cb  jmp     short loc_1400219D5
0x1400219cd  mov     sil, 1
0x1400219d0  mov     [rsp+38h+var_18], sil
0x1400219d5  mov     cl, bl
0x1400219d7  call    __scrt_release_startup_lock
0x1400219dc  call    __scrt_get_dyn_tls_init_callback
0x1400219e1  mov     rbx, rax
0x1400219e4  cmp     qword ptr [rax], 0
0x1400219e8  jz      short loc_140021A07
0x1400219ea  mov     rcx, rax
0x1400219ed  call    __scrt_is_nonwritable_in_current_image
0x1400219f2  test    al, al
0x1400219f4  jz      short loc_140021A07
0x1400219f6  xor     r8d, r8d
0x1400219f9  lea     edx, [r8+2]
0x1400219fd  xor     ecx, ecx
0x1400219ff  mov     rax, [rbx]
0x140021a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021a07  call    __scrt_get_dyn_tls_dtor_callback
0x140021a0c  mov     rbx, rax
0x140021a0f  cmp     qword ptr [rax], 0
0x140021a13  jz      short loc_140021A29
0x140021a15  mov     rcx, rax
0x140021a18  call    __scrt_is_nonwritable_in_current_image
0x140021a1d  test    al, al
0x140021a1f  jz      short loc_140021A29
0x140021a21  mov     rcx, [rbx]; Callback
0x140021a24  call    _register_thread_local_exe_atexit_callback_0
0x140021a29  call    _get_initial_wide_environment
0x140021a2e  mov     rdi, rax
0x140021a31  call    __p___wargv
0x140021a36  mov     rbx, [rax]
0x140021a39  call    __p___argc
0x140021a3e  mov     r8, rdi
0x140021a41  mov     rdx, rbx; wchar_t **
0x140021a44  mov     ecx, [rax]; int
0x140021a46  call    wmain
0x140021a4b  mov     ebx, eax
0x140021a4d  call    __scrt_is_managed_app
0x140021a52  test    al, al
0x140021a54  jz      short loc_140021AAB
0x140021a56  test    sil, sil
0x140021a59  jnz     short loc_140021A60
0x140021a5b  call    _o__cexit_0
0x140021a60  xor     edx, edx
0x140021a62  mov     cl, 1
0x140021a64  call    __scrt_uninitialize_crt
0x140021a69  mov     eax, ebx
0x140021a6b  jmp     short loc_140021A86
0x140021a6d  mov     ebx, eax
0x140021a6f  call    __scrt_is_managed_app
0x140021a74  test    al, al
0x140021a76  jz      short loc_140021AB3
0x140021a78  cmp     [rsp+38h+var_18], 0
0x140021a7d  jnz     short loc_140021A84
0x140021a7f  call    _c_exit_0
0x140021a84  mov     eax, ebx
0x140021a86  mov     rbx, [rsp+38h+arg_0]
0x140021a8b  mov     rsi, [rsp+38h+arg_8]
0x140021a90  add     rsp, 30h
0x140021a94  pop     rdi
0x140021a95  retn
0x140021a96  mov     ecx, 7
0x140021a9b  call    __scrt_fastfail
0x140021aa1  mov     ecx, 7
0x140021aa6  call    __scrt_fastfail
0x140021aab  mov     ecx, ebx; Code
0x140021aad  call    _o_exit_0
0x140021ab3  mov     ecx, ebx
0x140021ab5  call    _o__exit_0
0x140021aba  nop
0x140032e4d  push    rbp
0x140032e4f  sub     rsp, 20h
0x140032e53  mov     rbp, rdx
0x140032e56  mov     rdx, rcx; ExceptionPtr
0x140032e59  mov     rcx, [rcx]
0x140032e5c  mov     ecx, [rcx]; ExceptionNum
0x140032e5e  call    _seh_filter_exe
0x140032e63  nop
0x140032e64  add     rsp, 20h
0x140032e68  pop     rbp
0x140032e69  retn
```
