# AtlThunk_AllocateData

- ea: `0x14000d780`
- end: `0x14000d7f2`
- name: `AtlThunk_AllocateData`
- size: `114`
- prototype: `AtlThunkData_t *__stdcall()`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400032cc`
- `0x140008980`
- `0x140008a74`

## callees

- `0x14000d350`
- `0x14000d644`
- `0x14000d780`
- `0x14000f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000d7e1`
- `KERNEL32!HeapFree` at `0x14000d7e1`
- `KERNEL32!HeapAlloc` at `0x14000d798`
- `KERNEL32!HeapAlloc` at `0x14000d798`
- `KERNEL32!GetProcessHeap` at `0x14000d786`
- `KERNEL32!GetProcessHeap` at `0x14000d7d3`
- `KERNEL32!GetProcessHeap` at `0x14000d786`
- `KERNEL32!GetProcessHeap` at `0x14000d7d3`

## pseudocode

```c
AtlThunkData_t *__stdcall AtlThunk_AllocateData()
{
  HANDLE ProcessHeap; // rax
  _QWORD *v1; // rbx
  __int64 (*ProcAddressAll_AtlThunkData_t______cdecl___void)(void); // rax
  PSLIST_ENTRY v4; // rax
  HANDLE v5; // rax

  ProcessHeap = GetProcessHeap();
  v1 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v1 )
    return 0;
  ProcAddressAll_AtlThunkData_t______cdecl___void = (__int64 (*)(void))GetProcAddressAll_AtlThunkData_t______cdecl___void__();
  *(_DWORD *)v1 = ProcAddressAll_AtlThunkData_t______cdecl___void == 0;
  if ( ProcAddressAll_AtlThunkData_t______cdecl___void )
    v4 = (PSLIST_ENTRY)ProcAddressAll_AtlThunkData_t______cdecl___void();
  else
    v4 = __AllocStdCallThunk_cmn();
  v1[1] = v4;
  if ( !v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v1);
    return 0;
  }
  return (AtlThunkData_t *)v1;
}

```

## disassembly

```asm
0x14000d780  push    rbx
0x14000d782  sub     rsp, 20h
0x14000d786  call    cs:__imp_GetProcessHeap
0x14000d78c  mov     edx, 8; dwFlags
0x14000d791  mov     rcx, rax; hHeap
0x14000d794  lea     r8d, [rdx+8]; dwBytes
0x14000d798  call    cs:__imp_HeapAlloc
0x14000d79e  mov     rbx, rax
0x14000d7a1  test    rax, rax
0x14000d7a4  jnz     short loc_14000D7AA
0x14000d7a6  xor     eax, eax
0x14000d7a8  jmp     short loc_14000D7EC
0x14000d7aa  call    GetProcAddressAll_AtlThunkData_t______cdecl___void__
0x14000d7af  xor     ecx, ecx
0x14000d7b1  test    rax, rax
0x14000d7b4  setz    cl
0x14000d7b7  mov     [rbx], ecx
0x14000d7b9  test    rax, rax
0x14000d7bc  jz      short loc_14000D7C5
0x14000d7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7c3  jmp     short loc_14000D7CA
0x14000d7c5  call    ?__AllocStdCallThunk_cmn@@YAPEAXXZ; __AllocStdCallThunk_cmn(void)
0x14000d7ca  mov     [rbx+8], rax
0x14000d7ce  test    rax, rax
0x14000d7d1  jnz     short loc_14000D7E9
0x14000d7d3  call    cs:__imp_GetProcessHeap
0x14000d7d9  mov     r8, rbx; lpMem
0x14000d7dc  xor     edx, edx; dwFlags
0x14000d7de  mov     rcx, rax; hHeap
0x14000d7e1  call    cs:__imp_HeapFree
0x14000d7e7  jmp     short loc_14000D7A6
0x14000d7e9  mov     rax, rbx
0x14000d7ec  add     rsp, 20h
0x14000d7f0  pop     rbx
0x14000d7f1  retn
```
