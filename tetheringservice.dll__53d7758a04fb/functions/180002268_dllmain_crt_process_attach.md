# dllmain_crt_process_attach

- ea: `0x180002268`
- end: `0x180002362`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002210`

## callees

- `0x180002268`
- `0x1800025b4`
- `0x1800025f4`
- `0x180002630`
- `0x180002730`
- `0x180002804`
- `0x1800028a4`
- `0x180002aec`
- `0x180002b14`
- `0x180002b38`
- `0x180002b48`
- `0x180002b54`
- `0x180002f16`
- `0x180002f22`
- `0x180033010`

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
  ++dword_180041A30;
  return 1;
}

```

## disassembly

```asm
0x180002268  push    rbx
0x18000226a  push    rsi
0x18000226b  push    rdi
0x18000226c  push    r14
0x18000226e  sub     rsp, 28h
0x180002272  mov     rsi, rdx
0x180002275  mov     r14, rcx
0x180002278  xor     ecx, ecx
0x18000227a  call    __scrt_initialize_crt
0x18000227f  test    al, al
0x180002281  jz      loc_18000234A
0x180002287  call    __scrt_acquire_startup_lock
0x18000228c  mov     bl, al
0x18000228e  mov     [rsp+48h+arg_10], al
0x180002292  mov     dil, 1
0x180002295  cmp     cs:__scrt_current_native_startup_state, 0
0x18000229c  jnz     loc_180002356
0x1800022a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800022ac  call    __scrt_dllmain_before_initialize_c
0x1800022b1  test    al, al
0x1800022b3  jz      short loc_180002304
0x1800022b5  call    _RTC_Initialize
0x1800022ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800022bf  call    __scrt_initialize_default_local_stdio_options
0x1800022c4  lea     rdx, __xi_z; Last
0x1800022cb  lea     rcx, __xi_a; First
0x1800022d2  call    _initterm_e_0
0x1800022d7  test    eax, eax
0x1800022d9  jnz     short loc_180002304
0x1800022db  call    __scrt_dllmain_after_initialize_c
0x1800022e0  test    al, al
0x1800022e2  jz      short loc_180002304
0x1800022e4  lea     rdx, __xc_z; Last
0x1800022eb  lea     rcx, __xc_a; First
0x1800022f2  call    _initterm_0
0x1800022f7  mov     cs:__scrt_current_native_startup_state, 2
0x180002301  xor     dil, dil
0x180002304  mov     cl, bl
0x180002306  call    __scrt_release_startup_lock
0x18000230b  test    dil, dil
0x18000230e  jnz     short loc_18000234A
0x180002310  call    __scrt_get_dyn_tls_init_callback
0x180002315  mov     rbx, rax
0x180002318  cmp     qword ptr [rax], 0
0x18000231c  jz      short loc_18000233D
0x18000231e  mov     rcx, rax
0x180002321  call    __scrt_is_nonwritable_in_current_image
0x180002326  test    al, al
0x180002328  jz      short loc_18000233D
0x18000232a  mov     r8, rsi
0x18000232d  mov     edx, 2
0x180002332  mov     rcx, r14
0x180002335  mov     rax, [rbx]
0x180002338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233d  inc     cs:dword_180041A30
0x180002343  mov     eax, 1
0x180002348  jmp     short loc_18000234C
0x18000234a  xor     eax, eax
0x18000234c  add     rsp, 28h
0x180002350  pop     r14
0x180002352  pop     rdi
0x180002353  pop     rsi
0x180002354  pop     rbx
0x180002355  retn
0x180002356  mov     ecx, 7
0x18000235b  call    __scrt_fastfail
0x18003167c  push    rbp
0x18003167e  sub     rsp, 20h
0x180031682  mov     rbp, rdx
0x180031685  mov     cl, [rbp+60h]
0x180031688  add     rsp, 20h
0x18003168c  pop     rbp
0x18003168d  jmp     __scrt_release_startup_lock
```
