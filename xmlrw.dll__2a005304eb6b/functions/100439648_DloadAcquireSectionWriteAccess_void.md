# DloadAcquireSectionWriteAccess(void)

- ea: `0x100439648`
- end: `0x1004396f2`
- name: `?DloadAcquireSectionWriteAccess@@YAXXZ`
- size: `170`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100439a10`

## callees

- `0x100439648`
- `0x1004396f8`
- `0x1004398dc`
- `0x100439df0`

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
0x100439648  push    rbx
0x10043964a  sub     rsp, 20h
0x10043964e  test    cs:dword_100444E80, 1000h
0x100439658  jz      loc_1004396EC
0x10043965e  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x100439663  mov     ebx, 1
0x100439668  test    al, al
0x10043966a  jz      short loc_100439684
0x10043966c  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x100439673  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x10043967a  call    cs:__guard_dispatch_icall_fptr
0x100439680  jmp     short loc_10043969B
0x100439682  pause
0x100439684  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x10043968b  test    rax, rax
0x10043968e  jnz     short loc_100439682
0x100439690  lock cmpxchg cs:?DloadSrwLock@@3_KA, rbx; unsigned __int64 DloadSrwLock
0x100439699  jnz     short loc_100439684
0x10043969b  mov     eax, cs:?DloadSectionLockCount@@3KA; ulong DloadSectionLockCount
0x1004396a1  add     eax, ebx
0x1004396a3  mov     cs:?DloadSectionLockCount@@3KA, eax; ulong DloadSectionLockCount
0x1004396a9  cmp     eax, ebx
0x1004396ab  jnz     short loc_1004396BE
0x1004396ad  lea     rdx, ?DloadSectionOldProtection@@3KA; lpflOldProtect
0x1004396b4  mov     ecx, 4; flNewProtect
0x1004396b9  call    ?DloadProtectSection@@YAXKPEAK@Z; DloadProtectSection(ulong,ulong *)
0x1004396be  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1004396c3  test    al, al
0x1004396c5  jz      short loc_1004396E1
0x1004396c7  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1004396ce  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1004396d5  add     rsp, 20h
0x1004396d9  pop     rbx
0x1004396da  jmp     cs:__guard_dispatch_icall_fptr
0x1004396e1  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x1004396ec  add     rsp, 20h
0x1004396f0  pop     rbx
0x1004396f1  retn
```
