# DloadReleaseSectionWriteAccess(void)

- ea: `0x100424138`
- end: `0x1004241cb`
- name: `?DloadReleaseSectionWriteAccess@@YAXXZ`
- size: `147`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1004241e0`

## callees

- `0x100423ec0`
- `0x1004240a4`
- `0x100424138`
- `0x100424580`

## pseudocode

```c
void DloadReleaseSectionWriteAccess(void)
{
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

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
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
  if ( DloadGetSRWLockFunctionPointers() )
    ((void (__fastcall *)(unsigned __int64 *))DloadReleaseSRWLockExclusive)(&DloadSrwLock);
  else
    DloadSrwLock = 0;
}

```

## disassembly

```asm
0x100424138  sub     rsp, 28h
0x10042413c  test    cs:dword_10042DE10, 1000h
0x100424146  jz      short loc_1004241C6
0x100424148  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x10042414d  test    al, al
0x10042414f  jz      short loc_100424169
0x100424151  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x100424158  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x10042415f  call    cs:__guard_dispatch_icall_fptr
0x100424165  jmp     short loc_100424183
0x100424167  pause
0x100424169  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x100424170  test    rax, rax
0x100424173  jnz     short loc_100424167
0x100424175  lea     ecx, [rax+1]
0x100424178  lock cmpxchg cs:?DloadSrwLock@@3_KA, rcx; unsigned __int64 DloadSrwLock
0x100424181  jnz     short loc_100424169
0x100424183  add     cs:?DloadSectionLockCount@@3KA, 0FFFFFFFFh; ulong DloadSectionLockCount
0x10042418a  jnz     short loc_10042419C
0x10042418c  mov     ecx, cs:?DloadSectionOldProtection@@3KA; flNewProtect
0x100424192  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x100424197  call    ?DloadProtectSection@@YAXKPEAK@Z; DloadProtectSection(ulong,ulong *)
0x10042419c  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1004241a1  test    al, al
0x1004241a3  jz      short loc_1004241BB
0x1004241a5  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1004241ac  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1004241b3  call    cs:__guard_dispatch_icall_fptr
0x1004241b9  jmp     short loc_1004241C6
0x1004241bb  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x1004241c6  add     rsp, 28h
0x1004241ca  retn
```
