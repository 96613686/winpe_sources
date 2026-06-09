# dllmain_crt_process_detach

- ea: `0x1800102f0`
- end: `0x180010373`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180010180`

## callees

- `0x18000fd04`
- `0x18000fe50`
- `0x18000fe88`
- `0x180010018`
- `0x180010044`
- `0x1800102f0`
- `0x180010974`
- `0x180010bf0`
- `0x180010c8c`

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

  if ( dword_180021824 <= 0 )
    return 0;
  --dword_180021824;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180010373LL);
  }
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
0x1800102f0  mov     [rsp+arg_0], rbx
0x1800102f5  push    rdi
0x1800102f6  sub     rsp, 30h
0x1800102fa  mov     dil, cl
0x1800102fd  mov     eax, cs:dword_180021824
0x180010303  test    eax, eax
0x180010305  jg      short loc_180010314
0x180010307  xor     eax, eax
0x180010309  mov     rbx, [rsp+38h+arg_0]
0x18001030e  add     rsp, 30h
0x180010312  pop     rdi
0x180010313  retn
0x180010314  dec     eax
0x180010316  mov     cs:dword_180021824, eax
0x18001031c  call    __scrt_acquire_startup_lock
0x180010321  mov     bl, al
0x180010323  mov     [rsp+38h+var_18], al
0x180010327  cmp     cs:__scrt_current_native_startup_state, 2
0x18001032e  jnz     short loc_180010366
0x180010330  call    __scrt_dllmain_uninitialize_c
0x180010335  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18001033a  call    _RTC_Terminate
0x18001033f  mov     cs:__scrt_current_native_startup_state, 0
0x180010349  mov     cl, bl
0x18001034b  call    __scrt_release_startup_lock
0x180010350  xor     edx, edx
0x180010352  mov     cl, dil
0x180010355  call    __scrt_uninitialize_crt
0x18001035a  movzx   ebx, al
0x18001035d  call    __scrt_dllmain_uninitialize_critical
0x180010362  mov     eax, ebx
0x180010364  jmp     short loc_180010309
0x180010366  mov     ecx, 7
0x18001036b  call    __scrt_fastfail
0x180010370  nop
0x180010371  nop
0x180010372  int     3; Trap to Debugger
0x180016c6c  push    rbp
0x180016c6e  sub     rsp, 20h
0x180016c72  mov     rbp, rdx
0x180016c75  mov     cl, [rbp+20h]
0x180016c78  call    __scrt_release_startup_lock
0x180016c7d  nop
0x180016c7e  add     rsp, 20h
0x180016c82  pop     rbp
0x180016c83  retn
0x180016c85  push    rbp
0x180016c87  sub     rsp, 20h
0x180016c8b  mov     rbp, rdx
0x180016c8e  add     rsp, 20h
0x180016c92  pop     rbp
0x180016c93  jmp     __scrt_dllmain_uninitialize_critical
```
