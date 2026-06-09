# dllmain_crt_process_detach

- ea: `0x180005108`
- end: `0x18000518b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004fb0`

## callees

- `0x180005108`
- `0x180005344`
- `0x18000546c`
- `0x1800054a4`
- `0x180005634`
- `0x180005660`
- `0x1800057ec`
- `0x180005834`
- `0x180005884`

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

  if ( dword_180021370 <= 0 )
    return 0;
  --dword_180021370;
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
0x180005108  mov     [rsp+arg_0], rbx
0x18000510d  push    rdi
0x18000510e  sub     rsp, 30h
0x180005112  mov     dil, cl
0x180005115  mov     eax, cs:dword_180021370
0x18000511b  test    eax, eax
0x18000511d  jg      short loc_18000512C
0x18000511f  xor     eax, eax
0x180005121  mov     rbx, [rsp+38h+arg_0]
0x180005126  add     rsp, 30h
0x18000512a  pop     rdi
0x18000512b  retn
0x18000512c  dec     eax
0x18000512e  mov     cs:dword_180021370, eax
0x180005134  call    __scrt_acquire_startup_lock
0x180005139  mov     bl, al
0x18000513b  mov     [rsp+38h+var_18], al
0x18000513f  cmp     cs:__scrt_current_native_startup_state, 2
0x180005146  jnz     short loc_18000517E
0x180005148  call    __scrt_dllmain_uninitialize_c
0x18000514d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180005152  call    _RTC_Terminate
0x180005157  mov     cs:__scrt_current_native_startup_state, 0
0x180005161  mov     cl, bl
0x180005163  call    __scrt_release_startup_lock
0x180005168  xor     edx, edx
0x18000516a  mov     cl, dil
0x18000516d  call    __scrt_uninitialize_crt
0x180005172  movzx   ebx, al
0x180005175  call    __scrt_dllmain_uninitialize_critical
0x18000517a  mov     eax, ebx
0x18000517c  jmp     short loc_180005121
0x18000517e  mov     ecx, 7
0x180005183  call    __scrt_fastfail
0x1800150fd  push    rbp
0x1800150ff  sub     rsp, 20h
0x180015103  mov     rbp, rdx
0x180015106  mov     cl, [rbp+20h]
0x180015109  call    __scrt_release_startup_lock
0x18001510e  nop
0x18001510f  add     rsp, 20h
0x180015113  pop     rbp
0x180015114  retn
0x180015116  push    rbp
0x180015118  sub     rsp, 20h
0x18001511c  mov     rbp, rdx
0x18001511f  add     rsp, 20h
0x180015123  pop     rbp
0x180015124  jmp     __scrt_dllmain_uninitialize_critical
```
