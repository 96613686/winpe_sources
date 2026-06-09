# dllmain_crt_process_attach

- ea: `0x180005418`
- end: `0x180005512`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800053c0`

## callees

- `0x180005418`
- `0x18000583c`
- `0x180005864`
- `0x180005888`
- `0x1800058c8`
- `0x180005904`
- `0x180005a04`
- `0x180005ad8`
- `0x180005b78`
- `0x180005bd4`
- `0x180005be4`
- `0x180005bf0`
- `0x180005f46`
- `0x180005f52`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v7)(__int64, __int64, __int64); // rbx

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
  _scrt_release_startup_lock(v4);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v7)(a1, 2, a2);
  }
  ++dword_180010110;
  return 1;
}

```

## disassembly

```asm
0x180005418  push    rbx
0x18000541a  push    rsi
0x18000541b  push    rdi
0x18000541c  push    r14
0x18000541e  sub     rsp, 28h
0x180005422  mov     rsi, rdx
0x180005425  mov     r14, rcx
0x180005428  xor     ecx, ecx
0x18000542a  call    __scrt_initialize_crt
0x18000542f  test    al, al
0x180005431  jz      loc_1800054FA
0x180005437  call    __scrt_acquire_startup_lock
0x18000543c  mov     bl, al
0x18000543e  mov     [rsp+48h+arg_10], al
0x180005442  mov     dil, 1
0x180005445  cmp     cs:__scrt_current_native_startup_state, 0
0x18000544c  jnz     loc_180005506
0x180005452  mov     cs:__scrt_current_native_startup_state, 1
0x18000545c  call    __scrt_dllmain_before_initialize_c
0x180005461  test    al, al
0x180005463  jz      short loc_1800054B4
0x180005465  call    _RTC_Initialize
0x18000546a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000546f  call    __scrt_initialize_default_local_stdio_options
0x180005474  lea     rdx, __xi_z; Last
0x18000547b  lea     rcx, __xi_a; First
0x180005482  call    _initterm_e_0
0x180005487  test    eax, eax
0x180005489  jnz     short loc_1800054B4
0x18000548b  call    __scrt_dllmain_after_initialize_c
0x180005490  test    al, al
0x180005492  jz      short loc_1800054B4
0x180005494  lea     rdx, __xc_z; Last
0x18000549b  lea     rcx, __xc_a; First
0x1800054a2  call    _initterm_0
0x1800054a7  mov     cs:__scrt_current_native_startup_state, 2
0x1800054b1  xor     dil, dil
0x1800054b4  mov     cl, bl
0x1800054b6  call    __scrt_release_startup_lock
0x1800054bb  test    dil, dil
0x1800054be  jnz     short loc_1800054FA
0x1800054c0  call    __scrt_get_dyn_tls_init_callback
0x1800054c5  mov     rbx, rax
0x1800054c8  cmp     qword ptr [rax], 0
0x1800054cc  jz      short loc_1800054ED
0x1800054ce  mov     rcx, rax
0x1800054d1  call    __scrt_is_nonwritable_in_current_image
0x1800054d6  test    al, al
0x1800054d8  jz      short loc_1800054ED
0x1800054da  mov     r8, rsi
0x1800054dd  mov     edx, 2
0x1800054e2  mov     rcx, r14
0x1800054e5  mov     rax, [rbx]
0x1800054e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ed  inc     cs:dword_180010110
0x1800054f3  mov     eax, 1
0x1800054f8  jmp     short loc_1800054FC
0x1800054fa  xor     eax, eax
0x1800054fc  add     rsp, 28h
0x180005500  pop     r14
0x180005502  pop     rdi
0x180005503  pop     rsi
0x180005504  pop     rbx
0x180005505  retn
0x180005506  mov     ecx, 7
0x18000550b  call    __scrt_fastfail
0x18000ba8c  push    rbp
0x18000ba8e  sub     rsp, 20h
0x18000ba92  mov     rbp, rdx
0x18000ba95  mov     cl, [rbp+60h]
0x18000ba98  add     rsp, 20h
0x18000ba9c  pop     rbp
0x18000ba9d  jmp     __scrt_release_startup_lock
```
