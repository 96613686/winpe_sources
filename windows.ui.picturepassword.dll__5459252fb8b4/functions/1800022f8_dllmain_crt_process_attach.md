# dllmain_crt_process_attach

- ea: `0x1800022f8`
- end: `0x1800023f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800022a0`

## callees

- `0x1800022f8`
- `0x180002640`
- `0x180002680`
- `0x1800026bc`
- `0x1800027bc`
- `0x180002890`
- `0x180002930`
- `0x180002aa8`
- `0x180002ad0`
- `0x180002af4`
- `0x180002b04`
- `0x180002b10`
- `0x180002e66`
- `0x180002e72`
- `0x18001f010`

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
  ++dword_18002D2D0;
  return 1;
}

```

## disassembly

```asm
0x1800022f8  push    rbx
0x1800022fa  push    rsi
0x1800022fb  push    rdi
0x1800022fc  push    r14
0x1800022fe  sub     rsp, 28h
0x180002302  mov     rsi, rdx
0x180002305  mov     r14, rcx
0x180002308  xor     ecx, ecx
0x18000230a  call    __scrt_initialize_crt
0x18000230f  test    al, al
0x180002311  jz      loc_1800023DA
0x180002317  call    __scrt_acquire_startup_lock
0x18000231c  mov     bl, al
0x18000231e  mov     [rsp+48h+arg_10], al
0x180002322  mov     dil, 1
0x180002325  cmp     cs:__scrt_current_native_startup_state, 0
0x18000232c  jnz     loc_1800023E6
0x180002332  mov     cs:__scrt_current_native_startup_state, 1
0x18000233c  call    __scrt_dllmain_before_initialize_c
0x180002341  test    al, al
0x180002343  jz      short loc_180002394
0x180002345  call    _RTC_Initialize
0x18000234a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000234f  call    __scrt_initialize_default_local_stdio_options
0x180002354  lea     rdx, __xi_z; Last
0x18000235b  lea     rcx, __xi_a; First
0x180002362  call    _initterm_e_0
0x180002367  test    eax, eax
0x180002369  jnz     short loc_180002394
0x18000236b  call    __scrt_dllmain_after_initialize_c
0x180002370  test    al, al
0x180002372  jz      short loc_180002394
0x180002374  lea     rdx, __xc_z; Last
0x18000237b  lea     rcx, __xc_a; First
0x180002382  call    _initterm_0
0x180002387  mov     cs:__scrt_current_native_startup_state, 2
0x180002391  xor     dil, dil
0x180002394  mov     cl, bl
0x180002396  call    __scrt_release_startup_lock
0x18000239b  test    dil, dil
0x18000239e  jnz     short loc_1800023DA
0x1800023a0  call    __scrt_get_dyn_tls_init_callback
0x1800023a5  mov     rbx, rax
0x1800023a8  cmp     qword ptr [rax], 0
0x1800023ac  jz      short loc_1800023CD
0x1800023ae  mov     rcx, rax
0x1800023b1  call    __scrt_is_nonwritable_in_current_image
0x1800023b6  test    al, al
0x1800023b8  jz      short loc_1800023CD
0x1800023ba  mov     r8, rsi
0x1800023bd  mov     edx, 2
0x1800023c2  mov     rcx, r14
0x1800023c5  mov     rax, [rbx]
0x1800023c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023cd  inc     cs:dword_18002D2D0
0x1800023d3  mov     eax, 1
0x1800023d8  jmp     short loc_1800023DC
0x1800023da  xor     eax, eax
0x1800023dc  add     rsp, 28h
0x1800023e0  pop     r14
0x1800023e2  pop     rdi
0x1800023e3  pop     rsi
0x1800023e4  pop     rbx
0x1800023e5  retn
0x1800023e6  mov     ecx, 7
0x1800023eb  call    __scrt_fastfail
0x18001e42c  push    rbp
0x18001e42e  sub     rsp, 20h
0x18001e432  mov     rbp, rdx
0x18001e435  mov     cl, [rbp+60h]
0x18001e438  add     rsp, 20h
0x18001e43c  pop     rbp
0x18001e43d  jmp     __scrt_release_startup_lock
```
