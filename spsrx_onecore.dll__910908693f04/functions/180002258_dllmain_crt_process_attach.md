# dllmain_crt_process_attach

- ea: `0x180002258`
- end: `0x180002352`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002200`

## callees

- `0x180002258`
- `0x1800025f0`
- `0x180002630`
- `0x18000266c`
- `0x18000276c`
- `0x180002840`
- `0x1800028e0`
- `0x180002a58`
- `0x180002a80`
- `0x180002aa4`
- `0x180002ab4`
- `0x180002ac0`
- `0x180002de6`
- `0x180002df2`
- `0x180010010`

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
  ++dword_180015190;
  return 1;
}

```

## disassembly

```asm
0x180002258  push    rbx
0x18000225a  push    rsi
0x18000225b  push    rdi
0x18000225c  push    r14
0x18000225e  sub     rsp, 28h
0x180002262  mov     rsi, rdx
0x180002265  mov     r14, rcx
0x180002268  xor     ecx, ecx
0x18000226a  call    __scrt_initialize_crt
0x18000226f  test    al, al
0x180002271  jz      loc_18000233A
0x180002277  call    __scrt_acquire_startup_lock
0x18000227c  mov     bl, al
0x18000227e  mov     [rsp+48h+arg_10], al
0x180002282  mov     dil, 1
0x180002285  cmp     cs:__scrt_current_native_startup_state, 0
0x18000228c  jnz     loc_180002346
0x180002292  mov     cs:__scrt_current_native_startup_state, 1
0x18000229c  call    __scrt_dllmain_before_initialize_c
0x1800022a1  test    al, al
0x1800022a3  jz      short loc_1800022F4
0x1800022a5  call    _RTC_Initialize
0x1800022aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800022af  call    __scrt_initialize_default_local_stdio_options
0x1800022b4  lea     rdx, __xi_z; Last
0x1800022bb  lea     rcx, __xi_a; First
0x1800022c2  call    _initterm_e_0
0x1800022c7  test    eax, eax
0x1800022c9  jnz     short loc_1800022F4
0x1800022cb  call    __scrt_dllmain_after_initialize_c
0x1800022d0  test    al, al
0x1800022d2  jz      short loc_1800022F4
0x1800022d4  lea     rdx, __xc_z; Last
0x1800022db  lea     rcx, __xc_a; First
0x1800022e2  call    _initterm_0
0x1800022e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800022f1  xor     dil, dil
0x1800022f4  mov     cl, bl
0x1800022f6  call    __scrt_release_startup_lock
0x1800022fb  test    dil, dil
0x1800022fe  jnz     short loc_18000233A
0x180002300  call    __scrt_get_dyn_tls_init_callback
0x180002305  mov     rbx, rax
0x180002308  cmp     qword ptr [rax], 0
0x18000230c  jz      short loc_18000232D
0x18000230e  mov     rcx, rax
0x180002311  call    __scrt_is_nonwritable_in_current_image
0x180002316  test    al, al
0x180002318  jz      short loc_18000232D
0x18000231a  mov     r8, rsi
0x18000231d  mov     edx, 2
0x180002322  mov     rcx, r14
0x180002325  mov     rax, [rbx]
0x180002328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000232d  inc     cs:dword_180015190
0x180002333  mov     eax, 1
0x180002338  jmp     short loc_18000233C
0x18000233a  xor     eax, eax
0x18000233c  add     rsp, 28h
0x180002340  pop     r14
0x180002342  pop     rdi
0x180002343  pop     rsi
0x180002344  pop     rbx
0x180002345  retn
0x180002346  mov     ecx, 7
0x18000234b  call    __scrt_fastfail
0x180003566  push    rbp
0x180003568  sub     rsp, 20h
0x18000356c  mov     rbp, rdx
0x18000356f  mov     cl, [rbp+60h]
0x180003572  add     rsp, 20h
0x180003576  pop     rbp
0x180003577  jmp     __scrt_release_startup_lock
```
