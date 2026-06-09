# SmpDisposeSubSysSynch

- ea: `0x140017ff0`
- end: `0x140018081`
- name: `SmpDisposeSubSysSynch`
- size: `145`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400011b0`
- `0x140001e40`
- `0x140002bb0`
- `0x14000b8f0`
- `0x140018154`

## callees

- `0x140017ff0`

## import_xrefs

- `ntdll!NtClose` at `0x14001805d`
- `ntdll!NtClose` at `0x14001805d`
- `ntdll!RtlFreeHeap` at `0x140018075`
- `ntdll!RtlFreeHeap` at `0x140018075`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001801b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001801b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001804e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001804e`
- `ntdll!NtClearEvent` at `0x14001800e`
- `ntdll!NtClearEvent` at `0x14001800e`

## pseudocode

```c
void __fastcall SmpDisposeSubSysSynch(HANDLE *BaseAddress)
{
  HANDLE *v1; // rbx

  if ( BaseAddress )
  {
    v1 = BaseAddress;
    if ( (unsigned int)SmpSubSysSynchCacheSize >= 0x10 )
      goto LABEL_6;
    NtClearEvent(BaseAddress[1]);
    RtlAcquireSRWLockExclusive(&SmpSubSysSynchLock);
    if ( (unsigned int)SmpSubSysSynchCacheSize < 0x10 )
    {
      ++SmpSubSysSynchCacheSize;
      *v1 = (HANDLE)SmpSubSysSynchCache;
      SmpSubSysSynchCache = (__int64)v1;
      v1 = 0;
    }
    RtlReleaseSRWLockExclusive(&SmpSubSysSynchLock);
    if ( v1 )
    {
LABEL_6:
      NtClose(v1[1]);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v1);
    }
  }
}

```

## disassembly

```asm
0x140017ff0  test    rcx, rcx
0x140017ff3  jz      locret_140018080
0x140017ff9  push    rbx
0x140017ffa  sub     rsp, 20h
0x140017ffe  cmp     cs:SmpSubSysSynchCacheSize, 10h
0x140018005  mov     rbx, rcx
0x140018008  jnb     short loc_140018059
0x14001800a  mov     rcx, [rcx+8]; EventHandle
0x14001800e  call    cs:__imp_NtClearEvent
0x140018014  lea     rcx, SmpSubSysSynchLock
0x14001801b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140018021  mov     eax, cs:SmpSubSysSynchCacheSize
0x140018027  cmp     eax, 10h
0x14001802a  jnb     short loc_140018047
0x14001802c  inc     eax
0x14001802e  mov     cs:SmpSubSysSynchCacheSize, eax
0x140018034  mov     rax, cs:SmpSubSysSynchCache
0x14001803b  mov     [rbx], rax
0x14001803e  mov     cs:SmpSubSysSynchCache, rbx
0x140018045  xor     ebx, ebx
0x140018047  lea     rcx, SmpSubSysSynchLock
0x14001804e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140018054  test    rbx, rbx
0x140018057  jz      short loc_14001807B
0x140018059  mov     rcx, [rbx+8]; Handle
0x14001805d  call    cs:__imp_NtClose
0x140018063  mov     rcx, gs:60h
0x14001806c  mov     r8, rbx; BaseAddress
0x14001806f  xor     edx, edx; Flags
0x140018071  mov     rcx, [rcx+30h]; HeapHandle
0x140018075  call    cs:__imp_RtlFreeHeap
0x14001807b  add     rsp, 20h
0x14001807f  pop     rbx
0x140018080  retn
```
