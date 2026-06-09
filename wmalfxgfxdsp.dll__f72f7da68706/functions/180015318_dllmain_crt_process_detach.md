# dllmain_crt_process_detach

- ea: `0x180015318`
- end: `0x18001539b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800151c0`

## callees

- `0x180015318`
- `0x180015600`
- `0x180015638`
- `0x180015760`
- `0x180015798`
- `0x180015928`
- `0x180015954`
- `0x1800159f4`
- `0x180015a44`

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

  if ( dword_1801B9510 <= 0 )
    return 0;
  --dword_1801B9510;
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
0x180015318  mov     [rsp+arg_0], rbx
0x18001531d  push    rdi
0x18001531e  sub     rsp, 30h
0x180015322  mov     dil, cl
0x180015325  mov     eax, cs:dword_1801B9510
0x18001532b  test    eax, eax
0x18001532d  jg      short loc_18001533C
0x18001532f  xor     eax, eax
0x180015331  mov     rbx, [rsp+38h+arg_0]
0x180015336  add     rsp, 30h
0x18001533a  pop     rdi
0x18001533b  retn
0x18001533c  dec     eax
0x18001533e  mov     cs:dword_1801B9510, eax
0x180015344  call    __scrt_acquire_startup_lock
0x180015349  mov     bl, al
0x18001534b  mov     [rsp+38h+var_18], al
0x18001534f  cmp     cs:__scrt_current_native_startup_state, 2
0x180015356  jnz     short loc_18001538E
0x180015358  call    __scrt_dllmain_uninitialize_c
0x18001535d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180015362  call    _RTC_Terminate
0x180015367  mov     cs:__scrt_current_native_startup_state, 0
0x180015371  mov     cl, bl
0x180015373  call    __scrt_release_startup_lock
0x180015378  xor     edx, edx
0x18001537a  mov     cl, dil
0x18001537d  call    __scrt_uninitialize_crt
0x180015382  movzx   ebx, al
0x180015385  call    __scrt_dllmain_uninitialize_critical
0x18001538a  mov     eax, ebx
0x18001538c  jmp     short loc_180015331
0x18001538e  mov     ecx, 7
0x180015393  call    __scrt_fastfail
0x180085ad9  push    rbp
0x180085adb  sub     rsp, 20h
0x180085adf  mov     rbp, rdx
0x180085ae2  mov     cl, [rbp+20h]
0x180085ae5  call    __scrt_release_startup_lock
0x180085aea  nop
0x180085aeb  add     rsp, 20h
0x180085aef  pop     rbp
0x180085af0  retn
0x180085af2  push    rbp
0x180085af4  sub     rsp, 20h
0x180085af8  mov     rbp, rdx
0x180085afb  add     rsp, 20h
0x180085aff  pop     rbp
0x180085b00  jmp     __scrt_dllmain_uninitialize_critical
```
