# CMRSWLock::ReaderRelease(void)

- ea: `0x18003ab60`
- end: `0x18003ac7c`
- name: `?ReaderRelease@CMRSWLock@@QEAAXXZ`
- size: `284`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800022d4`
- `0x1800029e0`
- `0x180002bc0`
- `0x18000453c`
- `0x180004f90`
- `0x18000cf38`
- `0x18000d3e4`

## callees

- `0x18003a878`
- `0x18003ab60`
- `0x18003c514`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18003ac32`
- `KERNEL32!ReleaseSemaphore` at `0x18003ac32`
- `KERNEL32!GetCurrentThreadId` at `0x18003ab74`
- `KERNEL32!GetCurrentThreadId` at `0x18003ab74`
- `KERNEL32!EnterCriticalSection` at `0x18003ab85`
- `KERNEL32!EnterCriticalSection` at `0x18003ab85`
- `KERNEL32!LeaveCriticalSection` at `0x18003ac70`

## string_xrefs

- `0x18003abad`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003abe8`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003ac52`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003ac46`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18003aba1`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x18003abdc`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

## pseudocode

```c
void __fastcall CMRSWLock::ReaderRelease(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // edi
  DWORD CurrentThreadId; // esi
  int v4; // r9d
  int SpinCount_high; // eax
  __int64 v6; // rcx
  _DWORD *OwningThread; // rdx
  int v8; // eax
  bool v9; // zf
  int v10; // r9d

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(this);
  if ( LODWORD(this[1].SpinCount) == CurrentThreadId )
  {
    SpinCount_high = HIDWORD(this[1].SpinCount);
    if ( !SpinCount_high )
    {
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x22Eu,
        "m_ActiveWriter.m_uNestedReaders > 0",
        v4,
        0);
      SpinCount_high = HIDWORD(this[1].SpinCount);
    }
    HIDWORD(this[1].SpinCount) = SpinCount_high - 1;
  }
  else
  {
    v6 = 0;
    while ( *((_DWORD *)this[2].OwningThread + 2 * v6) != CurrentThreadId )
    {
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 > this[2].LockCount )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x236u,
          "GetReaderSlot(uThreadId, &uIndex) == 0L",
          v4,
          0);
        goto LABEL_10;
      }
    }
    v2 = v6;
LABEL_10:
    OwningThread = this[2].OwningThread;
    v8 = OwningThread[2 * v2 + 1];
    if ( v8 )
    {
      OwningThread[2 * v2 + 1] = v8 - 1;
    }
    else
    {
      CMRSWLock::FreeReaderSlot((CMRSWLock *)this, CurrentThreadId, v2);
      v9 = LODWORD(this[2].LockSemaphore)-- == 1;
      if ( v9 && LODWORD(this[2].SpinCount) && !ReleaseSemaphore(this[1].OwningThread, 1, 0) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x251u,
          "ReleaseSemaphore(m_hReaderDone, 1, 0)",
          v10,
          0);
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18003ab60  mov     [rsp+arg_0], rbx
0x18003ab65  mov     [rsp+arg_8], rsi
0x18003ab6a  push    rdi
0x18003ab6b  sub     rsp, 30h
0x18003ab6f  mov     rbx, rcx
0x18003ab72  xor     edi, edi
0x18003ab74  call    cs:__imp_GetCurrentThreadId
0x18003ab7b  nop     dword ptr [rax+rax+00h]
0x18003ab80  mov     rcx, rbx; lpCriticalSection
0x18003ab83  mov     esi, eax
0x18003ab85  call    cs:__imp_EnterCriticalSection
0x18003ab8c  nop     dword ptr [rax+rax+00h]
0x18003ab91  cmp     [rbx+48h], esi
0x18003ab94  jnz     short loc_18003ABC6
0x18003ab96  mov     eax, [rbx+4Ch]
0x18003ab99  test    eax, eax
0x18003ab9b  jnz     short loc_18003ABBC
0x18003ab9d  and     [rsp+38h+var_18], edi
0x18003aba1  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders > 0"
0x18003aba8  mov     edx, 22Eh; unsigned int
0x18003abad  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003abb4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003abb9  mov     eax, [rbx+4Ch]
0x18003abbc  dec     eax
0x18003abbe  mov     [rbx+4Ch], eax
0x18003abc1  jmp     loc_18003AC5E
0x18003abc6  mov     rdx, [rbx+60h]
0x18003abca  xor     ecx, ecx
0x18003abcc  cmp     [rdx+rcx*8], esi
0x18003abcf  jz      short loc_18003ABF6
0x18003abd1  inc     ecx
0x18003abd3  cmp     ecx, [rbx+58h]
0x18003abd6  jbe     short loc_18003ABCC
0x18003abd8  and     [rsp+38h+var_18], edi
0x18003abdc  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x18003abe3  mov     edx, 236h; unsigned int
0x18003abe8  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003abef  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003abf4  jmp     short loc_18003ABF8
0x18003abf6  mov     edi, ecx
0x18003abf8  mov     rdx, [rbx+60h]
0x18003abfc  mov     ecx, edi
0x18003abfe  mov     eax, [rdx+rcx*8+4]
0x18003ac02  test    eax, eax
0x18003ac04  jz      short loc_18003AC0E
0x18003ac06  dec     eax
0x18003ac08  mov     [rdx+rcx*8+4], eax
0x18003ac0c  jmp     short loc_18003AC5E
0x18003ac0e  mov     r8d, edi; unsigned int
0x18003ac11  mov     edx, esi; unsigned int
0x18003ac13  mov     rcx, rbx; this
0x18003ac16  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x18003ac1b  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x18003ac1f  jnz     short loc_18003AC5E
0x18003ac21  cmp     dword ptr [rbx+70h], 0
0x18003ac25  jbe     short loc_18003AC5E
0x18003ac27  mov     rcx, [rbx+38h]; hSemaphore
0x18003ac2b  xor     r8d, r8d; lpPreviousCount
0x18003ac2e  lea     edx, [r8+1]; lReleaseCount
0x18003ac32  call    cs:__imp_ReleaseSemaphore
0x18003ac39  nop     dword ptr [rax+rax+00h]
0x18003ac3e  test    eax, eax
0x18003ac40  jnz     short loc_18003AC5E
0x18003ac42  and     [rsp+38h+var_18], eax
0x18003ac46  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x18003ac4d  mov     edx, 251h; unsigned int
0x18003ac52  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003ac59  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003ac5e  mov     rcx, rbx
0x18003ac61  mov     rbx, [rsp+38h+arg_0]
0x18003ac66  mov     rsi, [rsp+38h+arg_8]
0x18003ac6b  add     rsp, 30h
0x18003ac6f  pop     rdi
0x18003ac70  jmp     cs:__imp_LeaveCriticalSection
```
