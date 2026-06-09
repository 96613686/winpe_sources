# __scrt_common_main_seh

- ea: `0x14000f630`
- end: `0x14000f7a0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14000f7b0`

## callees

- `0x140006ab0`
- `0x14000f630`
- `0x14000f848`
- `0x14000f888`
- `0x14000f95c`
- `0x14000f9fc`
- `0x14000fa28`
- `0x140010230`
- `0x140010240`
- `0x140010250`
- `0x14001025c`
- `0x1400102a8`
- `0x140010496`
- `0x1400104a2`
- `0x1400104ae`
- `0x1400104ba`
- `0x14001051a`
- `0x14001054a`
- `0x140010556`
- `0x1400105a8`
- `0x1400105d8`
- `0x140067010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // di
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  __int64 v10; // rcx
  _tls_callback_type *v11; // rbx
  int show_window_mode; // ebx
  WCHAR *wide_winmain_command_line_0; // rax
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
  v11 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v11);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v10);
  wide_winmain_command_line_0 = (WCHAR *)o__get_wide_winmain_command_line_0();
  v14 = wWinMain(&_ImageBase, 0, wide_winmain_command_line_0, show_window_mode);
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
0x14000f630  mov     [rsp+arg_0], rbx
0x14000f635  push    rdi
0x14000f636  sub     rsp, 30h
0x14000f63a  mov     ecx, 1
0x14000f63f  call    __scrt_initialize_crt
0x14000f644  test    al, al
0x14000f646  jz      loc_14000F77B
0x14000f64c  xor     dil, dil
0x14000f64f  mov     [rsp+38h+var_18], dil
0x14000f654  call    __scrt_acquire_startup_lock
0x14000f659  mov     bl, al
0x14000f65b  mov     ecx, cs:__scrt_current_native_startup_state
0x14000f661  cmp     ecx, 1
0x14000f664  jz      loc_14000F786
0x14000f66a  test    ecx, ecx
0x14000f66c  jnz     short loc_14000F6B8
0x14000f66e  mov     cs:__scrt_current_native_startup_state, 1
0x14000f678  lea     rdx, __xi_z; Last
0x14000f67f  lea     rcx, __xi_a; First
0x14000f686  call    _initterm_e_0
0x14000f68b  test    eax, eax
0x14000f68d  jz      short loc_14000F699
0x14000f68f  mov     eax, 0FFh
0x14000f694  jmp     loc_14000F770
0x14000f699  lea     rdx, __xc_z; Last
0x14000f6a0  lea     rcx, __xc_a; First
0x14000f6a7  call    _initterm_0
0x14000f6ac  mov     cs:__scrt_current_native_startup_state, 2
0x14000f6b6  jmp     short loc_14000F6C0
0x14000f6b8  mov     dil, 1
0x14000f6bb  mov     [rsp+38h+var_18], dil
0x14000f6c0  mov     cl, bl
0x14000f6c2  call    __scrt_release_startup_lock
0x14000f6c7  call    __scrt_get_dyn_tls_init_callback
0x14000f6cc  mov     rbx, rax
0x14000f6cf  cmp     qword ptr [rax], 0
0x14000f6d3  jz      short loc_14000F6F2
0x14000f6d5  mov     rcx, rax
0x14000f6d8  call    __scrt_is_nonwritable_in_current_image
0x14000f6dd  test    al, al
0x14000f6df  jz      short loc_14000F6F2
0x14000f6e1  xor     r8d, r8d
0x14000f6e4  lea     edx, [r8+2]
0x14000f6e8  xor     ecx, ecx
0x14000f6ea  mov     rax, [rbx]
0x14000f6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6f2  call    __scrt_get_dyn_tls_dtor_callback
0x14000f6f7  mov     rbx, rax
0x14000f6fa  cmp     qword ptr [rax], 0
0x14000f6fe  jz      short loc_14000F714
0x14000f700  mov     rcx, rax
0x14000f703  call    __scrt_is_nonwritable_in_current_image
0x14000f708  test    al, al
0x14000f70a  jz      short loc_14000F714
0x14000f70c  mov     rcx, [rbx]; Callback
0x14000f70f  call    _register_thread_local_exe_atexit_callback_0
0x14000f714  call    __scrt_get_show_window_mode
0x14000f719  movzx   ebx, ax
0x14000f71c  call    _o__get_wide_winmain_command_line_0
0x14000f721  mov     r9d, ebx; nShowCmd
0x14000f724  mov     r8, rax; lpCmdLine
0x14000f727  xor     edx, edx; hPrevInstance
0x14000f729  lea     rcx, __ImageBase; hInstance
0x14000f730  call    wWinMain
0x14000f735  mov     ebx, eax
0x14000f737  call    __scrt_is_managed_app
0x14000f73c  test    al, al
0x14000f73e  jz      short loc_14000F790
0x14000f740  test    dil, dil
0x14000f743  jnz     short loc_14000F74A
0x14000f745  call    _o__cexit_0
0x14000f74a  xor     edx, edx
0x14000f74c  mov     cl, 1
0x14000f74e  call    __scrt_uninitialize_crt
0x14000f753  mov     eax, ebx
0x14000f755  jmp     short loc_14000F770
0x14000f757  mov     ebx, eax
0x14000f759  call    __scrt_is_managed_app
0x14000f75e  test    al, al
0x14000f760  jz      short loc_14000F798
0x14000f762  cmp     [rsp+38h+var_18], 0
0x14000f767  jnz     short loc_14000F76E
0x14000f769  call    _c_exit_0
0x14000f76e  mov     eax, ebx
0x14000f770  mov     rbx, [rsp+38h+arg_0]
0x14000f775  add     rsp, 30h
0x14000f779  pop     rdi
0x14000f77a  retn
0x14000f77b  mov     ecx, 7
0x14000f780  call    __scrt_fastfail
0x14000f786  mov     ecx, 7
0x14000f78b  call    __scrt_fastfail
0x14000f790  mov     ecx, ebx; Code
0x14000f792  call    _o_exit_0
0x14000f798  mov     ecx, ebx
0x14000f79a  call    _o__exit_0
0x14000f79f  nop
0x140060cb7  push    rbp
0x140060cb9  sub     rsp, 20h
0x140060cbd  mov     rbp, rdx
0x140060cc0  mov     rdx, rcx; ExceptionPtr
0x140060cc3  mov     rcx, [rcx]
0x140060cc6  mov     ecx, [rcx]; ExceptionNum
0x140060cc8  call    _seh_filter_exe
0x140060ccd  nop
0x140060cce  add     rsp, 20h
0x140060cd2  pop     rbp
0x140060cd3  retn
```
