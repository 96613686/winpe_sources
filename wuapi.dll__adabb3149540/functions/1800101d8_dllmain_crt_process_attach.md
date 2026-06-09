# dllmain_crt_process_attach

- ea: `0x1800101d8`
- end: `0x1800102e9`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180010180`

## callees

- `0x18000fd04`
- `0x18000fd44`
- `0x18000fd80`
- `0x18000fea4`
- `0x18000ff78`
- `0x180010018`
- `0x1800101d8`
- `0x180010974`
- `0x180010bdc`
- `0x180010c14`
- `0x180010c38`
- `0x180010c48`
- `0x1800156c6`
- `0x1800156d2`
- `0x180015a00`

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
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1800102E9LL);
  }
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
  ++dword_180021824;
  return 1;
}

```

## disassembly

```asm
0x1800101d8  mov     [rsp+arg_0], rbx
0x1800101dd  mov     [rsp+arg_8], rsi
0x1800101e2  mov     [rsp+arg_18], rdi
0x1800101e7  push    r14
0x1800101e9  sub     rsp, 20h
0x1800101ed  mov     rsi, rdx
0x1800101f0  mov     r14, rcx
0x1800101f3  xor     ecx, ecx
0x1800101f5  call    __scrt_initialize_crt
0x1800101fa  test    al, al
0x1800101fc  jz      loc_1800102C5
0x180010202  call    __scrt_acquire_startup_lock
0x180010207  mov     bl, al
0x180010209  mov     [rsp+28h+arg_10], al
0x18001020d  mov     dil, 1
0x180010210  cmp     cs:__scrt_current_native_startup_state, 0
0x180010217  jnz     loc_1800102DD
0x18001021d  mov     cs:__scrt_current_native_startup_state, 1
0x180010227  call    __scrt_dllmain_before_initialize_c
0x18001022c  test    al, al
0x18001022e  jz      short loc_18001027F
0x180010230  call    _RTC_Initialize
0x180010235  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001023a  call    __scrt_initialize_default_local_stdio_options
0x18001023f  lea     rdx, __xi_z; Last
0x180010246  lea     rcx, __xi_a; First
0x18001024d  call    _initterm_e_0
0x180010252  test    eax, eax
0x180010254  jnz     short loc_18001027F
0x180010256  call    __scrt_dllmain_after_initialize_c
0x18001025b  test    al, al
0x18001025d  jz      short loc_18001027F
0x18001025f  lea     rdx, __xc_z; Last
0x180010266  lea     rcx, __xc_a; First
0x18001026d  call    _initterm_0
0x180010272  mov     cs:__scrt_current_native_startup_state, 2
0x18001027c  xor     dil, dil
0x18001027f  mov     cl, bl
0x180010281  call    __scrt_release_startup_lock
0x180010286  test    dil, dil
0x180010289  jnz     short loc_1800102C5
0x18001028b  call    __scrt_get_dyn_tls_init_callback
0x180010290  mov     rbx, rax
0x180010293  cmp     qword ptr [rax], 0
0x180010297  jz      short loc_1800102B8
0x180010299  mov     rcx, rax
0x18001029c  call    __scrt_is_nonwritable_in_current_image
0x1800102a1  test    al, al
0x1800102a3  jz      short loc_1800102B8
0x1800102a5  mov     r8, rsi
0x1800102a8  mov     edx, 2
0x1800102ad  mov     rcx, r14
0x1800102b0  mov     rax, [rbx]
0x1800102b3  call    _guard_dispatch_icall
0x1800102b8  inc     cs:dword_180021824
0x1800102be  mov     eax, 1
0x1800102c3  jmp     short loc_1800102C7
0x1800102c5  xor     eax, eax
0x1800102c7  mov     rbx, [rsp+28h+arg_0]
0x1800102cc  mov     rsi, [rsp+28h+arg_8]
0x1800102d1  mov     rdi, [rsp+28h+arg_18]
0x1800102d6  add     rsp, 20h
0x1800102da  pop     r14
0x1800102dc  retn
0x1800102dd  mov     ecx, 7
0x1800102e2  call    __scrt_fastfail
0x1800102e7  nop
0x1800102e8  int     3; Trap to Debugger
0x180016c4f  push    rbp
0x180016c51  sub     rsp, 20h
0x180016c55  mov     rbp, rdx
0x180016c58  mov     cl, [rbp+40h]
0x180016c5b  add     rsp, 20h
0x180016c5f  pop     rbp
0x180016c60  jmp     __scrt_release_startup_lock
```
