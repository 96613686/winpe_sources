# dllmain_crt_process_detach

- ea: `0x180002018`
- end: `0x18000209b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001ec0`

## callees

- `0x180002018`
- `0x180002254`
- `0x18000237c`
- `0x1800023b4`
- `0x180002544`
- `0x180002570`
- `0x180002700`
- `0x180002748`
- `0x180002798`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18000FA10 <= 0 )
    return 0;
  --dword_18000FA10;
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
0x180002018  mov     [rsp+arg_0], rbx
0x18000201d  push    rdi
0x18000201e  sub     rsp, 30h
0x180002022  mov     dil, cl
0x180002025  mov     eax, cs:dword_18000FA10
0x18000202b  test    eax, eax
0x18000202d  jg      short loc_18000203C
0x18000202f  xor     eax, eax
0x180002031  mov     rbx, [rsp+38h+arg_0]
0x180002036  add     rsp, 30h
0x18000203a  pop     rdi
0x18000203b  retn
0x18000203c  dec     eax
0x18000203e  mov     cs:dword_18000FA10, eax
0x180002044  call    __scrt_acquire_startup_lock
0x180002049  mov     bl, al
0x18000204b  mov     [rsp+38h+var_18], al
0x18000204f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002056  jnz     short loc_18000208E
0x180002058  call    __scrt_dllmain_uninitialize_c
0x18000205d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002062  call    _RTC_Terminate
0x180002067  mov     cs:__scrt_current_native_startup_state, 0
0x180002071  mov     cl, bl
0x180002073  call    __scrt_release_startup_lock
0x180002078  xor     edx, edx
0x18000207a  mov     cl, dil
0x18000207d  call    __scrt_uninitialize_crt
0x180002082  movzx   ebx, al
0x180002085  call    __scrt_dllmain_uninitialize_critical
0x18000208a  mov     eax, ebx
0x18000208c  jmp     short loc_180002031
0x18000208e  mov     ecx, 7
0x180002093  call    __scrt_fastfail
0x1800097d9  push    rbp
0x1800097db  sub     rsp, 20h
0x1800097df  mov     rbp, rdx
0x1800097e2  mov     cl, [rbp+20h]
0x1800097e5  call    __scrt_release_startup_lock
0x1800097ea  nop
0x1800097eb  add     rsp, 20h
0x1800097ef  pop     rbp
0x1800097f0  retn
0x1800097f2  push    rbp
0x1800097f4  sub     rsp, 20h
0x1800097f8  mov     rbp, rdx
0x1800097fb  add     rsp, 20h
0x1800097ff  pop     rbp
0x180009800  jmp     __scrt_dllmain_uninitialize_critical
```
