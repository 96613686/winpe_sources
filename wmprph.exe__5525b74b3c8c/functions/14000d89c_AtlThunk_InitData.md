# AtlThunk_InitData

- ea: `0x14000d89c`
- end: `0x14000d915`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400032cc`
- `0x140008980`
- `0x140008a74`

## callees

- `0x14000d548`
- `0x14000d89c`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x14000d8d9`
- `KERNEL32!GetCurrentProcess` at `0x14000d8d9`
- `KERNEL32!FlushInstructionCache` at `0x14000d8eb`
- `KERNEL32!FlushInstructionCache` at `0x14000d8eb`

## pseudocode

```c
void __stdcall AtlThunk_InitData(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)
{
  char *v3; // rbx
  HANDLE CurrentProcess; // rax
  void (__fastcall *ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64)(_QWORD, void *, size_t); // rax

  if ( Thunk )
  {
    v3 = (char *)*((_QWORD *)Thunk + 1);
    if ( v3 )
    {
      if ( *(_DWORD *)Thunk )
      {
        *(_WORD *)v3 = -18104;
        *(_QWORD *)(v3 + 2) = FirstParameter;
        *((_WORD *)v3 + 5) = -18360;
        *(_QWORD *)(v3 + 12) = Proc;
        *((_WORD *)v3 + 10) = -7937;
        CurrentProcess = GetCurrentProcess();
        FlushInstructionCache(CurrentProcess, v3, 0x16u);
      }
      else
      {
        ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64 = (void (__fastcall *)(_QWORD, void *, size_t))GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__();
        if ( ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64 )
          ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64(
            *((_QWORD *)Thunk + 1),
            Proc,
            FirstParameter);
      }
    }
  }
}

```

## disassembly

```asm
0x14000d89c  test    rcx, rcx
0x14000d89f  jz      short locret_14000D914
0x14000d8a1  push    rbx
0x14000d8a2  push    rbp
0x14000d8a3  push    rsi
0x14000d8a4  push    rdi
0x14000d8a5  sub     rsp, 28h
0x14000d8a9  mov     rbx, [rcx+8]
0x14000d8ad  mov     rsi, r8
0x14000d8b0  mov     rbp, rdx
0x14000d8b3  mov     rdi, rcx
0x14000d8b6  test    rbx, rbx
0x14000d8b9  jz      short loc_14000D90C
0x14000d8bb  cmp     dword ptr [rcx], 0
0x14000d8be  jz      short loc_14000D8F3
0x14000d8c0  mov     word ptr [rbx], 0B948h
0x14000d8c5  mov     [rbx+2], r8
0x14000d8c9  mov     word ptr [rbx+0Ah], 0B848h
0x14000d8cf  mov     [rbx+0Ch], rdx
0x14000d8d3  mov     word ptr [rbx+14h], 0E0FFh
0x14000d8d9  call    cs:__imp_GetCurrentProcess
0x14000d8df  mov     r8d, 16h; dwSize
0x14000d8e5  mov     rdx, rbx; lpBaseAddress
0x14000d8e8  mov     rcx, rax; hProcess
0x14000d8eb  call    cs:__imp_FlushInstructionCache
0x14000d8f1  jmp     short loc_14000D90C
0x14000d8f3  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x14000d8f8  test    rax, rax
0x14000d8fb  jz      short loc_14000D90C
0x14000d8fd  mov     rcx, [rdi+8]
0x14000d901  mov     r8, rsi
0x14000d904  mov     rdx, rbp
0x14000d907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d90c  add     rsp, 28h
0x14000d910  pop     rdi
0x14000d911  pop     rsi
0x14000d912  pop     rbp
0x14000d913  pop     rbx
0x14000d914  retn
```
