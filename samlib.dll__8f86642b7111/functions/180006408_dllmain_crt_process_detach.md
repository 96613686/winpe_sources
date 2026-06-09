# dllmain_crt_process_detach

- ea: `0x180006408`
- end: `0x18000648b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800062b0`

## callees

- `0x180006408`
- `0x180006714`
- `0x18000674c`
- `0x180006874`
- `0x1800068ac`
- `0x180006a3c`
- `0x180006a68`
- `0x180006aa8`
- `0x180006af8`

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

  if ( dword_180027110 <= 0 )
    return 0;
  --dword_180027110;
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
0x180006408  mov     [rsp+arg_0], rbx
0x18000640d  push    rdi
0x18000640e  sub     rsp, 30h
0x180006412  mov     dil, cl
0x180006415  mov     eax, cs:dword_180027110
0x18000641b  test    eax, eax
0x18000641d  jg      short loc_18000642C
0x18000641f  xor     eax, eax
0x180006421  mov     rbx, [rsp+38h+arg_0]
0x180006426  add     rsp, 30h
0x18000642a  pop     rdi
0x18000642b  retn
0x18000642c  dec     eax
0x18000642e  mov     cs:dword_180027110, eax
0x180006434  call    __scrt_acquire_startup_lock
0x180006439  mov     bl, al
0x18000643b  mov     [rsp+38h+var_18], al
0x18000643f  cmp     cs:__scrt_current_native_startup_state, 2
0x180006446  jnz     short loc_18000647E
0x180006448  call    __scrt_dllmain_uninitialize_c
0x18000644d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180006452  call    _RTC_Terminate
0x180006457  mov     cs:__scrt_current_native_startup_state, 0
0x180006461  mov     cl, bl
0x180006463  call    __scrt_release_startup_lock
0x180006468  xor     edx, edx
0x18000646a  mov     cl, dil
0x18000646d  call    __scrt_uninitialize_crt
0x180006472  movzx   ebx, al
0x180006475  call    __scrt_dllmain_uninitialize_critical
0x18000647a  mov     eax, ebx
0x18000647c  jmp     short loc_180006421
0x18000647e  mov     ecx, 7
0x180006483  call    __scrt_fastfail
0x180017d2f  push    rbp
0x180017d31  sub     rsp, 20h
0x180017d35  mov     rbp, rdx
0x180017d38  mov     cl, [rbp+20h]
0x180017d3b  call    __scrt_release_startup_lock
0x180017d40  nop
0x180017d41  add     rsp, 20h
0x180017d45  pop     rbp
0x180017d46  retn
0x180017d48  push    rbp
0x180017d4a  sub     rsp, 20h
0x180017d4e  mov     rbp, rdx
0x180017d51  add     rsp, 20h
0x180017d55  pop     rbp
0x180017d56  jmp     __scrt_dllmain_uninitialize_critical
```
