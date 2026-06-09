# CMRSWLock::WriterRelease(void)

- ea: `0x180024b0c`
- end: `0x180024c0e`
- name: `?WriterRelease@CMRSWLock@@QEAAXXZ`
- size: `258`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800053a0`
- `0x180005a4c`
- `0x180005e28`
- `0x180006488`
- `0x1800067f0`
- `0x180006bc4`
- `0x180006e48`
- `0x180006f84`
- `0x1800071a0`
- `0x180007278`
- `0x180007358`
- `0x1800074bc`
- `0x180007a24`
- `0x180008b58`
- `0x18000a97c`

## callees

- `0x1800227d4`
- `0x180024b0c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180024b1f`
- `KERNEL32!GetCurrentThreadId` at `0x180024b1f`
- `KERNEL32!LeaveCriticalSection` at `0x180024c07`
- `KERNEL32!EnterCriticalSection` at `0x180024b19`
- `KERNEL32!EnterCriticalSection` at `0x180024b19`
- `KERNEL32!ReleaseSemaphore` at `0x180024bb1`
- `KERNEL32!ReleaseSemaphore` at `0x180024bd7`
- `KERNEL32!ReleaseSemaphore` at `0x180024bb1`
- `KERNEL32!ReleaseSemaphore` at `0x180024bd7`

## string_xrefs

- `0x180024b25`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024b36`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180024b66`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180024b8c`: `m_uActiveReaders == 0`
- `0x180024bbb`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180024be1`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

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
0x180024b0c  mov     [rsp+arg_0], rbx
0x180024b11  push    rsi
0x180024b12  sub     rsp, 30h
0x180024b16  mov     rbx, rcx
0x180024b19  call    cs:__imp_EnterCriticalSection
0x180024b1f  call    cs:__imp_GetCurrentThreadId
0x180024b25  lea     rsi, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024b2c  cmp     [rbx+48h], eax
0x180024b2f  jz      short loc_180024B4A
0x180024b31  and     [rsp+38h+var_18], 0
0x180024b36  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180024b3d  mov     edx, 195h; unsigned int
0x180024b42  mov     rcx, rsi; char *
0x180024b45  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024b4a  mov     eax, [rbx+50h]
0x180024b4d  test    eax, eax
0x180024b4f  jz      short loc_180024B5B
0x180024b51  dec     eax
0x180024b53  mov     [rbx+50h], eax
0x180024b56  jmp     loc_180024BFA
0x180024b5b  cmp     dword ptr [rbx+4Ch], 0
0x180024b5f  jz      short loc_180024B7A
0x180024b61  and     [rsp+38h+var_18], 0
0x180024b66  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180024b6d  mov     edx, 1A1h; unsigned int
0x180024b72  mov     rcx, rsi; char *
0x180024b75  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024b7a  xor     eax, eax
0x180024b7c  mov     [rbx+48h], rax
0x180024b80  mov     [rbx+50h], eax
0x180024b83  cmp     [rbx+68h], eax
0x180024b86  jz      short loc_180024BA0
0x180024b88  and     [rsp+38h+var_18], eax
0x180024b8c  lea     r8, aMUactivereader; "m_uActiveReaders == 0"
0x180024b93  mov     edx, 1A4h; unsigned int
0x180024b98  mov     rcx, rsi; char *
0x180024b9b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024ba0  cmp     dword ptr [rbx+70h], 0
0x180024ba4  jz      short loc_180024BC9
0x180024ba6  mov     rcx, [rbx+38h]; hSemaphore
0x180024baa  xor     r8d, r8d; lpPreviousCount
0x180024bad  lea     edx, [r8+1]; lReleaseCount
0x180024bb1  call    cs:__imp_ReleaseSemaphore
0x180024bb7  test    eax, eax
0x180024bb9  jnz     short loc_180024BFA
0x180024bbb  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180024bc2  mov     edx, 1AFh
0x180024bc7  jmp     short loc_180024BED
0x180024bc9  mov     edx, [rbx+6Ch]; lReleaseCount
0x180024bcc  test    edx, edx
0x180024bce  jz      short loc_180024BFA
0x180024bd0  mov     rcx, [rbx+30h]; hSemaphore
0x180024bd4  xor     r8d, r8d; lpPreviousCount
0x180024bd7  call    cs:__imp_ReleaseSemaphore
0x180024bdd  test    eax, eax
0x180024bdf  jnz     short loc_180024BFA
0x180024be1  lea     r8, aReleasesemapho; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180024be8  mov     edx, 1B8h; unsigned int
0x180024bed  and     [rsp+38h+var_18], 0
0x180024bf2  mov     rcx, rsi; char *
0x180024bf5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024bfa  mov     rcx, rbx
0x180024bfd  mov     rbx, [rsp+38h+arg_0]
0x180024c02  add     rsp, 30h
0x180024c06  pop     rsi
0x180024c07  jmp     cs:__imp_LeaveCriticalSection
```
