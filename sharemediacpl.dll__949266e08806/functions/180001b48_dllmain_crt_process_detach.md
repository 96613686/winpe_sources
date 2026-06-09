# dllmain_crt_process_detach

- ea: `0x180001b48`
- end: `0x180001bcb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800019f0`

## callees

- `0x180001b48`
- `0x180001db0`
- `0x180001ed8`
- `0x180001f10`
- `0x1800020a0`
- `0x1800020cc`
- `0x1800024c0`
- `0x180002508`
- `0x180002558`

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

  if ( dword_18002A490 <= 0 )
    return 0;
  --dword_18002A490;
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
0x180001b48  mov     [rsp+arg_0], rbx
0x180001b4d  push    rdi
0x180001b4e  sub     rsp, 30h
0x180001b52  mov     dil, cl
0x180001b55  mov     eax, cs:dword_18002A490
0x180001b5b  test    eax, eax
0x180001b5d  jg      short loc_180001B6C
0x180001b5f  xor     eax, eax
0x180001b61  mov     rbx, [rsp+38h+arg_0]
0x180001b66  add     rsp, 30h
0x180001b6a  pop     rdi
0x180001b6b  retn
0x180001b6c  dec     eax
0x180001b6e  mov     cs:dword_18002A490, eax
0x180001b74  call    __scrt_acquire_startup_lock
0x180001b79  mov     bl, al
0x180001b7b  mov     [rsp+38h+var_18], al
0x180001b7f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001b86  jnz     short loc_180001BBE
0x180001b88  call    __scrt_dllmain_uninitialize_c
0x180001b8d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001b92  call    _RTC_Terminate
0x180001b97  mov     cs:__scrt_current_native_startup_state, 0
0x180001ba1  mov     cl, bl
0x180001ba3  call    __scrt_release_startup_lock
0x180001ba8  xor     edx, edx
0x180001baa  mov     cl, dil
0x180001bad  call    __scrt_uninitialize_crt
0x180001bb2  movzx   ebx, al
0x180001bb5  call    __scrt_dllmain_uninitialize_critical
0x180001bba  mov     eax, ebx
0x180001bbc  jmp     short loc_180001B61
0x180001bbe  mov     ecx, 7
0x180001bc3  call    __scrt_fastfail
0x18001d379  push    rbp
0x18001d37b  sub     rsp, 20h
0x18001d37f  mov     rbp, rdx
0x18001d382  mov     cl, [rbp+20h]
0x18001d385  call    __scrt_release_startup_lock
0x18001d38a  nop
0x18001d38b  add     rsp, 20h
0x18001d38f  pop     rbp
0x18001d390  retn
0x18001d392  push    rbp
0x18001d394  sub     rsp, 20h
0x18001d398  mov     rbp, rdx
0x18001d39b  add     rsp, 20h
0x18001d39f  pop     rbp
0x18001d3a0  jmp     __scrt_dllmain_uninitialize_critical
```
