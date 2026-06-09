# dllmain_crt_process_detach

- ea: `0x180001458`
- end: `0x1800014db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001300`

## callees

- `0x180001458`
- `0x18000175c`
- `0x180001884`
- `0x1800018bc`
- `0x180001a4c`
- `0x180001a78`
- `0x180001b1c`
- `0x180001b64`
- `0x180001bb4`

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

  if ( dword_180012350 <= 0 )
    return 0;
  --dword_180012350;
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
0x180001458  mov     [rsp+arg_0], rbx
0x18000145d  push    rdi
0x18000145e  sub     rsp, 30h
0x180001462  mov     dil, cl
0x180001465  mov     eax, cs:dword_180012350
0x18000146b  test    eax, eax
0x18000146d  jg      short loc_18000147C
0x18000146f  xor     eax, eax
0x180001471  mov     rbx, [rsp+38h+arg_0]
0x180001476  add     rsp, 30h
0x18000147a  pop     rdi
0x18000147b  retn
0x18000147c  dec     eax
0x18000147e  mov     cs:dword_180012350, eax
0x180001484  call    __scrt_acquire_startup_lock
0x180001489  mov     bl, al
0x18000148b  mov     [rsp+38h+var_18], al
0x18000148f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001496  jnz     short loc_1800014CE
0x180001498  call    __scrt_dllmain_uninitialize_c
0x18000149d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800014a2  call    _RTC_Terminate
0x1800014a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800014b1  mov     cl, bl
0x1800014b3  call    __scrt_release_startup_lock
0x1800014b8  xor     edx, edx
0x1800014ba  mov     cl, dil
0x1800014bd  call    __scrt_uninitialize_crt
0x1800014c2  movzx   ebx, al
0x1800014c5  call    __scrt_dllmain_uninitialize_critical
0x1800014ca  mov     eax, ebx
0x1800014cc  jmp     short loc_180001471
0x1800014ce  mov     ecx, 7
0x1800014d3  call    __scrt_fastfail
0x18000dca9  push    rbp
0x18000dcab  sub     rsp, 20h
0x18000dcaf  mov     rbp, rdx
0x18000dcb2  mov     cl, [rbp+20h]
0x18000dcb5  call    __scrt_release_startup_lock
0x18000dcba  nop
0x18000dcbb  add     rsp, 20h
0x18000dcbf  pop     rbp
0x18000dcc0  retn
0x18000dcc2  push    rbp
0x18000dcc4  sub     rsp, 20h
0x18000dcc8  mov     rbp, rdx
0x18000dccb  add     rsp, 20h
0x18000dccf  pop     rbp
0x18000dcd0  jmp     __scrt_dllmain_uninitialize_critical
```
