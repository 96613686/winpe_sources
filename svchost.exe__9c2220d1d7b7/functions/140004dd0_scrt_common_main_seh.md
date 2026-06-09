# __scrt_common_main_seh

- ea: `0x140004dd0`
- end: `0x140004f4b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140004f60`

## callees

- `0x140002ca0`
- `0x140004dd0`
- `0x140004fb4`
- `0x140004ff4`
- `0x1400050c8`
- `0x140005168`
- `0x140005194`
- `0x140005360`
- `0x140005370`
- `0x140005380`
- `0x140005398`
- `0x1400057c6`
- `0x1400057d2`
- `0x1400057de`
- `0x1400057ea`
- `0x1400057f6`
- `0x140005802`
- `0x140005826`
- `0x140005856`
- `0x140005862`
- `0x140005892`
- `0x1400058da`
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
0x140004dd0  mov     [rsp+arg_0], rbx
0x140004dd5  mov     [rsp+arg_8], rsi
0x140004dda  push    rdi
0x140004ddb  sub     rsp, 30h
0x140004ddf  mov     ecx, 1
0x140004de4  call    __scrt_initialize_crt
0x140004de9  test    al, al
0x140004deb  jz      loc_140004F26
0x140004df1  xor     sil, sil
0x140004df4  mov     [rsp+38h+var_18], sil
0x140004df9  call    __scrt_acquire_startup_lock
0x140004dfe  mov     bl, al
0x140004e00  mov     ecx, cs:__scrt_current_native_startup_state
0x140004e06  cmp     ecx, 1
0x140004e09  jz      loc_140004F31
0x140004e0f  test    ecx, ecx
0x140004e11  jnz     short loc_140004E5D
0x140004e13  mov     cs:__scrt_current_native_startup_state, 1
0x140004e1d  lea     rdx, __xi_z; Last
0x140004e24  lea     rcx, __xi_a; First
0x140004e2b  call    _initterm_e_0
0x140004e30  test    eax, eax
0x140004e32  jz      short loc_140004E3E
0x140004e34  mov     eax, 0FFh
0x140004e39  jmp     loc_140004F16
0x140004e3e  lea     rdx, __xc_z; Last
0x140004e45  lea     rcx, __xc_a; First
0x140004e4c  call    _initterm_0
0x140004e51  mov     cs:__scrt_current_native_startup_state, 2
0x140004e5b  jmp     short loc_140004E65
0x140004e5d  mov     sil, 1
0x140004e60  mov     [rsp+38h+var_18], sil
0x140004e65  mov     cl, bl
0x140004e67  call    __scrt_release_startup_lock
0x140004e6c  call    __scrt_get_dyn_tls_init_callback
0x140004e71  mov     rbx, rax
0x140004e74  cmp     qword ptr [rax], 0
0x140004e78  jz      short loc_140004E97
0x140004e7a  mov     rcx, rax
0x140004e7d  call    __scrt_is_nonwritable_in_current_image
0x140004e82  test    al, al
0x140004e84  jz      short loc_140004E97
0x140004e86  xor     r8d, r8d
0x140004e89  lea     edx, [r8+2]
0x140004e8d  xor     ecx, ecx
0x140004e8f  mov     rax, [rbx]
0x140004e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e97  call    __scrt_get_dyn_tls_dtor_callback
0x140004e9c  mov     rbx, rax
0x140004e9f  cmp     qword ptr [rax], 0
0x140004ea3  jz      short loc_140004EB9
0x140004ea5  mov     rcx, rax
0x140004ea8  call    __scrt_is_nonwritable_in_current_image
0x140004ead  test    al, al
0x140004eaf  jz      short loc_140004EB9
0x140004eb1  mov     rcx, [rbx]; Callback
0x140004eb4  call    _register_thread_local_exe_atexit_callback_0
0x140004eb9  call    _get_initial_wide_environment
0x140004ebe  mov     rdi, rax
0x140004ec1  call    __p___wargv
0x140004ec6  mov     rbx, [rax]
0x140004ec9  call    __p___argc
0x140004ece  mov     r8, rdi
0x140004ed1  mov     rdx, rbx
0x140004ed4  mov     ecx, [rax]
0x140004ed6  call    wmain
0x140004edb  mov     ebx, eax
0x140004edd  call    __scrt_is_managed_app
0x140004ee2  test    al, al
0x140004ee4  jz      short loc_140004F3B
0x140004ee6  test    sil, sil
0x140004ee9  jnz     short loc_140004EF0
0x140004eeb  call    _o__cexit_0
0x140004ef0  xor     edx, edx
0x140004ef2  mov     cl, 1
0x140004ef4  call    __scrt_uninitialize_crt
0x140004ef9  mov     eax, ebx
0x140004efb  jmp     short loc_140004F16
0x140004efd  mov     ebx, eax
0x140004eff  call    __scrt_is_managed_app
0x140004f04  test    al, al
0x140004f06  jz      short loc_140004F43
0x140004f08  cmp     [rsp+38h+var_18], 0
0x140004f0d  jnz     short loc_140004F14
0x140004f0f  call    _c_exit_0
0x140004f14  mov     eax, ebx
0x140004f16  mov     rbx, [rsp+38h+arg_0]
0x140004f1b  mov     rsi, [rsp+38h+arg_8]
0x140004f20  add     rsp, 30h
0x140004f24  pop     rdi
0x140004f25  retn
0x140004f26  mov     ecx, 7
0x140004f2b  call    __scrt_fastfail
0x140004f31  mov     ecx, 7
0x140004f36  call    __scrt_fastfail
0x140004f3b  mov     ecx, ebx; Code
0x140004f3d  call    _o_exit_0
0x140004f43  mov     ecx, ebx
0x140004f45  call    _o__exit_0
0x140004f4a  nop
0x140008d3c  push    rbp
0x140008d3e  sub     rsp, 20h
0x140008d42  mov     rbp, rdx
0x140008d45  mov     rdx, rcx; ExceptionPtr
0x140008d48  mov     rcx, [rcx]
0x140008d4b  mov     ecx, [rcx]; ExceptionNum
0x140008d4d  call    _seh_filter_exe
0x140008d52  nop
0x140008d53  add     rsp, 20h
0x140008d57  pop     rbp
0x140008d58  retn
```
