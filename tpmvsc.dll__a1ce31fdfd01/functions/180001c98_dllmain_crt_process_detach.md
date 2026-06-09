# dllmain_crt_process_detach

- ea: `0x180001c98`
- end: `0x180001d1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001b40`

## callees

- `0x180001c98`
- `0x180001fb4`
- `0x1800020dc`
- `0x180002114`
- `0x1800022a4`
- `0x1800022d0`
- `0x180002548`
- `0x180002590`
- `0x1800025e0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800485D0 <= 0 )
    return 0;
  --dword_1800485D0;
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
0x180001c98  mov     [rsp+arg_0], rbx
0x180001c9d  push    rdi
0x180001c9e  sub     rsp, 30h
0x180001ca2  mov     dil, cl
0x180001ca5  mov     eax, cs:dword_1800485D0
0x180001cab  test    eax, eax
0x180001cad  jg      short loc_180001CBC
0x180001caf  xor     eax, eax
0x180001cb1  mov     rbx, [rsp+38h+arg_0]
0x180001cb6  add     rsp, 30h
0x180001cba  pop     rdi
0x180001cbb  retn
0x180001cbc  dec     eax
0x180001cbe  mov     cs:dword_1800485D0, eax
0x180001cc4  call    __scrt_acquire_startup_lock
0x180001cc9  mov     bl, al
0x180001ccb  mov     [rsp+38h+var_18], al
0x180001ccf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001cd6  jnz     short loc_180001D0E
0x180001cd8  call    __scrt_dllmain_uninitialize_c
0x180001cdd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001ce2  call    _RTC_Terminate
0x180001ce7  mov     cs:__scrt_current_native_startup_state, 0
0x180001cf1  mov     cl, bl
0x180001cf3  call    __scrt_release_startup_lock
0x180001cf8  xor     edx, edx
0x180001cfa  mov     cl, dil
0x180001cfd  call    __scrt_uninitialize_crt
0x180001d02  movzx   ebx, al
0x180001d05  call    __scrt_dllmain_uninitialize_critical
0x180001d0a  mov     eax, ebx
0x180001d0c  jmp     short loc_180001CB1
0x180001d0e  mov     ecx, 7
0x180001d13  call    __scrt_fastfail
0x180034bb9  push    rbp
0x180034bbb  sub     rsp, 20h
0x180034bbf  mov     rbp, rdx
0x180034bc2  mov     cl, [rbp+20h]
0x180034bc5  call    __scrt_release_startup_lock
0x180034bca  nop
0x180034bcb  add     rsp, 20h
0x180034bcf  pop     rbp
0x180034bd0  retn
0x180034bd2  push    rbp
0x180034bd4  sub     rsp, 20h
0x180034bd8  mov     rbp, rdx
0x180034bdb  add     rsp, 20h
0x180034bdf  pop     rbp
0x180034be0  jmp     __scrt_dllmain_uninitialize_critical
```
