# dllmain_crt_process_detach

- ea: `0x180001390`
- end: `0x180001413`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180001390`
- `0x180001958`
- `0x180001aa4`
- `0x180001adc`
- `0x180001c6c`
- `0x180001c98`
- `0x180001dfc`
- `0x180001e58`
- `0x180002010`

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

  if ( dword_180012330 <= 0 )
    return 0;
  --dword_180012330;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180001413LL);
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
0x180001390  mov     [rsp+arg_0], rbx
0x180001395  push    rdi
0x180001396  sub     rsp, 30h
0x18000139a  mov     dil, cl
0x18000139d  mov     eax, cs:dword_180012330
0x1800013a3  test    eax, eax
0x1800013a5  jg      short loc_1800013B4
0x1800013a7  xor     eax, eax
0x1800013a9  mov     rbx, [rsp+38h+arg_0]
0x1800013ae  add     rsp, 30h
0x1800013b2  pop     rdi
0x1800013b3  retn
0x1800013b4  dec     eax
0x1800013b6  mov     cs:dword_180012330, eax
0x1800013bc  call    __scrt_acquire_startup_lock
0x1800013c1  mov     bl, al
0x1800013c3  mov     [rsp+38h+var_18], al
0x1800013c7  cmp     cs:__scrt_current_native_startup_state, 2
0x1800013ce  jnz     short loc_180001406
0x1800013d0  call    __scrt_dllmain_uninitialize_c
0x1800013d5  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800013da  call    _RTC_Terminate
0x1800013df  mov     cs:__scrt_current_native_startup_state, 0
0x1800013e9  mov     cl, bl
0x1800013eb  call    __scrt_release_startup_lock
0x1800013f0  xor     edx, edx
0x1800013f2  mov     cl, dil
0x1800013f5  call    __scrt_uninitialize_crt
0x1800013fa  movzx   ebx, al
0x1800013fd  call    __scrt_dllmain_uninitialize_critical
0x180001402  mov     eax, ebx
0x180001404  jmp     short loc_1800013A9
0x180001406  mov     ecx, 7
0x18000140b  call    __scrt_fastfail
0x180001410  nop
0x180001411  nop
0x180001412  int     3; Trap to Debugger
0x18000ccb9  push    rbp
0x18000ccbb  sub     rsp, 20h
0x18000ccbf  mov     rbp, rdx
0x18000ccc2  mov     cl, [rbp+20h]
0x18000ccc5  call    __scrt_release_startup_lock
0x18000ccca  nop
0x18000cccb  add     rsp, 20h
0x18000cccf  pop     rbp
0x18000ccd0  retn
0x18000ccd2  push    rbp
0x18000ccd4  sub     rsp, 20h
0x18000ccd8  mov     rbp, rdx
0x18000ccdb  add     rsp, 20h
0x18000ccdf  pop     rbp
0x18000cce0  jmp     __scrt_dllmain_uninitialize_critical
```
