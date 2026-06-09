# LB_ARBITRATOR::PerformArbitration(ushort * *,ushort *,int *,int *,ulong *,void * *)

- ea: `0x180020c3c`
- end: `0x180021231`
- name: `?PerformArbitration@LB_ARBITRATOR@@QEAAJPEAPEAGPEAGPEAH2PEAKPEAPEAX@Z`
- size: `1525`
- prototype: `__int64 __fastcall(LB_ARBITRATOR *this, const unsigned __int16 **, unsigned __int16 *, int *, int *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001fc58`

## callees

- `0x18001e3d4`
- `0x18001f9c0`
- `0x18001f9f4`
- `0x1800206c0`
- `0x180020764`
- `0x18002079c`
- `0x1800208cc`
- `0x180020c00`
- `0x180020c3c`
- `0x1800214a4`
- `0x180021544`
- `0x1800215e4`
- `0x180021698`
- `0x180021744`
- `0x180021810`
- `0x180021884`
- `0x18002199c`
- `0x180023a6c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180020e2a`
- `KERNEL32!CompareStringW` at `0x180020ef9`
- `KERNEL32!CompareStringW` at `0x180020e2a`
- `KERNEL32!CompareStringW` at `0x180020ef9`
- `RPCRT4!I_RpcFree` at `0x180020ca5`
- `RPCRT4!I_RpcFree` at `0x180020d09`
- `RPCRT4!I_RpcFree` at `0x180020dc1`
- `RPCRT4!I_RpcFree` at `0x180020e9a`
- `RPCRT4!I_RpcFree` at `0x180020faf`
- `RPCRT4!I_RpcFree` at `0x180020fbe`
- `RPCRT4!I_RpcFree` at `0x180021078`
- `RPCRT4!I_RpcFree` at `0x1800211b6`
- `RPCRT4!I_RpcFree` at `0x180020ca5`
- `RPCRT4!I_RpcFree` at `0x180020d09`
- `RPCRT4!I_RpcFree` at `0x180020dc1`
- `RPCRT4!I_RpcFree` at `0x180020e9a`
- `RPCRT4!I_RpcFree` at `0x180020faf`
- `RPCRT4!I_RpcFree` at `0x180020fbe`
- `RPCRT4!I_RpcFree` at `0x180021078`
- `RPCRT4!I_RpcFree` at `0x1800211b6`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180020dd5`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180020eae`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180020dd5`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180020eae`

## pseudocode

```c
__int64 __fastcall LB_ARBITRATOR::PerformArbitration(
        LB_ARBITRATOR *this,
        const unsigned __int16 **a2,
        unsigned __int16 *a3,
        int *a4,
        int *a5,
        unsigned int *a6,
        void **a7)
{
  unsigned __int16 *v10; // rsi
  unsigned int FirstError; // edi
  unsigned int i; // edi
  struct _GUID *v14; // rdx
  LBS_CALL *v15; // rcx
  int v16; // edx
  unsigned __int16 v17; // bp
  unsigned int v18; // r15d
  WCHAR *v19; // r14
  unsigned __int64 v20; // r12
  unsigned int v21; // r12d
  unsigned int v22; // eax
  struct LBS_CALL *v23; // rax
  struct LBS_CALL *v24; // rdi
  int v25; // eax
  int v26; // edx
  unsigned int j; // ebp
  LBS_CALL *v28; // rcx
  __int64 v29; // rcx
  int v30; // edx
  __int64 v31; // r8
  unsigned int v32; // ecx
  __int64 v33; // rdx
  LB_ARBITRATOR *v34; // rcx
  unsigned int v35; // ebp
  LBS_CALL *v36; // rcx
  unsigned int v37; // ebp
  unsigned int v38; // eax
  struct LBS_CALL *v39; // r14
  __int64 v40; // r8
  unsigned int v41; // ecx
  __int64 v42; // rdx
  LB_ABANDONED_CALL_MANAGER *v43; // rcx
  unsigned __int16 v44; // [rsp+80h] [rbp+8h]

  v10 = 0;
  *a4 = 0;
  if ( !*((_DWORD *)this + 16) )
  {
    v10 = DuplicateString(*a2);
    if ( !v10 )
      return 14;
  }
  FirstError = LB_ARBITRATOR::InitCallEnvironment(this);
  if ( FirstError )
  {
    if ( v10 )
      I_RpcFree(v10);
    return FirstError;
  }
  for ( i = 0; i < *((_DWORD *)this + 12); ++i )
  {
    v14 = (struct _GUID *)((char *)this + 84);
    v15 = (LBS_CALL *)(*((_QWORD *)this + 3) + 184LL * i);
    if ( *((_DWORD *)this + 16) == 1 )
      LBS_CALL::SubmitQuery(v15, v14);
    else
      LBS_CALL::SubmitLockOrQuery(v15, v14, (unsigned __int16 *)*a2, *a3, (struct _GUID *)((char *)this + 68));
  }
  if ( LB_ARBITRATOR::GetNumberOfPendingCalls(this, 0) )
  {
    v17 = 0;
    v18 = g_LBSResponseTimeout;
    v44 = 0;
    if ( *((_DWORD *)this + 16) != 1 )
      v18 = g_LBSResponseTimeout >> 1;
    v19 = 0;
    v20 = MEMORY[0x7FFE0320] * MEMORY[0x7FFE0004];
    *a5 = v16;
    v21 = v18 + (v20 >> 24);
    do
    {
      v22 = CalculateRemainingTimeout(v21);
      v23 = LB_ARBITRATOR::WaitForCallSignal(this, v22);
      v24 = v23;
      if ( v23 )
      {
        v25 = *((_DWORD *)v23 + 37);
        if ( v25 != 6 )
        {
          switch ( v25 )
          {
            case 2:
              if ( v19 )
              {
                if ( !*a5
                  && (CompareStringW(0x7Fu, 1u, v19, -1, *((PCNZWCH *)v24 + 16), -1) != 2 || v17 != *((_WORD *)v24 + 60)) )
                {
                  *a5 = 1;
                }
              }
              else
              {
                v19 = DuplicateString(*((const unsigned __int16 **)v24 + 16));
                if ( v19 )
                {
                  v17 = *((_WORD *)v24 + 60);
                  v44 = v17;
                }
                else
                {
                  I_RpcFree(*((void **)v24 + 16));
                  *((_QWORD *)v24 + 16) = 0;
                  RpcSsDestroyClientContext((void **)v24 + 17);
                  LBS_CALL::ChangeCallState(v24, 6, 14);
                }
              }
              break;
            case 1:
              v26 = *((_DWORD *)v24 + 36);
              if ( v26 )
              {
                if ( v26 == 1 || v26 == 2 )
                {
                  if ( v26 == 1 )
                  {
                    if ( v19 )
                    {
                      if ( !*a5
                        && (CompareStringW(0x7Fu, 1u, v19, -1, *((PCNZWCH *)v24 + 16), -1) != 2
                         || v17 != *((_WORD *)v24 + 60)) )
                      {
                        *a5 = 1;
                      }
                    }
                    else
                    {
                      v19 = DuplicateString(*((const unsigned __int16 **)v24 + 16));
                      if ( v19 )
                      {
                        v44 = *((_WORD *)v24 + 60);
                      }
                      else
                      {
                        I_RpcFree(*((void **)v24 + 16));
                        *((_QWORD *)v24 + 16) = 0;
                        RpcSsDestroyClientContext((void **)v24 + 17);
                        LBS_CALL::ChangeCallState(v24, 6, 14);
                      }
                    }
                  }
                  if ( !*((_DWORD *)this + 16) )
                  {
                    for ( j = 0; j < *((_DWORD *)this + 12); ++j )
                    {
                      v28 = (LBS_CALL *)(*((_QWORD *)this + 3) + 184LL * j);
                      if ( *((_DWORD *)v28 + 37) == 1 && *((_DWORD *)v28 + 38) == 2 && !*((_DWORD *)v28 + 36) )
                        LBS_CALL::SubmitRollback(v28);
                    }
                    *((_DWORD *)this + 16) = 1;
                    v21 += v18;
                  }
                  if ( *((_DWORD *)v24 + 36) == 2 )
                    LBS_CALL::SubmitQuery(v24, (struct _GUID *)((char *)this + 84));
                  v17 = v44;
                }
              }
              else if ( *((_DWORD *)this + 16) == 1 )
              {
                LBS_CALL::SubmitRollback(v24);
              }
              break;
            case 3:
              LBS_CALL::SubmitQuery(v24, (struct _GUID *)((char *)this + 84));
              break;
          }
        }
      }
    }
    while ( LB_ARBITRATOR::GetNumberOfPendingCalls(this, 0) && v24 );
    LB_ARBITRATOR::MarkAllPendingCallsAsAbandoned(this);
    FirstError = 0;
    if ( v19 )
    {
      if ( v10 )
        I_RpcFree(v10);
      if ( *a5 )
      {
        I_RpcFree(v19);
        if ( *((_DWORD *)this + 12) )
        {
          do
          {
            v29 = *((_QWORD *)this + 3) + 184LL * FirstError;
            if ( *(_DWORD *)(v29 + 152) == 2 && *(_QWORD *)(v29 + 136) )
              LBS_CALL::SubmitClose((LBS_CALL *)v29);
            ++FirstError;
          }
          while ( FirstError < *((_DWORD *)this + 12) );
        }
        _InterlockedIncrement((volatile signed __int32 *)&g_TotalFailedConsistencyChecks);
        FirstError = 1727;
        goto LABEL_106;
      }
      *a2 = v19;
      *a3 = v17;
      goto LABEL_71;
    }
    if ( *((_DWORD *)this + 16) == 1 )
    {
      if ( v10 )
        I_RpcFree(v10);
      v30 = 1;
    }
    else
    {
      if ( !*((_DWORD *)this + 12) )
      {
LABEL_83:
        LB_ARBITRATOR::UnmarkAllAbandonedPendingCalls(this);
        if ( LB_ARBITRATOR::GetNumberOfPendingCalls(v34, 0) )
          FirstError = 1818;
        else
          FirstError = LB_ARBITRATOR::GetFirstError(this);
        LB_ARBITRATOR::MarkAllPendingCallsAsAbandoned(this);
LABEL_106:
        LB_ARBITRATOR::UpdateSuccessCounters(this, FirstError == 0);
        if ( LB_ARBITRATOR::GetNumberOfPendingCalls(this, 1) )
        {
          LB_ABANDONED_CALL_MANAGER::AbandonArbitrator(v43, this);
          *a4 = 1;
        }
        return FirstError;
      }
      v31 = *((_QWORD *)this + 3);
      v32 = 0;
      while ( 1 )
      {
        v33 = 184LL * v32;
        if ( *(_DWORD *)(v33 + v31 + 152) == 2 && *(_DWORD *)(v33 + v31 + 148) == 1 )
          break;
        if ( ++v32 >= *((_DWORD *)this + 12) )
          goto LABEL_83;
      }
      v35 = 0;
      do
      {
        v36 = (LBS_CALL *)(*((_QWORD *)this + 3) + 184LL * v35);
        if ( *((_DWORD *)v36 + 38) == 2 && *((_DWORD *)v36 + 37) == 1 )
          LBS_CALL::SubmitCommit(v36);
        ++v35;
      }
      while ( v35 < *((_DWORD *)this + 12) );
      if ( LB_ARBITRATOR::GetNumberOfPendingCalls(this, 0) )
      {
        v37 = g_LBSResponseTimeout + ((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24);
        do
        {
          v38 = CalculateRemainingTimeout(v37);
          v39 = LB_ARBITRATOR::WaitForCallSignal(this, v38);
        }
        while ( LB_ARBITRATOR::GetNumberOfPendingCalls(this, 0) && v39 );
      }
      if ( *((_DWORD *)this + 12) )
      {
        v40 = *((_QWORD *)this + 3);
        v41 = 0;
        while ( 1 )
        {
          v42 = 184LL * v41;
          if ( *(_DWORD *)(v42 + v40 + 152) == 2 && *(_DWORD *)(v42 + v40 + 148) == 4 )
            break;
          if ( ++v41 >= *((_DWORD *)this + 12) )
            goto LABEL_99;
        }
        *a2 = v10;
LABEL_71:
        LB_ARBITRATOR::GetAllUseCounts(this, a6, a7);
        goto LABEL_106;
      }
LABEL_99:
      if ( v10 )
        I_RpcFree(v10);
      v30 = 0;
    }
    if ( LB_ARBITRATOR::GetNumberOfPendingCalls(this, v30) )
      FirstError = 1818;
    else
      FirstError = LB_ARBITRATOR::GetFirstError(this);
    goto LABEL_106;
  }
  if ( v10 )
    I_RpcFree(v10);
  LB_ARBITRATOR::UpdateSuccessCounters(this, 0);
  return LB_ARBITRATOR::GetFirstError(this);
}

```

## disassembly

```asm
0x180020c3c  mov     [rsp+arg_18], r9
0x180020c41  mov     [rsp+arg_10], r8
0x180020c46  mov     [rsp+arg_8], rdx
0x180020c4b  push    rbx
0x180020c4c  push    rbp
0x180020c4d  push    rsi
0x180020c4e  push    rdi
0x180020c4f  push    r12
0x180020c51  push    r13
0x180020c53  push    r14
0x180020c55  push    r15
0x180020c57  sub     rsp, 38h
0x180020c5b  xor     r13d, r13d
0x180020c5e  mov     r15, r8
0x180020c61  mov     r14, rdx
0x180020c64  mov     rbx, rcx
0x180020c67  mov     esi, r13d
0x180020c6a  mov     [r9], r13d
0x180020c6d  cmp     [rcx+40h], r13d
0x180020c71  jnz     short loc_180020C8B
0x180020c73  mov     rcx, [rdx]; Src
0x180020c76  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180020c7b  mov     rsi, rax
0x180020c7e  test    rax, rax
0x180020c81  jnz     short loc_180020C8B
0x180020c83  lea     eax, [rsi+0Eh]
0x180020c86  jmp     loc_180021220
0x180020c8b  mov     rcx, rbx; this
0x180020c8e  call    ?InitCallEnvironment@LB_ARBITRATOR@@AEAAJXZ; LB_ARBITRATOR::InitCallEnvironment(void)
0x180020c93  mov     edi, eax
0x180020c95  test    eax, eax
0x180020c97  jz      short loc_180020CB0
0x180020c99  test    rsi, rsi
0x180020c9c  jz      loc_18002121E
0x180020ca2  mov     rcx, rsi; Object
0x180020ca5  call    cs:__imp_I_RpcFree
0x180020cab  jmp     loc_18002121E
0x180020cb0  mov     edi, r13d
0x180020cb3  cmp     [rbx+30h], r13d
0x180020cb7  jbe     short loc_180020CF3
0x180020cb9  mov     eax, edi
0x180020cbb  lea     rdx, [rbx+54h]; struct _GUID *
0x180020cbf  imul    rcx, rax, 0B8h
0x180020cc6  add     rcx, [rbx+18h]; this
0x180020cca  cmp     dword ptr [rbx+40h], 1
0x180020cce  jnz     short loc_180020CD7
0x180020cd0  call    ?SubmitQuery@LBS_CALL@@QEAAXPEAU_GUID@@@Z; LBS_CALL::SubmitQuery(_GUID *)
0x180020cd5  jmp     short loc_180020CEC
0x180020cd7  movzx   r9d, word ptr [r15]; unsigned __int16
0x180020cdb  lea     rax, [rbx+44h]
0x180020cdf  mov     r8, [r14]; unsigned __int16 *
0x180020ce2  mov     [rsp+78h+lpString2], rax; struct _GUID *
0x180020ce7  call    ?SubmitLockOrQuery@LBS_CALL@@QEAAXPEAU_GUID@@PEAGG0@Z; LBS_CALL::SubmitLockOrQuery(_GUID *,ushort *,ushort,_GUID *)
0x180020cec  inc     edi
0x180020cee  cmp     edi, [rbx+30h]
0x180020cf1  jb      short loc_180020CB9
0x180020cf3  xor     edx, edx; int
0x180020cf5  mov     rcx, rbx; this
0x180020cf8  call    ?GetNumberOfPendingCalls@LB_ARBITRATOR@@AEAAKH@Z; LB_ARBITRATOR::GetNumberOfPendingCalls(int)
0x180020cfd  test    eax, eax
0x180020cff  jnz     short loc_180020D26
0x180020d01  test    rsi, rsi
0x180020d04  jz      short loc_180020D0F
0x180020d06  mov     rcx, rsi; Object
0x180020d09  call    cs:__imp_I_RpcFree
0x180020d0f  xor     edx, edx; int
0x180020d11  mov     rcx, rbx; this
0x180020d14  call    ?UpdateSuccessCounters@LB_ARBITRATOR@@AEAAXH@Z; LB_ARBITRATOR::UpdateSuccessCounters(int)
0x180020d19  mov     rcx, rbx; this
0x180020d1c  call    ?GetFirstError@LB_ARBITRATOR@@AEAAJXZ; LB_ARBITRATOR::GetFirstError(void)
0x180020d21  jmp     loc_180021220
0x180020d26  cmp     dword ptr [rbx+40h], 1
0x180020d2a  mov     ebp, r13d
0x180020d2d  mov     r15d, cs:?g_LBSResponseTimeout@@3KA; ulong g_LBSResponseTimeout
0x180020d34  mov     [rsp+78h+arg_0], r13d
0x180020d3c  jz      short loc_180020D41
0x180020d3e  shr     r15d, 1
0x180020d41  mov     eax, 7FFE0320h
0x180020d46  mov     r14, r13
0x180020d49  mov     r13, [rsp+78h+arg_20]
0x180020d51  mov     rax, [rax]
0x180020d54  mov     r12d, ds:7FFE0004h
0x180020d5c  imul    r12, rax
0x180020d60  mov     [r13+0], edx
0x180020d64  shr     r12, 18h
0x180020d68  add     r12d, r15d
0x180020d6b  mov     ecx, r12d; unsigned int
0x180020d6e  call    ?CalculateRemainingTimeout@@YAKK@Z; CalculateRemainingTimeout(ulong)
0x180020d73  mov     edx, eax; unsigned int
0x180020d75  mov     rcx, rbx; this
0x180020d78  call    ?WaitForCallSignal@LB_ARBITRATOR@@AEAAPEAVLBS_CALL@@K@Z; LB_ARBITRATOR::WaitForCallSignal(ulong)
0x180020d7d  mov     rdi, rax
0x180020d80  test    rax, rax
0x180020d83  jz      loc_180020F79
0x180020d89  mov     eax, [rax+94h]
0x180020d8f  cmp     eax, 6
0x180020d92  jz      loc_180020F79
0x180020d98  cmp     eax, 2
0x180020d9b  jnz     loc_180020E4C
0x180020da1  test    r14, r14
0x180020da4  jnz     short loc_180020E00
0x180020da6  mov     rcx, [rdi+80h]; Src
0x180020dad  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180020db2  mov     r14, rax
0x180020db5  test    rax, rax
0x180020db8  jnz     short loc_180020DF0
0x180020dba  mov     rcx, [rdi+80h]; Object
0x180020dc1  call    cs:__imp_I_RpcFree
0x180020dc7  lea     rcx, [rdi+88h]; ContextHandle
0x180020dce  mov     [rdi+80h], r14
0x180020dd5  call    cs:__imp_RpcSsDestroyClientContext
0x180020ddb  lea     edx, [r14+6]
0x180020ddf  mov     rcx, rdi
0x180020de2  lea     r8d, [r14+0Eh]
0x180020de6  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x180020deb  jmp     loc_180020F79
0x180020df0  movzx   ebp, word ptr [rdi+78h]
0x180020df4  mov     [rsp+78h+arg_0], ebp
0x180020dfb  jmp     loc_180020F79
0x180020e00  cmp     dword ptr [r13+0], 0
0x180020e05  jnz     loc_180020F79
0x180020e0b  mov     rax, [rdi+80h]
0x180020e12  or      ecx, 0FFFFFFFFh
0x180020e15  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180020e19  mov     r9d, ecx; cchCount1
0x180020e1c  mov     r8, r14; lpString1
0x180020e1f  mov     [rsp+78h+lpString2], rax; lpString2
0x180020e24  lea     edx, [rcx+2]; dwCmpFlags
0x180020e27  lea     ecx, [rdx+7Eh]; Locale
0x180020e2a  call    cs:__imp_CompareStringW
0x180020e30  cmp     eax, 2
0x180020e33  jnz     short loc_180020E3F
0x180020e35  cmp     bp, [rdi+78h]
0x180020e39  jz      loc_180020F79
0x180020e3f  mov     dword ptr [r13+0], 1
0x180020e47  jmp     loc_180020F79
0x180020e4c  cmp     eax, 1
0x180020e4f  jnz     loc_18002101D
0x180020e55  mov     edx, [rdi+90h]
0x180020e5b  mov     ecx, edx
0x180020e5d  test    edx, edx
0x180020e5f  jz      loc_180021006
0x180020e65  sub     ecx, eax
0x180020e67  jz      short loc_180020E71
0x180020e69  cmp     ecx, eax
0x180020e6b  jnz     loc_180020F79
0x180020e71  cmp     edx, 1
0x180020e74  jnz     loc_180020F12
0x180020e7a  test    r14, r14
0x180020e7d  jnz     short loc_180020ED3
0x180020e7f  mov     rcx, [rdi+80h]; Src
0x180020e86  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180020e8b  mov     r14, rax
0x180020e8e  test    rax, rax
0x180020e91  jnz     short loc_180020EC6
0x180020e93  mov     rcx, [rdi+80h]; Object
0x180020e9a  call    cs:__imp_I_RpcFree
0x180020ea0  lea     rcx, [rdi+88h]; ContextHandle
0x180020ea7  mov     [rdi+80h], r14
0x180020eae  call    cs:__imp_RpcSsDestroyClientContext
0x180020eb4  lea     edx, [r14+6]
0x180020eb8  mov     rcx, rdi
0x180020ebb  lea     r8d, [r14+0Eh]
0x180020ebf  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x180020ec4  jmp     short loc_180020F12
0x180020ec6  movzx   eax, word ptr [rdi+78h]
0x180020eca  mov     [rsp+78h+arg_0], eax
0x180020ed1  jmp     short loc_180020F12
0x180020ed3  cmp     dword ptr [r13+0], 0
0x180020ed8  jnz     short loc_180020F12
0x180020eda  mov     rax, [rdi+80h]
0x180020ee1  or      ecx, 0FFFFFFFFh
0x180020ee4  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180020ee8  mov     r9d, ecx; cchCount1
0x180020eeb  mov     r8, r14; lpString1
0x180020eee  mov     [rsp+78h+lpString2], rax; lpString2
0x180020ef3  lea     edx, [rcx+2]; dwCmpFlags
0x180020ef6  lea     ecx, [rdx+7Eh]; Locale
0x180020ef9  call    cs:__imp_CompareStringW
0x180020eff  cmp     eax, 2
0x180020f02  jnz     short loc_180020F0A
0x180020f04  cmp     bp, [rdi+78h]
0x180020f08  jz      short loc_180020F12
0x180020f0a  mov     dword ptr [r13+0], 1
0x180020f12  cmp     dword ptr [rbx+40h], 0
0x180020f16  jnz     short loc_180020F5D
0x180020f18  xor     ebp, ebp
0x180020f1a  cmp     [rbx+30h], ebp
0x180020f1d  jbe     short loc_180020F53
0x180020f1f  mov     eax, ebp
0x180020f21  imul    rcx, rax, 0B8h
0x180020f28  add     rcx, [rbx+18h]; this
0x180020f2c  cmp     dword ptr [rcx+94h], 1
0x180020f33  jnz     short loc_180020F4C
0x180020f35  cmp     dword ptr [rcx+98h], 2
0x180020f3c  jnz     short loc_180020F4C
0x180020f3e  cmp     dword ptr [rcx+90h], 0
0x180020f45  jnz     short loc_180020F4C
0x180020f47  call    ?SubmitRollback@LBS_CALL@@QEAAXXZ; LBS_CALL::SubmitRollback(void)
0x180020f4c  inc     ebp
0x180020f4e  cmp     ebp, [rbx+30h]
0x180020f51  jb      short loc_180020F1F
0x180020f53  mov     dword ptr [rbx+40h], 1
0x180020f5a  add     r12d, r15d
0x180020f5d  cmp     dword ptr [rdi+90h], 2
0x180020f64  jnz     short loc_180020F72
0x180020f66  lea     rdx, [rbx+54h]; struct _GUID *
0x180020f6a  mov     rcx, rdi; this
0x180020f6d  call    ?SubmitQuery@LBS_CALL@@QEAAXPEAU_GUID@@@Z; LBS_CALL::SubmitQuery(_GUID *)
0x180020f72  mov     ebp, [rsp+78h+arg_0]
0x180020f79  xor     edx, edx; int
0x180020f7b  mov     rcx, rbx; this
0x180020f7e  call    ?GetNumberOfPendingCalls@LB_ARBITRATOR@@AEAAKH@Z; LB_ARBITRATOR::GetNumberOfPendingCalls(int)
0x180020f83  test    eax, eax
0x180020f85  jz      short loc_180020F90
0x180020f87  test    rdi, rdi
0x180020f8a  jnz     loc_180020D6B
0x180020f90  mov     rcx, rbx; this
0x180020f93  call    ?MarkAllPendingCallsAsAbandoned@LB_ARBITRATOR@@AEAAXXZ; LB_ARBITRATOR::MarkAllPendingCallsAsAbandoned(void)
0x180020f98  xor     r15d, r15d
0x180020f9b  mov     edi, r15d
0x180020f9e  test    r14, r14
0x180020fa1  jz      loc_18002106A
0x180020fa7  test    rsi, rsi
0x180020faa  jz      short loc_180020FB5
0x180020fac  mov     rcx, rsi; Object
0x180020faf  call    cs:__imp_I_RpcFree
0x180020fb5  cmp     [r13+0], r15d
0x180020fb9  jz      short loc_180021037
0x180020fbb  mov     rcx, r14; Object
0x180020fbe  call    cs:__imp_I_RpcFree
0x180020fc4  cmp     [rbx+30h], r15d
0x180020fc8  jbe     short loc_180020FF5
0x180020fca  mov     eax, edi
0x180020fcc  imul    rcx, rax, 0B8h
0x180020fd3  add     rcx, [rbx+18h]; this
0x180020fd7  cmp     dword ptr [rcx+98h], 2
0x180020fde  jnz     short loc_180020FEE
0x180020fe0  cmp     [rcx+88h], r15
0x180020fe7  jz      short loc_180020FEE
0x180020fe9  call    ?SubmitClose@LBS_CALL@@QEAAXXZ; LBS_CALL::SubmitClose(void)
0x180020fee  inc     edi
0x180020ff0  cmp     edi, [rbx+30h]
0x180020ff3  jb      short loc_180020FCA
0x180020ff5  lock inc cs:?g_TotalFailedConsistencyChecks@@3KA; ulong g_TotalFailedConsistencyChecks
0x180020ffc  mov     edi, 6BFh
0x180021001  jmp     loc_1800211E7
0x180021006  cmp     dword ptr [rbx+40h], 1
0x18002100a  jnz     loc_180020F79
0x180021010  mov     rcx, rdi; this
0x180021013  call    ?SubmitRollback@LBS_CALL@@QEAAXXZ; LBS_CALL::SubmitRollback(void)
0x180021018  jmp     loc_180020F79
0x18002101d  cmp     eax, 3
0x180021020  jnz     loc_180020F79
0x180021026  lea     rdx, [rbx+54h]; struct _GUID *
0x18002102a  mov     rcx, rdi; this
0x18002102d  call    ?SubmitQuery@LBS_CALL@@QEAAXPEAU_GUID@@@Z; LBS_CALL::SubmitQuery(_GUID *)
0x180021032  jmp     loc_180020F79
0x180021037  mov     rax, [rsp+78h+arg_8]
0x18002103f  mov     [rax], r14
0x180021042  mov     rax, [rsp+78h+arg_10]
0x18002104a  mov     [rax], bp
0x18002104d  mov     r8, [rsp+78h+arg_30]; void **
0x180021055  mov     rcx, rbx; this
0x180021058  mov     rdx, [rsp+78h+arg_28]; unsigned int *
0x180021060  call    ?GetAllUseCounts@LB_ARBITRATOR@@AEAAXPEAKPEAPEAX@Z; LB_ARBITRATOR::GetAllUseCounts(ulong *,void * *)
0x180021065  jmp     loc_1800211E7
0x18002106a  cmp     dword ptr [rbx+40h], 1
0x18002106e  jnz     short loc_1800210A2
0x180021070  test    rsi, rsi
0x180021073  jz      short loc_18002107E
0x180021075  mov     rcx, rsi; Object
0x180021078  call    cs:__imp_I_RpcFree
0x18002107e  mov     edx, 1; int
0x180021083  mov     rcx, rbx; this
0x180021086  call    ?GetNumberOfPendingCalls@LB_ARBITRATOR@@AEAAKH@Z; LB_ARBITRATOR::GetNumberOfPendingCalls(int)
0x18002108b  test    eax, eax
0x18002108d  jnz     loc_1800211D3
0x180021093  mov     rcx, rbx; this
0x180021096  call    ?GetFirstError@LB_ARBITRATOR@@AEAAJXZ; LB_ARBITRATOR::GetFirstError(void)
0x18002109b  mov     edi, eax
0x18002109d  jmp     loc_1800211E7
0x1800210a2  cmp     [rbx+30h], r15d
0x1800210a6  jbe     short loc_1800210D5
0x1800210a8  mov     r8, [rbx+18h]
0x1800210ac  mov     ecx, r15d
0x1800210af  mov     eax, ecx
0x1800210b1  imul    rdx, rax, 0B8h
0x1800210b8  cmp     dword ptr [rdx+r8+98h], 2
0x1800210c1  jnz     short loc_1800210CE
0x1800210c3  cmp     dword ptr [rdx+r8+94h], 1
0x1800210cc  jz      short loc_1800210FB
0x1800210ce  inc     ecx
0x1800210d0  cmp     ecx, [rbx+30h]
0x1800210d3  jb      short loc_1800210AF
0x1800210d5  mov     rcx, rbx; this
0x1800210d8  call    ?UnmarkAllAbandonedPendingCalls@LB_ARBITRATOR@@AEAAXXZ; LB_ARBITRATOR::UnmarkAllAbandonedPendingCalls(void)
0x1800210dd  xor     edx, edx; int
0x1800210df  call    ?GetNumberOfPendingCalls@LB_ARBITRATOR@@AEAAKH@Z; LB_ARBITRATOR::GetNumberOfPendingCalls(int)
0x1800210e4  test    eax, eax
  ... truncated ...
```
