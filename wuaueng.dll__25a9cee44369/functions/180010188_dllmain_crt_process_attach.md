# dllmain_crt_process_attach

- ea: `0x180010188`
- end: `0x180010299`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180010130`

## callees

- `0x18000fcb4`
- `0x18000fcf4`
- `0x18000fd30`
- `0x18000fe54`
- `0x18000ff28`
- `0x18000ffc8`
- `0x180010188`
- `0x180010924`
- `0x180010b8c`
- `0x180010bc4`
- `0x180010be8`
- `0x180010bf8`
- `0x180015676`
- `0x180015682`
- `0x1800159b0`

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
    JUMPOUT(0x180010299LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( _scrt_dllmain_before_initialize_c() )
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
  ++dword_180021824;
  return 1;
}

```

## disassembly

```asm
0x180010188  mov     [rsp+arg_0], rbx
0x18001018d  mov     [rsp+arg_8], rsi
0x180010192  mov     [rsp+arg_18], rdi
0x180010197  push    r14
0x180010199  sub     rsp, 20h
0x18001019d  mov     rsi, rdx
0x1800101a0  mov     r14, rcx
0x1800101a3  xor     ecx, ecx
0x1800101a5  call    __scrt_initialize_crt
0x1800101aa  test    al, al
0x1800101ac  jz      loc_180010275
0x1800101b2  call    __scrt_acquire_startup_lock
0x1800101b7  mov     bl, al
0x1800101b9  mov     [rsp+28h+arg_10], al
0x1800101bd  mov     dil, 1
0x1800101c0  cmp     cs:__scrt_current_native_startup_state, 0
0x1800101c7  jnz     loc_18001028D
0x1800101cd  mov     cs:__scrt_current_native_startup_state, 1
0x1800101d7  call    __scrt_dllmain_before_initialize_c
0x1800101dc  test    al, al
0x1800101de  jz      short loc_18001022F
0x1800101e0  call    _RTC_Initialize
0x1800101e5  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800101ea  call    __scrt_initialize_default_local_stdio_options
0x1800101ef  lea     rdx, __xi_z; Last
0x1800101f6  lea     rcx, __xi_a; First
0x1800101fd  call    _initterm_e_0
0x180010202  test    eax, eax
0x180010204  jnz     short loc_18001022F
0x180010206  call    __scrt_dllmain_after_initialize_c
0x18001020b  test    al, al
0x18001020d  jz      short loc_18001022F
0x18001020f  lea     rdx, __xc_z; Last
0x180010216  lea     rcx, __xc_a; First
0x18001021d  call    _initterm_0
0x180010222  mov     cs:__scrt_current_native_startup_state, 2
0x18001022c  xor     dil, dil
0x18001022f  mov     cl, bl
0x180010231  call    __scrt_release_startup_lock
0x180010236  test    dil, dil
0x180010239  jnz     short loc_180010275
0x18001023b  call    __scrt_get_dyn_tls_init_callback
0x180010240  mov     rbx, rax
0x180010243  cmp     qword ptr [rax], 0
0x180010247  jz      short loc_180010268
0x180010249  mov     rcx, rax
0x18001024c  call    __scrt_is_nonwritable_in_current_image
0x180010251  test    al, al
0x180010253  jz      short loc_180010268
0x180010255  mov     r8, rsi
0x180010258  mov     edx, 2
0x18001025d  mov     rcx, r14
0x180010260  mov     rax, [rbx]
0x180010263  call    _guard_dispatch_icall
0x180010268  inc     cs:dword_180021824
0x18001026e  mov     eax, 1
0x180010273  jmp     short loc_180010277
0x180010275  xor     eax, eax
0x180010277  mov     rbx, [rsp+28h+arg_0]
0x18001027c  mov     rsi, [rsp+28h+arg_8]
0x180010281  mov     rdi, [rsp+28h+arg_18]
0x180010286  add     rsp, 20h
0x18001028a  pop     r14
0x18001028c  retn
0x18001028d  mov     ecx, 7
0x180010292  call    __scrt_fastfail
0x180010297  nop
0x180010298  int     3; Trap to Debugger
0x180016bff  push    rbp
0x180016c01  sub     rsp, 20h
0x180016c05  mov     rbp, rdx
0x180016c08  mov     cl, [rbp+40h]
0x180016c0b  add     rsp, 20h
0x180016c0f  pop     rbp
0x180016c10  jmp     __scrt_release_startup_lock
```
