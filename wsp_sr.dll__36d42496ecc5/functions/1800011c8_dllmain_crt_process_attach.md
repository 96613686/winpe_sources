# dllmain_crt_process_attach

- ea: `0x1800011c8`
- end: `0x1800012c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001170`

## callees

- `0x1800011c8`
- `0x1800015dc`
- `0x180001604`
- `0x180001628`
- `0x180001668`
- `0x1800016a4`
- `0x1800017a4`
- `0x180001878`
- `0x180001918`
- `0x1800019d4`
- `0x1800019e4`
- `0x1800019f0`
- `0x180001d16`
- `0x180001d22`
- `0x18002d010`

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
  ++dword_1800C7230;
  return 1;
}

```

## disassembly

```asm
0x1800011c8  push    rbx
0x1800011ca  push    rsi
0x1800011cb  push    rdi
0x1800011cc  push    r14
0x1800011ce  sub     rsp, 28h
0x1800011d2  mov     rsi, rdx
0x1800011d5  mov     r14, rcx
0x1800011d8  xor     ecx, ecx
0x1800011da  call    __scrt_initialize_crt
0x1800011df  test    al, al
0x1800011e1  jz      loc_1800012AA
0x1800011e7  call    __scrt_acquire_startup_lock
0x1800011ec  mov     bl, al
0x1800011ee  mov     [rsp+48h+arg_10], al
0x1800011f2  mov     dil, 1
0x1800011f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800011fc  jnz     loc_1800012B6
0x180001202  mov     cs:__scrt_current_native_startup_state, 1
0x18000120c  call    __scrt_dllmain_before_initialize_c
0x180001211  test    al, al
0x180001213  jz      short loc_180001264
0x180001215  call    _RTC_Initialize
0x18000121a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000121f  call    __scrt_initialize_default_local_stdio_options
0x180001224  lea     rdx, __xi_z; Last
0x18000122b  lea     rcx, __xi_a; First
0x180001232  call    _initterm_e_0
0x180001237  test    eax, eax
0x180001239  jnz     short loc_180001264
0x18000123b  call    __scrt_dllmain_after_initialize_c
0x180001240  test    al, al
0x180001242  jz      short loc_180001264
0x180001244  lea     rdx, __xc_z; Last
0x18000124b  lea     rcx, __xc_a; First
0x180001252  call    _initterm_0
0x180001257  mov     cs:__scrt_current_native_startup_state, 2
0x180001261  xor     dil, dil
0x180001264  mov     cl, bl
0x180001266  call    __scrt_release_startup_lock
0x18000126b  test    dil, dil
0x18000126e  jnz     short loc_1800012AA
0x180001270  call    __scrt_get_dyn_tls_init_callback
0x180001275  mov     rbx, rax
0x180001278  cmp     qword ptr [rax], 0
0x18000127c  jz      short loc_18000129D
0x18000127e  mov     rcx, rax
0x180001281  call    __scrt_is_nonwritable_in_current_image
0x180001286  test    al, al
0x180001288  jz      short loc_18000129D
0x18000128a  mov     r8, rsi
0x18000128d  mov     edx, 2
0x180001292  mov     rcx, r14
0x180001295  mov     rax, [rbx]
0x180001298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000129d  inc     cs:dword_1800C7230
0x1800012a3  mov     eax, 1
0x1800012a8  jmp     short loc_1800012AC
0x1800012aa  xor     eax, eax
0x1800012ac  add     rsp, 28h
0x1800012b0  pop     r14
0x1800012b2  pop     rdi
0x1800012b3  pop     rsi
0x1800012b4  pop     rbx
0x1800012b5  retn
0x1800012b6  mov     ecx, 7
0x1800012bb  call    __scrt_fastfail
0x180029e1c  push    rbp
0x180029e1e  sub     rsp, 20h
0x180029e22  mov     rbp, rdx
0x180029e25  mov     cl, [rbp+60h]
0x180029e28  add     rsp, 20h
0x180029e2c  pop     rbp
0x180029e2d  jmp     __scrt_release_startup_lock
```
