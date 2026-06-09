# dllmain_crt_process_attach

- ea: `0x180001278`
- end: `0x180001389`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180001278`
- `0x180001958`
- `0x180001998`
- `0x1800019d4`
- `0x180001af8`
- `0x180001bcc`
- `0x180001c6c`
- `0x180001de8`
- `0x180001e10`
- `0x180001e34`
- `0x180001e58`
- `0x180001fcc`
- `0x180002556`
- `0x180002562`
- `0x18000d010`

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
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180001389LL);
  }
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
  ++dword_180012330;
  return 1;
}

```

## disassembly

```asm
0x180001278  mov     [rsp+arg_0], rbx
0x18000127d  mov     [rsp+arg_8], rsi
0x180001282  mov     [rsp+arg_18], rdi
0x180001287  push    r14
0x180001289  sub     rsp, 20h
0x18000128d  mov     rsi, rdx
0x180001290  mov     r14, rcx
0x180001293  xor     ecx, ecx
0x180001295  call    __scrt_initialize_crt
0x18000129a  test    al, al
0x18000129c  jz      loc_180001365
0x1800012a2  call    __scrt_acquire_startup_lock
0x1800012a7  mov     bl, al
0x1800012a9  mov     [rsp+28h+arg_10], al
0x1800012ad  mov     dil, 1
0x1800012b0  cmp     cs:__scrt_current_native_startup_state, 0
0x1800012b7  jnz     loc_18000137D
0x1800012bd  mov     cs:__scrt_current_native_startup_state, 1
0x1800012c7  call    __scrt_dllmain_before_initialize_c
0x1800012cc  test    al, al
0x1800012ce  jz      short loc_18000131F
0x1800012d0  call    _RTC_Initialize
0x1800012d5  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800012da  call    __scrt_initialize_default_local_stdio_options
0x1800012df  lea     rdx, __xi_z; Last
0x1800012e6  lea     rcx, __xi_a; First
0x1800012ed  call    _initterm_e_0
0x1800012f2  test    eax, eax
0x1800012f4  jnz     short loc_18000131F
0x1800012f6  call    __scrt_dllmain_after_initialize_c
0x1800012fb  test    al, al
0x1800012fd  jz      short loc_18000131F
0x1800012ff  lea     rdx, __xc_z; Last
0x180001306  lea     rcx, __xc_a; First
0x18000130d  call    _initterm_0
0x180001312  mov     cs:__scrt_current_native_startup_state, 2
0x18000131c  xor     dil, dil
0x18000131f  mov     cl, bl
0x180001321  call    __scrt_release_startup_lock
0x180001326  test    dil, dil
0x180001329  jnz     short loc_180001365
0x18000132b  call    __scrt_get_dyn_tls_init_callback
0x180001330  mov     rbx, rax
0x180001333  cmp     qword ptr [rax], 0
0x180001337  jz      short loc_180001358
0x180001339  mov     rcx, rax
0x18000133c  call    __scrt_is_nonwritable_in_current_image
0x180001341  test    al, al
0x180001343  jz      short loc_180001358
0x180001345  mov     r8, rsi
0x180001348  mov     edx, 2
0x18000134d  mov     rcx, r14
0x180001350  mov     rax, [rbx]
0x180001353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001358  inc     cs:dword_180012330
0x18000135e  mov     eax, 1
0x180001363  jmp     short loc_180001367
0x180001365  xor     eax, eax
0x180001367  mov     rbx, [rsp+28h+arg_0]
0x18000136c  mov     rsi, [rsp+28h+arg_8]
0x180001371  mov     rdi, [rsp+28h+arg_18]
0x180001376  add     rsp, 20h
0x18000137a  pop     r14
0x18000137c  retn
0x18000137d  mov     ecx, 7
0x180001382  call    __scrt_fastfail
0x180001387  nop
0x180001388  int     3; Trap to Debugger
0x18000cc9c  push    rbp
0x18000cc9e  sub     rsp, 20h
0x18000cca2  mov     rbp, rdx
0x18000cca5  mov     cl, [rbp+40h]
0x18000cca8  add     rsp, 20h
0x18000ccac  pop     rbp
0x18000ccad  jmp     __scrt_release_startup_lock
```
