# __scrt_common_main_seh

- ea: `0x140004a10`
- end: `0x140004b8b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140004ba0`

## callees

- `0x140002a30`
- `0x140004a10`
- `0x140004bf4`
- `0x140004c34`
- `0x140004d08`
- `0x140004da8`
- `0x140004dd4`
- `0x140004f88`
- `0x140004f98`
- `0x140004fa8`
- `0x140004fc0`
- `0x1400053e6`
- `0x1400053f2`
- `0x1400053fe`
- `0x14000540a`
- `0x140005416`
- `0x140005422`
- `0x140005446`
- `0x140005476`
- `0x140005482`
- `0x1400054b2`
- `0x1400054fa`
- `0x140009010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // bl
  __int64 v2; // rcx
  __int64 v4; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v6; // rcx
  void (__fastcall **v7)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v9; // rbx
  wchar_t **initial_wide_environment; // rdi
  wchar_t **v11; // rbx
  int *v12; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = _scrt_acquire_startup_lock(v0);
  v2 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
LABEL_7:
    LOBYTE(v2) = v1;
    _scrt_release_startup_lock(v2);
    dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v4);
    v7 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
    if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v7)(0, 2);
    dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v6);
    v9 = dyn_tls_dtor_callback;
    if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
      register_thread_local_exe_atexit_callback_0(*v9);
    initial_wide_environment = get_initial_wide_environment();
    v11 = *_p___wargv();
    v12 = _p___argc();
    wmain((unsigned int)*v12, v11, initial_wide_environment);
  }
  _scrt_current_native_startup_state = 1;
  if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
  {
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
    goto LABEL_7;
  }
  return 255;
}

```

## disassembly

```asm
0x140004a10  mov     [rsp+arg_0], rbx
0x140004a15  mov     [rsp+arg_8], rsi
0x140004a1a  push    rdi
0x140004a1b  sub     rsp, 30h
0x140004a1f  mov     ecx, 1
0x140004a24  call    __scrt_initialize_crt
0x140004a29  test    al, al
0x140004a2b  jz      loc_140004B66
0x140004a31  xor     sil, sil
0x140004a34  mov     [rsp+38h+var_18], sil
0x140004a39  call    __scrt_acquire_startup_lock
0x140004a3e  mov     bl, al
0x140004a40  mov     ecx, cs:__scrt_current_native_startup_state
0x140004a46  cmp     ecx, 1
0x140004a49  jz      loc_140004B71
0x140004a4f  test    ecx, ecx
0x140004a51  jnz     short loc_140004A9D
0x140004a53  mov     cs:__scrt_current_native_startup_state, 1
0x140004a5d  lea     rdx, __xi_z; Last
0x140004a64  lea     rcx, __xi_a; First
0x140004a6b  call    _initterm_e_0
0x140004a70  test    eax, eax
0x140004a72  jz      short loc_140004A7E
0x140004a74  mov     eax, 0FFh
0x140004a79  jmp     loc_140004B56
0x140004a7e  lea     rdx, __xc_z; Last
0x140004a85  lea     rcx, __xc_a; First
0x140004a8c  call    _initterm_0
0x140004a91  mov     cs:__scrt_current_native_startup_state, 2
0x140004a9b  jmp     short loc_140004AA5
0x140004a9d  mov     sil, 1
0x140004aa0  mov     [rsp+38h+var_18], sil
0x140004aa5  mov     cl, bl
0x140004aa7  call    __scrt_release_startup_lock
0x140004aac  call    __scrt_get_dyn_tls_init_callback
0x140004ab1  mov     rbx, rax
0x140004ab4  cmp     qword ptr [rax], 0
0x140004ab8  jz      short loc_140004AD7
0x140004aba  mov     rcx, rax
0x140004abd  call    __scrt_is_nonwritable_in_current_image
0x140004ac2  test    al, al
0x140004ac4  jz      short loc_140004AD7
0x140004ac6  xor     r8d, r8d
0x140004ac9  lea     edx, [r8+2]
0x140004acd  xor     ecx, ecx
0x140004acf  mov     rax, [rbx]
0x140004ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ad7  call    __scrt_get_dyn_tls_dtor_callback
0x140004adc  mov     rbx, rax
0x140004adf  cmp     qword ptr [rax], 0
0x140004ae3  jz      short loc_140004AF9
0x140004ae5  mov     rcx, rax
0x140004ae8  call    __scrt_is_nonwritable_in_current_image
0x140004aed  test    al, al
0x140004aef  jz      short loc_140004AF9
0x140004af1  mov     rcx, [rbx]; Callback
0x140004af4  call    _register_thread_local_exe_atexit_callback_0
0x140004af9  call    _get_initial_wide_environment
0x140004afe  mov     rdi, rax
0x140004b01  call    __p___wargv
0x140004b06  mov     rbx, [rax]
0x140004b09  call    __p___argc
0x140004b0e  mov     r8, rdi
0x140004b11  mov     rdx, rbx
0x140004b14  mov     ecx, [rax]
0x140004b16  call    wmain
0x140004b1b  mov     ebx, eax
0x140004b1d  call    __scrt_is_managed_app
0x140004b22  test    al, al
0x140004b24  jz      short loc_140004B7B
0x140004b26  test    sil, sil
0x140004b29  jnz     short loc_140004B30
0x140004b2b  call    _o__cexit_0
0x140004b30  xor     edx, edx
0x140004b32  mov     cl, 1
0x140004b34  call    __scrt_uninitialize_crt
0x140004b39  mov     eax, ebx
0x140004b3b  jmp     short loc_140004B56
0x140004b3d  mov     ebx, eax
0x140004b3f  call    __scrt_is_managed_app
0x140004b44  test    al, al
0x140004b46  jz      short loc_140004B83
0x140004b48  cmp     [rsp+38h+var_18], 0
0x140004b4d  jnz     short loc_140004B54
0x140004b4f  call    _c_exit_0
0x140004b54  mov     eax, ebx
0x140004b56  mov     rbx, [rsp+38h+arg_0]
0x140004b5b  mov     rsi, [rsp+38h+arg_8]
0x140004b60  add     rsp, 30h
0x140004b64  pop     rdi
0x140004b65  retn
0x140004b66  mov     ecx, 7
0x140004b6b  call    __scrt_fastfail
0x140004b71  mov     ecx, 7
0x140004b76  call    __scrt_fastfail
0x140004b7b  mov     ecx, ebx; Code
0x140004b7d  call    _o_exit_0
0x140004b83  mov     ecx, ebx
0x140004b85  call    _o__exit_0
0x140004b8a  nop
0x1400086ec  push    rbp
0x1400086ee  sub     rsp, 20h
0x1400086f2  mov     rbp, rdx
0x1400086f5  mov     rdx, rcx; ExceptionPtr
0x1400086f8  mov     rcx, [rcx]
0x1400086fb  mov     ecx, [rcx]; ExceptionNum
0x1400086fd  call    _seh_filter_exe
0x140008702  nop
0x140008703  add     rsp, 20h
0x140008707  pop     rbp
0x140008708  retn
```
