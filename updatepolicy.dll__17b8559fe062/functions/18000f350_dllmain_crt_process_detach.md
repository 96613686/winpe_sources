# dllmain_crt_process_detach

- ea: `0x18000f350`
- end: `0x18000f3d3`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000f1e0`

## callees

- `0x18000ede0`
- `0x18000ef2c`
- `0x18000ef64`
- `0x18000f0f4`
- `0x18000f120`
- `0x18000f350`
- `0x18000fa08`
- `0x18000fc5c`
- `0x18000fcf8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001F814 <= 0 )
    return 0;
  --dword_18001F814;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x18000F3D3LL);
  }
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
0x18000f350  mov     [rsp+arg_0], rbx
0x18000f355  push    rdi
0x18000f356  sub     rsp, 30h
0x18000f35a  mov     dil, cl
0x18000f35d  mov     eax, cs:dword_18001F814
0x18000f363  test    eax, eax
0x18000f365  jg      short loc_18000F374
0x18000f367  xor     eax, eax
0x18000f369  mov     rbx, [rsp+38h+arg_0]
0x18000f36e  add     rsp, 30h
0x18000f372  pop     rdi
0x18000f373  retn
0x18000f374  dec     eax
0x18000f376  mov     cs:dword_18001F814, eax
0x18000f37c  call    __scrt_acquire_startup_lock
0x18000f381  mov     bl, al
0x18000f383  mov     [rsp+38h+var_18], al
0x18000f387  cmp     cs:__scrt_current_native_startup_state, 2
0x18000f38e  jnz     short loc_18000F3C6
0x18000f390  call    __scrt_dllmain_uninitialize_c
0x18000f395  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000f39a  call    _RTC_Terminate
0x18000f39f  mov     cs:__scrt_current_native_startup_state, 0
0x18000f3a9  mov     cl, bl
0x18000f3ab  call    __scrt_release_startup_lock
0x18000f3b0  xor     edx, edx
0x18000f3b2  mov     cl, dil
0x18000f3b5  call    __scrt_uninitialize_crt
0x18000f3ba  movzx   ebx, al
0x18000f3bd  call    __scrt_dllmain_uninitialize_critical
0x18000f3c2  mov     eax, ebx
0x18000f3c4  jmp     short loc_18000F369
0x18000f3c6  mov     ecx, 7
0x18000f3cb  call    __scrt_fastfail
0x18000f3d0  nop
0x18000f3d1  nop
0x18000f3d2  int     3; Trap to Debugger
0x180016654  push    rbp
0x180016656  sub     rsp, 20h
0x18001665a  mov     rbp, rdx
0x18001665d  mov     cl, [rbp+20h]
0x180016660  call    __scrt_release_startup_lock
0x180016665  nop
0x180016666  add     rsp, 20h
0x18001666a  pop     rbp
0x18001666b  retn
0x18001666d  push    rbp
0x18001666f  sub     rsp, 20h
0x180016673  mov     rbp, rdx
0x180016676  add     rsp, 20h
0x18001667a  pop     rbp
0x18001667b  jmp     __scrt_dllmain_uninitialize_critical
```
