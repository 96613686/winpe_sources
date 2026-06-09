# dllmain_crt_process_detach

- ea: `0x100416734`
- end: `0x1004167b8`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1004165c0`
- `0x1004167c0`

## callees

- `0x100416734`
- `0x100416ccc`
- `0x100416d24`
- `0x100416e70`
- `0x100416ea8`
- `0x100417048`
- `0x100417074`
- `0x100417124`
- `0x1004172bc`

## pseudocode

```c
_BOOL8 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  BOOL v7; // ebx
  __int64 v8; // rcx

  if ( dword_100434CD4 <= 0 )
    return 0;
  --dword_100434CD4;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1004167B8LL);
  }
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0) != 0;
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x100416734  mov     [rsp+arg_0], rbx
0x100416739  push    rdi
0x10041673a  sub     rsp, 30h
0x10041673e  mov     dil, cl
0x100416741  mov     eax, cs:dword_100434CD4
0x100416747  test    eax, eax
0x100416749  jg      short loc_100416758
0x10041674b  xor     eax, eax
0x10041674d  mov     rbx, [rsp+38h+arg_0]
0x100416752  add     rsp, 30h
0x100416756  pop     rdi
0x100416757  retn
0x100416758  dec     eax
0x10041675a  mov     cs:dword_100434CD4, eax
0x100416760  call    __scrt_acquire_startup_lock
0x100416765  mov     bl, al
0x100416767  mov     [rsp+38h+var_18], al
0x10041676b  cmp     cs:__scrt_current_native_startup_state, 2
0x100416772  jnz     short loc_1004167AB
0x100416774  call    __scrt_dllmain_uninitialize_c
0x100416779  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x10041677e  call    _RTC_Terminate
0x100416783  and     cs:__scrt_current_native_startup_state, 0
0x10041678a  mov     cl, bl
0x10041678c  call    __scrt_release_startup_lock
0x100416791  xor     edx, edx
0x100416793  mov     cl, dil
0x100416796  call    __scrt_uninitialize_crt
0x10041679b  neg     al
0x10041679d  sbb     ebx, ebx
0x10041679f  and     ebx, 1
0x1004167a2  call    __scrt_dllmain_uninitialize_critical
0x1004167a7  mov     eax, ebx
0x1004167a9  jmp     short loc_10041674D
0x1004167ab  mov     ecx, 7
0x1004167b0  call    __scrt_fastfail
0x1004167b5  nop
0x1004167b6  nop
0x1004167b7  int     3; Trap to Debugger
0x10042508d  push    rbp
0x10042508f  sub     rsp, 20h
0x100425093  mov     rbp, rdx
0x100425096  mov     cl, [rbp+20h]
0x100425099  call    __scrt_release_startup_lock
0x10042509e  nop
0x10042509f  add     rsp, 20h
0x1004250a3  pop     rbp
0x1004250a4  retn
0x1004250a6  push    rbp
0x1004250a8  sub     rsp, 20h
0x1004250ac  mov     rbp, rdx
0x1004250af  add     rsp, 20h
0x1004250b3  pop     rbp
0x1004250b4  jmp     __scrt_dllmain_uninitialize_critical
```
