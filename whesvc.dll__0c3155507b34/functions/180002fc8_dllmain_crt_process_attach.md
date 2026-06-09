# dllmain_crt_process_attach

- ea: `0x180002fc8`
- end: `0x1800030c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002f70`

## callees

- `0x180002fc8`
- `0x18000333c`
- `0x18000337c`
- `0x1800033b8`
- `0x1800034b8`
- `0x18000358c`
- `0x18000362c`
- `0x180003818`
- `0x180003840`
- `0x180003864`
- `0x180003874`
- `0x180003880`
- `0x180003c56`
- `0x180003c62`
- `0x180029010`

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
  ++dword_180034790;
  return 1;
}

```

## disassembly

```asm
0x180002fc8  push    rbx
0x180002fca  push    rsi
0x180002fcb  push    rdi
0x180002fcc  push    r14
0x180002fce  sub     rsp, 28h
0x180002fd2  mov     rsi, rdx
0x180002fd5  mov     r14, rcx
0x180002fd8  xor     ecx, ecx
0x180002fda  call    __scrt_initialize_crt
0x180002fdf  test    al, al
0x180002fe1  jz      loc_1800030AA
0x180002fe7  call    __scrt_acquire_startup_lock
0x180002fec  mov     bl, al
0x180002fee  mov     [rsp+48h+arg_10], al
0x180002ff2  mov     dil, 1
0x180002ff5  cmp     cs:__scrt_current_native_startup_state, 0
0x180002ffc  jnz     loc_1800030B6
0x180003002  mov     cs:__scrt_current_native_startup_state, 1
0x18000300c  call    __scrt_dllmain_before_initialize_c
0x180003011  test    al, al
0x180003013  jz      short loc_180003064
0x180003015  call    _RTC_Initialize
0x18000301a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000301f  call    __scrt_initialize_default_local_stdio_options
0x180003024  lea     rdx, __xi_z; Last
0x18000302b  lea     rcx, __xi_a; First
0x180003032  call    _initterm_e_0
0x180003037  test    eax, eax
0x180003039  jnz     short loc_180003064
0x18000303b  call    __scrt_dllmain_after_initialize_c
0x180003040  test    al, al
0x180003042  jz      short loc_180003064
0x180003044  lea     rdx, __xc_z; Last
0x18000304b  lea     rcx, __xc_a; First
0x180003052  call    _initterm_0
0x180003057  mov     cs:__scrt_current_native_startup_state, 2
0x180003061  xor     dil, dil
0x180003064  mov     cl, bl
0x180003066  call    __scrt_release_startup_lock
0x18000306b  test    dil, dil
0x18000306e  jnz     short loc_1800030AA
0x180003070  call    __scrt_get_dyn_tls_init_callback
0x180003075  mov     rbx, rax
0x180003078  cmp     qword ptr [rax], 0
0x18000307c  jz      short loc_18000309D
0x18000307e  mov     rcx, rax
0x180003081  call    __scrt_is_nonwritable_in_current_image
0x180003086  test    al, al
0x180003088  jz      short loc_18000309D
0x18000308a  mov     r8, rsi
0x18000308d  mov     edx, 2
0x180003092  mov     rcx, r14
0x180003095  mov     rax, [rbx]
0x180003098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309d  inc     cs:dword_180034790
0x1800030a3  mov     eax, 1
0x1800030a8  jmp     short loc_1800030AC
0x1800030aa  xor     eax, eax
0x1800030ac  add     rsp, 28h
0x1800030b0  pop     r14
0x1800030b2  pop     rdi
0x1800030b3  pop     rsi
0x1800030b4  pop     rbx
0x1800030b5  retn
0x1800030b6  mov     ecx, 7
0x1800030bb  call    __scrt_fastfail
0x18002669c  push    rbp
0x18002669e  sub     rsp, 20h
0x1800266a2  mov     rbp, rdx
0x1800266a5  mov     cl, [rbp+60h]
0x1800266a8  add     rsp, 20h
0x1800266ac  pop     rbp
0x1800266ad  jmp     __scrt_release_startup_lock
```
