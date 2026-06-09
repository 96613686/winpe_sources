# CClientContext::GetEndpointsMarkedToClose(CDynArray<void *,CDeallocateNone> *)

- ea: `0x1800054f4`
- end: `0x1800056f2`
- name: `?GetEndpointsMarkedToClose@CClientContext@@AEAAKPEAV?$CDynArray@PEAXVCDeallocateNone@@@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800036ac`
- `0x180004604`
- `0x180004b18`

## callees

- `0x180003170`
- `0x1800054f4`
- `0x180005850`
- `0x18000a960`
- `0x18003c514`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180005673`
- `KERNEL32!ReleaseSemaphore` at `0x18000569f`
- `KERNEL32!ReleaseSemaphore` at `0x180005673`
- `KERNEL32!ReleaseSemaphore` at `0x18000569f`
- `KERNEL32!GetCurrentThreadId` at `0x1800055d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800055d9`
- `KERNEL32!EnterCriticalSection` at `0x1800055cd`
- `KERNEL32!EnterCriticalSection` at `0x1800055cd`
- `KERNEL32!LeaveCriticalSection` at `0x1800056cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800056cb`

## string_xrefs

- `0x1800055e5`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800055f1`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180005621`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180005649`: `m_uActiveReaders == 0`
- `0x180005683`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x1800056af`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
__int64 __fastcall CClientContext::GetEndpointsMarkedToClose(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebp
  unsigned int v5; // edi
  __int64 v6; // rdx
  const char *v7; // rdx
  void *v8; // rcx
  LPCRITICAL_SECTION v9; // rbx
  int v10; // r9d
  int DebugInfo; // eax
  int v12; // r9d
  const char *v13; // r8
  unsigned int v14; // edx
  LONG LockSemaphore_high; // edx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-28h] BYREF
  int v18; // [rsp+38h] [rbp-20h]

  lpCriticalSection = (LPCRITICAL_SECTION)a1;
  v3 = 0;
  v18 = 0;
  CAutoWriterLock::Lock(&lpCriticalSection);
  v5 = 0;
  if ( *(_DWORD *)(a1 + 204) )
  {
    while ( 1 )
    {
      v6 = 0;
      if ( v5 < *(_DWORD *)(a1 + 204) )
        v6 = *(_QWORD *)(*(_QWORD *)(a1 + 192) + 8LL * v5);
      if ( v6 )
      {
        v3 = CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(a2);
        if ( ElValidateWin32(v3, v7, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x616u) )
          break;
      }
      if ( v5 < *(_DWORD *)(a1 + 204) )
        *(_QWORD *)(*(_QWORD *)(a1 + 192) + 8LL * v5) = 0;
      if ( ++v5 >= *(_DWORD *)(a1 + 204) )
        goto LABEL_9;
    }
  }
  else
  {
LABEL_9:
    v8 = *(void **)(a1 + 192);
    if ( v8 )
    {
      operator delete(v8);
      *(_QWORD *)(a1 + 192) = 0;
      *(_QWORD *)(a1 + 200) = 0;
    }
  }
  if ( v18 == 1 )
  {
    v9 = lpCriticalSection;
    EnterCriticalSection(lpCriticalSection);
    if ( LODWORD(v9[1].SpinCount) != GetCurrentThreadId() )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x195u,
        "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
        v10,
        0);
    DebugInfo = (int)v9[2].DebugInfo;
    if ( DebugInfo )
    {
      LODWORD(v9[2].DebugInfo) = DebugInfo - 1;
LABEL_27:
      LeaveCriticalSection(v9);
      return v3;
    }
    if ( HIDWORD(v9[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x1A1u,
        "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
        v10,
        0);
    v9[1].SpinCount = 0;
    LODWORD(v9[2].DebugInfo) = 0;
    if ( LODWORD(v9[2].LockSemaphore) )
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v10, 0);
    if ( LODWORD(v9[2].SpinCount) )
    {
      if ( ReleaseSemaphore(v9[1].OwningThread, 1, 0) )
        goto LABEL_27;
      v13 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
      v14 = 431;
    }
    else
    {
      LockSemaphore_high = HIDWORD(v9[2].LockSemaphore);
      if ( !LockSemaphore_high || ReleaseSemaphore(*(HANDLE *)&v9[1].LockCount, LockSemaphore_high, 0) )
        goto LABEL_27;
      v13 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
      v14 = 440;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v14, v13, v12, 0);
    goto LABEL_27;
  }
  return v3;
}

```

## disassembly

```asm
0x1800054f4  mov     rax, rsp
0x1800054f7  mov     [rax+8], rbx
0x1800054fb  mov     [rax+10h], rbp
0x1800054ff  mov     [rax+18h], rsi
0x180005503  push    rdi
0x180005504  push    r14
0x180005506  push    r15
0x180005508  sub     rsp, 40h
0x18000550c  mov     rbx, rcx
0x18000550f  mov     [rax-28h], rcx
0x180005513  xor     r15d, r15d
0x180005516  lea     rcx, [rax-28h]; this
0x18000551a  mov     ebp, r15d
0x18000551d  mov     [rax-20h], r15d
0x180005521  mov     r14, rdx
0x180005524  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180005529  mov     edi, r15d
0x18000552c  cmp     [rbx+0CCh], r15d
0x180005533  jbe     short loc_180005591
0x180005535  mov     rdx, r15
0x180005538  mov     esi, edi
0x18000553a  cmp     edi, [rbx+0CCh]
0x180005540  jnb     short loc_18000554D
0x180005542  mov     rax, [rbx+0C0h]
0x180005549  mov     rdx, [rax+rsi*8]
0x18000554d  test    rdx, rdx
0x180005550  jz      short loc_180005574
0x180005552  mov     rcx, r14
0x180005555  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x18000555a  mov     r9d, 616h; unsigned int
0x180005560  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180005567  mov     ecx, eax; unsigned int
0x180005569  mov     ebp, eax
0x18000556b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005570  test    eax, eax
0x180005572  jnz     short loc_1800055B0
0x180005574  cmp     edi, [rbx+0CCh]
0x18000557a  jnb     short loc_180005587
0x18000557c  mov     rcx, [rbx+0C0h]
0x180005583  mov     [rcx+rsi*8], r15
0x180005587  inc     edi
0x180005589  cmp     edi, [rbx+0CCh]
0x18000558f  jb      short loc_180005535
0x180005591  mov     rcx, [rbx+0C0h]; void *
0x180005598  test    rcx, rcx
0x18000559b  jz      short loc_1800055B0
0x18000559d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800055a2  mov     [rbx+0C0h], r15
0x1800055a9  mov     [rbx+0C8h], r15
0x1800055b0  mov     eax, [rsp+58h+var_20]
0x1800055b4  test    eax, eax
0x1800055b6  jz      loc_1800056D7
0x1800055bc  cmp     eax, 1
0x1800055bf  jnz     loc_1800056D7
0x1800055c5  mov     rbx, [rsp+58h+lpCriticalSection]
0x1800055ca  mov     rcx, rbx; lpCriticalSection
0x1800055cd  call    cs:__imp_EnterCriticalSection
0x1800055d4  nop     dword ptr [rax+rax+00h]
0x1800055d9  call    cs:__imp_GetCurrentThreadId
0x1800055e0  nop     dword ptr [rax+rax+00h]
0x1800055e5  lea     rdi, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800055ec  cmp     [rbx+48h], eax
0x1800055ef  jz      short loc_18000560A
0x1800055f1  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x1800055f8  mov     [rsp+58h+var_38], r15d; int
0x1800055fd  mov     edx, 195h; unsigned int
0x180005602  mov     rcx, rdi; char *
0x180005605  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000560a  mov     eax, [rbx+50h]
0x18000560d  test    eax, eax
0x18000560f  jz      short loc_18000561B
0x180005611  dec     eax
0x180005613  mov     [rbx+50h], eax
0x180005616  jmp     loc_1800056C8
0x18000561b  cmp     [rbx+4Ch], r15d
0x18000561f  jz      short loc_18000563A
0x180005621  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180005628  mov     [rsp+58h+var_38], r15d; int
0x18000562d  mov     edx, 1A1h; unsigned int
0x180005632  mov     rcx, rdi; char *
0x180005635  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000563a  xor     eax, eax
0x18000563c  mov     [rbx+48h], rax
0x180005640  mov     [rbx+50h], eax
0x180005643  cmp     [rbx+68h], r15d
0x180005647  jz      short loc_180005662
0x180005649  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x180005650  mov     [rsp+58h+var_38], r15d; int
0x180005655  mov     edx, 1A4h; unsigned int
0x18000565a  mov     rcx, rdi; char *
0x18000565d  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005662  cmp     [rbx+70h], r15d
0x180005666  jz      short loc_180005691
0x180005668  mov     rcx, [rbx+38h]; hSemaphore
0x18000566c  xor     r8d, r8d; lpPreviousCount
0x18000566f  lea     edx, [r8+1]; lReleaseCount
0x180005673  call    cs:__imp_ReleaseSemaphore
0x18000567a  nop     dword ptr [rax+rax+00h]
0x18000567f  test    eax, eax
0x180005681  jnz     short loc_1800056C8
0x180005683  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x18000568a  mov     edx, 1AFh
0x18000568f  jmp     short loc_1800056BB
0x180005691  mov     edx, [rbx+6Ch]; lReleaseCount
0x180005694  test    edx, edx
0x180005696  jz      short loc_1800056C8
0x180005698  mov     rcx, [rbx+30h]; hSemaphore
0x18000569c  xor     r8d, r8d; lpPreviousCount
0x18000569f  call    cs:__imp_ReleaseSemaphore
0x1800056a6  nop     dword ptr [rax+rax+00h]
0x1800056ab  test    eax, eax
0x1800056ad  jnz     short loc_1800056C8
0x1800056af  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x1800056b6  mov     edx, 1B8h; unsigned int
0x1800056bb  mov     rcx, rdi; char *
0x1800056be  mov     [rsp+58h+var_38], r15d; int
0x1800056c3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800056c8  mov     rcx, rbx; lpCriticalSection
0x1800056cb  call    cs:__imp_LeaveCriticalSection
0x1800056d2  nop     dword ptr [rax+rax+00h]
0x1800056d7  mov     rbx, [rsp+58h+arg_0]
0x1800056dc  mov     eax, ebp
0x1800056de  mov     rbp, [rsp+58h+arg_8]
0x1800056e3  mov     rsi, [rsp+58h+arg_10]
0x1800056e8  add     rsp, 40h
0x1800056ec  pop     r15
0x1800056ee  pop     r14
0x1800056f0  pop     rdi
0x1800056f1  retn
```
