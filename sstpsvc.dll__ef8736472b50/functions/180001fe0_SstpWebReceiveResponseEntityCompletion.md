# SstpWebReceiveResponseEntityCompletion

- ea: `0x180001fe0`
- end: `0x180002319`
- name: `SstpWebReceiveResponseEntityCompletion`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180002f80`
- `0x1800071cc`
- `0x180007f48`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`
- `0x18001d2a0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002122`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002122`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000204d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000204d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000206d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000206d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000210f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000210f`

## pseudocode

```c
__int64 __fastcall SstpWebReceiveResponseEntityCompletion(__int64 a1, unsigned int a2, int a3)
{
  __int64 v3; // rdi
  RTL_SRWLOCK *v7; // rcx
  int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 result; // rax
  _QWORD *v13; // rsi
  char *v14; // rbx
  __int64 v15; // rax
  int v16; // [rsp+20h] [rbp-1028h] BYREF
  _BYTE v17[2044]; // [rsp+24h] [rbp-1024h] BYREF
  int v18; // [rsp+820h] [rbp-828h] BYREF
  _BYTE v19[2044]; // [rsp+824h] [rbp-824h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( a2 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"CoId=%hs:ReceiveResponseEntity fails with %d", v3 + 552, a2);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
    }
    v13 = (_QWORD *)(a1 - 24);
    v14 = (char *)SstpSvcGlobals + 424;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
    if ( (_QWORD *)*v13 == v13 )
    {
      v15 = *((_QWORD *)v14 + 5);
      *v13 = v15;
      v13[1] = v14 + 40;
      *(_QWORD *)(v15 + 8) = v13;
      *((_QWORD *)v14 + 5) = v13;
      ++*(_DWORD *)(v13[2] + 28LL);
      if ( ++*((_DWORD *)v14 + 5) >= *((_DWORD *)v14 + 4) )
      {
        FreeUnusedBufferPoolBlocks(v14);
        *((_DWORD *)v14 + 5) = 0;
      }
    }
    else
    {
      ++g_ulDoubleBufferFrees;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 64));
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 288));
    InitiateCallContextCleanup(v3, 1u);
  }
  else
  {
    v7 = (RTL_SRWLOCK *)SstpSvcGlobals;
    *(_DWORD *)(a1 + 92) = a3;
    *(_DWORD *)(a1 + 88) = *(_DWORD *)(v3 + 240);
    AcquireSRWLockShared(v7 + 96);
    v8 = *((_DWORD *)SstpSvcGlobals + 194);
    ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
    if ( (v8 & 1) != 0 && v3 && *(_QWORD *)(v3 + 624) )
    {
      ProxySendToRelatedCtx((LPOVERLAPPED)a1);
    }
    else
    {
      v18 = 0;
      memset_0(v19, 0, sizeof(v19));
      v9 = *(_QWORD *)(a1 + 56);
      *(_QWORD *)(a1 + 56) = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 288));
      if ( *(_BYTE *)(v9 + 435) )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          LOWORD(v18) = 0;
          FormatRRASErrorString(&v18, L"CoId=%hs:Dropping packet since disconnect in progress", v9 + 552);
          if ( (byte_18002E903 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v18);
        }
        LOBYTE(v10) = 1;
        FreeBufferToPool((char *)SstpSvcGlobals + 424, a1, v10);
      }
      else
      {
        *(_QWORD *)(a1 + 48) = a1 + 40;
        *(_QWORD *)(a1 + 40) = a1 + 40;
        v11 = *(_QWORD **)(v9 + 424);
        *(_QWORD *)(a1 + 40) = v9 + 416;
        *(_QWORD *)(a1 + 48) = v11;
        *v11 = a1 + 40;
        *(_QWORD *)(v9 + 424) = a1 + 40;
        if ( !*(_BYTE *)(v9 + 432) )
        {
          *(_BYTE *)(v9 + 432) = 1;
          _InterlockedIncrement((volatile signed __int32 *)(v9 + 208));
          SubmitThreadpoolWork(*(PTP_WORK *)(v9 + 336));
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 288));
    }
    PostReceiveOnCall(v3);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 208), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (**)(void))(v3 + 216))();
  return result;
}

```

## disassembly

```asm
0x180001fe0  mov     [rsp+arg_10], rbx
0x180001fe5  push    rbp
0x180001fe6  push    rsi
0x180001fe7  push    rdi
0x180001fe8  mov     eax, 1030h
0x180001fed  call    _alloca_probe
0x180001ff2  sub     rsp, rax
0x180001ff5  mov     rax, cs:__security_cookie
0x180001ffc  xor     rax, rsp
0x180001fff  mov     [rsp+1048h+var_28], rax
0x180002007  mov     rdi, [rcx+38h]
0x18000200b  mov     rbp, r8
0x18000200e  mov     ebx, edx
0x180002010  mov     rsi, rcx
0x180002013  xor     eax, eax
0x180002015  lea     rcx, [rsp+1048h+var_1024]; void *
0x18000201a  xor     edx, edx; Val
0x18000201c  mov     [rsp+1048h+var_1028], eax
0x180002020  mov     r8d, 7FCh; Size
0x180002026  call    memset_0
0x18000202b  test    ebx, ebx
0x18000202d  jnz     loc_180002173
0x180002033  mov     rcx, cs:SstpSvcGlobals
0x18000203a  mov     [rsi+5Ch], ebp
0x18000203d  add     rcx, 300h; SRWLock
0x180002044  mov     eax, [rdi+0F0h]
0x18000204a  mov     [rsi+58h], eax
0x18000204d  call    cs:__imp_AcquireSRWLockShared
0x180002054  nop     dword ptr [rax+rax+00h]
0x180002059  mov     rcx, cs:SstpSvcGlobals
0x180002060  mov     ebx, [rcx+308h]
0x180002066  add     rcx, 300h; SRWLock
0x18000206d  call    cs:__imp_ReleaseSRWLockShared
0x180002074  nop     dword ptr [rax+rax+00h]
0x180002079  bt      ebx, 0
0x18000207d  jb      loc_180002277
0x180002083  xor     eax, eax
0x180002085  lea     rcx, [rsp+1048h+var_824]; void *
0x18000208d  xor     edx, edx; Val
0x18000208f  mov     [rsp+1048h+var_828], eax
0x180002096  mov     r8d, 7FCh; Size
0x18000209c  call    memset_0
0x1800020a1  mov     rbx, [rsi+38h]
0x1800020a5  mov     qword ptr [rsi+38h], 0
0x1800020ad  lea     rcx, [rbx+120h]; lpCriticalSection
0x1800020b4  call    cs:__imp_EnterCriticalSection
0x1800020bb  nop     dword ptr [rax+rax+00h]
0x1800020c0  cmp     byte ptr [rbx+1B3h], 0
0x1800020c7  jnz     loc_18000229B
0x1800020cd  lea     r8, [rsi+28h]
0x1800020d1  mov     [rsi+30h], r8
0x1800020d5  lea     rdx, [rbx+1A0h]
0x1800020dc  mov     [r8], r8
0x1800020df  mov     rax, [rdx+8]
0x1800020e3  mov     [r8], rdx
0x1800020e6  mov     [rsi+30h], rax
0x1800020ea  mov     [rax], r8
0x1800020ed  mov     [rdx+8], r8
0x1800020f1  cmp     byte ptr [rbx+1B0h], 0
0x1800020f8  jnz     short loc_18000211B
0x1800020fa  mov     byte ptr [rbx+1B0h], 1
0x180002101  lock inc dword ptr [rbx+0D0h]
0x180002108  mov     rcx, [rbx+150h]; pwk
0x18000210f  call    cs:__imp_SubmitThreadpoolWork
0x180002116  nop     dword ptr [rax+rax+00h]
0x18000211b  lea     rcx, [rbx+120h]; lpCriticalSection
0x180002122  call    cs:__imp_LeaveCriticalSection
0x180002129  nop     dword ptr [rax+rax+00h]
0x18000212e  mov     rcx, rdi
0x180002131  call    PostReceiveOnCall
0x180002136  lea     rcx, [rdi+0D0h]
0x18000213d  mov     eax, 0FFFFFFFFh
0x180002142  lock xadd [rcx], eax
0x180002146  cmp     eax, 1
0x180002149  jz      loc_18000230B
0x18000214f  mov     rcx, [rsp+1048h+var_28]
0x180002157  xor     rcx, rsp; StackCookie
0x18000215a  call    __security_check_cookie
0x18000215f  mov     rbx, [rsp+1048h+arg_10]
0x180002167  add     rsp, 1030h
0x18000216e  pop     rdi
0x18000216f  pop     rsi
0x180002170  pop     rbp
0x180002171  retn
0x180002173  test    cs:byte_18002E903, 8
0x18000217a  jnz     loc_18000220C
0x180002180  mov     rbx, cs:SstpSvcGlobals
0x180002187  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18000218b  add     rbx, 1A8h
0x180002192  lea     rcx, [rbx+40h]; lpCriticalSection
0x180002196  call    cs:__imp_EnterCriticalSection
0x18000219d  nop     dword ptr [rax+rax+00h]
0x1800021a2  cmp     [rsi], rsi
0x1800021a5  jnz     loc_180002258
0x1800021ab  mov     rax, [rbx+28h]
0x1800021af  lea     rcx, [rbx+28h]
0x1800021b3  mov     [rsi], rax
0x1800021b6  mov     [rsi+8], rcx
0x1800021ba  mov     [rax+8], rsi
0x1800021be  mov     [rcx], rsi
0x1800021c1  mov     rax, [rsi+10h]
0x1800021c5  inc     dword ptr [rax+1Ch]
0x1800021c8  inc     dword ptr [rbx+14h]
0x1800021cb  mov     eax, [rbx+14h]
0x1800021ce  cmp     eax, [rbx+10h]
0x1800021d1  jnb     loc_180002263
0x1800021d7  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800021db  call    cs:__imp_LeaveCriticalSection
0x1800021e2  nop     dword ptr [rax+rax+00h]
0x1800021e7  lea     rcx, [rdi+120h]; lpCriticalSection
0x1800021ee  call    cs:__imp_EnterCriticalSection
0x1800021f5  nop     dword ptr [rax+rax+00h]
0x1800021fa  mov     edx, 1
0x1800021ff  mov     rcx, rdi
0x180002202  call    InitiateCallContextCleanup
0x180002207  jmp     loc_180002136
0x18000220c  xor     eax, eax
0x18000220e  lea     r8, [rdi+228h]
0x180002215  mov     r9d, ebx
0x180002218  mov     word ptr [rsp+1048h+var_1028], ax
0x18000221d  lea     rdx, aCoidHsReceiver; "CoId=%hs:ReceiveResponseEntity fails wi"...
0x180002224  lea     rcx, [rsp+1048h+var_1028]
0x180002229  call    FormatRRASErrorString
0x18000222e  test    cs:byte_18002E903, 8
0x180002235  jz      loc_180002180
0x18000223b  lea     r8, [rsp+1048h+var_1028]
0x180002240  lea     rdx, RasSSTPSvcTraceError
0x180002247  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000224e  call    McTemplateU0z_EventWriteTransfer
0x180002253  jmp     loc_180002180
0x180002258  inc     cs:g_ulDoubleBufferFrees
0x18000225e  jmp     loc_1800021D7
0x180002263  mov     rcx, rbx
0x180002266  call    FreeUnusedBufferPoolBlocks
0x18000226b  mov     dword ptr [rbx+14h], 0
0x180002272  jmp     loc_1800021D7
0x180002277  test    rdi, rdi
0x18000227a  jz      loc_180002083
0x180002280  cmp     qword ptr [rdi+270h], 0
0x180002288  jz      loc_180002083
0x18000228e  mov     rcx, rsi; Overlapped
0x180002291  call    ProxySendToRelatedCtx
0x180002296  jmp     loc_18000212E
0x18000229b  test    cs:byte_18002E903, 8
0x1800022a2  jz      short loc_1800022ED
0x1800022a4  xor     eax, eax
0x1800022a6  lea     r8, [rbx+228h]
0x1800022ad  lea     rdx, aCoidHsDropping; "CoId=%hs:Dropping packet since disconne"...
0x1800022b4  mov     word ptr [rsp+1048h+var_828], ax
0x1800022bc  lea     rcx, [rsp+1048h+var_828]
0x1800022c4  call    FormatRRASErrorString
0x1800022c9  test    cs:byte_18002E903, 8
0x1800022d0  jz      short loc_1800022ED
0x1800022d2  lea     r8, [rsp+1048h+var_828]
0x1800022da  lea     rdx, RasSSTPSvcTraceError
0x1800022e1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800022e8  call    McTemplateU0z_EventWriteTransfer
0x1800022ed  mov     rcx, cs:SstpSvcGlobals
0x1800022f4  mov     r8b, 1
0x1800022f7  add     rcx, 1A8h
0x1800022fe  mov     rdx, rsi
0x180002301  call    FreeBufferToPool
0x180002306  jmp     loc_18000211B
0x18000230b  mov     rax, [rcx+8]
0x18000230f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002314  jmp     loc_18000214F
```
