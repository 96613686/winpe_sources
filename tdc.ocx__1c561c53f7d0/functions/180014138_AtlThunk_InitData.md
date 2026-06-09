# AtlThunk_InitData

- ea: `0x180014138`
- end: `0x1800141b1`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800044b0`
- `0x180009360`

## callees

- `0x180013de4`
- `0x180014138`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180014175`
- `KERNEL32!GetCurrentProcess` at `0x180014175`
- `KERNEL32!FlushInstructionCache` at `0x180014187`
- `KERNEL32!FlushInstructionCache` at `0x180014187`

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
0x180014138  test    rcx, rcx
0x18001413b  jz      short locret_1800141B0
0x18001413d  push    rbx
0x18001413e  push    rbp
0x18001413f  push    rsi
0x180014140  push    rdi
0x180014141  sub     rsp, 28h
0x180014145  mov     rbx, [rcx+8]
0x180014149  mov     rsi, r8
0x18001414c  mov     rbp, rdx
0x18001414f  mov     rdi, rcx
0x180014152  test    rbx, rbx
0x180014155  jz      short loc_1800141A8
0x180014157  cmp     dword ptr [rcx], 0
0x18001415a  jz      short loc_18001418F
0x18001415c  mov     word ptr [rbx], 0B948h
0x180014161  mov     [rbx+2], r8
0x180014165  mov     word ptr [rbx+0Ah], 0B848h
0x18001416b  mov     [rbx+0Ch], rdx
0x18001416f  mov     word ptr [rbx+14h], 0E0FFh
0x180014175  call    cs:__imp_GetCurrentProcess
0x18001417b  mov     r8d, 16h; dwSize
0x180014181  mov     rdx, rbx; lpBaseAddress
0x180014184  mov     rcx, rax; hProcess
0x180014187  call    cs:__imp_FlushInstructionCache
0x18001418d  jmp     short loc_1800141A8
0x18001418f  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x180014194  test    rax, rax
0x180014197  jz      short loc_1800141A8
0x180014199  mov     rcx, [rdi+8]
0x18001419d  mov     r8, rsi
0x1800141a0  mov     rdx, rbp
0x1800141a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a8  add     rsp, 28h
0x1800141ac  pop     rdi
0x1800141ad  pop     rsi
0x1800141ae  pop     rbp
0x1800141af  pop     rbx
0x1800141b0  retn
```
