# CListenerEx::SpawnTransferWorkItem(IConnection *)

- ea: `0x180011cb8`
- end: `0x180011f73`
- name: `?SpawnTransferWorkItem@CListenerEx@@AEAAJPEAVIConnection@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(CListenerEx *__hidden this, struct IConnection *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001bcf8`

## callees

- `0x18000a210`
- `0x180011cb8`
- `0x180011f80`
- `0x180011fa4`
- `0x180012350`
- `0x180024a8c`
- `0x1800326dc`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180011e14`
- `ntdll!RtlCaptureStackBackTrace` at `0x180011e14`
- `ntdll!RtlAcquireResourceExclusive` at `0x180011cf2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180011e8f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180011cf2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180011e8f`
- `ntdll!RtlReleaseResource` at `0x180011d6a`
- `ntdll!RtlReleaseResource` at `0x180011f4f`
- `ntdll!RtlReleaseResource` at `0x180011d6a`
- `ntdll!RtlReleaseResource` at `0x180011f4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011d26`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ed2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011ec4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011ec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f1e`

## string_xrefs

- `0x180011eea`: `CreateThread( Tranfer ) failed: 0x%x`

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
0x180011cb8  mov     rax, rsp
0x180011cbb  mov     [rax+10h], rbx
0x180011cbf  mov     [rax+20h], rbp
0x180011cc3  push    rsi
0x180011cc4  push    rdi
0x180011cc5  push    r12
0x180011cc7  push    r14
0x180011cc9  push    r15
0x180011ccb  sub     rsp, 50h
0x180011ccf  mov     r15, rdx
0x180011cd2  mov     rbp, rcx
0x180011cd5  lea     rdi, [rcx+0C80h]
0x180011cdc  mov     [rax-48h], rdi
0x180011ce0  mov     dword ptr [rax-40h], 1
0x180011ce7  cmp     dword ptr [rdi+60h], 0
0x180011ceb  jz      short loc_180011CF9
0x180011ced  mov     dl, 1; Wait
0x180011cef  mov     rcx, rdi; Resource
0x180011cf2  call    cs:__imp_RtlAcquireResourceExclusive
0x180011cf8  nop
0x180011cf9  lea     r14, [rbp+0C70h]
0x180011d00  mov     rsi, [r14]
0x180011d03  cmp     rsi, r14
0x180011d06  jz      short loc_180011D61
0x180011d08  mov     r12, [rsi]
0x180011d0b  lea     rcx, [rsi+28h]; lpCriticalSection
0x180011d0f  call    cs:__imp_EnterCriticalSection
0x180011d15  nop
0x180011d16  lea     rcx, [rsi+28h]; lpCriticalSection
0x180011d1a  call    cs:__imp_LeaveCriticalSection
0x180011d20  xor     edx, edx; dwMilliseconds
0x180011d22  mov     rcx, [rsi+10h]; hHandle
0x180011d26  call    cs:__imp_WaitForSingleObject
0x180011d2c  test    eax, eax
0x180011d2e  jnz     short loc_180011D59
0x180011d30  mov     rax, [rsi]
0x180011d33  cmp     [rax+8], rsi
0x180011d37  jnz     loc_180011E5F
0x180011d3d  mov     rcx, [rsi+8]
0x180011d41  cmp     [rcx], rsi
0x180011d44  jnz     loc_180011E5F
0x180011d4a  mov     [rcx], rax
0x180011d4d  mov     [rax+8], rcx
0x180011d51  mov     rcx, rsi; this
0x180011d54  call    ??_GTRANSFER_THREAD_INFO@CListenerEx@@QEAAPEAXI@Z; CListenerEx::TRANSFER_THREAD_INFO::`scalar deleting destructor'(uint)
0x180011d59  mov     rsi, r12
0x180011d5c  cmp     r12, r14
0x180011d5f  jnz     short loc_180011D08
0x180011d61  cmp     dword ptr [rdi+60h], 0
0x180011d65  jz      short loc_180011D71
0x180011d67  mov     rcx, rdi; Resource
0x180011d6a  call    cs:__imp_RtlReleaseResource
0x180011d70  nop
0x180011d71  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d78  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011d7d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011d82  mov     rbx, rax
0x180011d85  mov     [rsp+78h+arg_10], rax
0x180011d8d  test    rax, rax
0x180011d90  jz      loc_180011E66
0x180011d96  mov     qword ptr [rax+10h], 0
0x180011d9e  mov     qword ptr [rax+18h], 0
0x180011da6  mov     qword ptr [rax+20h], 0
0x180011dae  lea     rcx, [rax+28h]; this
0x180011db2  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x180011db7  nop
0x180011db8  mov     [rbx+8], rbx
0x180011dbc  mov     [rbx], rbx
0x180011dbf  mov     rsi, [rbx+20h]
0x180011dc3  mov     [rbx+20h], rbp
0x180011dc7  test    rbp, rbp
0x180011dca  jz      short loc_180011E1F
0x180011dcc  cmp     dword ptr [rbp+0Ch], 1
0x180011dd0  jnz     short loc_180011E1A
0x180011dd2  mov     eax, 1
0x180011dd7  lock xadd [rbp+20h], eax
0x180011ddc  inc     eax
0x180011dde  mov     [rsp+78h+BackTraceHash], 0
0x180011de9  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x180011df0  jnz     short loc_180011E1A
0x180011df2  and     eax, 1Fh
0x180011df5  lea     r8, [rax+rax*2]
0x180011df9  shl     r8, 4
0x180011dfd  add     r8, 28h ; '('
0x180011e01  add     r8, rbp; BackTrace
0x180011e04  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x180011e0c  mov     edx, 6; FramesToCapture
0x180011e11  lea     ecx, [rdx-5]; FramesToSkip
0x180011e14  call    cs:__imp_RtlCaptureStackBackTrace
0x180011e1a  lock inc qword ptr [rbp+18h]
0x180011e1f  test    rsi, rsi
0x180011e22  jz      short loc_180011E2C
0x180011e24  mov     rcx, rsi
0x180011e27  call    ?Release@?$CTSPrivateObject@VIListenerItem@@@@UEAAKXZ; CTSPrivateObject<IListenerItem>::Release(void)
0x180011e2c  mov     rsi, [rbx+18h]
0x180011e30  mov     [rbx+18h], r15
0x180011e34  test    r15, r15
0x180011e37  jz      short loc_180011E48
0x180011e39  mov     rax, [r15]
0x180011e3c  mov     rcx, r15
0x180011e3f  mov     rax, [rax+8]
0x180011e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e48  test    rsi, rsi
0x180011e4b  jz      short loc_180011E5D
0x180011e4d  mov     rax, [rsi]
0x180011e50  mov     rcx, rsi
0x180011e53  mov     rax, [rax+10h]
0x180011e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e5c  nop
0x180011e5d  jmp     short loc_180011E68
0x180011e5f  mov     ecx, 3
0x180011e64  int     29h; Win8: RtlFailFast(ecx)
0x180011e66  xor     ebx, ebx
0x180011e68  test    rbx, rbx
0x180011e6b  jnz     short loc_180011E77
0x180011e6d  mov     edi, 8007000Eh
0x180011e72  jmp     loc_180011F58
0x180011e77  mov     [rsp+78h+var_48], rdi
0x180011e7c  mov     [rsp+78h+var_40], 1
0x180011e84  cmp     dword ptr [rdi+60h], 0
0x180011e88  jz      short loc_180011E96
0x180011e8a  mov     dl, 1; Wait
0x180011e8c  mov     rcx, rdi; Resource
0x180011e8f  call    cs:__imp_RtlAcquireResourceExclusive
0x180011e95  nop
0x180011e96  mov     [rsp+78h+BackTraceHash], 0
0x180011ea1  lea     rax, [rsp+78h+BackTraceHash]
0x180011ea9  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180011eae  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180011eb6  mov     r9, rbx; lpParameter
0x180011eb9  lea     r8, ?staticTransferWorkItem@CListenerEx@@CAKPEAX@Z; lpStartAddress
0x180011ec0  xor     edx, edx; dwStackSize
0x180011ec2  xor     ecx, ecx; lpThreadAttributes
0x180011ec4  call    cs:__imp_CreateThread
0x180011eca  mov     rsi, rax
0x180011ecd  test    rax, rax
0x180011ed0  jnz     short loc_180011F15
0x180011ed2  call    cs:__imp_GetLastError
0x180011ed8  mov     edi, eax
0x180011eda  test    eax, eax
0x180011edc  jle     short loc_180011EE7
0x180011ede  movzx   edi, ax
0x180011ee1  or      edi, 80070000h
0x180011ee7  mov     r8d, edi
0x180011eea  lea     rdx, aCreatethreadTr; "CreateThread( Tranfer ) failed: 0x%x"
0x180011ef1  mov     ecx, 8; int
0x180011ef6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011efb  nop
0x180011efc  lea     rcx, [rsp+78h+var_48]; this
0x180011f01  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180011f06  nop
0x180011f07  test    edi, edi
0x180011f09  jns     short loc_180011F58
0x180011f0b  mov     rcx, rbx; this
0x180011f0e  call    ??_GTRANSFER_THREAD_INFO@CListenerEx@@QEAAPEAXI@Z; CListenerEx::TRANSFER_THREAD_INFO::`scalar deleting destructor'(uint)
0x180011f13  jmp     short loc_180011F58
0x180011f15  mov     rcx, [rbx+10h]; hObject
0x180011f19  test    rcx, rcx
0x180011f1c  jz      short loc_180011F24
0x180011f1e  call    cs:__imp_CloseHandle
0x180011f24  mov     [rbx+10h], rsi
0x180011f28  mov     rax, [r14+8]
0x180011f2c  cmp     [rax], r14
0x180011f2f  jz      short loc_180011F38
0x180011f31  mov     ecx, 3
0x180011f36  int     29h; Win8: RtlFailFast(ecx)
0x180011f38  mov     [rbx], r14
0x180011f3b  mov     [rbx+8], rax
0x180011f3f  mov     [rax], rbx
0x180011f42  mov     [r14+8], rbx
0x180011f46  cmp     dword ptr [rdi+60h], 0
0x180011f4a  jz      short loc_180011F56
0x180011f4c  mov     rcx, rdi; Resource
0x180011f4f  call    cs:__imp_RtlReleaseResource
0x180011f55  nop
0x180011f56  xor     edi, edi
0x180011f58  mov     eax, edi
0x180011f5a  lea     r11, [rsp+78h+var_28]
0x180011f5f  mov     rbx, [r11+38h]
0x180011f63  mov     rbp, [r11+48h]
0x180011f67  mov     rsp, r11
0x180011f6a  pop     r15
0x180011f6c  pop     r14
0x180011f6e  pop     r12
0x180011f70  pop     rdi
0x180011f71  pop     rsi
0x180011f72  retn
```
