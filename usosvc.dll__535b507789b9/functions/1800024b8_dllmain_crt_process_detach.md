# dllmain_crt_process_detach

- ea: `0x1800024b8`
- end: `0x18000253b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002360`

## callees

- `0x1800024b8`
- `0x1800026f4`
- `0x18000281c`
- `0x180002854`
- `0x1800029e4`
- `0x180002a10`
- `0x180002c80`
- `0x180002cc8`
- `0x180002d18`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180015430 <= 0 )
    return 0;
  --dword_180015430;
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
0x1800024b8  mov     [rsp+arg_0], rbx
0x1800024bd  push    rdi
0x1800024be  sub     rsp, 30h
0x1800024c2  mov     dil, cl
0x1800024c5  mov     eax, cs:dword_180015430
0x1800024cb  test    eax, eax
0x1800024cd  jg      short loc_1800024DC
0x1800024cf  xor     eax, eax
0x1800024d1  mov     rbx, [rsp+38h+arg_0]
0x1800024d6  add     rsp, 30h
0x1800024da  pop     rdi
0x1800024db  retn
0x1800024dc  dec     eax
0x1800024de  mov     cs:dword_180015430, eax
0x1800024e4  call    __scrt_acquire_startup_lock
0x1800024e9  mov     bl, al
0x1800024eb  mov     [rsp+38h+var_18], al
0x1800024ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800024f6  jnz     short loc_18000252E
0x1800024f8  call    __scrt_dllmain_uninitialize_c
0x1800024fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002502  call    _RTC_Terminate
0x180002507  mov     cs:__scrt_current_native_startup_state, 0
0x180002511  mov     cl, bl
0x180002513  call    __scrt_release_startup_lock
0x180002518  xor     edx, edx
0x18000251a  mov     cl, dil
0x18000251d  call    __scrt_uninitialize_crt
0x180002522  movzx   ebx, al
0x180002525  call    __scrt_dllmain_uninitialize_critical
0x18000252a  mov     eax, ebx
0x18000252c  jmp     short loc_1800024D1
0x18000252e  mov     ecx, 7
0x180002533  call    __scrt_fastfail
0x18000e4f9  push    rbp
0x18000e4fb  sub     rsp, 20h
0x18000e4ff  mov     rbp, rdx
0x18000e502  mov     cl, [rbp+20h]
0x18000e505  call    __scrt_release_startup_lock
0x18000e50a  nop
0x18000e50b  add     rsp, 20h
0x18000e50f  pop     rbp
0x18000e510  retn
0x18000e512  push    rbp
0x18000e514  sub     rsp, 20h
0x18000e518  mov     rbp, rdx
0x18000e51b  add     rsp, 20h
0x18000e51f  pop     rbp
0x18000e520  jmp     __scrt_dllmain_uninitialize_critical
```
