# __scrt_common_main_seh

- ea: `0x1400258e0`
- end: `0x140025a5b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140025a70`

## callees

- `0x140004c40`
- `0x1400258e0`
- `0x140025c94`
- `0x140025cd4`
- `0x140025da8`
- `0x140025e48`
- `0x140025e74`
- `0x140026114`
- `0x140026124`
- `0x140026134`
- `0x14002ad66`
- `0x14002ad96`
- `0x14002ada2`
- `0x14002adae`
- `0x14002adba`
- `0x14002adc6`
- `0x14002adde`
- `0x14002adea`
- `0x14002adf6`
- `0x14002ae02`
- `0x14002ae0e`
- `0x140035bc0`
- `0x140068010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // si
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v10; // rbx
  wchar_t **v11; // rbx
  int *v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = 0;
  v2 = _scrt_acquire_startup_lock(v0);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
    v1 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v2;
  _scrt_release_startup_lock(v3);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v8)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v7);
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  get_initial_wide_environment_0();
  v11 = *_p___wargv_0();
  v12 = _p___argc_0();
  v13 = wmain(*v12, (__int64)v11);
  if ( !(unsigned __int8)Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_MustDoNoWake(v14) )
    exit_0(v13);
  if ( !v1 )
    cexit_0();
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v13;
}

```

## disassembly

```asm
0x1400258e0  mov     [rsp+arg_0], rbx
0x1400258e5  mov     [rsp+arg_8], rsi
0x1400258ea  push    rdi
0x1400258eb  sub     rsp, 30h
0x1400258ef  mov     ecx, 1
0x1400258f4  call    __scrt_initialize_crt
0x1400258f9  test    al, al
0x1400258fb  jz      loc_140025A36
0x140025901  xor     sil, sil
0x140025904  mov     [rsp+38h+var_18], sil
0x140025909  call    __scrt_acquire_startup_lock
0x14002590e  mov     bl, al
0x140025910  mov     ecx, cs:__scrt_current_native_startup_state
0x140025916  cmp     ecx, 1
0x140025919  jz      loc_140025A41
0x14002591f  test    ecx, ecx
0x140025921  jnz     short loc_14002596D
0x140025923  mov     cs:__scrt_current_native_startup_state, 1
0x14002592d  lea     rdx, __xi_z; Last
0x140025934  lea     rcx, __xi_a; First
0x14002593b  call    _initterm_e_0
0x140025940  test    eax, eax
0x140025942  jz      short loc_14002594E
0x140025944  mov     eax, 0FFh
0x140025949  jmp     loc_140025A26
0x14002594e  lea     rdx, __xc_z; Last
0x140025955  lea     rcx, __xc_a; First
0x14002595c  call    _initterm_0
0x140025961  mov     cs:__scrt_current_native_startup_state, 2
0x14002596b  jmp     short loc_140025975
0x14002596d  mov     sil, 1
0x140025970  mov     [rsp+38h+var_18], sil
0x140025975  mov     cl, bl
0x140025977  call    __scrt_release_startup_lock
0x14002597c  call    __scrt_get_dyn_tls_init_callback
0x140025981  mov     rbx, rax
0x140025984  cmp     qword ptr [rax], 0
0x140025988  jz      short loc_1400259A7
0x14002598a  mov     rcx, rax
0x14002598d  call    __scrt_is_nonwritable_in_current_image
0x140025992  test    al, al
0x140025994  jz      short loc_1400259A7
0x140025996  xor     r8d, r8d
0x140025999  lea     edx, [r8+2]
0x14002599d  xor     ecx, ecx
0x14002599f  mov     rax, [rbx]
0x1400259a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400259a7  call    __scrt_get_dyn_tls_dtor_callback
0x1400259ac  mov     rbx, rax
0x1400259af  cmp     qword ptr [rax], 0
0x1400259b3  jz      short loc_1400259C9
0x1400259b5  mov     rcx, rax
0x1400259b8  call    __scrt_is_nonwritable_in_current_image
0x1400259bd  test    al, al
0x1400259bf  jz      short loc_1400259C9
0x1400259c1  mov     rcx, [rbx]; Callback
0x1400259c4  call    _register_thread_local_exe_atexit_callback_0
0x1400259c9  call    _get_initial_wide_environment_0
0x1400259ce  mov     rdi, rax
0x1400259d1  call    __p___wargv_0
0x1400259d6  mov     rbx, [rax]
0x1400259d9  call    __p___argc_0
0x1400259de  mov     r8, rdi
0x1400259e1  mov     rdx, rbx
0x1400259e4  mov     ecx, [rax]
0x1400259e6  call    wmain
0x1400259eb  mov     ebx, eax
0x1400259ed  call    ?v_MustDoNoWake@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@MEAA_NXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_MustDoNoWake(void)
0x1400259f2  test    al, al
0x1400259f4  jz      short loc_140025A4B
0x1400259f6  test    sil, sil
0x1400259f9  jnz     short loc_140025A00
0x1400259fb  call    _cexit_0
0x140025a00  xor     edx, edx
0x140025a02  mov     cl, 1
0x140025a04  call    __scrt_uninitialize_crt
0x140025a09  mov     eax, ebx
0x140025a0b  jmp     short loc_140025A26
0x140025a0d  mov     ebx, eax
0x140025a0f  call    ?v_MustDoNoWake@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@MEAA_NXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_MustDoNoWake(void)
0x140025a14  test    al, al
0x140025a16  jz      short loc_140025A53
0x140025a18  cmp     [rsp+38h+var_18], 0
0x140025a1d  jnz     short loc_140025A24
0x140025a1f  call    _c_exit_0
0x140025a24  mov     eax, ebx
0x140025a26  mov     rbx, [rsp+38h+arg_0]
0x140025a2b  mov     rsi, [rsp+38h+arg_8]
0x140025a30  add     rsp, 30h
0x140025a34  pop     rdi
0x140025a35  retn
0x140025a36  mov     ecx, 7
0x140025a3b  call    __scrt_fastfail
0x140025a41  mov     ecx, 7
0x140025a46  call    __scrt_fastfail
0x140025a4b  mov     ecx, ebx; Code
0x140025a4d  call    exit_0
0x140025a53  mov     ecx, ebx; Code
0x140025a55  call    _exit_0
0x140065dc7  push    rbp
0x140065dc9  sub     rsp, 20h
0x140065dcd  mov     rbp, rdx
0x140065dd0  mov     rdx, rcx; ExceptionPtr
0x140065dd3  mov     rcx, [rcx]
0x140065dd6  mov     ecx, [rcx]; ExceptionNum
0x140065dd8  call    _seh_filter_exe_0
0x140065ddd  nop
0x140065dde  add     rsp, 20h
0x140065de2  pop     rbp
0x140065de3  retn
```
