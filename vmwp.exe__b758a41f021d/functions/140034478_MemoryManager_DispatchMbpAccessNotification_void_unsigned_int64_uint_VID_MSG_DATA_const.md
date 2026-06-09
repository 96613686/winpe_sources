# MemoryManager::DispatchMbpAccessNotification(void *,unsigned __int64,uint,_VID_MSG_DATA * const)

- ea: `0x140034478`
- end: `0x140034a32`
- name: `?DispatchMbpAccessNotification@MemoryManager@@QEAA?AUDispatchMemoryNotificationResult@@PEAX_KIQEAU_VID_MSG_DATA@@@Z`
- size: `1466`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140203d80`

## callees

- `0x140034478`
- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x14008a328`
- `0x1400ba144`
- `0x14011ea40`
- `0x1402053e4`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400347cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003480e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003489d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400347cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003480e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003489d`

## string_xrefs

- `0x1400347fc`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140034978`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140034998`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MemoryManager::DispatchMbpAccessNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v8; // r15
  signed __int32 v9; // eax
  signed __int32 v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rbp
  __int64 v13; // rdi
  __int64 v14; // rbx
  char v15; // al
  _QWORD *v16; // r12
  _DWORD *v17; // r13
  __int64 **v18; // r13
  signed __int32 *v19; // r12
  signed __int32 v20; // eax
  signed __int32 v21; // ebx
  signed __int32 v22; // edx
  __int64 *v23; // rsi
  signed __int32 *v24; // rbx
  signed __int32 v25; // eax
  signed __int32 v26; // edi
  __int64 v27; // rcx
  int v28; // edx
  int v29; // edx
  __int64 v31; // r12
  __int64 v32; // rax
  int v33; // ecx
  int v34; // ecx
  signed __int32 v35; // edx
  signed __int32 v36; // edx
  bool v37; // zf
  unsigned int v38; // [rsp+20h] [rbp-B8h]
  __int64 v39; // [rsp+40h] [rbp-98h]
  _QWORD v42[3]; // [rsp+70h] [rbp-68h] BYREF
  char v43; // [rsp+88h] [rbp-50h]
  __int64 v44; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v44 = a1;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_OWORD *)(a2 + 32) = 0;
  *(_BYTE *)a2 = 1;
  v8 = *(_QWORD *)(a1 + 160) + 24LL;
  v9 = _InterlockedCompareExchange((volatile signed __int32 *)v8, 4, 0);
  v10 = v9;
  if ( v9 )
  {
    if ( (v9 & 1) != 0 && *(_DWORD *)(v8 + 4) == GetCurrentThreadId() )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    }
    else
    {
      do
      {
        while ( (v10 & 1) != 0 )
        {
          if ( !(unsigned int)RrwpLockWait(v8, 0xFFFFFFFFLL, 0) )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
              (const char *)0x102,
              v38);
          _m_prefetchw((const void *)v8);
          v10 = *(_DWORD *)v8;
        }
        v35 = v10;
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)v8, v10 + 4, v10);
      }
      while ( v10 != v35 );
    }
    a1 = v44;
  }
  v11 = 0;
  v12 = a4;
  v13 = 0;
  v14 = 0;
  v39 = 0;
  v15 = 1;
  v16 = (_QWORD *)(a2 + 16);
  v17 = (_DWORD *)(a2 + 4);
  while ( 1 )
  {
    if ( !v15 )
    {
      RrwLockRelease(v8);
      *(_QWORD *)(a2 + 32) = v13;
      *(_QWORD *)(a2 + 40) = v14;
      if ( !v13 )
        return a2;
      v44 = v12;
      *(_BYTE *)a2 = (**(unsigned int (__fastcall ***)(__int64, __int64, _QWORD, __int64, _DWORD *, __int64 *, _QWORD *))v13)(
                       v13,
                       v12,
                       a5,
                       v14,
                       v17,
                       &v44,
                       v16) == 1;
      if ( *(_DWORD *)(v13 + 8) == 2 )
      {
        if ( *v16 > 1u )
          *v16 = 1;
      }
      else
      {
        v12 = v44;
      }
      v27 = 0;
      v28 = *(_DWORD *)(v13 + 8);
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          if ( v29 == 1 )
            v27 = v12 - *(_QWORD *)(v11 + 8);
          goto LABEL_31;
        }
      }
      else if ( *(_BYTE *)v11 )
      {
        v27 = v12 - *(_QWORD *)(v11 + 144);
LABEL_31:
        *(_QWORD *)(a2 + 8) = v27;
        return a2;
      }
      v27 = v12;
      goto LABEL_31;
    }
    v18 = *(__int64 ***)(a1 + 160);
    v19 = (signed __int32 *)(v18 + 3);
    v20 = _InterlockedCompareExchange((volatile signed __int32 *)v18 + 6, 4, 0);
    v21 = v20;
    if ( v20 )
    {
      if ( (v20 & 1) != 0 && *((_DWORD *)v18 + 7) == GetCurrentThreadId() )
      {
        _InterlockedIncrement((volatile signed __int32 *)v18 + 8);
      }
      else
      {
        do
        {
          while ( (v21 & 1) != 0 )
          {
            if ( !(unsigned int)RrwpLockWait(v18 + 3, 0xFFFFFFFFLL, 0) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v38);
            _m_prefetchw(v19);
            v21 = *v19;
          }
          v22 = v21;
          v21 = _InterlockedCompareExchange(v19, v21 + 4, v21);
        }
        while ( v21 != v22 );
      }
    }
    v23 = *v18;
    if ( *v18 == v18[1] )
    {
LABEL_16:
      v11 = 0;
    }
    else
    {
      while ( *(_QWORD *)(*v23 + 152) != a3 )
      {
        if ( ++v23 == v18[1] )
          goto LABEL_16;
      }
      v11 = *v23;
    }
    RrwLockRelease(v18 + 3);
    if ( v11 )
      break;
    *(_QWORD *)(a2 + 8) = a4;
    v17 = (_DWORD *)(a2 + 4);
    *(_DWORD *)(a2 + 4) = 3;
    v16 = (_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 1;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x8000FFFFLL,
      v38);
    if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
      VmlDebugTraceEx(0, &off_1402E4060);
    v14 = v39;
LABEL_42:
    v15 = 0;
    a1 = v44;
  }
  if ( (*(_BYTE *)(v11 + 168) & 8) == 0 )
  {
    v24 = (signed __int32 *)(v11 + 24);
    v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 24), 4, 0);
    v26 = v25;
    if ( v25 )
    {
      if ( (v25 & 1) != 0 && *(_DWORD *)(v11 + 28) == GetCurrentThreadId() )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 32));
      }
      else
      {
        do
        {
          while ( (v26 & 1) != 0 )
          {
            if ( !(unsigned int)RrwpLockWait(v11 + 24, 0xFFFFFFFFLL, 0) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v38);
            _m_prefetchw(v24);
            v26 = *v24;
          }
          v36 = v26;
          v26 = _InterlockedCompareExchange(v24, v26 + 4, v26);
        }
        while ( v26 != v36 );
      }
    }
    v31 = *(_QWORD *)(v11 + 88);
    if ( v31 == -1 )
    {
      IntervalTree<MemoryNotification>::Find(v11 + 72, v42, a4);
      if ( v43 )
      {
        v13 = v42[0];
        v32 = v42[1];
      }
      else
      {
        v13 = 0;
        v32 = 0;
      }
    }
    else
    {
      v13 = *(_QWORD *)(v11 + 88);
      v32 = *(_QWORD *)(v11 + 96);
    }
    v39 = v32;
    RrwLockRelease(v11 + 24);
    *(_BYTE *)(a2 + 24) = v31 == -1;
    v17 = (_DWORD *)(a2 + 4);
    if ( !v13 )
    {
      v14 = v39;
      v37 = v31 == -1;
      v16 = (_QWORD *)(a2 + 16);
      if ( v37 )
      {
        *v17 = 3;
        *(_QWORD *)(a2 + 8) = a4;
        *v16 = 1;
      }
      else
      {
        *v17 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *v16 = *(_QWORD *)(v11 + 120);
      }
      goto LABEL_42;
    }
    *v17 = 0;
    v16 = (_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 1;
    v12 = 0;
    v33 = *(_DWORD *)(v13 + 8);
    if ( v33 )
    {
      v34 = v33 - 1;
      if ( v34 )
      {
        if ( v34 == 1 )
          v12 = *(_QWORD *)(v11 + 8) + a4;
        goto LABEL_40;
      }
LABEL_65:
      v12 = a4;
    }
    else
    {
      if ( !*(_BYTE *)v11 )
        goto LABEL_65;
      v12 = *(_QWORD *)(v11 + 144) + a4;
    }
LABEL_40:
    v14 = v39;
    if ( !v39 )
    {
      v14 = a6;
      v39 = a6;
    }
    goto LABEL_42;
  }
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x387,
    (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
    (const char *)0x8000FFFFLL,
    v38);
  if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
    VmlDebugTraceEx(0, &off_1402E4008);
  *(_BYTE *)a2 = 0;
  RrwLockRelease(v8);
  return a2;
}

```

## disassembly

```asm
0x140034478  mov     [rsp+arg_10], rbx
0x14003447d  push    rbp
0x14003447e  push    rsi
0x14003447f  push    rdi
0x140034480  push    r12
0x140034482  push    r13
0x140034484  push    r14
0x140034486  push    r15
0x140034488  sub     rsp, 0A0h
0x14003448f  mov     rax, cs:__security_cookie
0x140034496  xor     rax, rsp
0x140034499  mov     [rsp+0D8h+var_40], rax
0x1400344a1  mov     rdi, r9
0x1400344a4  mov     [rsp+0D8h+var_90], r9
0x1400344a9  mov     [rsp+0D8h+var_88], r8
0x1400344ae  mov     r14, rdx
0x1400344b1  mov     [rsp+0D8h+var_48], rcx
0x1400344b9  mov     rax, [rsp+0D8h+arg_28]
0x1400344c1  mov     [rsp+0D8h+var_80], rax
0x1400344c6  xorps   xmm0, xmm0
0x1400344c9  movups  xmmword ptr [rdx], xmm0
0x1400344cc  movups  xmmword ptr [rdx+10h], xmm0
0x1400344d0  movups  xmmword ptr [rdx+20h], xmm0
0x1400344d4  mov     byte ptr [rdx], 1
0x1400344d7  mov     r15, [rcx+0A0h]
0x1400344de  add     r15, 18h
0x1400344e2  mov     edx, 4
0x1400344e7  xor     eax, eax
0x1400344e9  lock cmpxchg [r15], edx
0x1400344ee  mov     ebx, eax
0x1400344f0  jz      short loc_14003452F
0x1400344f2  test    al, 1
0x1400344f4  jnz     loc_1400347CC
0x1400344fa  test    bl, 1
0x1400344fd  jz      loc_140034773
0x140034503  xor     r8d, r8d
0x140034506  or      edx, 0FFFFFFFFh
0x140034509  mov     rcx, r15
0x14003450c  call    RrwpLockWait
0x140034511  test    eax, eax
0x140034513  jz      loc_1400347EE
0x140034519  prefetchw byte ptr [r15]
0x14003451d  mov     ebx, [r15]
0x140034520  jmp     short loc_1400344FA
0x140034522  mov     edx, 4
0x140034527  mov     rcx, [rsp+0D8h+var_48]
0x14003452f  xor     esi, esi
0x140034531  mov     rbp, rdi
0x140034534  xor     edi, edi
0x140034536  xor     ebx, ebx
0x140034538  mov     [rsp+0D8h+var_98], rbx
0x14003453d  mov     [rsp+0D8h+var_78], r15
0x140034542  mov     al, 1
0x140034544  mov     [rsp+0D8h+var_70], al
0x140034548  lea     r12, [r14+10h]
0x14003454c  lea     r13, [r14+4]
0x140034550  test    al, al
0x140034552  jz      loc_140034620
0x140034558  mov     r13, [rcx+0A0h]
0x14003455f  lea     r12, [r13+18h]
0x140034563  xor     eax, eax
0x140034565  lock cmpxchg [r12], edx
0x14003456b  mov     ebx, eax
0x14003456d  jz      short loc_140034593
0x14003456f  test    al, 1
0x140034571  jnz     loc_14003480E
0x140034577  test    bl, 1
0x14003457a  jnz     loc_1400347A8
0x140034580  mov     edx, ebx
0x140034582  lea     ecx, [rbx+4]
0x140034585  mov     eax, ebx
0x140034587  lock cmpxchg [r12], ecx
0x14003458d  mov     ebx, eax
0x14003458f  cmp     eax, edx
0x140034591  jnz     short loc_140034577
0x140034593  mov     rsi, [r13+0]
0x140034597  cmp     rsi, [r13+8]
0x14003459b  jz      short loc_1400345BC
0x14003459d  mov     rcx, [rsp+0D8h+var_88]
0x1400345a2  mov     rax, [rsi]
0x1400345a5  cmp     [rax+98h], rcx
0x1400345ac  jz      loc_140034832
0x1400345b2  add     rsi, 8
0x1400345b6  cmp     rsi, [r13+8]
0x1400345ba  jnz     short loc_1400345A2
0x1400345bc  xor     esi, esi
0x1400345be  mov     rcx, r12
0x1400345c1  call    RrwLockRelease
0x1400345c6  test    rsi, rsi
0x1400345c9  jz      loc_14003483A
0x1400345cf  test    byte ptr [rsi+0A8h], 8
0x1400345d6  jnz     loc_1400349AA
0x1400345dc  lea     rbx, [rsi+18h]
0x1400345e0  xor     eax, eax
0x1400345e2  lea     ecx, [rax+4]
0x1400345e5  lock cmpxchg [rbx], ecx
0x1400345e9  mov     edi, eax
0x1400345eb  jz      loc_1400346DD
0x1400345f1  test    al, 1
0x1400345f3  jnz     loc_14003489D
0x1400345f9  test    dil, 1
0x1400345fd  jz      loc_14003478E
0x140034603  xor     r8d, r8d
0x140034606  or      edx, 0FFFFFFFFh
0x140034609  mov     rcx, rbx
0x14003460c  call    RrwpLockWait
0x140034611  test    eax, eax
0x140034613  jz      loc_14003498A
0x140034619  prefetchw byte ptr [rbx]
0x14003461c  mov     edi, [rbx]
0x14003461e  jmp     short loc_1400345F9
0x140034620  mov     rcx, r15
0x140034623  call    RrwLockRelease
0x140034628  mov     [r14+20h], rdi
0x14003462c  mov     [r14+28h], rbx
0x140034630  test    rdi, rdi
0x140034633  jz      short loc_1400346AE
0x140034635  mov     [rsp+0D8h+var_48], rbp
0x14003463d  mov     rax, [rdi]
0x140034640  mov     [rsp+0D8h+var_A8], r12
0x140034645  lea     rcx, [rsp+0D8h+var_48]
0x14003464d  mov     [rsp+0D8h+var_B0], rcx
0x140034652  mov     [rsp+0D8h+var_B8], r13
0x140034657  mov     r9, rbx
0x14003465a  mov     r8d, [rsp+0D8h+arg_20]
0x140034662  mov     rdx, rbp
0x140034665  mov     rcx, rdi
0x140034668  mov     rax, [rax]
0x14003466b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034670  cmp     eax, 1
0x140034673  setz    al
0x140034676  mov     [r14], al
0x140034679  cmp     dword ptr [rdi+8], 2
0x14003467d  jz      loc_1400349F3
0x140034683  mov     rbp, [rsp+0D8h+var_48]
0x14003468b  xor     ecx, ecx
0x14003468d  mov     edx, [rdi+8]
0x140034690  test    edx, edx
0x140034692  jz      loc_140034A17
0x140034698  sub     edx, 1
0x14003469b  jz      loc_140034A2A
0x1400346a1  cmp     edx, 1
0x1400346a4  jz      loc_140034A0B
0x1400346aa  mov     [r14+8], rcx
0x1400346ae  mov     rax, r14
0x1400346b1  mov     rcx, [rsp+0D8h+var_40]
0x1400346b9  xor     rcx, rsp; StackCookie
0x1400346bc  call    __security_check_cookie
0x1400346c1  mov     rbx, [rsp+0D8h+arg_10]
0x1400346c9  add     rsp, 0A0h
0x1400346d0  pop     r15
0x1400346d2  pop     r14
0x1400346d4  pop     r13
0x1400346d6  pop     r12
0x1400346d8  pop     rdi
0x1400346d9  pop     rsi
0x1400346da  pop     rbp
0x1400346db  retn
0x1400346dd  mov     r12, [rsi+58h]
0x1400346e1  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1400346e5  setz    r13b
0x1400346e9  jz      loc_1400348BD
0x1400346ef  mov     rdi, r12
0x1400346f2  mov     rax, [rsi+60h]
0x1400346f6  mov     [rsp+0D8h+var_98], rax
0x1400346fb  mov     rcx, rbx
0x1400346fe  call    RrwLockRelease
0x140034703  mov     [r14+18h], r13b
0x140034707  lea     r13, [r14+4]
0x14003470b  test    rdi, rdi
0x14003470e  jz      loc_140034920
0x140034714  mov     dword ptr [r13+0], 0
0x14003471c  lea     r12, [r14+10h]
0x140034720  mov     qword ptr [r12], 1
0x140034728  xor     ebp, ebp
0x14003472a  mov     ecx, [rdi+8]
0x14003472d  test    ecx, ecx
0x14003472f  jz      loc_140034900
0x140034735  sub     ecx, 1
0x140034738  jz      loc_140034916
0x14003473e  cmp     ecx, 1
0x140034741  jz      loc_1400348F2
0x140034747  mov     rbx, [rsp+0D8h+var_98]
0x14003474c  test    rbx, rbx
0x14003474f  jnz     short loc_14003475B
0x140034751  mov     rbx, [rsp+0D8h+var_80]
0x140034756  mov     [rsp+0D8h+var_98], rbx
0x14003475b  xor     al, al
0x14003475d  mov     [rsp+0D8h+var_70], al
0x140034761  mov     rcx, [rsp+0D8h+var_48]
0x140034769  mov     edx, 4
0x14003476e  jmp     loc_140034550
0x140034773  mov     edx, ebx
0x140034775  lea     ecx, [rbx+4]
0x140034778  mov     eax, ebx
0x14003477a  lock cmpxchg [r15], ecx
0x14003477f  mov     ebx, eax
0x140034781  cmp     eax, edx
0x140034783  jnz     loc_1400344FA
0x140034789  jmp     loc_140034522
0x14003478e  mov     edx, edi
0x140034790  lea     ecx, [rdi+4]
0x140034793  mov     eax, edi
0x140034795  lock cmpxchg [rbx], ecx
0x140034799  mov     edi, eax
0x14003479b  cmp     eax, edx
0x14003479d  jnz     loc_1400345F9
0x1400347a3  jmp     loc_1400346DD
0x1400347a8  xor     r8d, r8d
0x1400347ab  or      edx, 0FFFFFFFFh
0x1400347ae  mov     rcx, r12
0x1400347b1  call    RrwpLockWait
0x1400347b6  test    eax, eax
0x1400347b8  jz      loc_14003496A
0x1400347be  prefetchw byte ptr [r12]
0x1400347c3  mov     ebx, [r12]
0x1400347c7  jmp     loc_140034577
0x1400347cc  call    cs:__imp_GetCurrentThreadId
0x1400347d3  nop     dword ptr [rax+rax+00h]
0x1400347d8  mov     ecx, [r15+4]
0x1400347dc  cmp     ecx, eax
0x1400347de  jnz     loc_1400344FA
0x1400347e4  lock inc dword ptr [r15+8]
0x1400347e9  jmp     loc_140034522
0x1400347ee  mov     rcx, [rsp+0D8h]; this
0x1400347f6  mov     r9d, 102h; char *
0x1400347fc  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x140034803  mov     edx, 249h; void *
0x140034808  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14003480e  call    cs:__imp_GetCurrentThreadId
0x140034815  nop     dword ptr [rax+rax+00h]
0x14003481a  mov     ecx, [r12+4]
0x14003481f  cmp     ecx, eax
0x140034821  jnz     loc_140034577
0x140034827  lock inc dword ptr [r12+8]
0x14003482d  jmp     loc_140034593
0x140034832  mov     rsi, rax
0x140034835  jmp     loc_1400345BE
0x14003483a  mov     rax, [rsp+0D8h+var_90]
0x14003483f  mov     [r14+8], rax
0x140034843  lea     r13, [r14+4]
0x140034847  mov     dword ptr [r13+0], 3
0x14003484f  lea     r12, [r14+10h]
0x140034853  mov     qword ptr [r12], 1
0x14003485b  mov     rcx, [rsp+0D8h]; this
0x140034863  mov     r9d, 8000FFFFh; char *
0x140034869  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x140034870  mov     edx, 381h; void *
0x140034875  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14003487a  xor     ecx, ecx
0x14003487c  call    VmlIsDebugTraceEnabled
0x140034881  test    eax, eax
0x140034883  jz      short loc_140034893
0x140034885  lea     rdx, off_1402E4060; "Unexpected error.\n"
0x14003488c  xor     ecx, ecx
0x14003488e  call    VmlDebugTraceEx
0x140034893  mov     rbx, [rsp+0D8h+var_98]
0x140034898  jmp     loc_14003475B
0x14003489d  call    cs:__imp_GetCurrentThreadId
0x1400348a4  nop     dword ptr [rax+rax+00h]
0x1400348a9  mov     ecx, [rbx+4]
0x1400348ac  cmp     ecx, eax
0x1400348ae  jnz     loc_1400345F9
0x1400348b4  lock inc dword ptr [rbx+8]
0x1400348b8  jmp     loc_1400346DD
0x1400348bd  lea     rcx, [rsi+48h]
0x1400348c1  mov     r8, [rsp+0D8h+var_90]
0x1400348c6  lea     rdx, [rsp+0D8h+var_68]
0x1400348cb  call    ?Find@?$IntervalTree@UMemoryNotification@@@@QEBA?AV?$optional@UMemoryNotification@@@std@@_K@Z; IntervalTree<MemoryNotification>::Find(unsigned __int64)
0x1400348d0  cmp     [rsp+0D8h+var_50], 0
0x1400348d8  jz      short loc_1400348E9
0x1400348da  mov     rdi, [rsp+0D8h+var_68]
0x1400348df  mov     rax, [rsp+0D8h+var_60]
0x1400348e4  jmp     loc_1400346F6
0x1400348e9  xor     edi, edi
0x1400348eb  xor     eax, eax
0x1400348ed  jmp     loc_1400346F6
0x1400348f2  mov     rbp, [rsp+0D8h+var_90]
0x1400348f7  add     rbp, [rsi+8]
0x1400348fb  jmp     loc_140034747
0x140034900  cmp     [rsi], bpl
0x140034903  jz      short loc_140034916
0x140034905  mov     rbp, [rsp+0D8h+var_90]
0x14003490a  add     rbp, [rsi+90h]
0x140034911  jmp     loc_140034747
0x140034916  mov     rbp, [rsp+0D8h+var_90]
0x14003491b  jmp     loc_140034747
0x140034920  mov     rbx, [rsp+0D8h+var_98]
0x140034925  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140034929  lea     r12, [r14+10h]
0x14003492d  jnz     short loc_14003494D
0x14003492f  mov     dword ptr [r13+0], 3
0x140034937  mov     rax, [rsp+0D8h+var_90]
0x14003493c  mov     [r14+8], rax
0x140034940  mov     qword ptr [r12], 1
0x140034948  jmp     loc_14003475B
0x14003494d  mov     dword ptr [r13+0], 0
0x140034955  mov     qword ptr [r14+8], 0
0x14003495d  mov     rax, [rsi+78h]
0x140034961  mov     [r12], rax
  ... truncated ...
```
