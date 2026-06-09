# CAutoWriterLock::Lock(void)

- ea: `0x180003170`
- end: `0x180003282`
- name: `?Lock@CAutoWriterLock@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(CAutoWriterLock *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001754`
- `0x180001950`
- `0x1800020d8`
- `0x180002544`
- `0x180002f08`
- `0x1800036ac`
- `0x180003cb4`
- `0x180003e40`
- `0x180003f54`
- `0x180004604`
- `0x180004b18`
- `0x1800054f4`
- `0x18000d66c`

## callees

- `0x180003170`
- `0x18003c514`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800031e3`
- `KERNEL32!WaitForSingleObject` at `0x1800031e3`
- `KERNEL32!GetCurrentThreadId` at `0x180003197`
- `KERNEL32!GetCurrentThreadId` at `0x180003251`
- `KERNEL32!GetCurrentThreadId` at `0x180003197`
- `KERNEL32!GetCurrentThreadId` at `0x180003251`
- `KERNEL32!EnterCriticalSection` at `0x180003188`
- `KERNEL32!EnterCriticalSection` at `0x180003213`
- `KERNEL32!EnterCriticalSection` at `0x180003188`
- `KERNEL32!EnterCriticalSection` at `0x180003213`
- `KERNEL32!LeaveCriticalSection` at `0x1800031d1`
- `KERNEL32!LeaveCriticalSection` at `0x180003263`
- `KERNEL32!LeaveCriticalSection` at `0x1800031d1`
- `KERNEL32!LeaveCriticalSection` at `0x180003263`

## string_xrefs

- `0x180003204`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180003245`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18000323e`: `m_ActiveWriter.m_uNestedReaders == 0`
- `0x1800031f8`: `WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CAutoWriterLock::Lock(LPCRITICAL_SECTION *this)
{
  LPCRITICAL_SECTION v1; // rbx
  int SpinCount; // edi
  int v4; // r9d
  unsigned int v5; // edx
  int v6; // r9d

  v1 = *this;
  EnterCriticalSection(*this);
  SpinCount = v1[1].SpinCount;
  if ( SpinCount != GetCurrentThreadId() )
  {
    if ( SpinCount || LODWORD(v1[2].LockSemaphore) )
    {
      ++LODWORD(v1[2].SpinCount);
      do
      {
        LeaveCriticalSection(v1);
        if ( WaitForSingleObject(v1[1].OwningThread, 0xFFFFFFFF) )
          WdsAssert(
            "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
            0x164u,
            "WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
            v6,
            0);
        EnterCriticalSection(v1);
      }
      while ( LODWORD(v1[2].LockSemaphore) || LODWORD(v1[1].SpinCount) );
      --LODWORD(v1[2].SpinCount);
      if ( !HIDWORD(v1[1].SpinCount) )
        goto LABEL_15;
      v5 = 371;
    }
    else
    {
      if ( !HIDWORD(v1[1].SpinCount) )
      {
LABEL_15:
        LODWORD(v1[1].SpinCount) = GetCurrentThreadId();
        goto LABEL_16;
      }
      v5 = 329;
    }
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      v5,
      "m_ActiveWriter.m_uNestedReaders == 0",
      v4,
      0);
    goto LABEL_15;
  }
  ++LODWORD(v1[2].DebugInfo);
LABEL_16:
  LeaveCriticalSection(v1);
  ++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x180003170  mov     [rsp+arg_0], rbx
0x180003175  mov     [rsp+arg_8], rsi
0x18000317a  push    rdi
0x18000317b  sub     rsp, 30h
0x18000317f  mov     rbx, [rcx]
0x180003182  mov     rsi, rcx
0x180003185  mov     rcx, rbx; lpCriticalSection
0x180003188  call    cs:__imp_EnterCriticalSection
0x18000318f  nop     dword ptr [rax+rax+00h]
0x180003194  mov     edi, [rbx+48h]
0x180003197  call    cs:__imp_GetCurrentThreadId
0x18000319e  nop     dword ptr [rax+rax+00h]
0x1800031a3  cmp     edi, eax
0x1800031a5  jnz     short loc_1800031AF
0x1800031a7  inc     dword ptr [rbx+50h]
0x1800031aa  jmp     loc_180003260
0x1800031af  test    edi, edi
0x1800031b1  jnz     short loc_1800031C8
0x1800031b3  cmp     [rbx+68h], edi
0x1800031b6  jnz     short loc_1800031C8
0x1800031b8  cmp     [rbx+4Ch], edi
0x1800031bb  jz      loc_180003251
0x1800031c1  mov     edx, 149h
0x1800031c6  jmp     short loc_180003239
0x1800031c8  inc     dword ptr [rbx+70h]
0x1800031cb  or      edi, 0FFFFFFFFh
0x1800031ce  mov     rcx, rbx; lpCriticalSection
0x1800031d1  call    cs:__imp_LeaveCriticalSection
0x1800031d8  nop     dword ptr [rax+rax+00h]
0x1800031dd  mov     rcx, [rbx+38h]; hHandle
0x1800031e1  mov     edx, edi; dwMilliseconds
0x1800031e3  call    cs:__imp_WaitForSingleObject
0x1800031ea  nop     dword ptr [rax+rax+00h]
0x1800031ef  test    eax, eax
0x1800031f1  jz      short loc_180003210
0x1800031f3  and     [rsp+38h+var_18], 0
0x1800031f8  lea     r8, aWaitforsingleo; "WaitForSingleObject(m_hReaderDone, 0xFF"...
0x1800031ff  mov     edx, 164h; unsigned int
0x180003204  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000320b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180003210  mov     rcx, rbx; lpCriticalSection
0x180003213  call    cs:__imp_EnterCriticalSection
0x18000321a  nop     dword ptr [rax+rax+00h]
0x18000321f  cmp     dword ptr [rbx+68h], 0
0x180003223  jnz     short loc_1800031CE
0x180003225  cmp     dword ptr [rbx+48h], 0
0x180003229  jnz     short loc_1800031CE
0x18000322b  add     [rbx+70h], edi
0x18000322e  cmp     dword ptr [rbx+4Ch], 0
0x180003232  jz      short loc_180003251
0x180003234  mov     edx, 173h; unsigned int
0x180003239  and     [rsp+38h+var_18], 0
0x18000323e  lea     r8, aMActivewriterM_1; "m_ActiveWriter.m_uNestedReaders == 0"
0x180003245  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000324c  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180003251  call    cs:__imp_GetCurrentThreadId
0x180003258  nop     dword ptr [rax+rax+00h]
0x18000325d  mov     [rbx+48h], eax
0x180003260  mov     rcx, rbx; lpCriticalSection
0x180003263  call    cs:__imp_LeaveCriticalSection
0x18000326a  nop     dword ptr [rax+rax+00h]
0x18000326f  inc     dword ptr [rsi+8]
0x180003272  mov     rsi, [rsp+38h+arg_8]
0x180003277  mov     rbx, [rsp+38h+arg_0]
0x18000327c  add     rsp, 30h
0x180003280  pop     rdi
0x180003281  retn
```
