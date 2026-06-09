# CMRSWLock::ReaderRelease(void)

- ea: `0x1800134f4`
- end: `0x1800135f9`
- name: `?ReaderRelease@CMRSWLock@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`
- `0x1800042f4`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x180006dfc`

## callees

- `0x180012f34`
- `0x180013254`
- `0x1800134f4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180013513`
- `KERNEL32!EnterCriticalSection` at `0x180013513`
- `KERNEL32!LeaveCriticalSection` at `0x1800135f2`
- `KERNEL32!GetCurrentThreadId` at `0x180013508`
- `KERNEL32!GetCurrentThreadId` at `0x180013508`
- `KERNEL32!ReleaseSemaphore` at `0x1800135ba`
- `KERNEL32!ReleaseSemaphore` at `0x1800135ba`

## string_xrefs

- `0x180013535`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180013570`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800135d4`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800135c8`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180013529`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180013564`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

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
0x1800134f4  mov     [rsp+arg_0], rbx
0x1800134f9  mov     [rsp+arg_8], rsi
0x1800134fe  push    rdi
0x1800134ff  sub     rsp, 30h
0x180013503  mov     rbx, rcx
0x180013506  xor     edi, edi
0x180013508  call    cs:__imp_GetCurrentThreadId
0x18001350e  mov     rcx, rbx; lpCriticalSection
0x180013511  mov     esi, eax
0x180013513  call    cs:__imp_EnterCriticalSection
0x180013519  cmp     [rbx+48h], esi
0x18001351c  jnz     short loc_18001354E
0x18001351e  mov     eax, [rbx+4Ch]
0x180013521  test    eax, eax
0x180013523  jnz     short loc_180013544
0x180013525  and     [rsp+38h+var_18], edi
0x180013529  lea     r8, aMActivewriterM_1; "m_ActiveWriter.m_uNestedReaders > 0"
0x180013530  mov     edx, 22Eh; unsigned int
0x180013535  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001353c  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180013541  mov     eax, [rbx+4Ch]
0x180013544  dec     eax
0x180013546  mov     [rbx+4Ch], eax
0x180013549  jmp     loc_1800135E0
0x18001354e  mov     rdx, [rbx+60h]
0x180013552  xor     ecx, ecx
0x180013554  cmp     [rdx+rcx*8], esi
0x180013557  jz      short loc_18001357E
0x180013559  inc     ecx
0x18001355b  cmp     ecx, [rbx+58h]
0x18001355e  jbe     short loc_180013554
0x180013560  and     [rsp+38h+var_18], edi
0x180013564  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x18001356b  mov     edx, 236h; unsigned int
0x180013570  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013577  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001357c  jmp     short loc_180013580
0x18001357e  mov     edi, ecx
0x180013580  mov     rdx, [rbx+60h]
0x180013584  mov     ecx, edi
0x180013586  mov     eax, [rdx+rcx*8+4]
0x18001358a  test    eax, eax
0x18001358c  jz      short loc_180013596
0x18001358e  dec     eax
0x180013590  mov     [rdx+rcx*8+4], eax
0x180013594  jmp     short loc_1800135E0
0x180013596  mov     r8d, edi; unsigned int
0x180013599  mov     edx, esi; unsigned int
0x18001359b  mov     rcx, rbx; this
0x18001359e  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x1800135a3  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x1800135a7  jnz     short loc_1800135E0
0x1800135a9  cmp     dword ptr [rbx+70h], 0
0x1800135ad  jbe     short loc_1800135E0
0x1800135af  mov     rcx, [rbx+38h]; hSemaphore
0x1800135b3  xor     r8d, r8d; lpPreviousCount
0x1800135b6  lea     edx, [r8+1]; lReleaseCount
0x1800135ba  call    cs:__imp_ReleaseSemaphore
0x1800135c0  test    eax, eax
0x1800135c2  jnz     short loc_1800135E0
0x1800135c4  and     [rsp+38h+var_18], eax
0x1800135c8  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x1800135cf  mov     edx, 251h; unsigned int
0x1800135d4  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800135db  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800135e0  mov     rcx, rbx
0x1800135e3  mov     rbx, [rsp+38h+arg_0]
0x1800135e8  mov     rsi, [rsp+38h+arg_8]
0x1800135ed  add     rsp, 30h
0x1800135f1  pop     rdi
0x1800135f2  jmp     cs:__imp_LeaveCriticalSection
```
