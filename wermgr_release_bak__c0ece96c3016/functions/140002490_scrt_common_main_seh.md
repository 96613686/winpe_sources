# __scrt_common_main_seh

- ea: `0x140002490`
- end: `0x140002600`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140002610`

## callees

- `0x140002490`
- `0x140002628`
- `0x140002668`
- `0x14000273c`
- `0x1400027dc`
- `0x140002808`
- `0x1400029b0`
- `0x1400029c0`
- `0x1400029d0`
- `0x1400029dc`
- `0x140002a28`
- `0x140002e36`
- `0x140002e42`
- `0x140002e4e`
- `0x140002e5a`
- `0x140002eae`
- `0x140002ede`
- `0x140002eea`
- `0x140002f38`
- `0x140002f68`
- `0x14000e49c`
- `0x14001e010`

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
  CHAR *narrow_winmain_command_line_0; // rax
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
  narrow_winmain_command_line_0 = (CHAR *)o__get_narrow_winmain_command_line_0();
  v14 = WinMain(&_ImageBase, 0, narrow_winmain_command_line_0, show_window_mode);
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
0x140002490  mov     [rsp+arg_0], rbx
0x140002495  push    rdi
0x140002496  sub     rsp, 30h
0x14000249a  mov     ecx, 1
0x14000249f  call    __scrt_initialize_crt
0x1400024a4  test    al, al
0x1400024a6  jz      loc_1400025DB
0x1400024ac  xor     dil, dil
0x1400024af  mov     [rsp+38h+var_18], dil
0x1400024b4  call    __scrt_acquire_startup_lock
0x1400024b9  mov     bl, al
0x1400024bb  mov     ecx, cs:__scrt_current_native_startup_state
0x1400024c1  cmp     ecx, 1
0x1400024c4  jz      loc_1400025E6
0x1400024ca  test    ecx, ecx
0x1400024cc  jnz     short loc_140002518
0x1400024ce  mov     cs:__scrt_current_native_startup_state, 1
0x1400024d8  lea     rdx, __xi_z; Last
0x1400024df  lea     rcx, __xi_a; First
0x1400024e6  call    _initterm_e_0
0x1400024eb  test    eax, eax
0x1400024ed  jz      short loc_1400024F9
0x1400024ef  mov     eax, 0FFh
0x1400024f4  jmp     loc_1400025D0
0x1400024f9  lea     rdx, __xc_z; Last
0x140002500  lea     rcx, __xc_a; First
0x140002507  call    _initterm_0
0x14000250c  mov     cs:__scrt_current_native_startup_state, 2
0x140002516  jmp     short loc_140002520
0x140002518  mov     dil, 1
0x14000251b  mov     [rsp+38h+var_18], dil
0x140002520  mov     cl, bl
0x140002522  call    __scrt_release_startup_lock
0x140002527  call    __scrt_get_dyn_tls_init_callback
0x14000252c  mov     rbx, rax
0x14000252f  cmp     qword ptr [rax], 0
0x140002533  jz      short loc_140002552
0x140002535  mov     rcx, rax
0x140002538  call    __scrt_is_nonwritable_in_current_image
0x14000253d  test    al, al
0x14000253f  jz      short loc_140002552
0x140002541  xor     r8d, r8d
0x140002544  lea     edx, [r8+2]
0x140002548  xor     ecx, ecx
0x14000254a  mov     rax, [rbx]
0x14000254d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002552  call    __scrt_get_dyn_tls_dtor_callback
0x140002557  mov     rbx, rax
0x14000255a  cmp     qword ptr [rax], 0
0x14000255e  jz      short loc_140002574
0x140002560  mov     rcx, rax
0x140002563  call    __scrt_is_nonwritable_in_current_image
0x140002568  test    al, al
0x14000256a  jz      short loc_140002574
0x14000256c  mov     rcx, [rbx]; Callback
0x14000256f  call    _register_thread_local_exe_atexit_callback_0
0x140002574  call    __scrt_get_show_window_mode
0x140002579  movzx   ebx, ax
0x14000257c  call    _o__get_narrow_winmain_command_line_0
0x140002581  mov     r9d, ebx; nShowCmd
0x140002584  mov     r8, rax; lpCmdLine
0x140002587  xor     edx, edx; hPrevInstance
0x140002589  lea     rcx, __ImageBase; hInstance
0x140002590  call    WinMain
0x140002595  mov     ebx, eax
0x140002597  call    __scrt_is_managed_app
0x14000259c  test    al, al
0x14000259e  jz      short loc_1400025F0
0x1400025a0  test    dil, dil
0x1400025a3  jnz     short loc_1400025AA
0x1400025a5  call    _o__cexit_0
0x1400025aa  xor     edx, edx
0x1400025ac  mov     cl, 1
0x1400025ae  call    __scrt_uninitialize_crt
0x1400025b3  mov     eax, ebx
0x1400025b5  jmp     short loc_1400025D0
0x1400025b7  mov     ebx, eax
0x1400025b9  call    __scrt_is_managed_app
0x1400025be  test    al, al
0x1400025c0  jz      short loc_1400025F8
0x1400025c2  cmp     [rsp+38h+var_18], 0
0x1400025c7  jnz     short loc_1400025CE
0x1400025c9  call    _c_exit_0
0x1400025ce  mov     eax, ebx
0x1400025d0  mov     rbx, [rsp+38h+arg_0]
0x1400025d5  add     rsp, 30h
0x1400025d9  pop     rdi
0x1400025da  retn
0x1400025db  mov     ecx, 7
0x1400025e0  call    __scrt_fastfail
0x1400025e6  mov     ecx, 7
0x1400025eb  call    __scrt_fastfail
0x1400025f0  mov     ecx, ebx; Code
0x1400025f2  call    _o_exit_0
0x1400025f8  mov     ecx, ebx
0x1400025fa  call    _o__exit_0
0x1400025ff  nop
0x14001ca2c  push    rbp
0x14001ca2e  sub     rsp, 20h
0x14001ca32  mov     rbp, rdx
0x14001ca35  mov     rdx, rcx; ExceptionPtr
0x14001ca38  mov     rcx, [rcx]
0x14001ca3b  mov     ecx, [rcx]; ExceptionNum
0x14001ca3d  call    _seh_filter_exe
0x14001ca42  nop
0x14001ca43  add     rsp, 20h
0x14001ca47  pop     rbp
0x14001ca48  retn
```
