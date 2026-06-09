# dllmain_crt_process_detach

- ea: `0x18000e428`
- end: `0x18000e4ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000e2d0`

## callees

- `0x18000e428`
- `0x18000e69c`
- `0x18000e7c4`
- `0x18000e7fc`
- `0x18000e98c`
- `0x18000e9b8`
- `0x18000eb18`
- `0x18000eb60`
- `0x18000ebb0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  if ( dword_180029410 <= 0 )
    return 0;
  --dword_180029410;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0);
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x18000e428  mov     [rsp+arg_0], rbx
0x18000e42d  push    rdi
0x18000e42e  sub     rsp, 30h
0x18000e432  mov     dil, cl
0x18000e435  mov     eax, cs:dword_180029410
0x18000e43b  test    eax, eax
0x18000e43d  jg      short loc_18000E44C
0x18000e43f  xor     eax, eax
0x18000e441  mov     rbx, [rsp+38h+arg_0]
0x18000e446  add     rsp, 30h
0x18000e44a  pop     rdi
0x18000e44b  retn
0x18000e44c  dec     eax
0x18000e44e  mov     cs:dword_180029410, eax
0x18000e454  call    __scrt_acquire_startup_lock
0x18000e459  mov     bl, al
0x18000e45b  mov     [rsp+38h+var_18], al
0x18000e45f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000e466  jnz     short loc_18000E49E
0x18000e468  call    __scrt_dllmain_uninitialize_c
0x18000e46d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000e472  call    _RTC_Terminate
0x18000e477  mov     cs:__scrt_current_native_startup_state, 0
0x18000e481  mov     cl, bl
0x18000e483  call    __scrt_release_startup_lock
0x18000e488  xor     edx, edx
0x18000e48a  mov     cl, dil
0x18000e48d  call    __scrt_uninitialize_crt
0x18000e492  movzx   ebx, al
0x18000e495  call    __scrt_dllmain_uninitialize_critical
0x18000e49a  mov     eax, ebx
0x18000e49c  jmp     short loc_18000E441
0x18000e49e  mov     ecx, 7
0x18000e4a3  call    __scrt_fastfail
0x18001c9c3  push    rbp
0x18001c9c5  sub     rsp, 20h
0x18001c9c9  mov     rbp, rdx
0x18001c9cc  mov     cl, [rbp+20h]
0x18001c9cf  call    __scrt_release_startup_lock
0x18001c9d4  nop
0x18001c9d5  add     rsp, 20h
0x18001c9d9  pop     rbp
0x18001c9da  retn
0x18001c9dc  push    rbp
0x18001c9de  sub     rsp, 20h
0x18001c9e2  mov     rbp, rdx
0x18001c9e5  add     rsp, 20h
0x18001c9e9  pop     rbp
0x18001c9ea  jmp     __scrt_dllmain_uninitialize_critical
```
