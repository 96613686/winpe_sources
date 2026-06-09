# __scrt_common_main_seh

- ea: `0x140001620`
- end: `0x140001790`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400017a0`

## callees

- `0x140001340`
- `0x140001620`
- `0x140001974`
- `0x1400019b4`
- `0x140001a88`
- `0x140001b28`
- `0x140001b54`
- `0x140001d40`
- `0x140001d50`
- `0x140001d74`
- `0x140001ee8`
- `0x140001f34`
- `0x1400055b6`
- `0x1400055c2`
- `0x1400055ce`
- `0x1400055da`
- `0x140005616`
- `0x140005646`
- `0x14000565e`
- `0x14000568e`
- `0x1400056ca`
- `0x1400059e0`

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
  v0 = wWinMain((HINSTANCE)0x140000000LL, 0, wide_winmain_command_line_0, show_window_mode);
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
0x140001620  mov     [rsp+arg_0], rbx
0x140001625  push    rdi
0x140001626  sub     rsp, 30h
0x14000162a  mov     ecx, 1
0x14000162f  call    __scrt_initialize_crt
0x140001634  test    al, al
0x140001636  jz      loc_14000176B
0x14000163c  xor     dil, dil
0x14000163f  mov     [rsp+38h+var_18], dil
0x140001644  call    __scrt_acquire_startup_lock
0x140001649  mov     bl, al
0x14000164b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001651  cmp     ecx, 1
0x140001654  jz      loc_140001776
0x14000165a  test    ecx, ecx
0x14000165c  jnz     short loc_1400016A8
0x14000165e  mov     cs:__scrt_current_native_startup_state, 1
0x140001668  lea     rdx, __xi_z; Last
0x14000166f  lea     rcx, __xi_a; First
0x140001676  call    _initterm_e_0
0x14000167b  test    eax, eax
0x14000167d  jz      short loc_140001689
0x14000167f  mov     eax, 0FFh
0x140001684  jmp     loc_140001760
0x140001689  lea     rdx, __xc_z; Last
0x140001690  lea     rcx, __xc_a; First
0x140001697  call    _initterm_0
0x14000169c  mov     cs:__scrt_current_native_startup_state, 2
0x1400016a6  jmp     short loc_1400016B0
0x1400016a8  mov     dil, 1
0x1400016ab  mov     [rsp+38h+var_18], dil
0x1400016b0  mov     cl, bl
0x1400016b2  call    __scrt_release_startup_lock
0x1400016b7  call    __scrt_get_dyn_tls_init_callback
0x1400016bc  mov     rbx, rax
0x1400016bf  cmp     qword ptr [rax], 0
0x1400016c3  jz      short loc_1400016E2
0x1400016c5  mov     rcx, rax
0x1400016c8  call    __scrt_is_nonwritable_in_current_image
0x1400016cd  test    al, al
0x1400016cf  jz      short loc_1400016E2
0x1400016d1  xor     r8d, r8d
0x1400016d4  lea     edx, [r8+2]
0x1400016d8  xor     ecx, ecx
0x1400016da  mov     rax, [rbx]
0x1400016dd  call    _guard_dispatch_icall
0x1400016e2  call    __scrt_get_dyn_tls_dtor_callback
0x1400016e7  mov     rbx, rax
0x1400016ea  cmp     qword ptr [rax], 0
0x1400016ee  jz      short loc_140001704
0x1400016f0  mov     rcx, rax
0x1400016f3  call    __scrt_is_nonwritable_in_current_image
0x1400016f8  test    al, al
0x1400016fa  jz      short loc_140001704
0x1400016fc  mov     rcx, [rbx]; Callback
0x1400016ff  call    _register_thread_local_exe_atexit_callback_0
0x140001704  call    __scrt_get_show_window_mode
0x140001709  movzx   ebx, ax
0x14000170c  call    _o__get_wide_winmain_command_line_0
0x140001711  mov     r9d, ebx; nShowCmd
0x140001714  mov     r8, rax; lpCmdLine
0x140001717  xor     edx, edx; hPrevInstance
0x140001719  lea     rcx, cs:140000000h; hInstance
0x140001720  call    wWinMain
0x140001725  mov     ebx, eax
0x140001727  call    __scrt_is_managed_app
0x14000172c  test    al, al
0x14000172e  jz      short loc_140001780
0x140001730  test    dil, dil
0x140001733  jnz     short loc_14000173A
0x140001735  call    _o__cexit_0
0x14000173a  xor     edx, edx
0x14000173c  mov     cl, 1
0x14000173e  call    __scrt_uninitialize_crt
0x140001743  mov     eax, ebx
0x140001745  jmp     short loc_140001760
0x140001747  mov     ebx, eax
0x140001749  call    __scrt_is_managed_app
0x14000174e  test    al, al
0x140001750  jz      short loc_140001788
0x140001752  cmp     [rsp+38h+var_18], 0
0x140001757  jnz     short loc_14000175E
0x140001759  call    _c_exit_0
0x14000175e  mov     eax, ebx
0x140001760  mov     rbx, [rsp+38h+arg_0]
0x140001765  add     rsp, 30h
0x140001769  pop     rdi
0x14000176a  retn
0x14000176b  mov     ecx, 7
0x140001770  call    __scrt_fastfail
0x140001775  nop
0x140001776  mov     ecx, 7
0x14000177b  call    __scrt_fastfail
0x140001780  mov     ecx, ebx; Code
0x140001782  call    _o_exit_0
0x140001788  mov     ecx, ebx
0x14000178a  call    _o__exit_0
0x14000178f  nop
0x1400064a5  push    rbp
0x1400064a7  sub     rsp, 20h
0x1400064ab  mov     rbp, rdx
0x1400064ae  mov     rdx, rcx; ExceptionPtr
0x1400064b1  mov     rcx, [rcx]
0x1400064b4  mov     ecx, [rcx]; ExceptionNum
0x1400064b6  call    _seh_filter_exe
0x1400064bb  nop
0x1400064bc  add     rsp, 20h
0x1400064c0  pop     rbp
0x1400064c1  retn
```
