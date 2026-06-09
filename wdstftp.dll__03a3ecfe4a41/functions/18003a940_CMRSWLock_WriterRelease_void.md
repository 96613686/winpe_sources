# CMRSWLock::WriterRelease(void)

- ea: `0x18003a940`
- end: `0x18003aa5f`
- name: `?WriterRelease@CMRSWLock@@QEAAXXZ`
- size: `287`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001754`
- `0x180001950`
- `0x1800020d8`
- `0x180002f08`
- `0x1800036ac`
- `0x180003cb4`
- `0x180003e40`
- `0x180003f54`
- `0x18000d66c`

## callees

- `0x18003a940`
- `0x18003c514`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18003a9f1`
- `KERNEL32!ReleaseSemaphore` at `0x18003aa1d`
- `KERNEL32!ReleaseSemaphore` at `0x18003a9f1`
- `KERNEL32!ReleaseSemaphore` at `0x18003aa1d`
- `KERNEL32!GetCurrentThreadId` at `0x18003a959`
- `KERNEL32!GetCurrentThreadId` at `0x18003a959`
- `KERNEL32!EnterCriticalSection` at `0x18003a94d`
- `KERNEL32!EnterCriticalSection` at `0x18003a94d`
- `KERNEL32!LeaveCriticalSection` at `0x18003aa53`

## string_xrefs

- `0x18003a965`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003a976`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x18003a9a6`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x18003a9cc`: `m_uActiveReaders == 0`
- `0x18003aa01`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18003aa2d`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

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
0x18003a940  mov     [rsp+arg_0], rbx
0x18003a945  push    rsi
0x18003a946  sub     rsp, 30h
0x18003a94a  mov     rbx, rcx
0x18003a94d  call    cs:__imp_EnterCriticalSection
0x18003a954  nop     dword ptr [rax+rax+00h]
0x18003a959  call    cs:__imp_GetCurrentThreadId
0x18003a960  nop     dword ptr [rax+rax+00h]
0x18003a965  lea     rsi, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003a96c  cmp     [rbx+48h], eax
0x18003a96f  jz      short loc_18003A98A
0x18003a971  and     [rsp+38h+var_18], 0
0x18003a976  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x18003a97d  mov     edx, 195h; unsigned int
0x18003a982  mov     rcx, rsi; char *
0x18003a985  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003a98a  mov     eax, [rbx+50h]
0x18003a98d  test    eax, eax
0x18003a98f  jz      short loc_18003A99B
0x18003a991  dec     eax
0x18003a993  mov     [rbx+50h], eax
0x18003a996  jmp     loc_18003AA46
0x18003a99b  cmp     dword ptr [rbx+4Ch], 0
0x18003a99f  jz      short loc_18003A9BA
0x18003a9a1  and     [rsp+38h+var_18], 0
0x18003a9a6  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x18003a9ad  mov     edx, 1A1h; unsigned int
0x18003a9b2  mov     rcx, rsi; char *
0x18003a9b5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003a9ba  xor     eax, eax
0x18003a9bc  mov     [rbx+48h], rax
0x18003a9c0  mov     [rbx+50h], eax
0x18003a9c3  cmp     [rbx+68h], eax
0x18003a9c6  jz      short loc_18003A9E0
0x18003a9c8  and     [rsp+38h+var_18], eax
0x18003a9cc  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x18003a9d3  mov     edx, 1A4h; unsigned int
0x18003a9d8  mov     rcx, rsi; char *
0x18003a9db  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003a9e0  cmp     dword ptr [rbx+70h], 0
0x18003a9e4  jz      short loc_18003AA0F
0x18003a9e6  mov     rcx, [rbx+38h]; hSemaphore
0x18003a9ea  xor     r8d, r8d; lpPreviousCount
0x18003a9ed  lea     edx, [r8+1]; lReleaseCount
0x18003a9f1  call    cs:__imp_ReleaseSemaphore
0x18003a9f8  nop     dword ptr [rax+rax+00h]
0x18003a9fd  test    eax, eax
0x18003a9ff  jnz     short loc_18003AA46
0x18003aa01  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x18003aa08  mov     edx, 1AFh
0x18003aa0d  jmp     short loc_18003AA39
0x18003aa0f  mov     edx, [rbx+6Ch]; lReleaseCount
0x18003aa12  test    edx, edx
0x18003aa14  jz      short loc_18003AA46
0x18003aa16  mov     rcx, [rbx+30h]; hSemaphore
0x18003aa1a  xor     r8d, r8d; lpPreviousCount
0x18003aa1d  call    cs:__imp_ReleaseSemaphore
0x18003aa24  nop     dword ptr [rax+rax+00h]
0x18003aa29  test    eax, eax
0x18003aa2b  jnz     short loc_18003AA46
0x18003aa2d  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x18003aa34  mov     edx, 1B8h; unsigned int
0x18003aa39  and     [rsp+38h+var_18], 0
0x18003aa3e  mov     rcx, rsi; char *
0x18003aa41  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003aa46  mov     rcx, rbx
0x18003aa49  mov     rbx, [rsp+38h+arg_0]
0x18003aa4e  add     rsp, 30h
0x18003aa52  pop     rsi
0x18003aa53  jmp     cs:__imp_LeaveCriticalSection
```
