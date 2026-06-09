# dllmain_crt_process_detach

- ea: `0x1800012c8`
- end: `0x18000134b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001170`

## callees

- `0x1800012c8`
- `0x1800015f0`
- `0x180001628`
- `0x180001750`
- `0x180001788`
- `0x180001918`
- `0x180001944`
- `0x1800019e4`
- `0x180001a34`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800C7230 <= 0 )
    return 0;
  --dword_1800C7230;
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
0x1800012c8  mov     [rsp+arg_0], rbx
0x1800012cd  push    rdi
0x1800012ce  sub     rsp, 30h
0x1800012d2  mov     dil, cl
0x1800012d5  mov     eax, cs:dword_1800C7230
0x1800012db  test    eax, eax
0x1800012dd  jg      short loc_1800012EC
0x1800012df  xor     eax, eax
0x1800012e1  mov     rbx, [rsp+38h+arg_0]
0x1800012e6  add     rsp, 30h
0x1800012ea  pop     rdi
0x1800012eb  retn
0x1800012ec  dec     eax
0x1800012ee  mov     cs:dword_1800C7230, eax
0x1800012f4  call    __scrt_acquire_startup_lock
0x1800012f9  mov     bl, al
0x1800012fb  mov     [rsp+38h+var_18], al
0x1800012ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180001306  jnz     short loc_18000133E
0x180001308  call    __scrt_dllmain_uninitialize_c
0x18000130d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001312  call    _RTC_Terminate
0x180001317  mov     cs:__scrt_current_native_startup_state, 0
0x180001321  mov     cl, bl
0x180001323  call    __scrt_release_startup_lock
0x180001328  xor     edx, edx
0x18000132a  mov     cl, dil
0x18000132d  call    __scrt_uninitialize_crt
0x180001332  movzx   ebx, al
0x180001335  call    __scrt_dllmain_uninitialize_critical
0x18000133a  mov     eax, ebx
0x18000133c  jmp     short loc_1800012E1
0x18000133e  mov     ecx, 7
0x180001343  call    __scrt_fastfail
0x180029e39  push    rbp
0x180029e3b  sub     rsp, 20h
0x180029e3f  mov     rbp, rdx
0x180029e42  mov     cl, [rbp+20h]
0x180029e45  call    __scrt_release_startup_lock
0x180029e4a  nop
0x180029e4b  add     rsp, 20h
0x180029e4f  pop     rbp
0x180029e50  retn
0x180029e52  push    rbp
0x180029e54  sub     rsp, 20h
0x180029e58  mov     rbp, rdx
0x180029e5b  add     rsp, 20h
0x180029e5f  pop     rbp
0x180029e60  jmp     __scrt_dllmain_uninitialize_critical
```
