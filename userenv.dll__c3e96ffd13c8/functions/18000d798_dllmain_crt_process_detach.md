# dllmain_crt_process_detach

- ea: `0x18000d798`
- end: `0x18000d81b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000d640`

## callees

- `0x18000d798`
- `0x18000da0c`
- `0x18000db34`
- `0x18000db6c`
- `0x18000dcfc`
- `0x18000dd28`
- `0x18000de88`
- `0x18000ded0`
- `0x18000df20`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180028310 <= 0 )
    return 0;
  --dword_180028310;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
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
0x18000d798  mov     [rsp+arg_0], rbx
0x18000d79d  push    rdi
0x18000d79e  sub     rsp, 30h
0x18000d7a2  mov     dil, cl
0x18000d7a5  mov     eax, cs:dword_180028310
0x18000d7ab  test    eax, eax
0x18000d7ad  jg      short loc_18000D7BC
0x18000d7af  xor     eax, eax
0x18000d7b1  mov     rbx, [rsp+38h+arg_0]
0x18000d7b6  add     rsp, 30h
0x18000d7ba  pop     rdi
0x18000d7bb  retn
0x18000d7bc  dec     eax
0x18000d7be  mov     cs:dword_180028310, eax
0x18000d7c4  call    __scrt_acquire_startup_lock
0x18000d7c9  mov     bl, al
0x18000d7cb  mov     [rsp+38h+var_18], al
0x18000d7cf  cmp     cs:__scrt_current_native_startup_state, 2
0x18000d7d6  jnz     short loc_18000D80E
0x18000d7d8  call    __scrt_dllmain_uninitialize_c
0x18000d7dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000d7e2  call    _RTC_Terminate
0x18000d7e7  mov     cs:__scrt_current_native_startup_state, 0
0x18000d7f1  mov     cl, bl
0x18000d7f3  call    __scrt_release_startup_lock
0x18000d7f8  xor     edx, edx
0x18000d7fa  mov     cl, dil
0x18000d7fd  call    __scrt_uninitialize_crt
0x18000d802  movzx   ebx, al
0x18000d805  call    __scrt_dllmain_uninitialize_critical
0x18000d80a  mov     eax, ebx
0x18000d80c  jmp     short loc_18000D7B1
0x18000d80e  mov     ecx, 7
0x18000d813  call    __scrt_fastfail
0x18001ae61  push    rbp
0x18001ae63  sub     rsp, 20h
0x18001ae67  mov     rbp, rdx
0x18001ae6a  mov     cl, [rbp+20h]
0x18001ae6d  call    __scrt_release_startup_lock
0x18001ae72  nop
0x18001ae73  add     rsp, 20h
0x18001ae77  pop     rbp
0x18001ae78  retn
0x18001ae7a  push    rbp
0x18001ae7c  sub     rsp, 20h
0x18001ae80  mov     rbp, rdx
0x18001ae83  add     rsp, 20h
0x18001ae87  pop     rbp
0x18001ae88  jmp     __scrt_dllmain_uninitialize_critical
```
