# CMRSWLock::WriterRelease(void)

- ea: `0x18001ff50`
- end: `0x180020088`
- name: `?WriterRelease@CMRSWLock@@QEAAXXZ`
- size: `312`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002640`

## callees

- `0x18001ff50`
- `0x180027900`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001ff62`
- `KERNEL32!EnterCriticalSection` at `0x18001ff62`
- `KERNEL32!LeaveCriticalSection` at `0x18002007c`
- `KERNEL32!GetCurrentThreadId` at `0x18001ff6e`
- `KERNEL32!GetCurrentThreadId` at `0x18001ff6e`
- `KERNEL32!ReleaseSemaphore` at `0x180020012`
- `KERNEL32!ReleaseSemaphore` at `0x18002003e`
- `KERNEL32!ReleaseSemaphore` at `0x180020012`
- `KERNEL32!ReleaseSemaphore` at `0x18002003e`

## string_xrefs

- `0x18001ff7f`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001ff90`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x18001ffc3`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x18001ffec`: `m_uActiveReaders == 0`
- `0x180020022`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18002004e`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
void __fastcall CMRSWLock::WriterRelease(CMRSWLock *this)
{
  int v2; // eax
  const char *v3; // r8
  unsigned int v4; // edx
  LONG v5; // edx

  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( *((_DWORD *)this + 18) != GetCurrentThreadId() )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x195u,
      "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
      1,
      0);
  v2 = *((_DWORD *)this + 20);
  if ( v2 )
  {
    *((_DWORD *)this + 20) = v2 - 1;
    goto LABEL_16;
  }
  if ( *((_DWORD *)this + 19) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x1A1u,
      "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
      1,
      0);
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  if ( *((_DWORD *)this + 26) )
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", 1, 0);
  if ( *((_DWORD *)this + 28) )
  {
    if ( ReleaseSemaphore(*((HANDLE *)this + 7), 1, 0) )
      goto LABEL_16;
    v3 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
    v4 = 431;
LABEL_15:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v4, v3, 1, 0);
    goto LABEL_16;
  }
  v5 = *((_DWORD *)this + 27);
  if ( v5 && !ReleaseSemaphore(*((HANDLE *)this + 6), v5, 0) )
  {
    v3 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
    v4 = 440;
    goto LABEL_15;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001ff50  mov     [rsp+arg_0], rbx
0x18001ff55  mov     [rsp+arg_8], rbp
0x18001ff5a  push    rsi
0x18001ff5b  sub     rsp, 30h
0x18001ff5f  mov     rbx, rcx
0x18001ff62  call    cs:__imp_EnterCriticalSection
0x18001ff69  nop     dword ptr [rax+rax+00h]
0x18001ff6e  call    cs:__imp_GetCurrentThreadId
0x18001ff75  nop     dword ptr [rax+rax+00h]
0x18001ff7a  mov     esi, 1
0x18001ff7f  lea     rbp, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001ff86  cmp     [rbx+48h], eax
0x18001ff89  jz      short loc_18001FFA7
0x18001ff8b  and     [rsp+38h+var_18], 0
0x18001ff90  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x18001ff97  mov     r9d, esi; int
0x18001ff9a  mov     edx, 195h; unsigned int
0x18001ff9f  mov     rcx, rbp; char *
0x18001ffa2  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001ffa7  mov     eax, [rbx+50h]
0x18001ffaa  test    eax, eax
0x18001ffac  jz      short loc_18001FFB8
0x18001ffae  dec     eax
0x18001ffb0  mov     [rbx+50h], eax
0x18001ffb3  jmp     loc_18002006A
0x18001ffb8  cmp     dword ptr [rbx+4Ch], 0
0x18001ffbc  jz      short loc_18001FFDA
0x18001ffbe  and     [rsp+38h+var_18], 0
0x18001ffc3  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x18001ffca  mov     r9d, esi; int
0x18001ffcd  mov     edx, 1A1h; unsigned int
0x18001ffd2  mov     rcx, rbp; char *
0x18001ffd5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001ffda  xor     eax, eax
0x18001ffdc  mov     [rbx+48h], rax
0x18001ffe0  mov     [rbx+50h], eax
0x18001ffe3  cmp     [rbx+68h], eax
0x18001ffe6  jz      short loc_180020003
0x18001ffe8  and     [rsp+38h+var_18], eax
0x18001ffec  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x18001fff3  mov     r9d, esi; int
0x18001fff6  mov     edx, 1A4h; unsigned int
0x18001fffb  mov     rcx, rbp; char *
0x18001fffe  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020003  cmp     dword ptr [rbx+70h], 0
0x180020007  jz      short loc_180020030
0x180020009  mov     rcx, [rbx+38h]; hSemaphore
0x18002000d  xor     r8d, r8d; lpPreviousCount
0x180020010  mov     edx, esi; lReleaseCount
0x180020012  call    cs:__imp_ReleaseSemaphore
0x180020019  nop     dword ptr [rax+rax+00h]
0x18002001e  test    eax, eax
0x180020020  jnz     short loc_18002006A
0x180020022  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180020029  mov     edx, 1AFh
0x18002002e  jmp     short loc_18002005A
0x180020030  mov     edx, [rbx+6Ch]; lReleaseCount
0x180020033  test    edx, edx
0x180020035  jz      short loc_18002006A
0x180020037  mov     rcx, [rbx+30h]; hSemaphore
0x18002003b  xor     r8d, r8d; lpPreviousCount
0x18002003e  call    cs:__imp_ReleaseSemaphore
0x180020045  nop     dword ptr [rax+rax+00h]
0x18002004a  test    eax, eax
0x18002004c  jnz     short loc_18002006A
0x18002004e  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180020055  mov     edx, 1B8h; unsigned int
0x18002005a  and     [rsp+38h+var_18], 0
0x18002005f  mov     r9d, esi; int
0x180020062  mov     rcx, rbp; char *
0x180020065  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18002006a  mov     rcx, rbx
0x18002006d  mov     rbx, [rsp+38h+arg_0]
0x180020072  mov     rbp, [rsp+38h+arg_8]
0x180020077  add     rsp, 30h
0x18002007b  pop     rsi
0x18002007c  jmp     cs:__imp_LeaveCriticalSection
```
