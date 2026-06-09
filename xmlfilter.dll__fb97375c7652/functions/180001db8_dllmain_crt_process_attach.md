# dllmain_crt_process_attach

- ea: `0x180001db8`
- end: `0x180001eb2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001d60`

## callees

- `0x180001db8`
- `0x18000218c`
- `0x1800021cc`
- `0x180002208`
- `0x180002308`
- `0x1800023dc`
- `0x18000247c`
- `0x18000264c`
- `0x180002674`
- `0x180002698`
- `0x1800026a8`
- `0x1800026b4`
- `0x180002a16`
- `0x180002a22`
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
      if ( _scrt_dllmain_after_initialize_c() )
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
  ++dword_1800217F0;
  return 1;
}

```

## disassembly

```asm
0x180001db8  push    rbx
0x180001dba  push    rsi
0x180001dbb  push    rdi
0x180001dbc  push    r14
0x180001dbe  sub     rsp, 28h
0x180001dc2  mov     rsi, rdx
0x180001dc5  mov     r14, rcx
0x180001dc8  xor     ecx, ecx
0x180001dca  call    __scrt_initialize_crt
0x180001dcf  test    al, al
0x180001dd1  jz      loc_180001E9A
0x180001dd7  call    __scrt_acquire_startup_lock
0x180001ddc  mov     bl, al
0x180001dde  mov     [rsp+48h+arg_10], al
0x180001de2  mov     dil, 1
0x180001de5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001dec  jnz     loc_180001EA6
0x180001df2  mov     cs:__scrt_current_native_startup_state, 1
0x180001dfc  call    __scrt_dllmain_before_initialize_c
0x180001e01  test    al, al
0x180001e03  jz      short loc_180001E54
0x180001e05  call    _RTC_Initialize
0x180001e0a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001e0f  call    __scrt_initialize_default_local_stdio_options
0x180001e14  lea     rdx, __xi_z; Last
0x180001e1b  lea     rcx, __xi_a; First
0x180001e22  call    _initterm_e_0
0x180001e27  test    eax, eax
0x180001e29  jnz     short loc_180001E54
0x180001e2b  call    __scrt_dllmain_after_initialize_c
0x180001e30  test    al, al
0x180001e32  jz      short loc_180001E54
0x180001e34  lea     rdx, __xc_z; Last
0x180001e3b  lea     rcx, __xc_a; First
0x180001e42  call    _initterm_0
0x180001e47  mov     cs:__scrt_current_native_startup_state, 2
0x180001e51  xor     dil, dil
0x180001e54  mov     cl, bl
0x180001e56  call    __scrt_release_startup_lock
0x180001e5b  test    dil, dil
0x180001e5e  jnz     short loc_180001E9A
0x180001e60  call    __scrt_get_dyn_tls_init_callback
0x180001e65  mov     rbx, rax
0x180001e68  cmp     qword ptr [rax], 0
0x180001e6c  jz      short loc_180001E8D
0x180001e6e  mov     rcx, rax
0x180001e71  call    __scrt_is_nonwritable_in_current_image
0x180001e76  test    al, al
0x180001e78  jz      short loc_180001E8D
0x180001e7a  mov     r8, rsi
0x180001e7d  mov     edx, 2
0x180001e82  mov     rcx, r14
0x180001e85  mov     rax, [rbx]
0x180001e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e8d  inc     cs:dword_1800217F0
0x180001e93  mov     eax, 1
0x180001e98  jmp     short loc_180001E9C
0x180001e9a  xor     eax, eax
0x180001e9c  add     rsp, 28h
0x180001ea0  pop     r14
0x180001ea2  pop     rdi
0x180001ea3  pop     rsi
0x180001ea4  pop     rbx
0x180001ea5  retn
0x180001ea6  mov     ecx, 7
0x180001eab  call    __scrt_fastfail
0x1800144ec  push    rbp
0x1800144ee  sub     rsp, 20h
0x1800144f2  mov     rbp, rdx
0x1800144f5  mov     cl, [rbp+60h]
0x1800144f8  add     rsp, 20h
0x1800144fc  pop     rbp
0x1800144fd  jmp     __scrt_release_startup_lock
```
