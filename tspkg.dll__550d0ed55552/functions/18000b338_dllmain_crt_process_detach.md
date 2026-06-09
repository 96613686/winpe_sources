# dllmain_crt_process_detach

- ea: `0x18000b338`
- end: `0x18000b3bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000b1e0`

## callees

- `0x18000b338`
- `0x18000b574`
- `0x18000b69c`
- `0x18000b6d4`
- `0x18000b864`
- `0x18000b890`
- `0x18000ba5c`
- `0x18000baa4`
- `0x18000baf4`

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

  if ( dword_180025410 <= 0 )
    return 0;
  --dword_180025410;
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
0x18000b338  mov     [rsp+arg_0], rbx
0x18000b33d  push    rdi
0x18000b33e  sub     rsp, 30h
0x18000b342  mov     dil, cl
0x18000b345  mov     eax, cs:dword_180025410
0x18000b34b  test    eax, eax
0x18000b34d  jg      short loc_18000B35C
0x18000b34f  xor     eax, eax
0x18000b351  mov     rbx, [rsp+38h+arg_0]
0x18000b356  add     rsp, 30h
0x18000b35a  pop     rdi
0x18000b35b  retn
0x18000b35c  dec     eax
0x18000b35e  mov     cs:dword_180025410, eax
0x18000b364  call    __scrt_acquire_startup_lock
0x18000b369  mov     bl, al
0x18000b36b  mov     [rsp+38h+var_18], al
0x18000b36f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000b376  jnz     short loc_18000B3AE
0x18000b378  call    __scrt_dllmain_uninitialize_c
0x18000b37d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000b382  call    _RTC_Terminate
0x18000b387  mov     cs:__scrt_current_native_startup_state, 0
0x18000b391  mov     cl, bl
0x18000b393  call    __scrt_release_startup_lock
0x18000b398  xor     edx, edx
0x18000b39a  mov     cl, dil
0x18000b39d  call    __scrt_uninitialize_crt
0x18000b3a2  movzx   ebx, al
0x18000b3a5  call    __scrt_dllmain_uninitialize_critical
0x18000b3aa  mov     eax, ebx
0x18000b3ac  jmp     short loc_18000B351
0x18000b3ae  mov     ecx, 7
0x18000b3b3  call    __scrt_fastfail
0x18001c6d9  push    rbp
0x18001c6db  sub     rsp, 20h
0x18001c6df  mov     rbp, rdx
0x18001c6e2  mov     cl, [rbp+20h]
0x18001c6e5  call    __scrt_release_startup_lock
0x18001c6ea  nop
0x18001c6eb  add     rsp, 20h
0x18001c6ef  pop     rbp
0x18001c6f0  retn
0x18001c6f2  push    rbp
0x18001c6f4  sub     rsp, 20h
0x18001c6f8  mov     rbp, rdx
0x18001c6fb  add     rsp, 20h
0x18001c6ff  pop     rbp
0x18001c700  jmp     __scrt_dllmain_uninitialize_critical
```
