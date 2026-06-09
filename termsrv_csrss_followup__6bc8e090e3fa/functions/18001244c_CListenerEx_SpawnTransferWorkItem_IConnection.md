# CListenerEx::SpawnTransferWorkItem(IConnection *)

- ea: `0x18001244c`
- end: `0x18001274a`
- name: `?SpawnTransferWorkItem@CListenerEx@@AEAAJPEAVIConnection@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(CListenerEx *__hidden this, struct IConnection *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001cab0`

## callees

- `0x180009940`
- `0x18001244c`
- `0x180012750`
- `0x18001277c`
- `0x180012a80`
- `0x180025e6c`
- `0x18003444c`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x1800125c6`
- `ntdll!RtlCaptureStackBackTrace` at `0x1800125c6`
- `ntdll!RtlAcquireResourceExclusive` at `0x180012486`
- `ntdll!RtlAcquireResourceExclusive` at `0x180012647`
- `ntdll!RtlAcquireResourceExclusive` at `0x180012486`
- `ntdll!RtlAcquireResourceExclusive` at `0x180012647`
- `ntdll!RtlReleaseResource` at `0x180012516`
- `ntdll!RtlReleaseResource` at `0x18001271f`
- `ntdll!RtlReleaseResource` at `0x180012516`
- `ntdll!RtlReleaseResource` at `0x18001271f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800124cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800124cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800124ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800124ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012696`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012682`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800126e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800126e8`

## string_xrefs

- `0x1800126b4`: `CreateThread( Tranfer ) failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CListenerEx::SpawnTransferWorkItem(CListenerEx *this, struct IConnection *a2)
{
  struct _RTL_RESOURCE *v4; // rdi
  char *v5; // r14
  HANDLE *v6; // rsi
  HANDLE *v7; // r12
  unsigned int v8; // edx
  HANDLE *v9; // rax
  HANDLE **v10; // rcx
  char **v11; // rax
  unsigned int v12; // edx
  char **v13; // rbx
  char *v14; // rsi
  char v15; // al
  char *v16; // rsi
  signed int v17; // edi
  char *v18; // rsi
  signed int LastError; // eax
  unsigned int v20; // edx
  char *v21; // rcx
  char **v22; // rax
  struct _RTL_RESOURCE *v24; // [rsp+30h] [rbp-48h] BYREF
  int v25; // [rsp+38h] [rbp-40h]
  ULONG BackTraceHash; // [rsp+80h] [rbp+8h] BYREF
  char **v27; // [rsp+90h] [rbp+18h]

  v4 = (struct _RTL_RESOURCE *)((char *)this + 3200);
  v24 = (struct _RTL_RESOURCE *)((char *)this + 3200);
  v25 = 1;
  if ( *((_DWORD *)this + 824) )
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 3200), 1u);
  v5 = (char *)this + 3184;
  v6 = (HANDLE *)*((_QWORD *)this + 398);
  if ( v6 != (HANDLE *)((char *)this + 3184) )
  {
    do
    {
      v7 = (HANDLE *)*v6;
      EnterCriticalSection((LPCRITICAL_SECTION)v6 + 1);
      LeaveCriticalSection((LPCRITICAL_SECTION)v6 + 1);
      if ( !WaitForSingleObject(v6[2], 0) )
      {
        v9 = (HANDLE *)*v6;
        if ( *((HANDLE **)*v6 + 1) != v6 || (v10 = (HANDLE **)v6[1], *v10 != v6) )
          __fastfail(3u);
        *v10 = v9;
        v9[1] = v10;
        CListenerEx::TRANSFER_THREAD_INFO::`scalar deleting destructor'((CListenerEx::TRANSFER_THREAD_INFO *)v6, v8);
      }
      v6 = v7;
    }
    while ( v7 != (HANDLE *)v5 );
  }
  if ( LODWORD(v4[1].Lock.DebugInfo) )
    RtlReleaseResource(v4);
  v11 = (char **)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v13 = v11;
  v27 = v11;
  if ( v11 )
  {
    v11[2] = 0;
    v11[3] = 0;
    v11[4] = 0;
    CCriticalSection::CCriticalSection((CCriticalSection *)(v11 + 5), v12);
    v13[1] = (char *)v13;
    *v13 = (char *)v13;
    v14 = v13[4];
    v13[4] = (char *)this;
    if ( this )
    {
      if ( *((_DWORD *)this + 3) == 1 )
      {
        v15 = _InterlockedIncrement((volatile signed __int32 *)this + 8);
        BackTraceHash = 0;
        if ( g_bCaptureObjectStackTrace == 1 )
          RtlCaptureStackBackTrace(1u, 6u, (PVOID *)this + 6 * (v15 & 0x1F) + 5, &BackTraceHash);
      }
      _InterlockedIncrement64((volatile signed __int64 *)this + 3);
    }
    if ( v14 )
      CTSPrivateObject<IListenerItem>::Release(v14);
    v16 = v13[3];
    v13[3] = (char *)a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( v16 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  else
  {
    v13 = 0;
  }
  if ( v13 )
  {
    v24 = v4;
    v25 = 1;
    if ( LODWORD(v4[1].Lock.DebugInfo) )
      RtlAcquireResourceExclusive(v4, 1u);
    BackTraceHash = 0;
    v18 = (char *)CreateThread(0, 0, CListenerEx::staticTransferWorkItem, v13, 0, &BackTraceHash);
    if ( v18 )
    {
      v21 = v13[2];
      if ( v21 )
        CloseHandle(v21);
      v13[2] = v18;
      v22 = (char **)*((_QWORD *)this + 399);
      if ( *v22 != v5 )
        __fastfail(3u);
      *v13 = v5;
      v13[1] = (char *)v22;
      *v22 = (char *)v13;
      *((_QWORD *)this + 399) = v13;
      if ( LODWORD(v4[1].Lock.DebugInfo) )
        RtlReleaseResource(v4);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "CreateThread( Tranfer ) failed: 0x%x", v17);
      CAutoLock::Unlock((CAutoLock *)&v24);
      if ( v17 < 0 )
        CListenerEx::TRANSFER_THREAD_INFO::`scalar deleting destructor'((CListenerEx::TRANSFER_THREAD_INFO *)v13, v20);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001244c  mov     rax, rsp
0x18001244f  mov     [rax+10h], rbx
0x180012453  mov     [rax+20h], rbp
0x180012457  push    rsi
0x180012458  push    rdi
0x180012459  push    r12
0x18001245b  push    r14
0x18001245d  push    r15
0x18001245f  sub     rsp, 50h
0x180012463  mov     r15, rdx
0x180012466  mov     rbp, rcx
0x180012469  lea     rdi, [rcx+0C80h]
0x180012470  mov     [rax-48h], rdi
0x180012474  mov     dword ptr [rax-40h], 1
0x18001247b  cmp     dword ptr [rdi+60h], 0
0x18001247f  jz      short loc_180012493
0x180012481  mov     dl, 1; Wait
0x180012483  mov     rcx, rdi; Resource
0x180012486  call    cs:__imp_RtlAcquireResourceExclusive
0x18001248d  nop     dword ptr [rax+rax+00h]
0x180012492  nop
0x180012493  lea     r14, [rbp+0C70h]
0x18001249a  mov     rsi, [r14]
0x18001249d  cmp     rsi, r14
0x1800124a0  jz      short loc_18001250D
0x1800124a2  mov     r12, [rsi]
0x1800124a5  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800124a9  call    cs:__imp_EnterCriticalSection
0x1800124b0  nop     dword ptr [rax+rax+00h]
0x1800124b5  nop
0x1800124b6  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800124ba  call    cs:__imp_LeaveCriticalSection
0x1800124c1  nop     dword ptr [rax+rax+00h]
0x1800124c6  xor     edx, edx; dwMilliseconds
0x1800124c8  mov     rcx, [rsi+10h]; hHandle
0x1800124cc  call    cs:__imp_WaitForSingleObject
0x1800124d3  nop     dword ptr [rax+rax+00h]
0x1800124d8  test    eax, eax
0x1800124da  jnz     short loc_180012505
0x1800124dc  mov     rax, [rsi]
0x1800124df  cmp     [rax+8], rsi
0x1800124e3  jnz     loc_180012617
0x1800124e9  mov     rcx, [rsi+8]
0x1800124ed  cmp     [rcx], rsi
0x1800124f0  jnz     loc_180012617
0x1800124f6  mov     [rcx], rax
0x1800124f9  mov     [rax+8], rcx
0x1800124fd  mov     rcx, rsi; this
0x180012500  call    ??_GTRANSFER_THREAD_INFO@CListenerEx@@QEAAPEAXI@Z; CListenerEx::TRANSFER_THREAD_INFO::`scalar deleting destructor'(uint)
0x180012505  mov     rsi, r12
0x180012508  cmp     r12, r14
0x18001250b  jnz     short loc_1800124A2
0x18001250d  cmp     dword ptr [rdi+60h], 0
0x180012511  jz      short loc_180012523
0x180012513  mov     rcx, rdi; Resource
0x180012516  call    cs:__imp_RtlReleaseResource
0x18001251d  nop     dword ptr [rax+rax+00h]
0x180012522  nop
0x180012523  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001252a  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001252f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012534  mov     rbx, rax
0x180012537  mov     [rsp+78h+arg_10], rax
0x18001253f  test    rax, rax
0x180012542  jz      loc_18001261E
0x180012548  mov     qword ptr [rax+10h], 0
0x180012550  mov     qword ptr [rax+18h], 0
0x180012558  mov     qword ptr [rax+20h], 0
0x180012560  lea     rcx, [rax+28h]; this
0x180012564  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x180012569  nop
0x18001256a  mov     [rbx+8], rbx
0x18001256e  mov     [rbx], rbx
0x180012571  mov     rsi, [rbx+20h]
0x180012575  mov     [rbx+20h], rbp
0x180012579  test    rbp, rbp
0x18001257c  jz      short loc_1800125D7
0x18001257e  cmp     dword ptr [rbp+0Ch], 1
0x180012582  jnz     short loc_1800125D2
0x180012584  mov     eax, 1
0x180012589  lock xadd [rbp+20h], eax
0x18001258e  inc     eax
0x180012590  mov     [rsp+78h+BackTraceHash], 0
0x18001259b  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x1800125a2  jnz     short loc_1800125D2
0x1800125a4  and     eax, 1Fh
0x1800125a7  lea     r8, [rax+rax*2]
0x1800125ab  shl     r8, 4
0x1800125af  add     r8, 28h ; '('
0x1800125b3  add     r8, rbp; BackTrace
0x1800125b6  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x1800125be  mov     edx, 6; FramesToCapture
0x1800125c3  lea     ecx, [rdx-5]; FramesToSkip
0x1800125c6  call    cs:__imp_RtlCaptureStackBackTrace
0x1800125cd  nop     dword ptr [rax+rax+00h]
0x1800125d2  lock inc qword ptr [rbp+18h]
0x1800125d7  test    rsi, rsi
0x1800125da  jz      short loc_1800125E4
0x1800125dc  mov     rcx, rsi
0x1800125df  call    ?Release@?$CTSPrivateObject@VIListenerItem@@@@UEAAKXZ; CTSPrivateObject<IListenerItem>::Release(void)
0x1800125e4  mov     rsi, [rbx+18h]
0x1800125e8  mov     [rbx+18h], r15
0x1800125ec  test    r15, r15
0x1800125ef  jz      short loc_180012600
0x1800125f1  mov     rax, [r15]
0x1800125f4  mov     rcx, r15
0x1800125f7  mov     rax, [rax+8]
0x1800125fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012600  test    rsi, rsi
0x180012603  jz      short loc_180012615
0x180012605  mov     rax, [rsi]
0x180012608  mov     rcx, rsi
0x18001260b  mov     rax, [rax+10h]
0x18001260f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012614  nop
0x180012615  jmp     short loc_180012620
0x180012617  mov     ecx, 3
0x18001261c  int     29h; Win8: RtlFailFast(ecx)
0x18001261e  xor     ebx, ebx
0x180012620  test    rbx, rbx
0x180012623  jnz     short loc_18001262F
0x180012625  mov     edi, 8007000Eh
0x18001262a  jmp     loc_18001272E
0x18001262f  mov     [rsp+78h+var_48], rdi
0x180012634  mov     [rsp+78h+var_40], 1
0x18001263c  cmp     dword ptr [rdi+60h], 0
0x180012640  jz      short loc_180012654
0x180012642  mov     dl, 1; Wait
0x180012644  mov     rcx, rdi; Resource
0x180012647  call    cs:__imp_RtlAcquireResourceExclusive
0x18001264e  nop     dword ptr [rax+rax+00h]
0x180012653  nop
0x180012654  mov     [rsp+78h+BackTraceHash], 0
0x18001265f  lea     rax, [rsp+78h+BackTraceHash]
0x180012667  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18001266c  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180012674  mov     r9, rbx; lpParameter
0x180012677  lea     r8, ?staticTransferWorkItem@CListenerEx@@CAKPEAX@Z; lpStartAddress
0x18001267e  xor     edx, edx; dwStackSize
0x180012680  xor     ecx, ecx; lpThreadAttributes
0x180012682  call    cs:__imp_CreateThread
0x180012689  nop     dword ptr [rax+rax+00h]
0x18001268e  mov     rsi, rax
0x180012691  test    rax, rax
0x180012694  jnz     short loc_1800126DF
0x180012696  call    cs:__imp_GetLastError
0x18001269d  nop     dword ptr [rax+rax+00h]
0x1800126a2  mov     edi, eax
0x1800126a4  test    eax, eax
0x1800126a6  jle     short loc_1800126B1
0x1800126a8  movzx   edi, ax
0x1800126ab  or      edi, 80070000h
0x1800126b1  mov     r8d, edi
0x1800126b4  lea     rdx, aCreatethreadTr; "CreateThread( Tranfer ) failed: 0x%x"
0x1800126bb  mov     ecx, 8; int
0x1800126c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800126c5  nop
0x1800126c6  lea     rcx, [rsp+78h+var_48]; this
0x1800126cb  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800126d0  nop
0x1800126d1  test    edi, edi
0x1800126d3  jns     short loc_18001272E
0x1800126d5  mov     rcx, rbx; this
0x1800126d8  call    ??_GTRANSFER_THREAD_INFO@CListenerEx@@QEAAPEAXI@Z; CListenerEx::TRANSFER_THREAD_INFO::`scalar deleting destructor'(uint)
0x1800126dd  jmp     short loc_18001272E
0x1800126df  mov     rcx, [rbx+10h]; hObject
0x1800126e3  test    rcx, rcx
0x1800126e6  jz      short loc_1800126F4
0x1800126e8  call    cs:__imp_CloseHandle
0x1800126ef  nop     dword ptr [rax+rax+00h]
0x1800126f4  mov     [rbx+10h], rsi
0x1800126f8  mov     rax, [r14+8]
0x1800126fc  cmp     [rax], r14
0x1800126ff  jz      short loc_180012708
0x180012701  mov     ecx, 3
0x180012706  int     29h; Win8: RtlFailFast(ecx)
0x180012708  mov     [rbx], r14
0x18001270b  mov     [rbx+8], rax
0x18001270f  mov     [rax], rbx
0x180012712  mov     [r14+8], rbx
0x180012716  cmp     dword ptr [rdi+60h], 0
0x18001271a  jz      short loc_18001272C
0x18001271c  mov     rcx, rdi; Resource
0x18001271f  call    cs:__imp_RtlReleaseResource
0x180012726  nop     dword ptr [rax+rax+00h]
0x18001272b  nop
0x18001272c  xor     edi, edi
0x18001272e  mov     eax, edi
0x180012730  lea     r11, [rsp+78h+var_28]
0x180012735  mov     rbx, [r11+38h]
0x180012739  mov     rbp, [r11+48h]
0x18001273d  mov     rsp, r11
0x180012740  pop     r15
0x180012742  pop     r14
0x180012744  pop     r12
0x180012746  pop     rdi
0x180012747  pop     rsi
0x180012748  retn
```
