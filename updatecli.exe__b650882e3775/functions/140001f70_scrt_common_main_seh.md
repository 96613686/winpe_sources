# __scrt_common_main_seh

- ea: `0x140001f70`
- end: `0x1400020eb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002100`

## callees

- `0x140001f70`
- `0x140002154`
- `0x140002194`
- `0x140002268`
- `0x140002308`
- `0x140002334`
- `0x1400025f4`
- `0x140002604`
- `0x140002614`
- `0x14000262c`
- `0x140002ab6`
- `0x140002ac2`
- `0x140002ace`
- `0x140002ada`
- `0x140002afe`
- `0x140002b0a`
- `0x140002b52`
- `0x140002b82`
- `0x140002b8e`
- `0x140002bd8`
- `0x140002c08`
- `0x14000a6a8`
- `0x14000c010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // si
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v10; // rbx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx

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
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  get_initial_wide_environment();
  _p___wargv();
  _p___argc();
  v11 = wmain();
  if ( !(unsigned __int8)_scrt_is_managed_app(v12) )
    o_exit_0(v11);
  if ( !v1 )
    o__cexit_0(v13);
  LOBYTE(v13) = 1;
  _scrt_uninitialize_crt(v13, 0);
  return v11;
}

```

## disassembly

```asm
0x140001f70  mov     [rsp+arg_0], rbx
0x140001f75  mov     [rsp+arg_8], rsi
0x140001f7a  push    rdi
0x140001f7b  sub     rsp, 30h
0x140001f7f  mov     ecx, 1
0x140001f84  call    __scrt_initialize_crt
0x140001f89  test    al, al
0x140001f8b  jz      loc_1400020C6
0x140001f91  xor     sil, sil
0x140001f94  mov     [rsp+38h+var_18], sil
0x140001f99  call    __scrt_acquire_startup_lock
0x140001f9e  mov     bl, al
0x140001fa0  mov     ecx, cs:__scrt_current_native_startup_state
0x140001fa6  cmp     ecx, 1
0x140001fa9  jz      loc_1400020D1
0x140001faf  test    ecx, ecx
0x140001fb1  jnz     short loc_140001FFD
0x140001fb3  mov     cs:__scrt_current_native_startup_state, 1
0x140001fbd  lea     rdx, __xi_z; Last
0x140001fc4  lea     rcx, __xi_a; First
0x140001fcb  call    _initterm_e_0
0x140001fd0  test    eax, eax
0x140001fd2  jz      short loc_140001FDE
0x140001fd4  mov     eax, 0FFh
0x140001fd9  jmp     loc_1400020B6
0x140001fde  lea     rdx, __xc_z; Last
0x140001fe5  lea     rcx, __xc_a; First
0x140001fec  call    _initterm_0
0x140001ff1  mov     cs:__scrt_current_native_startup_state, 2
0x140001ffb  jmp     short loc_140002005
0x140001ffd  mov     sil, 1
0x140002000  mov     [rsp+38h+var_18], sil
0x140002005  mov     cl, bl
0x140002007  call    __scrt_release_startup_lock
0x14000200c  call    __scrt_get_dyn_tls_init_callback
0x140002011  mov     rbx, rax
0x140002014  cmp     qword ptr [rax], 0
0x140002018  jz      short loc_140002037
0x14000201a  mov     rcx, rax
0x14000201d  call    __scrt_is_nonwritable_in_current_image
0x140002022  test    al, al
0x140002024  jz      short loc_140002037
0x140002026  xor     r8d, r8d
0x140002029  lea     edx, [r8+2]
0x14000202d  xor     ecx, ecx
0x14000202f  mov     rax, [rbx]
0x140002032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002037  call    __scrt_get_dyn_tls_dtor_callback
0x14000203c  mov     rbx, rax
0x14000203f  cmp     qword ptr [rax], 0
0x140002043  jz      short loc_140002059
0x140002045  mov     rcx, rax
0x140002048  call    __scrt_is_nonwritable_in_current_image
0x14000204d  test    al, al
0x14000204f  jz      short loc_140002059
0x140002051  mov     rcx, [rbx]; Callback
0x140002054  call    _register_thread_local_exe_atexit_callback_0
0x140002059  call    _get_initial_wide_environment
0x14000205e  mov     rdi, rax
0x140002061  call    __p___wargv
0x140002066  mov     rbx, [rax]
0x140002069  call    __p___argc
0x14000206e  mov     r8, rdi
0x140002071  mov     rdx, rbx
0x140002074  mov     ecx, [rax]
0x140002076  call    wmain
0x14000207b  mov     ebx, eax
0x14000207d  call    __scrt_is_managed_app
0x140002082  test    al, al
0x140002084  jz      short loc_1400020DB
0x140002086  test    sil, sil
0x140002089  jnz     short loc_140002090
0x14000208b  call    _o__cexit_0
0x140002090  xor     edx, edx
0x140002092  mov     cl, 1
0x140002094  call    __scrt_uninitialize_crt
0x140002099  mov     eax, ebx
0x14000209b  jmp     short loc_1400020B6
0x14000209d  mov     ebx, eax
0x14000209f  call    __scrt_is_managed_app
0x1400020a4  test    al, al
0x1400020a6  jz      short loc_1400020E3
0x1400020a8  cmp     [rsp+38h+var_18], 0
0x1400020ad  jnz     short loc_1400020B4
0x1400020af  call    _c_exit_0
0x1400020b4  mov     eax, ebx
0x1400020b6  mov     rbx, [rsp+38h+arg_0]
0x1400020bb  mov     rsi, [rsp+38h+arg_8]
0x1400020c0  add     rsp, 30h
0x1400020c4  pop     rdi
0x1400020c5  retn
0x1400020c6  mov     ecx, 7
0x1400020cb  call    __scrt_fastfail
0x1400020d1  mov     ecx, 7
0x1400020d6  call    __scrt_fastfail
0x1400020db  mov     ecx, ebx; Code
0x1400020dd  call    _o_exit_0
0x1400020e3  mov     ecx, ebx
0x1400020e5  call    _o__exit_0
0x1400020ea  nop
0x14000acfc  push    rbp
0x14000acfe  sub     rsp, 20h
0x14000ad02  mov     rbp, rdx
0x14000ad05  mov     rdx, rcx; ExceptionPtr
0x14000ad08  mov     rcx, [rcx]
0x14000ad0b  mov     ecx, [rcx]; ExceptionNum
0x14000ad0d  call    _seh_filter_exe
0x14000ad12  nop
0x14000ad13  add     rsp, 20h
0x14000ad17  pop     rbp
0x14000ad18  retn
```
