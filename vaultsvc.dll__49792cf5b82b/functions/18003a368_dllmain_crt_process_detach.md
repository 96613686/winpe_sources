# dllmain_crt_process_detach

- ea: `0x18003a368`
- end: `0x18003a3eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18003a210`

## callees

- `0x18003a368`
- `0x18003a674`
- `0x18003a6ac`
- `0x18003a7d4`
- `0x18003a80c`
- `0x18003a99c`
- `0x18003a9c8`
- `0x18003aa68`
- `0x18003aab8`

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

  if ( dword_18005F4F0 <= 0 )
    return 0;
  --dword_18005F4F0;
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
0x18003a368  mov     [rsp+arg_0], rbx
0x18003a36d  push    rdi
0x18003a36e  sub     rsp, 30h
0x18003a372  mov     dil, cl
0x18003a375  mov     eax, cs:dword_18005F4F0
0x18003a37b  test    eax, eax
0x18003a37d  jg      short loc_18003A38C
0x18003a37f  xor     eax, eax
0x18003a381  mov     rbx, [rsp+38h+arg_0]
0x18003a386  add     rsp, 30h
0x18003a38a  pop     rdi
0x18003a38b  retn
0x18003a38c  dec     eax
0x18003a38e  mov     cs:dword_18005F4F0, eax
0x18003a394  call    __scrt_acquire_startup_lock
0x18003a399  mov     bl, al
0x18003a39b  mov     [rsp+38h+var_18], al
0x18003a39f  cmp     cs:__scrt_current_native_startup_state, 2
0x18003a3a6  jnz     short loc_18003A3DE
0x18003a3a8  call    __scrt_dllmain_uninitialize_c
0x18003a3ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18003a3b2  call    _RTC_Terminate
0x18003a3b7  mov     cs:__scrt_current_native_startup_state, 0
0x18003a3c1  mov     cl, bl
0x18003a3c3  call    __scrt_release_startup_lock
0x18003a3c8  xor     edx, edx
0x18003a3ca  mov     cl, dil
0x18003a3cd  call    __scrt_uninitialize_crt
0x18003a3d2  movzx   ebx, al
0x18003a3d5  call    __scrt_dllmain_uninitialize_critical
0x18003a3da  mov     eax, ebx
0x18003a3dc  jmp     short loc_18003A381
0x18003a3de  mov     ecx, 7
0x18003a3e3  call    __scrt_fastfail
0x18004c926  push    rbp
0x18004c928  sub     rsp, 20h
0x18004c92c  mov     rbp, rdx
0x18004c92f  mov     cl, [rbp+20h]
0x18004c932  call    __scrt_release_startup_lock
0x18004c937  nop
0x18004c938  add     rsp, 20h
0x18004c93c  pop     rbp
0x18004c93d  retn
0x18004c93f  push    rbp
0x18004c941  sub     rsp, 20h
0x18004c945  mov     rbp, rdx
0x18004c948  add     rsp, 20h
0x18004c94c  pop     rbp
0x18004c94d  jmp     __scrt_dllmain_uninitialize_critical
```
