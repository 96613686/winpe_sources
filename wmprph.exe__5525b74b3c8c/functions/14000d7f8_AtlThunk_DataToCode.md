# AtlThunk_DataToCode

- ea: `0x14000d7f8`
- end: `0x14000d834`
- name: `AtlThunk_DataToCode`
- size: `60`
- prototype: `WNDPROC __stdcall(AtlThunkData_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140007eec`
- `0x140008980`
- `0x140008a74`

## callees

- `0x14000d254`
- `0x14000d7f8`
- `0x14000f010`

## pseudocode

```c
WNDPROC __stdcall AtlThunk_DataToCode(AtlThunkData_t *a1)
{
  WNDPROC result; // rax
  __int64 (__fastcall *ProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64)(_QWORD); // rax

  if ( !a1 )
    return 0;
  result = (WNDPROC)*((_QWORD *)a1 + 1);
  if ( !result )
    return 0;
  if ( *(_DWORD *)a1 )
    return result;
  ProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64 = (__int64 (__fastcall *)(_QWORD))GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__();
  if ( ProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64 )
    return (WNDPROC)ProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64(*((_QWORD *)a1 + 1));
  else
    return 0;
}

```

## disassembly

```asm
0x14000d7f8  push    rbx
0x14000d7fa  sub     rsp, 20h
0x14000d7fe  mov     rbx, rcx
0x14000d801  test    rcx, rcx
0x14000d804  jz      short loc_14000D82C
0x14000d806  mov     rax, [rcx+8]
0x14000d80a  test    rax, rax
0x14000d80d  jz      short loc_14000D82C
0x14000d80f  cmp     dword ptr [rcx], 0
0x14000d812  jnz     short loc_14000D82E
0x14000d814  call    GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__
0x14000d819  test    rax, rax
0x14000d81c  jz      short loc_14000D82C
0x14000d81e  mov     rcx, [rbx+8]
0x14000d822  add     rsp, 20h
0x14000d826  pop     rbx
0x14000d827  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x14000d82c  xor     eax, eax
0x14000d82e  add     rsp, 20h
0x14000d832  pop     rbx
0x14000d833  retn
```
