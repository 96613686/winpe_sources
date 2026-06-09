# DloadAcquireSectionWriteAccess(void)

- ea: `0x100423e10`
- end: `0x100423eba`
- name: `?DloadAcquireSectionWriteAccess@@YAXXZ`
- size: `170`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1004241e0`

## callees

- `0x100423e10`
- `0x100423ec0`
- `0x1004240a4`
- `0x100424580`

## pseudocode

```c
void DloadAcquireSectionWriteAccess(void)
{
  if ( DloadGetSRWLockFunctionPointers() )
  {
    ((void (__fastcall *)(unsigned __int64 *))DloadAcquireSRWLockExclusive)(&DloadSrwLock);
  }
  else
  {
    do
    {
      while ( DloadSrwLock )
        _mm_pause();
    }
    while ( _InterlockedCompareExchange64((volatile signed __int64 *)&DloadSrwLock, 1, 0) );
  }
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  if ( DloadGetSRWLockFunctionPointers() )
    ((void (__fastcall *)(unsigned __int64 *))DloadReleaseSRWLockExclusive)(&DloadSrwLock);
  else
    DloadSrwLock = 0;
}

```

## disassembly

```asm
0x100423e10  push    rbx
0x100423e12  sub     rsp, 20h
0x100423e16  test    cs:dword_10042DE10, 1000h
0x100423e20  jz      loc_100423EB4
0x100423e26  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x100423e2b  mov     ebx, 1
0x100423e30  test    al, al
0x100423e32  jz      short loc_100423E4C
0x100423e34  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x100423e3b  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x100423e42  call    cs:__guard_dispatch_icall_fptr
0x100423e48  jmp     short loc_100423E63
0x100423e4a  pause
0x100423e4c  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x100423e53  test    rax, rax
0x100423e56  jnz     short loc_100423E4A
0x100423e58  lock cmpxchg cs:?DloadSrwLock@@3_KA, rbx; unsigned __int64 DloadSrwLock
0x100423e61  jnz     short loc_100423E4C
0x100423e63  mov     eax, cs:?DloadSectionLockCount@@3KA; ulong DloadSectionLockCount
0x100423e69  add     eax, ebx
0x100423e6b  mov     cs:?DloadSectionLockCount@@3KA, eax; ulong DloadSectionLockCount
0x100423e71  cmp     eax, ebx
0x100423e73  jnz     short loc_100423E86
0x100423e75  lea     rdx, ?DloadSectionOldProtection@@3KA; lpflOldProtect
0x100423e7c  mov     ecx, 4; flNewProtect
0x100423e81  call    ?DloadProtectSection@@YAXKPEAK@Z; DloadProtectSection(ulong,ulong *)
0x100423e86  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x100423e8b  test    al, al
0x100423e8d  jz      short loc_100423EA9
0x100423e8f  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x100423e96  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x100423e9d  add     rsp, 20h
0x100423ea1  pop     rbx
0x100423ea2  jmp     cs:__guard_dispatch_icall_fptr
0x100423ea9  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x100423eb4  add     rsp, 20h
0x100423eb8  pop     rbx
0x100423eb9  retn
```
