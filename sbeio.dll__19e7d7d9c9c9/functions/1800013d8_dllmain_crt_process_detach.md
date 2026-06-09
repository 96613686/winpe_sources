# dllmain_crt_process_detach

- ea: `0x1800013d8`
- end: `0x18000145b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x1800013d8`
- `0x1800016e4`
- `0x18000171c`
- `0x180001844`
- `0x18000187c`
- `0x180001a0c`
- `0x180001a38`
- `0x180001ad8`
- `0x180001b28`

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

  if ( dword_180032290 <= 0 )
    return 0;
  --dword_180032290;
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
0x1800013d8  mov     [rsp+arg_0], rbx
0x1800013dd  push    rdi
0x1800013de  sub     rsp, 30h
0x1800013e2  mov     dil, cl
0x1800013e5  mov     eax, cs:dword_180032290
0x1800013eb  test    eax, eax
0x1800013ed  jg      short loc_1800013FC
0x1800013ef  xor     eax, eax
0x1800013f1  mov     rbx, [rsp+38h+arg_0]
0x1800013f6  add     rsp, 30h
0x1800013fa  pop     rdi
0x1800013fb  retn
0x1800013fc  dec     eax
0x1800013fe  mov     cs:dword_180032290, eax
0x180001404  call    __scrt_acquire_startup_lock
0x180001409  mov     bl, al
0x18000140b  mov     [rsp+38h+var_18], al
0x18000140f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001416  jnz     short loc_18000144E
0x180001418  call    __scrt_dllmain_uninitialize_c
0x18000141d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001422  call    _RTC_Terminate
0x180001427  mov     cs:__scrt_current_native_startup_state, 0
0x180001431  mov     cl, bl
0x180001433  call    __scrt_release_startup_lock
0x180001438  xor     edx, edx
0x18000143a  mov     cl, dil
0x18000143d  call    __scrt_uninitialize_crt
0x180001442  movzx   ebx, al
0x180001445  call    __scrt_dllmain_uninitialize_critical
0x18000144a  mov     eax, ebx
0x18000144c  jmp     short loc_1800013F1
0x18000144e  mov     ecx, 7
0x180001453  call    __scrt_fastfail
0x18002a119  push    rbp
0x18002a11b  sub     rsp, 20h
0x18002a11f  mov     rbp, rdx
0x18002a122  mov     cl, [rbp+20h]
0x18002a125  call    __scrt_release_startup_lock
0x18002a12a  nop
0x18002a12b  add     rsp, 20h
0x18002a12f  pop     rbp
0x18002a130  retn
0x18002a132  push    rbp
0x18002a134  sub     rsp, 20h
0x18002a138  mov     rbp, rdx
0x18002a13b  add     rsp, 20h
0x18002a13f  pop     rbp
0x18002a140  jmp     __scrt_dllmain_uninitialize_critical
```
