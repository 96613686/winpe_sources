# dllmain_crt_process_detach

- ea: `0x1800342f8`
- end: `0x18003437b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800341a0`

## callees

- `0x1800342f8`
- `0x180034534`
- `0x18003465c`
- `0x180034694`
- `0x180034824`
- `0x180034850`
- `0x1800349bc`
- `0x180034a04`
- `0x180034a54`

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

  if ( dword_1800655B0 <= 0 )
    return 0;
  --dword_1800655B0;
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
0x1800342f8  mov     [rsp+arg_0], rbx
0x1800342fd  push    rdi
0x1800342fe  sub     rsp, 30h
0x180034302  mov     dil, cl
0x180034305  mov     eax, cs:dword_1800655B0
0x18003430b  test    eax, eax
0x18003430d  jg      short loc_18003431C
0x18003430f  xor     eax, eax
0x180034311  mov     rbx, [rsp+38h+arg_0]
0x180034316  add     rsp, 30h
0x18003431a  pop     rdi
0x18003431b  retn
0x18003431c  dec     eax
0x18003431e  mov     cs:dword_1800655B0, eax
0x180034324  call    __scrt_acquire_startup_lock
0x180034329  mov     bl, al
0x18003432b  mov     [rsp+38h+var_18], al
0x18003432f  cmp     cs:__scrt_current_native_startup_state, 2
0x180034336  jnz     short loc_18003436E
0x180034338  call    __scrt_dllmain_uninitialize_c
0x18003433d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180034342  call    _RTC_Terminate
0x180034347  mov     cs:__scrt_current_native_startup_state, 0
0x180034351  mov     cl, bl
0x180034353  call    __scrt_release_startup_lock
0x180034358  xor     edx, edx
0x18003435a  mov     cl, dil
0x18003435d  call    __scrt_uninitialize_crt
0x180034362  movzx   ebx, al
0x180034365  call    __scrt_dllmain_uninitialize_critical
0x18003436a  mov     eax, ebx
0x18003436c  jmp     short loc_180034311
0x18003436e  mov     ecx, 7
0x180034373  call    __scrt_fastfail
0x18004c8da  push    rbp
0x18004c8dc  sub     rsp, 20h
0x18004c8e0  mov     rbp, rdx
0x18004c8e3  mov     cl, [rbp+20h]
0x18004c8e6  call    __scrt_release_startup_lock
0x18004c8eb  nop
0x18004c8ec  add     rsp, 20h
0x18004c8f0  pop     rbp
0x18004c8f1  retn
0x18004c8f3  push    rbp
0x18004c8f5  sub     rsp, 20h
0x18004c8f9  mov     rbp, rdx
0x18004c8fc  add     rsp, 20h
0x18004c900  pop     rbp
0x18004c901  jmp     __scrt_dllmain_uninitialize_critical
```
