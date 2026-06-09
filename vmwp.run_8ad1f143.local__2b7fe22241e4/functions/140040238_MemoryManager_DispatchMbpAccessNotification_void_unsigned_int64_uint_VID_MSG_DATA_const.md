# MemoryManager::DispatchMbpAccessNotification(void *,unsigned __int64,uint,_VID_MSG_DATA * const)

- ea: `0x140040238`
- end: `0x1400407f2`
- name: `?DispatchMbpAccessNotification@MemoryManager@@QEAA?AUDispatchMemoryNotificationResult@@PEAX_KIQEAU_VID_MSG_DATA@@@Z`
- size: `1466`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140212250`

## callees

- `0x140040238`
- `0x140040ff8`
- `0x140041a5c`
- `0x140042260`
- `0x14005497c`
- `0x140078cb8`
- `0x14009d7cc`
- `0x140132960`
- `0x1402138dc`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004058c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400405ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004065d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004058c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400405ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004065d`

## string_xrefs

- `0x1400405bc`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140040738`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140040758`: `onecore\vm\common\vml\VmReaderWriterLock.h`

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
      VmlDebugTraceEx(0, &off_1402DAC50);
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
    VmlDebugTraceEx(0, &off_1402DABF8);
  *(_BYTE *)a2 = 0;
  RrwLockRelease(v8);
  return a2;
}

```

## disassembly

```asm
0x140040238  mov     [rsp+arg_10], rbx
0x14004023d  push    rbp
0x14004023e  push    rsi
0x14004023f  push    rdi
0x140040240  push    r12
0x140040242  push    r13
0x140040244  push    r14
0x140040246  push    r15
0x140040248  sub     rsp, 0A0h
0x14004024f  mov     rax, cs:__security_cookie
0x140040256  xor     rax, rsp
0x140040259  mov     [rsp+0D8h+var_40], rax
0x140040261  mov     rdi, r9
0x140040264  mov     [rsp+0D8h+var_90], r9
0x140040269  mov     [rsp+0D8h+var_88], r8
0x14004026e  mov     r14, rdx
0x140040271  mov     [rsp+0D8h+var_48], rcx
0x140040279  mov     rax, [rsp+0D8h+arg_28]
0x140040281  mov     [rsp+0D8h+var_80], rax
0x140040286  xorps   xmm0, xmm0
0x140040289  movups  xmmword ptr [rdx], xmm0
0x14004028c  movups  xmmword ptr [rdx+10h], xmm0
0x140040290  movups  xmmword ptr [rdx+20h], xmm0
0x140040294  mov     byte ptr [rdx], 1
0x140040297  mov     r15, [rcx+0A0h]
0x14004029e  add     r15, 18h
0x1400402a2  mov     edx, 4
0x1400402a7  xor     eax, eax
0x1400402a9  lock cmpxchg [r15], edx
0x1400402ae  mov     ebx, eax
0x1400402b0  jz      short loc_1400402EF
0x1400402b2  test    al, 1
0x1400402b4  jnz     loc_14004058C
0x1400402ba  test    bl, 1
0x1400402bd  jz      loc_140040533
0x1400402c3  xor     r8d, r8d
0x1400402c6  or      edx, 0FFFFFFFFh
0x1400402c9  mov     rcx, r15
0x1400402cc  call    RrwpLockWait
0x1400402d1  test    eax, eax
0x1400402d3  jz      loc_1400405AE
0x1400402d9  prefetchw byte ptr [r15]
0x1400402dd  mov     ebx, [r15]
0x1400402e0  jmp     short loc_1400402BA
0x1400402e2  mov     edx, 4
0x1400402e7  mov     rcx, [rsp+0D8h+var_48]
0x1400402ef  xor     esi, esi
0x1400402f1  mov     rbp, rdi
0x1400402f4  xor     edi, edi
0x1400402f6  xor     ebx, ebx
0x1400402f8  mov     [rsp+0D8h+var_98], rbx
0x1400402fd  mov     [rsp+0D8h+var_78], r15
0x140040302  mov     al, 1
0x140040304  mov     [rsp+0D8h+var_70], al
0x140040308  lea     r12, [r14+10h]
0x14004030c  lea     r13, [r14+4]
0x140040310  test    al, al
0x140040312  jz      loc_1400403E0
0x140040318  mov     r13, [rcx+0A0h]
0x14004031f  lea     r12, [r13+18h]
0x140040323  xor     eax, eax
0x140040325  lock cmpxchg [r12], edx
0x14004032b  mov     ebx, eax
0x14004032d  jz      short loc_140040353
0x14004032f  test    al, 1
0x140040331  jnz     loc_1400405CE
0x140040337  test    bl, 1
0x14004033a  jnz     loc_140040568
0x140040340  mov     edx, ebx
0x140040342  lea     ecx, [rbx+4]
0x140040345  mov     eax, ebx
0x140040347  lock cmpxchg [r12], ecx
0x14004034d  mov     ebx, eax
0x14004034f  cmp     eax, edx
0x140040351  jnz     short loc_140040337
0x140040353  mov     rsi, [r13+0]
0x140040357  cmp     rsi, [r13+8]
0x14004035b  jz      short loc_14004037C
0x14004035d  mov     rcx, [rsp+0D8h+var_88]
0x140040362  mov     rax, [rsi]
0x140040365  cmp     [rax+98h], rcx
0x14004036c  jz      loc_1400405F2
0x140040372  add     rsi, 8
0x140040376  cmp     rsi, [r13+8]
0x14004037a  jnz     short loc_140040362
0x14004037c  xor     esi, esi
0x14004037e  mov     rcx, r12
0x140040381  call    RrwLockRelease
0x140040386  test    rsi, rsi
0x140040389  jz      loc_1400405FA
0x14004038f  test    byte ptr [rsi+0A8h], 8
0x140040396  jnz     loc_14004076A
0x14004039c  lea     rbx, [rsi+18h]
0x1400403a0  xor     eax, eax
0x1400403a2  lea     ecx, [rax+4]
0x1400403a5  lock cmpxchg [rbx], ecx
0x1400403a9  mov     edi, eax
0x1400403ab  jz      loc_14004049D
0x1400403b1  test    al, 1
0x1400403b3  jnz     loc_14004065D
0x1400403b9  test    dil, 1
0x1400403bd  jz      loc_14004054E
0x1400403c3  xor     r8d, r8d
0x1400403c6  or      edx, 0FFFFFFFFh
0x1400403c9  mov     rcx, rbx
0x1400403cc  call    RrwpLockWait
0x1400403d1  test    eax, eax
0x1400403d3  jz      loc_14004074A
0x1400403d9  prefetchw byte ptr [rbx]
0x1400403dc  mov     edi, [rbx]
0x1400403de  jmp     short loc_1400403B9
0x1400403e0  mov     rcx, r15
0x1400403e3  call    RrwLockRelease
0x1400403e8  mov     [r14+20h], rdi
0x1400403ec  mov     [r14+28h], rbx
0x1400403f0  test    rdi, rdi
0x1400403f3  jz      short loc_14004046E
0x1400403f5  mov     [rsp+0D8h+var_48], rbp
0x1400403fd  mov     rax, [rdi]
0x140040400  mov     [rsp+0D8h+var_A8], r12
0x140040405  lea     rcx, [rsp+0D8h+var_48]
0x14004040d  mov     [rsp+0D8h+var_B0], rcx
0x140040412  mov     [rsp+0D8h+var_B8], r13
0x140040417  mov     r9, rbx
0x14004041a  mov     r8d, [rsp+0D8h+arg_20]
0x140040422  mov     rdx, rbp
0x140040425  mov     rcx, rdi
0x140040428  mov     rax, [rax]
0x14004042b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040430  cmp     eax, 1
0x140040433  setz    al
0x140040436  mov     [r14], al
0x140040439  cmp     dword ptr [rdi+8], 2
0x14004043d  jz      loc_1400407B3
0x140040443  mov     rbp, [rsp+0D8h+var_48]
0x14004044b  xor     ecx, ecx
0x14004044d  mov     edx, [rdi+8]
0x140040450  test    edx, edx
0x140040452  jz      loc_1400407D7
0x140040458  sub     edx, 1
0x14004045b  jz      loc_1400407EA
0x140040461  cmp     edx, 1
0x140040464  jz      loc_1400407CB
0x14004046a  mov     [r14+8], rcx
0x14004046e  mov     rax, r14
0x140040471  mov     rcx, [rsp+0D8h+var_40]
0x140040479  xor     rcx, rsp; StackCookie
0x14004047c  call    __security_check_cookie
0x140040481  mov     rbx, [rsp+0D8h+arg_10]
0x140040489  add     rsp, 0A0h
0x140040490  pop     r15
0x140040492  pop     r14
0x140040494  pop     r13
0x140040496  pop     r12
0x140040498  pop     rdi
0x140040499  pop     rsi
0x14004049a  pop     rbp
0x14004049b  retn
0x14004049d  mov     r12, [rsi+58h]
0x1400404a1  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1400404a5  setz    r13b
0x1400404a9  jz      loc_14004067D
0x1400404af  mov     rdi, r12
0x1400404b2  mov     rax, [rsi+60h]
0x1400404b6  mov     [rsp+0D8h+var_98], rax
0x1400404bb  mov     rcx, rbx
0x1400404be  call    RrwLockRelease
0x1400404c3  mov     [r14+18h], r13b
0x1400404c7  lea     r13, [r14+4]
0x1400404cb  test    rdi, rdi
0x1400404ce  jz      loc_1400406E0
0x1400404d4  mov     dword ptr [r13+0], 0
0x1400404dc  lea     r12, [r14+10h]
0x1400404e0  mov     qword ptr [r12], 1
0x1400404e8  xor     ebp, ebp
0x1400404ea  mov     ecx, [rdi+8]
0x1400404ed  test    ecx, ecx
0x1400404ef  jz      loc_1400406C0
0x1400404f5  sub     ecx, 1
0x1400404f8  jz      loc_1400406D6
0x1400404fe  cmp     ecx, 1
0x140040501  jz      loc_1400406B2
0x140040507  mov     rbx, [rsp+0D8h+var_98]
0x14004050c  test    rbx, rbx
0x14004050f  jnz     short loc_14004051B
0x140040511  mov     rbx, [rsp+0D8h+var_80]
0x140040516  mov     [rsp+0D8h+var_98], rbx
0x14004051b  xor     al, al
0x14004051d  mov     [rsp+0D8h+var_70], al
0x140040521  mov     rcx, [rsp+0D8h+var_48]
0x140040529  mov     edx, 4
0x14004052e  jmp     loc_140040310
0x140040533  mov     edx, ebx
0x140040535  lea     ecx, [rbx+4]
0x140040538  mov     eax, ebx
0x14004053a  lock cmpxchg [r15], ecx
0x14004053f  mov     ebx, eax
0x140040541  cmp     eax, edx
0x140040543  jnz     loc_1400402BA
0x140040549  jmp     loc_1400402E2
0x14004054e  mov     edx, edi
0x140040550  lea     ecx, [rdi+4]
0x140040553  mov     eax, edi
0x140040555  lock cmpxchg [rbx], ecx
0x140040559  mov     edi, eax
0x14004055b  cmp     eax, edx
0x14004055d  jnz     loc_1400403B9
0x140040563  jmp     loc_14004049D
0x140040568  xor     r8d, r8d
0x14004056b  or      edx, 0FFFFFFFFh
0x14004056e  mov     rcx, r12
0x140040571  call    RrwpLockWait
0x140040576  test    eax, eax
0x140040578  jz      loc_14004072A
0x14004057e  prefetchw byte ptr [r12]
0x140040583  mov     ebx, [r12]
0x140040587  jmp     loc_140040337
0x14004058c  call    cs:__imp_GetCurrentThreadId
0x140040593  nop     dword ptr [rax+rax+00h]
0x140040598  mov     ecx, [r15+4]
0x14004059c  cmp     ecx, eax
0x14004059e  jnz     loc_1400402BA
0x1400405a4  lock inc dword ptr [r15+8]
0x1400405a9  jmp     loc_1400402E2
0x1400405ae  mov     rcx, [rsp+0D8h]; this
0x1400405b6  mov     r9d, 102h; char *
0x1400405bc  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400405c3  mov     edx, 249h; void *
0x1400405c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400405ce  call    cs:__imp_GetCurrentThreadId
0x1400405d5  nop     dword ptr [rax+rax+00h]
0x1400405da  mov     ecx, [r12+4]
0x1400405df  cmp     ecx, eax
0x1400405e1  jnz     loc_140040337
0x1400405e7  lock inc dword ptr [r12+8]
0x1400405ed  jmp     loc_140040353
0x1400405f2  mov     rsi, rax
0x1400405f5  jmp     loc_14004037E
0x1400405fa  mov     rax, [rsp+0D8h+var_90]
0x1400405ff  mov     [r14+8], rax
0x140040603  lea     r13, [r14+4]
0x140040607  mov     dword ptr [r13+0], 3
0x14004060f  lea     r12, [r14+10h]
0x140040613  mov     qword ptr [r12], 1
0x14004061b  mov     rcx, [rsp+0D8h]; this
0x140040623  mov     r9d, 8000FFFFh; char *
0x140040629  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x140040630  mov     edx, 381h; void *
0x140040635  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14004063a  xor     ecx, ecx
0x14004063c  call    VmlIsDebugTraceEnabled
0x140040641  test    eax, eax
0x140040643  jz      short loc_140040653
0x140040645  lea     rdx, off_1402DAC50; "Unexpected error.\n"
0x14004064c  xor     ecx, ecx
0x14004064e  call    VmlDebugTraceEx
0x140040653  mov     rbx, [rsp+0D8h+var_98]
0x140040658  jmp     loc_14004051B
0x14004065d  call    cs:__imp_GetCurrentThreadId
0x140040664  nop     dword ptr [rax+rax+00h]
0x140040669  mov     ecx, [rbx+4]
0x14004066c  cmp     ecx, eax
0x14004066e  jnz     loc_1400403B9
0x140040674  lock inc dword ptr [rbx+8]
0x140040678  jmp     loc_14004049D
0x14004067d  lea     rcx, [rsi+48h]
0x140040681  mov     r8, [rsp+0D8h+var_90]
0x140040686  lea     rdx, [rsp+0D8h+var_68]
0x14004068b  call    ?Find@?$IntervalTree@UMemoryNotification@@@@QEBA?AV?$optional@UMemoryNotification@@@std@@_K@Z; IntervalTree<MemoryNotification>::Find(unsigned __int64)
0x140040690  cmp     [rsp+0D8h+var_50], 0
0x140040698  jz      short loc_1400406A9
0x14004069a  mov     rdi, [rsp+0D8h+var_68]
0x14004069f  mov     rax, [rsp+0D8h+var_60]
0x1400406a4  jmp     loc_1400404B6
0x1400406a9  xor     edi, edi
0x1400406ab  xor     eax, eax
0x1400406ad  jmp     loc_1400404B6
0x1400406b2  mov     rbp, [rsp+0D8h+var_90]
0x1400406b7  add     rbp, [rsi+8]
0x1400406bb  jmp     loc_140040507
0x1400406c0  cmp     [rsi], bpl
0x1400406c3  jz      short loc_1400406D6
0x1400406c5  mov     rbp, [rsp+0D8h+var_90]
0x1400406ca  add     rbp, [rsi+90h]
0x1400406d1  jmp     loc_140040507
0x1400406d6  mov     rbp, [rsp+0D8h+var_90]
0x1400406db  jmp     loc_140040507
0x1400406e0  mov     rbx, [rsp+0D8h+var_98]
0x1400406e5  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1400406e9  lea     r12, [r14+10h]
0x1400406ed  jnz     short loc_14004070D
0x1400406ef  mov     dword ptr [r13+0], 3
0x1400406f7  mov     rax, [rsp+0D8h+var_90]
0x1400406fc  mov     [r14+8], rax
0x140040700  mov     qword ptr [r12], 1
0x140040708  jmp     loc_14004051B
0x14004070d  mov     dword ptr [r13+0], 0
0x140040715  mov     qword ptr [r14+8], 0
0x14004071d  mov     rax, [rsi+78h]
0x140040721  mov     [r12], rax
  ... truncated ...
```
