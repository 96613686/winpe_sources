# dllmain_crt_process_detach

- ea: `0x1800021e8`
- end: `0x18000226b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002090`

## callees

- `0x1800021e8`
- `0x180002580`
- `0x1800025b8`
- `0x1800026e0`
- `0x180002718`
- `0x1800028a8`
- `0x1800028d4`
- `0x180002974`
- `0x1800029c4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001C3B0 <= 0 )
    return 0;
  --dword_18001C3B0;
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
0x1800021e8  mov     [rsp+arg_0], rbx
0x1800021ed  push    rdi
0x1800021ee  sub     rsp, 30h
0x1800021f2  mov     dil, cl
0x1800021f5  mov     eax, cs:dword_18001C3B0
0x1800021fb  test    eax, eax
0x1800021fd  jg      short loc_18000220C
0x1800021ff  xor     eax, eax
0x180002201  mov     rbx, [rsp+38h+arg_0]
0x180002206  add     rsp, 30h
0x18000220a  pop     rdi
0x18000220b  retn
0x18000220c  dec     eax
0x18000220e  mov     cs:dword_18001C3B0, eax
0x180002214  call    __scrt_acquire_startup_lock
0x180002219  mov     bl, al
0x18000221b  mov     [rsp+38h+var_18], al
0x18000221f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002226  jnz     short loc_18000225E
0x180002228  call    __scrt_dllmain_uninitialize_c
0x18000222d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002232  call    _RTC_Terminate
0x180002237  mov     cs:__scrt_current_native_startup_state, 0
0x180002241  mov     cl, bl
0x180002243  call    __scrt_release_startup_lock
0x180002248  xor     edx, edx
0x18000224a  mov     cl, dil
0x18000224d  call    __scrt_uninitialize_crt
0x180002252  movzx   ebx, al
0x180002255  call    __scrt_dllmain_uninitialize_critical
0x18000225a  mov     eax, ebx
0x18000225c  jmp     short loc_180002201
0x18000225e  mov     ecx, 7
0x180002263  call    __scrt_fastfail
0x18000ff49  push    rbp
0x18000ff4b  sub     rsp, 20h
0x18000ff4f  mov     rbp, rdx
0x18000ff52  mov     cl, [rbp+20h]
0x18000ff55  call    __scrt_release_startup_lock
0x18000ff5a  nop
0x18000ff5b  add     rsp, 20h
0x18000ff5f  pop     rbp
0x18000ff60  retn
0x18000ff62  push    rbp
0x18000ff64  sub     rsp, 20h
0x18000ff68  mov     rbp, rdx
0x18000ff6b  add     rsp, 20h
0x18000ff6f  pop     rbp
0x18000ff70  jmp     __scrt_dllmain_uninitialize_critical
```
