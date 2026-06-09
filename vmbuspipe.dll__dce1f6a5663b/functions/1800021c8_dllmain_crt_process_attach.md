# dllmain_crt_process_attach

- ea: `0x1800021c8`
- end: `0x1800022c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002170`

## callees

- `0x1800021c8`
- `0x180002534`
- `0x180002574`
- `0x1800025b0`
- `0x1800026b0`
- `0x180002784`
- `0x180002824`
- `0x1800029f8`
- `0x180002a20`
- `0x180002a44`
- `0x180002a54`
- `0x180002a60`
- `0x180002fa6`
- `0x180002fb2`
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
  ++dword_18000C1F0;
  return 1;
}

```

## disassembly

```asm
0x1800021c8  push    rbx
0x1800021ca  push    rsi
0x1800021cb  push    rdi
0x1800021cc  push    r14
0x1800021ce  sub     rsp, 28h
0x1800021d2  mov     rsi, rdx
0x1800021d5  mov     r14, rcx
0x1800021d8  xor     ecx, ecx
0x1800021da  call    __scrt_initialize_crt
0x1800021df  test    al, al
0x1800021e1  jz      loc_1800022AA
0x1800021e7  call    __scrt_acquire_startup_lock
0x1800021ec  mov     bl, al
0x1800021ee  mov     [rsp+48h+arg_10], al
0x1800021f2  mov     dil, 1
0x1800021f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800021fc  jnz     loc_1800022B6
0x180002202  mov     cs:__scrt_current_native_startup_state, 1
0x18000220c  call    __scrt_dllmain_before_initialize_c
0x180002211  test    al, al
0x180002213  jz      short loc_180002264
0x180002215  call    _RTC_Initialize
0x18000221a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000221f  call    __scrt_initialize_default_local_stdio_options
0x180002224  lea     rdx, __xi_z; Last
0x18000222b  lea     rcx, __xi_a; First
0x180002232  call    _initterm_e_0
0x180002237  test    eax, eax
0x180002239  jnz     short loc_180002264
0x18000223b  call    __scrt_dllmain_after_initialize_c
0x180002240  test    al, al
0x180002242  jz      short loc_180002264
0x180002244  lea     rdx, __xc_z; Last
0x18000224b  lea     rcx, __xc_a; First
0x180002252  call    _initterm_0
0x180002257  mov     cs:__scrt_current_native_startup_state, 2
0x180002261  xor     dil, dil
0x180002264  mov     cl, bl
0x180002266  call    __scrt_release_startup_lock
0x18000226b  test    dil, dil
0x18000226e  jnz     short loc_1800022AA
0x180002270  call    __scrt_get_dyn_tls_init_callback
0x180002275  mov     rbx, rax
0x180002278  cmp     qword ptr [rax], 0
0x18000227c  jz      short loc_18000229D
0x18000227e  mov     rcx, rax
0x180002281  call    __scrt_is_nonwritable_in_current_image
0x180002286  test    al, al
0x180002288  jz      short loc_18000229D
0x18000228a  mov     r8, rsi
0x18000228d  mov     edx, 2
0x180002292  mov     rcx, r14
0x180002295  mov     rax, [rbx]
0x180002298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000229d  inc     cs:dword_18000C1F0
0x1800022a3  mov     eax, 1
0x1800022a8  jmp     short loc_1800022AC
0x1800022aa  xor     eax, eax
0x1800022ac  add     rsp, 28h
0x1800022b0  pop     r14
0x1800022b2  pop     rdi
0x1800022b3  pop     rsi
0x1800022b4  pop     rbx
0x1800022b5  retn
0x1800022b6  mov     ecx, 7
0x1800022bb  call    __scrt_fastfail
0x180007a30  push    rbp
0x180007a32  sub     rsp, 20h
0x180007a36  mov     rbp, rdx
0x180007a39  mov     cl, [rbp+60h]
0x180007a3c  add     rsp, 20h
0x180007a40  pop     rbp
0x180007a41  jmp     __scrt_release_startup_lock
```
