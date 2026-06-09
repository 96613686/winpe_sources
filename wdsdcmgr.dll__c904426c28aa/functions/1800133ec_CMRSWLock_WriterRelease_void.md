# CMRSWLock::WriterRelease(void)

- ea: `0x1800133ec`
- end: `0x1800134ee`
- name: `?WriterRelease@CMRSWLock@@QEAAXXZ`
- size: `258`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
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
- `0x1800133ec`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800133f9`
- `KERNEL32!EnterCriticalSection` at `0x1800133f9`
- `KERNEL32!LeaveCriticalSection` at `0x1800134e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800133ff`
- `KERNEL32!GetCurrentThreadId` at `0x1800133ff`
- `KERNEL32!ReleaseSemaphore` at `0x180013491`
- `KERNEL32!ReleaseSemaphore` at `0x1800134b7`
- `KERNEL32!ReleaseSemaphore` at `0x180013491`
- `KERNEL32!ReleaseSemaphore` at `0x1800134b7`

## string_xrefs

- `0x180013405`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180013416`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180013446`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x18001346c`: `m_uActiveReaders == 0`
- `0x18001349b`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x1800134c1`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
void __fastcall CMRSWLock::WriterRelease(CMRSWLock *this)
{
  int v2; // r9d
  int v3; // eax
  int v4; // r9d
  const char *v5; // r8
  unsigned int v6; // edx
  LONG v7; // edx

  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( *((_DWORD *)this + 18) != GetCurrentThreadId() )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x195u,
      "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
      v2,
      0);
  v3 = *((_DWORD *)this + 20);
  if ( v3 )
  {
    *((_DWORD *)this + 20) = v3 - 1;
    goto LABEL_16;
  }
  if ( *((_DWORD *)this + 19) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x1A1u,
      "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
      v2,
      0);
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  if ( *((_DWORD *)this + 26) )
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v2, 0);
  if ( *((_DWORD *)this + 28) )
  {
    if ( ReleaseSemaphore(*((HANDLE *)this + 7), 1, 0) )
      goto LABEL_16;
    v5 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
    v6 = 431;
LABEL_15:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v6, v5, v4, 0);
    goto LABEL_16;
  }
  v7 = *((_DWORD *)this + 27);
  if ( v7 && !ReleaseSemaphore(*((HANDLE *)this + 6), v7, 0) )
  {
    v5 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
    v6 = 440;
    goto LABEL_15;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800133ec  mov     [rsp+arg_0], rbx
0x1800133f1  push    rsi
0x1800133f2  sub     rsp, 30h
0x1800133f6  mov     rbx, rcx
0x1800133f9  call    cs:__imp_EnterCriticalSection
0x1800133ff  call    cs:__imp_GetCurrentThreadId
0x180013405  lea     rsi, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001340c  cmp     [rbx+48h], eax
0x18001340f  jz      short loc_18001342A
0x180013411  and     [rsp+38h+var_18], 0
0x180013416  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x18001341d  mov     edx, 195h; unsigned int
0x180013422  mov     rcx, rsi; char *
0x180013425  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001342a  mov     eax, [rbx+50h]
0x18001342d  test    eax, eax
0x18001342f  jz      short loc_18001343B
0x180013431  dec     eax
0x180013433  mov     [rbx+50h], eax
0x180013436  jmp     loc_1800134DA
0x18001343b  cmp     dword ptr [rbx+4Ch], 0
0x18001343f  jz      short loc_18001345A
0x180013441  and     [rsp+38h+var_18], 0
0x180013446  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x18001344d  mov     edx, 1A1h; unsigned int
0x180013452  mov     rcx, rsi; char *
0x180013455  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001345a  xor     eax, eax
0x18001345c  mov     [rbx+48h], rax
0x180013460  mov     [rbx+50h], eax
0x180013463  cmp     [rbx+68h], eax
0x180013466  jz      short loc_180013480
0x180013468  and     [rsp+38h+var_18], eax
0x18001346c  lea     r8, aMUactivereader; "m_uActiveReaders == 0"
0x180013473  mov     edx, 1A4h; unsigned int
0x180013478  mov     rcx, rsi; char *
0x18001347b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180013480  cmp     dword ptr [rbx+70h], 0
0x180013484  jz      short loc_1800134A9
0x180013486  mov     rcx, [rbx+38h]; hSemaphore
0x18001348a  xor     r8d, r8d; lpPreviousCount
0x18001348d  lea     edx, [r8+1]; lReleaseCount
0x180013491  call    cs:__imp_ReleaseSemaphore
0x180013497  test    eax, eax
0x180013499  jnz     short loc_1800134DA
0x18001349b  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x1800134a2  mov     edx, 1AFh
0x1800134a7  jmp     short loc_1800134CD
0x1800134a9  mov     edx, [rbx+6Ch]; lReleaseCount
0x1800134ac  test    edx, edx
0x1800134ae  jz      short loc_1800134DA
0x1800134b0  mov     rcx, [rbx+30h]; hSemaphore
0x1800134b4  xor     r8d, r8d; lpPreviousCount
0x1800134b7  call    cs:__imp_ReleaseSemaphore
0x1800134bd  test    eax, eax
0x1800134bf  jnz     short loc_1800134DA
0x1800134c1  lea     r8, aReleasesemapho; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x1800134c8  mov     edx, 1B8h; unsigned int
0x1800134cd  and     [rsp+38h+var_18], 0
0x1800134d2  mov     rcx, rsi; char *
0x1800134d5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800134da  mov     rcx, rbx
0x1800134dd  mov     rbx, [rsp+38h+arg_0]
0x1800134e2  add     rsp, 30h
0x1800134e6  pop     rsi
0x1800134e7  jmp     cs:__imp_LeaveCriticalSection
```
