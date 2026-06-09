# AtlThunk_InitData

- ea: `0x180042d2c`
- end: `0x180042da5`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180014e4c`
- `0x180019920`
- `0x180019a38`

## callees

- `0x1800429c0`
- `0x180042d2c`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042d69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042d69`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180042d7b`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180042d7b`

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
0x180042d2c  test    rcx, rcx
0x180042d2f  jz      short locret_180042DA4
0x180042d31  push    rbx
0x180042d32  push    rbp
0x180042d33  push    rsi
0x180042d34  push    rdi
0x180042d35  sub     rsp, 28h
0x180042d39  mov     rbx, [rcx+8]
0x180042d3d  mov     rsi, r8
0x180042d40  mov     rbp, rdx
0x180042d43  mov     rdi, rcx
0x180042d46  test    rbx, rbx
0x180042d49  jz      short loc_180042D9C
0x180042d4b  cmp     dword ptr [rcx], 0
0x180042d4e  jz      short loc_180042D83
0x180042d50  mov     word ptr [rbx], 0B948h
0x180042d55  mov     [rbx+2], r8
0x180042d59  mov     word ptr [rbx+0Ah], 0B848h
0x180042d5f  mov     [rbx+0Ch], rdx
0x180042d63  mov     word ptr [rbx+14h], 0E0FFh
0x180042d69  call    cs:__imp_GetCurrentProcess
0x180042d6f  mov     r8d, 16h; dwSize
0x180042d75  mov     rdx, rbx; lpBaseAddress
0x180042d78  mov     rcx, rax; hProcess
0x180042d7b  call    cs:__imp_FlushInstructionCache
0x180042d81  jmp     short loc_180042D9C
0x180042d83  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x180042d88  test    rax, rax
0x180042d8b  jz      short loc_180042D9C
0x180042d8d  mov     rcx, [rdi+8]
0x180042d91  mov     r8, rsi
0x180042d94  mov     rdx, rbp
0x180042d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d9c  add     rsp, 28h
0x180042da0  pop     rdi
0x180042da1  pop     rsi
0x180042da2  pop     rbp
0x180042da3  pop     rbx
0x180042da4  retn
```
