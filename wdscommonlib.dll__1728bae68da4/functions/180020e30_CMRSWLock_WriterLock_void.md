# CMRSWLock::WriterLock(void)

- ea: `0x180020e30`
- end: `0x180020f42`
- name: `?WriterLock@CMRSWLock@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002960`
- `0x180004870`

## callees

- `0x180020e30`
- `0x180028a50`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180020e42`
- `KERNEL32!EnterCriticalSection` at `0x180020ed1`
- `KERNEL32!EnterCriticalSection` at `0x180020e42`
- `KERNEL32!EnterCriticalSection` at `0x180020ed1`
- `KERNEL32!LeaveCriticalSection` at `0x180020e88`
- `KERNEL32!LeaveCriticalSection` at `0x180020e88`
- `KERNEL32!LeaveCriticalSection` at `0x180020f36`
- `KERNEL32!WaitForSingleObject` at `0x180020e9b`
- `KERNEL32!WaitForSingleObject` at `0x180020e9b`
- `KERNEL32!GetCurrentThreadId` at `0x180020e51`
- `KERNEL32!GetCurrentThreadId` at `0x180020f15`
- `KERNEL32!GetCurrentThreadId` at `0x180020e51`
- `KERNEL32!GetCurrentThreadId` at `0x180020f15`

## string_xrefs

- `0x180020ebd`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020f09`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020efc`: `m_ActiveWriter.m_uNestedReaders == 0`
- `0x180020eb0`: `WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

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
0x180020e30  mov     [rsp+arg_0], rbx
0x180020e35  mov     [rsp+arg_8], rsi
0x180020e3a  push    rdi
0x180020e3b  sub     rsp, 30h
0x180020e3f  mov     rbx, rcx
0x180020e42  call    cs:__imp_EnterCriticalSection
0x180020e49  nop     dword ptr [rax+rax+00h]
0x180020e4e  mov     esi, [rbx+48h]
0x180020e51  call    cs:__imp_GetCurrentThreadId
0x180020e58  nop     dword ptr [rax+rax+00h]
0x180020e5d  cmp     esi, eax
0x180020e5f  jnz     short loc_180020E69
0x180020e61  inc     dword ptr [rbx+50h]
0x180020e64  jmp     loc_180020F24
0x180020e69  test    esi, esi
0x180020e6b  jnz     short loc_180020E82
0x180020e6d  cmp     [rbx+68h], esi
0x180020e70  jnz     short loc_180020E82
0x180020e72  cmp     [rbx+4Ch], esi
0x180020e75  jz      loc_180020F15
0x180020e7b  mov     edx, 149h
0x180020e80  jmp     short loc_180020EF7
0x180020e82  inc     dword ptr [rbx+70h]
0x180020e85  mov     rcx, rbx; lpCriticalSection
0x180020e88  call    cs:__imp_LeaveCriticalSection
0x180020e8f  nop     dword ptr [rax+rax+00h]
0x180020e94  mov     rcx, [rbx+38h]; hHandle
0x180020e98  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020e9b  call    cs:__imp_WaitForSingleObject
0x180020ea2  nop     dword ptr [rax+rax+00h]
0x180020ea7  test    eax, eax
0x180020ea9  jz      short loc_180020ECE
0x180020eab  and     [rsp+38h+var_18], 0
0x180020eb0  lea     r8, aWaitforsingleo; "WaitForSingleObject(m_hReaderDone, 0xFF"...
0x180020eb7  mov     r9d, 1; int
0x180020ebd  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020ec4  mov     edx, 164h; unsigned int
0x180020ec9  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020ece  mov     rcx, rbx; lpCriticalSection
0x180020ed1  call    cs:__imp_EnterCriticalSection
0x180020ed8  nop     dword ptr [rax+rax+00h]
0x180020edd  cmp     dword ptr [rbx+68h], 0
0x180020ee1  jnz     short loc_180020E85
0x180020ee3  cmp     dword ptr [rbx+48h], 0
0x180020ee7  jnz     short loc_180020E85
0x180020ee9  dec     dword ptr [rbx+70h]
0x180020eec  cmp     dword ptr [rbx+4Ch], 0
0x180020ef0  jz      short loc_180020F15
0x180020ef2  mov     edx, 173h; unsigned int
0x180020ef7  and     [rsp+38h+var_18], 0
0x180020efc  lea     r8, aMActivewriterM_1; "m_ActiveWriter.m_uNestedReaders == 0"
0x180020f03  mov     r9d, 1; int
0x180020f09  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020f10  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020f15  call    cs:__imp_GetCurrentThreadId
0x180020f1c  nop     dword ptr [rax+rax+00h]
0x180020f21  mov     [rbx+48h], eax
0x180020f24  mov     rcx, rbx
0x180020f27  mov     rbx, [rsp+38h+arg_0]
0x180020f2c  mov     rsi, [rsp+38h+arg_8]
0x180020f31  add     rsp, 30h
0x180020f35  pop     rdi
0x180020f36  jmp     cs:__imp_LeaveCriticalSection
```
