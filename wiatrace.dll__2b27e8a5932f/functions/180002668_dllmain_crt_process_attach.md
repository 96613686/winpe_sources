# dllmain_crt_process_attach

- ea: `0x180002668`
- end: `0x180002762`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002610`

## callees

- `0x180002668`
- `0x180002a60`
- `0x180002a88`
- `0x180002aac`
- `0x180002aec`
- `0x180002b28`
- `0x180002c28`
- `0x180002cfc`
- `0x180002d9c`
- `0x180002df8`
- `0x180002e08`
- `0x180002e14`
- `0x180003176`
- `0x180003182`
- `0x180004010`

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
  ++dword_180007090;
  return 1;
}

```

## disassembly

```asm
0x180002668  push    rbx
0x18000266a  push    rsi
0x18000266b  push    rdi
0x18000266c  push    r14
0x18000266e  sub     rsp, 28h
0x180002672  mov     rsi, rdx
0x180002675  mov     r14, rcx
0x180002678  xor     ecx, ecx
0x18000267a  call    __scrt_initialize_crt
0x18000267f  test    al, al
0x180002681  jz      loc_18000274A
0x180002687  call    __scrt_acquire_startup_lock
0x18000268c  mov     bl, al
0x18000268e  mov     [rsp+48h+arg_10], al
0x180002692  mov     dil, 1
0x180002695  cmp     cs:__scrt_current_native_startup_state, 0
0x18000269c  jnz     loc_180002756
0x1800026a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800026ac  call    __scrt_dllmain_before_initialize_c
0x1800026b1  test    al, al
0x1800026b3  jz      short loc_180002704
0x1800026b5  call    _RTC_Initialize
0x1800026ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800026bf  call    __scrt_initialize_default_local_stdio_options
0x1800026c4  lea     rdx, __xi_z; Last
0x1800026cb  lea     rcx, __xi_a; First
0x1800026d2  call    _initterm_e_0
0x1800026d7  test    eax, eax
0x1800026d9  jnz     short loc_180002704
0x1800026db  call    __scrt_dllmain_after_initialize_c
0x1800026e0  test    al, al
0x1800026e2  jz      short loc_180002704
0x1800026e4  lea     rdx, __xc_z; Last
0x1800026eb  lea     rcx, __xc_a; First
0x1800026f2  call    _initterm_0
0x1800026f7  mov     cs:__scrt_current_native_startup_state, 2
0x180002701  xor     dil, dil
0x180002704  mov     cl, bl
0x180002706  call    __scrt_release_startup_lock
0x18000270b  test    dil, dil
0x18000270e  jnz     short loc_18000274A
0x180002710  call    __scrt_get_dyn_tls_init_callback
0x180002715  mov     rbx, rax
0x180002718  cmp     qword ptr [rax], 0
0x18000271c  jz      short loc_18000273D
0x18000271e  mov     rcx, rax
0x180002721  call    __scrt_is_nonwritable_in_current_image
0x180002726  test    al, al
0x180002728  jz      short loc_18000273D
0x18000272a  mov     r8, rsi
0x18000272d  mov     edx, 2
0x180002732  mov     rcx, r14
0x180002735  mov     rax, [rbx]
0x180002738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273d  inc     cs:dword_180007090
0x180002743  mov     eax, 1
0x180002748  jmp     short loc_18000274C
0x18000274a  xor     eax, eax
0x18000274c  add     rsp, 28h
0x180002750  pop     r14
0x180002752  pop     rdi
0x180002753  pop     rsi
0x180002754  pop     rbx
0x180002755  retn
0x180002756  mov     ecx, 7
0x18000275b  call    __scrt_fastfail
0x18000344c  push    rbp
0x18000344e  sub     rsp, 20h
0x180003452  mov     rbp, rdx
0x180003455  mov     cl, [rbp+60h]
0x180003458  add     rsp, 20h
0x18000345c  pop     rbp
0x18000345d  jmp     __scrt_release_startup_lock
```
