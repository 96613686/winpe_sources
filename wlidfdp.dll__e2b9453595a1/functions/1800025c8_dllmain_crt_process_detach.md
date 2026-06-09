# dllmain_crt_process_detach

- ea: `0x1800025c8`
- end: `0x18000264b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002470`

## callees

- `0x1800025c8`
- `0x18000284c`
- `0x180002974`
- `0x1800029ac`
- `0x180002b3c`
- `0x180002b68`
- `0x180002d64`
- `0x180002dac`
- `0x180002dfc`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180020490 <= 0 )
    return 0;
  --dword_180020490;
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
0x1800025c8  mov     [rsp+arg_0], rbx
0x1800025cd  push    rdi
0x1800025ce  sub     rsp, 30h
0x1800025d2  mov     dil, cl
0x1800025d5  mov     eax, cs:dword_180020490
0x1800025db  test    eax, eax
0x1800025dd  jg      short loc_1800025EC
0x1800025df  xor     eax, eax
0x1800025e1  mov     rbx, [rsp+38h+arg_0]
0x1800025e6  add     rsp, 30h
0x1800025ea  pop     rdi
0x1800025eb  retn
0x1800025ec  dec     eax
0x1800025ee  mov     cs:dword_180020490, eax
0x1800025f4  call    __scrt_acquire_startup_lock
0x1800025f9  mov     bl, al
0x1800025fb  mov     [rsp+38h+var_18], al
0x1800025ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180002606  jnz     short loc_18000263E
0x180002608  call    __scrt_dllmain_uninitialize_c
0x18000260d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002612  call    _RTC_Terminate
0x180002617  mov     cs:__scrt_current_native_startup_state, 0
0x180002621  mov     cl, bl
0x180002623  call    __scrt_release_startup_lock
0x180002628  xor     edx, edx
0x18000262a  mov     cl, dil
0x18000262d  call    __scrt_uninitialize_crt
0x180002632  movzx   ebx, al
0x180002635  call    __scrt_dllmain_uninitialize_critical
0x18000263a  mov     eax, ebx
0x18000263c  jmp     short loc_1800025E1
0x18000263e  mov     ecx, 7
0x180002643  call    __scrt_fastfail
0x1800106e9  push    rbp
0x1800106eb  sub     rsp, 20h
0x1800106ef  mov     rbp, rdx
0x1800106f2  mov     cl, [rbp+20h]
0x1800106f5  call    __scrt_release_startup_lock
0x1800106fa  nop
0x1800106fb  add     rsp, 20h
0x1800106ff  pop     rbp
0x180010700  retn
0x180010702  push    rbp
0x180010704  sub     rsp, 20h
0x180010708  mov     rbp, rdx
0x18001070b  add     rsp, 20h
0x18001070f  pop     rbp
0x180010710  jmp     __scrt_dllmain_uninitialize_critical
```
