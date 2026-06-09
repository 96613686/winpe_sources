# __scrt_common_main_seh

- ea: `0x1400012e0`
- end: `0x140001450`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001460`

## callees

- `0x1400012e0`
- `0x1400014e0`
- `0x140001520`
- `0x1400015f4`
- `0x140001694`
- `0x1400016c0`
- `0x14000185c`
- `0x14000186c`
- `0x14000187c`
- `0x140001888`
- `0x1400018d4`
- `0x140001cd6`
- `0x140001ce2`
- `0x140001cee`
- `0x140001cfa`
- `0x140001d2a`
- `0x140001d5a`
- `0x140001d66`
- `0x140001db8`
- `0x140001de8`
- `0x140005c80`
- `0x140007010`

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
  __int64 v13; // rcx
  WCHAR *wide_winmain_command_line_0; // rax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rcx

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
  wide_winmain_command_line_0 = (WCHAR *)o__get_wide_winmain_command_line_0(v13);
  v15 = wWinMain(&_ImageBase, 0, wide_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v16) )
    o_exit_0(v15);
  if ( !v1 )
    o__cexit_0(v17);
  LOBYTE(v17) = 1;
  _scrt_uninitialize_crt(v17, 0);
  return v15;
}

```

## disassembly

```asm
0x1400012e0  mov     [rsp+arg_0], rbx
0x1400012e5  push    rdi
0x1400012e6  sub     rsp, 30h
0x1400012ea  mov     ecx, 1
0x1400012ef  call    __scrt_initialize_crt
0x1400012f4  test    al, al
0x1400012f6  jz      loc_14000142B
0x1400012fc  xor     dil, dil
0x1400012ff  mov     [rsp+38h+var_18], dil
0x140001304  call    __scrt_acquire_startup_lock
0x140001309  mov     bl, al
0x14000130b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001311  cmp     ecx, 1
0x140001314  jz      loc_140001436
0x14000131a  test    ecx, ecx
0x14000131c  jnz     short loc_140001368
0x14000131e  mov     cs:__scrt_current_native_startup_state, 1
0x140001328  lea     rdx, __xi_z; Last
0x14000132f  lea     rcx, __xi_a; First
0x140001336  call    _initterm_e_0
0x14000133b  test    eax, eax
0x14000133d  jz      short loc_140001349
0x14000133f  mov     eax, 0FFh
0x140001344  jmp     loc_140001420
0x140001349  lea     rdx, __xc_z; Last
0x140001350  lea     rcx, __xc_a; First
0x140001357  call    _initterm_0
0x14000135c  mov     cs:__scrt_current_native_startup_state, 2
0x140001366  jmp     short loc_140001370
0x140001368  mov     dil, 1
0x14000136b  mov     [rsp+38h+var_18], dil
0x140001370  mov     cl, bl
0x140001372  call    __scrt_release_startup_lock
0x140001377  call    __scrt_get_dyn_tls_init_callback
0x14000137c  mov     rbx, rax
0x14000137f  cmp     qword ptr [rax], 0
0x140001383  jz      short loc_1400013A2
0x140001385  mov     rcx, rax
0x140001388  call    __scrt_is_nonwritable_in_current_image
0x14000138d  test    al, al
0x14000138f  jz      short loc_1400013A2
0x140001391  xor     r8d, r8d
0x140001394  lea     edx, [r8+2]
0x140001398  xor     ecx, ecx
0x14000139a  mov     rax, [rbx]
0x14000139d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400013a2  call    __scrt_get_dyn_tls_dtor_callback
0x1400013a7  mov     rbx, rax
0x1400013aa  cmp     qword ptr [rax], 0
0x1400013ae  jz      short loc_1400013C4
0x1400013b0  mov     rcx, rax
0x1400013b3  call    __scrt_is_nonwritable_in_current_image
0x1400013b8  test    al, al
0x1400013ba  jz      short loc_1400013C4
0x1400013bc  mov     rcx, [rbx]; Callback
0x1400013bf  call    _register_thread_local_exe_atexit_callback_0
0x1400013c4  call    __scrt_get_show_window_mode
0x1400013c9  movzx   ebx, ax
0x1400013cc  call    _o__get_wide_winmain_command_line_0
0x1400013d1  mov     r9d, ebx; nShowCmd
0x1400013d4  mov     r8, rax; lpCmdLine
0x1400013d7  xor     edx, edx; hPrevInstance
0x1400013d9  lea     rcx, __ImageBase; hInstance
0x1400013e0  call    wWinMain
0x1400013e5  mov     ebx, eax
0x1400013e7  call    __scrt_is_managed_app
0x1400013ec  test    al, al
0x1400013ee  jz      short loc_140001440
0x1400013f0  test    dil, dil
0x1400013f3  jnz     short loc_1400013FA
0x1400013f5  call    _o__cexit_0
0x1400013fa  xor     edx, edx
0x1400013fc  mov     cl, 1
0x1400013fe  call    __scrt_uninitialize_crt
0x140001403  mov     eax, ebx
0x140001405  jmp     short loc_140001420
0x140001407  mov     ebx, eax
0x140001409  call    __scrt_is_managed_app
0x14000140e  test    al, al
0x140001410  jz      short loc_140001448
0x140001412  cmp     [rsp+38h+var_18], 0
0x140001417  jnz     short loc_14000141E
0x140001419  call    _c_exit_0
0x14000141e  mov     eax, ebx
0x140001420  mov     rbx, [rsp+38h+arg_0]
0x140001425  add     rsp, 30h
0x140001429  pop     rdi
0x14000142a  retn
0x14000142b  mov     ecx, 7
0x140001430  call    __scrt_fastfail
0x140001436  mov     ecx, 7
0x14000143b  call    __scrt_fastfail
0x140001440  mov     ecx, ebx; Code
0x140001442  call    _o_exit_0
0x140001448  mov     ecx, ebx
0x14000144a  call    _o__exit_0
0x14000144f  nop
0x14000670c  push    rbp
0x14000670e  sub     rsp, 20h
0x140006712  mov     rbp, rdx
0x140006715  mov     rdx, rcx; ExceptionPtr
0x140006718  mov     rcx, [rcx]
0x14000671b  mov     ecx, [rcx]; ExceptionNum
0x14000671d  call    _seh_filter_exe
0x140006722  nop
0x140006723  add     rsp, 20h
0x140006727  pop     rbp
0x140006728  retn
```
