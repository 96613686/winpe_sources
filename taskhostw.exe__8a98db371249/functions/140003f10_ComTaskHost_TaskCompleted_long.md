# ComTaskHost::TaskCompleted(long)

- ea: `0x140003f10`
- end: `0x140004223`
- name: `?TaskCompleted@ComTaskHost@@UEAAJJ@Z`
- size: `787`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003f10`
- `0x140009370`
- `0x140009b24`
- `0x140009be0`
- `0x140009c30`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003fc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003fc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004036`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400040f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004036`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400040f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003f9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003f9c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400040dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400040dd`
- `RPCRT4!NdrClientCall3` at `0x14000400c`
- `RPCRT4!NdrClientCall3` at `0x14000400c`

## pseudocode

```c
__int64 __fastcall ComTaskHost::TaskCompleted(ComTaskHost *this, int a2)
{
  int v4; // ebx
  __int64 v5; // r8
  int Pointer; // eax
  signed int v7; // ebx
  int v8; // edx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // ebp
  volatile unsigned int v13; // ecx
  __int32 v14; // [rsp+90h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids, this, a2);
  v14 = 0;
  _InterlockedExchange(&v14, 0);
  _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
  _InterlockedExchange(&v14, _InterlockedCompareExchange(&dword_1400159E4, 0, 0) != 0);
  if ( _InterlockedCompareExchange(&v14, 0, 0) )
  {
    if ( a2 == -2147009395 )
    {
      v11 = -2147024809;
      goto LABEL_18;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    *((_DWORD *)this + 22) = 1;
    *((_DWORD *)this + 23) = a2;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 5, 1) == 1 )
    {
      v4 = *((_DWORD *)this + 17);
      if ( GetCurrentThreadId() == g_dwMainThreadId )
      {
        v7 = 0;
        v13 = 0;
        if ( a2 < 0 )
          v13 = (unsigned __int16)a2;
        g_dwLastTaskResult = v13;
        g_ucLastTaskFlags |= 1u;
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                  3u,
                                  0,
                                  g_hStatusContext,
                                  this,
                                  (char *)this + 24,
                                  1,
                                  a2,
                                  v4).Pointer;
        v7 = Pointer;
        if ( Pointer > 0 )
          v7 = (unsigned __int16)Pointer | 0x80070000;
      }
      if ( v7 >= 0 )
      {
        _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 6, 5);
        goto LABEL_12;
      }
      v11 = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v5, this, a2, v7);
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 7, 5) != 5 )
      {
LABEL_12:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            (unsigned int)WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids,
            (_DWORD)this,
            (__int64)L"HandleFailedStart");
        v9 = _InterlockedExchange64((volatile __int64 *)this + 9, 0);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        (*(void (__fastcall **)(ComTaskMgrWnd *, ComTaskHost *))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 24LL))(
          ComTaskMgrBase::s_pVirtualSingleton,
          this);
        (*(void (__fastcall **)(ComTaskHost *))(*(_QWORD *)this + 16LL))(this);
        v11 = v7;
        if ( v7 >= 0 )
          goto LABEL_18;
LABEL_24:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v10, this, a2, v11);
        goto LABEL_18;
      }
    }
    else
    {
      v11 = -2147467260;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    goto LABEL_24;
  }
  v11 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids, this);
LABEL_18:
  _InterlockedExchange(&v14, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
    SetEvent((HANDLE)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1));
  return v11;
}

```

## disassembly

```asm
0x140003f10  mov     [rsp+arg_0], rbx
0x140003f15  mov     [rsp+arg_8], rbp
0x140003f1a  push    rsi
0x140003f1b  push    rdi
0x140003f1c  push    r12
0x140003f1e  push    r14
0x140003f20  push    r15
0x140003f22  sub     rsp, 50h
0x140003f26  mov     esi, edx
0x140003f28  mov     rdi, rcx
0x140003f2b  lea     r15, WPP_GLOBAL_Control
0x140003f32  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f39  cmp     rcx, r15
0x140003f3c  jz      short loc_140003F48
0x140003f3e  test    byte ptr [rcx+1Ch], 4
0x140003f42  jnz     loc_14000412B
0x140003f48  mov     [rsp+78h+arg_10], 0
0x140003f53  xor     eax, eax
0x140003f55  xchg    eax, [rsp+78h+arg_10]
0x140003f5c  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x140003f63  xor     ecx, ecx
0x140003f65  xor     eax, eax
0x140003f67  lock cmpxchg cs:dword_1400159E4, ecx
0x140003f6f  setnz   cl
0x140003f72  xchg    ecx, [rsp+78h+arg_10]
0x140003f79  xor     ecx, ecx
0x140003f7b  xor     eax, eax
0x140003f7d  lock cmpxchg [rsp+78h+arg_10], ecx
0x140003f86  jz      loc_1400041E9
0x140003f8c  cmp     esi, 80073C8Dh
0x140003f92  jz      loc_1400040E5
0x140003f98  lea     rcx, [rdi+60h]; lpCriticalSection
0x140003f9c  call    cs:__imp_EnterCriticalSection
0x140003fa2  mov     dword ptr [rdi+58h], 1
0x140003fa9  mov     [rdi+5Ch], esi
0x140003fac  mov     eax, 1
0x140003fb1  mov     r12d, 5
0x140003fb7  lock cmpxchg [rdi+10h], r12d
0x140003fbd  jnz     loc_1400040EC
0x140003fc3  mov     ebx, [rdi+44h]
0x140003fc6  call    cs:__imp_GetCurrentThreadId
0x140003fcc  cmp     eax, cs:?g_dwMainThreadId@@3KA; ulong g_dwMainThreadId
0x140003fd2  jz      loc_14000414C
0x140003fd8  lea     rax, [rdi+18h]
0x140003fdc  mov     [rsp+78h+var_38], ebx
0x140003fe0  mov     [rsp+78h+var_40], esi
0x140003fe4  mov     [rsp+78h+var_48], 1
0x140003fec  mov     [rsp+78h+var_50], rax
0x140003ff1  mov     [rsp+78h+var_58], rdi
0x140003ff6  mov     r9, cs:?g_hStatusContext@@3PEAXEA; void * g_hStatusContext
0x140003ffd  xor     r8d, r8d; pReturnValue
0x140004000  mov     edx, 3; nProcNum
0x140004005  lea     rcx, pProxyInfo; pProxyInfo
0x14000400c  call    cs:__imp_NdrClientCall3
0x140004012  mov     rbx, rax
0x140004015  test    eax, eax
0x140004017  jg      loc_140004172
0x14000401d  test    ebx, ebx
0x14000401f  js      loc_140004180
0x140004025  mov     ecx, 6
0x14000402a  mov     eax, r12d
0x14000402d  lock cmpxchg [rdi+10h], ecx
0x140004032  lea     rcx, [rdi+60h]; lpCriticalSection
0x140004036  call    cs:__imp_LeaveCriticalSection
0x14000403c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004043  cmp     rcx, r15
0x140004046  jz      short loc_140004052
0x140004048  test    byte ptr [rcx+1Ch], 4
0x14000404c  jnz     loc_1400041C5
0x140004052  xor     ecx, ecx
0x140004054  xchg    rcx, [rdi+48h]
0x140004058  test    rcx, rcx
0x14000405b  jz      short loc_140004069
0x14000405d  mov     rax, [rcx]
0x140004060  mov     rax, [rax+10h]
0x140004064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004069  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140004070  mov     rax, [rcx]
0x140004073  mov     rdx, rdi
0x140004076  mov     rax, [rax+18h]
0x14000407a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000407f  mov     rax, [rdi]
0x140004082  mov     rcx, rdi
0x140004085  mov     rax, [rax+10h]
0x140004089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000408e  mov     ebp, ebx
0x140004090  test    ebx, ebx
0x140004092  js      short loc_1400040FB
0x140004094  xor     ecx, ecx
0x140004096  xchg    ecx, [rsp+78h+arg_10]
0x14000409d  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1400040a4  mov     ecx, edx
0x1400040a6  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, ecx; ShutdownMgr::Sync ShutdownMgr::s_sync
0x1400040ae  cmp     ecx, 1
0x1400040b1  jz      short loc_1400040CE
0x1400040b3  mov     eax, ebp
0x1400040b5  lea     r11, [rsp+78h+var_28]
0x1400040ba  mov     rbx, [r11+30h]
0x1400040be  mov     rbp, [r11+38h]
0x1400040c2  mov     rsp, r11
0x1400040c5  pop     r15
0x1400040c7  pop     r14
0x1400040c9  pop     r12
0x1400040cb  pop     rdi
0x1400040cc  pop     rsi
0x1400040cd  retn
0x1400040ce  mov     rax, rdx
0x1400040d1  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rdx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x1400040da  mov     rcx, rax; hEvent
0x1400040dd  call    cs:__imp_SetEvent
0x1400040e3  jmp     short loc_1400040B3
0x1400040e5  mov     ebp, 80070057h
0x1400040ea  jmp     short loc_140004094
0x1400040ec  mov     ebp, 80004004h
0x1400040f1  lea     rcx, [rdi+60h]; lpCriticalSection
0x1400040f5  call    cs:__imp_LeaveCriticalSection
0x1400040fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004102  cmp     rcx, r15
0x140004105  jz      short loc_140004094
0x140004107  test    byte ptr [rcx+1Ch], 1
0x14000410b  jz      short loc_140004094
0x14000410d  mov     edx, 19h
0x140004112  mov     dword ptr [rsp+78h+var_50], ebp
0x140004116  mov     dword ptr [rsp+78h+var_58], esi
0x14000411a  mov     r9, rdi
0x14000411d  mov     rcx, [rcx+10h]
0x140004121  call    WPP_SF_qDD
0x140004126  jmp     loc_140004094
0x14000412b  mov     edx, 0Ah
0x140004130  mov     dword ptr [rsp+78h+var_58], esi
0x140004134  mov     r9, rdi
0x140004137  lea     r8, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids
0x14000413e  mov     rcx, [rcx+10h]
0x140004142  call    WPP_SF_qD
0x140004147  jmp     loc_140003F48
0x14000414c  xor     ebx, ebx
0x14000414e  movzx   eax, si
0x140004151  xor     ecx, ecx
0x140004153  test    esi, esi
0x140004155  cmovs   ecx, eax
0x140004158  mov     cs:?g_dwLastTaskResult@@3KC, ecx; ulong volatile g_dwLastTaskResult
0x14000415e  movzx   eax, cs:?g_ucLastTaskFlags@@3EC; uchar volatile g_ucLastTaskFlags
0x140004165  or      al, 1
0x140004167  mov     cs:?g_ucLastTaskFlags@@3EC, al; uchar volatile g_ucLastTaskFlags
0x14000416d  jmp     loc_14000401D
0x140004172  movzx   ebx, ax
0x140004175  or      ebx, 80070000h
0x14000417b  jmp     loc_14000401D
0x140004180  mov     ebp, ebx
0x140004182  mov     rcx, cs:WPP_GLOBAL_Control
0x140004189  cmp     rcx, r15
0x14000418c  jz      short loc_1400041AD
0x14000418e  test    byte ptr [rcx+1Ch], 1
0x140004192  jz      short loc_1400041AD
0x140004194  mov     edx, 18h
0x140004199  mov     dword ptr [rsp+78h+var_50], ebx
0x14000419d  mov     dword ptr [rsp+78h+var_58], esi
0x1400041a1  mov     r9, rdi
0x1400041a4  mov     rcx, [rcx+10h]
0x1400041a8  call    WPP_SF_qDD
0x1400041ad  mov     ecx, 7
0x1400041b2  mov     eax, r12d
0x1400041b5  lock cmpxchg [rdi+10h], ecx
0x1400041ba  jz      loc_1400040F1
0x1400041c0  jmp     loc_140004032
0x1400041c5  lea     rax, aHandlefailedst; "HandleFailedStart"
0x1400041cc  mov     [rsp+78h+var_58], rax
0x1400041d1  mov     r9, rdi
0x1400041d4  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x1400041db  mov     rcx, [rcx+10h]
0x1400041df  call    WPP_SF_qS
0x1400041e4  jmp     loc_140004052
0x1400041e9  xor     ebp, ebp
0x1400041eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041f2  cmp     rcx, r15
0x1400041f5  jz      loc_140004094
0x1400041fb  test    byte ptr [rcx+1Ch], 4
0x1400041ff  jz      loc_140004094
0x140004205  mov     edx, 0Bh
0x14000420a  mov     r9, rdi
0x14000420d  lea     r8, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids
0x140004214  mov     rcx, [rcx+10h]
0x140004218  call    WPP_SF_q
0x14000421d  jmp     loc_140004094
```
