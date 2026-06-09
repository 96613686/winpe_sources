# AtlThunk_FreeData

- ea: `0x14000d83c`
- end: `0x14000d893`
- name: `AtlThunk_FreeData`
- size: `87`
- prototype: `void __stdcall(AtlThunkData_t *Thunk)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002080`
- `0x140002108`
- `0x140002238`

## callees

- `0x14000d44c`
- `0x14000d83c`
- `0x14000f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000d887`
- `KERNEL32!HeapFree` at `0x14000d887`
- `KERNEL32!GetProcessHeap` at `0x14000d879`
- `KERNEL32!GetProcessHeap` at `0x14000d879`
- `KERNEL32!InterlockedPushEntrySList` at `0x14000d85e`
- `KERNEL32!InterlockedPushEntrySList` at `0x14000d85e`

## pseudocode

```c
void __stdcall AtlThunk_FreeData(AtlThunkData_t *Thunk)
{
  struct _SLIST_ENTRY *v1; // rdx
  void (__fastcall *ProcAddressAll_void____cdecl___AtlThunkData_t)(_QWORD); // rax
  HANDLE ProcessHeap; // rax

  if ( Thunk )
  {
    v1 = (struct _SLIST_ENTRY *)*((_QWORD *)Thunk + 1);
    if ( v1 )
    {
      if ( *(_DWORD *)Thunk )
      {
        InterlockedPushEntrySList(__AtlThunkPool, v1);
      }
      else
      {
        ProcAddressAll_void____cdecl___AtlThunkData_t = (void (__fastcall *)(_QWORD))GetProcAddressAll_void____cdecl___AtlThunkData_t____();
        if ( ProcAddressAll_void____cdecl___AtlThunkData_t )
          ProcAddressAll_void____cdecl___AtlThunkData_t(*((_QWORD *)Thunk + 1));
      }
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, Thunk);
  }
}

```

## disassembly

```asm
0x14000d83c  test    rcx, rcx
0x14000d83f  jz      short locret_14000D892
0x14000d841  push    rbx
0x14000d842  sub     rsp, 20h
0x14000d846  mov     rdx, [rcx+8]; ListEntry
0x14000d84a  mov     rbx, rcx
0x14000d84d  test    rdx, rdx
0x14000d850  jz      short loc_14000D879
0x14000d852  cmp     dword ptr [rcx], 0
0x14000d855  jz      short loc_14000D866
0x14000d857  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000d85e  call    cs:__imp_InterlockedPushEntrySList
0x14000d864  jmp     short loc_14000D879
0x14000d866  call    GetProcAddressAll_void____cdecl___AtlThunkData_t____
0x14000d86b  test    rax, rax
0x14000d86e  jz      short loc_14000D879
0x14000d870  mov     rcx, [rbx+8]
0x14000d874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d879  call    cs:__imp_GetProcessHeap
0x14000d87f  mov     r8, rbx; lpMem
0x14000d882  xor     edx, edx; dwFlags
0x14000d884  mov     rcx, rax; hHeap
0x14000d887  call    cs:__imp_HeapFree
0x14000d88d  add     rsp, 20h
0x14000d891  pop     rbx
0x14000d892  retn
```
