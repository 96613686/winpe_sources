# ComTaskHost::HandleReportingState(long,ComTaskHost::StateType)

- ea: `0x1400058d0`
- end: `0x140005b14`
- name: `?HandleReportingState@ComTaskHost@@AEAAJJW4StateType@1@@Z`
- size: `580`
- prototype: `__int64 __fastcall(__int64, int, signed __int32)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140004a30`

## callees

- `0x1400058d0`
- `0x140009b24`
- `0x140009c30`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005926`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005926`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000599c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005a3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000599c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005a3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005902`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005902`
- `RPCRT4!NdrClientCall3` at `0x14000596d`
- `RPCRT4!NdrClientCall3` at `0x14000596d`

## pseudocode

```c
__int64 __fastcall ComTaskHost::HandleReportingState(__int64 a1, int a2, signed __int32 a3)
{
  int v6; // r14d
  __int64 v7; // r8
  int Pointer; // eax
  signed int v9; // r15d
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // r14d
  volatile unsigned int v15; // ecx

  if ( a2 != -2147009395 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    *(_DWORD *)(a1 + 88) = 1;
    *(_DWORD *)(a1 + 92) = a2;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), a3, 1) == 1 )
    {
      v6 = *(_DWORD *)(a1 + 68);
      if ( GetCurrentThreadId() == g_dwMainThreadId )
      {
        v15 = 0;
        v9 = 0;
        if ( a2 < 0 )
          v15 = (unsigned __int16)a2;
        g_dwLastTaskResult = v15;
        g_ucLastTaskFlags |= 1u;
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                  3u,
                                  0,
                                  g_hStatusContext,
                                  a1,
                                  a1 + 24,
                                  1,
                                  a2,
                                  v6).Pointer;
        v9 = Pointer;
        if ( Pointer > 0 )
          v9 = (unsigned __int16)Pointer | 0x80070000;
      }
      if ( v9 >= 0 )
      {
        _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), a3 + 1, a3);
        goto LABEL_8;
      }
      v13 = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v7, a1, a2, v9);
      if ( a3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), a3 + 2, a3) )
      {
LABEL_8:
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            (unsigned int)WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids,
            a1,
            (__int64)L"HandleFailedStart");
        v11 = _InterlockedExchange64((volatile __int64 *)(a1 + 72), 0);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        (*(void (__fastcall **)(ComTaskMgrWnd *, __int64))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 24LL))(
          ComTaskMgrBase::s_pVirtualSingleton,
          a1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
        v13 = v9;
        if ( v9 >= 0 )
          return v13;
        goto LABEL_18;
      }
    }
    else
    {
      v13 = -2147467260;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
LABEL_18:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v12, a1, a2, v13);
    return v13;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400058d0  mov     rax, rsp
0x1400058d3  push    rbx
0x1400058d4  push    rsi
0x1400058d5  push    rdi
0x1400058d6  sub     rsp, 60h
0x1400058da  mov     esi, r8d
0x1400058dd  mov     edi, edx
0x1400058df  mov     rbx, rcx
0x1400058e2  cmp     edx, 80073C8Dh
0x1400058e8  jz      loc_140005A21
0x1400058ee  mov     [rax+8], rbp
0x1400058f2  add     rcx, 60h ; '`'; lpCriticalSection
0x1400058f6  mov     [rax+18h], r12
0x1400058fa  mov     [rax-20h], r14
0x1400058fe  mov     [rax-28h], r15
0x140005902  call    cs:__imp_EnterCriticalSection
0x140005908  mov     eax, 1
0x14000590d  mov     dword ptr [rbx+58h], 1
0x140005914  mov     [rbx+5Ch], edi
0x140005917  lock cmpxchg [rbx+10h], esi
0x14000591c  jnz     loc_140005A2E
0x140005922  mov     r14d, [rbx+44h]
0x140005926  call    cs:__imp_GetCurrentThreadId
0x14000592c  cmp     eax, cs:?g_dwMainThreadId@@3KA; ulong g_dwMainThreadId
0x140005932  jz      loc_140005A73
0x140005938  mov     r9, cs:?g_hStatusContext@@3PEAXEA; void * g_hStatusContext
0x14000593f  lea     rax, [rbx+18h]
0x140005943  mov     [rsp+78h+var_38], r14d
0x140005948  lea     rcx, pProxyInfo; pProxyInfo
0x14000594f  mov     [rsp+78h+var_40], edi
0x140005953  xor     r8d, r8d; pReturnValue
0x140005956  mov     [rsp+78h+var_48], 1
0x14000595e  mov     edx, 3; nProcNum
0x140005963  mov     [rsp+78h+var_50], rax
0x140005968  mov     [rsp+78h+var_58], rbx
0x14000596d  call    cs:__imp_NdrClientCall3
0x140005973  mov     r15, rax
0x140005976  test    eax, eax
0x140005978  jg      loc_140005A9A
0x14000597e  lea     r12, WPP_GLOBAL_Control
0x140005985  test    r15d, r15d
0x140005988  js      loc_140005AAA
0x14000598e  lea     edx, [rsi+1]
0x140005991  mov     eax, esi
0x140005993  lock cmpxchg [rbx+10h], edx
0x140005998  lea     rcx, [rbx+60h]; lpCriticalSection
0x14000599c  call    cs:__imp_LeaveCriticalSection
0x1400059a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059a9  cmp     rcx, r12
0x1400059ac  jz      short loc_1400059B8
0x1400059ae  test    byte ptr [rcx+1Ch], 4
0x1400059b2  jnz     loc_140005AF0
0x1400059b8  xor     ecx, ecx
0x1400059ba  xchg    rcx, [rbx+48h]
0x1400059be  test    rcx, rcx
0x1400059c1  jz      short loc_1400059CF
0x1400059c3  mov     rax, [rcx]
0x1400059c6  mov     rax, [rax+10h]
0x1400059ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059cf  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x1400059d6  mov     rdx, rbx
0x1400059d9  mov     rax, [rcx]
0x1400059dc  mov     rax, [rax+18h]
0x1400059e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059e5  mov     rax, [rbx]
0x1400059e8  mov     rcx, rbx
0x1400059eb  mov     rax, [rax+10h]
0x1400059ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059f4  mov     r14d, r15d
0x1400059f7  test    r15d, r15d
0x1400059fa  js      short loc_140005A45
0x1400059fc  mov     r15, [rsp+78h+var_28]
0x140005a01  mov     eax, r14d
0x140005a04  mov     r14, [rsp+78h+var_20]
0x140005a09  mov     r12, [rsp+78h+arg_10]
0x140005a11  mov     rbp, [rsp+78h+arg_0]
0x140005a19  add     rsp, 60h
0x140005a1d  pop     rdi
0x140005a1e  pop     rsi
0x140005a1f  pop     rbx
0x140005a20  retn
0x140005a21  mov     eax, 80070057h
0x140005a26  add     rsp, 60h
0x140005a2a  pop     rdi
0x140005a2b  pop     rsi
0x140005a2c  pop     rbx
0x140005a2d  retn
0x140005a2e  mov     r14d, 80004004h
0x140005a34  lea     r12, WPP_GLOBAL_Control
0x140005a3b  lea     rcx, [rbx+60h]; lpCriticalSection
0x140005a3f  call    cs:__imp_LeaveCriticalSection
0x140005a45  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a4c  cmp     rcx, r12
0x140005a4f  jz      short loc_1400059FC
0x140005a51  test    byte ptr [rcx+1Ch], 1
0x140005a55  jz      short loc_1400059FC
0x140005a57  mov     rcx, [rcx+10h]
0x140005a5b  mov     edx, 19h
0x140005a60  mov     dword ptr [rsp+78h+var_50], r14d
0x140005a65  mov     r9, rbx
0x140005a68  mov     dword ptr [rsp+78h+var_58], edi
0x140005a6c  call    WPP_SF_qDD
0x140005a71  jmp     short loc_1400059FC
0x140005a73  xor     ecx, ecx
0x140005a75  movzx   eax, di
0x140005a78  xor     r15d, r15d
0x140005a7b  test    edi, edi
0x140005a7d  cmovs   ecx, eax
0x140005a80  mov     cs:?g_dwLastTaskResult@@3KC, ecx; ulong volatile g_dwLastTaskResult
0x140005a86  movzx   eax, cs:?g_ucLastTaskFlags@@3EC; uchar volatile g_ucLastTaskFlags
0x140005a8d  or      al, 1
0x140005a8f  mov     cs:?g_ucLastTaskFlags@@3EC, al; uchar volatile g_ucLastTaskFlags
0x140005a95  jmp     loc_14000597E
0x140005a9a  movzx   r15d, ax
0x140005a9e  or      r15d, 80070000h
0x140005aa5  jmp     loc_14000597E
0x140005aaa  mov     r14d, r15d
0x140005aad  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ab4  cmp     rcx, r12
0x140005ab7  jz      short loc_140005AD9
0x140005ab9  test    byte ptr [rcx+1Ch], 1
0x140005abd  jz      short loc_140005AD9
0x140005abf  mov     rcx, [rcx+10h]
0x140005ac3  mov     edx, 18h
0x140005ac8  mov     dword ptr [rsp+78h+var_50], r15d
0x140005acd  mov     r9, rbx
0x140005ad0  mov     dword ptr [rsp+78h+var_58], edi
0x140005ad4  call    WPP_SF_qDD
0x140005ad9  lea     ecx, [rsi+2]
0x140005adc  mov     eax, esi
0x140005ade  lock cmpxchg [rbx+10h], ecx
0x140005ae3  cmp     esi, eax
0x140005ae5  jz      loc_140005A3B
0x140005aeb  jmp     loc_140005998
0x140005af0  mov     rcx, [rcx+10h]
0x140005af4  lea     rax, aHandlefailedst; "HandleFailedStart"
0x140005afb  mov     r9, rbx
0x140005afe  mov     [rsp+78h+var_58], rax
0x140005b03  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140005b0a  call    WPP_SF_qS
0x140005b0f  jmp     loc_1400059B8
```
