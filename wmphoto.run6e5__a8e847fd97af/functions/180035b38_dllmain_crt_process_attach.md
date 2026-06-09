# dllmain_crt_process_attach

- ea: `0x180035b38`
- end: `0x180035c32`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180035ae0`

## callees

- `0x180035b38`
- `0x180035eb8`
- `0x180035ef8`
- `0x180035f34`
- `0x180036034`
- `0x180036108`
- `0x1800361a8`
- `0x180036628`
- `0x180036650`
- `0x180036674`
- `0x180036684`
- `0x180036690`
- `0x180036a76`
- `0x180036a82`
- `0x180044010`

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
  ++dword_1800502D0;
  return 1;
}

```

## disassembly

```asm
0x180035b38  push    rbx
0x180035b3a  push    rsi
0x180035b3b  push    rdi
0x180035b3c  push    r14
0x180035b3e  sub     rsp, 28h
0x180035b42  mov     rsi, rdx
0x180035b45  mov     r14, rcx
0x180035b48  xor     ecx, ecx
0x180035b4a  call    __scrt_initialize_crt
0x180035b4f  test    al, al
0x180035b51  jz      loc_180035C1A
0x180035b57  call    __scrt_acquire_startup_lock
0x180035b5c  mov     bl, al
0x180035b5e  mov     [rsp+48h+arg_10], al
0x180035b62  mov     dil, 1
0x180035b65  cmp     cs:__scrt_current_native_startup_state, 0
0x180035b6c  jnz     loc_180035C26
0x180035b72  mov     cs:__scrt_current_native_startup_state, 1
0x180035b7c  call    __scrt_dllmain_before_initialize_c
0x180035b81  test    al, al
0x180035b83  jz      short loc_180035BD4
0x180035b85  call    _RTC_Initialize
0x180035b8a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180035b8f  call    __scrt_initialize_default_local_stdio_options
0x180035b94  lea     rdx, __xi_z; Last
0x180035b9b  lea     rcx, __xi_a; First
0x180035ba2  call    _initterm_e_0
0x180035ba7  test    eax, eax
0x180035ba9  jnz     short loc_180035BD4
0x180035bab  call    __scrt_dllmain_after_initialize_c
0x180035bb0  test    al, al
0x180035bb2  jz      short loc_180035BD4
0x180035bb4  lea     rdx, __xc_z; Last
0x180035bbb  lea     rcx, __xc_a; First
0x180035bc2  call    _initterm_0
0x180035bc7  mov     cs:__scrt_current_native_startup_state, 2
0x180035bd1  xor     dil, dil
0x180035bd4  mov     cl, bl
0x180035bd6  call    __scrt_release_startup_lock
0x180035bdb  test    dil, dil
0x180035bde  jnz     short loc_180035C1A
0x180035be0  call    __scrt_get_dyn_tls_init_callback
0x180035be5  mov     rbx, rax
0x180035be8  cmp     qword ptr [rax], 0
0x180035bec  jz      short loc_180035C0D
0x180035bee  mov     rcx, rax
0x180035bf1  call    __scrt_is_nonwritable_in_current_image
0x180035bf6  test    al, al
0x180035bf8  jz      short loc_180035C0D
0x180035bfa  mov     r8, rsi
0x180035bfd  mov     edx, 2
0x180035c02  mov     rcx, r14
0x180035c05  mov     rax, [rbx]
0x180035c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c0d  inc     cs:dword_1800502D0
0x180035c13  mov     eax, 1
0x180035c18  jmp     short loc_180035C1C
0x180035c1a  xor     eax, eax
0x180035c1c  add     rsp, 28h
0x180035c20  pop     r14
0x180035c22  pop     rdi
0x180035c23  pop     rsi
0x180035c24  pop     rbx
0x180035c25  retn
0x180035c26  mov     ecx, 7
0x180035c2b  call    __scrt_fastfail
0x180043882  push    rbp
0x180043884  sub     rsp, 20h
0x180043888  mov     rbp, rdx
0x18004388b  mov     cl, [rbp+60h]
0x18004388e  add     rsp, 20h
0x180043892  pop     rbp
0x180043893  jmp     __scrt_release_startup_lock
```
