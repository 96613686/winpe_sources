# dllmain_crt_process_detach

- ea: `0x100426724`
- end: `0x1004267a8`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1004265b0`
- `0x1004267b0`

## callees

- `0x100426724`
- `0x100426cbc`
- `0x100426d04`
- `0x100426e50`
- `0x100426e88`
- `0x100427028`
- `0x100427054`
- `0x100427104`
- `0x10042729c`

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

  if ( dword_100450C54 <= 0 )
    return 0;
  --dword_100450C54;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1004267A8LL);
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
0x100426724  mov     [rsp+arg_0], rbx
0x100426729  push    rdi
0x10042672a  sub     rsp, 30h
0x10042672e  mov     dil, cl
0x100426731  mov     eax, cs:dword_100450C54
0x100426737  test    eax, eax
0x100426739  jg      short loc_100426748
0x10042673b  xor     eax, eax
0x10042673d  mov     rbx, [rsp+38h+arg_0]
0x100426742  add     rsp, 30h
0x100426746  pop     rdi
0x100426747  retn
0x100426748  dec     eax
0x10042674a  mov     cs:dword_100450C54, eax
0x100426750  call    __scrt_acquire_startup_lock
0x100426755  mov     bl, al
0x100426757  mov     [rsp+38h+var_18], al
0x10042675b  cmp     cs:__scrt_current_native_startup_state, 2
0x100426762  jnz     short loc_10042679B
0x100426764  call    __scrt_dllmain_uninitialize_c
0x100426769  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x10042676e  call    _RTC_Terminate
0x100426773  and     cs:__scrt_current_native_startup_state, 0
0x10042677a  mov     cl, bl
0x10042677c  call    __scrt_release_startup_lock
0x100426781  xor     edx, edx
0x100426783  mov     cl, dil
0x100426786  call    __scrt_uninitialize_crt
0x10042678b  neg     al
0x10042678d  sbb     ebx, ebx
0x10042678f  and     ebx, 1
0x100426792  call    __scrt_dllmain_uninitialize_critical
0x100426797  mov     eax, ebx
0x100426799  jmp     short loc_10042673D
0x10042679b  mov     ecx, 7
0x1004267a0  call    __scrt_fastfail
0x1004267a5  nop
0x1004267a6  nop
0x1004267a7  int     3; Trap to Debugger
0x10043a87d  push    rbp
0x10043a87f  sub     rsp, 20h
0x10043a883  mov     rbp, rdx
0x10043a886  mov     cl, [rbp+20h]
0x10043a889  call    __scrt_release_startup_lock
0x10043a88e  nop
0x10043a88f  add     rsp, 20h
0x10043a893  pop     rbp
0x10043a894  retn
0x10043a896  push    rbp
0x10043a898  sub     rsp, 20h
0x10043a89c  mov     rbp, rdx
0x10043a89f  add     rsp, 20h
0x10043a8a3  pop     rbp
0x10043a8a4  jmp     __scrt_dllmain_uninitialize_critical
```
