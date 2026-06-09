# dllmain_crt_process_detach

- ea: `0x1800108b0`
- end: `0x180010933`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180010740`

## callees

- `0x180010340`
- `0x18001048c`
- `0x1800104c4`
- `0x180010654`
- `0x180010680`
- `0x1800108b0`
- `0x180010f40`
- `0x18001118c`
- `0x180011228`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001F884 <= 0 )
    return 0;
  --dword_18001F884;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180010933LL);
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
0x1800108b0  mov     [rsp+arg_0], rbx
0x1800108b5  push    rdi
0x1800108b6  sub     rsp, 30h
0x1800108ba  mov     dil, cl
0x1800108bd  mov     eax, cs:dword_18001F884
0x1800108c3  test    eax, eax
0x1800108c5  jg      short loc_1800108D4
0x1800108c7  xor     eax, eax
0x1800108c9  mov     rbx, [rsp+38h+arg_0]
0x1800108ce  add     rsp, 30h
0x1800108d2  pop     rdi
0x1800108d3  retn
0x1800108d4  dec     eax
0x1800108d6  mov     cs:dword_18001F884, eax
0x1800108dc  call    __scrt_acquire_startup_lock
0x1800108e1  mov     bl, al
0x1800108e3  mov     [rsp+38h+var_18], al
0x1800108e7  cmp     cs:__scrt_current_native_startup_state, 2
0x1800108ee  jnz     short loc_180010926
0x1800108f0  call    __scrt_dllmain_uninitialize_c
0x1800108f5  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800108fa  call    _RTC_Terminate
0x1800108ff  mov     cs:__scrt_current_native_startup_state, 0
0x180010909  mov     cl, bl
0x18001090b  call    __scrt_release_startup_lock
0x180010910  xor     edx, edx
0x180010912  mov     cl, dil
0x180010915  call    __scrt_uninitialize_crt
0x18001091a  movzx   ebx, al
0x18001091d  call    __scrt_dllmain_uninitialize_critical
0x180010922  mov     eax, ebx
0x180010924  jmp     short loc_1800108C9
0x180010926  mov     ecx, 7
0x18001092b  call    __scrt_fastfail
0x180010930  nop
0x180010931  nop
0x180010932  int     3; Trap to Debugger
0x180015ebc  push    rbp
0x180015ebe  sub     rsp, 20h
0x180015ec2  mov     rbp, rdx
0x180015ec5  mov     cl, [rbp+20h]
0x180015ec8  call    __scrt_release_startup_lock
0x180015ecd  nop
0x180015ece  add     rsp, 20h
0x180015ed2  pop     rbp
0x180015ed3  retn
0x180015ed5  push    rbp
0x180015ed7  sub     rsp, 20h
0x180015edb  mov     rbp, rdx
0x180015ede  add     rsp, 20h
0x180015ee2  pop     rbp
0x180015ee3  jmp     __scrt_dllmain_uninitialize_critical
```
