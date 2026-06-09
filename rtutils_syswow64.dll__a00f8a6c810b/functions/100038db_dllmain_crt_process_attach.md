# dllmain_crt_process_attach

- ea: `0x100038db`
- end: `0x100039e4`
- name: `dllmain_crt_process_attach`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x10003880`

## callees

- `0x100038db`
- `0x10003d2d`
- `0x10003d51`
- `0x10003dbe`
- `0x10003df8`
- `0x10003e29`
- `0x10003ee8`
- `0x10003fb8`
- `0x10004055`
- `0x100040aa`
- `0x100040b6`
- `0x100040c8`
- `0x10004130`
- `0x10004190`
- `0x100044d7`
- `0x100044e3`

## pseudocode

```c
int __cdecl dllmain_crt_process_attach(int a1, int a2)
{
  char v2; // bl
  _DWORD *dyn_tls_init_callback; // eax
  _DWORD *v4; // esi
  char v6; // [esp+13h] [ebp-1Dh]

  if ( !(unsigned __int8)__scrt_initialize_crt(0) )
    return 0;
  v6 = __scrt_acquire_startup_lock();
  v2 = 1;
  if ( __scrt_current_native_startup_state )
    __scrt_fastfail(7);
  __scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)__scrt_dllmain_before_initialize_c() )
  {
    _RTC_Initialize();
    __scrt_initialize_type_info();
    __scrt_initialize_default_local_stdio_options();
    if ( !_initterm_e((_PIFV *)&__xi_a, (_PIFV *)&__xi_z) )
    {
      if ( (unsigned __int8)__scrt_dllmain_after_initialize_c() )
      {
        _initterm((_PVFV *)&__xc_a, (_PVFV *)&__xc_z);
        __scrt_current_native_startup_state = 2;
        v2 = 0;
      }
    }
  }
  __scrt_release_startup_lock(v6);
  if ( v2 )
    return 0;
  dyn_tls_init_callback = (_DWORD *)__scrt_get_dyn_tls_init_callback();
  v4 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)__scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      ((void (__thiscall *)(_DWORD, int, int, int))*v4)(*v4, a1, 2, a2);
  }
  ++dword_1000B0B0;
  return 1;
}

```

## disassembly

```asm
0x100038db  push    10h
0x100038dd  push    offset stru_1000A6F0
0x100038e2  call    __SEH_prolog4
0x100038e7  push    0
0x100038e9  call    ___scrt_initialize_crt
0x100038ee  pop     ecx
0x100038ef  test    al, al
0x100038f1  jz      loc_100039CB
0x100038f7  call    ___scrt_acquire_startup_lock
0x100038fc  mov     byte ptr [ebp+var_1D], al
0x100038ff  mov     bl, 1
0x10003901  mov     [ebp+var_19], bl
0x10003904  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1000390b  cmp     ___scrt_current_native_startup_state, 0
0x10003912  jnz     loc_100039DD
0x10003918  mov     ___scrt_current_native_startup_state, 1
0x10003922  call    ___scrt_dllmain_before_initialize_c
0x10003927  test    al, al
0x10003929  jz      short loc_10003978
0x1000392b  call    __RTC_Initialize
0x10003930  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x10003935  call    ___scrt_initialize_default_local_stdio_options
0x1000393a  push    offset ___xi_z; Last
0x1000393f  push    offset ___xi_a; First
0x10003944  call    __initterm_e
0x10003949  pop     ecx
0x1000394a  pop     ecx
0x1000394b  test    eax, eax
0x1000394d  jnz     short loc_10003978
0x1000394f  call    ___scrt_dllmain_after_initialize_c
0x10003954  test    al, al
0x10003956  jz      short loc_10003978
0x10003958  push    offset ___xc_z; Last
0x1000395d  push    offset ___xc_a; First
0x10003962  call    __initterm
0x10003967  pop     ecx
0x10003968  pop     ecx
0x10003969  mov     ___scrt_current_native_startup_state, 2
0x10003973  xor     bl, bl
0x10003975  mov     [ebp+var_19], bl
0x10003978  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1000397f  call    loc_100039C1
0x10003984  test    bl, bl
0x10003986  jnz     short loc_100039CB
0x10003988  call    ___scrt_get_dyn_tls_init_callback
0x1000398d  mov     esi, eax
0x1000398f  cmp     dword ptr [esi], 0
0x10003992  jz      short loc_100039B3
0x10003994  push    esi
0x10003995  call    ___scrt_is_nonwritable_in_current_image
0x1000399a  pop     ecx
0x1000399b  test    al, al
0x1000399d  jz      short loc_100039B3
0x1000399f  push    [ebp+arg_4]
0x100039a2  push    2
0x100039a4  push    [ebp+arg_0]
0x100039a7  mov     esi, [esi]
0x100039a9  mov     ecx, esi
0x100039ab  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100039b1  call    esi
0x100039b3  inc     dword_1000B0B0
0x100039b9  xor     eax, eax
0x100039bb  inc     eax
0x100039bc  jmp     short loc_100039CD
0x100039be  mov     bl, [ebp+var_19]
0x100039c1  push    [ebp+var_1D]
0x100039c4  call    ___scrt_release_startup_lock
0x100039c9  pop     ecx
0x100039ca  retn
0x100039cb  xor     eax, eax
0x100039cd  mov     ecx, [ebp+ms_exc.registration.Next]
0x100039d0  mov     large fs:0, ecx
0x100039d7  pop     ecx
0x100039d8  pop     edi
0x100039d9  pop     esi
0x100039da  pop     ebx
0x100039db  leave
0x100039dc  retn
0x100039dd  push    7
0x100039df  call    ___scrt_fastfail
```
