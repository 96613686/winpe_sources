# CMRSWLock::WriterLock(void)

- ea: `0x18001fe30`
- end: `0x18001ff42`
- name: `?WriterLock@CMRSWLock@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f00`
- `0x180003dd0`

## callees

- `0x18001fe30`
- `0x180027900`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001fe42`
- `KERNEL32!EnterCriticalSection` at `0x18001fed1`
- `KERNEL32!EnterCriticalSection` at `0x18001fe42`
- `KERNEL32!EnterCriticalSection` at `0x18001fed1`
- `KERNEL32!LeaveCriticalSection` at `0x18001fe88`
- `KERNEL32!LeaveCriticalSection` at `0x18001fe88`
- `KERNEL32!LeaveCriticalSection` at `0x18001ff36`
- `KERNEL32!WaitForSingleObject` at `0x18001fe9b`
- `KERNEL32!WaitForSingleObject` at `0x18001fe9b`
- `KERNEL32!GetCurrentThreadId` at `0x18001fe51`
- `KERNEL32!GetCurrentThreadId` at `0x18001ff15`
- `KERNEL32!GetCurrentThreadId` at `0x18001fe51`
- `KERNEL32!GetCurrentThreadId` at `0x18001ff15`

## string_xrefs

- `0x18001febd`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001ff09`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fefc`: `m_ActiveWriter.m_uNestedReaders == 0`
- `0x18001feb0`: `WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CMRSWLock::WriterLock(LPCRITICAL_SECTION lpCriticalSection)
{
  int SpinCount; // esi
  unsigned int v3; // edx

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
            1,
            0);
        EnterCriticalSection(lpCriticalSection);
      }
      while ( LODWORD(lpCriticalSection[2].LockSemaphore) || LODWORD(lpCriticalSection[1].SpinCount) );
      --LODWORD(lpCriticalSection[2].SpinCount);
      if ( !HIDWORD(lpCriticalSection[1].SpinCount) )
        goto LABEL_15;
      v3 = 371;
    }
    else
    {
      if ( !HIDWORD(lpCriticalSection[1].SpinCount) )
      {
LABEL_15:
        LODWORD(lpCriticalSection[1].SpinCount) = GetCurrentThreadId();
        goto LABEL_16;
      }
      v3 = 329;
    }
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      v3,
      "m_ActiveWriter.m_uNestedReaders == 0",
      1,
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
0x18001fe30  mov     [rsp+arg_0], rbx
0x18001fe35  mov     [rsp+arg_8], rsi
0x18001fe3a  push    rdi
0x18001fe3b  sub     rsp, 30h
0x18001fe3f  mov     rbx, rcx
0x18001fe42  call    cs:__imp_EnterCriticalSection
0x18001fe49  nop     dword ptr [rax+rax+00h]
0x18001fe4e  mov     esi, [rbx+48h]
0x18001fe51  call    cs:__imp_GetCurrentThreadId
0x18001fe58  nop     dword ptr [rax+rax+00h]
0x18001fe5d  cmp     esi, eax
0x18001fe5f  jnz     short loc_18001FE69
0x18001fe61  inc     dword ptr [rbx+50h]
0x18001fe64  jmp     loc_18001FF24
0x18001fe69  test    esi, esi
0x18001fe6b  jnz     short loc_18001FE82
0x18001fe6d  cmp     [rbx+68h], esi
0x18001fe70  jnz     short loc_18001FE82
0x18001fe72  cmp     [rbx+4Ch], esi
0x18001fe75  jz      loc_18001FF15
0x18001fe7b  mov     edx, 149h
0x18001fe80  jmp     short loc_18001FEF7
0x18001fe82  inc     dword ptr [rbx+70h]
0x18001fe85  mov     rcx, rbx; lpCriticalSection
0x18001fe88  call    cs:__imp_LeaveCriticalSection
0x18001fe8f  nop     dword ptr [rax+rax+00h]
0x18001fe94  mov     rcx, [rbx+38h]; hHandle
0x18001fe98  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001fe9b  call    cs:__imp_WaitForSingleObject
0x18001fea2  nop     dword ptr [rax+rax+00h]
0x18001fea7  test    eax, eax
0x18001fea9  jz      short loc_18001FECE
0x18001feab  and     [rsp+38h+var_18], 0
0x18001feb0  lea     r8, aWaitforsingleo; "WaitForSingleObject(m_hReaderDone, 0xFF"...
0x18001feb7  mov     r9d, 1; int
0x18001febd  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fec4  mov     edx, 164h; unsigned int
0x18001fec9  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fece  mov     rcx, rbx; lpCriticalSection
0x18001fed1  call    cs:__imp_EnterCriticalSection
0x18001fed8  nop     dword ptr [rax+rax+00h]
0x18001fedd  cmp     dword ptr [rbx+68h], 0
0x18001fee1  jnz     short loc_18001FE85
0x18001fee3  cmp     dword ptr [rbx+48h], 0
0x18001fee7  jnz     short loc_18001FE85
0x18001fee9  dec     dword ptr [rbx+70h]
0x18001feec  cmp     dword ptr [rbx+4Ch], 0
0x18001fef0  jz      short loc_18001FF15
0x18001fef2  mov     edx, 173h; unsigned int
0x18001fef7  and     [rsp+38h+var_18], 0
0x18001fefc  lea     r8, aMActivewriterM_1; "m_ActiveWriter.m_uNestedReaders == 0"
0x18001ff03  mov     r9d, 1; int
0x18001ff09  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001ff10  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001ff15  call    cs:__imp_GetCurrentThreadId
0x18001ff1c  nop     dword ptr [rax+rax+00h]
0x18001ff21  mov     [rbx+48h], eax
0x18001ff24  mov     rcx, rbx
0x18001ff27  mov     rbx, [rsp+38h+arg_0]
0x18001ff2c  mov     rsi, [rsp+38h+arg_8]
0x18001ff31  add     rsp, 30h
0x18001ff35  pop     rdi
0x18001ff36  jmp     cs:__imp_LeaveCriticalSection
```
