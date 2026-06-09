# dllmain_crt_process_detach

- ea: `0x18000c778`
- end: `0x18000c7fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000c620`

## callees

- `0x18000c778`
- `0x18000caa0`
- `0x18000cbc8`
- `0x18000cc00`
- `0x18000cd90`
- `0x18000cdbc`
- `0x18000cfd0`
- `0x18000d018`
- `0x18000d068`

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

  if ( dword_180025A70 <= 0 )
    return 0;
  --dword_180025A70;
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
0x18000c778  mov     [rsp+arg_0], rbx
0x18000c77d  push    rdi
0x18000c77e  sub     rsp, 30h
0x18000c782  mov     dil, cl
0x18000c785  mov     eax, cs:dword_180025A70
0x18000c78b  test    eax, eax
0x18000c78d  jg      short loc_18000C79C
0x18000c78f  xor     eax, eax
0x18000c791  mov     rbx, [rsp+38h+arg_0]
0x18000c796  add     rsp, 30h
0x18000c79a  pop     rdi
0x18000c79b  retn
0x18000c79c  dec     eax
0x18000c79e  mov     cs:dword_180025A70, eax
0x18000c7a4  call    __scrt_acquire_startup_lock
0x18000c7a9  mov     bl, al
0x18000c7ab  mov     [rsp+38h+var_18], al
0x18000c7af  cmp     cs:__scrt_current_native_startup_state, 2
0x18000c7b6  jnz     short loc_18000C7EE
0x18000c7b8  call    __scrt_dllmain_uninitialize_c
0x18000c7bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000c7c2  call    _RTC_Terminate
0x18000c7c7  mov     cs:__scrt_current_native_startup_state, 0
0x18000c7d1  mov     cl, bl
0x18000c7d3  call    __scrt_release_startup_lock
0x18000c7d8  xor     edx, edx
0x18000c7da  mov     cl, dil
0x18000c7dd  call    __scrt_uninitialize_crt
0x18000c7e2  movzx   ebx, al
0x18000c7e5  call    __scrt_dllmain_uninitialize_critical
0x18000c7ea  mov     eax, ebx
0x18000c7ec  jmp     short loc_18000C791
0x18000c7ee  mov     ecx, 7
0x18000c7f3  call    __scrt_fastfail
0x18001aa8e  push    rbp
0x18001aa90  sub     rsp, 20h
0x18001aa94  mov     rbp, rdx
0x18001aa97  mov     cl, [rbp+20h]
0x18001aa9a  call    __scrt_release_startup_lock
0x18001aa9f  nop
0x18001aaa0  add     rsp, 20h
0x18001aaa4  pop     rbp
0x18001aaa5  retn
0x18001aaa7  push    rbp
0x18001aaa9  sub     rsp, 20h
0x18001aaad  mov     rbp, rdx
0x18001aab0  add     rsp, 20h
0x18001aab4  pop     rbp
0x18001aab5  jmp     __scrt_dllmain_uninitialize_critical
```
