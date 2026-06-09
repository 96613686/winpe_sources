# WapCreateSessionHandle

- ea: `0x18001e5b8`
- end: `0x18001eb3d`
- name: `WapCreateSessionHandle`
- size: `1413`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e590`

## callees

- `0x180014f30`
- `0x1800180e0`
- `0x18001e5b8`
- `0x18001f18c`
- `0x18001f3d8`
- `0x18001f410`
- `0x18001f5f0`
- `0x18001f6c0`
- `0x18001f750`
- `0x18001f9e8`
- `0x1800391c0`
- `0x18004e5a0`
- `0x1800650b4`
- `0x18006ad9c`
- `0x1800722f0`
- `0x180072c70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e889`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e889`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e89a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e89a`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001e82e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001e82e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e706`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e706`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e726`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e726`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e84a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e84a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e879`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e879`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001e773`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001e773`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e627`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e645`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e8c5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e8ec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e9eb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e627`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e645`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e8c5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e8ec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e9eb`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18001e7fe`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18001e7fe`

## pseudocode

```c
__int64 __fastcall WapCreateSessionHandle(union _SLIST_HEADER *a1, int a2, union _SLIST_HEADER *a3)
{
  union _SLIST_HEADER *v4; // r12
  int v5; // r13d
  __int64 v6; // rdx
  __int64 v7; // rcx
  ULONG v8; // eax
  __int64 v9; // rdi
  unsigned __int64 v10; // r8
  RTL_SRWLOCK *v11; // rsi
  RTL_SRWLOCK *v12; // rbx
  volatile signed __int32 *Ptr; // rsi
  __int64 Heap; // rax
  int v15; // r8d
  int v16; // r9d
  unsigned int EndpointManager; // ebx
  __int64 v18; // rdx
  unsigned __int8 CurrentProcessorNumber; // al
  unsigned int v20; // r13d
  __int64 v21; // r14
  union _SLIST_HEADER *v22; // rax
  PSLIST_ENTRY v23; // rax
  PSLIST_ENTRY v24; // r12
  int v25; // eax
  ULONGLONG v26; // r13
  DWORD v27; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  union _SLIST_HEADER *v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  union _SLIST_HEADER *v37; // [rsp+58h] [rbp-A8h] BYREF
  GUID v38; // [rsp+60h] [rbp-A0h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+80h] [rbp-80h]
  GUID v41; // [rsp+88h] [rbp-78h] BYREF
  ULONGLONG Alignment; // [rsp+98h] [rbp-68h] BYREF
  char v43[16]; // [rsp+A0h] [rbp-60h] BYREF
  union _SLIST_HEADER **v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h]
  union _SLIST_HEADER **v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 *v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  __int64 *p_Alignment; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+E8h] [rbp-18h]
  GUID *v52; // [rsp+F0h] [rbp-10h]
  __int64 v53; // [rsp+F8h] [rbp-8h]
  int *v54; // [rsp+100h] [rbp+0h]
  __int64 v55; // [rsp+108h] [rbp+8h]

  v34 = a1;
  v37 = a3;
  v36 = a2;
  v40 = 0;
  v38 = 0;
  v4 = a3;
  v5 = a2;
  ActivityId = 0;
  WapEtwGenerateActivityIdFromEnvironment(&v38);
  LOBYTE(v40) = 0;
  if ( !EventActivityIdControl(1u, &ActivityId) )
  {
    if ( !(_BYTE)v40 )
    {
      v8 = EventActivityIdControl(2u, &v38);
      v7 = (unsigned __int8)v40;
      if ( !v8 )
        v7 = 1;
      LOBYTE(v40) = v7;
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v7, v6, &v38, &ActivityId);
  }
  if ( !(_BYTE)v40 )
    ActivityId = 0;
  v4->Alignment = 0;
  LOBYTE(v9) = 0;
  if ( (v5 & 0x7FFFFFFF) != 0 )
  {
    LODWORD(Ptr) = 0;
    EndpointManager = 87;
    goto LABEL_45;
  }
  if ( !WaHandleTableInitialized
    || ((unsigned int)a1 & 0xF0000000) != 0x10000000
    || (v10 = (unsigned __int64)BYTE4(v34) << 6,
        (unsigned int)(unsigned __int16)(HIDWORD(v34) >> 8) >= *(_DWORD *)((char *)WaHandleTable + v10 + 16))
    || (v7 = (unsigned __int16)(HIDWORD(v34) >> 8),
        v11 = (RTL_SRWLOCK *)(32 * ((unsigned __int64)HIDWORD(v34) >> 24)
                            + *(_QWORD *)(*(_QWORD *)((char *)WaHandleTable + v10 + 8) + 8 * v7)),
        v11[3].Ptr != a1)
    || !v11 )
  {
    LODWORD(Ptr) = 0;
LABEL_56:
    EndpointManager = 6;
    goto LABEL_45;
  }
  v12 = v11 + 2;
  AcquireSRWLockShared(v11 + 2);
  if ( v11[3].Ptr == a1 )
  {
    Ptr = (volatile signed __int32 *)v11->Ptr;
    _InterlockedIncrement(Ptr + 1);
  }
  else
  {
    Ptr = 0;
  }
  ReleaseSRWLockShared(v12);
  if ( !Ptr )
    goto LABEL_56;
  Heap = WxAllocateHeapEx(v7, 408);
  v9 = Heap;
  if ( !Heap )
  {
    v21 = 0;
    EndpointManager = 8;
    goto LABEL_35;
  }
  memset_0((void *)(Heap + 8), 0, 0x190u);
  *(_DWORD *)v9 = 1397966163;
  *(_DWORD *)(v9 + 4) = 1;
  InitializeSRWLock((PSRWLOCK)(v9 + 8));
  *(_QWORD *)(v9 + 16) = Ptr;
  _InterlockedIncrement(Ptr + 1);
  if ( v5 < 0 )
    *(_BYTE *)(v9 + 33) = 1;
  EndpointManager = WaCreateEndpointManager(v9, 0, v15, v16, v9 + 40);
  if ( EndpointManager )
  {
    *(_QWORD *)(v9 + 40) = 0;
    goto LABEL_42;
  }
  EndpointManager = WaGetCurrentThreadToken((__int64 *)(v9 + 112));
  if ( EndpointManager )
  {
    *(_QWORD *)(v9 + 112) = 0;
    goto LABEL_42;
  }
  EndpointManager = WaCreateCookieJar(v9 + 48);
  if ( EndpointManager )
  {
    *(_QWORD *)(v9 + 48) = 0;
LABEL_42:
    WapCleanupSession((LPVOID)v9);
    v21 = 0;
    LOBYTE(v9) = 0;
    goto LABEL_35;
  }
  EndpointManager = WaCreateDnsCache(v9, v18, v9 + 56);
  if ( EndpointManager )
  {
    *(_QWORD *)(v9 + 56) = 0;
    goto LABEL_42;
  }
  *(_DWORD *)(v9 + 360) = 1;
  *(_QWORD *)(v9 + 344) = 2;
  CurrentProcessorNumber = RtlGetCurrentProcessorNumber();
  v20 = CurrentProcessorNumber;
  v21 = v9;
  v22 = (union _SLIST_HEADER *)((char *)WaHandleTable + 64 * (unsigned __int64)CurrentProcessorNumber + 32);
  v34 = v22;
  while ( 1 )
  {
    v23 = InterlockedPopEntrySList(v22);
    v24 = v23;
    if ( v23 )
      break;
    EndpointManager = WapExpandHandleTable(v20);
    v22 = v34;
    if ( EndpointManager )
    {
      WapCleanupSession((LPVOID)v9);
      v4 = v37;
      goto LABEL_34;
    }
  }
  AcquireSRWLockExclusive((PSRWLOCK)&v23[1]);
  v25 = *((_DWORD *)&v24[1].Next + 2) + 1;
  v24->Next = (struct _SLIST_ENTRY *)v9;
  *((_DWORD *)&v24[1].Next + 2) = v25 & 0xFFFFFFF | 0x20000000;
  v26 = *((_QWORD *)&v24[1].Next + 1);
  ReleaseSRWLockExclusive((PSRWLOCK)&v24[1]);
  *(_QWORD *)(v9 + 24) = v26;
  v27 = GetCurrentThreadId() << 16;
  CurrentProcessId = GetCurrentProcessId();
  *(_QWORD *)(v9 + 120) = v26;
  *(_DWORD *)(v9 + 128) = v9;
  *(_DWORD *)(v9 + 132) = v27 ^ CurrentProcessId;
  v41 = 0;
  if ( !EventActivityIdControl(1u, &v41) )
  {
    if ( !Microsoft_Windows_Networking_CorrelationEnabled
      || !(unsigned int)EtwEx_tidActivityInfo(v29, ActivityStart, v9 + 120) )
    {
      EventActivityIdControl(2u, &v41);
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v31, v30, v9 + 120, &v41);
  }
  v4 = v37;
  EndpointManager = 0;
  v37->Alignment = v26;
LABEL_34:
  v5 = v36;
LABEL_35:
  WaDereferenceApiObject(Ptr);
  LODWORD(v7) = 0;
  if ( !EndpointManager )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 1) != 0 )
    {
      *(_QWORD *)&v41.Data1 = (unsigned int)v5;
      Alignment = v4->Alignment;
      v44 = &v34;
      v46 = &v37;
      v48 = &v35;
      p_Alignment = (__int64 *)&Alignment;
      v52 = &v41;
      v54 = &v36;
      v36 = 0;
      v35 = v21;
      v37 = a1;
      v34 = (union _SLIST_HEADER *)Ptr;
      v45 = 8;
      v47 = 8;
      v49 = 8;
      v51 = 8;
      v53 = 8;
      v55 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ApiCreateSessionTrace, v32, 7, v43);
    }
    goto LABEL_38;
  }
LABEL_45:
  if ( (Microsoft_Windows_WebIOEnableBits & 2) != 0 )
    McTemplateU0pxpxxq_EventWriteTransfer(
      v7,
      (unsigned int)ApiCreateSessionFailedTrace,
      (_DWORD)Ptr,
      (_DWORD)a1,
      v9,
      v4->Alignment,
      v5,
      EndpointManager);
LABEL_38:
  if ( (_BYTE)v40 )
    EventActivityIdControl(2u, &ActivityId);
  return EndpointManager;
}

```

## disassembly

```asm
0x18001e5b8  mov     [rsp-8+arg_8], rbx
0x18001e5bd  push    rbp
0x18001e5be  push    rsi
0x18001e5bf  push    rdi
0x18001e5c0  push    r12
0x18001e5c2  push    r13
0x18001e5c4  push    r14
0x18001e5c6  push    r15
0x18001e5c8  lea     rbp, [rsp-20h]
0x18001e5cd  sub     rsp, 120h
0x18001e5d4  mov     rax, cs:__security_cookie
0x18001e5db  xor     rax, rsp
0x18001e5de  mov     [rbp+50h+var_40], rax
0x18001e5e2  xorps   xmm0, xmm0
0x18001e5e5  mov     [rsp+150h+var_110], rcx
0x18001e5ea  mov     r15, rcx
0x18001e5ed  mov     [rsp+150h+var_F8], r8
0x18001e5f2  xor     eax, eax
0x18001e5f4  mov     [rsp+150h+var_100], edx
0x18001e5f8  lea     rcx, [rsp+150h+var_F0]
0x18001e5fd  mov     [rbp+50h+var_D0], eax
0x18001e600  movups  xmmword ptr [rsp+150h+var_F0.Data1], xmm0
0x18001e605  mov     r12, r8
0x18001e608  mov     r13d, edx
0x18001e60b  movups  xmmword ptr [rsp+150h+ActivityId.Data1], xmm0
0x18001e610  call    WapEtwGenerateActivityIdFromEnvironment
0x18001e615  xor     r14d, r14d
0x18001e618  lea     rdx, [rsp+150h+ActivityId]; ActivityId
0x18001e61d  mov     byte ptr [rbp+50h+var_D0], r14b
0x18001e621  lea     ebx, [r14+1]
0x18001e625  mov     ecx, ebx; ControlCode
0x18001e627  call    cs:__imp_EventActivityIdControl
0x18001e62e  nop     dword ptr [rax+rax+00h]
0x18001e633  test    eax, eax
0x18001e635  jnz     short loc_18001E66B
0x18001e637  cmp     byte ptr [rbp+50h+var_D0], r14b
0x18001e63b  jnz     short loc_18001E65D
0x18001e63d  lea     rdx, [rsp+150h+var_F0]; ActivityId
0x18001e642  lea     ecx, [rbx+1]; ControlCode
0x18001e645  call    cs:__imp_EventActivityIdControl
0x18001e64c  nop     dword ptr [rax+rax+00h]
0x18001e651  movzx   ecx, byte ptr [rbp+50h+var_D0]
0x18001e655  test    eax, eax
0x18001e657  cmovz   ecx, ebx
0x18001e65a  mov     byte ptr [rbp+50h+var_D0], cl
0x18001e65d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18001e663  test    eax, eax
0x18001e665  jnz     loc_18001EAC8
0x18001e66b  cmp     byte ptr [rbp+50h+var_D0], r14b
0x18001e66f  jz      loc_18001EA21
0x18001e675  mov     [r12], r14
0x18001e679  mov     rdi, r14
0x18001e67c  test    r13d, 7FFFFFFFh
0x18001e683  jnz     loc_18001EA50
0x18001e689  cmp     cs:WaHandleTableInitialized, r14b
0x18001e690  jz      loc_18001EB30
0x18001e696  mov     eax, r15d
0x18001e699  and     eax, 0F0000000h
0x18001e69e  cmp     eax, 10000000h
0x18001e6a3  jnz     loc_18001EB30
0x18001e6a9  mov     eax, dword ptr [rsp+150h+var_110+4]
0x18001e6ad  mov     r9, cs:WaHandleTable
0x18001e6b4  mov     edx, eax
0x18001e6b6  movzx   r8d, al
0x18001e6ba  shr     eax, 8
0x18001e6bd  shl     r8, 6
0x18001e6c1  movzx   eax, ax
0x18001e6c4  cmp     eax, [r8+r9+10h]
0x18001e6c9  jnb     loc_18001EB30
0x18001e6cf  mov     eax, edx
0x18001e6d1  shr     rdx, 18h
0x18001e6d5  shr     rax, 8
0x18001e6d9  movzx   ecx, ax
0x18001e6dc  mov     rax, [r8+r9+8]
0x18001e6e1  shl     rdx, 5
0x18001e6e5  mov     rsi, [rax+rcx*8]
0x18001e6e9  add     rsi, rdx
0x18001e6ec  cmp     [rsi+18h], r15
0x18001e6f0  jnz     loc_18001EB30
0x18001e6f6  test    rsi, rsi
0x18001e6f9  jz      loc_18001EB30
0x18001e6ff  lea     rbx, [rsi+10h]
0x18001e703  mov     rcx, rbx; SRWLock
0x18001e706  call    cs:__imp_AcquireSRWLockShared
0x18001e70d  nop     dword ptr [rax+rax+00h]
0x18001e712  cmp     [rsi+18h], r15
0x18001e716  jnz     loc_18001EA48
0x18001e71c  mov     rsi, [rsi]
0x18001e71f  lock inc dword ptr [rsi+4]
0x18001e723  mov     rcx, rbx; SRWLock
0x18001e726  call    cs:__imp_ReleaseSRWLockShared
0x18001e72d  nop     dword ptr [rax+rax+00h]
0x18001e732  test    rsi, rsi
0x18001e735  jz      loc_18001EB33
0x18001e73b  mov     edx, 198h
0x18001e740  call    WxAllocateHeapEx
0x18001e745  mov     rdi, rax
0x18001e748  test    rax, rax
0x18001e74b  jz      loc_18001EB09
0x18001e751  lea     rcx, [rax+8]; void *
0x18001e755  xor     edx, edx; Val
0x18001e757  mov     r8d, 190h; Size
0x18001e75d  call    memset_0
0x18001e762  lea     rcx, [rdi+8]; SRWLock
0x18001e766  mov     dword ptr [rdi], 53534553h
0x18001e76c  mov     dword ptr [rdi+4], 1
0x18001e773  call    cs:__imp_InitializeSRWLock
0x18001e77a  nop     dword ptr [rax+rax+00h]
0x18001e77f  mov     [rdi+10h], rsi
0x18001e783  lock inc dword ptr [rsi+4]
0x18001e787  test    r13d, r13d
0x18001e78a  jns     short loc_18001E790
0x18001e78c  mov     byte ptr [rdi+21h], 1
0x18001e790  lea     r14, [rdi+28h]
0x18001e794  xor     edx, edx
0x18001e796  mov     rcx, rdi
0x18001e799  mov     [rsp+150h+var_130], r14
0x18001e79e  call    WaCreateEndpointManager
0x18001e7a3  mov     ebx, eax
0x18001e7a5  test    eax, eax
0x18001e7a7  jnz     loc_18001EA96
0x18001e7ad  lea     rcx, [rdi+70h]
0x18001e7b1  call    WaGetCurrentThreadToken
0x18001e7b6  mov     ebx, eax
0x18001e7b8  test    eax, eax
0x18001e7ba  jnz     loc_18001EB16
0x18001e7c0  lea     rcx, [rdi+30h]
0x18001e7c4  call    WaCreateCookieJar
0x18001e7c9  mov     ebx, eax
0x18001e7cb  test    eax, eax
0x18001e7cd  jnz     loc_18001EA2E
0x18001e7d3  lea     r8, [rdi+38h]
0x18001e7d7  mov     rcx, rdi
0x18001e7da  call    WaCreateDnsCache
0x18001e7df  mov     ebx, eax
0x18001e7e1  test    eax, eax
0x18001e7e3  jnz     loc_18001EB23
0x18001e7e9  mov     dword ptr [rdi+168h], 1
0x18001e7f3  mov     qword ptr [rdi+158h], 2
0x18001e7fe  call    cs:__imp_RtlGetCurrentProcessorNumber
0x18001e805  nop     dword ptr [rax+rax+00h]
0x18001e80a  movzx   r13d, al
0x18001e80e  mov     r14, rdi
0x18001e811  mov     rax, cs:WaHandleTable
0x18001e818  mov     ecx, r13d
0x18001e81b  shl     rcx, 6
0x18001e81f  add     rax, 20h ; ' '
0x18001e823  add     rax, rcx
0x18001e826  mov     [rsp+150h+var_110], rax
0x18001e82b  mov     rcx, rax; ListHead
0x18001e82e  call    cs:__imp_InterlockedPopEntrySList
0x18001e835  nop     dword ptr [rax+rax+00h]
0x18001e83a  mov     r12, rax
0x18001e83d  test    rax, rax
0x18001e840  jz      loc_18001EA9F
0x18001e846  lea     rcx, [rax+10h]; SRWLock
0x18001e84a  call    cs:__imp_AcquireSRWLockExclusive
0x18001e851  nop     dword ptr [rax+rax+00h]
0x18001e856  mov     eax, [r12+18h]
0x18001e85b  lea     rcx, [r12+10h]; SRWLock
0x18001e860  inc     eax
0x18001e862  mov     [r12], rdi
0x18001e866  and     eax, 0FFFFFFFh
0x18001e86b  bts     eax, 1Dh
0x18001e86f  mov     [r12+18h], eax
0x18001e874  mov     r13, [r12+18h]
0x18001e879  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e880  nop     dword ptr [rax+rax+00h]
0x18001e885  mov     [rdi+18h], r13
0x18001e889  call    cs:__imp_GetCurrentThreadId
0x18001e890  nop     dword ptr [rax+rax+00h]
0x18001e895  mov     ebx, eax
0x18001e897  shl     ebx, 10h
0x18001e89a  call    cs:__imp_GetCurrentProcessId
0x18001e8a1  nop     dword ptr [rax+rax+00h]
0x18001e8a6  xorps   xmm0, xmm0
0x18001e8a9  lea     rdx, [rbp+50h+var_C8]; ActivityId
0x18001e8ad  xor     eax, ebx
0x18001e8af  mov     ecx, 1; ControlCode
0x18001e8b4  lea     rbx, [rdi+78h]
0x18001e8b8  mov     [rbx], r13
0x18001e8bb  mov     [rbx+8], edi
0x18001e8be  mov     [rbx+0Ch], eax
0x18001e8c1  movups  xmmword ptr [rbp+50h+var_C8.Data1], xmm0
0x18001e8c5  call    cs:__imp_EventActivityIdControl
0x18001e8cc  nop     dword ptr [rax+rax+00h]
0x18001e8d1  test    eax, eax
0x18001e8d3  jnz     short loc_18001E906
0x18001e8d5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18001e8db  test    eax, eax
0x18001e8dd  jnz     loc_18001EAED
0x18001e8e3  lea     rdx, [rbp+50h+var_C8]; ActivityId
0x18001e8e7  mov     ecx, 2; ControlCode
0x18001e8ec  call    cs:__imp_EventActivityIdControl
0x18001e8f3  nop     dword ptr [rax+rax+00h]
0x18001e8f8  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18001e8fe  test    eax, eax
0x18001e900  jnz     loc_18001EADC
0x18001e906  mov     r12, [rsp+150h+var_F8]
0x18001e90b  xor     ebx, ebx
0x18001e90d  mov     [r12], r13
0x18001e911  mov     r13d, [rsp+150h+var_100]
0x18001e916  mov     rcx, rsi
0x18001e919  call    WaDereferenceApiObject
0x18001e91e  xor     ecx, ecx
0x18001e920  test    ebx, ebx
0x18001e922  jnz     loc_18001EA58
0x18001e928  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 1
0x18001e92f  jz      loc_18001E9DB
0x18001e935  mov     eax, r13d
0x18001e938  lea     r9d, [rcx+7]
0x18001e93c  mov     qword ptr [rbp+50h+var_C8.Data1], rax
0x18001e940  lea     rdx, ApiCreateSessionTrace
0x18001e947  mov     rax, [r12]
0x18001e94b  mov     [rbp+50h+var_B8], rax
0x18001e94f  lea     rax, [rsp+150h+var_110]
0x18001e954  mov     [rbp+50h+var_A0], rax
0x18001e958  lea     rax, [rsp+150h+var_F8]
0x18001e95d  mov     [rbp+50h+var_90], rax
0x18001e961  lea     rax, [rsp+150h+var_108]
0x18001e966  mov     [rbp+50h+var_80], rax
0x18001e96a  lea     rax, [rbp+50h+var_B8]
0x18001e96e  mov     [rbp+50h+var_70], rax
0x18001e972  lea     rax, [rbp+50h+var_C8]
0x18001e976  mov     [rbp+50h+var_60], rax
0x18001e97a  lea     rax, [rsp+150h+var_100]
0x18001e97f  mov     [rbp+50h+var_50], rax
0x18001e983  lea     rax, [rbp+50h+var_B0]
0x18001e987  mov     [rsp+150h+var_100], ecx
0x18001e98b  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18001e992  mov     [rsp+150h+var_130], rax
0x18001e997  mov     [rsp+150h+var_108], r14
0x18001e99c  mov     [rsp+150h+var_F8], r15
0x18001e9a1  mov     [rsp+150h+var_110], rsi
0x18001e9a6  mov     [rbp+50h+var_98], 8
0x18001e9ae  mov     [rbp+50h+var_88], 8
0x18001e9b6  mov     [rbp+50h+var_78], 8
0x18001e9be  mov     [rbp+50h+var_68], 8
0x18001e9c6  mov     [rbp+50h+var_58], 8
0x18001e9ce  mov     [rbp+50h+var_48], 4
0x18001e9d6  call    McGenEventWrite_EventWriteTransfer
0x18001e9db  cmp     byte ptr [rbp+50h+var_D0], 0
0x18001e9df  jz      short loc_18001E9F7
0x18001e9e1  lea     rdx, [rsp+150h+ActivityId]; ActivityId
0x18001e9e6  mov     ecx, 2; ControlCode
0x18001e9eb  call    cs:__imp_EventActivityIdControl
0x18001e9f2  nop     dword ptr [rax+rax+00h]
0x18001e9f7  mov     eax, ebx
0x18001e9f9  mov     rcx, [rbp+50h+var_40]
0x18001e9fd  xor     rcx, rsp; StackCookie
0x18001ea00  call    __security_check_cookie
0x18001ea05  mov     rbx, [rsp+150h+arg_8]
0x18001ea0d  add     rsp, 120h
0x18001ea14  pop     r15
0x18001ea16  pop     r14
0x18001ea18  pop     r13
0x18001ea1a  pop     r12
0x18001ea1c  pop     rdi
0x18001ea1d  pop     rsi
0x18001ea1e  pop     rbp
0x18001ea1f  retn
0x18001ea21  xorps   xmm0, xmm0
0x18001ea24  movups  xmmword ptr [rsp+150h+ActivityId.Data1], xmm0
0x18001ea29  jmp     loc_18001E675
0x18001ea2e  mov     qword ptr [rdi+30h], 0
0x18001ea36  mov     rcx, rdi; lpMem
0x18001ea39  call    WapCleanupSession
0x18001ea3e  xor     r14d, r14d
0x18001ea41  xor     edi, edi
0x18001ea43  jmp     loc_18001E916
0x18001ea48  mov     rsi, r14
0x18001ea4b  jmp     loc_18001E723
0x18001ea50  mov     rsi, r14
0x18001ea53  mov     ebx, 57h ; 'W'
0x18001ea58  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 2
0x18001ea5f  jz      loc_18001E9DB
0x18001ea65  mov     [rsp+150h+var_118], ebx
0x18001ea69  lea     rdx, ApiCreateSessionFailedTrace
0x18001ea70  mov     eax, r13d
0x18001ea73  mov     r9, r15
0x18001ea76  mov     [rsp+150h+var_120], rax
0x18001ea7b  mov     r8, rsi
0x18001ea7e  mov     rax, [r12]
0x18001ea82  mov     [rsp+150h+var_128], rax
0x18001ea87  mov     [rsp+150h+var_130], rdi
0x18001ea8c  call    McTemplateU0pxpxxq_EventWriteTransfer
0x18001ea91  jmp     loc_18001E9DB
0x18001ea96  mov     qword ptr [r14], 0
0x18001ea9d  jmp     short loc_18001EA36
0x18001ea9f  mov     ecx, r13d
0x18001eaa2  call    WapExpandHandleTable
0x18001eaa7  mov     ebx, eax
0x18001eaa9  test    eax, eax
0x18001eaab  mov     rax, [rsp+150h+var_110]
0x18001eab0  jz      loc_18001E82B
0x18001eab6  mov     rcx, rdi; lpMem
0x18001eab9  call    WapCleanupSession
0x18001eabe  mov     r12, [rsp+150h+var_F8]
0x18001eac3  jmp     loc_18001E911
0x18001eac8  lea     r9, [rsp+150h+ActivityId]
  ... truncated ...
```
