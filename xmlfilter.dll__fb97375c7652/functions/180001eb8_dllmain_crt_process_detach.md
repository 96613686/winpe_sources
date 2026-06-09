# dllmain_crt_process_detach

- ea: `0x180001eb8`
- end: `0x180001f3b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001d60`

## callees

- `0x180001eb8`
- `0x18000218c`
- `0x1800022b4`
- `0x1800022ec`
- `0x18000247c`
- `0x1800024a8`
- `0x180002660`
- `0x1800026a8`
- `0x1800026f8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800217F0 <= 0 )
    return 0;
  --dword_1800217F0;
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
0x180001eb8  mov     [rsp+arg_0], rbx
0x180001ebd  push    rdi
0x180001ebe  sub     rsp, 30h
0x180001ec2  mov     dil, cl
0x180001ec5  mov     eax, cs:dword_1800217F0
0x180001ecb  test    eax, eax
0x180001ecd  jg      short loc_180001EDC
0x180001ecf  xor     eax, eax
0x180001ed1  mov     rbx, [rsp+38h+arg_0]
0x180001ed6  add     rsp, 30h
0x180001eda  pop     rdi
0x180001edb  retn
0x180001edc  dec     eax
0x180001ede  mov     cs:dword_1800217F0, eax
0x180001ee4  call    __scrt_acquire_startup_lock
0x180001ee9  mov     bl, al
0x180001eeb  mov     [rsp+38h+var_18], al
0x180001eef  cmp     cs:__scrt_current_native_startup_state, 2
0x180001ef6  jnz     short loc_180001F2E
0x180001ef8  call    __scrt_dllmain_uninitialize_c
0x180001efd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001f02  call    _RTC_Terminate
0x180001f07  mov     cs:__scrt_current_native_startup_state, 0
0x180001f11  mov     cl, bl
0x180001f13  call    __scrt_release_startup_lock
0x180001f18  xor     edx, edx
0x180001f1a  mov     cl, dil
0x180001f1d  call    __scrt_uninitialize_crt
0x180001f22  movzx   ebx, al
0x180001f25  call    __scrt_dllmain_uninitialize_critical
0x180001f2a  mov     eax, ebx
0x180001f2c  jmp     short loc_180001ED1
0x180001f2e  mov     ecx, 7
0x180001f33  call    __scrt_fastfail
0x180014509  push    rbp
0x18001450b  sub     rsp, 20h
0x18001450f  mov     rbp, rdx
0x180014512  mov     cl, [rbp+20h]
0x180014515  call    __scrt_release_startup_lock
0x18001451a  nop
0x18001451b  add     rsp, 20h
0x18001451f  pop     rbp
0x180014520  retn
0x180014522  push    rbp
0x180014524  sub     rsp, 20h
0x180014528  mov     rbp, rdx
0x18001452b  add     rsp, 20h
0x18001452f  pop     rbp
0x180014530  jmp     __scrt_dllmain_uninitialize_critical
```
