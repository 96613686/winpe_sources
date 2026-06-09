# dllmain_crt_process_detach

- ea: `0x180001ba8`
- end: `0x180001c2b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001ba8`
- `0x180001de4`
- `0x180001f0c`
- `0x180001f44`
- `0x1800020d4`
- `0x180002100`
- `0x180002598`
- `0x1800025e0`
- `0x180002630`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180013330 <= 0 )
    return 0;
  --dword_180013330;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x180001ba8  mov     [rsp+arg_0], rbx
0x180001bad  push    rdi
0x180001bae  sub     rsp, 30h
0x180001bb2  mov     dil, cl
0x180001bb5  mov     eax, cs:dword_180013330
0x180001bbb  test    eax, eax
0x180001bbd  jg      short loc_180001BCC
0x180001bbf  xor     eax, eax
0x180001bc1  mov     rbx, [rsp+38h+arg_0]
0x180001bc6  add     rsp, 30h
0x180001bca  pop     rdi
0x180001bcb  retn
0x180001bcc  dec     eax
0x180001bce  mov     cs:dword_180013330, eax
0x180001bd4  call    __scrt_acquire_startup_lock
0x180001bd9  mov     bl, al
0x180001bdb  mov     [rsp+38h+var_18], al
0x180001bdf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001be6  jnz     short loc_180001C1E
0x180001be8  call    __scrt_dllmain_uninitialize_c
0x180001bed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001bf2  call    _RTC_Terminate
0x180001bf7  mov     cs:__scrt_current_native_startup_state, 0
0x180001c01  mov     cl, bl
0x180001c03  call    __scrt_release_startup_lock
0x180001c08  xor     edx, edx
0x180001c0a  mov     cl, dil
0x180001c0d  call    __scrt_uninitialize_crt
0x180001c12  movzx   ebx, al
0x180001c15  call    __scrt_dllmain_uninitialize_critical
0x180001c1a  mov     eax, ebx
0x180001c1c  jmp     short loc_180001BC1
0x180001c1e  mov     ecx, 7
0x180001c23  call    __scrt_fastfail
0x18000bba9  push    rbp
0x18000bbab  sub     rsp, 20h
0x18000bbaf  mov     rbp, rdx
0x18000bbb2  mov     cl, [rbp+20h]
0x18000bbb5  call    __scrt_release_startup_lock
0x18000bbba  nop
0x18000bbbb  add     rsp, 20h
0x18000bbbf  pop     rbp
0x18000bbc0  retn
0x18000bbc2  push    rbp
0x18000bbc4  sub     rsp, 20h
0x18000bbc8  mov     rbp, rdx
0x18000bbcb  add     rsp, 20h
0x18000bbcf  pop     rbp
0x18000bbd0  jmp     __scrt_dllmain_uninitialize_critical
```
