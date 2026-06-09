# dllmain_crt_process_attach

- ea: `0x180001f18`
- end: `0x180002012`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001ec0`

## callees

- `0x180001f18`
- `0x180002254`
- `0x180002294`
- `0x1800022d0`
- `0x1800023d0`
- `0x1800024a4`
- `0x180002544`
- `0x1800026ec`
- `0x180002714`
- `0x180002738`
- `0x180002748`
- `0x180002754`
- `0x180002ab6`
- `0x180002ac2`
- `0x18000a010`

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
    _scrt_fastfail(7u);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( _scrt_dllmain_after_initialize_c() )
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
  ++dword_18000FA10;
  return 1;
}

```

## disassembly

```asm
0x180001f18  push    rbx
0x180001f1a  push    rsi
0x180001f1b  push    rdi
0x180001f1c  push    r14
0x180001f1e  sub     rsp, 28h
0x180001f22  mov     rsi, rdx
0x180001f25  mov     r14, rcx
0x180001f28  xor     ecx, ecx
0x180001f2a  call    __scrt_initialize_crt
0x180001f2f  test    al, al
0x180001f31  jz      loc_180001FFA
0x180001f37  call    __scrt_acquire_startup_lock
0x180001f3c  mov     bl, al
0x180001f3e  mov     [rsp+48h+arg_10], al
0x180001f42  mov     dil, 1
0x180001f45  cmp     cs:__scrt_current_native_startup_state, 0
0x180001f4c  jnz     loc_180002006
0x180001f52  mov     cs:__scrt_current_native_startup_state, 1
0x180001f5c  call    __scrt_dllmain_before_initialize_c
0x180001f61  test    al, al
0x180001f63  jz      short loc_180001FB4
0x180001f65  call    _RTC_Initialize
0x180001f6a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001f6f  call    __scrt_initialize_default_local_stdio_options
0x180001f74  lea     rdx, __xi_z; Last
0x180001f7b  lea     rcx, __xi_a; First
0x180001f82  call    _initterm_e_0
0x180001f87  test    eax, eax
0x180001f89  jnz     short loc_180001FB4
0x180001f8b  call    __scrt_dllmain_after_initialize_c
0x180001f90  test    al, al
0x180001f92  jz      short loc_180001FB4
0x180001f94  lea     rdx, __xc_z; Last
0x180001f9b  lea     rcx, __xc_a; First
0x180001fa2  call    _initterm_0
0x180001fa7  mov     cs:__scrt_current_native_startup_state, 2
0x180001fb1  xor     dil, dil
0x180001fb4  mov     cl, bl
0x180001fb6  call    __scrt_release_startup_lock
0x180001fbb  test    dil, dil
0x180001fbe  jnz     short loc_180001FFA
0x180001fc0  call    __scrt_get_dyn_tls_init_callback
0x180001fc5  mov     rbx, rax
0x180001fc8  cmp     qword ptr [rax], 0
0x180001fcc  jz      short loc_180001FED
0x180001fce  mov     rcx, rax
0x180001fd1  call    __scrt_is_nonwritable_in_current_image
0x180001fd6  test    al, al
0x180001fd8  jz      short loc_180001FED
0x180001fda  mov     r8, rsi
0x180001fdd  mov     edx, 2
0x180001fe2  mov     rcx, r14
0x180001fe5  mov     rax, [rbx]
0x180001fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fed  inc     cs:dword_18000FA10
0x180001ff3  mov     eax, 1
0x180001ff8  jmp     short loc_180001FFC
0x180001ffa  xor     eax, eax
0x180001ffc  add     rsp, 28h
0x180002000  pop     r14
0x180002002  pop     rdi
0x180002003  pop     rsi
0x180002004  pop     rbx
0x180002005  retn
0x180002006  mov     ecx, 7
0x18000200b  call    __scrt_fastfail
0x1800097bc  push    rbp
0x1800097be  sub     rsp, 20h
0x1800097c2  mov     rbp, rdx
0x1800097c5  mov     cl, [rbp+60h]
0x1800097c8  add     rsp, 20h
0x1800097cc  pop     rbp
0x1800097cd  jmp     __scrt_release_startup_lock
```
