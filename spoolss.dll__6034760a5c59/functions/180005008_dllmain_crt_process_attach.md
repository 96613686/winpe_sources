# dllmain_crt_process_attach

- ea: `0x180005008`
- end: `0x180005102`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180004fb0`

## callees

- `0x180005008`
- `0x180005344`
- `0x180005384`
- `0x1800053c0`
- `0x1800054c0`
- `0x180005594`
- `0x180005634`
- `0x1800057d8`
- `0x180005800`
- `0x180005824`
- `0x180005834`
- `0x180005840`
- `0x180005b96`
- `0x180005ba2`
- `0x180016010`

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
  ++dword_180021370;
  return 1;
}

```

## disassembly

```asm
0x180005008  push    rbx
0x18000500a  push    rsi
0x18000500b  push    rdi
0x18000500c  push    r14
0x18000500e  sub     rsp, 28h
0x180005012  mov     rsi, rdx
0x180005015  mov     r14, rcx
0x180005018  xor     ecx, ecx
0x18000501a  call    __scrt_initialize_crt
0x18000501f  test    al, al
0x180005021  jz      loc_1800050EA
0x180005027  call    __scrt_acquire_startup_lock
0x18000502c  mov     bl, al
0x18000502e  mov     [rsp+48h+arg_10], al
0x180005032  mov     dil, 1
0x180005035  cmp     cs:__scrt_current_native_startup_state, 0
0x18000503c  jnz     loc_1800050F6
0x180005042  mov     cs:__scrt_current_native_startup_state, 1
0x18000504c  call    __scrt_dllmain_before_initialize_c
0x180005051  test    al, al
0x180005053  jz      short loc_1800050A4
0x180005055  call    _RTC_Initialize
0x18000505a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000505f  call    __scrt_initialize_default_local_stdio_options
0x180005064  lea     rdx, __xi_z; Last
0x18000506b  lea     rcx, __xi_a; First
0x180005072  call    _initterm_e_0
0x180005077  test    eax, eax
0x180005079  jnz     short loc_1800050A4
0x18000507b  call    __scrt_dllmain_after_initialize_c
0x180005080  test    al, al
0x180005082  jz      short loc_1800050A4
0x180005084  lea     rdx, __xc_z; Last
0x18000508b  lea     rcx, __xc_a; First
0x180005092  call    _initterm_0
0x180005097  mov     cs:__scrt_current_native_startup_state, 2
0x1800050a1  xor     dil, dil
0x1800050a4  mov     cl, bl
0x1800050a6  call    __scrt_release_startup_lock
0x1800050ab  test    dil, dil
0x1800050ae  jnz     short loc_1800050EA
0x1800050b0  call    __scrt_get_dyn_tls_init_callback
0x1800050b5  mov     rbx, rax
0x1800050b8  cmp     qword ptr [rax], 0
0x1800050bc  jz      short loc_1800050DD
0x1800050be  mov     rcx, rax
0x1800050c1  call    __scrt_is_nonwritable_in_current_image
0x1800050c6  test    al, al
0x1800050c8  jz      short loc_1800050DD
0x1800050ca  mov     r8, rsi
0x1800050cd  mov     edx, 2
0x1800050d2  mov     rcx, r14
0x1800050d5  mov     rax, [rbx]
0x1800050d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050dd  inc     cs:dword_180021370
0x1800050e3  mov     eax, 1
0x1800050e8  jmp     short loc_1800050EC
0x1800050ea  xor     eax, eax
0x1800050ec  add     rsp, 28h
0x1800050f0  pop     r14
0x1800050f2  pop     rdi
0x1800050f3  pop     rsi
0x1800050f4  pop     rbx
0x1800050f5  retn
0x1800050f6  mov     ecx, 7
0x1800050fb  call    __scrt_fastfail
0x1800150e0  push    rbp
0x1800150e2  sub     rsp, 20h
0x1800150e6  mov     rbp, rdx
0x1800150e9  mov     cl, [rbp+60h]
0x1800150ec  add     rsp, 20h
0x1800150f0  pop     rbp
0x1800150f1  jmp     __scrt_release_startup_lock
```
