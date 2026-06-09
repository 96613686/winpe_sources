# dllmain_crt_process_attach

- ea: `0x1800341f8`
- end: `0x1800342f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800341a0`

## callees

- `0x1800341f8`
- `0x180034534`
- `0x180034574`
- `0x1800345b0`
- `0x1800346b0`
- `0x180034784`
- `0x180034824`
- `0x1800349a8`
- `0x1800349d0`
- `0x1800349f4`
- `0x180034a04`
- `0x180034a10`
- `0x180034d86`
- `0x180034d92`
- `0x18004d010`

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
  ++dword_1800655B0;
  return 1;
}

```

## disassembly

```asm
0x1800341f8  push    rbx
0x1800341fa  push    rsi
0x1800341fb  push    rdi
0x1800341fc  push    r14
0x1800341fe  sub     rsp, 28h
0x180034202  mov     rsi, rdx
0x180034205  mov     r14, rcx
0x180034208  xor     ecx, ecx
0x18003420a  call    __scrt_initialize_crt
0x18003420f  test    al, al
0x180034211  jz      loc_1800342DA
0x180034217  call    __scrt_acquire_startup_lock
0x18003421c  mov     bl, al
0x18003421e  mov     [rsp+48h+arg_10], al
0x180034222  mov     dil, 1
0x180034225  cmp     cs:__scrt_current_native_startup_state, 0
0x18003422c  jnz     loc_1800342E6
0x180034232  mov     cs:__scrt_current_native_startup_state, 1
0x18003423c  call    __scrt_dllmain_before_initialize_c
0x180034241  test    al, al
0x180034243  jz      short loc_180034294
0x180034245  call    _RTC_Initialize
0x18003424a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18003424f  call    __scrt_initialize_default_local_stdio_options
0x180034254  lea     rdx, __xi_z; Last
0x18003425b  lea     rcx, __xi_a; First
0x180034262  call    _initterm_e_0
0x180034267  test    eax, eax
0x180034269  jnz     short loc_180034294
0x18003426b  call    __scrt_dllmain_after_initialize_c
0x180034270  test    al, al
0x180034272  jz      short loc_180034294
0x180034274  lea     rdx, __xc_z; Last
0x18003427b  lea     rcx, __xc_a; First
0x180034282  call    _initterm_0
0x180034287  mov     cs:__scrt_current_native_startup_state, 2
0x180034291  xor     dil, dil
0x180034294  mov     cl, bl
0x180034296  call    __scrt_release_startup_lock
0x18003429b  test    dil, dil
0x18003429e  jnz     short loc_1800342DA
0x1800342a0  call    __scrt_get_dyn_tls_init_callback
0x1800342a5  mov     rbx, rax
0x1800342a8  cmp     qword ptr [rax], 0
0x1800342ac  jz      short loc_1800342CD
0x1800342ae  mov     rcx, rax
0x1800342b1  call    __scrt_is_nonwritable_in_current_image
0x1800342b6  test    al, al
0x1800342b8  jz      short loc_1800342CD
0x1800342ba  mov     r8, rsi
0x1800342bd  mov     edx, 2
0x1800342c2  mov     rcx, r14
0x1800342c5  mov     rax, [rbx]
0x1800342c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342cd  inc     cs:dword_1800655B0
0x1800342d3  mov     eax, 1
0x1800342d8  jmp     short loc_1800342DC
0x1800342da  xor     eax, eax
0x1800342dc  add     rsp, 28h
0x1800342e0  pop     r14
0x1800342e2  pop     rdi
0x1800342e3  pop     rsi
0x1800342e4  pop     rbx
0x1800342e5  retn
0x1800342e6  mov     ecx, 7
0x1800342eb  call    __scrt_fastfail
0x18004c8bd  push    rbp
0x18004c8bf  sub     rsp, 20h
0x18004c8c3  mov     rbp, rdx
0x18004c8c6  mov     cl, [rbp+60h]
0x18004c8c9  add     rsp, 20h
0x18004c8cd  pop     rbp
0x18004c8ce  jmp     __scrt_release_startup_lock
```
