# CMRSWLock::ReaderRelease(void)

- ea: `0x18001fd00`
- end: `0x18001fe1c`
- name: `?ReaderRelease@CMRSWLock@@QEAAXXZ`
- size: `284`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002610`

## callees

- `0x18001f9f0`
- `0x18001fd00`
- `0x180027900`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001fd1e`
- `KERNEL32!EnterCriticalSection` at `0x18001fd1e`
- `KERNEL32!LeaveCriticalSection` at `0x18001fe10`
- `KERNEL32!GetCurrentThreadId` at `0x18001fd0d`
- `KERNEL32!GetCurrentThreadId` at `0x18001fd0d`
- `KERNEL32!ReleaseSemaphore` at `0x18001fdd3`
- `KERNEL32!ReleaseSemaphore` at `0x18001fdd3`

## string_xrefs

- `0x18001fd47`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fd88`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fdf7`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fdeb`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18001fd3a`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x18001fd7b`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

## pseudocode

```c
void __fastcall CMRSWLock::ReaderRelease(struct _RTL_CRITICAL_SECTION *this)
{
  DWORD CurrentThreadId; // esi
  __int64 v3; // r8
  _DWORD *OwningThread; // rdx
  int v5; // eax
  bool v6; // zf

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(this);
  if ( LODWORD(this[1].SpinCount) == CurrentThreadId )
  {
    if ( !HIDWORD(this[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x22Eu,
        "m_ActiveWriter.m_uNestedReaders > 0",
        1,
        0);
    --HIDWORD(this[1].SpinCount);
  }
  else
  {
    v3 = 0;
    while ( *((_DWORD *)this[2].OwningThread + 2 * v3) != CurrentThreadId )
    {
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 > this[2].LockCount )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x236u,
          "GetReaderSlot(uThreadId, &uIndex) == 0L",
          1,
          0);
        v3 = 0;
        break;
      }
    }
    OwningThread = this[2].OwningThread;
    v5 = OwningThread[2 * v3 + 1];
    if ( v5 )
    {
      OwningThread[2 * v3 + 1] = v5 - 1;
    }
    else
    {
      CMRSWLock::FreeReaderSlot((CMRSWLock *)this, CurrentThreadId, v3);
      v6 = LODWORD(this[2].LockSemaphore)-- == 1;
      if ( v6 && LODWORD(this[2].SpinCount) && !ReleaseSemaphore(this[1].OwningThread, 1, 0) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x251u,
          "ReleaseSemaphore(m_hReaderDone, 1, 0)",
          1,
          0);
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18001fd00  mov     [rsp+arg_0], rbx
0x18001fd05  push    rsi
0x18001fd06  sub     rsp, 30h
0x18001fd0a  mov     rbx, rcx
0x18001fd0d  call    cs:__imp_GetCurrentThreadId
0x18001fd14  nop     dword ptr [rax+rax+00h]
0x18001fd19  mov     rcx, rbx; lpCriticalSection
0x18001fd1c  mov     esi, eax
0x18001fd1e  call    cs:__imp_EnterCriticalSection
0x18001fd25  nop     dword ptr [rax+rax+00h]
0x18001fd2a  cmp     [rbx+48h], esi
0x18001fd2d  jnz     short loc_18001FD60
0x18001fd2f  cmp     dword ptr [rbx+4Ch], 0
0x18001fd33  ja      short loc_18001FD58
0x18001fd35  and     [rsp+38h+var_18], 0
0x18001fd3a  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders > 0"
0x18001fd41  mov     r9d, 1; int
0x18001fd47  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fd4e  mov     edx, 22Eh; unsigned int
0x18001fd53  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fd58  dec     dword ptr [rbx+4Ch]
0x18001fd5b  jmp     loc_18001FE03
0x18001fd60  mov     rcx, [rbx+60h]
0x18001fd64  xor     r8d, r8d
0x18001fd67  cmp     [rcx+r8*8], esi
0x18001fd6b  jz      short loc_18001FD9C
0x18001fd6d  inc     r8d
0x18001fd70  cmp     r8d, [rbx+58h]
0x18001fd74  jbe     short loc_18001FD67
0x18001fd76  and     [rsp+38h+var_18], 0
0x18001fd7b  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x18001fd82  mov     r9d, 1; int
0x18001fd88  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fd8f  mov     edx, 236h; unsigned int
0x18001fd94  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fd99  xor     r8d, r8d; unsigned int
0x18001fd9c  mov     rdx, [rbx+60h]
0x18001fda0  mov     eax, [rdx+r8*8+4]
0x18001fda5  test    eax, eax
0x18001fda7  jz      short loc_18001FDB2
0x18001fda9  dec     eax
0x18001fdab  mov     [rdx+r8*8+4], eax
0x18001fdb0  jmp     short loc_18001FE03
0x18001fdb2  mov     edx, esi; unsigned int
0x18001fdb4  mov     rcx, rbx; this
0x18001fdb7  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x18001fdbc  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x18001fdc0  jnz     short loc_18001FE03
0x18001fdc2  cmp     dword ptr [rbx+70h], 0
0x18001fdc6  jbe     short loc_18001FE03
0x18001fdc8  mov     rcx, [rbx+38h]; hSemaphore
0x18001fdcc  xor     r8d, r8d; lpPreviousCount
0x18001fdcf  lea     edx, [r8+1]; lReleaseCount
0x18001fdd3  call    cs:__imp_ReleaseSemaphore
0x18001fdda  nop     dword ptr [rax+rax+00h]
0x18001fddf  test    eax, eax
0x18001fde1  jnz     short loc_18001FE03
0x18001fde3  and     [rsp+38h+var_18], eax
0x18001fde7  lea     r9d, [rax+1]; int
0x18001fdeb  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x18001fdf2  mov     edx, 251h; unsigned int
0x18001fdf7  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fdfe  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fe03  mov     rcx, rbx
0x18001fe06  mov     rbx, [rsp+38h+arg_0]
0x18001fe0b  add     rsp, 30h
0x18001fe0f  pop     rsi
0x18001fe10  jmp     cs:__imp_LeaveCriticalSection
```
