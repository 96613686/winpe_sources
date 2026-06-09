# dllmain_crt_process_detach

- ea: `0x180005468`
- end: `0x1800054eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180005310`

## callees

- `0x180005468`
- `0x1800056a4`
- `0x1800057cc`
- `0x180005804`
- `0x180005994`
- `0x1800059c0`
- `0x180005b4c`
- `0x180005b94`
- `0x180005be4`

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

  if ( dword_180022370 <= 0 )
    return 0;
  --dword_180022370;
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
0x180005468  mov     [rsp+arg_0], rbx
0x18000546d  push    rdi
0x18000546e  sub     rsp, 30h
0x180005472  mov     dil, cl
0x180005475  mov     eax, cs:dword_180022370
0x18000547b  test    eax, eax
0x18000547d  jg      short loc_18000548C
0x18000547f  xor     eax, eax
0x180005481  mov     rbx, [rsp+38h+arg_0]
0x180005486  add     rsp, 30h
0x18000548a  pop     rdi
0x18000548b  retn
0x18000548c  dec     eax
0x18000548e  mov     cs:dword_180022370, eax
0x180005494  call    __scrt_acquire_startup_lock
0x180005499  mov     bl, al
0x18000549b  mov     [rsp+38h+var_18], al
0x18000549f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800054a6  jnz     short loc_1800054DE
0x1800054a8  call    __scrt_dllmain_uninitialize_c
0x1800054ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800054b2  call    _RTC_Terminate
0x1800054b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800054c1  mov     cl, bl
0x1800054c3  call    __scrt_release_startup_lock
0x1800054c8  xor     edx, edx
0x1800054ca  mov     cl, dil
0x1800054cd  call    __scrt_uninitialize_crt
0x1800054d2  movzx   ebx, al
0x1800054d5  call    __scrt_dllmain_uninitialize_critical
0x1800054da  mov     eax, ebx
0x1800054dc  jmp     short loc_180005481
0x1800054de  mov     ecx, 7
0x1800054e3  call    __scrt_fastfail
0x180016afd  push    rbp
0x180016aff  sub     rsp, 20h
0x180016b03  mov     rbp, rdx
0x180016b06  mov     cl, [rbp+20h]
0x180016b09  call    __scrt_release_startup_lock
0x180016b0e  nop
0x180016b0f  add     rsp, 20h
0x180016b13  pop     rbp
0x180016b14  retn
0x180016b16  push    rbp
0x180016b18  sub     rsp, 20h
0x180016b1c  mov     rbp, rdx
0x180016b1f  add     rsp, 20h
0x180016b23  pop     rbp
0x180016b24  jmp     __scrt_dllmain_uninitialize_critical
```
