# dllmain_crt_process_detach

- ea: `0x180001258`
- end: `0x1800012db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001100`

## callees

- `0x180001258`
- `0x180001570`
- `0x1800015a8`
- `0x1800016d0`
- `0x180001708`
- `0x180001898`
- `0x1800018c4`
- `0x180001904`
- `0x180001954`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_18000A1B0 <= 0 )
    return 0;
  --dword_18000A1B0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180001258  mov     [rsp+arg_0], rbx
0x18000125d  push    rdi
0x18000125e  sub     rsp, 30h
0x180001262  mov     dil, cl
0x180001265  mov     eax, cs:dword_18000A1B0
0x18000126b  test    eax, eax
0x18000126d  jg      short loc_18000127C
0x18000126f  xor     eax, eax
0x180001271  mov     rbx, [rsp+38h+arg_0]
0x180001276  add     rsp, 30h
0x18000127a  pop     rdi
0x18000127b  retn
0x18000127c  dec     eax
0x18000127e  mov     cs:dword_18000A1B0, eax
0x180001284  call    __scrt_acquire_startup_lock
0x180001289  mov     bl, al
0x18000128b  mov     [rsp+38h+var_18], al
0x18000128f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001296  jnz     short loc_1800012CE
0x180001298  call    __scrt_dllmain_uninitialize_c
0x18000129d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800012a2  call    _RTC_Terminate
0x1800012a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800012b1  mov     cl, bl
0x1800012b3  call    __scrt_release_startup_lock
0x1800012b8  xor     edx, edx
0x1800012ba  mov     cl, dil
0x1800012bd  call    __scrt_uninitialize_crt
0x1800012c2  movzx   ebx, al
0x1800012c5  call    __scrt_dllmain_uninitialize_critical
0x1800012ca  mov     eax, ebx
0x1800012cc  jmp     short loc_180001271
0x1800012ce  mov     ecx, 7
0x1800012d3  call    __scrt_fastfail
0x180004fe9  push    rbp
0x180004feb  sub     rsp, 20h
0x180004fef  mov     rbp, rdx
0x180004ff2  mov     cl, [rbp+20h]
0x180004ff5  call    __scrt_release_startup_lock
0x180004ffa  nop
0x180004ffb  add     rsp, 20h
0x180004fff  pop     rbp
0x180005000  retn
0x180005002  push    rbp
0x180005004  sub     rsp, 20h
0x180005008  mov     rbp, rdx
0x18000500b  add     rsp, 20h
0x18000500f  pop     rbp
0x180005010  jmp     __scrt_dllmain_uninitialize_critical
```
