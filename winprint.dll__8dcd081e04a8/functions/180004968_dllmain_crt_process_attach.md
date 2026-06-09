# dllmain_crt_process_attach

- ea: `0x180004968`
- end: `0x180004a62`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180004910`

## callees

- `0x180004968`
- `0x180004d60`
- `0x180004d88`
- `0x180004dac`
- `0x180004dec`
- `0x180004e28`
- `0x180004f28`
- `0x180004ffc`
- `0x18000509c`
- `0x1800050f8`
- `0x180005108`
- `0x180005114`
- `0x180005476`
- `0x180005482`
- `0x180008010`

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
  ++dword_18000D450;
  return 1;
}

```

## disassembly

```asm
0x180004968  push    rbx
0x18000496a  push    rsi
0x18000496b  push    rdi
0x18000496c  push    r14
0x18000496e  sub     rsp, 28h
0x180004972  mov     rsi, rdx
0x180004975  mov     r14, rcx
0x180004978  xor     ecx, ecx
0x18000497a  call    __scrt_initialize_crt
0x18000497f  test    al, al
0x180004981  jz      loc_180004A4A
0x180004987  call    __scrt_acquire_startup_lock
0x18000498c  mov     bl, al
0x18000498e  mov     [rsp+48h+arg_10], al
0x180004992  mov     dil, 1
0x180004995  cmp     cs:__scrt_current_native_startup_state, 0
0x18000499c  jnz     loc_180004A56
0x1800049a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800049ac  call    __scrt_dllmain_before_initialize_c
0x1800049b1  test    al, al
0x1800049b3  jz      short loc_180004A04
0x1800049b5  call    _RTC_Initialize
0x1800049ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800049bf  call    __scrt_initialize_default_local_stdio_options
0x1800049c4  lea     rdx, __xi_z; Last
0x1800049cb  lea     rcx, __xi_a; First
0x1800049d2  call    _initterm_e_0
0x1800049d7  test    eax, eax
0x1800049d9  jnz     short loc_180004A04
0x1800049db  call    __scrt_dllmain_after_initialize_c
0x1800049e0  test    al, al
0x1800049e2  jz      short loc_180004A04
0x1800049e4  lea     rdx, __xc_z; Last
0x1800049eb  lea     rcx, __xc_a; First
0x1800049f2  call    _initterm_0
0x1800049f7  mov     cs:__scrt_current_native_startup_state, 2
0x180004a01  xor     dil, dil
0x180004a04  mov     cl, bl
0x180004a06  call    __scrt_release_startup_lock
0x180004a0b  test    dil, dil
0x180004a0e  jnz     short loc_180004A4A
0x180004a10  call    __scrt_get_dyn_tls_init_callback
0x180004a15  mov     rbx, rax
0x180004a18  cmp     qword ptr [rax], 0
0x180004a1c  jz      short loc_180004A3D
0x180004a1e  mov     rcx, rax
0x180004a21  call    __scrt_is_nonwritable_in_current_image
0x180004a26  test    al, al
0x180004a28  jz      short loc_180004A3D
0x180004a2a  mov     r8, rsi
0x180004a2d  mov     edx, 2
0x180004a32  mov     rcx, r14
0x180004a35  mov     rax, [rbx]
0x180004a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a3d  inc     cs:dword_18000D450
0x180004a43  mov     eax, 1
0x180004a48  jmp     short loc_180004A4C
0x180004a4a  xor     eax, eax
0x180004a4c  add     rsp, 28h
0x180004a50  pop     r14
0x180004a52  pop     rdi
0x180004a53  pop     rsi
0x180004a54  pop     rbx
0x180004a55  retn
0x180004a56  mov     ecx, 7
0x180004a5b  call    __scrt_fastfail
0x180007852  push    rbp
0x180007854  sub     rsp, 20h
0x180007858  mov     rbp, rdx
0x18000785b  mov     cl, [rbp+60h]
0x18000785e  add     rsp, 20h
0x180007862  pop     rbp
0x180007863  jmp     __scrt_release_startup_lock
```
