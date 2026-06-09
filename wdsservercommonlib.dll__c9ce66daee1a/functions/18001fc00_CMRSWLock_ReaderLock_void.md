# CMRSWLock::ReaderLock(void)

- ea: `0x18001fc00`
- end: `0x18001fcf6`
- name: `?ReaderLock@CMRSWLock@@QEAAXXZ`
- size: `246`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001ed0`
- `0x180003da0`

## callees

- `0x18001f910`
- `0x18001fc00`
- `0x180027900`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001fc1e`
- `KERNEL32!EnterCriticalSection` at `0x18001fc6f`
- `KERNEL32!EnterCriticalSection` at `0x18001fc1e`
- `KERNEL32!EnterCriticalSection` at `0x18001fc6f`
- `KERNEL32!LeaveCriticalSection` at `0x18001fc53`
- `KERNEL32!LeaveCriticalSection` at `0x18001fc8a`
- `KERNEL32!LeaveCriticalSection` at `0x18001fc53`
- `KERNEL32!LeaveCriticalSection` at `0x18001fc8a`
- `KERNEL32!LeaveCriticalSection` at `0x18001fcea`
- `KERNEL32!WaitForSingleObject` at `0x18001fc9c`
- `KERNEL32!WaitForSingleObject` at `0x18001fc9c`
- `KERNEL32!GetCurrentThreadId` at `0x18001fc0d`
- `KERNEL32!GetCurrentThreadId` at `0x18001fc0d`

## string_xrefs

- `0x18001fcbe`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fcb1`: `WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CMRSWLock::ReaderLock(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD CurrentThreadId; // edi
  _DWORD *OwningThread; // rdx
  __int64 v4; // rax

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[1].SpinCount) == CurrentThreadId )
  {
    ++HIDWORD(lpCriticalSection[1].SpinCount);
  }
  else
  {
    OwningThread = lpCriticalSection[2].OwningThread;
    v4 = 0;
    do
    {
      if ( OwningThread[2 * v4] == CurrentThreadId )
      {
        ++OwningThread[2 * v4 + 1];
        goto LABEL_13;
      }
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 <= lpCriticalSection[2].LockCount );
    ++HIDWORD(lpCriticalSection[2].LockSemaphore);
    LeaveCriticalSection(lpCriticalSection);
    CMRSWLock::AllocateReaderSlot(lpCriticalSection, CurrentThreadId);
    while ( 1 )
    {
      EnterCriticalSection(lpCriticalSection);
      if ( !LODWORD(lpCriticalSection[1].SpinCount) && !LODWORD(lpCriticalSection[2].SpinCount) )
        break;
      LeaveCriticalSection(lpCriticalSection);
      if ( WaitForSingleObject(*(HANDLE *)&lpCriticalSection[1].LockCount, 0xFFFFFFFF) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x218u,
          "WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
          1,
          0);
    }
    ++LODWORD(lpCriticalSection[2].LockSemaphore);
    --HIDWORD(lpCriticalSection[2].LockSemaphore);
  }
LABEL_13:
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001fc00  mov     [rsp+arg_0], rbx
0x18001fc05  push    rdi
0x18001fc06  sub     rsp, 30h
0x18001fc0a  mov     rbx, rcx
0x18001fc0d  call    cs:__imp_GetCurrentThreadId
0x18001fc14  nop     dword ptr [rax+rax+00h]
0x18001fc19  mov     rcx, rbx; lpCriticalSection
0x18001fc1c  mov     edi, eax
0x18001fc1e  call    cs:__imp_EnterCriticalSection
0x18001fc25  nop     dword ptr [rax+rax+00h]
0x18001fc2a  cmp     [rbx+48h], edi
0x18001fc2d  jnz     short loc_18001FC37
0x18001fc2f  inc     dword ptr [rbx+4Ch]
0x18001fc32  jmp     loc_18001FCDD
0x18001fc37  mov     rdx, [rbx+60h]
0x18001fc3b  xor     eax, eax
0x18001fc3d  cmp     [rdx+rax*8], edi
0x18001fc40  jz      loc_18001FCD9
0x18001fc46  inc     eax
0x18001fc48  cmp     eax, [rbx+58h]
0x18001fc4b  jbe     short loc_18001FC3D
0x18001fc4d  inc     dword ptr [rbx+6Ch]
0x18001fc50  mov     rcx, rbx; lpCriticalSection
0x18001fc53  call    cs:__imp_LeaveCriticalSection
0x18001fc5a  nop     dword ptr [rax+rax+00h]
0x18001fc5f  mov     edx, edi; unsigned int
0x18001fc61  mov     rcx, rbx; lpCriticalSection
0x18001fc64  call    ?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z; CMRSWLock::AllocateReaderSlot(ulong)
0x18001fc69  or      edi, 0FFFFFFFFh
0x18001fc6c  mov     rcx, rbx; lpCriticalSection
0x18001fc6f  call    cs:__imp_EnterCriticalSection
0x18001fc76  nop     dword ptr [rax+rax+00h]
0x18001fc7b  cmp     dword ptr [rbx+48h], 0
0x18001fc7f  jnz     short loc_18001FC87
0x18001fc81  cmp     dword ptr [rbx+70h], 0
0x18001fc85  jz      short loc_18001FCD1
0x18001fc87  mov     rcx, rbx; lpCriticalSection
0x18001fc8a  call    cs:__imp_LeaveCriticalSection
0x18001fc91  nop     dword ptr [rax+rax+00h]
0x18001fc96  mov     rcx, [rbx+30h]; hHandle
0x18001fc9a  mov     edx, edi; dwMilliseconds
0x18001fc9c  call    cs:__imp_WaitForSingleObject
0x18001fca3  nop     dword ptr [rax+rax+00h]
0x18001fca8  test    eax, eax
0x18001fcaa  jz      short loc_18001FC6C
0x18001fcac  and     [rsp+38h+var_18], 0
0x18001fcb1  lea     r8, aWaitforsingleo_1; "WaitForSingleObject(m_hWriterDone, 0xFF"...
0x18001fcb8  mov     r9d, 1; int
0x18001fcbe  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fcc5  mov     edx, 218h; unsigned int
0x18001fcca  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fccf  jmp     short loc_18001FC6C
0x18001fcd1  inc     dword ptr [rbx+68h]
0x18001fcd4  add     [rbx+6Ch], edi
0x18001fcd7  jmp     short loc_18001FCDD
0x18001fcd9  inc     dword ptr [rdx+rax*8+4]
0x18001fcdd  mov     rcx, rbx
0x18001fce0  mov     rbx, [rsp+38h+arg_0]
0x18001fce5  add     rsp, 30h
0x18001fce9  pop     rdi
0x18001fcea  jmp     cs:__imp_LeaveCriticalSection
```
