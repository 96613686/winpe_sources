# AtlThunk_InitData

- ea: `0x180026df4`
- end: `0x180026e6d`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180009090`
- `0x18000baa0`
- `0x18000dd64`
- `0x18000de44`
- `0x18000df24`
- `0x180020030`
- `0x1800247f0`

## callees

- `0x180026a88`
- `0x180026df4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026e31`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180026e43`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180026e43`

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
0x180026df4  test    rcx, rcx
0x180026df7  jz      short locret_180026E6C
0x180026df9  push    rbx
0x180026dfa  push    rbp
0x180026dfb  push    rsi
0x180026dfc  push    rdi
0x180026dfd  sub     rsp, 28h
0x180026e01  mov     rbx, [rcx+8]
0x180026e05  mov     rsi, r8
0x180026e08  mov     rbp, rdx
0x180026e0b  mov     rdi, rcx
0x180026e0e  test    rbx, rbx
0x180026e11  jz      short loc_180026E64
0x180026e13  cmp     dword ptr [rcx], 0
0x180026e16  jz      short loc_180026E4B
0x180026e18  mov     word ptr [rbx], 0B948h
0x180026e1d  mov     [rbx+2], r8
0x180026e21  mov     word ptr [rbx+0Ah], 0B848h
0x180026e27  mov     [rbx+0Ch], rdx
0x180026e2b  mov     word ptr [rbx+14h], 0E0FFh
0x180026e31  call    cs:__imp_GetCurrentProcess
0x180026e37  mov     r8d, 16h; dwSize
0x180026e3d  mov     rdx, rbx; lpBaseAddress
0x180026e40  mov     rcx, rax; hProcess
0x180026e43  call    cs:__imp_FlushInstructionCache
0x180026e49  jmp     short loc_180026E64
0x180026e4b  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x180026e50  test    rax, rax
0x180026e53  jz      short loc_180026E64
0x180026e55  mov     rcx, [rdi+8]
0x180026e59  mov     r8, rsi
0x180026e5c  mov     rdx, rbp
0x180026e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e64  add     rsp, 28h
0x180026e68  pop     rdi
0x180026e69  pop     rsi
0x180026e6a  pop     rbp
0x180026e6b  pop     rbx
0x180026e6c  retn
```
