# dllmain_crt_process_detach

- ea: `0x180036208`
- end: `0x18003628b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800360b0`

## callees

- `0x180036208`
- `0x180036488`
- `0x1800365b0`
- `0x1800365e8`
- `0x180036778`
- `0x1800367a4`
- `0x180036c00`
- `0x180036c48`
- `0x180036c98`

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

  if ( dword_1800512D0 <= 0 )
    return 0;
  --dword_1800512D0;
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
0x180036208  mov     [rsp+arg_0], rbx
0x18003620d  push    rdi
0x18003620e  sub     rsp, 30h
0x180036212  mov     dil, cl
0x180036215  mov     eax, cs:dword_1800512D0
0x18003621b  test    eax, eax
0x18003621d  jg      short loc_18003622C
0x18003621f  xor     eax, eax
0x180036221  mov     rbx, [rsp+38h+arg_0]
0x180036226  add     rsp, 30h
0x18003622a  pop     rdi
0x18003622b  retn
0x18003622c  dec     eax
0x18003622e  mov     cs:dword_1800512D0, eax
0x180036234  call    __scrt_acquire_startup_lock
0x180036239  mov     bl, al
0x18003623b  mov     [rsp+38h+var_18], al
0x18003623f  cmp     cs:__scrt_current_native_startup_state, 2
0x180036246  jnz     short loc_18003627E
0x180036248  call    __scrt_dllmain_uninitialize_c
0x18003624d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180036252  call    _RTC_Terminate
0x180036257  mov     cs:__scrt_current_native_startup_state, 0
0x180036261  mov     cl, bl
0x180036263  call    __scrt_release_startup_lock
0x180036268  xor     edx, edx
0x18003626a  mov     cl, dil
0x18003626d  call    __scrt_uninitialize_crt
0x180036272  movzx   ebx, al
0x180036275  call    __scrt_dllmain_uninitialize_critical
0x18003627a  mov     eax, ebx
0x18003627c  jmp     short loc_180036221
0x18003627e  mov     ecx, 7
0x180036283  call    __scrt_fastfail
0x1800440af  push    rbp
0x1800440b1  sub     rsp, 20h
0x1800440b5  mov     rbp, rdx
0x1800440b8  mov     cl, [rbp+20h]
0x1800440bb  call    __scrt_release_startup_lock
0x1800440c0  nop
0x1800440c1  add     rsp, 20h
0x1800440c5  pop     rbp
0x1800440c6  retn
0x1800440c8  push    rbp
0x1800440ca  sub     rsp, 20h
0x1800440ce  mov     rbp, rdx
0x1800440d1  add     rsp, 20h
0x1800440d5  pop     rbp
0x1800440d6  jmp     __scrt_dllmain_uninitialize_critical
```
