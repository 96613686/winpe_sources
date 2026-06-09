# CMRSWLock::ReaderLock(void)

- ea: `0x180020c00`
- end: `0x180020cf6`
- name: `?ReaderLock@CMRSWLock@@QEAAXXZ`
- size: `246`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002930`
- `0x180004840`

## callees

- `0x180020910`
- `0x180020c00`
- `0x180028a50`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180020c1e`
- `KERNEL32!EnterCriticalSection` at `0x180020c6f`
- `KERNEL32!EnterCriticalSection` at `0x180020c1e`
- `KERNEL32!EnterCriticalSection` at `0x180020c6f`
- `KERNEL32!LeaveCriticalSection` at `0x180020c53`
- `KERNEL32!LeaveCriticalSection` at `0x180020c8a`
- `KERNEL32!LeaveCriticalSection` at `0x180020c53`
- `KERNEL32!LeaveCriticalSection` at `0x180020c8a`
- `KERNEL32!LeaveCriticalSection` at `0x180020cea`
- `KERNEL32!WaitForSingleObject` at `0x180020c9c`
- `KERNEL32!WaitForSingleObject` at `0x180020c9c`
- `KERNEL32!GetCurrentThreadId` at `0x180020c0d`
- `KERNEL32!GetCurrentThreadId` at `0x180020c0d`

## string_xrefs

- `0x180020cbe`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020cb1`: `WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

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
0x180020c00  mov     [rsp+arg_0], rbx
0x180020c05  push    rdi
0x180020c06  sub     rsp, 30h
0x180020c0a  mov     rbx, rcx
0x180020c0d  call    cs:__imp_GetCurrentThreadId
0x180020c14  nop     dword ptr [rax+rax+00h]
0x180020c19  mov     rcx, rbx; lpCriticalSection
0x180020c1c  mov     edi, eax
0x180020c1e  call    cs:__imp_EnterCriticalSection
0x180020c25  nop     dword ptr [rax+rax+00h]
0x180020c2a  cmp     [rbx+48h], edi
0x180020c2d  jnz     short loc_180020C37
0x180020c2f  inc     dword ptr [rbx+4Ch]
0x180020c32  jmp     loc_180020CDD
0x180020c37  mov     rdx, [rbx+60h]
0x180020c3b  xor     eax, eax
0x180020c3d  cmp     [rdx+rax*8], edi
0x180020c40  jz      loc_180020CD9
0x180020c46  inc     eax
0x180020c48  cmp     eax, [rbx+58h]
0x180020c4b  jbe     short loc_180020C3D
0x180020c4d  inc     dword ptr [rbx+6Ch]
0x180020c50  mov     rcx, rbx; lpCriticalSection
0x180020c53  call    cs:__imp_LeaveCriticalSection
0x180020c5a  nop     dword ptr [rax+rax+00h]
0x180020c5f  mov     edx, edi; unsigned int
0x180020c61  mov     rcx, rbx; lpCriticalSection
0x180020c64  call    ?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z; CMRSWLock::AllocateReaderSlot(ulong)
0x180020c69  or      edi, 0FFFFFFFFh
0x180020c6c  mov     rcx, rbx; lpCriticalSection
0x180020c6f  call    cs:__imp_EnterCriticalSection
0x180020c76  nop     dword ptr [rax+rax+00h]
0x180020c7b  cmp     dword ptr [rbx+48h], 0
0x180020c7f  jnz     short loc_180020C87
0x180020c81  cmp     dword ptr [rbx+70h], 0
0x180020c85  jz      short loc_180020CD1
0x180020c87  mov     rcx, rbx; lpCriticalSection
0x180020c8a  call    cs:__imp_LeaveCriticalSection
0x180020c91  nop     dword ptr [rax+rax+00h]
0x180020c96  mov     rcx, [rbx+30h]; hHandle
0x180020c9a  mov     edx, edi; dwMilliseconds
0x180020c9c  call    cs:__imp_WaitForSingleObject
0x180020ca3  nop     dword ptr [rax+rax+00h]
0x180020ca8  test    eax, eax
0x180020caa  jz      short loc_180020C6C
0x180020cac  and     [rsp+38h+var_18], 0
0x180020cb1  lea     r8, aWaitforsingleo_1; "WaitForSingleObject(m_hWriterDone, 0xFF"...
0x180020cb8  mov     r9d, 1; int
0x180020cbe  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020cc5  mov     edx, 218h; unsigned int
0x180020cca  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020ccf  jmp     short loc_180020C6C
0x180020cd1  inc     dword ptr [rbx+68h]
0x180020cd4  add     [rbx+6Ch], edi
0x180020cd7  jmp     short loc_180020CDD
0x180020cd9  inc     dword ptr [rdx+rax*8+4]
0x180020cdd  mov     rcx, rbx
0x180020ce0  mov     rbx, [rsp+38h+arg_0]
0x180020ce5  add     rsp, 30h
0x180020ce9  pop     rdi
0x180020cea  jmp     cs:__imp_LeaveCriticalSection
```
