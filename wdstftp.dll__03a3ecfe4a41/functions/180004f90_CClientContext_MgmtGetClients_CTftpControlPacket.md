# CClientContext::MgmtGetClients(CTftpControlPacket *)

- ea: `0x180004f90`
- end: `0x1800054eb`
- name: `?MgmtGetClients@CClientContext@@QEAAKPEAVCTftpControlPacket@@@Z`
- size: `1371`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CTftpControlPacket *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002784`

## callees

- `0x180004f90`
- `0x18000a960`
- `0x180039fac`
- `0x18003a878`
- `0x18003aa68`
- `0x18003ab60`
- `0x18003bd24`
- `0x18003c514`
- `0x18003ce78`
- `0x180060808`
- `0x180060e4e`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x1800050cc`
- `KERNEL32!ReleaseSemaphore` at `0x180005451`
- `KERNEL32!ReleaseSemaphore` at `0x18000549f`
- `KERNEL32!ReleaseSemaphore` at `0x1800050cc`
- `KERNEL32!ReleaseSemaphore` at `0x180005451`
- `KERNEL32!ReleaseSemaphore` at `0x18000549f`
- `KERNEL32!GetCurrentThreadId` at `0x180005003`
- `KERNEL32!GetCurrentThreadId` at `0x180005358`
- `KERNEL32!GetCurrentThreadId` at `0x180005003`
- `KERNEL32!GetCurrentThreadId` at `0x180005358`
- `KERNEL32!EnterCriticalSection` at `0x180005014`
- `KERNEL32!EnterCriticalSection` at `0x1800051b4`
- `KERNEL32!EnterCriticalSection` at `0x18000536a`
- `KERNEL32!EnterCriticalSection` at `0x180005014`
- `KERNEL32!EnterCriticalSection` at `0x1800051b4`
- `KERNEL32!EnterCriticalSection` at `0x18000536a`
- `KERNEL32!LeaveCriticalSection` at `0x1800050f8`
- `KERNEL32!LeaveCriticalSection` at `0x18000524d`
- `KERNEL32!LeaveCriticalSection` at `0x1800054cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800050f8`
- `KERNEL32!LeaveCriticalSection` at `0x18000524d`
- `KERNEL32!LeaveCriticalSection` at `0x1800054cb`

## string_xrefs

- `0x180005028`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180005062`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180005400`: `m_pReaderSlots[uIndex].m_uThreadId == uThreadId`
- `0x180005424`: `m_pReaderSlots[uIndex].m_uNestedReaders == 0`
- `0x180005461`: `ReleaseSemaphore(m_hReaderSlots, 1, 0)`
- `0x1800050dc`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x1800054af`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180005033`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180005383`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180005075`: `GetReaderSlot(uThreadId, &uIndex) == 0L`
- `0x1800053bf`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

## pseudocode

```c
__int64 __fastcall CClientContext::MgmtGetClients(struct _RTL_CRITICAL_SECTION *this, struct CTftpControlPacket *a2)
{
  unsigned int v3; // r12d
  unsigned int v4; // r14d
  unsigned int OwningThread_high; // eax
  unsigned int v6; // r15d
  __int64 *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // ebx
  DWORD CurrentThreadId; // edi
  int v12; // r9d
  int SpinCount_high; // eax
  unsigned int v14; // ecx
  _DWORD *OwningThread; // rdx
  int v16; // eax
  bool v17; // zf
  int v18; // r9d
  unsigned __int64 v19; // rax
  struct _WDSTFTP_CLIENT *v20; // rax
  struct _WDSTFTP_CLIENT *v21; // r13
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // r15
  char *v25; // rbx
  unsigned int v26; // ebx
  const char *v27; // rdx
  const char *v28; // rdx
  int v29; // r14d
  const unsigned __int16 *v30; // rdx
  const char *v31; // rdx
  __int64 v32; // rdi
  void **v33; // rbx
  unsigned int v34; // edi
  DWORD v35; // r14d
  int v36; // r9d
  int v37; // eax
  _DWORD *v38; // r9
  unsigned int v39; // ecx
  _DWORD *v40; // rcx
  int v41; // eax
  const char *v42; // r8
  unsigned int v43; // edx
  int v44; // r9d
  __int64 v47; // [rsp+A0h] [rbp+18h]
  __int64 v48; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  CMRSWLock::ReaderLock(this);
  v4 = 0;
  CMRSWLock::ReaderLock(this);
  OwningThread_high = HIDWORD(this[4].OwningThread);
  v6 = 8;
  if ( OwningThread_high )
  {
    v7 = *(__int64 **)&this[4].LockCount;
    v8 = OwningThread_high;
    do
    {
      v9 = *v7++;
      v4 += *(_DWORD *)(v9 + 28);
      --v8;
    }
    while ( v8 );
  }
  v10 = 0;
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
        v12,
        0);
      SpinCount_high = HIDWORD(this[1].SpinCount);
    }
    HIDWORD(this[1].SpinCount) = SpinCount_high - 1;
  }
  else
  {
    v14 = 0;
    while ( *((_DWORD *)this[2].OwningThread + 2 * v14) != CurrentThreadId )
    {
      if ( ++v14 > this[2].LockCount )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x236u,
          "GetReaderSlot(uThreadId, &uIndex) == 0L",
          v12,
          0);
        goto LABEL_13;
      }
    }
    v10 = v14;
LABEL_13:
    OwningThread = this[2].OwningThread;
    v16 = OwningThread[2 * v10 + 1];
    if ( v16 )
    {
      OwningThread[2 * v10 + 1] = v16 - 1;
    }
    else
    {
      CMRSWLock::FreeReaderSlot((CMRSWLock *)this, CurrentThreadId, v10);
      v17 = LODWORD(this[2].LockSemaphore)-- == 1;
      if ( v17 && LODWORD(this[2].SpinCount) && !ReleaseSemaphore(this[1].OwningThread, 1, 0) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x251u,
          "ReleaseSemaphore(m_hReaderDone, 1, 0)",
          v18,
          0);
    }
  }
  LeaveCriticalSection(this);
  v19 = 56LL * v4;
  if ( !is_mul_ok(v4, 0x38u) )
    v19 = -1;
  v20 = (struct _WDSTFTP_CLIENT *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  if ( !v20 )
    goto LABEL_38;
  memset_0(v20, 0, 56LL * v4);
  v22 = 0;
  if ( HIDWORD(this[4].OwningThread) )
  {
    while ( 1 )
    {
      v23 = *(_QWORD *)(*(_QWORD *)&this[4].LockCount + 8 * v22);
      v48 = v23;
      v24 = 0;
      if ( *(_DWORD *)(v23 + 28) )
        break;
LABEL_26:
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= HIDWORD(this[4].OwningThread) )
        goto LABEL_27;
    }
    while ( 1 )
    {
      v47 = *(_QWORD *)(*(_QWORD *)(v23 + 16) + 8 * v24);
      v25 = (char *)v21 + 56 * v3;
      EnterCriticalSection((LPCRITICAL_SECTION)(v47 + 24));
      memset_0(v25, 0, 0x38u);
      *((_QWORD *)v25 + 5) = *(_QWORD *)(v47 + 2432);
      *((_DWORD *)v25 + 12) = *(_DWORD *)(v47 + 2332);
      *((_QWORD *)v25 + 4) = *(_QWORD *)(v47 + 2424);
      *((_DWORD *)v25 + 7) = *(_DWORD *)(v47 + 2340);
      *((_DWORD *)v25 + 13) = *(_DWORD *)(v47 + 2336);
      *((_DWORD *)v25 + 6) = *(_DWORD *)(v47 + 1152);
      memmove_0(v25 + 8, (const void *)(v47 + 1136), 0x10u);
      v26 = DuplicateStringW(*(const unsigned __int16 **)(v47 + 2376), (unsigned __int16 **)v25);
      ElValidateWin32(v26, v27, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x8DDu);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v47 + 24));
      if ( ElValidateWin32(v26, v28, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x5D7u) )
        break;
      v23 = v48;
      ++v3;
      v24 = (unsigned int)(v24 + 1);
      if ( (unsigned int)v24 >= *(_DWORD *)(v48 + 28) )
        goto LABEL_26;
    }
    v6 = v26;
    v29 = 1;
  }
  else
  {
LABEL_27:
    v29 = 0;
    CMRSWLock::ReaderRelease((CMRSWLock *)this);
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(0x10000u, L"CClientContext::MgmtGetClients: TFTP client list contains %u client(s)", v3);
    v6 = CTftpControlPacket::AddClients(a2, v30, v21, v3);
    ElValidateWin32(v6, v31, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x5E9u);
  }
  if ( v3 )
  {
    v32 = v3;
    v33 = (void **)v21;
    do
    {
      if ( v33 && *v33 )
      {
        operator delete(*v33);
        *v33 = 0;
      }
      v33 += 7;
      --v32;
    }
    while ( v32 );
  }
  operator delete(v21);
  if ( v29 )
  {
LABEL_38:
    v34 = 0;
    v35 = GetCurrentThreadId();
    EnterCriticalSection(this);
    if ( LODWORD(this[1].SpinCount) == v35 )
    {
      v37 = HIDWORD(this[1].SpinCount);
      if ( !v37 )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x22Eu,
          "m_ActiveWriter.m_uNestedReaders > 0",
          v36,
          0);
        v37 = HIDWORD(this[1].SpinCount);
      }
      HIDWORD(this[1].SpinCount) = v37 - 1;
      goto LABEL_62;
    }
    v38 = this[2].OwningThread;
    v39 = 0;
    while ( v38[2 * v39] != v35 )
    {
      if ( ++v39 > this[2].LockCount )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x236u,
          "GetReaderSlot(uThreadId, &uIndex) == 0L",
          (int)v38,
          0);
        goto LABEL_47;
      }
    }
    v34 = v39;
LABEL_47:
    v40 = this[2].OwningThread;
    v41 = v40[2 * v34 + 1];
    if ( v41 )
    {
      v40[2 * v34 + 1] = v41 - 1;
LABEL_62:
      LeaveCriticalSection(this);
      return v6;
    }
    if ( v34 >= HIDWORD(this[2].DebugInfo) )
    {
      v42 = "0";
      v43 = 286;
    }
    else
    {
      if ( v40[2 * v34] != v35 )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x109u,
          "m_pReaderSlots[uIndex].m_uThreadId == uThreadId",
          (int)v38,
          0);
        v40 = this[2].OwningThread;
      }
      if ( v40[2 * v34 + 1] )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x10Eu,
          "m_pReaderSlots[uIndex].m_uNestedReaders == 0",
          (int)v38,
          0);
        v40 = this[2].OwningThread;
      }
      *(_QWORD *)&v40[2 * v34] = 0;
      if ( ReleaseSemaphore(this[1].LockSemaphore, 1, 0) )
        goto LABEL_58;
      v42 = "ReleaseSemaphore(m_hReaderSlots, 1, 0)";
      v43 = 282;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v43, v42, (int)v38, 0);
LABEL_58:
    v17 = LODWORD(this[2].LockSemaphore)-- == 1;
    if ( v17 && LODWORD(this[2].SpinCount) && !ReleaseSemaphore(this[1].OwningThread, 1, 0) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x251u,
        "ReleaseSemaphore(m_hReaderDone, 1, 0)",
        v44,
        0);
    goto LABEL_62;
  }
  return v6;
}

```

## disassembly

```asm
0x180004f90  mov     [rsp+arg_8], rdx
0x180004f95  push    rbx
0x180004f96  push    rbp
0x180004f97  push    rsi
0x180004f98  push    rdi
0x180004f99  push    r12
0x180004f9b  push    r13
0x180004f9d  push    r14
0x180004f9f  push    r15
0x180004fa1  sub     rsp, 48h
0x180004fa5  xor     r13d, r13d
0x180004fa8  mov     rsi, rcx
0x180004fab  mov     r12d, r13d
0x180004fae  mov     [rsp+88h+arg_18], r13
0x180004fb6  mov     [rsp+88h+arg_10], r13
0x180004fbe  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180004fc3  mov     rcx, rsi; lpCriticalSection
0x180004fc6  mov     [rsp+88h+arg_0], 1
0x180004fd1  mov     r14d, r13d
0x180004fd4  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180004fd9  mov     eax, [rsi+0B4h]
0x180004fdf  lea     r15d, [r13+8]
0x180004fe3  test    eax, eax
0x180004fe5  jz      short loc_180005000
0x180004fe7  mov     rcx, [rsi+0A8h]
0x180004fee  mov     edx, eax
0x180004ff0  mov     rax, [rcx]
0x180004ff3  add     rcx, r15
0x180004ff6  add     r14d, [rax+1Ch]
0x180004ffa  sub     rdx, 1
0x180004ffe  jnz     short loc_180004FF0
0x180005000  mov     ebx, r13d
0x180005003  call    cs:__imp_GetCurrentThreadId
0x18000500a  nop     dword ptr [rax+rax+00h]
0x18000500f  mov     rcx, rsi; lpCriticalSection
0x180005012  mov     edi, eax
0x180005014  call    cs:__imp_EnterCriticalSection
0x18000501b  nop     dword ptr [rax+rax+00h]
0x180005020  cmp     [rsi+48h], edi
0x180005023  jnz     short loc_180005059
0x180005025  mov     eax, [rsi+4Ch]
0x180005028  lea     rbp, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000502f  test    eax, eax
0x180005031  jnz     short loc_18000504F
0x180005033  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders > 0"
0x18000503a  mov     [rsp+88h+var_68], r13d; int
0x18000503f  mov     edx, 22Eh; unsigned int
0x180005044  mov     rcx, rbp; char *
0x180005047  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000504c  mov     eax, [rsi+4Ch]
0x18000504f  dec     eax
0x180005051  mov     [rsi+4Ch], eax
0x180005054  jmp     loc_1800050F5
0x180005059  mov     rdx, [rsi+60h]
0x18000505d  mov     ecx, r13d
0x180005060  mov     eax, ecx
0x180005062  lea     rbp, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180005069  cmp     [rdx+rax*8], edi
0x18000506c  jz      short loc_180005090
0x18000506e  inc     ecx
0x180005070  cmp     ecx, [rsi+58h]
0x180005073  jbe     short loc_180005060
0x180005075  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x18000507c  mov     [rsp+88h+var_68], r13d; int
0x180005081  mov     edx, 236h; unsigned int
0x180005086  mov     rcx, rbp; char *
0x180005089  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000508e  jmp     short loc_180005092
0x180005090  mov     ebx, ecx
0x180005092  mov     rdx, [rsi+60h]
0x180005096  mov     ecx, ebx
0x180005098  mov     eax, [rdx+rcx*8+4]
0x18000509c  test    eax, eax
0x18000509e  jz      short loc_1800050A8
0x1800050a0  dec     eax
0x1800050a2  mov     [rdx+rcx*8+4], eax
0x1800050a6  jmp     short loc_1800050F5
0x1800050a8  mov     r8d, ebx; unsigned int
0x1800050ab  mov     edx, edi; unsigned int
0x1800050ad  mov     rcx, rsi; this
0x1800050b0  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x1800050b5  add     dword ptr [rsi+68h], 0FFFFFFFFh
0x1800050b9  jnz     short loc_1800050F5
0x1800050bb  cmp     [rsi+70h], r13d
0x1800050bf  jbe     short loc_1800050F5
0x1800050c1  mov     rcx, [rsi+38h]; hSemaphore
0x1800050c5  xor     r8d, r8d; lpPreviousCount
0x1800050c8  lea     edx, [r8+1]; lReleaseCount
0x1800050cc  call    cs:__imp_ReleaseSemaphore
0x1800050d3  nop     dword ptr [rax+rax+00h]
0x1800050d8  test    eax, eax
0x1800050da  jnz     short loc_1800050F5
0x1800050dc  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x1800050e3  mov     [rsp+88h+var_68], r13d; int
0x1800050e8  mov     edx, 251h; unsigned int
0x1800050ed  mov     rcx, rbp; char *
0x1800050f0  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800050f5  mov     rcx, rsi; lpCriticalSection
0x1800050f8  call    cs:__imp_LeaveCriticalSection
0x1800050ff  nop     dword ptr [rax+rax+00h]
0x180005104  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000510b  mov     ebx, r14d
0x18000510e  mov     eax, 38h ; '8'
0x180005113  mul     rbx
0x180005116  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000511d  cmovo   rax, rcx
0x180005121  mov     rcx, rax; unsigned __int64
0x180005124  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005129  mov     r13, rax
0x18000512c  test    rax, rax
0x18000512f  jnz     short loc_18000513E
0x180005131  mov     r14d, [rsp+88h+arg_0]
0x180005139  jmp     loc_180005349
0x18000513e  imul    r8, rbx, 38h ; '8'; Size
0x180005142  xor     edx, edx; Val
0x180005144  mov     rcx, r13; void *
0x180005147  call    memset_0
0x18000514c  xor     r14d, r14d
0x18000514f  cmp     [rsi+0B4h], r12d
0x180005156  jbe     loc_1800052A1
0x18000515c  mov     rax, r12
0x18000515f  cmp     r14d, [rsi+0B4h]
0x180005166  jnb     short loc_18000517B
0x180005168  mov     rax, [rsi+0A8h]
0x18000516f  mov     rax, [rax+r14*8]
0x180005173  mov     [rsp+88h+arg_18], rax
0x18000517b  xor     r15d, r15d
0x18000517e  cmp     [rax+1Ch], r15d
0x180005182  jbe     loc_180005291
0x180005188  cmp     r15d, [rax+1Ch]
0x18000518c  jnb     short loc_18000519E
0x18000518e  mov     rax, [rax+10h]
0x180005192  mov     rax, [rax+r15*8]
0x180005196  mov     [rsp+88h+arg_10], rax
0x18000519e  mov     rdi, [rsp+88h+arg_10]
0x1800051a6  mov     eax, r12d
0x1800051a9  imul    rbx, rax, 38h ; '8'
0x1800051ad  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800051b1  add     rbx, r13
0x1800051b4  call    cs:__imp_EnterCriticalSection
0x1800051bb  nop     dword ptr [rax+rax+00h]
0x1800051c0  xor     edx, edx; Val
0x1800051c2  mov     rcx, rbx; void *
0x1800051c5  lea     r8d, [rdx+38h]; Size
0x1800051c9  call    memset_0
0x1800051ce  mov     rcx, rdi
0x1800051d1  mov     r8d, 10h; Size
0x1800051d7  mov     rax, [rcx+980h]
0x1800051de  lea     rdx, [rcx+470h]; Src
0x1800051e5  mov     [rbx+28h], rax
0x1800051e9  mov     eax, [rcx+91Ch]
0x1800051ef  mov     [rbx+30h], eax
0x1800051f2  mov     rax, [rcx+978h]
0x1800051f9  mov     [rbx+20h], rax
0x1800051fd  mov     eax, [rcx+924h]
0x180005203  mov     [rbx+1Ch], eax
0x180005206  mov     eax, [rcx+920h]
0x18000520c  mov     [rbx+34h], eax
0x18000520f  mov     eax, [rcx+480h]
0x180005215  lea     rcx, [rbx+8]; void *
0x180005219  mov     [rbx+18h], eax
0x18000521c  call    memmove_0
0x180005221  mov     rax, rdi
0x180005224  mov     rdx, rbx; unsigned __int16 **
0x180005227  mov     rcx, [rax+948h]; unsigned __int16 *
0x18000522e  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180005233  mov     r9d, 8DDh; unsigned int
0x180005239  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180005240  mov     ecx, eax; unsigned int
0x180005242  mov     ebx, eax
0x180005244  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005249  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000524d  call    cs:__imp_LeaveCriticalSection
0x180005254  nop     dword ptr [rax+rax+00h]
0x180005259  mov     r9d, 5D7h; unsigned int
0x18000525f  mov     dword ptr [rsp+88h+var_58], ebx
0x180005263  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000526a  mov     ecx, ebx; unsigned int
0x18000526c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005271  test    eax, eax
0x180005273  jnz     loc_1800052F9
0x180005279  mov     rax, [rsp+88h+arg_18]
0x180005281  inc     r12d
0x180005284  inc     r15d
0x180005287  cmp     r15d, [rax+1Ch]
0x18000528b  jb      loc_18000518E
0x180005291  inc     r14d
0x180005294  cmp     r14d, [rsi+0B4h]
0x18000529b  jb      loc_180005168
0x1800052a1  mov     rcx, rsi; this
0x1800052a4  xor     r14d, r14d
0x1800052a7  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x1800052ac  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800052b3  test    rax, rax
0x1800052b6  jz      short loc_1800052CD
0x1800052b8  mov     r8d, r12d
0x1800052bb  lea     rdx, aCclientcontext; "CClientContext::MgmtGetClients: TFTP cl"...
0x1800052c2  mov     ecx, 10000h
0x1800052c7  call    cs:__guard_dispatch_icall_fptr
0x1800052cd  mov     rcx, [rsp+88h+arg_8]; this
0x1800052d5  mov     r9d, r12d; unsigned int
0x1800052d8  mov     r8, r13; struct _WDSTFTP_CLIENT *
0x1800052db  call    ?AddClients@CTftpControlPacket@@QEAAKPEBGPEAU_WDSTFTP_CLIENT@@K@Z; CTftpControlPacket::AddClients(ushort const *,_WDSTFTP_CLIENT *,ulong)
0x1800052e0  mov     r9d, 5E9h; unsigned int
0x1800052e6  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800052ed  mov     ecx, eax; unsigned int
0x1800052ef  mov     r15d, eax
0x1800052f2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800052f7  jmp     short loc_180005306
0x1800052f9  mov     r15, [rsp+88h+var_58]
0x1800052fe  mov     r14d, [rsp+88h+arg_0]
0x180005306  test    r12d, r12d
0x180005309  jz      short loc_180005335
0x18000530b  mov     edi, r12d
0x18000530e  mov     rbx, r13
0x180005311  xor     r12d, r12d
0x180005314  test    rbx, rbx
0x180005317  jz      short loc_180005329
0x180005319  mov     rcx, [rbx]; void *
0x18000531c  test    rcx, rcx
0x18000531f  jz      short loc_180005329
0x180005321  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005326  mov     [rbx], r12
0x180005329  add     rbx, 38h ; '8'
0x18000532d  sub     rdi, 1
0x180005331  jnz     short loc_180005314
0x180005333  jmp     short loc_180005338
0x180005335  xor     r12d, r12d
0x180005338  mov     rcx, r13; void *
0x18000533b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005340  test    r14d, r14d
0x180005343  jz      loc_1800054D7
0x180005349  lea     eax, [r14-1]
0x18000534d  test    eax, eax
0x18000534f  jnz     loc_1800054D7
0x180005355  mov     edi, r12d
0x180005358  call    cs:__imp_GetCurrentThreadId
0x18000535f  nop     dword ptr [rax+rax+00h]
0x180005364  mov     rcx, rsi; lpCriticalSection
0x180005367  mov     r14d, eax
0x18000536a  call    cs:__imp_EnterCriticalSection
0x180005371  nop     dword ptr [rax+rax+00h]
0x180005376  cmp     [rsi+48h], r14d
0x18000537a  jnz     short loc_1800053A9
0x18000537c  mov     eax, [rsi+4Ch]
0x18000537f  test    eax, eax
0x180005381  jnz     short loc_18000539F
0x180005383  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders > 0"
0x18000538a  mov     [rsp+88h+var_68], r12d; int
0x18000538f  mov     edx, 22Eh; unsigned int
0x180005394  mov     rcx, rbp; char *
0x180005397  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000539c  mov     eax, [rsi+4Ch]
0x18000539f  dec     eax
0x1800053a1  mov     [rsi+4Ch], eax
0x1800053a4  jmp     loc_1800054C8
0x1800053a9  mov     r9, [rsi+60h]; int
0x1800053ad  mov     ecx, r12d
0x1800053b0  mov     eax, ecx
0x1800053b2  cmp     [r9+rax*8], r14d
0x1800053b6  jz      short loc_1800053DA
0x1800053b8  inc     ecx
0x1800053ba  cmp     ecx, [rsi+58h]
0x1800053bd  jbe     short loc_1800053B0
0x1800053bf  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x1800053c6  mov     [rsp+88h+var_68], r12d; int
0x1800053cb  mov     edx, 236h; unsigned int
0x1800053d0  mov     rcx, rbp; char *
0x1800053d3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800053d8  jmp     short loc_1800053DC
0x1800053da  mov     edi, ecx
0x1800053dc  mov     rcx, [rsi+60h]
0x1800053e0  mov     ebx, edi
0x1800053e2  mov     eax, [rcx+rbx*8+4]
0x1800053e6  test    eax, eax
0x1800053e8  jz      short loc_1800053F5
0x1800053ea  dec     eax
0x1800053ec  mov     [rcx+rbx*8+4], eax
0x1800053f0  jmp     loc_1800054C8
0x1800053f5  cmp     edi, [rsi+54h]
0x1800053f8  jnb     short loc_18000546F
0x1800053fa  cmp     [rcx+rbx*8], r14d
0x1800053fe  jz      short loc_18000541D
0x180005400  lea     r8, aMPreaderslotsU; "m_pReaderSlots[uIndex].m_uThreadId == u"...
0x180005407  mov     [rsp+88h+var_68], r12d; int
0x18000540c  mov     edx, 109h; unsigned int
0x180005411  mov     rcx, rbp; char *
0x180005414  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005419  mov     rcx, [rsi+60h]
0x18000541d  cmp     [rcx+rbx*8+4], r12d
0x180005422  jz      short loc_180005441
0x180005424  lea     r8, aMPreaderslotsU_0; "m_pReaderSlots[uIndex].m_uNestedReaders"...
0x18000542b  mov     [rsp+88h+var_68], r12d; int
0x180005430  mov     edx, 10Eh; unsigned int
0x180005435  mov     rcx, rbp; char *
0x180005438  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000543d  mov     rcx, [rsi+60h]
0x180005441  xor     eax, eax
0x180005443  xor     r8d, r8d; lpPreviousCount
0x180005446  mov     [rcx+rbx*8], rax
  ... truncated ...
```
