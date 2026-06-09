# dllmain_crt_process_detach

- ea: `0x180001c18`
- end: `0x180001c9b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001ac0`

## callees

- `0x180001c18`
- `0x180001ef8`
- `0x180002020`
- `0x180002058`
- `0x1800021e8`
- `0x180002214`
- `0x1800023d8`
- `0x180002420`
- `0x180002470`

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

  if ( dword_180023510 <= 0 )
    return 0;
  --dword_180023510;
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
0x180001c18  mov     [rsp+arg_0], rbx
0x180001c1d  push    rdi
0x180001c1e  sub     rsp, 30h
0x180001c22  mov     dil, cl
0x180001c25  mov     eax, cs:dword_180023510
0x180001c2b  test    eax, eax
0x180001c2d  jg      short loc_180001C3C
0x180001c2f  xor     eax, eax
0x180001c31  mov     rbx, [rsp+38h+arg_0]
0x180001c36  add     rsp, 30h
0x180001c3a  pop     rdi
0x180001c3b  retn
0x180001c3c  dec     eax
0x180001c3e  mov     cs:dword_180023510, eax
0x180001c44  call    __scrt_acquire_startup_lock
0x180001c49  mov     bl, al
0x180001c4b  mov     [rsp+38h+var_18], al
0x180001c4f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001c56  jnz     short loc_180001C8E
0x180001c58  call    __scrt_dllmain_uninitialize_c
0x180001c5d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001c62  call    _RTC_Terminate
0x180001c67  mov     cs:__scrt_current_native_startup_state, 0
0x180001c71  mov     cl, bl
0x180001c73  call    __scrt_release_startup_lock
0x180001c78  xor     edx, edx
0x180001c7a  mov     cl, dil
0x180001c7d  call    __scrt_uninitialize_crt
0x180001c82  movzx   ebx, al
0x180001c85  call    __scrt_dllmain_uninitialize_critical
0x180001c8a  mov     eax, ebx
0x180001c8c  jmp     short loc_180001C31
0x180001c8e  mov     ecx, 7
0x180001c93  call    __scrt_fastfail
0x180019959  push    rbp
0x18001995b  sub     rsp, 20h
0x18001995f  mov     rbp, rdx
0x180019962  mov     cl, [rbp+20h]
0x180019965  call    __scrt_release_startup_lock
0x18001996a  nop
0x18001996b  add     rsp, 20h
0x18001996f  pop     rbp
0x180019970  retn
0x180019972  push    rbp
0x180019974  sub     rsp, 20h
0x180019978  mov     rbp, rdx
0x18001997b  add     rsp, 20h
0x18001997f  pop     rbp
0x180019980  jmp     __scrt_dllmain_uninitialize_critical
```
