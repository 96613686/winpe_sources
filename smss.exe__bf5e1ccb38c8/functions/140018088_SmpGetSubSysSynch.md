# SmpGetSubSysSynch

- ea: `0x140018088`
- end: `0x14001814e`
- name: `SmpGetSubSysSynch`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003390`
- `0x140018154`

## callees

- `0x140018088`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400180f7`
- `ntdll!RtlAllocateHeap` at `0x1400180f7`
- `ntdll!RtlFreeHeap` at `0x140018135`
- `ntdll!RtlFreeHeap` at `0x140018135`
- `ntdll!NtCreateEvent` at `0x140018119`
- `ntdll!NtCreateEvent` at `0x140018119`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400180a1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400180a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400180cd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400180cd`

## pseudocode

```c
_DWORD *SmpGetSubSysSynch()
{
  _DWORD *v0; // rbx
  PVOID Heap; // rax

  if ( SmpSubSysSynchCache )
  {
    v0 = 0;
    RtlAcquireSRWLockExclusive(&SmpSubSysSynchLock);
    if ( SmpSubSysSynchCache )
    {
      --SmpSubSysSynchCacheSize;
      v0 = (_DWORD *)SmpSubSysSynchCache;
      SmpSubSysSynchCache = *(_QWORD *)SmpSubSysSynchCache;
    }
    RtlReleaseSRWLockExclusive(&SmpSubSysSynchLock);
    if ( v0 )
      goto LABEL_8;
  }
  Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag + 0x80000, 0x10u);
  v0 = Heap;
  if ( Heap )
  {
    if ( NtCreateEvent((PHANDLE)Heap + 1, 0x100002u, 0, NotificationEvent, 0) < 0 )
    {
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v0);
      return 0;
    }
LABEL_8:
    *v0 = 0;
  }
  return v0;
}

```

## disassembly

```asm
0x140018088  push    rbx
0x14001808a  sub     rsp, 30h
0x14001808e  cmp     cs:SmpSubSysSynchCache, 0
0x140018096  jz      short loc_1400180D8
0x140018098  lea     rcx, SmpSubSysSynchLock
0x14001809f  xor     ebx, ebx
0x1400180a1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400180a7  mov     rax, cs:SmpSubSysSynchCache
0x1400180ae  test    rax, rax
0x1400180b1  jz      short loc_1400180C6
0x1400180b3  dec     cs:SmpSubSysSynchCacheSize
0x1400180b9  mov     rbx, rax
0x1400180bc  mov     rax, [rax]
0x1400180bf  mov     cs:SmpSubSysSynchCache, rax
0x1400180c6  lea     rcx, SmpSubSysSynchLock
0x1400180cd  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400180d3  test    rbx, rbx
0x1400180d6  jnz     short loc_14001813F
0x1400180d8  mov     rcx, gs:60h
0x1400180e1  mov     r8d, 10h; Size
0x1400180e7  mov     edx, cs:SmBaseTag
0x1400180ed  add     edx, 80000h; Flags
0x1400180f3  mov     rcx, [rcx+30h]; HeapHandle
0x1400180f7  call    cs:__imp_RtlAllocateHeap
0x1400180fd  mov     rbx, rax
0x140018100  test    rax, rax
0x140018103  jz      short loc_140018145
0x140018105  lea     rcx, [rax+8]; EventHandle
0x140018109  mov     [rsp+38h+InitialState], 0; InitialState
0x14001810e  xor     r9d, r9d; EventType
0x140018111  xor     r8d, r8d; ObjectAttributes
0x140018114  mov     edx, 100002h; DesiredAccess
0x140018119  call    cs:__imp_NtCreateEvent
0x14001811f  test    eax, eax
0x140018121  jns     short loc_14001813F
0x140018123  mov     rcx, gs:60h
0x14001812c  mov     r8, rbx; BaseAddress
0x14001812f  xor     edx, edx; Flags
0x140018131  mov     rcx, [rcx+30h]; HeapHandle
0x140018135  call    cs:__imp_RtlFreeHeap
0x14001813b  xor     ebx, ebx
0x14001813d  jmp     short loc_140018145
0x14001813f  mov     dword ptr [rbx], 0
0x140018145  mov     rax, rbx
0x140018148  add     rsp, 30h
0x14001814c  pop     rbx
0x14001814d  retn
```
