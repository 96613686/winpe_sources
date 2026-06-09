# WaitForExclusiveLineClientAccess

- ea: `0x18001f5ac`
- end: `0x18001f618`
- name: `WaitForExclusiveLineClientAccess`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005378`
- `0x180012a90`
- `0x180015f70`
- `0x180016290`
- `0x18001c114`
- `0x1800330a8`

## callees

- `0x18001f5ac`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f605`
- `KERNEL32!LeaveCriticalSection` at `0x18001f605`
- `KERNEL32!EnterCriticalSection` at `0x18001f5d8`
- `KERNEL32!EnterCriticalSection` at `0x18001f5d8`

## pseudocode

```c
__int64 __fastcall WaitForExclusiveLineClientAccess(unsigned __int64 a1)
{
  unsigned __int64 v2; // rdi

  v2 = a1 >> 4;
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  if ( *(_DWORD *)a1 == 1229734732 )
    return 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v2 & gdwPointerToLockTableIndexBits));
  return 0;
}

```

## disassembly

```asm
0x18001f5ac  mov     [rsp+arg_0], rbx
0x18001f5b1  push    rdi
0x18001f5b2  sub     rsp, 20h
0x18001f5b6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f5bc  mov     rdi, rcx
0x18001f5bf  mov     rbx, rcx
0x18001f5c2  shr     rdi, 4
0x18001f5c6  and     rax, rdi
0x18001f5c9  lea     rdx, [rax+rax*4]
0x18001f5cd  mov     rax, cs:gLockTable
0x18001f5d4  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x18001f5d8  call    cs:__imp_EnterCriticalSection
0x18001f5de  cmp     dword ptr [rbx], 494C434Ch
0x18001f5e4  jnz     short loc_18001F5ED
0x18001f5e6  mov     eax, 1
0x18001f5eb  jmp     short loc_18001F60D
0x18001f5ed  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f5f3  and     rax, rdi
0x18001f5f6  lea     rcx, [rax+rax*4]
0x18001f5fa  mov     rax, cs:gLockTable
0x18001f601  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001f605  call    cs:__imp_LeaveCriticalSection
0x18001f60b  xor     eax, eax
0x18001f60d  mov     rbx, [rsp+28h+arg_0]
0x18001f612  add     rsp, 20h
0x18001f616  pop     rdi
0x18001f617  retn
```
