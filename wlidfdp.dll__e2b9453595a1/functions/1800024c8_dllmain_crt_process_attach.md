# dllmain_crt_process_attach

- ea: `0x1800024c8`
- end: `0x1800025c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002470`

## callees

- `0x1800024c8`
- `0x18000284c`
- `0x18000288c`
- `0x1800028c8`
- `0x1800029c8`
- `0x180002a9c`
- `0x180002b3c`
- `0x180002d50`
- `0x180002d78`
- `0x180002d9c`
- `0x180002dac`
- `0x180002db8`
- `0x180003286`
- `0x180003292`
- `0x180012010`

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
  ++dword_180020490;
  return 1;
}

```

## disassembly

```asm
0x1800024c8  push    rbx
0x1800024ca  push    rsi
0x1800024cb  push    rdi
0x1800024cc  push    r14
0x1800024ce  sub     rsp, 28h
0x1800024d2  mov     rsi, rdx
0x1800024d5  mov     r14, rcx
0x1800024d8  xor     ecx, ecx
0x1800024da  call    __scrt_initialize_crt
0x1800024df  test    al, al
0x1800024e1  jz      loc_1800025AA
0x1800024e7  call    __scrt_acquire_startup_lock
0x1800024ec  mov     bl, al
0x1800024ee  mov     [rsp+48h+arg_10], al
0x1800024f2  mov     dil, 1
0x1800024f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800024fc  jnz     loc_1800025B6
0x180002502  mov     cs:__scrt_current_native_startup_state, 1
0x18000250c  call    __scrt_dllmain_before_initialize_c
0x180002511  test    al, al
0x180002513  jz      short loc_180002564
0x180002515  call    _RTC_Initialize
0x18000251a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000251f  call    __scrt_initialize_default_local_stdio_options
0x180002524  lea     rdx, __xi_z; Last
0x18000252b  lea     rcx, __xi_a; First
0x180002532  call    _initterm_e_0
0x180002537  test    eax, eax
0x180002539  jnz     short loc_180002564
0x18000253b  call    __scrt_dllmain_after_initialize_c
0x180002540  test    al, al
0x180002542  jz      short loc_180002564
0x180002544  lea     rdx, __xc_z; Last
0x18000254b  lea     rcx, __xc_a; First
0x180002552  call    _initterm_0
0x180002557  mov     cs:__scrt_current_native_startup_state, 2
0x180002561  xor     dil, dil
0x180002564  mov     cl, bl
0x180002566  call    __scrt_release_startup_lock
0x18000256b  test    dil, dil
0x18000256e  jnz     short loc_1800025AA
0x180002570  call    __scrt_get_dyn_tls_init_callback
0x180002575  mov     rbx, rax
0x180002578  cmp     qword ptr [rax], 0
0x18000257c  jz      short loc_18000259D
0x18000257e  mov     rcx, rax
0x180002581  call    __scrt_is_nonwritable_in_current_image
0x180002586  test    al, al
0x180002588  jz      short loc_18000259D
0x18000258a  mov     r8, rsi
0x18000258d  mov     edx, 2
0x180002592  mov     rcx, r14
0x180002595  mov     rax, [rbx]
0x180002598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259d  inc     cs:dword_180020490
0x1800025a3  mov     eax, 1
0x1800025a8  jmp     short loc_1800025AC
0x1800025aa  xor     eax, eax
0x1800025ac  add     rsp, 28h
0x1800025b0  pop     r14
0x1800025b2  pop     rdi
0x1800025b3  pop     rsi
0x1800025b4  pop     rbx
0x1800025b5  retn
0x1800025b6  mov     ecx, 7
0x1800025bb  call    __scrt_fastfail
0x1800106cc  push    rbp
0x1800106ce  sub     rsp, 20h
0x1800106d2  mov     rbp, rdx
0x1800106d5  mov     cl, [rbp+60h]
0x1800106d8  add     rsp, 20h
0x1800106dc  pop     rbp
0x1800106dd  jmp     __scrt_release_startup_lock
```
