# dllmain_crt_process_attach

- ea: `0x18000bf28`
- end: `0x18000c022`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000bed0`

## callees

- `0x18000bf28`
- `0x18000c32c`
- `0x18000c354`
- `0x18000c378`
- `0x18000c3b8`
- `0x18000c3f4`
- `0x18000c4f4`
- `0x18000c5c8`
- `0x18000c668`
- `0x18000c724`
- `0x18000c734`
- `0x18000c740`
- `0x18000caa6`
- `0x18000cab2`
- `0x180017010`

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
  ++dword_1800203D0;
  return 1;
}

```

## disassembly

```asm
0x18000bf28  push    rbx
0x18000bf2a  push    rsi
0x18000bf2b  push    rdi
0x18000bf2c  push    r14
0x18000bf2e  sub     rsp, 28h
0x18000bf32  mov     rsi, rdx
0x18000bf35  mov     r14, rcx
0x18000bf38  xor     ecx, ecx
0x18000bf3a  call    __scrt_initialize_crt
0x18000bf3f  test    al, al
0x18000bf41  jz      loc_18000C00A
0x18000bf47  call    __scrt_acquire_startup_lock
0x18000bf4c  mov     bl, al
0x18000bf4e  mov     [rsp+48h+arg_10], al
0x18000bf52  mov     dil, 1
0x18000bf55  cmp     cs:__scrt_current_native_startup_state, 0
0x18000bf5c  jnz     loc_18000C016
0x18000bf62  mov     cs:__scrt_current_native_startup_state, 1
0x18000bf6c  call    __scrt_dllmain_before_initialize_c
0x18000bf71  test    al, al
0x18000bf73  jz      short loc_18000BFC4
0x18000bf75  call    _RTC_Initialize
0x18000bf7a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000bf7f  call    __scrt_initialize_default_local_stdio_options
0x18000bf84  lea     rdx, __xi_z; Last
0x18000bf8b  lea     rcx, __xi_a; First
0x18000bf92  call    _initterm_e_0
0x18000bf97  test    eax, eax
0x18000bf99  jnz     short loc_18000BFC4
0x18000bf9b  call    __scrt_dllmain_after_initialize_c
0x18000bfa0  test    al, al
0x18000bfa2  jz      short loc_18000BFC4
0x18000bfa4  lea     rdx, __xc_z; Last
0x18000bfab  lea     rcx, __xc_a; First
0x18000bfb2  call    _initterm_0
0x18000bfb7  mov     cs:__scrt_current_native_startup_state, 2
0x18000bfc1  xor     dil, dil
0x18000bfc4  mov     cl, bl
0x18000bfc6  call    __scrt_release_startup_lock
0x18000bfcb  test    dil, dil
0x18000bfce  jnz     short loc_18000C00A
0x18000bfd0  call    __scrt_get_dyn_tls_init_callback
0x18000bfd5  mov     rbx, rax
0x18000bfd8  cmp     qword ptr [rax], 0
0x18000bfdc  jz      short loc_18000BFFD
0x18000bfde  mov     rcx, rax
0x18000bfe1  call    __scrt_is_nonwritable_in_current_image
0x18000bfe6  test    al, al
0x18000bfe8  jz      short loc_18000BFFD
0x18000bfea  mov     r8, rsi
0x18000bfed  mov     edx, 2
0x18000bff2  mov     rcx, r14
0x18000bff5  mov     rax, [rbx]
0x18000bff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bffd  inc     cs:dword_1800203D0
0x18000c003  mov     eax, 1
0x18000c008  jmp     short loc_18000C00C
0x18000c00a  xor     eax, eax
0x18000c00c  add     rsp, 28h
0x18000c010  pop     r14
0x18000c012  pop     rdi
0x18000c013  pop     rsi
0x18000c014  pop     rbx
0x18000c015  retn
0x18000c016  mov     ecx, 7
0x18000c01b  call    __scrt_fastfail
0x180016d6c  push    rbp
0x180016d6e  sub     rsp, 20h
0x180016d72  mov     rbp, rdx
0x180016d75  mov     cl, [rbp+60h]
0x180016d78  add     rsp, 20h
0x180016d7c  pop     rbp
0x180016d7d  jmp     __scrt_release_startup_lock
```
