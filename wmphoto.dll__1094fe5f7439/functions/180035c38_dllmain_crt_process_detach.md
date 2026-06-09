# dllmain_crt_process_detach

- ea: `0x180035c38`
- end: `0x180035cbb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180035ae0`

## callees

- `0x180035c38`
- `0x180035eb8`
- `0x180035fe0`
- `0x180036018`
- `0x1800361a8`
- `0x1800361d4`
- `0x18003663c`
- `0x180036684`
- `0x1800366d4`

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

  if ( dword_1800502D0 <= 0 )
    return 0;
  --dword_1800502D0;
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
0x180035c38  mov     [rsp+arg_0], rbx
0x180035c3d  push    rdi
0x180035c3e  sub     rsp, 30h
0x180035c42  mov     dil, cl
0x180035c45  mov     eax, cs:dword_1800502D0
0x180035c4b  test    eax, eax
0x180035c4d  jg      short loc_180035C5C
0x180035c4f  xor     eax, eax
0x180035c51  mov     rbx, [rsp+38h+arg_0]
0x180035c56  add     rsp, 30h
0x180035c5a  pop     rdi
0x180035c5b  retn
0x180035c5c  dec     eax
0x180035c5e  mov     cs:dword_1800502D0, eax
0x180035c64  call    __scrt_acquire_startup_lock
0x180035c69  mov     bl, al
0x180035c6b  mov     [rsp+38h+var_18], al
0x180035c6f  cmp     cs:__scrt_current_native_startup_state, 2
0x180035c76  jnz     short loc_180035CAE
0x180035c78  call    __scrt_dllmain_uninitialize_c
0x180035c7d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180035c82  call    _RTC_Terminate
0x180035c87  mov     cs:__scrt_current_native_startup_state, 0
0x180035c91  mov     cl, bl
0x180035c93  call    __scrt_release_startup_lock
0x180035c98  xor     edx, edx
0x180035c9a  mov     cl, dil
0x180035c9d  call    __scrt_uninitialize_crt
0x180035ca2  movzx   ebx, al
0x180035ca5  call    __scrt_dllmain_uninitialize_critical
0x180035caa  mov     eax, ebx
0x180035cac  jmp     short loc_180035C51
0x180035cae  mov     ecx, 7
0x180035cb3  call    __scrt_fastfail
0x18004389f  push    rbp
0x1800438a1  sub     rsp, 20h
0x1800438a5  mov     rbp, rdx
0x1800438a8  mov     cl, [rbp+20h]
0x1800438ab  call    __scrt_release_startup_lock
0x1800438b0  nop
0x1800438b1  add     rsp, 20h
0x1800438b5  pop     rbp
0x1800438b6  retn
0x1800438b8  push    rbp
0x1800438ba  sub     rsp, 20h
0x1800438be  mov     rbp, rdx
0x1800438c1  add     rsp, 20h
0x1800438c5  pop     rbp
0x1800438c6  jmp     __scrt_dllmain_uninitialize_critical
```
