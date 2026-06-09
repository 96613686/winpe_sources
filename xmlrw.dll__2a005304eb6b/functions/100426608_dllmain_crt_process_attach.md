# dllmain_crt_process_attach

- ea: `0x100426608`
- end: `0x10042671e`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1004265b0`

## callees

- `0x100426608`
- `0x100426ca8`
- `0x100426ce0`
- `0x100426d04`
- `0x100426d44`
- `0x100426d80`
- `0x100426ea4`
- `0x100426f88`
- `0x100427028`
- `0x1004270e4`
- `0x100427104`
- `0x100427258`
- `0x100429e98`
- `0x100429ee0`
- `0x100439df0`

## pseudocode

```c
__int64 dllmain_crt_process_attach()
{
  char v0; // bl
  char v1; // di
  __int64 v2; // rcx
  _QWORD *dyn_tls_init_callback; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v0 = _scrt_acquire_startup_lock();
  v1 = 1;
  if ( _scrt_current_native_startup_state )
  {
    _scrt_fastfail(7);
    __debugbreak();
  }
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v1 = 0;
      }
    }
  }
  LOBYTE(v2) = v0;
  _scrt_release_startup_lock(v2);
  if ( v1 )
    return 0;
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback();
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
  }
  ++dword_100450C54;
  return 1;
}

```

## disassembly

```asm
0x100426608  mov     [rsp+arg_0], rbx
0x10042660d  mov     [rsp+arg_8], rsi
0x100426612  mov     [rsp+arg_18], rdi
0x100426617  push    r14
0x100426619  sub     rsp, 20h
0x10042661d  mov     rsi, rdx
0x100426620  mov     r14, rcx
0x100426623  xor     ecx, ecx
0x100426625  call    __scrt_initialize_crt
0x10042662a  test    al, al
0x10042662c  jz      loc_1004266FA
0x100426632  call    __scrt_acquire_startup_lock
0x100426637  mov     bl, al
0x100426639  mov     [rsp+28h+arg_10], al
0x10042663d  mov     dil, 1
0x100426640  cmp     cs:__scrt_current_native_startup_state, 0
0x100426647  jnz     loc_100426712
0x10042664d  mov     cs:__scrt_current_native_startup_state, 1
0x100426657  call    __scrt_dllmain_before_initialize_c
0x10042665c  test    al, al
0x10042665e  jz      short loc_1004266AF
0x100426660  call    _RTC_Initialize
0x100426665  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x10042666a  call    __scrt_initialize_default_local_stdio_options
0x10042666f  lea     rdx, __xi_z; Last
0x100426676  lea     rcx, __xi_a; First
0x10042667d  call    _initterm_e
0x100426682  test    eax, eax
0x100426684  jnz     short loc_1004266AF
0x100426686  call    __scrt_dllmain_after_initialize_c
0x10042668b  test    al, al
0x10042668d  jz      short loc_1004266AF
0x10042668f  lea     rdx, __xc_z; Last
0x100426696  lea     rcx, __xc_a; First
0x10042669d  call    _initterm
0x1004266a2  mov     cs:__scrt_current_native_startup_state, 2
0x1004266ac  xor     dil, dil
0x1004266af  mov     cl, bl
0x1004266b1  call    __scrt_release_startup_lock
0x1004266b6  test    dil, dil
0x1004266b9  jnz     short loc_1004266FA
0x1004266bb  call    __scrt_get_dyn_tls_init_callback
0x1004266c0  mov     rbx, rax
0x1004266c3  cmp     qword ptr [rax], 0
0x1004266c7  jz      short loc_1004266ED
0x1004266c9  mov     rcx, rax
0x1004266cc  call    __scrt_is_nonwritable_in_current_image
0x1004266d1  test    al, al
0x1004266d3  jz      short loc_1004266ED
0x1004266d5  mov     r8, rsi
0x1004266d8  mov     edx, 2
0x1004266dd  mov     rcx, r14
0x1004266e0  mov     rax, [rbx]
0x1004266e3  mov     r9, cs:__guard_dispatch_icall_fptr
0x1004266ea  call    r9 ; _guard_dispatch_icall_nop
0x1004266ed  inc     cs:dword_100450C54
0x1004266f3  mov     eax, 1
0x1004266f8  jmp     short loc_1004266FC
0x1004266fa  xor     eax, eax
0x1004266fc  mov     rbx, [rsp+28h+arg_0]
0x100426701  mov     rsi, [rsp+28h+arg_8]
0x100426706  mov     rdi, [rsp+28h+arg_18]
0x10042670b  add     rsp, 20h
0x10042670f  pop     r14
0x100426711  retn
0x100426712  mov     ecx, 7
0x100426717  call    __scrt_fastfail
0x10042671c  nop
0x10042671d  int     3; Trap to Debugger
0x10043a860  push    rbp
0x10043a862  sub     rsp, 20h
0x10043a866  mov     rbp, rdx
0x10043a869  mov     cl, [rbp+40h]
0x10043a86c  add     rsp, 20h
0x10043a870  pop     rbp
0x10043a871  jmp     __scrt_release_startup_lock
```
