# dllmain_crt_process_detach

- ea: `0x180001548`
- end: `0x1800015cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800013f0`

## callees

- `0x180001548`
- `0x1800017cc`
- `0x1800018f4`
- `0x18000192c`
- `0x180001abc`
- `0x180001ae8`
- `0x180001cd4`
- `0x180001d1c`
- `0x180001d6c`

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

  if ( dword_1800158D0 <= 0 )
    return 0;
  --dword_1800158D0;
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
0x180001548  mov     [rsp+arg_0], rbx
0x18000154d  push    rdi
0x18000154e  sub     rsp, 30h
0x180001552  mov     dil, cl
0x180001555  mov     eax, cs:dword_1800158D0
0x18000155b  test    eax, eax
0x18000155d  jg      short loc_18000156C
0x18000155f  xor     eax, eax
0x180001561  mov     rbx, [rsp+38h+arg_0]
0x180001566  add     rsp, 30h
0x18000156a  pop     rdi
0x18000156b  retn
0x18000156c  dec     eax
0x18000156e  mov     cs:dword_1800158D0, eax
0x180001574  call    __scrt_acquire_startup_lock
0x180001579  mov     bl, al
0x18000157b  mov     [rsp+38h+var_18], al
0x18000157f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001586  jnz     short loc_1800015BE
0x180001588  call    __scrt_dllmain_uninitialize_c
0x18000158d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001592  call    _RTC_Terminate
0x180001597  mov     cs:__scrt_current_native_startup_state, 0
0x1800015a1  mov     cl, bl
0x1800015a3  call    __scrt_release_startup_lock
0x1800015a8  xor     edx, edx
0x1800015aa  mov     cl, dil
0x1800015ad  call    __scrt_uninitialize_crt
0x1800015b2  movzx   ebx, al
0x1800015b5  call    __scrt_dllmain_uninitialize_critical
0x1800015ba  mov     eax, ebx
0x1800015bc  jmp     short loc_180001561
0x1800015be  mov     ecx, 7
0x1800015c3  call    __scrt_fastfail
0x18000d849  push    rbp
0x18000d84b  sub     rsp, 20h
0x18000d84f  mov     rbp, rdx
0x18000d852  mov     cl, [rbp+20h]
0x18000d855  call    __scrt_release_startup_lock
0x18000d85a  nop
0x18000d85b  add     rsp, 20h
0x18000d85f  pop     rbp
0x18000d860  retn
0x18000d862  push    rbp
0x18000d864  sub     rsp, 20h
0x18000d868  mov     rbp, rdx
0x18000d86b  add     rsp, 20h
0x18000d86f  pop     rbp
0x18000d870  jmp     __scrt_dllmain_uninitialize_critical
```
