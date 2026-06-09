# __scrt_common_main_seh

- ea: `0x140002210`
- end: `0x14000238b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400023a0`

## callees

- `0x140002210`
- `0x140002464`
- `0x1400024a4`
- `0x140002578`
- `0x140002618`
- `0x140002644`
- `0x1400027ec`
- `0x1400027fc`
- `0x14000280c`
- `0x140002824`
- `0x140002e06`
- `0x140002e12`
- `0x140002e1e`
- `0x140002e2a`
- `0x140002e5a`
- `0x140002e66`
- `0x140002eba`
- `0x140002eea`
- `0x140002ef6`
- `0x140002f48`
- `0x140002f78`
- `0x140007634`
- `0x140012010`

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
  v13 = wmain((char *)(unsigned int)*v12, (const wchar_t **)v11);
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
0x140002210  mov     [rsp+arg_0], rbx
0x140002215  mov     [rsp+arg_8], rsi
0x14000221a  push    rdi
0x14000221b  sub     rsp, 30h
0x14000221f  mov     ecx, 1
0x140002224  call    __scrt_initialize_crt
0x140002229  test    al, al
0x14000222b  jz      loc_140002366
0x140002231  xor     sil, sil
0x140002234  mov     [rsp+38h+var_18], sil
0x140002239  call    __scrt_acquire_startup_lock
0x14000223e  mov     bl, al
0x140002240  mov     ecx, cs:__scrt_current_native_startup_state
0x140002246  cmp     ecx, 1
0x140002249  jz      loc_140002371
0x14000224f  test    ecx, ecx
0x140002251  jnz     short loc_14000229D
0x140002253  mov     cs:__scrt_current_native_startup_state, 1
0x14000225d  lea     rdx, __xi_z; Last
0x140002264  lea     rcx, __xi_a; First
0x14000226b  call    _initterm_e_0
0x140002270  test    eax, eax
0x140002272  jz      short loc_14000227E
0x140002274  mov     eax, 0FFh
0x140002279  jmp     loc_140002356
0x14000227e  lea     rdx, __xc_z; Last
0x140002285  lea     rcx, __xc_a; First
0x14000228c  call    _initterm_0
0x140002291  mov     cs:__scrt_current_native_startup_state, 2
0x14000229b  jmp     short loc_1400022A5
0x14000229d  mov     sil, 1
0x1400022a0  mov     [rsp+38h+var_18], sil
0x1400022a5  mov     cl, bl
0x1400022a7  call    __scrt_release_startup_lock
0x1400022ac  call    __scrt_get_dyn_tls_init_callback
0x1400022b1  mov     rbx, rax
0x1400022b4  cmp     qword ptr [rax], 0
0x1400022b8  jz      short loc_1400022D7
0x1400022ba  mov     rcx, rax
0x1400022bd  call    __scrt_is_nonwritable_in_current_image
0x1400022c2  test    al, al
0x1400022c4  jz      short loc_1400022D7
0x1400022c6  xor     r8d, r8d
0x1400022c9  lea     edx, [r8+2]
0x1400022cd  xor     ecx, ecx
0x1400022cf  mov     rax, [rbx]
0x1400022d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022d7  call    __scrt_get_dyn_tls_dtor_callback
0x1400022dc  mov     rbx, rax
0x1400022df  cmp     qword ptr [rax], 0
0x1400022e3  jz      short loc_1400022F9
0x1400022e5  mov     rcx, rax
0x1400022e8  call    __scrt_is_nonwritable_in_current_image
0x1400022ed  test    al, al
0x1400022ef  jz      short loc_1400022F9
0x1400022f1  mov     rcx, [rbx]; Callback
0x1400022f4  call    _register_thread_local_exe_atexit_callback_0
0x1400022f9  call    _get_initial_wide_environment
0x1400022fe  mov     rdi, rax
0x140002301  call    __p___wargv
0x140002306  mov     rbx, [rax]
0x140002309  call    __p___argc
0x14000230e  mov     r8, rdi
0x140002311  mov     rdx, rbx
0x140002314  mov     ecx, [rax]
0x140002316  call    wmain
0x14000231b  mov     ebx, eax
0x14000231d  call    __scrt_is_managed_app
0x140002322  test    al, al
0x140002324  jz      short loc_14000237B
0x140002326  test    sil, sil
0x140002329  jnz     short loc_140002330
0x14000232b  call    _o__cexit_0
0x140002330  xor     edx, edx
0x140002332  mov     cl, 1
0x140002334  call    __scrt_uninitialize_crt
0x140002339  mov     eax, ebx
0x14000233b  jmp     short loc_140002356
0x14000233d  mov     ebx, eax
0x14000233f  call    __scrt_is_managed_app
0x140002344  test    al, al
0x140002346  jz      short loc_140002383
0x140002348  cmp     [rsp+38h+var_18], 0
0x14000234d  jnz     short loc_140002354
0x14000234f  call    _c_exit_0
0x140002354  mov     eax, ebx
0x140002356  mov     rbx, [rsp+38h+arg_0]
0x14000235b  mov     rsi, [rsp+38h+arg_8]
0x140002360  add     rsp, 30h
0x140002364  pop     rdi
0x140002365  retn
0x140002366  mov     ecx, 7
0x14000236b  call    __scrt_fastfail
0x140002371  mov     ecx, 7
0x140002376  call    __scrt_fastfail
0x14000237b  mov     ecx, ebx; Code
0x14000237d  call    _o_exit_0
0x140002383  mov     ecx, ebx
0x140002385  call    _o__exit_0
0x14000238a  nop
0x14001138c  push    rbp
0x14001138e  sub     rsp, 20h
0x140011392  mov     rbp, rdx
0x140011395  mov     rdx, rcx; ExceptionPtr
0x140011398  mov     rcx, [rcx]
0x14001139b  mov     ecx, [rcx]; ExceptionNum
0x14001139d  call    _seh_filter_exe
0x1400113a2  nop
0x1400113a3  add     rsp, 20h
0x1400113a7  pop     rbp
0x1400113a8  retn
```
