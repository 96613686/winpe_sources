# DloadReleaseSectionWriteAccess(void)

- ea: `0x100439970`
- end: `0x100439a03`
- name: `?DloadReleaseSectionWriteAccess@@YAXXZ`
- size: `147`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100439a10`

## callees

- `0x1004396f8`
- `0x1004398dc`
- `0x100439970`
- `0x100439df0`

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
0x100439970  sub     rsp, 28h
0x100439974  test    cs:dword_100444E80, 1000h
0x10043997e  jz      short loc_1004399FE
0x100439980  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x100439985  test    al, al
0x100439987  jz      short loc_1004399A1
0x100439989  mov     rax, cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x100439990  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x100439997  call    cs:__guard_dispatch_icall_fptr
0x10043999d  jmp     short loc_1004399BB
0x10043999f  pause
0x1004399a1  mov     rax, cs:?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1004399a8  test    rax, rax
0x1004399ab  jnz     short loc_10043999F
0x1004399ad  lea     ecx, [rax+1]
0x1004399b0  lock cmpxchg cs:?DloadSrwLock@@3_KA, rcx; unsigned __int64 DloadSrwLock
0x1004399b9  jnz     short loc_1004399A1
0x1004399bb  add     cs:?DloadSectionLockCount@@3KA, 0FFFFFFFFh; ulong DloadSectionLockCount
0x1004399c2  jnz     short loc_1004399D4
0x1004399c4  mov     ecx, cs:?DloadSectionOldProtection@@3KA; flNewProtect
0x1004399ca  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x1004399cf  call    ?DloadProtectSection@@YAXKPEAK@Z; DloadProtectSection(ulong,ulong *)
0x1004399d4  call    ?DloadGetSRWLockFunctionPointers@@YAEXZ; DloadGetSRWLockFunctionPointers(void)
0x1004399d9  test    al, al
0x1004399db  jz      short loc_1004399F3
0x1004399dd  mov     rax, cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x1004399e4  lea     rcx, ?DloadSrwLock@@3_KA; unsigned __int64 DloadSrwLock
0x1004399eb  call    cs:__guard_dispatch_icall_fptr
0x1004399f1  jmp     short loc_1004399FE
0x1004399f3  mov     cs:?DloadSrwLock@@3_KA, 0; unsigned __int64 DloadSrwLock
0x1004399fe  add     rsp, 28h
0x100439a02  retn
```
