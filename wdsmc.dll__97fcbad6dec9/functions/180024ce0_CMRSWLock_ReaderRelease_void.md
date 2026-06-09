# CMRSWLock::ReaderRelease(void)

- ea: `0x180024ce0`
- end: `0x180024de5`
- name: `?ReaderRelease@CMRSWLock@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000635c`
- `0x1800063e4`
- `0x1800070ac`
- `0x180007668`
- `0x1800077b0`
- `0x1800078a8`
- `0x180009260`
- `0x18000a5a4`
- `0x18000a880`
- `0x18000f1f4`
- `0x18000f560`
- `0x180018da4`
- `0x180018f20`

## callees

- `0x1800227d4`
- `0x180024a4c`
- `0x180024ce0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180024cf4`
- `KERNEL32!GetCurrentThreadId` at `0x180024cf4`
- `KERNEL32!LeaveCriticalSection` at `0x180024dde`
- `KERNEL32!EnterCriticalSection` at `0x180024cff`
- `KERNEL32!EnterCriticalSection` at `0x180024cff`
- `KERNEL32!ReleaseSemaphore` at `0x180024da6`
- `KERNEL32!ReleaseSemaphore` at `0x180024da6`

## string_xrefs

- `0x180024d21`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024d5c`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024dc0`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024db4`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180024d15`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180024d50`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

## pseudocode

```c
void __fastcall CMRSWLock::ReaderRelease(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // edi
  DWORD CurrentThreadId; // esi
  int v4; // r9d
  int SpinCount_high; // eax
  __int64 v6; // rcx
  _DWORD *OwningThread; // rdx
  int v8; // eax
  bool v9; // zf
  int v10; // r9d

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(this);
  if ( LODWORD(this[1].SpinCount) == CurrentThreadId )
  {
    SpinCount_high = HIDWORD(this[1].SpinCount);
    if ( !SpinCount_high )
    {
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x22Eu,
        "m_ActiveWriter.m_uNestedReaders > 0",
        v4,
        0);
      SpinCount_high = HIDWORD(this[1].SpinCount);
    }
    HIDWORD(this[1].SpinCount) = SpinCount_high - 1;
  }
  else
  {
    v6 = 0;
    while ( *((_DWORD *)this[2].OwningThread + 2 * v6) != CurrentThreadId )
    {
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 > this[2].LockCount )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x236u,
          "GetReaderSlot(uThreadId, &uIndex) == 0L",
          v4,
          0);
        goto LABEL_10;
      }
    }
    v2 = v6;
LABEL_10:
    OwningThread = this[2].OwningThread;
    v8 = OwningThread[2 * v2 + 1];
    if ( v8 )
    {
      OwningThread[2 * v2 + 1] = v8 - 1;
    }
    else
    {
      CMRSWLock::FreeReaderSlot((CMRSWLock *)this, CurrentThreadId, v2);
      v9 = LODWORD(this[2].LockSemaphore)-- == 1;
      if ( v9 && LODWORD(this[2].SpinCount) && !ReleaseSemaphore(this[1].OwningThread, 1, 0) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x251u,
          "ReleaseSemaphore(m_hReaderDone, 1, 0)",
          v10,
          0);
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180024ce0  mov     [rsp+arg_0], rbx
0x180024ce5  mov     [rsp+arg_8], rsi
0x180024cea  push    rdi
0x180024ceb  sub     rsp, 30h
0x180024cef  mov     rbx, rcx
0x180024cf2  xor     edi, edi
0x180024cf4  call    cs:__imp_GetCurrentThreadId
0x180024cfa  mov     rcx, rbx; lpCriticalSection
0x180024cfd  mov     esi, eax
0x180024cff  call    cs:__imp_EnterCriticalSection
0x180024d05  cmp     [rbx+48h], esi
0x180024d08  jnz     short loc_180024D3A
0x180024d0a  mov     eax, [rbx+4Ch]
0x180024d0d  test    eax, eax
0x180024d0f  jnz     short loc_180024D30
0x180024d11  and     [rsp+38h+var_18], edi
0x180024d15  lea     r8, aMActivewriterM_1; "m_ActiveWriter.m_uNestedReaders > 0"
0x180024d1c  mov     edx, 22Eh; unsigned int
0x180024d21  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024d28  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024d2d  mov     eax, [rbx+4Ch]
0x180024d30  dec     eax
0x180024d32  mov     [rbx+4Ch], eax
0x180024d35  jmp     loc_180024DCC
0x180024d3a  mov     rdx, [rbx+60h]
0x180024d3e  xor     ecx, ecx
0x180024d40  cmp     [rdx+rcx*8], esi
0x180024d43  jz      short loc_180024D6A
0x180024d45  inc     ecx
0x180024d47  cmp     ecx, [rbx+58h]
0x180024d4a  jbe     short loc_180024D40
0x180024d4c  and     [rsp+38h+var_18], edi
0x180024d50  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x180024d57  mov     edx, 236h; unsigned int
0x180024d5c  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024d63  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024d68  jmp     short loc_180024D6C
0x180024d6a  mov     edi, ecx
0x180024d6c  mov     rdx, [rbx+60h]
0x180024d70  mov     ecx, edi
0x180024d72  mov     eax, [rdx+rcx*8+4]
0x180024d76  test    eax, eax
0x180024d78  jz      short loc_180024D82
0x180024d7a  dec     eax
0x180024d7c  mov     [rdx+rcx*8+4], eax
0x180024d80  jmp     short loc_180024DCC
0x180024d82  mov     r8d, edi; unsigned int
0x180024d85  mov     edx, esi; unsigned int
0x180024d87  mov     rcx, rbx; this
0x180024d8a  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x180024d8f  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x180024d93  jnz     short loc_180024DCC
0x180024d95  cmp     dword ptr [rbx+70h], 0
0x180024d99  jbe     short loc_180024DCC
0x180024d9b  mov     rcx, [rbx+38h]; hSemaphore
0x180024d9f  xor     r8d, r8d; lpPreviousCount
0x180024da2  lea     edx, [r8+1]; lReleaseCount
0x180024da6  call    cs:__imp_ReleaseSemaphore
0x180024dac  test    eax, eax
0x180024dae  jnz     short loc_180024DCC
0x180024db0  and     [rsp+38h+var_18], eax
0x180024db4  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180024dbb  mov     edx, 251h; unsigned int
0x180024dc0  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024dc7  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024dcc  mov     rcx, rbx
0x180024dcf  mov     rbx, [rsp+38h+arg_0]
0x180024dd4  mov     rsi, [rsp+38h+arg_8]
0x180024dd9  add     rsp, 30h
0x180024ddd  pop     rdi
0x180024dde  jmp     cs:__imp_LeaveCriticalSection
```
