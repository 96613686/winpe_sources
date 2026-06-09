# __scrt_common_main_seh

- ea: `0x1400011e0`
- end: `0x140001350`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001360`

## callees

- `0x1400011e0`
- `0x1400013e0`
- `0x140001420`
- `0x1400014f4`
- `0x140001594`
- `0x1400015c0`
- `0x14000175c`
- `0x14000176c`
- `0x14000177c`
- `0x140001788`
- `0x1400017d4`
- `0x140001bd6`
- `0x140001be2`
- `0x140001bee`
- `0x140001bfa`
- `0x140001c36`
- `0x140001c66`
- `0x140001c72`
- `0x140001ca2`
- `0x140001cd2`
- `0x14000ccb8`
- `0x14000f010`

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
  v14 = wWinMain((HINSTANCE)0x140000000LL, 0, wide_winmain_command_line_0, show_window_mode);
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
0x1400011e0  mov     [rsp+arg_0], rbx
0x1400011e5  push    rdi
0x1400011e6  sub     rsp, 30h
0x1400011ea  mov     ecx, 1
0x1400011ef  call    __scrt_initialize_crt
0x1400011f4  test    al, al
0x1400011f6  jz      loc_14000132B
0x1400011fc  xor     dil, dil
0x1400011ff  mov     [rsp+38h+var_18], dil
0x140001204  call    __scrt_acquire_startup_lock
0x140001209  mov     bl, al
0x14000120b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001211  cmp     ecx, 1
0x140001214  jz      loc_140001336
0x14000121a  test    ecx, ecx
0x14000121c  jnz     short loc_140001268
0x14000121e  mov     cs:__scrt_current_native_startup_state, 1
0x140001228  lea     rdx, __xi_z; Last
0x14000122f  lea     rcx, __xi_a; First
0x140001236  call    _initterm_e_0
0x14000123b  test    eax, eax
0x14000123d  jz      short loc_140001249
0x14000123f  mov     eax, 0FFh
0x140001244  jmp     loc_140001320
0x140001249  lea     rdx, __xc_z; Last
0x140001250  lea     rcx, __xc_a; First
0x140001257  call    _initterm_0
0x14000125c  mov     cs:__scrt_current_native_startup_state, 2
0x140001266  jmp     short loc_140001270
0x140001268  mov     dil, 1
0x14000126b  mov     [rsp+38h+var_18], dil
0x140001270  mov     cl, bl
0x140001272  call    __scrt_release_startup_lock
0x140001277  call    __scrt_get_dyn_tls_init_callback
0x14000127c  mov     rbx, rax
0x14000127f  cmp     qword ptr [rax], 0
0x140001283  jz      short loc_1400012A2
0x140001285  mov     rcx, rax
0x140001288  call    __scrt_is_nonwritable_in_current_image
0x14000128d  test    al, al
0x14000128f  jz      short loc_1400012A2
0x140001291  xor     r8d, r8d
0x140001294  lea     edx, [r8+2]
0x140001298  xor     ecx, ecx
0x14000129a  mov     rax, [rbx]
0x14000129d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400012a2  call    __scrt_get_dyn_tls_dtor_callback
0x1400012a7  mov     rbx, rax
0x1400012aa  cmp     qword ptr [rax], 0
0x1400012ae  jz      short loc_1400012C4
0x1400012b0  mov     rcx, rax
0x1400012b3  call    __scrt_is_nonwritable_in_current_image
0x1400012b8  test    al, al
0x1400012ba  jz      short loc_1400012C4
0x1400012bc  mov     rcx, [rbx]; Callback
0x1400012bf  call    _register_thread_local_exe_atexit_callback_0
0x1400012c4  call    __scrt_get_show_window_mode
0x1400012c9  movzx   ebx, ax
0x1400012cc  call    _o__get_wide_winmain_command_line_0
0x1400012d1  mov     r9d, ebx; nShowCmd
0x1400012d4  mov     r8, rax; lpCmdLine
0x1400012d7  xor     edx, edx; hPrevInstance
0x1400012d9  lea     rcx, cs:140000000h; hInstance
0x1400012e0  call    wWinMain
0x1400012e5  mov     ebx, eax
0x1400012e7  call    __scrt_is_managed_app
0x1400012ec  test    al, al
0x1400012ee  jz      short loc_140001340
0x1400012f0  test    dil, dil
0x1400012f3  jnz     short loc_1400012FA
0x1400012f5  call    _o__cexit_0
0x1400012fa  xor     edx, edx
0x1400012fc  mov     cl, 1
0x1400012fe  call    __scrt_uninitialize_crt
0x140001303  mov     eax, ebx
0x140001305  jmp     short loc_140001320
0x140001307  mov     ebx, eax
0x140001309  call    __scrt_is_managed_app
0x14000130e  test    al, al
0x140001310  jz      short loc_140001348
0x140001312  cmp     [rsp+38h+var_18], 0
0x140001317  jnz     short loc_14000131E
0x140001319  call    _c_exit_0
0x14000131e  mov     eax, ebx
0x140001320  mov     rbx, [rsp+38h+arg_0]
0x140001325  add     rsp, 30h
0x140001329  pop     rdi
0x14000132a  retn
0x14000132b  mov     ecx, 7
0x140001330  call    __scrt_fastfail
0x140001336  mov     ecx, 7
0x14000133b  call    __scrt_fastfail
0x140001340  mov     ecx, ebx; Code
0x140001342  call    _o_exit_0
0x140001348  mov     ecx, ebx
0x14000134a  call    _o__exit_0
0x14000134f  nop
0x14000e45c  push    rbp
0x14000e45e  sub     rsp, 20h
0x14000e462  mov     rbp, rdx
0x14000e465  mov     rdx, rcx; ExceptionPtr
0x14000e468  mov     rcx, [rcx]
0x14000e46b  mov     ecx, [rcx]; ExceptionNum
0x14000e46d  call    _seh_filter_exe
0x14000e472  nop
0x14000e473  add     rsp, 20h
0x14000e477  pop     rbp
0x14000e478  retn
```
