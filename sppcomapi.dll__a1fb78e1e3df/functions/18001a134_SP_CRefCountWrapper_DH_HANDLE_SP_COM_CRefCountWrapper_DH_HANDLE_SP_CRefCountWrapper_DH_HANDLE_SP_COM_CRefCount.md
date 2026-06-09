# SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)

- ea: `0x18001a134`
- end: `0x18001a1a5`
- name: `??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a404`
- `0x180036fc4`
- `0x180037288`
- `0x180038f90`
- `0x18003a240`

## callees

- `0x18001a134`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a172`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a186`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a15e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a15e`

## pseudocode

```c
void __fastcall SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v3; // rcx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      v3 = (void *)v1[1];
      if ( v3 )
      {
        CloseHandle(v3);
        v1[1] = 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001a134  mov     [rsp+arg_0], rbx
0x18001a139  push    rdi
0x18001a13a  sub     rsp, 20h
0x18001a13e  mov     rbx, [rcx]
0x18001a141  mov     rdi, rcx
0x18001a144  test    rbx, rbx
0x18001a147  jz      short loc_18001A199
0x18001a149  or      eax, 0FFFFFFFFh
0x18001a14c  lock xadd [rbx], eax
0x18001a150  cmp     eax, 1
0x18001a153  jnz     short loc_18001A192
0x18001a155  mov     rcx, [rbx+8]; hObject
0x18001a159  test    rcx, rcx
0x18001a15c  jz      short loc_18001A172
0x18001a15e  call    cs:__imp_CloseHandle
0x18001a165  nop     dword ptr [rax+rax+00h]
0x18001a16a  mov     qword ptr [rbx+8], 0
0x18001a172  call    cs:__imp_GetProcessHeap
0x18001a179  nop     dword ptr [rax+rax+00h]
0x18001a17e  mov     r8, rbx; lpMem
0x18001a181  xor     edx, edx; dwFlags
0x18001a183  mov     rcx, rax; hHeap
0x18001a186  call    cs:__imp_HeapFree
0x18001a18d  nop     dword ptr [rax+rax+00h]
0x18001a192  mov     qword ptr [rdi], 0
0x18001a199  mov     rbx, [rsp+28h+arg_0]
0x18001a19e  add     rsp, 20h
0x18001a1a2  pop     rdi
0x18001a1a3  retn
```
