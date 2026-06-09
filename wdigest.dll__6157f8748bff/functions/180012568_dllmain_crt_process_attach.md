# dllmain_crt_process_attach

- ea: `0x180012568`
- end: `0x180012662`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180012510`

## callees

- `0x180012568`
- `0x1800128a4`
- `0x1800128e4`
- `0x180012920`
- `0x180012a20`
- `0x180012af4`
- `0x180012b94`
- `0x180012d8c`
- `0x180012db4`
- `0x180012dd8`
- `0x180012de8`
- `0x180012df4`
- `0x1800131d6`
- `0x1800131e2`
- `0x180038010`

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
  ++dword_1800453B0;
  return 1;
}

```

## disassembly

```asm
0x180012568  push    rbx
0x18001256a  push    rsi
0x18001256b  push    rdi
0x18001256c  push    r14
0x18001256e  sub     rsp, 28h
0x180012572  mov     rsi, rdx
0x180012575  mov     r14, rcx
0x180012578  xor     ecx, ecx
0x18001257a  call    __scrt_initialize_crt
0x18001257f  test    al, al
0x180012581  jz      loc_18001264A
0x180012587  call    __scrt_acquire_startup_lock
0x18001258c  mov     bl, al
0x18001258e  mov     [rsp+48h+arg_10], al
0x180012592  mov     dil, 1
0x180012595  cmp     cs:__scrt_current_native_startup_state, 0
0x18001259c  jnz     loc_180012656
0x1800125a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800125ac  call    __scrt_dllmain_before_initialize_c
0x1800125b1  test    al, al
0x1800125b3  jz      short loc_180012604
0x1800125b5  call    _RTC_Initialize
0x1800125ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800125bf  call    __scrt_initialize_default_local_stdio_options
0x1800125c4  lea     rdx, __xi_z; Last
0x1800125cb  lea     rcx, __xi_a; First
0x1800125d2  call    _initterm_e_0
0x1800125d7  test    eax, eax
0x1800125d9  jnz     short loc_180012604
0x1800125db  call    __scrt_dllmain_after_initialize_c
0x1800125e0  test    al, al
0x1800125e2  jz      short loc_180012604
0x1800125e4  lea     rdx, __xc_z; Last
0x1800125eb  lea     rcx, __xc_a; First
0x1800125f2  call    _initterm_0
0x1800125f7  mov     cs:__scrt_current_native_startup_state, 2
0x180012601  xor     dil, dil
0x180012604  mov     cl, bl
0x180012606  call    __scrt_release_startup_lock
0x18001260b  test    dil, dil
0x18001260e  jnz     short loc_18001264A
0x180012610  call    __scrt_get_dyn_tls_init_callback
0x180012615  mov     rbx, rax
0x180012618  cmp     qword ptr [rax], 0
0x18001261c  jz      short loc_18001263D
0x18001261e  mov     rcx, rax
0x180012621  call    __scrt_is_nonwritable_in_current_image
0x180012626  test    al, al
0x180012628  jz      short loc_18001263D
0x18001262a  mov     r8, rsi
0x18001262d  mov     edx, 2
0x180012632  mov     rcx, r14
0x180012635  mov     rax, [rbx]
0x180012638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001263d  inc     cs:dword_1800453B0
0x180012643  mov     eax, 1
0x180012648  jmp     short loc_18001264C
0x18001264a  xor     eax, eax
0x18001264c  add     rsp, 28h
0x180012650  pop     r14
0x180012652  pop     rdi
0x180012653  pop     rsi
0x180012654  pop     rbx
0x180012655  retn
0x180012656  mov     ecx, 7
0x18001265b  call    __scrt_fastfail
0x180037862  push    rbp
0x180037864  sub     rsp, 20h
0x180037868  mov     rbp, rdx
0x18003786b  mov     cl, [rbp+60h]
0x18003786e  add     rsp, 20h
0x180037872  pop     rbp
0x180037873  jmp     __scrt_release_startup_lock
```
