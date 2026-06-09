# dllmain_crt_process_detach

- ea: `0x180002768`
- end: `0x1800027eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002610`

## callees

- `0x180002768`
- `0x180002a74`
- `0x180002aac`
- `0x180002bd4`
- `0x180002c0c`
- `0x180002d9c`
- `0x180002dc8`
- `0x180002e08`
- `0x180002e58`

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

  if ( dword_180007090 <= 0 )
    return 0;
  --dword_180007090;
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
0x180002768  mov     [rsp+arg_0], rbx
0x18000276d  push    rdi
0x18000276e  sub     rsp, 30h
0x180002772  mov     dil, cl
0x180002775  mov     eax, cs:dword_180007090
0x18000277b  test    eax, eax
0x18000277d  jg      short loc_18000278C
0x18000277f  xor     eax, eax
0x180002781  mov     rbx, [rsp+38h+arg_0]
0x180002786  add     rsp, 30h
0x18000278a  pop     rdi
0x18000278b  retn
0x18000278c  dec     eax
0x18000278e  mov     cs:dword_180007090, eax
0x180002794  call    __scrt_acquire_startup_lock
0x180002799  mov     bl, al
0x18000279b  mov     [rsp+38h+var_18], al
0x18000279f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800027a6  jnz     short loc_1800027DE
0x1800027a8  call    __scrt_dllmain_uninitialize_c
0x1800027ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800027b2  call    _RTC_Terminate
0x1800027b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800027c1  mov     cl, bl
0x1800027c3  call    __scrt_release_startup_lock
0x1800027c8  xor     edx, edx
0x1800027ca  mov     cl, dil
0x1800027cd  call    __scrt_uninitialize_crt
0x1800027d2  movzx   ebx, al
0x1800027d5  call    __scrt_dllmain_uninitialize_critical
0x1800027da  mov     eax, ebx
0x1800027dc  jmp     short loc_180002781
0x1800027de  mov     ecx, 7
0x1800027e3  call    __scrt_fastfail
0x180003469  push    rbp
0x18000346b  sub     rsp, 20h
0x18000346f  mov     rbp, rdx
0x180003472  mov     cl, [rbp+20h]
0x180003475  call    __scrt_release_startup_lock
0x18000347a  nop
0x18000347b  add     rsp, 20h
0x18000347f  pop     rbp
0x180003480  retn
0x180003482  push    rbp
0x180003484  sub     rsp, 20h
0x180003488  mov     rbp, rdx
0x18000348b  add     rsp, 20h
0x18000348f  pop     rbp
0x180003490  jmp     __scrt_dllmain_uninitialize_critical
```
