# dllmain_crt_process_detach

- ea: `0x18000fe58`
- end: `0x18000fedb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000fd00`

## callees

- `0x18000fe58`
- `0x1800101bc`
- `0x1800101f4`
- `0x18001031c`
- `0x180010354`
- `0x1800104e4`
- `0x180010510`
- `0x180010550`
- `0x1800105a0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180024470 <= 0 )
    return 0;
  --dword_180024470;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x18000fe58  mov     [rsp+arg_0], rbx
0x18000fe5d  push    rdi
0x18000fe5e  sub     rsp, 30h
0x18000fe62  mov     dil, cl
0x18000fe65  mov     eax, cs:dword_180024470
0x18000fe6b  test    eax, eax
0x18000fe6d  jg      short loc_18000FE7C
0x18000fe6f  xor     eax, eax
0x18000fe71  mov     rbx, [rsp+38h+arg_0]
0x18000fe76  add     rsp, 30h
0x18000fe7a  pop     rdi
0x18000fe7b  retn
0x18000fe7c  dec     eax
0x18000fe7e  mov     cs:dword_180024470, eax
0x18000fe84  call    __scrt_acquire_startup_lock
0x18000fe89  mov     bl, al
0x18000fe8b  mov     [rsp+38h+var_18], al
0x18000fe8f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000fe96  jnz     short loc_18000FECE
0x18000fe98  call    __scrt_dllmain_uninitialize_c
0x18000fe9d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000fea2  call    _RTC_Terminate
0x18000fea7  mov     cs:__scrt_current_native_startup_state, 0
0x18000feb1  mov     cl, bl
0x18000feb3  call    __scrt_release_startup_lock
0x18000feb8  xor     edx, edx
0x18000feba  mov     cl, dil
0x18000febd  call    __scrt_uninitialize_crt
0x18000fec2  movzx   ebx, al
0x18000fec5  call    __scrt_dllmain_uninitialize_critical
0x18000feca  mov     eax, ebx
0x18000fecc  jmp     short loc_18000FE71
0x18000fece  mov     ecx, 7
0x18000fed3  call    __scrt_fastfail
0x180018959  push    rbp
0x18001895b  sub     rsp, 20h
0x18001895f  mov     rbp, rdx
0x180018962  mov     cl, [rbp+20h]
0x180018965  call    __scrt_release_startup_lock
0x18001896a  nop
0x18001896b  add     rsp, 20h
0x18001896f  pop     rbp
0x180018970  retn
0x180018972  push    rbp
0x180018974  sub     rsp, 20h
0x180018978  mov     rbp, rdx
0x18001897b  add     rsp, 20h
0x18001897f  pop     rbp
0x180018980  jmp     __scrt_dllmain_uninitialize_critical
```
