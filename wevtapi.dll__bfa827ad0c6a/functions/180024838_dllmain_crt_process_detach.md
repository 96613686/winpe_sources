# dllmain_crt_process_detach

- ea: `0x180024838`
- end: `0x1800248bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800246e0`

## callees

- `0x180024838`
- `0x180024aac`
- `0x180024bd4`
- `0x180024c0c`
- `0x180024d9c`
- `0x180024dc8`
- `0x18002506c`
- `0x1800250b4`
- `0x180025104`

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

  if ( dword_18004B290 <= 0 )
    return 0;
  --dword_18004B290;
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
0x180024838  mov     [rsp+arg_0], rbx
0x18002483d  push    rdi
0x18002483e  sub     rsp, 30h
0x180024842  mov     dil, cl
0x180024845  mov     eax, cs:dword_18004B290
0x18002484b  test    eax, eax
0x18002484d  jg      short loc_18002485C
0x18002484f  xor     eax, eax
0x180024851  mov     rbx, [rsp+38h+arg_0]
0x180024856  add     rsp, 30h
0x18002485a  pop     rdi
0x18002485b  retn
0x18002485c  dec     eax
0x18002485e  mov     cs:dword_18004B290, eax
0x180024864  call    __scrt_acquire_startup_lock
0x180024869  mov     bl, al
0x18002486b  mov     [rsp+38h+var_18], al
0x18002486f  cmp     cs:__scrt_current_native_startup_state, 2
0x180024876  jnz     short loc_1800248AE
0x180024878  call    __scrt_dllmain_uninitialize_c
0x18002487d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180024882  call    _RTC_Terminate
0x180024887  mov     cs:__scrt_current_native_startup_state, 0
0x180024891  mov     cl, bl
0x180024893  call    __scrt_release_startup_lock
0x180024898  xor     edx, edx
0x18002489a  mov     cl, dil
0x18002489d  call    __scrt_uninitialize_crt
0x1800248a2  movzx   ebx, al
0x1800248a5  call    __scrt_dllmain_uninitialize_critical
0x1800248aa  mov     eax, ebx
0x1800248ac  jmp     short loc_180024851
0x1800248ae  mov     ecx, 7
0x1800248b3  call    __scrt_fastfail
0x18003a824  push    rbp
0x18003a826  sub     rsp, 20h
0x18003a82a  mov     rbp, rdx
0x18003a82d  mov     cl, [rbp+20h]
0x18003a830  call    __scrt_release_startup_lock
0x18003a835  nop
0x18003a836  add     rsp, 20h
0x18003a83a  pop     rbp
0x18003a83b  retn
0x18003a83d  push    rbp
0x18003a83f  sub     rsp, 20h
0x18003a843  mov     rbp, rdx
0x18003a846  add     rsp, 20h
0x18003a84a  pop     rbp
0x18003a84b  jmp     __scrt_dllmain_uninitialize_critical
```
