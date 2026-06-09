# dllmain_crt_process_detach

- ea: `0x180001378`
- end: `0x1800013fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180001378`
- `0x1800015b4`
- `0x1800016dc`
- `0x180001714`
- `0x1800018a4`
- `0x1800018d0`
- `0x180001ad0`
- `0x180001b20`
- `0x180001b70`

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

  if ( dword_18001A2C8 <= 0 )
    return 0;
  --dword_18001A2C8;
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
0x180001378  mov     [rsp+arg_0], rbx
0x18000137d  push    rdi
0x18000137e  sub     rsp, 30h
0x180001382  mov     dil, cl
0x180001385  mov     eax, cs:dword_18001A2C8
0x18000138b  test    eax, eax
0x18000138d  jg      short loc_18000139C
0x18000138f  xor     eax, eax
0x180001391  mov     rbx, [rsp+38h+arg_0]
0x180001396  add     rsp, 30h
0x18000139a  pop     rdi
0x18000139b  retn
0x18000139c  dec     eax
0x18000139e  mov     cs:dword_18001A2C8, eax
0x1800013a4  call    __scrt_acquire_startup_lock
0x1800013a9  mov     bl, al
0x1800013ab  mov     [rsp+38h+var_18], al
0x1800013af  cmp     cs:__scrt_current_native_startup_state, 2
0x1800013b6  jnz     short loc_1800013EE
0x1800013b8  call    __scrt_dllmain_uninitialize_c
0x1800013bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800013c2  call    _RTC_Terminate
0x1800013c7  mov     cs:__scrt_current_native_startup_state, 0
0x1800013d1  mov     cl, bl
0x1800013d3  call    __scrt_release_startup_lock
0x1800013d8  xor     edx, edx
0x1800013da  mov     cl, dil
0x1800013dd  call    __scrt_uninitialize_crt
0x1800013e2  movzx   ebx, al
0x1800013e5  call    __scrt_dllmain_uninitialize_critical
0x1800013ea  mov     eax, ebx
0x1800013ec  jmp     short loc_180001391
0x1800013ee  mov     ecx, 7
0x1800013f3  call    __scrt_fastfail
0x18000c9fd  push    rbp
0x18000c9ff  sub     rsp, 20h
0x18000ca03  mov     rbp, rdx
0x18000ca06  mov     cl, [rbp+20h]
0x18000ca09  call    __scrt_release_startup_lock
0x18000ca0e  nop
0x18000ca0f  add     rsp, 20h
0x18000ca13  pop     rbp
0x18000ca14  retn
0x18000ca16  push    rbp
0x18000ca18  sub     rsp, 20h
0x18000ca1c  mov     rbp, rdx
0x18000ca1f  add     rsp, 20h
0x18000ca23  pop     rbp
0x18000ca24  jmp     __scrt_dllmain_uninitialize_critical
```
