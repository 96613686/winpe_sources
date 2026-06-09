# dllmain_crt_process_detach

- ea: `0x180005518`
- end: `0x18000559b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800053c0`

## callees

- `0x180005518`
- `0x180005850`
- `0x180005888`
- `0x1800059b0`
- `0x1800059e8`
- `0x180005b78`
- `0x180005ba4`
- `0x180005be4`
- `0x180005c34`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_180010110 <= 0 )
    return 0;
  --dword_180010110;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180005518  mov     [rsp+arg_0], rbx
0x18000551d  push    rdi
0x18000551e  sub     rsp, 30h
0x180005522  mov     dil, cl
0x180005525  mov     eax, cs:dword_180010110
0x18000552b  test    eax, eax
0x18000552d  jg      short loc_18000553C
0x18000552f  xor     eax, eax
0x180005531  mov     rbx, [rsp+38h+arg_0]
0x180005536  add     rsp, 30h
0x18000553a  pop     rdi
0x18000553b  retn
0x18000553c  dec     eax
0x18000553e  mov     cs:dword_180010110, eax
0x180005544  call    __scrt_acquire_startup_lock
0x180005549  mov     bl, al
0x18000554b  mov     [rsp+38h+var_18], al
0x18000554f  cmp     cs:__scrt_current_native_startup_state, 2
0x180005556  jnz     short loc_18000558E
0x180005558  call    __scrt_dllmain_uninitialize_c
0x18000555d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180005562  call    _RTC_Terminate
0x180005567  mov     cs:__scrt_current_native_startup_state, 0
0x180005571  mov     cl, bl
0x180005573  call    __scrt_release_startup_lock
0x180005578  xor     edx, edx
0x18000557a  mov     cl, dil
0x18000557d  call    __scrt_uninitialize_crt
0x180005582  movzx   ebx, al
0x180005585  call    __scrt_dllmain_uninitialize_critical
0x18000558a  mov     eax, ebx
0x18000558c  jmp     short loc_180005531
0x18000558e  mov     ecx, 7
0x180005593  call    __scrt_fastfail
0x18000baa9  push    rbp
0x18000baab  sub     rsp, 20h
0x18000baaf  mov     rbp, rdx
0x18000bab2  mov     cl, [rbp+20h]
0x18000bab5  call    __scrt_release_startup_lock
0x18000baba  nop
0x18000babb  add     rsp, 20h
0x18000babf  pop     rbp
0x18000bac0  retn
0x18000bac2  push    rbp
0x18000bac4  sub     rsp, 20h
0x18000bac8  mov     rbp, rdx
0x18000bacb  add     rsp, 20h
0x18000bacf  pop     rbp
0x18000bad0  jmp     __scrt_dllmain_uninitialize_critical
```
