# __scrt_common_main_seh

- ea: `0x140001f70`
- end: `0x1400020e0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400020f0`

## callees

- `0x140001f70`
- `0x140002144`
- `0x140002184`
- `0x140002258`
- `0x1400022f8`
- `0x140002324`
- `0x1400025e4`
- `0x1400025f4`
- `0x140002604`
- `0x140002610`
- `0x14000265c`
- `0x140002ae6`
- `0x140002af2`
- `0x140002afe`
- `0x140002b0a`
- `0x140002b6a`
- `0x140002b9a`
- `0x140002ba6`
- `0x140002bf8`
- `0x140002c28`
- `0x14000a678`
- `0x14000c010`

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
  v15 = wWinMain((HINSTANCE)0x140000000LL, 0, wide_winmain_command_line_0, show_window_mode);
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
0x140001f70  mov     [rsp+arg_0], rbx
0x140001f75  push    rdi
0x140001f76  sub     rsp, 30h
0x140001f7a  mov     ecx, 1
0x140001f7f  call    __scrt_initialize_crt
0x140001f84  test    al, al
0x140001f86  jz      loc_1400020BB
0x140001f8c  xor     dil, dil
0x140001f8f  mov     [rsp+38h+var_18], dil
0x140001f94  call    __scrt_acquire_startup_lock
0x140001f99  mov     bl, al
0x140001f9b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001fa1  cmp     ecx, 1
0x140001fa4  jz      loc_1400020C6
0x140001faa  test    ecx, ecx
0x140001fac  jnz     short loc_140001FF8
0x140001fae  mov     cs:__scrt_current_native_startup_state, 1
0x140001fb8  lea     rdx, __xi_z; Last
0x140001fbf  lea     rcx, __xi_a; First
0x140001fc6  call    _initterm_e_0
0x140001fcb  test    eax, eax
0x140001fcd  jz      short loc_140001FD9
0x140001fcf  mov     eax, 0FFh
0x140001fd4  jmp     loc_1400020B0
0x140001fd9  lea     rdx, __xc_z; Last
0x140001fe0  lea     rcx, __xc_a; First
0x140001fe7  call    _initterm_0
0x140001fec  mov     cs:__scrt_current_native_startup_state, 2
0x140001ff6  jmp     short loc_140002000
0x140001ff8  mov     dil, 1
0x140001ffb  mov     [rsp+38h+var_18], dil
0x140002000  mov     cl, bl
0x140002002  call    __scrt_release_startup_lock
0x140002007  call    __scrt_get_dyn_tls_init_callback
0x14000200c  mov     rbx, rax
0x14000200f  cmp     qword ptr [rax], 0
0x140002013  jz      short loc_140002032
0x140002015  mov     rcx, rax
0x140002018  call    __scrt_is_nonwritable_in_current_image
0x14000201d  test    al, al
0x14000201f  jz      short loc_140002032
0x140002021  xor     r8d, r8d
0x140002024  lea     edx, [r8+2]
0x140002028  xor     ecx, ecx
0x14000202a  mov     rax, [rbx]
0x14000202d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002032  call    __scrt_get_dyn_tls_dtor_callback
0x140002037  mov     rbx, rax
0x14000203a  cmp     qword ptr [rax], 0
0x14000203e  jz      short loc_140002054
0x140002040  mov     rcx, rax
0x140002043  call    __scrt_is_nonwritable_in_current_image
0x140002048  test    al, al
0x14000204a  jz      short loc_140002054
0x14000204c  mov     rcx, [rbx]; Callback
0x14000204f  call    _register_thread_local_exe_atexit_callback_0
0x140002054  call    __scrt_get_show_window_mode
0x140002059  movzx   ebx, ax
0x14000205c  call    _o__get_wide_winmain_command_line_0
0x140002061  mov     r9d, ebx; nShowCmd
0x140002064  mov     r8, rax; lpCmdLine
0x140002067  xor     edx, edx; hPrevInstance
0x140002069  lea     rcx, cs:140000000h; hInstance
0x140002070  call    wWinMain
0x140002075  mov     ebx, eax
0x140002077  call    __scrt_is_managed_app
0x14000207c  test    al, al
0x14000207e  jz      short loc_1400020D0
0x140002080  test    dil, dil
0x140002083  jnz     short loc_14000208A
0x140002085  call    _o__cexit_0
0x14000208a  xor     edx, edx
0x14000208c  mov     cl, 1
0x14000208e  call    __scrt_uninitialize_crt
0x140002093  mov     eax, ebx
0x140002095  jmp     short loc_1400020B0
0x140002097  mov     ebx, eax
0x140002099  call    __scrt_is_managed_app
0x14000209e  test    al, al
0x1400020a0  jz      short loc_1400020D8
0x1400020a2  cmp     [rsp+38h+var_18], 0
0x1400020a7  jnz     short loc_1400020AE
0x1400020a9  call    _c_exit_0
0x1400020ae  mov     eax, ebx
0x1400020b0  mov     rbx, [rsp+38h+arg_0]
0x1400020b5  add     rsp, 30h
0x1400020b9  pop     rdi
0x1400020ba  retn
0x1400020bb  mov     ecx, 7
0x1400020c0  call    __scrt_fastfail
0x1400020c6  mov     ecx, 7
0x1400020cb  call    __scrt_fastfail
0x1400020d0  mov     ecx, ebx; Code
0x1400020d2  call    _o_exit_0
0x1400020d8  mov     ecx, ebx
0x1400020da  call    _o__exit_0
0x1400020df  nop
0x14000acdc  push    rbp
0x14000acde  sub     rsp, 20h
0x14000ace2  mov     rbp, rdx
0x14000ace5  mov     rdx, rcx; ExceptionPtr
0x14000ace8  mov     rcx, [rcx]
0x14000aceb  mov     ecx, [rcx]; ExceptionNum
0x14000aced  call    _seh_filter_exe
0x14000acf2  nop
0x14000acf3  add     rsp, 20h
0x14000acf7  pop     rbp
0x14000acf8  retn
```
