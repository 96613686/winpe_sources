# CMRSWLock::WriterLock(void)

- ea: `0x180013314`
- end: `0x1800133e5`
- name: `?WriterLock@CMRSWLock@@QEAAXXZ`
- size: `209`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002268`
- `0x18000259c`
- `0x180005430`
- `0x18000563c`
- `0x180005818`

## callees

- `0x180012f34`
- `0x180013314`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180013321`
- `KERNEL32!EnterCriticalSection` at `0x180013390`
- `KERNEL32!EnterCriticalSection` at `0x180013321`
- `KERNEL32!EnterCriticalSection` at `0x180013390`
- `KERNEL32!LeaveCriticalSection` at `0x18001335a`
- `KERNEL32!LeaveCriticalSection` at `0x18001335a`
- `KERNEL32!LeaveCriticalSection` at `0x1800133de`
- `KERNEL32!GetCurrentThreadId` at `0x18001332a`
- `KERNEL32!GetCurrentThreadId` at `0x1800133c8`
- `KERNEL32!GetCurrentThreadId` at `0x18001332a`
- `KERNEL32!GetCurrentThreadId` at `0x1800133c8`
- `KERNEL32!WaitForSingleObject` at `0x180013366`
- `KERNEL32!WaitForSingleObject` at `0x180013366`

## string_xrefs

- `0x180013381`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800133bc`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800133b5`: `m_ActiveWriter.m_uNestedReaders == 0`
- `0x180013375`: `WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CMRSWLock::WriterLock(LPCRITICAL_SECTION lpCriticalSection)
{
  int SpinCount; // edi
  int v3; // r9d
  unsigned int v4; // edx
  int v5; // r9d

  EnterCriticalSection(lpCriticalSection);
  SpinCount = lpCriticalSection[1].SpinCount;
  if ( SpinCount != GetCurrentThreadId() )
  {
    if ( SpinCount || LODWORD(lpCriticalSection[2].LockSemaphore) )
    {
      ++LODWORD(lpCriticalSection[2].SpinCount);
      do
      {
        LeaveCriticalSection(lpCriticalSection);
        if ( WaitForSingleObject(lpCriticalSection[1].OwningThread, 0xFFFFFFFF) )
          WdsAssert(
            "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
            0x164u,
            "WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
            v5,
            0);
        EnterCriticalSection(lpCriticalSection);
      }
      while ( LODWORD(lpCriticalSection[2].LockSemaphore) || LODWORD(lpCriticalSection[1].SpinCount) );
      --LODWORD(lpCriticalSection[2].SpinCount);
      if ( !HIDWORD(lpCriticalSection[1].SpinCount) )
        goto LABEL_15;
      v4 = 371;
    }
    else
    {
      if ( !HIDWORD(lpCriticalSection[1].SpinCount) )
      {
LABEL_15:
        LODWORD(lpCriticalSection[1].SpinCount) = GetCurrentThreadId();
        goto LABEL_16;
      }
      v4 = 329;
    }
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      v4,
      "m_ActiveWriter.m_uNestedReaders == 0",
      v3,
      0);
    goto LABEL_15;
  }
  ++LODWORD(lpCriticalSection[2].DebugInfo);
LABEL_16:
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180013314  mov     [rsp+arg_0], rbx
0x180013319  push    rdi
0x18001331a  sub     rsp, 30h
0x18001331e  mov     rbx, rcx
0x180013321  call    cs:__imp_EnterCriticalSection
0x180013327  mov     edi, [rbx+48h]
0x18001332a  call    cs:__imp_GetCurrentThreadId
0x180013330  cmp     edi, eax
0x180013332  jnz     short loc_18001333C
0x180013334  inc     dword ptr [rbx+50h]
0x180013337  jmp     loc_1800133D1
0x18001333c  test    edi, edi
0x18001333e  jnz     short loc_180013351
0x180013340  cmp     [rbx+68h], edi
0x180013343  jnz     short loc_180013351
0x180013345  cmp     [rbx+4Ch], edi
0x180013348  jz      short loc_1800133C8
0x18001334a  mov     edx, 149h
0x18001334f  jmp     short loc_1800133B0
0x180013351  inc     dword ptr [rbx+70h]
0x180013354  or      edi, 0FFFFFFFFh
0x180013357  mov     rcx, rbx; lpCriticalSection
0x18001335a  call    cs:__imp_LeaveCriticalSection
0x180013360  mov     rcx, [rbx+38h]; hHandle
0x180013364  mov     edx, edi; dwMilliseconds
0x180013366  call    cs:__imp_WaitForSingleObject
0x18001336c  test    eax, eax
0x18001336e  jz      short loc_18001338D
0x180013370  and     [rsp+38h+var_18], 0
0x180013375  lea     r8, aWaitforsingleo_1; "WaitForSingleObject(m_hReaderDone, 0xFF"...
0x18001337c  mov     edx, 164h; unsigned int
0x180013381  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013388  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001338d  mov     rcx, rbx; lpCriticalSection
0x180013390  call    cs:__imp_EnterCriticalSection
0x180013396  cmp     dword ptr [rbx+68h], 0
0x18001339a  jnz     short loc_180013357
0x18001339c  cmp     dword ptr [rbx+48h], 0
0x1800133a0  jnz     short loc_180013357
0x1800133a2  add     [rbx+70h], edi
0x1800133a5  cmp     dword ptr [rbx+4Ch], 0
0x1800133a9  jz      short loc_1800133C8
0x1800133ab  mov     edx, 173h; unsigned int
0x1800133b0  and     [rsp+38h+var_18], 0
0x1800133b5  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uNestedReaders == 0"
0x1800133bc  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800133c3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800133c8  call    cs:__imp_GetCurrentThreadId
0x1800133ce  mov     [rbx+48h], eax
0x1800133d1  mov     rcx, rbx
0x1800133d4  mov     rbx, [rsp+38h+arg_0]
0x1800133d9  add     rsp, 30h
0x1800133dd  pop     rdi
0x1800133de  jmp     cs:__imp_LeaveCriticalSection
```
