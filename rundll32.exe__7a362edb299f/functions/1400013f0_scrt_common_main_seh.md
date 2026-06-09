# __scrt_common_main_seh

- ea: `0x1400013f0`
- end: `0x140001560`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001570`

## callees

- `0x1400013f0`
- `0x1400015e8`
- `0x140001628`
- `0x1400016fc`
- `0x14000179c`
- `0x1400017c8`
- `0x140001994`
- `0x1400019a4`
- `0x1400019b4`
- `0x1400019c0`
- `0x140001a0c`
- `0x1400020bc`
- `0x1400020c8`
- `0x1400020d4`
- `0x1400020e0`
- `0x140002128`
- `0x140002158`
- `0x140002164`
- `0x1400021b8`
- `0x1400021e8`
- `0x140007798`
- `0x14000c010`

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
  __int64 v9; // rcx
  _tls_callback_type *v10; // rbx
  int show_window_mode; // ebx
  __int64 v12; // rcx
  WCHAR *wide_winmain_command_line_0; // rax

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
    v10 = dyn_tls_dtor_callback;
    if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
      register_thread_local_exe_atexit_callback_0(*v10);
    show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v9);
    wide_winmain_command_line_0 = (WCHAR *)o__get_wide_winmain_command_line_0(v12);
    wWinMain(&_ImageBase, 0, wide_winmain_command_line_0, show_window_mode);
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
0x1400013f0  mov     [rsp+arg_0], rbx
0x1400013f5  push    rdi
0x1400013f6  sub     rsp, 30h
0x1400013fa  mov     ecx, 1
0x1400013ff  call    __scrt_initialize_crt
0x140001404  test    al, al
0x140001406  jz      loc_14000153B
0x14000140c  xor     dil, dil
0x14000140f  mov     [rsp+38h+var_18], dil
0x140001414  call    __scrt_acquire_startup_lock
0x140001419  mov     bl, al
0x14000141b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001421  cmp     ecx, 1
0x140001424  jz      loc_140001546
0x14000142a  test    ecx, ecx
0x14000142c  jnz     short loc_140001478
0x14000142e  mov     cs:__scrt_current_native_startup_state, 1
0x140001438  lea     rdx, __xi_z; Last
0x14000143f  lea     rcx, __xi_a; First
0x140001446  call    _initterm_e_0
0x14000144b  test    eax, eax
0x14000144d  jz      short loc_140001459
0x14000144f  mov     eax, 0FFh
0x140001454  jmp     loc_140001530
0x140001459  lea     rdx, __xc_z; Last
0x140001460  lea     rcx, __xc_a; First
0x140001467  call    _initterm_0
0x14000146c  mov     cs:__scrt_current_native_startup_state, 2
0x140001476  jmp     short loc_140001480
0x140001478  mov     dil, 1
0x14000147b  mov     [rsp+38h+var_18], dil
0x140001480  mov     cl, bl
0x140001482  call    __scrt_release_startup_lock
0x140001487  call    __scrt_get_dyn_tls_init_callback
0x14000148c  mov     rbx, rax
0x14000148f  cmp     qword ptr [rax], 0
0x140001493  jz      short loc_1400014B2
0x140001495  mov     rcx, rax
0x140001498  call    __scrt_is_nonwritable_in_current_image
0x14000149d  test    al, al
0x14000149f  jz      short loc_1400014B2
0x1400014a1  xor     r8d, r8d
0x1400014a4  lea     edx, [r8+2]
0x1400014a8  xor     ecx, ecx
0x1400014aa  mov     rax, [rbx]
0x1400014ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400014b2  call    __scrt_get_dyn_tls_dtor_callback
0x1400014b7  mov     rbx, rax
0x1400014ba  cmp     qword ptr [rax], 0
0x1400014be  jz      short loc_1400014D4
0x1400014c0  mov     rcx, rax
0x1400014c3  call    __scrt_is_nonwritable_in_current_image
0x1400014c8  test    al, al
0x1400014ca  jz      short loc_1400014D4
0x1400014cc  mov     rcx, [rbx]; Callback
0x1400014cf  call    _register_thread_local_exe_atexit_callback_0
0x1400014d4  call    __scrt_get_show_window_mode
0x1400014d9  movzx   ebx, ax
0x1400014dc  call    _o__get_wide_winmain_command_line_0
0x1400014e1  mov     r9d, ebx; nShowCmd
0x1400014e4  mov     r8, rax; lpCmdLine
0x1400014e7  xor     edx, edx; hPrevInstance
0x1400014e9  lea     rcx, __ImageBase; hInstance
0x1400014f0  call    wWinMain
0x1400014f5  mov     ebx, eax
0x1400014f7  call    __scrt_is_managed_app
0x1400014fc  test    al, al
0x1400014fe  jz      short loc_140001550
0x140001500  test    dil, dil
0x140001503  jnz     short loc_14000150A
0x140001505  call    _o__cexit_0
0x14000150a  xor     edx, edx
0x14000150c  mov     cl, 1
0x14000150e  call    __scrt_uninitialize_crt
0x140001513  mov     eax, ebx
0x140001515  jmp     short loc_140001530
0x140001517  mov     ebx, eax
0x140001519  call    __scrt_is_managed_app
0x14000151e  test    al, al
0x140001520  jz      short loc_140001558
0x140001522  cmp     [rsp+38h+var_18], 0
0x140001527  jnz     short loc_14000152E
0x140001529  call    _c_exit_0
0x14000152e  mov     eax, ebx
0x140001530  mov     rbx, [rsp+38h+arg_0]
0x140001535  add     rsp, 30h
0x140001539  pop     rdi
0x14000153a  retn
0x14000153b  mov     ecx, 7
0x140001540  call    __scrt_fastfail
0x140001546  mov     ecx, 7
0x14000154b  call    __scrt_fastfail
0x140001550  mov     ecx, ebx; Code
0x140001552  call    _o_exit_0
0x140001558  mov     ecx, ebx
0x14000155a  call    _o__exit_0
0x14000155f  nop
0x14000b25c  push    rbp
0x14000b25e  sub     rsp, 20h
0x14000b262  mov     rbp, rdx
0x14000b265  mov     rdx, rcx; ExceptionPtr
0x14000b268  mov     rcx, [rcx]
0x14000b26b  mov     ecx, [rcx]; ExceptionNum
0x14000b26d  call    _seh_filter_exe
0x14000b272  nop
0x14000b273  add     rsp, 20h
0x14000b277  pop     rbp
0x14000b278  retn
```
