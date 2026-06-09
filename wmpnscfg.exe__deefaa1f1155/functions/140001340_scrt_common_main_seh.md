# __scrt_common_main_seh

- ea: `0x140001340`
- end: `0x1400014b0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400014c0`

## callees

- `0x140001340`
- `0x140001514`
- `0x140001554`
- `0x140001628`
- `0x1400016c8`
- `0x1400016f4`
- `0x1400018d0`
- `0x1400018e0`
- `0x1400018f0`
- `0x1400018fc`
- `0x140001948`
- `0x140001d56`
- `0x140001d62`
- `0x140001d6e`
- `0x140001d7a`
- `0x140001dc2`
- `0x140001df2`
- `0x140001dfe`
- `0x140001e3a`
- `0x140001e6a`
- `0x140005658`
- `0x140008010`

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
0x140001340  mov     [rsp+arg_0], rbx
0x140001345  push    rdi
0x140001346  sub     rsp, 30h
0x14000134a  mov     ecx, 1
0x14000134f  call    __scrt_initialize_crt
0x140001354  test    al, al
0x140001356  jz      loc_14000148B
0x14000135c  xor     dil, dil
0x14000135f  mov     [rsp+38h+var_18], dil
0x140001364  call    __scrt_acquire_startup_lock
0x140001369  mov     bl, al
0x14000136b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001371  cmp     ecx, 1
0x140001374  jz      loc_140001496
0x14000137a  test    ecx, ecx
0x14000137c  jnz     short loc_1400013C8
0x14000137e  mov     cs:__scrt_current_native_startup_state, 1
0x140001388  lea     rdx, __xi_z; Last
0x14000138f  lea     rcx, __xi_a; First
0x140001396  call    _initterm_e_0
0x14000139b  test    eax, eax
0x14000139d  jz      short loc_1400013A9
0x14000139f  mov     eax, 0FFh
0x1400013a4  jmp     loc_140001480
0x1400013a9  lea     rdx, __xc_z; Last
0x1400013b0  lea     rcx, __xc_a; First
0x1400013b7  call    _initterm_0
0x1400013bc  mov     cs:__scrt_current_native_startup_state, 2
0x1400013c6  jmp     short loc_1400013D0
0x1400013c8  mov     dil, 1
0x1400013cb  mov     [rsp+38h+var_18], dil
0x1400013d0  mov     cl, bl
0x1400013d2  call    __scrt_release_startup_lock
0x1400013d7  call    __scrt_get_dyn_tls_init_callback
0x1400013dc  mov     rbx, rax
0x1400013df  cmp     qword ptr [rax], 0
0x1400013e3  jz      short loc_140001402
0x1400013e5  mov     rcx, rax
0x1400013e8  call    __scrt_is_nonwritable_in_current_image
0x1400013ed  test    al, al
0x1400013ef  jz      short loc_140001402
0x1400013f1  xor     r8d, r8d
0x1400013f4  lea     edx, [r8+2]
0x1400013f8  xor     ecx, ecx
0x1400013fa  mov     rax, [rbx]
0x1400013fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001402  call    __scrt_get_dyn_tls_dtor_callback
0x140001407  mov     rbx, rax
0x14000140a  cmp     qword ptr [rax], 0
0x14000140e  jz      short loc_140001424
0x140001410  mov     rcx, rax
0x140001413  call    __scrt_is_nonwritable_in_current_image
0x140001418  test    al, al
0x14000141a  jz      short loc_140001424
0x14000141c  mov     rcx, [rbx]; Callback
0x14000141f  call    _register_thread_local_exe_atexit_callback_0
0x140001424  call    __scrt_get_show_window_mode
0x140001429  movzx   ebx, ax
0x14000142c  call    _o__get_wide_winmain_command_line_0
0x140001431  mov     r9d, ebx; nShowCmd
0x140001434  mov     r8, rax; lpCmdLine
0x140001437  xor     edx, edx; hPrevInstance
0x140001439  lea     rcx, __ImageBase; hInstance
0x140001440  call    wWinMain
0x140001445  mov     ebx, eax
0x140001447  call    __scrt_is_managed_app
0x14000144c  test    al, al
0x14000144e  jz      short loc_1400014A0
0x140001450  test    dil, dil
0x140001453  jnz     short loc_14000145A
0x140001455  call    _o__cexit_0
0x14000145a  xor     edx, edx
0x14000145c  mov     cl, 1
0x14000145e  call    __scrt_uninitialize_crt
0x140001463  mov     eax, ebx
0x140001465  jmp     short loc_140001480
0x140001467  mov     ebx, eax
0x140001469  call    __scrt_is_managed_app
0x14000146e  test    al, al
0x140001470  jz      short loc_1400014A8
0x140001472  cmp     [rsp+38h+var_18], 0
0x140001477  jnz     short loc_14000147E
0x140001479  call    _c_exit_0
0x14000147e  mov     eax, ebx
0x140001480  mov     rbx, [rsp+38h+arg_0]
0x140001485  add     rsp, 30h
0x140001489  pop     rdi
0x14000148a  retn
0x14000148b  mov     ecx, 7
0x140001490  call    __scrt_fastfail
0x140001496  mov     ecx, 7
0x14000149b  call    __scrt_fastfail
0x1400014a0  mov     ecx, ebx; Code
0x1400014a2  call    _o_exit_0
0x1400014a8  mov     ecx, ebx
0x1400014aa  call    _o__exit_0
0x1400014af  nop
0x14000765c  push    rbp
0x14000765e  sub     rsp, 20h
0x140007662  mov     rbp, rdx
0x140007665  mov     rdx, rcx; ExceptionPtr
0x140007668  mov     rcx, [rcx]
0x14000766b  mov     ecx, [rcx]; ExceptionNum
0x14000766d  call    _seh_filter_exe
0x140007672  nop
0x140007673  add     rsp, 20h
0x140007677  pop     rbp
0x140007678  retn
```
