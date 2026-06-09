# dllmain_crt_process_detach

- ea: `0x1800030c8`
- end: `0x18000314b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002f70`

## callees

- `0x1800030c8`
- `0x18000333c`
- `0x180003464`
- `0x18000349c`
- `0x18000362c`
- `0x180003658`
- `0x18000382c`
- `0x180003874`
- `0x1800038c4`

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

  if ( dword_180034790 <= 0 )
    return 0;
  --dword_180034790;
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
0x1800030c8  mov     [rsp+arg_0], rbx
0x1800030cd  push    rdi
0x1800030ce  sub     rsp, 30h
0x1800030d2  mov     dil, cl
0x1800030d5  mov     eax, cs:dword_180034790
0x1800030db  test    eax, eax
0x1800030dd  jg      short loc_1800030EC
0x1800030df  xor     eax, eax
0x1800030e1  mov     rbx, [rsp+38h+arg_0]
0x1800030e6  add     rsp, 30h
0x1800030ea  pop     rdi
0x1800030eb  retn
0x1800030ec  dec     eax
0x1800030ee  mov     cs:dword_180034790, eax
0x1800030f4  call    __scrt_acquire_startup_lock
0x1800030f9  mov     bl, al
0x1800030fb  mov     [rsp+38h+var_18], al
0x1800030ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180003106  jnz     short loc_18000313E
0x180003108  call    __scrt_dllmain_uninitialize_c
0x18000310d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180003112  call    _RTC_Terminate
0x180003117  mov     cs:__scrt_current_native_startup_state, 0
0x180003121  mov     cl, bl
0x180003123  call    __scrt_release_startup_lock
0x180003128  xor     edx, edx
0x18000312a  mov     cl, dil
0x18000312d  call    __scrt_uninitialize_crt
0x180003132  movzx   ebx, al
0x180003135  call    __scrt_dllmain_uninitialize_critical
0x18000313a  mov     eax, ebx
0x18000313c  jmp     short loc_1800030E1
0x18000313e  mov     ecx, 7
0x180003143  call    __scrt_fastfail
0x1800266b9  push    rbp
0x1800266bb  sub     rsp, 20h
0x1800266bf  mov     rbp, rdx
0x1800266c2  mov     cl, [rbp+20h]
0x1800266c5  call    __scrt_release_startup_lock
0x1800266ca  nop
0x1800266cb  add     rsp, 20h
0x1800266cf  pop     rbp
0x1800266d0  retn
0x1800266d2  push    rbp
0x1800266d4  sub     rsp, 20h
0x1800266d8  mov     rbp, rdx
0x1800266db  add     rsp, 20h
0x1800266df  pop     rbp
0x1800266e0  jmp     __scrt_dllmain_uninitialize_critical
```
