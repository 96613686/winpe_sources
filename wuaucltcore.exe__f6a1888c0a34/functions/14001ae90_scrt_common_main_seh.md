# __scrt_common_main_seh

- ea: `0x14001ae90`
- end: `0x14001b000`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14001b010`

## callees

- `0x1400080bc`
- `0x14001a913`
- `0x14001a94f`
- `0x14001a967`
- `0x14001a9b8`
- `0x14001aa00`
- `0x14001aa84`
- `0x14001aac4`
- `0x14001ab98`
- `0x14001ac38`
- `0x14001ac64`
- `0x14001ae90`
- `0x14001b4b4`
- `0x14001b628`
- `0x14001b674`
- `0x14001b8ac`
- `0x14001b8bc`
- `0x1400202c8`
- `0x1400202d4`
- `0x1400202e0`
- `0x1400202ec`
- `0x1400206e0`

## pseudocode

```c
__int64 __fastcall _scrt_common_main_seh()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  char v2; // di
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
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    _scrt_fastfail(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
  {
LABEL_19:
    _scrt_fastfail(7);
    goto LABEL_20;
  }
  if ( _scrt_current_native_startup_state )
  {
    v2 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v0;
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
  v0 = wWinMain(&_ImageBase, 0, wide_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    o_exit_0(v0);
  if ( !v2 )
    o__cexit_0(v15);
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x14001ae90  mov     [rsp+arg_0], rbx
0x14001ae95  push    rdi
0x14001ae96  sub     rsp, 30h
0x14001ae9a  mov     ecx, 1
0x14001ae9f  call    __scrt_initialize_crt
0x14001aea4  test    al, al
0x14001aea6  jz      loc_14001AFDB
0x14001aeac  xor     dil, dil
0x14001aeaf  mov     [rsp+38h+var_18], dil
0x14001aeb4  call    __scrt_acquire_startup_lock
0x14001aeb9  mov     bl, al
0x14001aebb  mov     ecx, cs:__scrt_current_native_startup_state
0x14001aec1  cmp     ecx, 1
0x14001aec4  jz      loc_14001AFE6
0x14001aeca  test    ecx, ecx
0x14001aecc  jnz     short loc_14001AF18
0x14001aece  mov     cs:__scrt_current_native_startup_state, 1
0x14001aed8  lea     rdx, __xi_z; Last
0x14001aedf  lea     rcx, __xi_a; First
0x14001aee6  call    _initterm_e_0
0x14001aeeb  test    eax, eax
0x14001aeed  jz      short loc_14001AEF9
0x14001aeef  mov     eax, 0FFh
0x14001aef4  jmp     loc_14001AFD0
0x14001aef9  lea     rdx, __xc_z; Last
0x14001af00  lea     rcx, __xc_a; First
0x14001af07  call    _initterm_0
0x14001af0c  mov     cs:__scrt_current_native_startup_state, 2
0x14001af16  jmp     short loc_14001AF20
0x14001af18  mov     dil, 1
0x14001af1b  mov     [rsp+38h+var_18], dil
0x14001af20  mov     cl, bl
0x14001af22  call    __scrt_release_startup_lock
0x14001af27  call    __scrt_get_dyn_tls_init_callback
0x14001af2c  mov     rbx, rax
0x14001af2f  cmp     qword ptr [rax], 0
0x14001af33  jz      short loc_14001AF52
0x14001af35  mov     rcx, rax
0x14001af38  call    __scrt_is_nonwritable_in_current_image
0x14001af3d  test    al, al
0x14001af3f  jz      short loc_14001AF52
0x14001af41  xor     r8d, r8d
0x14001af44  lea     edx, [r8+2]
0x14001af48  xor     ecx, ecx
0x14001af4a  mov     rax, [rbx]
0x14001af4d  call    _guard_dispatch_icall
0x14001af52  call    __scrt_get_dyn_tls_dtor_callback
0x14001af57  mov     rbx, rax
0x14001af5a  cmp     qword ptr [rax], 0
0x14001af5e  jz      short loc_14001AF74
0x14001af60  mov     rcx, rax
0x14001af63  call    __scrt_is_nonwritable_in_current_image
0x14001af68  test    al, al
0x14001af6a  jz      short loc_14001AF74
0x14001af6c  mov     rcx, [rbx]; Callback
0x14001af6f  call    _register_thread_local_exe_atexit_callback_0
0x14001af74  call    __scrt_get_show_window_mode
0x14001af79  movzx   ebx, ax
0x14001af7c  call    _o__get_wide_winmain_command_line_0
0x14001af81  mov     r9d, ebx; nShowCmd
0x14001af84  mov     r8, rax; lpCmdLine
0x14001af87  xor     edx, edx; hPrevInstance
0x14001af89  lea     rcx, __ImageBase; hInstance
0x14001af90  call    wWinMain
0x14001af95  mov     ebx, eax
0x14001af97  call    __scrt_is_managed_app
0x14001af9c  test    al, al
0x14001af9e  jz      short loc_14001AFF0
0x14001afa0  test    dil, dil
0x14001afa3  jnz     short loc_14001AFAA
0x14001afa5  call    _o__cexit_0
0x14001afaa  xor     edx, edx
0x14001afac  mov     cl, 1
0x14001afae  call    __scrt_uninitialize_crt
0x14001afb3  mov     eax, ebx
0x14001afb5  jmp     short loc_14001AFD0
0x14001afb7  mov     ebx, eax
0x14001afb9  call    __scrt_is_managed_app
0x14001afbe  test    al, al
0x14001afc0  jz      short loc_14001AFF8
0x14001afc2  cmp     [rsp+38h+var_18], 0
0x14001afc7  jnz     short loc_14001AFCE
0x14001afc9  call    _c_exit_0
0x14001afce  mov     eax, ebx
0x14001afd0  mov     rbx, [rsp+38h+arg_0]
0x14001afd5  add     rsp, 30h
0x14001afd9  pop     rdi
0x14001afda  retn
0x14001afdb  mov     ecx, 7
0x14001afe0  call    __scrt_fastfail
0x14001afe5  nop
0x14001afe6  mov     ecx, 7
0x14001afeb  call    __scrt_fastfail
0x14001aff0  mov     ecx, ebx; Code
0x14001aff2  call    _o_exit_0
0x14001aff8  mov     ecx, ebx
0x14001affa  call    _o__exit_0
0x14001afff  nop
0x140021b76  push    rbp
0x140021b78  sub     rsp, 20h
0x140021b7c  mov     rbp, rdx
0x140021b7f  mov     rdx, rcx; ExceptionPtr
0x140021b82  mov     rcx, [rcx]
0x140021b85  mov     ecx, [rcx]; ExceptionNum
0x140021b87  call    _seh_filter_exe
0x140021b8c  nop
0x140021b8d  add     rsp, 20h
0x140021b91  pop     rbp
0x140021b92  retn
```
