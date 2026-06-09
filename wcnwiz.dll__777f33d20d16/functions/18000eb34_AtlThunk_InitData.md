# AtlThunk_InitData

- ea: `0x18000eb34`
- end: `0x18000ebad`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000af30`
- `0x18000d070`

## callees

- `0x18000e7c8`
- `0x18000eb34`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000eb71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000eb71`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000eb83`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18000eb83`

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
0x18000eb34  test    rcx, rcx
0x18000eb37  jz      short locret_18000EBAC
0x18000eb39  push    rbx
0x18000eb3a  push    rbp
0x18000eb3b  push    rsi
0x18000eb3c  push    rdi
0x18000eb3d  sub     rsp, 28h
0x18000eb41  mov     rbx, [rcx+8]
0x18000eb45  mov     rsi, r8
0x18000eb48  mov     rbp, rdx
0x18000eb4b  mov     rdi, rcx
0x18000eb4e  test    rbx, rbx
0x18000eb51  jz      short loc_18000EBA4
0x18000eb53  cmp     dword ptr [rcx], 0
0x18000eb56  jz      short loc_18000EB8B
0x18000eb58  mov     word ptr [rbx], 0B948h
0x18000eb5d  mov     [rbx+2], r8
0x18000eb61  mov     word ptr [rbx+0Ah], 0B848h
0x18000eb67  mov     [rbx+0Ch], rdx
0x18000eb6b  mov     word ptr [rbx+14h], 0E0FFh
0x18000eb71  call    cs:__imp_GetCurrentProcess
0x18000eb77  mov     r8d, 16h; dwSize
0x18000eb7d  mov     rdx, rbx; lpBaseAddress
0x18000eb80  mov     rcx, rax; hProcess
0x18000eb83  call    cs:__imp_FlushInstructionCache
0x18000eb89  jmp     short loc_18000EBA4
0x18000eb8b  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x18000eb90  test    rax, rax
0x18000eb93  jz      short loc_18000EBA4
0x18000eb95  mov     rcx, [rdi+8]
0x18000eb99  mov     r8, rsi
0x18000eb9c  mov     rdx, rbp
0x18000eb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba4  add     rsp, 28h
0x18000eba8  pop     rdi
0x18000eba9  pop     rsi
0x18000ebaa  pop     rbp
0x18000ebab  pop     rbx
0x18000ebac  retn
```
