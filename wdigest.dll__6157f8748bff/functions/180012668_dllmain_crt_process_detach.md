# dllmain_crt_process_detach

- ea: `0x180012668`
- end: `0x1800126eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180012510`

## callees

- `0x180012668`
- `0x1800128a4`
- `0x1800129cc`
- `0x180012a04`
- `0x180012b94`
- `0x180012bc0`
- `0x180012da0`
- `0x180012de8`
- `0x180012e38`

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

  if ( dword_1800453B0 <= 0 )
    return 0;
  --dword_1800453B0;
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
0x180012668  mov     [rsp+arg_0], rbx
0x18001266d  push    rdi
0x18001266e  sub     rsp, 30h
0x180012672  mov     dil, cl
0x180012675  mov     eax, cs:dword_1800453B0
0x18001267b  test    eax, eax
0x18001267d  jg      short loc_18001268C
0x18001267f  xor     eax, eax
0x180012681  mov     rbx, [rsp+38h+arg_0]
0x180012686  add     rsp, 30h
0x18001268a  pop     rdi
0x18001268b  retn
0x18001268c  dec     eax
0x18001268e  mov     cs:dword_1800453B0, eax
0x180012694  call    __scrt_acquire_startup_lock
0x180012699  mov     bl, al
0x18001269b  mov     [rsp+38h+var_18], al
0x18001269f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800126a6  jnz     short loc_1800126DE
0x1800126a8  call    __scrt_dllmain_uninitialize_c
0x1800126ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800126b2  call    _RTC_Terminate
0x1800126b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800126c1  mov     cl, bl
0x1800126c3  call    __scrt_release_startup_lock
0x1800126c8  xor     edx, edx
0x1800126ca  mov     cl, dil
0x1800126cd  call    __scrt_uninitialize_crt
0x1800126d2  movzx   ebx, al
0x1800126d5  call    __scrt_dllmain_uninitialize_critical
0x1800126da  mov     eax, ebx
0x1800126dc  jmp     short loc_180012681
0x1800126de  mov     ecx, 7
0x1800126e3  call    __scrt_fastfail
0x18003787f  push    rbp
0x180037881  sub     rsp, 20h
0x180037885  mov     rbp, rdx
0x180037888  mov     cl, [rbp+20h]
0x18003788b  call    __scrt_release_startup_lock
0x180037890  nop
0x180037891  add     rsp, 20h
0x180037895  pop     rbp
0x180037896  retn
0x180037898  push    rbp
0x18003789a  sub     rsp, 20h
0x18003789e  mov     rbp, rdx
0x1800378a1  add     rsp, 20h
0x1800378a5  pop     rbp
0x1800378a6  jmp     __scrt_dllmain_uninitialize_critical
```
