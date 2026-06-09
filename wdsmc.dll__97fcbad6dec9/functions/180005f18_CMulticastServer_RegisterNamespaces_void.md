# CMulticastServer::RegisterNamespaces(void)

- ea: `0x180005f18`
- end: `0x180006355`
- name: `?RegisterNamespaces@CMulticastServer@@QEAAKXZ`
- size: `1085`
- prototype: `unsigned int __fastcall(CMulticastServer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800053a0`

## callees

- `0x180002220`
- `0x180002368`
- `0x1800026b8`
- `0x180002810`
- `0x180005f18`
- `0x18000635c`
- `0x180008dcc`
- `0x18000b014`
- `0x18001a9a8`
- `0x18001b0ac`
- `0x18001b118`
- `0x1800220f8`
- `0x1800227d4`
- `0x180024dec`
- `0x180025850`
- `0x1800266a0`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006255`
- `KERNEL32!GetCurrentThreadId` at `0x180006255`
- `KERNEL32!LeaveCriticalSection` at `0x180006335`
- `KERNEL32!LeaveCriticalSection` at `0x180006335`
- `KERNEL32!EnterCriticalSection` at `0x18000624f`
- `KERNEL32!EnterCriticalSection` at `0x18000624f`
- `KERNEL32!ReleaseSemaphore` at `0x1800062e9`
- `KERNEL32!ReleaseSemaphore` at `0x18000630f`
- `KERNEL32!ReleaseSemaphore` at `0x1800062e9`
- `KERNEL32!ReleaseSemaphore` at `0x18000630f`

## string_xrefs

- `0x18000625b`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180006267`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180006297`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x1800062bf`: `m_uActiveReaders == 0`
- `0x1800062f3`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180006319`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
__int64 __fastcall CMulticastServer::RegisterNamespaces(CMulticastServer *this)
{
  CMulticastNamespace *v2; // rdi
  __int64 v3; // r13
  __int64 v4; // rdx
  unsigned int v5; // ebp
  const char *v6; // rdx
  unsigned int v7; // eax
  const char *v8; // rdx
  _DWORD *v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r15d
  const char *v12; // rdx
  struct CMulticastNamespace *Namespace; // r14
  unsigned int v14; // ebp
  struct _RTL_CRITICAL_SECTION *Provider; // rbp
  CMulticastNamespace *v16; // rax
  const char *v17; // rdx
  unsigned int v18; // edx
  unsigned int v19; // eax
  const char *v20; // rdx
  unsigned int i; // edi
  LPCRITICAL_SECTION v22; // rbx
  int v23; // r9d
  int DebugInfo; // eax
  int v25; // r9d
  const char *v26; // r8
  unsigned int v27; // edx
  LONG LockSemaphore_high; // edx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-48h] BYREF
  int v31; // [rsp+58h] [rbp-40h]
  void *v32; // [rsp+A0h] [rbp+8h] BYREF
  void *v33; // [rsp+A8h] [rbp+10h] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)this;
  v32 = 0;
  v33 = 0;
  v31 = 0;
  v2 = 0;
  v3 = 0;
  CAutoWriterLock::Lock(&lpCriticalSection);
  v5 = CWdsTptNamespaceStore::ReadNamespaces(*((_QWORD *)this + 106), v4, &v32);
  v7 = ElValidateWin32(v5, v6, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x211u);
  v9 = v32;
  if ( !v7 )
  {
    v10 = *((_DWORD *)v32 + 3);
    v11 = 0;
    if ( v10 )
    {
      while ( 1 )
      {
        v5 = 0;
        if ( v11 < v10 )
          v3 = *(_QWORD *)(*(_QWORD *)v9 + 8LL * v11);
        else
          v5 = 1413;
        if ( ElValidateWin32(v5, v8, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x21Bu) )
          break;
        Namespace = CMulticastServer::FindNamespace(this, *(const unsigned __int16 **)(v3 + 16));
        if ( Namespace )
        {
          v14 = -1054801657;
        }
        else
        {
          Provider = (struct _RTL_CRITICAL_SECTION *)CContentProvidersHandler::FindProvider(
                                                       (CMulticastServer *)((char *)this + 536),
                                                       *(const unsigned __int16 **)(v3 + 40));
          if ( Provider )
          {
            v16 = (CMulticastNamespace *)operator new(0x1D8u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v16 )
              v2 = CMulticastNamespace::CMulticastNamespace(v16);
            else
              v2 = 0;
            if ( v2 )
            {
              v14 = CMulticastNamespace::Initialize(v2, (struct _WDSTPT_NAMESPACE *)v3, Provider, &v33);
              if ( !ElValidateWin32(v14, v17, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x242u) )
              {
                if ( *((_QWORD *)this + 103) )
                {
                  *((_QWORD *)v2 + 57) = 0;
                  *((_QWORD *)v2 + 58) = *((_QWORD *)this + 104);
                  *(_QWORD *)(*((_QWORD *)this + 104) + 456LL) = v2;
                  *((_QWORD *)this + 104) = v2;
                }
                else
                {
                  *((_QWORD *)this + 104) = v2;
                  *((_QWORD *)this + 103) = v2;
                  *((_QWORD *)v2 + 57) = 0;
                  *((_QWORD *)v2 + 58) = 0;
                }
                ++*((_DWORD *)this + 211);
              }
            }
            else
            {
              v14 = 8;
            }
          }
          else
          {
            v14 = -1054801658;
          }
        }
        if ( ElValidateWin32(v14, v12, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x248u) )
        {
          if ( v14 == -1054801658 )
          {
            v18 = -1054801151;
          }
          else if ( v14 == -1054801657 )
          {
            v18 = -1054801150;
          }
          else
          {
            v18 = -1054801152;
            if ( v14 != -1054801653 )
              v18 = -1054801149;
          }
          CEventLog::Log((CEventLog *)&hEventLog, v18, 3);
          v19 = CWdsTptNamespaceStore::RemoveNamespace(
                  *((CWdsTptNamespaceStore **)this + 106),
                  *(const unsigned __int16 **)(v3 + 16));
          ElValidateWin32(v19, v20, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x283u);
          if ( v2 )
          {
            CMulticastNamespace::Close(v2, 1);
            CMulticastNamespace::Shutdown(v2);
            (*(void (__fastcall **)(CMulticastNamespace *))(*(_QWORD *)v2 + 8LL))(v2);
            v2 = 0;
          }
        }
        if ( Namespace )
          (*(void (__fastcall **)(struct CMulticastNamespace *))(*(_QWORD *)Namespace + 8LL))(Namespace);
        v10 = v9[3];
        if ( ++v11 >= v10 )
          goto LABEL_34;
      }
    }
    else
    {
LABEL_34:
      v5 = 0;
    }
  }
  if ( v9 )
  {
    for ( i = 0; i < v9[3]; ++i )
      CTptControlPacket::FreeNamespace(*(struct _WDSTPT_NAMESPACE **)(*(_QWORD *)v9 + 8LL * i), 1);
    if ( *(_QWORD *)v9 )
    {
      operator delete(*(void **)v9);
      *(_QWORD *)v9 = 0;
      *((_QWORD *)v9 + 1) = 0;
    }
    operator delete(v9);
  }
  if ( v31 == 1 )
  {
    v22 = lpCriticalSection;
    EnterCriticalSection(lpCriticalSection);
    if ( LODWORD(v22[1].SpinCount) != GetCurrentThreadId() )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x195u,
        "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
        v23,
        0);
    DebugInfo = (int)v22[2].DebugInfo;
    if ( DebugInfo )
    {
      LODWORD(v22[2].DebugInfo) = DebugInfo - 1;
LABEL_57:
      LeaveCriticalSection(v22);
      return v5;
    }
    if ( HIDWORD(v22[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x1A1u,
        "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
        v23,
        0);
    v22[1].SpinCount = 0;
    LODWORD(v22[2].DebugInfo) = 0;
    if ( LODWORD(v22[2].LockSemaphore) )
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v23, 0);
    if ( LODWORD(v22[2].SpinCount) )
    {
      if ( ReleaseSemaphore(v22[1].OwningThread, 1, 0) )
        goto LABEL_57;
      v26 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
      v27 = 431;
    }
    else
    {
      LockSemaphore_high = HIDWORD(v22[2].LockSemaphore);
      if ( !LockSemaphore_high || ReleaseSemaphore(*(HANDLE *)&v22[1].LockCount, LockSemaphore_high, 0) )
        goto LABEL_57;
      v26 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
      v27 = 440;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v27, v26, v25, 0);
    goto LABEL_57;
  }
  return v5;
}

```

## disassembly

```asm
0x180005f18  mov     rax, rsp
0x180005f1b  mov     [rax+18h], rbx
0x180005f1f  push    rbp
0x180005f20  push    rsi
0x180005f21  push    rdi
0x180005f22  push    r12
0x180005f24  push    r13
0x180005f26  push    r14
0x180005f28  push    r15
0x180005f2a  sub     rsp, 60h
0x180005f2e  xor     r12d, r12d
0x180005f31  mov     [rax-48h], rcx
0x180005f35  mov     rsi, rcx
0x180005f38  mov     [rax+8], r12
0x180005f3c  lea     rcx, [rax-48h]; this
0x180005f40  mov     [rax+10h], r12
0x180005f44  mov     r14d, r12d
0x180005f47  mov     [rax-40h], r12d
0x180005f4b  mov     edi, r12d
0x180005f4e  mov     r13d, r12d
0x180005f51  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180005f56  mov     rcx, [rsi+350h]
0x180005f5d  lea     r8, [rsp+98h+arg_0]
0x180005f65  call    ?ReadNamespaces@CWdsTptNamespaceStore@@QEAAKPEBGPEAPEAV?$CDynArray@PEAU_WDSTPT_NAMESPACE@@VCDeallocateNone@@@@@Z; CWdsTptNamespaceStore::ReadNamespaces(ushort const *,CDynArray<_WDSTPT_NAMESPACE *,CDeallocateNone> * *)
0x180005f6a  mov     r9d, 211h; unsigned int
0x180005f70  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005f77  mov     ecx, eax; unsigned int
0x180005f79  mov     ebp, eax
0x180005f7b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005f80  mov     rbx, [rsp+98h+arg_0]
0x180005f88  test    eax, eax
0x180005f8a  jnz     loc_1800061D1
0x180005f90  mov     eax, [rbx+0Ch]
0x180005f93  mov     r15d, r12d
0x180005f96  test    eax, eax
0x180005f98  jz      loc_1800061CE
0x180005f9e  mov     ebp, r12d
0x180005fa1  cmp     r15d, eax
0x180005fa4  jb      short loc_180005FAD
0x180005fa6  mov     ebp, 585h
0x180005fab  jmp     short loc_180005FB7
0x180005fad  mov     rax, [rbx]
0x180005fb0  mov     ecx, r15d
0x180005fb3  mov     r13, [rax+rcx*8]
0x180005fb7  mov     r9d, 21Bh; unsigned int
0x180005fbd  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005fc4  mov     ecx, ebp; unsigned int
0x180005fc6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005fcb  test    eax, eax
0x180005fcd  jnz     loc_1800061D1
0x180005fd3  mov     rdx, [r13+10h]; unsigned __int16 *
0x180005fd7  mov     rcx, rsi; this
0x180005fda  call    ?FindNamespace@CMulticastServer@@AEAAPEAVCMulticastNamespace@@PEBG@Z; CMulticastServer::FindNamespace(ushort const *)
0x180005fdf  mov     r14, rax
0x180005fe2  test    rax, rax
0x180005fe5  jz      short loc_180005FF1
0x180005fe7  mov     ebp, 0C1210107h
0x180005fec  jmp     loc_1800060CD
0x180005ff1  mov     rdx, [r13+28h]; unsigned __int16 *
0x180005ff5  lea     rcx, [rsi+218h]; this
0x180005ffc  call    ?FindProvider@CContentProvidersHandler@@QEAAPEAVCContentProvider@@PEBG@Z; CContentProvidersHandler::FindProvider(ushort const *)
0x180006001  mov     rbp, rax
0x180006004  test    rax, rax
0x180006007  jnz     short loc_180006013
0x180006009  mov     ebp, 0C1210106h
0x18000600e  jmp     loc_1800060CD
0x180006013  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000601a  mov     ecx, 1D8h; unsigned __int64
0x18000601f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006024  test    rax, rax
0x180006027  jz      short loc_180006036
0x180006029  mov     rcx, rax; this
0x18000602c  call    ??0CMulticastNamespace@@QEAA@XZ; CMulticastNamespace::CMulticastNamespace(void)
0x180006031  mov     rdi, rax
0x180006034  jmp     short loc_180006039
0x180006036  mov     rdi, r12
0x180006039  test    rdi, rdi
0x18000603c  jnz     short loc_180006046
0x18000603e  lea     ebp, [rdi+8]
0x180006041  jmp     loc_1800060CD
0x180006046  lea     r9, [rsp+98h+arg_8]; void **
0x18000604e  mov     r8, rbp; lpCriticalSection
0x180006051  mov     rdx, r13; Src
0x180006054  mov     rcx, rdi; this
0x180006057  call    ?Initialize@CMulticastNamespace@@QEAAKPEAU_WDSTPT_NAMESPACE@@PEAVCContentProvider@@PEAPEAX@Z; CMulticastNamespace::Initialize(_WDSTPT_NAMESPACE *,CContentProvider *,void * *)
0x18000605c  mov     r9d, 242h; unsigned int
0x180006062  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180006069  mov     ecx, eax; unsigned int
0x18000606b  mov     ebp, eax
0x18000606d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006072  test    eax, eax
0x180006074  jnz     short loc_1800060CD
0x180006076  cmp     [rsi+338h], r12
0x18000607d  jnz     short loc_18000609D
0x18000607f  mov     [rsi+340h], rdi
0x180006086  mov     [rsi+338h], rdi
0x18000608d  mov     [rdi+1C8h], r12
0x180006094  mov     [rdi+1D0h], r12
0x18000609b  jmp     short loc_1800060C7
0x18000609d  mov     [rdi+1C8h], r12
0x1800060a4  mov     rax, [rsi+340h]
0x1800060ab  mov     [rdi+1D0h], rax
0x1800060b2  mov     rax, [rsi+340h]
0x1800060b9  mov     [rax+1C8h], rdi
0x1800060c0  mov     [rsi+340h], rdi
0x1800060c7  inc     dword ptr [rsi+34Ch]
0x1800060cd  mov     r9d, 248h; unsigned int
0x1800060d3  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800060da  mov     ecx, ebp; unsigned int
0x1800060dc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800060e1  test    eax, eax
0x1800060e3  jz      loc_1800061A7
0x1800060e9  cmp     ebp, 0C1210106h
0x1800060ef  jz      short loc_180006115
0x1800060f1  cmp     ebp, 0C1210107h
0x1800060f7  jz      short loc_18000610E
0x1800060f9  cmp     ebp, 0C121010Bh
0x1800060ff  mov     edx, 0C1210300h
0x180006104  mov     eax, 0C1210303h
0x180006109  cmovnz  edx, eax
0x18000610c  jmp     short loc_18000611A
0x18000610e  mov     edx, 0C1210302h
0x180006113  jmp     short loc_18000611A
0x180006115  mov     edx, 0C1210301h; unsigned int
0x18000611a  mov     rcx, [r13+10h]
0x18000611e  mov     r9d, 1
0x180006124  mov     rax, [r13+28h]
0x180006128  mov     [rsp+98h+var_58], ebp
0x18000612c  mov     [rsp+98h+var_60], 5
0x180006134  mov     [rsp+98h+var_68], rax
0x180006139  lea     r8d, [r9+2]; int
0x18000613d  mov     [rsp+98h+var_70], 1
0x180006145  mov     qword ptr [rsp+98h+var_78], rcx
0x18000614a  lea     rcx, hEventLog; this
0x180006151  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180006156  mov     rdx, [r13+10h]; unsigned __int16 *
0x18000615a  mov     rcx, [rsi+350h]; this
0x180006161  call    ?RemoveNamespace@CWdsTptNamespaceStore@@QEAAKPEBG@Z; CWdsTptNamespaceStore::RemoveNamespace(ushort const *)
0x180006166  mov     ecx, eax; unsigned int
0x180006168  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000616f  mov     r9d, 283h; unsigned int
0x180006175  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000617a  test    rdi, rdi
0x18000617d  jz      short loc_1800061A7
0x18000617f  mov     edx, 1; int
0x180006184  mov     rcx, rdi; this
0x180006187  call    ?Close@CMulticastNamespace@@QEAAKH@Z; CMulticastNamespace::Close(int)
0x18000618c  mov     rcx, rdi; this
0x18000618f  call    ?Shutdown@CMulticastNamespace@@QEAAKXZ; CMulticastNamespace::Shutdown(void)
0x180006194  mov     rax, [rdi]
0x180006197  mov     rcx, rdi
0x18000619a  mov     rax, [rax+8]
0x18000619e  call    cs:__guard_dispatch_icall_fptr
0x1800061a4  mov     rdi, r12
0x1800061a7  test    r14, r14
0x1800061aa  jz      short loc_1800061BF
0x1800061ac  mov     rax, [r14]
0x1800061af  mov     rcx, r14
0x1800061b2  mov     rax, [rax+8]
0x1800061b6  call    cs:__guard_dispatch_icall_fptr
0x1800061bc  mov     r14, r12
0x1800061bf  mov     eax, [rbx+0Ch]
0x1800061c2  inc     r15d
0x1800061c5  cmp     r15d, eax
0x1800061c8  jb      loc_180005F9E
0x1800061ce  mov     ebp, r12d
0x1800061d1  test    rbx, rbx
0x1800061d4  jz      short loc_18000621D
0x1800061d6  mov     eax, [rbx+0Ch]
0x1800061d9  mov     edi, r12d
0x1800061dc  test    eax, eax
0x1800061de  jz      short loc_180006201
0x1800061e0  cmp     r12d, eax
0x1800061e3  jnb     short loc_1800061F8
0x1800061e5  mov     rax, [rbx]
0x1800061e8  mov     ecx, edi
0x1800061ea  mov     rcx, [rax+rcx*8]; struct _WDSTPT_NAMESPACE *
0x1800061ee  mov     edx, 1; int
0x1800061f3  call    ?FreeNamespace@CTptControlPacket@@SAXPEAU_WDSTPT_NAMESPACE@@H@Z; CTptControlPacket::FreeNamespace(_WDSTPT_NAMESPACE *,int)
0x1800061f8  mov     eax, [rbx+0Ch]
0x1800061fb  inc     edi
0x1800061fd  cmp     edi, eax
0x1800061ff  jb      short loc_1800061E5
0x180006201  mov     rcx, [rbx]; void *
0x180006204  test    rcx, rcx
0x180006207  jz      short loc_180006215
0x180006209  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000620e  mov     [rbx], r12
0x180006211  mov     [rbx+8], r12
0x180006215  mov     rcx, rbx; void *
0x180006218  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000621d  test    r14, r14
0x180006220  jz      short loc_180006232
0x180006222  mov     rax, [r14]
0x180006225  mov     rcx, r14
0x180006228  mov     rax, [rax+8]
0x18000622c  call    cs:__guard_dispatch_icall_fptr
0x180006232  mov     eax, [rsp+98h+var_40]
0x180006236  test    eax, eax
0x180006238  jz      loc_18000633B
0x18000623e  cmp     eax, 1
0x180006241  jnz     loc_18000633B
0x180006247  mov     rbx, [rsp+98h+lpCriticalSection]
0x18000624c  mov     rcx, rbx; lpCriticalSection
0x18000624f  call    cs:__imp_EnterCriticalSection
0x180006255  call    cs:__imp_GetCurrentThreadId
0x18000625b  lea     rdi, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180006262  cmp     [rbx+48h], eax
0x180006265  jz      short loc_180006280
0x180006267  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x18000626e  mov     [rsp+98h+var_78], r12d; int
0x180006273  mov     edx, 195h; unsigned int
0x180006278  mov     rcx, rdi; char *
0x18000627b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180006280  mov     eax, [rbx+50h]
0x180006283  test    eax, eax
0x180006285  jz      short loc_180006291
0x180006287  dec     eax
0x180006289  mov     [rbx+50h], eax
0x18000628c  jmp     loc_180006332
0x180006291  cmp     [rbx+4Ch], r12d
0x180006295  jz      short loc_1800062B0
0x180006297  lea     r8, aMActivewriterM_2; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x18000629e  mov     [rsp+98h+var_78], r12d; int
0x1800062a3  mov     edx, 1A1h; unsigned int
0x1800062a8  mov     rcx, rdi; char *
0x1800062ab  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800062b0  xor     eax, eax
0x1800062b2  mov     [rbx+48h], rax
0x1800062b6  mov     [rbx+50h], eax
0x1800062b9  cmp     [rbx+68h], r12d
0x1800062bd  jz      short loc_1800062D8
0x1800062bf  lea     r8, aMUactivereader; "m_uActiveReaders == 0"
0x1800062c6  mov     [rsp+98h+var_78], r12d; int
0x1800062cb  mov     edx, 1A4h; unsigned int
0x1800062d0  mov     rcx, rdi; char *
0x1800062d3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800062d8  cmp     [rbx+70h], r12d
0x1800062dc  jz      short loc_180006301
0x1800062de  mov     rcx, [rbx+38h]; hSemaphore
0x1800062e2  xor     r8d, r8d; lpPreviousCount
0x1800062e5  lea     edx, [r8+1]; lReleaseCount
0x1800062e9  call    cs:__imp_ReleaseSemaphore
0x1800062ef  test    eax, eax
0x1800062f1  jnz     short loc_180006332
0x1800062f3  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x1800062fa  mov     edx, 1AFh
0x1800062ff  jmp     short loc_180006325
0x180006301  mov     edx, [rbx+6Ch]; lReleaseCount
0x180006304  test    edx, edx
0x180006306  jz      short loc_180006332
0x180006308  mov     rcx, [rbx+30h]; hSemaphore
0x18000630c  xor     r8d, r8d; lpPreviousCount
0x18000630f  call    cs:__imp_ReleaseSemaphore
0x180006315  test    eax, eax
0x180006317  jnz     short loc_180006332
0x180006319  lea     r8, aReleasesemapho; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180006320  mov     edx, 1B8h; unsigned int
0x180006325  mov     rcx, rdi; char *
0x180006328  mov     [rsp+98h+var_78], r12d; int
0x18000632d  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180006332  mov     rcx, rbx; lpCriticalSection
0x180006335  call    cs:__imp_LeaveCriticalSection
0x18000633b  mov     eax, ebp
0x18000633d  mov     rbx, [rsp+98h+arg_10]
0x180006345  add     rsp, 60h
0x180006349  pop     r15
0x18000634b  pop     r14
0x18000634d  pop     r13
0x18000634f  pop     r12
0x180006351  pop     rdi
0x180006352  pop     rsi
0x180006353  pop     rbp
0x180006354  retn
```
