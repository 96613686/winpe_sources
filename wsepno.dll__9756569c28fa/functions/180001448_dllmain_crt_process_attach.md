# dllmain_crt_process_attach

- ea: `0x180001448`
- end: `0x180001542`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800013f0`

## callees

- `0x180001448`
- `0x1800017cc`
- `0x18000180c`
- `0x180001848`
- `0x180001948`
- `0x180001a1c`
- `0x180001abc`
- `0x180001cc0`
- `0x180001ce8`
- `0x180001d0c`
- `0x180001d1c`
- `0x180001d28`
- `0x1800020d6`
- `0x1800020e2`
- `0x18000f010`

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
  ++dword_1800158D0;
  return 1;
}

```

## disassembly

```asm
0x180001448  push    rbx
0x18000144a  push    rsi
0x18000144b  push    rdi
0x18000144c  push    r14
0x18000144e  sub     rsp, 28h
0x180001452  mov     rsi, rdx
0x180001455  mov     r14, rcx
0x180001458  xor     ecx, ecx
0x18000145a  call    __scrt_initialize_crt
0x18000145f  test    al, al
0x180001461  jz      loc_18000152A
0x180001467  call    __scrt_acquire_startup_lock
0x18000146c  mov     bl, al
0x18000146e  mov     [rsp+48h+arg_10], al
0x180001472  mov     dil, 1
0x180001475  cmp     cs:__scrt_current_native_startup_state, 0
0x18000147c  jnz     loc_180001536
0x180001482  mov     cs:__scrt_current_native_startup_state, 1
0x18000148c  call    __scrt_dllmain_before_initialize_c
0x180001491  test    al, al
0x180001493  jz      short loc_1800014E4
0x180001495  call    _RTC_Initialize
0x18000149a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000149f  call    __scrt_initialize_default_local_stdio_options
0x1800014a4  lea     rdx, __xi_z; Last
0x1800014ab  lea     rcx, __xi_a; First
0x1800014b2  call    _initterm_e_0
0x1800014b7  test    eax, eax
0x1800014b9  jnz     short loc_1800014E4
0x1800014bb  call    __scrt_dllmain_after_initialize_c
0x1800014c0  test    al, al
0x1800014c2  jz      short loc_1800014E4
0x1800014c4  lea     rdx, __xc_z; Last
0x1800014cb  lea     rcx, __xc_a; First
0x1800014d2  call    _initterm_0
0x1800014d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800014e1  xor     dil, dil
0x1800014e4  mov     cl, bl
0x1800014e6  call    __scrt_release_startup_lock
0x1800014eb  test    dil, dil
0x1800014ee  jnz     short loc_18000152A
0x1800014f0  call    __scrt_get_dyn_tls_init_callback
0x1800014f5  mov     rbx, rax
0x1800014f8  cmp     qword ptr [rax], 0
0x1800014fc  jz      short loc_18000151D
0x1800014fe  mov     rcx, rax
0x180001501  call    __scrt_is_nonwritable_in_current_image
0x180001506  test    al, al
0x180001508  jz      short loc_18000151D
0x18000150a  mov     r8, rsi
0x18000150d  mov     edx, 2
0x180001512  mov     rcx, r14
0x180001515  mov     rax, [rbx]
0x180001518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151d  inc     cs:dword_1800158D0
0x180001523  mov     eax, 1
0x180001528  jmp     short loc_18000152C
0x18000152a  xor     eax, eax
0x18000152c  add     rsp, 28h
0x180001530  pop     r14
0x180001532  pop     rdi
0x180001533  pop     rsi
0x180001534  pop     rbx
0x180001535  retn
0x180001536  mov     ecx, 7
0x18000153b  call    __scrt_fastfail
0x18000d82c  push    rbp
0x18000d82e  sub     rsp, 20h
0x18000d832  mov     rbp, rdx
0x18000d835  mov     cl, [rbp+60h]
0x18000d838  add     rsp, 20h
0x18000d83c  pop     rbp
0x18000d83d  jmp     __scrt_release_startup_lock
```
