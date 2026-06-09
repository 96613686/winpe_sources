# dllmain_crt_process_attach

- ea: `0x180036108`
- end: `0x180036202`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800360b0`

## callees

- `0x180036108`
- `0x180036488`
- `0x1800364c8`
- `0x180036504`
- `0x180036604`
- `0x1800366d8`
- `0x180036778`
- `0x180036bec`
- `0x180036c14`
- `0x180036c38`
- `0x180036c48`
- `0x180036c54`
- `0x180037046`
- `0x180037052`
- `0x180045010`

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
  ++dword_1800512D0;
  return 1;
}

```

## disassembly

```asm
0x180036108  push    rbx
0x18003610a  push    rsi
0x18003610b  push    rdi
0x18003610c  push    r14
0x18003610e  sub     rsp, 28h
0x180036112  mov     rsi, rdx
0x180036115  mov     r14, rcx
0x180036118  xor     ecx, ecx
0x18003611a  call    __scrt_initialize_crt
0x18003611f  test    al, al
0x180036121  jz      loc_1800361EA
0x180036127  call    __scrt_acquire_startup_lock
0x18003612c  mov     bl, al
0x18003612e  mov     [rsp+48h+arg_10], al
0x180036132  mov     dil, 1
0x180036135  cmp     cs:__scrt_current_native_startup_state, 0
0x18003613c  jnz     loc_1800361F6
0x180036142  mov     cs:__scrt_current_native_startup_state, 1
0x18003614c  call    __scrt_dllmain_before_initialize_c
0x180036151  test    al, al
0x180036153  jz      short loc_1800361A4
0x180036155  call    _RTC_Initialize
0x18003615a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18003615f  call    __scrt_initialize_default_local_stdio_options
0x180036164  lea     rdx, __xi_z; Last
0x18003616b  lea     rcx, __xi_a; First
0x180036172  call    _initterm_e_0
0x180036177  test    eax, eax
0x180036179  jnz     short loc_1800361A4
0x18003617b  call    __scrt_dllmain_after_initialize_c
0x180036180  test    al, al
0x180036182  jz      short loc_1800361A4
0x180036184  lea     rdx, __xc_z; Last
0x18003618b  lea     rcx, __xc_a; First
0x180036192  call    _initterm_0
0x180036197  mov     cs:__scrt_current_native_startup_state, 2
0x1800361a1  xor     dil, dil
0x1800361a4  mov     cl, bl
0x1800361a6  call    __scrt_release_startup_lock
0x1800361ab  test    dil, dil
0x1800361ae  jnz     short loc_1800361EA
0x1800361b0  call    __scrt_get_dyn_tls_init_callback
0x1800361b5  mov     rbx, rax
0x1800361b8  cmp     qword ptr [rax], 0
0x1800361bc  jz      short loc_1800361DD
0x1800361be  mov     rcx, rax
0x1800361c1  call    __scrt_is_nonwritable_in_current_image
0x1800361c6  test    al, al
0x1800361c8  jz      short loc_1800361DD
0x1800361ca  mov     r8, rsi
0x1800361cd  mov     edx, 2
0x1800361d2  mov     rcx, r14
0x1800361d5  mov     rax, [rbx]
0x1800361d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361dd  inc     cs:dword_1800512D0
0x1800361e3  mov     eax, 1
0x1800361e8  jmp     short loc_1800361EC
0x1800361ea  xor     eax, eax
0x1800361ec  add     rsp, 28h
0x1800361f0  pop     r14
0x1800361f2  pop     rdi
0x1800361f3  pop     rsi
0x1800361f4  pop     rbx
0x1800361f5  retn
0x1800361f6  mov     ecx, 7
0x1800361fb  call    __scrt_fastfail
0x180044092  push    rbp
0x180044094  sub     rsp, 20h
0x180044098  mov     rbp, rdx
0x18004409b  mov     cl, [rbp+60h]
0x18004409e  add     rsp, 20h
0x1800440a2  pop     rbp
0x1800440a3  jmp     __scrt_release_startup_lock
```
