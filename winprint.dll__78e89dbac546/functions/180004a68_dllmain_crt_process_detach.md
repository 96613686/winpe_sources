# dllmain_crt_process_detach

- ea: `0x180004a68`
- end: `0x180004aeb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004910`

## callees

- `0x180004a68`
- `0x180004d74`
- `0x180004dac`
- `0x180004ed4`
- `0x180004f0c`
- `0x18000509c`
- `0x1800050c8`
- `0x180005108`
- `0x180005158`

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

  if ( dword_18000D450 <= 0 )
    return 0;
  --dword_18000D450;
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
0x180004a68  mov     [rsp+arg_0], rbx
0x180004a6d  push    rdi
0x180004a6e  sub     rsp, 30h
0x180004a72  mov     dil, cl
0x180004a75  mov     eax, cs:dword_18000D450
0x180004a7b  test    eax, eax
0x180004a7d  jg      short loc_180004A8C
0x180004a7f  xor     eax, eax
0x180004a81  mov     rbx, [rsp+38h+arg_0]
0x180004a86  add     rsp, 30h
0x180004a8a  pop     rdi
0x180004a8b  retn
0x180004a8c  dec     eax
0x180004a8e  mov     cs:dword_18000D450, eax
0x180004a94  call    __scrt_acquire_startup_lock
0x180004a99  mov     bl, al
0x180004a9b  mov     [rsp+38h+var_18], al
0x180004a9f  cmp     cs:__scrt_current_native_startup_state, 2
0x180004aa6  jnz     short loc_180004ADE
0x180004aa8  call    __scrt_dllmain_uninitialize_c
0x180004aad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180004ab2  call    _RTC_Terminate
0x180004ab7  mov     cs:__scrt_current_native_startup_state, 0
0x180004ac1  mov     cl, bl
0x180004ac3  call    __scrt_release_startup_lock
0x180004ac8  xor     edx, edx
0x180004aca  mov     cl, dil
0x180004acd  call    __scrt_uninitialize_crt
0x180004ad2  movzx   ebx, al
0x180004ad5  call    __scrt_dllmain_uninitialize_critical
0x180004ada  mov     eax, ebx
0x180004adc  jmp     short loc_180004A81
0x180004ade  mov     ecx, 7
0x180004ae3  call    __scrt_fastfail
0x18000786f  push    rbp
0x180007871  sub     rsp, 20h
0x180007875  mov     rbp, rdx
0x180007878  mov     cl, [rbp+20h]
0x18000787b  call    __scrt_release_startup_lock
0x180007880  nop
0x180007881  add     rsp, 20h
0x180007885  pop     rbp
0x180007886  retn
0x180007888  push    rbp
0x18000788a  sub     rsp, 20h
0x18000788e  mov     rbp, rdx
0x180007891  add     rsp, 20h
0x180007895  pop     rbp
0x180007896  jmp     __scrt_dllmain_uninitialize_critical
```
