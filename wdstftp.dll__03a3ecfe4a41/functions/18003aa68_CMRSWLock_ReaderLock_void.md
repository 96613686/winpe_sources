# CMRSWLock::ReaderLock(void)

- ea: `0x18003aa68`
- end: `0x18003ab58`
- name: `?ReaderLock@CMRSWLock@@QEAAXXZ`
- size: `240`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800022d4`
- `0x1800029e0`
- `0x180002bc0`
- `0x18000414c`
- `0x18000453c`
- `0x180004f90`
- `0x18000cf38`
- `0x18000d3e4`

## callees

- `0x18003a7ac`
- `0x18003aa68`
- `0x18003c514`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18003ab04`
- `KERNEL32!WaitForSingleObject` at `0x18003ab04`
- `KERNEL32!GetCurrentThreadId` at `0x18003aa75`
- `KERNEL32!GetCurrentThreadId` at `0x18003aa75`
- `KERNEL32!EnterCriticalSection` at `0x18003aa86`
- `KERNEL32!EnterCriticalSection` at `0x18003aad7`
- `KERNEL32!EnterCriticalSection` at `0x18003aa86`
- `KERNEL32!EnterCriticalSection` at `0x18003aad7`
- `KERNEL32!LeaveCriticalSection` at `0x18003aabb`
- `KERNEL32!LeaveCriticalSection` at `0x18003aaf2`
- `KERNEL32!LeaveCriticalSection` at `0x18003aabb`
- `KERNEL32!LeaveCriticalSection` at `0x18003aaf2`
- `KERNEL32!LeaveCriticalSection` at `0x18003ab4c`

## string_xrefs

- `0x18003ab25`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003ab19`: `WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CMRSWLock::ReaderLock(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD CurrentThreadId; // edi
  _DWORD *OwningThread; // rcx
  __int64 v4; // rax
  int v5; // r9d

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
          v5,
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
0x18003aa68  mov     [rsp+arg_0], rbx
0x18003aa6d  push    rdi
0x18003aa6e  sub     rsp, 30h
0x18003aa72  mov     rbx, rcx
0x18003aa75  call    cs:__imp_GetCurrentThreadId
0x18003aa7c  nop     dword ptr [rax+rax+00h]
0x18003aa81  mov     rcx, rbx; lpCriticalSection
0x18003aa84  mov     edi, eax
0x18003aa86  call    cs:__imp_EnterCriticalSection
0x18003aa8d  nop     dword ptr [rax+rax+00h]
0x18003aa92  cmp     [rbx+48h], edi
0x18003aa95  jnz     short loc_18003AA9F
0x18003aa97  inc     dword ptr [rbx+4Ch]
0x18003aa9a  jmp     loc_18003AB3F
0x18003aa9f  mov     rcx, [rbx+60h]
0x18003aaa3  xor     eax, eax
0x18003aaa5  cmp     [rcx+rax*8], edi
0x18003aaa8  jz      loc_18003AB3B
0x18003aaae  inc     eax
0x18003aab0  cmp     eax, [rbx+58h]
0x18003aab3  jbe     short loc_18003AAA5
0x18003aab5  inc     dword ptr [rbx+6Ch]
0x18003aab8  mov     rcx, rbx; lpCriticalSection
0x18003aabb  call    cs:__imp_LeaveCriticalSection
0x18003aac2  nop     dword ptr [rax+rax+00h]
0x18003aac7  mov     edx, edi; unsigned int
0x18003aac9  mov     rcx, rbx; lpCriticalSection
0x18003aacc  call    ?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z; CMRSWLock::AllocateReaderSlot(ulong)
0x18003aad1  or      edi, 0FFFFFFFFh
0x18003aad4  mov     rcx, rbx; lpCriticalSection
0x18003aad7  call    cs:__imp_EnterCriticalSection
0x18003aade  nop     dword ptr [rax+rax+00h]
0x18003aae3  cmp     dword ptr [rbx+48h], 0
0x18003aae7  jnz     short loc_18003AAEF
0x18003aae9  cmp     dword ptr [rbx+70h], 0
0x18003aaed  jz      short loc_18003AB33
0x18003aaef  mov     rcx, rbx; lpCriticalSection
0x18003aaf2  call    cs:__imp_LeaveCriticalSection
0x18003aaf9  nop     dword ptr [rax+rax+00h]
0x18003aafe  mov     rcx, [rbx+30h]; hHandle
0x18003ab02  mov     edx, edi; dwMilliseconds
0x18003ab04  call    cs:__imp_WaitForSingleObject
0x18003ab0b  nop     dword ptr [rax+rax+00h]
0x18003ab10  test    eax, eax
0x18003ab12  jz      short loc_18003AAD4
0x18003ab14  and     [rsp+38h+var_18], 0
0x18003ab19  lea     r8, aWaitforsingleo_1; "WaitForSingleObject(m_hWriterDone, 0xFF"...
0x18003ab20  mov     edx, 218h; unsigned int
0x18003ab25  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003ab2c  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003ab31  jmp     short loc_18003AAD4
0x18003ab33  inc     dword ptr [rbx+68h]
0x18003ab36  add     [rbx+6Ch], edi
0x18003ab39  jmp     short loc_18003AB3F
0x18003ab3b  inc     dword ptr [rcx+rax*8+4]
0x18003ab3f  mov     rcx, rbx
0x18003ab42  mov     rbx, [rsp+38h+arg_0]
0x18003ab47  add     rsp, 30h
0x18003ab4b  pop     rdi
0x18003ab4c  jmp     cs:__imp_LeaveCriticalSection
```
