# __scrt_common_main_seh

- ea: `0x140001d20`
- end: `0x140001e9b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001eb0`

## callees

- `0x140001d20`
- `0x140001f04`
- `0x140001f44`
- `0x140002018`
- `0x1400020b8`
- `0x1400020e4`
- `0x1400022c8`
- `0x1400022d8`
- `0x1400022e8`
- `0x140002300`
- `0x140002726`
- `0x140002732`
- `0x14000273e`
- `0x14000274a`
- `0x140002762`
- `0x14000276e`
- `0x14000279e`
- `0x1400027ce`
- `0x1400027da`
- `0x140002828`
- `0x140002858`
- `0x14000cca0`
- `0x140016010`

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
  wchar_t **initial_wide_environment; // rdi
  wchar_t **v12; // rbx
  int *v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx

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
  initial_wide_environment = get_initial_wide_environment();
  v12 = *_p___wargv();
  v13 = _p___argc();
  v14 = wmain((unsigned int)*v13, v12, initial_wide_environment);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    o_exit_0(v14);
  if ( !v1 )
    o__cexit_0(v16);
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x140001d20  mov     [rsp+arg_0], rbx
0x140001d25  mov     [rsp+arg_8], rsi
0x140001d2a  push    rdi
0x140001d2b  sub     rsp, 30h
0x140001d2f  mov     ecx, 1
0x140001d34  call    __scrt_initialize_crt
0x140001d39  test    al, al
0x140001d3b  jz      loc_140001E76
0x140001d41  xor     sil, sil
0x140001d44  mov     [rsp+38h+var_18], sil
0x140001d49  call    __scrt_acquire_startup_lock
0x140001d4e  mov     bl, al
0x140001d50  mov     ecx, cs:__scrt_current_native_startup_state
0x140001d56  cmp     ecx, 1
0x140001d59  jz      loc_140001E81
0x140001d5f  test    ecx, ecx
0x140001d61  jnz     short loc_140001DAD
0x140001d63  mov     cs:__scrt_current_native_startup_state, 1
0x140001d6d  lea     rdx, __xi_z; Last
0x140001d74  lea     rcx, __xi_a; First
0x140001d7b  call    _initterm_e_0
0x140001d80  test    eax, eax
0x140001d82  jz      short loc_140001D8E
0x140001d84  mov     eax, 0FFh
0x140001d89  jmp     loc_140001E66
0x140001d8e  lea     rdx, __xc_z; Last
0x140001d95  lea     rcx, __xc_a; First
0x140001d9c  call    _initterm_0
0x140001da1  mov     cs:__scrt_current_native_startup_state, 2
0x140001dab  jmp     short loc_140001DB5
0x140001dad  mov     sil, 1
0x140001db0  mov     [rsp+38h+var_18], sil
0x140001db5  mov     cl, bl
0x140001db7  call    __scrt_release_startup_lock
0x140001dbc  call    __scrt_get_dyn_tls_init_callback
0x140001dc1  mov     rbx, rax
0x140001dc4  cmp     qword ptr [rax], 0
0x140001dc8  jz      short loc_140001DE7
0x140001dca  mov     rcx, rax
0x140001dcd  call    __scrt_is_nonwritable_in_current_image
0x140001dd2  test    al, al
0x140001dd4  jz      short loc_140001DE7
0x140001dd6  xor     r8d, r8d
0x140001dd9  lea     edx, [r8+2]
0x140001ddd  xor     ecx, ecx
0x140001ddf  mov     rax, [rbx]
0x140001de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001de7  call    __scrt_get_dyn_tls_dtor_callback
0x140001dec  mov     rbx, rax
0x140001def  cmp     qword ptr [rax], 0
0x140001df3  jz      short loc_140001E09
0x140001df5  mov     rcx, rax
0x140001df8  call    __scrt_is_nonwritable_in_current_image
0x140001dfd  test    al, al
0x140001dff  jz      short loc_140001E09
0x140001e01  mov     rcx, [rbx]; Callback
0x140001e04  call    _register_thread_local_exe_atexit_callback_0
0x140001e09  call    _get_initial_wide_environment
0x140001e0e  mov     rdi, rax
0x140001e11  call    __p___wargv
0x140001e16  mov     rbx, [rax]
0x140001e19  call    __p___argc
0x140001e1e  mov     r8, rdi
0x140001e21  mov     rdx, rbx
0x140001e24  mov     ecx, [rax]
0x140001e26  call    wmain
0x140001e2b  mov     ebx, eax
0x140001e2d  call    __scrt_is_managed_app
0x140001e32  test    al, al
0x140001e34  jz      short loc_140001E8B
0x140001e36  test    sil, sil
0x140001e39  jnz     short loc_140001E40
0x140001e3b  call    _o__cexit_0
0x140001e40  xor     edx, edx
0x140001e42  mov     cl, 1
0x140001e44  call    __scrt_uninitialize_crt
0x140001e49  mov     eax, ebx
0x140001e4b  jmp     short loc_140001E66
0x140001e4d  mov     ebx, eax
0x140001e4f  call    __scrt_is_managed_app
0x140001e54  test    al, al
0x140001e56  jz      short loc_140001E93
0x140001e58  cmp     [rsp+38h+var_18], 0
0x140001e5d  jnz     short loc_140001E64
0x140001e5f  call    _c_exit_0
0x140001e64  mov     eax, ebx
0x140001e66  mov     rbx, [rsp+38h+arg_0]
0x140001e6b  mov     rsi, [rsp+38h+arg_8]
0x140001e70  add     rsp, 30h
0x140001e74  pop     rdi
0x140001e75  retn
0x140001e76  mov     ecx, 7
0x140001e7b  call    __scrt_fastfail
0x140001e81  mov     ecx, 7
0x140001e86  call    __scrt_fastfail
0x140001e8b  mov     ecx, ebx; Code
0x140001e8d  call    _o_exit_0
0x140001e93  mov     ecx, ebx
0x140001e95  call    _o__exit_0
0x140001e9a  nop
0x1400155cc  push    rbp
0x1400155ce  sub     rsp, 20h
0x1400155d2  mov     rbp, rdx
0x1400155d5  mov     rdx, rcx; ExceptionPtr
0x1400155d8  mov     rcx, [rcx]
0x1400155db  mov     ecx, [rcx]; ExceptionNum
0x1400155dd  call    _seh_filter_exe
0x1400155e2  nop
0x1400155e3  add     rsp, 20h
0x1400155e7  pop     rbp
0x1400155e8  retn
```
