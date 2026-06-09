# dllmain_crt_process_detach

- ea: `0x1800205a8`
- end: `0x18002062b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180020450`

## callees

- `0x1800205a8`
- `0x180020d8c`
- `0x180020dc4`
- `0x180020eec`
- `0x180020f24`
- `0x1800210b4`
- `0x1800210e0`
- `0x180021180`
- `0x1800211d0`

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

  if ( dword_18006AB10 <= 0 )
    return 0;
  --dword_18006AB10;
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
0x1800205a8  mov     [rsp+arg_0], rbx
0x1800205ad  push    rdi
0x1800205ae  sub     rsp, 30h
0x1800205b2  mov     dil, cl
0x1800205b5  mov     eax, cs:dword_18006AB10
0x1800205bb  test    eax, eax
0x1800205bd  jg      short loc_1800205CC
0x1800205bf  xor     eax, eax
0x1800205c1  mov     rbx, [rsp+38h+arg_0]
0x1800205c6  add     rsp, 30h
0x1800205ca  pop     rdi
0x1800205cb  retn
0x1800205cc  dec     eax
0x1800205ce  mov     cs:dword_18006AB10, eax
0x1800205d4  call    __scrt_acquire_startup_lock
0x1800205d9  mov     bl, al
0x1800205db  mov     [rsp+38h+var_18], al
0x1800205df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800205e6  jnz     short loc_18002061E
0x1800205e8  call    __scrt_dllmain_uninitialize_c
0x1800205ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800205f2  call    _RTC_Terminate
0x1800205f7  mov     cs:__scrt_current_native_startup_state, 0
0x180020601  mov     cl, bl
0x180020603  call    __scrt_release_startup_lock
0x180020608  xor     edx, edx
0x18002060a  mov     cl, dil
0x18002060d  call    __scrt_uninitialize_crt
0x180020612  movzx   ebx, al
0x180020615  call    __scrt_dllmain_uninitialize_critical
0x18002061a  mov     eax, ebx
0x18002061c  jmp     short loc_1800205C1
0x18002061e  mov     ecx, 7
0x180020623  call    __scrt_fastfail
0x18004a878  push    rbp
0x18004a87a  sub     rsp, 20h
0x18004a87e  mov     rbp, rdx
0x18004a881  mov     cl, [rbp+20h]
0x18004a884  call    __scrt_release_startup_lock
0x18004a889  nop
0x18004a88a  add     rsp, 20h
0x18004a88e  pop     rbp
0x18004a88f  retn
0x18004a891  push    rbp
0x18004a893  sub     rsp, 20h
0x18004a897  mov     rbp, rdx
0x18004a89a  add     rsp, 20h
0x18004a89e  pop     rbp
0x18004a89f  jmp     __scrt_dllmain_uninitialize_critical
```
