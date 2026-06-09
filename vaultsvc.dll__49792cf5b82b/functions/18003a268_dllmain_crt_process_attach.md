# dllmain_crt_process_attach

- ea: `0x18003a268`
- end: `0x18003a362`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18003a210`

## callees

- `0x18003a268`
- `0x18003a660`
- `0x18003a688`
- `0x18003a6ac`
- `0x18003a6ec`
- `0x18003a728`
- `0x18003a828`
- `0x18003a8fc`
- `0x18003a99c`
- `0x18003aa58`
- `0x18003aa68`
- `0x18003aa74`
- `0x18003add6`
- `0x18003ade2`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 v6; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v8)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v5 = 0;
      }
    }
  }
  LOBYTE(v6) = v4;
  _scrt_release_startup_lock(v6);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v8 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v8)(a1, 2, a2);
  }
  ++dword_18005F4F0;
  return 1;
}

```

## disassembly

```asm
0x18003a268  push    rbx
0x18003a26a  push    rsi
0x18003a26b  push    rdi
0x18003a26c  push    r14
0x18003a26e  sub     rsp, 28h
0x18003a272  mov     rsi, rdx
0x18003a275  mov     r14, rcx
0x18003a278  xor     ecx, ecx
0x18003a27a  call    __scrt_initialize_crt
0x18003a27f  test    al, al
0x18003a281  jz      loc_18003A34A
0x18003a287  call    __scrt_acquire_startup_lock
0x18003a28c  mov     bl, al
0x18003a28e  mov     [rsp+48h+arg_10], al
0x18003a292  mov     dil, 1
0x18003a295  cmp     cs:__scrt_current_native_startup_state, 0
0x18003a29c  jnz     loc_18003A356
0x18003a2a2  mov     cs:__scrt_current_native_startup_state, 1
0x18003a2ac  call    __scrt_dllmain_before_initialize_c
0x18003a2b1  test    al, al
0x18003a2b3  jz      short loc_18003A304
0x18003a2b5  call    _RTC_Initialize
0x18003a2ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18003a2bf  call    __scrt_initialize_default_local_stdio_options
0x18003a2c4  lea     rdx, __xi_z; Last
0x18003a2cb  lea     rcx, __xi_a; First
0x18003a2d2  call    _initterm_e_0
0x18003a2d7  test    eax, eax
0x18003a2d9  jnz     short loc_18003A304
0x18003a2db  call    __scrt_dllmain_after_initialize_c
0x18003a2e0  test    al, al
0x18003a2e2  jz      short loc_18003A304
0x18003a2e4  lea     rdx, __xc_z; Last
0x18003a2eb  lea     rcx, __xc_a; First
0x18003a2f2  call    _initterm_0
0x18003a2f7  mov     cs:__scrt_current_native_startup_state, 2
0x18003a301  xor     dil, dil
0x18003a304  mov     cl, bl
0x18003a306  call    __scrt_release_startup_lock
0x18003a30b  test    dil, dil
0x18003a30e  jnz     short loc_18003A34A
0x18003a310  call    __scrt_get_dyn_tls_init_callback
0x18003a315  mov     rbx, rax
0x18003a318  cmp     qword ptr [rax], 0
0x18003a31c  jz      short loc_18003A33D
0x18003a31e  mov     rcx, rax
0x18003a321  call    __scrt_is_nonwritable_in_current_image
0x18003a326  test    al, al
0x18003a328  jz      short loc_18003A33D
0x18003a32a  mov     r8, rsi
0x18003a32d  mov     edx, 2
0x18003a332  mov     rcx, r14
0x18003a335  mov     rax, [rbx]
0x18003a338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a33d  inc     cs:dword_18005F4F0
0x18003a343  mov     eax, 1
0x18003a348  jmp     short loc_18003A34C
0x18003a34a  xor     eax, eax
0x18003a34c  add     rsp, 28h
0x18003a350  pop     r14
0x18003a352  pop     rdi
0x18003a353  pop     rsi
0x18003a354  pop     rbx
0x18003a355  retn
0x18003a356  mov     ecx, 7
0x18003a35b  call    __scrt_fastfail
0x18004c909  push    rbp
0x18004c90b  sub     rsp, 20h
0x18004c90f  mov     rbp, rdx
0x18004c912  mov     cl, [rbp+60h]
0x18004c915  add     rsp, 20h
0x18004c919  pop     rbp
0x18004c91a  jmp     __scrt_release_startup_lock
```
