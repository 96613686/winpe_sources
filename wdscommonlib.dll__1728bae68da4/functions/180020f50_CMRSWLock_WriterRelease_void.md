# CMRSWLock::WriterRelease(void)

- ea: `0x180020f50`
- end: `0x180021088`
- name: `?WriterRelease@CMRSWLock@@QEAAXXZ`
- size: `312`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800030a0`

## callees

- `0x180020f50`
- `0x180028a50`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180020f62`
- `KERNEL32!EnterCriticalSection` at `0x180020f62`
- `KERNEL32!LeaveCriticalSection` at `0x18002107c`
- `KERNEL32!GetCurrentThreadId` at `0x180020f6e`
- `KERNEL32!GetCurrentThreadId` at `0x180020f6e`
- `KERNEL32!ReleaseSemaphore` at `0x180021012`
- `KERNEL32!ReleaseSemaphore` at `0x18002103e`
- `KERNEL32!ReleaseSemaphore` at `0x180021012`
- `KERNEL32!ReleaseSemaphore` at `0x18002103e`

## string_xrefs

- `0x180020f7f`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020f90`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180020fc3`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180020fec`: `m_uActiveReaders == 0`
- `0x180021022`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18002104e`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

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
0x180020f50  mov     [rsp+arg_0], rbx
0x180020f55  mov     [rsp+arg_8], rbp
0x180020f5a  push    rsi
0x180020f5b  sub     rsp, 30h
0x180020f5f  mov     rbx, rcx
0x180020f62  call    cs:__imp_EnterCriticalSection
0x180020f69  nop     dword ptr [rax+rax+00h]
0x180020f6e  call    cs:__imp_GetCurrentThreadId
0x180020f75  nop     dword ptr [rax+rax+00h]
0x180020f7a  mov     esi, 1
0x180020f7f  lea     rbp, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020f86  cmp     [rbx+48h], eax
0x180020f89  jz      short loc_180020FA7
0x180020f8b  and     [rsp+38h+var_18], 0
0x180020f90  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180020f97  mov     r9d, esi; int
0x180020f9a  mov     edx, 195h; unsigned int
0x180020f9f  mov     rcx, rbp; char *
0x180020fa2  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020fa7  mov     eax, [rbx+50h]
0x180020faa  test    eax, eax
0x180020fac  jz      short loc_180020FB8
0x180020fae  dec     eax
0x180020fb0  mov     [rbx+50h], eax
0x180020fb3  jmp     loc_18002106A
0x180020fb8  cmp     dword ptr [rbx+4Ch], 0
0x180020fbc  jz      short loc_180020FDA
0x180020fbe  and     [rsp+38h+var_18], 0
0x180020fc3  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180020fca  mov     r9d, esi; int
0x180020fcd  mov     edx, 1A1h; unsigned int
0x180020fd2  mov     rcx, rbp; char *
0x180020fd5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020fda  xor     eax, eax
0x180020fdc  mov     [rbx+48h], rax
0x180020fe0  mov     [rbx+50h], eax
0x180020fe3  cmp     [rbx+68h], eax
0x180020fe6  jz      short loc_180021003
0x180020fe8  and     [rsp+38h+var_18], eax
0x180020fec  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x180020ff3  mov     r9d, esi; int
0x180020ff6  mov     edx, 1A4h; unsigned int
0x180020ffb  mov     rcx, rbp; char *
0x180020ffe  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180021003  cmp     dword ptr [rbx+70h], 0
0x180021007  jz      short loc_180021030
0x180021009  mov     rcx, [rbx+38h]; hSemaphore
0x18002100d  xor     r8d, r8d; lpPreviousCount
0x180021010  mov     edx, esi; lReleaseCount
0x180021012  call    cs:__imp_ReleaseSemaphore
0x180021019  nop     dword ptr [rax+rax+00h]
0x18002101e  test    eax, eax
0x180021020  jnz     short loc_18002106A
0x180021022  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180021029  mov     edx, 1AFh
0x18002102e  jmp     short loc_18002105A
0x180021030  mov     edx, [rbx+6Ch]; lReleaseCount
0x180021033  test    edx, edx
0x180021035  jz      short loc_18002106A
0x180021037  mov     rcx, [rbx+30h]; hSemaphore
0x18002103b  xor     r8d, r8d; lpPreviousCount
0x18002103e  call    cs:__imp_ReleaseSemaphore
0x180021045  nop     dword ptr [rax+rax+00h]
0x18002104a  test    eax, eax
0x18002104c  jnz     short loc_18002106A
0x18002104e  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180021055  mov     edx, 1B8h; unsigned int
0x18002105a  and     [rsp+38h+var_18], 0
0x18002105f  mov     r9d, esi; int
0x180021062  mov     rcx, rbp; char *
0x180021065  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18002106a  mov     rcx, rbx
0x18002106d  mov     rbx, [rsp+38h+arg_0]
0x180021072  mov     rbp, [rsp+38h+arg_8]
0x180021077  add     rsp, 30h
0x18002107b  pop     rsi
0x18002107c  jmp     cs:__imp_LeaveCriticalSection
```
