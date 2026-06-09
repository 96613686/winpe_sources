# UbpmpReleaseJobBackgroundMode

- ea: `0x18001f8cc`
- end: `0x18001f945`
- name: `UbpmpReleaseJobBackgroundMode`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001f8c0`
- `0x180032b50`

## callees

- `0x18001f8cc`
- `0x18001f94c`
- `0x18002046c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f8e2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f8e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f928`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f928`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f8e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f8e8`

## pseudocode

```c
__int64 __fastcall UbpmpReleaseJobBackgroundMode(__int64 a1)
{
  unsigned int v2; // edi

  v2 = 0;
  RtlAcquireSRWLockExclusive(&g_TaskHostJobObjectLock);
  dword_18004CF88 = GetCurrentThreadId();
  if ( *(_DWORD *)(a1 + 4) )
  {
    if ( *(_DWORD *)(a1 + 4) != 1 )
    {
LABEL_5:
      --*(_DWORD *)(a1 + 4);
      goto LABEL_6;
    }
    v2 = UbpmpSetJobBackgroundMode(*(HANDLE *)(a1 + 24));
    if ( !v2 )
    {
      if ( !*(_DWORD *)a1 )
      {
        DestroyJobObjectContext(a1);
        goto LABEL_6;
      }
      goto LABEL_5;
    }
  }
LABEL_6:
  dword_18004CF88 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostJobObjectLock);
  return v2;
}

```

## disassembly

```asm
0x18001f8cc  mov     [rsp+arg_0], rbx
0x18001f8d1  push    rdi
0x18001f8d2  sub     rsp, 20h
0x18001f8d6  mov     rbx, rcx
0x18001f8d9  xor     edi, edi
0x18001f8db  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x18001f8e2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001f8e8  call    cs:__imp_GetCurrentThreadId
0x18001f8ee  mov     cs:dword_18004CF88, eax
0x18001f8f4  cmp     [rbx+4], edi
0x18001f8f7  jz      short loc_18001F917
0x18001f8f9  cmp     dword ptr [rbx+4], 1
0x18001f8fd  jnz     short loc_18001F914
0x18001f8ff  mov     rcx, [rbx+18h]; hJob
0x18001f903  xor     edx, edx
0x18001f905  call    UbpmpSetJobBackgroundMode
0x18001f90a  mov     edi, eax
0x18001f90c  test    eax, eax
0x18001f90e  jnz     short loc_18001F917
0x18001f910  cmp     [rbx], eax
0x18001f912  jz      short loc_18001F93B
0x18001f914  dec     dword ptr [rbx+4]
0x18001f917  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x18001f91e  mov     cs:dword_18004CF88, 0
0x18001f928  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001f92e  mov     rbx, [rsp+28h+arg_0]
0x18001f933  mov     eax, edi
0x18001f935  add     rsp, 20h
0x18001f939  pop     rdi
0x18001f93a  retn
0x18001f93b  mov     rcx, rbx
0x18001f93e  call    DestroyJobObjectContext
0x18001f943  jmp     short loc_18001F917
```
