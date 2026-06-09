# dllmain_crt_process_detach

- ea: `0x180004ed8`
- end: `0x180004f5b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004d80`

## callees

- `0x180004ed8`
- `0x18000524c`
- `0x180005374`
- `0x1800053ac`
- `0x18000553c`
- `0x180005568`
- `0x180005718`
- `0x180005760`
- `0x1800057b0`

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

  if ( dword_1800404D0 <= 0 )
    return 0;
  --dword_1800404D0;
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
0x180004ed8  mov     [rsp+arg_0], rbx
0x180004edd  push    rdi
0x180004ede  sub     rsp, 30h
0x180004ee2  mov     dil, cl
0x180004ee5  mov     eax, cs:dword_1800404D0
0x180004eeb  test    eax, eax
0x180004eed  jg      short loc_180004EFC
0x180004eef  xor     eax, eax
0x180004ef1  mov     rbx, [rsp+38h+arg_0]
0x180004ef6  add     rsp, 30h
0x180004efa  pop     rdi
0x180004efb  retn
0x180004efc  dec     eax
0x180004efe  mov     cs:dword_1800404D0, eax
0x180004f04  call    __scrt_acquire_startup_lock
0x180004f09  mov     bl, al
0x180004f0b  mov     [rsp+38h+var_18], al
0x180004f0f  cmp     cs:__scrt_current_native_startup_state, 2
0x180004f16  jnz     short loc_180004F4E
0x180004f18  call    __scrt_dllmain_uninitialize_c
0x180004f1d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180004f22  call    _RTC_Terminate
0x180004f27  mov     cs:__scrt_current_native_startup_state, 0
0x180004f31  mov     cl, bl
0x180004f33  call    __scrt_release_startup_lock
0x180004f38  xor     edx, edx
0x180004f3a  mov     cl, dil
0x180004f3d  call    __scrt_uninitialize_crt
0x180004f42  movzx   ebx, al
0x180004f45  call    __scrt_dllmain_uninitialize_critical
0x180004f4a  mov     eax, ebx
0x180004f4c  jmp     short loc_180004EF1
0x180004f4e  mov     ecx, 7
0x180004f53  call    __scrt_fastfail
0x18002b039  push    rbp
0x18002b03b  sub     rsp, 20h
0x18002b03f  mov     rbp, rdx
0x18002b042  mov     cl, [rbp+20h]
0x18002b045  call    __scrt_release_startup_lock
0x18002b04a  nop
0x18002b04b  add     rsp, 20h
0x18002b04f  pop     rbp
0x18002b050  retn
0x18002b052  push    rbp
0x18002b054  sub     rsp, 20h
0x18002b058  mov     rbp, rdx
0x18002b05b  add     rsp, 20h
0x18002b05f  pop     rbp
0x18002b060  jmp     __scrt_dllmain_uninitialize_critical
```
