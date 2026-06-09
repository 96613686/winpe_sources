# SecpUnloadVMList(void)

- ea: `0x1800102bc`
- end: `0x180010370`
- name: `?SecpUnloadVMList@@YAXXZ`
- size: `180`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c904`

## callees

- `0x1800102bc`
- `0x180023010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800102f6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800102f6`
- `ntdll!RtlEnterCriticalSection` at `0x1800102d2`
- `ntdll!RtlEnterCriticalSection` at `0x1800102d2`
- `ntdll!NtFreeVirtualMemory` at `0x18001035b`
- `ntdll!NtFreeVirtualMemory` at `0x18001035b`
- `ntdll!RtlDeleteCriticalSection` at `0x180010303`
- `ntdll!RtlDeleteCriticalSection` at `0x180010303`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001033b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001033b`

## pseudocode

```c
void SecpUnloadVMList(void)
{
  unsigned int i; // ebx
  PVOID *v1; // rdx
  PVOID v2; // rcx
  ULONG_PTR RegionSize; // [rsp+30h] [rbp+8h] BYREF

  RegionSize = 0;
  RtlEnterCriticalSection(&SecVMListLock);
  for ( i = 0; i < SecVMListElements; ++i )
  {
    v1 = (PVOID *)((char *)SecVMList + 16 * i);
    if ( *((_BYTE *)v1 + 8) )
    {
      v2 = *v1;
      if ( SecpLsaInprocDispatch )
        (*(void (__fastcall **)(PVOID))SecpLsaInprocDispatch)(v2);
      else
        LocalFree(v2);
    }
    else
    {
      RegionSize = 0;
      NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, v1, &RegionSize, 0x8000u);
    }
  }
  LocalFree(SecVMList);
  RtlLeaveCriticalSection(&SecVMListLock);
  RtlDeleteCriticalSection(&SecVMListLock);
}

```

## disassembly

```asm
0x1800102bc  push    rbx
0x1800102be  sub     rsp, 20h
0x1800102c2  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800102c9  mov     [rsp+28h+RegionSize], 0
0x1800102d2  call    cs:__imp_RtlEnterCriticalSection
0x1800102d8  xor     ebx, ebx
0x1800102da  cmp     cs:?SecVMListElements@@3KA, ebx; ulong SecVMListElements
0x1800102e0  ja      short loc_18001030F
0x1800102e2  mov     rcx, cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA; hMem
0x1800102e9  call    cs:__imp_LocalFree
0x1800102ef  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800102f6  call    cs:__imp_RtlLeaveCriticalSection
0x1800102fc  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180010303  call    cs:__imp_RtlDeleteCriticalSection
0x180010309  add     rsp, 20h
0x18001030d  pop     rbx
0x18001030e  retn
0x18001030f  mov     edx, ebx
0x180010311  shl     rdx, 4
0x180010315  add     rdx, cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA; BaseAddress
0x18001031c  cmp     byte ptr [rdx+8], 0
0x180010320  jz      short loc_180010343
0x180010322  mov     rax, cs:SecpLsaInprocDispatch
0x180010329  mov     rcx, [rdx]; hMem
0x18001032c  test    rax, rax
0x18001032f  jz      short loc_18001033B
0x180010331  mov     rax, [rax]
0x180010334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010339  jmp     short loc_180010361
0x18001033b  call    cs:__imp_LocalFree
0x180010341  jmp     short loc_180010361
0x180010343  mov     r9d, 8000h; FreeType
0x180010349  mov     [rsp+28h+RegionSize], 0
0x180010352  lea     r8, [rsp+28h+RegionSize]; RegionSize
0x180010357  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001035b  call    cs:__imp_NtFreeVirtualMemory
0x180010361  inc     ebx
0x180010363  cmp     ebx, cs:?SecVMListElements@@3KA; ulong SecVMListElements
0x180010369  jb      short loc_18001030F
0x18001036b  jmp     loc_1800102E2
```
