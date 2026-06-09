# __scrt_common_main_seh

- ea: `0x1400022d0`
- end: `0x140002440`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140002450`

## callees

- `0x1400022d0`
- `0x1400024a4`
- `0x1400024e4`
- `0x1400025b8`
- `0x140002658`
- `0x140002684`
- `0x140002900`
- `0x140002910`
- `0x140002920`
- `0x14000292c`
- `0x140002978`
- `0x140002dd6`
- `0x140002de2`
- `0x140002dee`
- `0x140002dfa`
- `0x140002e66`
- `0x140002e96`
- `0x140002ea2`
- `0x140002ef8`
- `0x140002f34`
- `0x140012f54`
- `0x140029010`

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
0x1400022d0  mov     [rsp+arg_0], rbx
0x1400022d5  push    rdi
0x1400022d6  sub     rsp, 30h
0x1400022da  mov     ecx, 1
0x1400022df  call    __scrt_initialize_crt
0x1400022e4  test    al, al
0x1400022e6  jz      loc_14000241B
0x1400022ec  xor     dil, dil
0x1400022ef  mov     [rsp+38h+var_18], dil
0x1400022f4  call    __scrt_acquire_startup_lock
0x1400022f9  mov     bl, al
0x1400022fb  mov     ecx, cs:__scrt_current_native_startup_state
0x140002301  cmp     ecx, 1
0x140002304  jz      loc_140002426
0x14000230a  test    ecx, ecx
0x14000230c  jnz     short loc_140002358
0x14000230e  mov     cs:__scrt_current_native_startup_state, 1
0x140002318  lea     rdx, __xi_z; Last
0x14000231f  lea     rcx, __xi_a; First
0x140002326  call    _initterm_e_0
0x14000232b  test    eax, eax
0x14000232d  jz      short loc_140002339
0x14000232f  mov     eax, 0FFh
0x140002334  jmp     loc_140002410
0x140002339  lea     rdx, __xc_z; Last
0x140002340  lea     rcx, __xc_a; First
0x140002347  call    _initterm_0
0x14000234c  mov     cs:__scrt_current_native_startup_state, 2
0x140002356  jmp     short loc_140002360
0x140002358  mov     dil, 1
0x14000235b  mov     [rsp+38h+var_18], dil
0x140002360  mov     cl, bl
0x140002362  call    __scrt_release_startup_lock
0x140002367  call    __scrt_get_dyn_tls_init_callback
0x14000236c  mov     rbx, rax
0x14000236f  cmp     qword ptr [rax], 0
0x140002373  jz      short loc_140002392
0x140002375  mov     rcx, rax
0x140002378  call    __scrt_is_nonwritable_in_current_image
0x14000237d  test    al, al
0x14000237f  jz      short loc_140002392
0x140002381  xor     r8d, r8d
0x140002384  lea     edx, [r8+2]
0x140002388  xor     ecx, ecx
0x14000238a  mov     rax, [rbx]
0x14000238d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002392  call    __scrt_get_dyn_tls_dtor_callback
0x140002397  mov     rbx, rax
0x14000239a  cmp     qword ptr [rax], 0
0x14000239e  jz      short loc_1400023B4
0x1400023a0  mov     rcx, rax
0x1400023a3  call    __scrt_is_nonwritable_in_current_image
0x1400023a8  test    al, al
0x1400023aa  jz      short loc_1400023B4
0x1400023ac  mov     rcx, [rbx]; Callback
0x1400023af  call    _register_thread_local_exe_atexit_callback_0
0x1400023b4  call    __scrt_get_show_window_mode
0x1400023b9  movzx   ebx, ax
0x1400023bc  call    _o__get_wide_winmain_command_line_0
0x1400023c1  mov     r9d, ebx; nShowCmd
0x1400023c4  mov     r8, rax; lpCmdLine
0x1400023c7  xor     edx, edx; hPrevInstance
0x1400023c9  lea     rcx, __ImageBase; hInstance
0x1400023d0  call    wWinMain
0x1400023d5  mov     ebx, eax
0x1400023d7  call    __scrt_is_managed_app
0x1400023dc  test    al, al
0x1400023de  jz      short loc_140002430
0x1400023e0  test    dil, dil
0x1400023e3  jnz     short loc_1400023EA
0x1400023e5  call    _o__cexit_0
0x1400023ea  xor     edx, edx
0x1400023ec  mov     cl, 1
0x1400023ee  call    __scrt_uninitialize_crt
0x1400023f3  mov     eax, ebx
0x1400023f5  jmp     short loc_140002410
0x1400023f7  mov     ebx, eax
0x1400023f9  call    __scrt_is_managed_app
0x1400023fe  test    al, al
0x140002400  jz      short loc_140002438
0x140002402  cmp     [rsp+38h+var_18], 0
0x140002407  jnz     short loc_14000240E
0x140002409  call    _c_exit_0
0x14000240e  mov     eax, ebx
0x140002410  mov     rbx, [rsp+38h+arg_0]
0x140002415  add     rsp, 30h
0x140002419  pop     rdi
0x14000241a  retn
0x14000241b  mov     ecx, 7
0x140002420  call    __scrt_fastfail
0x140002426  mov     ecx, 7
0x14000242b  call    __scrt_fastfail
0x140002430  mov     ecx, ebx; Code
0x140002432  call    _o_exit_0
0x140002438  mov     ecx, ebx
0x14000243a  call    _o__exit_0
0x14000243f  nop
0x140026abc  push    rbp
0x140026abe  sub     rsp, 20h
0x140026ac2  mov     rbp, rdx
0x140026ac5  mov     rdx, rcx; ExceptionPtr
0x140026ac8  mov     rcx, [rcx]
0x140026acb  mov     ecx, [rcx]; ExceptionNum
0x140026acd  call    _seh_filter_exe
0x140026ad2  nop
0x140026ad3  add     rsp, 20h
0x140026ad7  pop     rbp
0x140026ad8  retn
```
