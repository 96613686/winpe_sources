# dllmain_crt_process_detach

- ea: `0x1800102a0`
- end: `0x180010323`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180010130`

## callees

- `0x18000fcb4`
- `0x18000fe00`
- `0x18000fe38`
- `0x18000ffc8`
- `0x18000fff4`
- `0x1800102a0`
- `0x180010924`
- `0x180010ba0`
- `0x180010c3c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180021824 <= 0 )
    return 0;
  --dword_180021824;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180010323LL);
  }
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
0x1800102a0  mov     [rsp+arg_0], rbx
0x1800102a5  push    rdi
0x1800102a6  sub     rsp, 30h
0x1800102aa  mov     dil, cl
0x1800102ad  mov     eax, cs:dword_180021824
0x1800102b3  test    eax, eax
0x1800102b5  jg      short loc_1800102C4
0x1800102b7  xor     eax, eax
0x1800102b9  mov     rbx, [rsp+38h+arg_0]
0x1800102be  add     rsp, 30h
0x1800102c2  pop     rdi
0x1800102c3  retn
0x1800102c4  dec     eax
0x1800102c6  mov     cs:dword_180021824, eax
0x1800102cc  call    __scrt_acquire_startup_lock
0x1800102d1  mov     bl, al
0x1800102d3  mov     [rsp+38h+var_18], al
0x1800102d7  cmp     cs:__scrt_current_native_startup_state, 2
0x1800102de  jnz     short loc_180010316
0x1800102e0  call    __scrt_dllmain_uninitialize_c
0x1800102e5  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800102ea  call    _RTC_Terminate
0x1800102ef  mov     cs:__scrt_current_native_startup_state, 0
0x1800102f9  mov     cl, bl
0x1800102fb  call    __scrt_release_startup_lock
0x180010300  xor     edx, edx
0x180010302  mov     cl, dil
0x180010305  call    __scrt_uninitialize_crt
0x18001030a  movzx   ebx, al
0x18001030d  call    __scrt_dllmain_uninitialize_critical
0x180010312  mov     eax, ebx
0x180010314  jmp     short loc_1800102B9
0x180010316  mov     ecx, 7
0x18001031b  call    __scrt_fastfail
0x180010320  nop
0x180010321  nop
0x180010322  int     3; Trap to Debugger
0x180016c1c  push    rbp
0x180016c1e  sub     rsp, 20h
0x180016c22  mov     rbp, rdx
0x180016c25  mov     cl, [rbp+20h]
0x180016c28  call    __scrt_release_startup_lock
0x180016c2d  nop
0x180016c2e  add     rsp, 20h
0x180016c32  pop     rbp
0x180016c33  retn
0x180016c35  push    rbp
0x180016c37  sub     rsp, 20h
0x180016c3b  mov     rbp, rdx
0x180016c3e  add     rsp, 20h
0x180016c42  pop     rbp
0x180016c43  jmp     __scrt_dllmain_uninitialize_critical
```
