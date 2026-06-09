# CClientContext::FindSession(tagWDS_ENDPOINT *,ushort *,CTftpSession * *)

- ea: `0x18000414c`
- end: `0x180004420`
- name: `?FindSession@CClientContext@@QEAAKPEAUtagWDS_ENDPOINT@@PEAGPEAPEAVCTftpSession@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct tagWDS_ENDPOINT *, unsigned __int16 *, struct CTftpSession **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002bc0`
- `0x180003f54`

## callees

- `0x180003550`
- `0x18000414c`
- `0x18000453c`
- `0x18003a878`
- `0x18003aa68`
- `0x18003c514`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x1800043d3`
- `KERNEL32!ReleaseSemaphore` at `0x1800043d3`
- `KERNEL32!GetCurrentThreadId` at `0x18000430c`
- `KERNEL32!GetCurrentThreadId` at `0x18000430c`
- `KERNEL32!EnterCriticalSection` at `0x18000431e`
- `KERNEL32!EnterCriticalSection` at `0x18000431e`
- `KERNEL32!LeaveCriticalSection` at `0x180004403`
- `KERNEL32!LeaveCriticalSection` at `0x180004403`

## string_xrefs

- `0x180004348`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180004388`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800043f4`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800043e3`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180004337`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180004377`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

## pseudocode

```c
__int64 __fastcall CClientContext::FindSession(
        struct _RTL_CRITICAL_SECTION *this,
        struct tagWDS_ENDPOINT *a2,
        unsigned __int16 *a3,
        struct CTftpSession **a4)
{
  struct CTftpSession *v4; // rbx
  unsigned int Endpoint; // esi
  CEndpointSessionMapEntry *v9; // r13
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  unsigned int Session; // eax
  const char *v14; // rdx
  struct tagWDS_ENDPOINT *v15; // rbx
  unsigned int v16; // eax
  struct CTftpSession *v17; // rbx
  unsigned int v18; // ebx
  DWORD CurrentThreadId; // r14d
  int v20; // r9d
  int SpinCount_high; // eax
  unsigned int v22; // ecx
  _DWORD *OwningThread; // rdx
  int v24; // eax
  bool v25; // zf
  int v26; // r9d
  struct CTftpSession *v28[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+80h] [rbp+40h] BYREF
  struct tagWDS_ENDPOINT *v30; // [rsp+88h] [rbp+48h]
  unsigned int v31; // [rsp+90h] [rbp+50h] BYREF
  struct CTftpSession **v32; // [rsp+98h] [rbp+58h]

  v32 = a4;
  v30 = a2;
  v4 = 0;
  v29 = 0;
  v31 = 0;
  v28[0] = 0;
  Endpoint = 0;
  v9 = 0;
  CMRSWLock::ReaderLock(this);
  if ( a3 )
  {
    Endpoint = CClientContext::FindEndpoint((CClientContext *)this, *a3, &v29);
    if ( !ElValidateWin32(Endpoint, v11, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x3ACu) )
    {
      Endpoint = 0;
      if ( v29 < HIDWORD(this[4].OwningThread) )
        v9 = *(CEndpointSessionMapEntry **)(*(_QWORD *)&this[4].LockCount + 8LL * v29);
      else
        Endpoint = 1413;
      if ( !ElValidateWin32(Endpoint, v12, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x3AFu) )
      {
        Session = CEndpointSessionMapEntry::FindSession(v9, a2, v28, &v31);
        Endpoint = Session;
        if ( Session != 1168
          && !ElValidateWin32(Session, v14, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x3BDu) )
        {
          v4 = v28[0];
LABEL_22:
          if ( !v4 || _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 558, 0) )
          {
            Endpoint = 1168;
          }
          else
          {
            v17 = v28[0];
            (**((void (__fastcall ***)(char *))v28[0] + 1))((char *)v28[0] + 8);
            *v32 = v17;
          }
        }
      }
    }
  }
  else
  {
    if ( !HIDWORD(this[4].OwningThread) )
    {
LABEL_21:
      if ( ElValidateWin32(0, v10, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x3E4u) )
        goto LABEL_26;
      goto LABEL_22;
    }
    v15 = v30;
    while ( 1 )
    {
      Endpoint = 0;
      if ( (unsigned int)a3 < HIDWORD(this[4].OwningThread) )
        v9 = *(CEndpointSessionMapEntry **)(*(_QWORD *)&this[4].LockCount + 8LL * (_QWORD)a3);
      else
        Endpoint = 1413;
      if ( ElValidateWin32(Endpoint, v10, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x3C8u) )
        break;
      v16 = CEndpointSessionMapEntry::FindSession(v9, v15, v28, &v31);
      Endpoint = v16;
      if ( !v16 )
      {
        v4 = v28[0];
        goto LABEL_21;
      }
      if ( v16 == 1168 )
      {
        a3 = (unsigned __int16 *)(unsigned int)((_DWORD)a3 + 1);
        if ( (unsigned int)a3 < HIDWORD(this[4].OwningThread) )
          continue;
      }
      break;
    }
  }
LABEL_26:
  v18 = 0;
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
        v20,
        0);
      SpinCount_high = HIDWORD(this[1].SpinCount);
    }
    HIDWORD(this[1].SpinCount) = SpinCount_high - 1;
  }
  else
  {
    v22 = 0;
    while ( *((_DWORD *)this[2].OwningThread + 2 * v22) != CurrentThreadId )
    {
      if ( ++v22 > this[2].LockCount )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x236u,
          "GetReaderSlot(uThreadId, &uIndex) == 0L",
          v20,
          0);
        goto LABEL_35;
      }
    }
    v18 = v22;
LABEL_35:
    OwningThread = this[2].OwningThread;
    v24 = OwningThread[2 * v18 + 1];
    if ( v24 )
    {
      OwningThread[2 * v18 + 1] = v24 - 1;
    }
    else
    {
      CMRSWLock::FreeReaderSlot((CMRSWLock *)this, CurrentThreadId, v18);
      v25 = LODWORD(this[2].LockSemaphore)-- == 1;
      if ( v25 && LODWORD(this[2].SpinCount) && !ReleaseSemaphore(this[1].OwningThread, 1, 0) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x251u,
          "ReleaseSemaphore(m_hReaderDone, 1, 0)",
          v26,
          0);
    }
  }
  LeaveCriticalSection(this);
  return Endpoint;
}

```

## disassembly

```asm
0x18000414c  mov     [rsp-38h+arg_18], r9
0x180004151  mov     [rsp-38h+arg_8], rdx
0x180004156  push    rbp
0x180004157  push    rbx
0x180004158  push    rsi
0x180004159  push    rdi
0x18000415a  push    r13
0x18000415c  push    r14
0x18000415e  push    r15
0x180004160  mov     rbp, rsp
0x180004163  sub     rsp, 40h
0x180004167  xor     ebx, ebx
0x180004169  mov     r14, r8
0x18000416c  and     [rbp+arg_0], ebx
0x18000416f  mov     r15, rdx
0x180004172  and     [rbp+arg_10], ebx
0x180004175  mov     rdi, rcx
0x180004178  mov     [rbp+var_10], rbx
0x18000417c  xor     esi, esi
0x18000417e  xor     r13d, r13d
0x180004181  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180004186  test    r14, r14
0x180004189  jz      loc_180004244
0x18000418f  movzx   edx, word ptr [r14]; unsigned __int16
0x180004193  lea     r8, [rbp+arg_0]; unsigned int *
0x180004197  mov     rcx, rdi; this
0x18000419a  call    ?FindEndpoint@CClientContext@@AEAAKGAEAK@Z; CClientContext::FindEndpoint(ushort,ulong &)
0x18000419f  mov     r9d, 3ACh; unsigned int
0x1800041a5  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800041ac  mov     ecx, eax; unsigned int
0x1800041ae  mov     esi, eax
0x1800041b0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800041b5  test    eax, eax
0x1800041b7  jnz     loc_180004306
0x1800041bd  mov     eax, [rbp+arg_0]
0x1800041c0  xor     esi, esi
0x1800041c2  cmp     eax, [rdi+0B4h]
0x1800041c8  jb      short loc_1800041D1
0x1800041ca  mov     esi, 585h
0x1800041cf  jmp     short loc_1800041DF
0x1800041d1  mov     rcx, rax
0x1800041d4  mov     rax, [rdi+0A8h]
0x1800041db  mov     r13, [rax+rcx*8]
0x1800041df  mov     r9d, 3AFh; unsigned int
0x1800041e5  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800041ec  mov     ecx, esi; unsigned int
0x1800041ee  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800041f3  test    eax, eax
0x1800041f5  jnz     loc_180004306
0x1800041fb  lea     r9, [rbp+arg_10]; unsigned int *
0x1800041ff  mov     rdx, r15; struct tagWDS_ENDPOINT *
0x180004202  lea     r8, [rbp+var_10]; struct CTftpSession **
0x180004206  mov     rcx, r13; this
0x180004209  call    ?FindSession@CEndpointSessionMapEntry@@QEAAKPEAUtagWDS_ENDPOINT@@PEAPEAVCTftpSession@@AEAK@Z; CEndpointSessionMapEntry::FindSession(tagWDS_ENDPOINT *,CTftpSession * *,ulong &)
0x18000420e  mov     r15d, 490h
0x180004214  mov     esi, eax
0x180004216  cmp     eax, r15d
0x180004219  jz      loc_180004306
0x18000421f  mov     r9d, 3BDh; unsigned int
0x180004225  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000422c  mov     ecx, eax; unsigned int
0x18000422e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004233  test    eax, eax
0x180004235  jnz     loc_180004306
0x18000423b  mov     rbx, [rbp+var_10]
0x18000423f  jmp     loc_1800042D3
0x180004244  mov     r15d, 490h
0x18000424a  cmp     [rdi+0B4h], ebx
0x180004250  jbe     short loc_1800042BB
0x180004252  mov     rbx, [rbp+arg_8]
0x180004256  xor     esi, esi
0x180004258  cmp     r14d, [rdi+0B4h]
0x18000425f  jb      short loc_180004268
0x180004261  mov     esi, 585h
0x180004266  jmp     short loc_180004273
0x180004268  mov     rax, [rdi+0A8h]
0x18000426f  mov     r13, [rax+r14*8]
0x180004273  mov     r9d, 3C8h; unsigned int
0x180004279  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180004280  mov     ecx, esi; unsigned int
0x180004282  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004287  test    eax, eax
0x180004289  jnz     short loc_180004306
0x18000428b  lea     r9, [rbp+arg_10]; unsigned int *
0x18000428f  mov     rdx, rbx; struct tagWDS_ENDPOINT *
0x180004292  lea     r8, [rbp+var_10]; struct CTftpSession **
0x180004296  mov     rcx, r13; this
0x180004299  call    ?FindSession@CEndpointSessionMapEntry@@QEAAKPEAUtagWDS_ENDPOINT@@PEAPEAVCTftpSession@@AEAK@Z; CEndpointSessionMapEntry::FindSession(tagWDS_ENDPOINT *,CTftpSession * *,ulong &)
0x18000429e  mov     esi, eax
0x1800042a0  test    eax, eax
0x1800042a2  jz      short loc_1800042B7
0x1800042a4  cmp     eax, r15d
0x1800042a7  jnz     short loc_180004306
0x1800042a9  inc     r14d
0x1800042ac  cmp     r14d, [rdi+0B4h]
0x1800042b3  jb      short loc_180004256
0x1800042b5  jmp     short loc_180004306
0x1800042b7  mov     rbx, [rbp+var_10]
0x1800042bb  mov     r9d, 3E4h; unsigned int
0x1800042c1  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800042c8  xor     ecx, ecx; unsigned int
0x1800042ca  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800042cf  test    eax, eax
0x1800042d1  jnz     short loc_180004306
0x1800042d3  test    rbx, rbx
0x1800042d6  jz      short loc_180004303
0x1800042d8  xor     eax, eax
0x1800042da  lock xadd [rbx+8B8h], eax
0x1800042e2  test    eax, eax
0x1800042e4  jnz     short loc_180004303
0x1800042e6  mov     rbx, [rbp+var_10]
0x1800042ea  lea     rcx, [rbx+8]
0x1800042ee  mov     rax, [rcx]
0x1800042f1  mov     rax, [rax]
0x1800042f4  call    cs:__guard_dispatch_icall_fptr
0x1800042fa  mov     rax, [rbp+arg_18]
0x1800042fe  mov     [rax], rbx
0x180004301  jmp     short loc_180004306
0x180004303  mov     esi, r15d
0x180004306  xor     r15d, r15d
0x180004309  mov     ebx, r15d
0x18000430c  call    cs:__imp_GetCurrentThreadId
0x180004313  nop     dword ptr [rax+rax+00h]
0x180004318  mov     rcx, rdi; lpCriticalSection
0x18000431b  mov     r14d, eax
0x18000431e  call    cs:__imp_EnterCriticalSection
0x180004325  nop     dword ptr [rax+rax+00h]
0x18000432a  cmp     [rdi+48h], r14d
0x18000432e  jnz     short loc_180004361
0x180004330  mov     eax, [rdi+4Ch]
0x180004333  test    eax, eax
0x180004335  jnz     short loc_180004357
0x180004337  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders > 0"
0x18000433e  mov     [rsp+40h+var_20], r15d; int
0x180004343  mov     edx, 22Eh; unsigned int
0x180004348  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000434f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004354  mov     eax, [rdi+4Ch]
0x180004357  dec     eax
0x180004359  mov     [rdi+4Ch], eax
0x18000435c  jmp     loc_180004400
0x180004361  mov     rdx, [rdi+60h]
0x180004365  mov     ecx, r15d
0x180004368  mov     eax, ecx
0x18000436a  cmp     [rdx+rax*8], r14d
0x18000436e  jz      short loc_180004396
0x180004370  inc     ecx
0x180004372  cmp     ecx, [rdi+58h]
0x180004375  jbe     short loc_180004368
0x180004377  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x18000437e  mov     [rsp+40h+var_20], r15d; int
0x180004383  mov     edx, 236h; unsigned int
0x180004388  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000438f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004394  jmp     short loc_180004398
0x180004396  mov     ebx, ecx
0x180004398  mov     rdx, [rdi+60h]
0x18000439c  mov     ecx, ebx
0x18000439e  mov     eax, [rdx+rcx*8+4]
0x1800043a2  test    eax, eax
0x1800043a4  jz      short loc_1800043AE
0x1800043a6  dec     eax
0x1800043a8  mov     [rdx+rcx*8+4], eax
0x1800043ac  jmp     short loc_180004400
0x1800043ae  mov     r8d, ebx; unsigned int
0x1800043b1  mov     edx, r14d; unsigned int
0x1800043b4  mov     rcx, rdi; this
0x1800043b7  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x1800043bc  add     dword ptr [rdi+68h], 0FFFFFFFFh
0x1800043c0  jnz     short loc_180004400
0x1800043c2  cmp     [rdi+70h], r15d
0x1800043c6  jbe     short loc_180004400
0x1800043c8  mov     rcx, [rdi+38h]; hSemaphore
0x1800043cc  xor     r8d, r8d; lpPreviousCount
0x1800043cf  lea     edx, [r8+1]; lReleaseCount
0x1800043d3  call    cs:__imp_ReleaseSemaphore
0x1800043da  nop     dword ptr [rax+rax+00h]
0x1800043df  test    eax, eax
0x1800043e1  jnz     short loc_180004400
0x1800043e3  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x1800043ea  mov     [rsp+40h+var_20], r15d; int
0x1800043ef  mov     edx, 251h; unsigned int
0x1800043f4  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800043fb  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004400  mov     rcx, rdi; lpCriticalSection
0x180004403  call    cs:__imp_LeaveCriticalSection
0x18000440a  nop     dword ptr [rax+rax+00h]
0x18000440f  mov     eax, esi
0x180004411  add     rsp, 40h
0x180004415  pop     r15
0x180004417  pop     r14
0x180004419  pop     r13
0x18000441b  pop     rdi
0x18000441c  pop     rsi
0x18000441d  pop     rbx
0x18000441e  pop     rbp
0x18000441f  retn
```
