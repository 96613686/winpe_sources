# dllmain_crt_process_detach

- ea: `0x180002358`
- end: `0x1800023db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002200`

## callees

- `0x180002358`
- `0x1800025f0`
- `0x180002718`
- `0x180002750`
- `0x1800028e0`
- `0x18000290c`
- `0x180002a6c`
- `0x180002ab4`
- `0x180002b04`

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

  if ( dword_180015190 <= 0 )
    return 0;
  --dword_180015190;
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
0x180002358  mov     [rsp+arg_0], rbx
0x18000235d  push    rdi
0x18000235e  sub     rsp, 30h
0x180002362  mov     dil, cl
0x180002365  mov     eax, cs:dword_180015190
0x18000236b  test    eax, eax
0x18000236d  jg      short loc_18000237C
0x18000236f  xor     eax, eax
0x180002371  mov     rbx, [rsp+38h+arg_0]
0x180002376  add     rsp, 30h
0x18000237a  pop     rdi
0x18000237b  retn
0x18000237c  dec     eax
0x18000237e  mov     cs:dword_180015190, eax
0x180002384  call    __scrt_acquire_startup_lock
0x180002389  mov     bl, al
0x18000238b  mov     [rsp+38h+var_18], al
0x18000238f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002396  jnz     short loc_1800023CE
0x180002398  call    __scrt_dllmain_uninitialize_c
0x18000239d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800023a2  call    _RTC_Terminate
0x1800023a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800023b1  mov     cl, bl
0x1800023b3  call    __scrt_release_startup_lock
0x1800023b8  xor     edx, edx
0x1800023ba  mov     cl, dil
0x1800023bd  call    __scrt_uninitialize_crt
0x1800023c2  movzx   ebx, al
0x1800023c5  call    __scrt_dllmain_uninitialize_critical
0x1800023ca  mov     eax, ebx
0x1800023cc  jmp     short loc_180002371
0x1800023ce  mov     ecx, 7
0x1800023d3  call    __scrt_fastfail
0x180003583  push    rbp
0x180003585  sub     rsp, 20h
0x180003589  mov     rbp, rdx
0x18000358c  mov     cl, [rbp+20h]
0x18000358f  call    __scrt_release_startup_lock
0x180003594  nop
0x180003595  add     rsp, 20h
0x180003599  pop     rbp
0x18000359a  retn
0x18000359c  push    rbp
0x18000359e  sub     rsp, 20h
0x1800035a2  mov     rbp, rdx
0x1800035a5  add     rsp, 20h
0x1800035a9  pop     rbp
0x1800035aa  jmp     __scrt_dllmain_uninitialize_critical
```
