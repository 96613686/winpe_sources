# dllmain_crt_process_detach

- ea: `0x1800022c8`
- end: `0x18000234b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002170`

## callees

- `0x1800022c8`
- `0x180002534`
- `0x18000265c`
- `0x180002694`
- `0x180002824`
- `0x180002850`
- `0x180002a0c`
- `0x180002a54`
- `0x180002aa4`

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

  if ( dword_18000C1F0 <= 0 )
    return 0;
  --dword_18000C1F0;
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
0x1800022c8  mov     [rsp+arg_0], rbx
0x1800022cd  push    rdi
0x1800022ce  sub     rsp, 30h
0x1800022d2  mov     dil, cl
0x1800022d5  mov     eax, cs:dword_18000C1F0
0x1800022db  test    eax, eax
0x1800022dd  jg      short loc_1800022EC
0x1800022df  xor     eax, eax
0x1800022e1  mov     rbx, [rsp+38h+arg_0]
0x1800022e6  add     rsp, 30h
0x1800022ea  pop     rdi
0x1800022eb  retn
0x1800022ec  dec     eax
0x1800022ee  mov     cs:dword_18000C1F0, eax
0x1800022f4  call    __scrt_acquire_startup_lock
0x1800022f9  mov     bl, al
0x1800022fb  mov     [rsp+38h+var_18], al
0x1800022ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180002306  jnz     short loc_18000233E
0x180002308  call    __scrt_dllmain_uninitialize_c
0x18000230d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002312  call    _RTC_Terminate
0x180002317  mov     cs:__scrt_current_native_startup_state, 0
0x180002321  mov     cl, bl
0x180002323  call    __scrt_release_startup_lock
0x180002328  xor     edx, edx
0x18000232a  mov     cl, dil
0x18000232d  call    __scrt_uninitialize_crt
0x180002332  movzx   ebx, al
0x180002335  call    __scrt_dllmain_uninitialize_critical
0x18000233a  mov     eax, ebx
0x18000233c  jmp     short loc_1800022E1
0x18000233e  mov     ecx, 7
0x180002343  call    __scrt_fastfail
0x180007a4d  push    rbp
0x180007a4f  sub     rsp, 20h
0x180007a53  mov     rbp, rdx
0x180007a56  mov     cl, [rbp+20h]
0x180007a59  call    __scrt_release_startup_lock
0x180007a5e  nop
0x180007a5f  add     rsp, 20h
0x180007a63  pop     rbp
0x180007a64  retn
0x180007a66  push    rbp
0x180007a68  sub     rsp, 20h
0x180007a6c  mov     rbp, rdx
0x180007a6f  add     rsp, 20h
0x180007a73  pop     rbp
0x180007a74  jmp     __scrt_dllmain_uninitialize_critical
```
