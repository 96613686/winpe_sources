# dllmain_crt_process_detach

- ea: `0x18000c028`
- end: `0x18000c0ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000bed0`

## callees

- `0x18000c028`
- `0x18000c340`
- `0x18000c378`
- `0x18000c4a0`
- `0x18000c4d8`
- `0x18000c668`
- `0x18000c694`
- `0x18000c734`
- `0x18000c784`

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

  if ( dword_1800203D0 <= 0 )
    return 0;
  --dword_1800203D0;
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
0x18000c028  mov     [rsp+arg_0], rbx
0x18000c02d  push    rdi
0x18000c02e  sub     rsp, 30h
0x18000c032  mov     dil, cl
0x18000c035  mov     eax, cs:dword_1800203D0
0x18000c03b  test    eax, eax
0x18000c03d  jg      short loc_18000C04C
0x18000c03f  xor     eax, eax
0x18000c041  mov     rbx, [rsp+38h+arg_0]
0x18000c046  add     rsp, 30h
0x18000c04a  pop     rdi
0x18000c04b  retn
0x18000c04c  dec     eax
0x18000c04e  mov     cs:dword_1800203D0, eax
0x18000c054  call    __scrt_acquire_startup_lock
0x18000c059  mov     bl, al
0x18000c05b  mov     [rsp+38h+var_18], al
0x18000c05f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000c066  jnz     short loc_18000C09E
0x18000c068  call    __scrt_dllmain_uninitialize_c
0x18000c06d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000c072  call    _RTC_Terminate
0x18000c077  mov     cs:__scrt_current_native_startup_state, 0
0x18000c081  mov     cl, bl
0x18000c083  call    __scrt_release_startup_lock
0x18000c088  xor     edx, edx
0x18000c08a  mov     cl, dil
0x18000c08d  call    __scrt_uninitialize_crt
0x18000c092  movzx   ebx, al
0x18000c095  call    __scrt_dllmain_uninitialize_critical
0x18000c09a  mov     eax, ebx
0x18000c09c  jmp     short loc_18000C041
0x18000c09e  mov     ecx, 7
0x18000c0a3  call    __scrt_fastfail
0x180016d89  push    rbp
0x180016d8b  sub     rsp, 20h
0x180016d8f  mov     rbp, rdx
0x180016d92  mov     cl, [rbp+20h]
0x180016d95  call    __scrt_release_startup_lock
0x180016d9a  nop
0x180016d9b  add     rsp, 20h
0x180016d9f  pop     rbp
0x180016da0  retn
0x180016da2  push    rbp
0x180016da4  sub     rsp, 20h
0x180016da8  mov     rbp, rdx
0x180016dab  add     rsp, 20h
0x180016daf  pop     rbp
0x180016db0  jmp     __scrt_dllmain_uninitialize_critical
```
