# dllmain_crt_process_detach

- ea: `0x180003998`
- end: `0x180003a1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003840`

## callees

- `0x180003998`
- `0x180003cd0`
- `0x180003d08`
- `0x180003e30`
- `0x180003e68`
- `0x180003ff8`
- `0x180004024`
- `0x180004064`
- `0x1800040b4`

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

  if ( dword_180010110 <= 0 )
    return 0;
  --dword_180010110;
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
0x180003998  mov     [rsp+arg_0], rbx
0x18000399d  push    rdi
0x18000399e  sub     rsp, 30h
0x1800039a2  mov     dil, cl
0x1800039a5  mov     eax, cs:dword_180010110
0x1800039ab  test    eax, eax
0x1800039ad  jg      short loc_1800039BC
0x1800039af  xor     eax, eax
0x1800039b1  mov     rbx, [rsp+38h+arg_0]
0x1800039b6  add     rsp, 30h
0x1800039ba  pop     rdi
0x1800039bb  retn
0x1800039bc  dec     eax
0x1800039be  mov     cs:dword_180010110, eax
0x1800039c4  call    __scrt_acquire_startup_lock
0x1800039c9  mov     bl, al
0x1800039cb  mov     [rsp+38h+var_18], al
0x1800039cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800039d6  jnz     short loc_180003A0E
0x1800039d8  call    __scrt_dllmain_uninitialize_c
0x1800039dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800039e2  call    _RTC_Terminate
0x1800039e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800039f1  mov     cl, bl
0x1800039f3  call    __scrt_release_startup_lock
0x1800039f8  xor     edx, edx
0x1800039fa  mov     cl, dil
0x1800039fd  call    __scrt_uninitialize_crt
0x180003a02  movzx   ebx, al
0x180003a05  call    __scrt_dllmain_uninitialize_critical
0x180003a0a  mov     eax, ebx
0x180003a0c  jmp     short loc_1800039B1
0x180003a0e  mov     ecx, 7
0x180003a13  call    __scrt_fastfail
0x18000a7f9  push    rbp
0x18000a7fb  sub     rsp, 20h
0x18000a7ff  mov     rbp, rdx
0x18000a802  mov     cl, [rbp+20h]
0x18000a805  call    __scrt_release_startup_lock
0x18000a80a  nop
0x18000a80b  add     rsp, 20h
0x18000a80f  pop     rbp
0x18000a810  retn
0x18000a812  push    rbp
0x18000a814  sub     rsp, 20h
0x18000a818  mov     rbp, rdx
0x18000a81b  add     rsp, 20h
0x18000a81f  pop     rbp
0x18000a820  jmp     __scrt_dllmain_uninitialize_critical
```
