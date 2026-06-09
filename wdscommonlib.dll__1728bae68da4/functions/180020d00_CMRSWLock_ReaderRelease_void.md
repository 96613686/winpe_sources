# CMRSWLock::ReaderRelease(void)

- ea: `0x180020d00`
- end: `0x180020e1c`
- name: `?ReaderRelease@CMRSWLock@@QEAAXXZ`
- size: `284`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003070`

## callees

- `0x1800209f0`
- `0x180020d00`
- `0x180028a50`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180020d1e`
- `KERNEL32!EnterCriticalSection` at `0x180020d1e`
- `KERNEL32!LeaveCriticalSection` at `0x180020e10`
- `KERNEL32!GetCurrentThreadId` at `0x180020d0d`
- `KERNEL32!GetCurrentThreadId` at `0x180020d0d`
- `KERNEL32!ReleaseSemaphore` at `0x180020dd3`
- `KERNEL32!ReleaseSemaphore` at `0x180020dd3`

## string_xrefs

- `0x180020d47`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020d88`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020df7`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020deb`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180020d3a`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180020d7b`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

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
0x180020d00  mov     [rsp+arg_0], rbx
0x180020d05  push    rsi
0x180020d06  sub     rsp, 30h
0x180020d0a  mov     rbx, rcx
0x180020d0d  call    cs:__imp_GetCurrentThreadId
0x180020d14  nop     dword ptr [rax+rax+00h]
0x180020d19  mov     rcx, rbx; lpCriticalSection
0x180020d1c  mov     esi, eax
0x180020d1e  call    cs:__imp_EnterCriticalSection
0x180020d25  nop     dword ptr [rax+rax+00h]
0x180020d2a  cmp     [rbx+48h], esi
0x180020d2d  jnz     short loc_180020D60
0x180020d2f  cmp     dword ptr [rbx+4Ch], 0
0x180020d33  ja      short loc_180020D58
0x180020d35  and     [rsp+38h+var_18], 0
0x180020d3a  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders > 0"
0x180020d41  mov     r9d, 1; int
0x180020d47  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020d4e  mov     edx, 22Eh; unsigned int
0x180020d53  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020d58  dec     dword ptr [rbx+4Ch]
0x180020d5b  jmp     loc_180020E03
0x180020d60  mov     rcx, [rbx+60h]
0x180020d64  xor     r8d, r8d
0x180020d67  cmp     [rcx+r8*8], esi
0x180020d6b  jz      short loc_180020D9C
0x180020d6d  inc     r8d
0x180020d70  cmp     r8d, [rbx+58h]
0x180020d74  jbe     short loc_180020D67
0x180020d76  and     [rsp+38h+var_18], 0
0x180020d7b  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x180020d82  mov     r9d, 1; int
0x180020d88  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020d8f  mov     edx, 236h; unsigned int
0x180020d94  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020d99  xor     r8d, r8d; unsigned int
0x180020d9c  mov     rdx, [rbx+60h]
0x180020da0  mov     eax, [rdx+r8*8+4]
0x180020da5  test    eax, eax
0x180020da7  jz      short loc_180020DB2
0x180020da9  dec     eax
0x180020dab  mov     [rdx+r8*8+4], eax
0x180020db0  jmp     short loc_180020E03
0x180020db2  mov     edx, esi; unsigned int
0x180020db4  mov     rcx, rbx; this
0x180020db7  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x180020dbc  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x180020dc0  jnz     short loc_180020E03
0x180020dc2  cmp     dword ptr [rbx+70h], 0
0x180020dc6  jbe     short loc_180020E03
0x180020dc8  mov     rcx, [rbx+38h]; hSemaphore
0x180020dcc  xor     r8d, r8d; lpPreviousCount
0x180020dcf  lea     edx, [r8+1]; lReleaseCount
0x180020dd3  call    cs:__imp_ReleaseSemaphore
0x180020dda  nop     dword ptr [rax+rax+00h]
0x180020ddf  test    eax, eax
0x180020de1  jnz     short loc_180020E03
0x180020de3  and     [rsp+38h+var_18], eax
0x180020de7  lea     r9d, [rax+1]; int
0x180020deb  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180020df2  mov     edx, 251h; unsigned int
0x180020df7  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020dfe  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020e03  mov     rcx, rbx
0x180020e06  mov     rbx, [rsp+38h+arg_0]
0x180020e0b  add     rsp, 30h
0x180020e0f  pop     rsi
0x180020e10  jmp     cs:__imp_LeaveCriticalSection
```
