# DBSession::_ReleaseTransaction(long,int,DB_TRANSACTION_STATE *,int *)

- ea: `0x18005500c`
- end: `0x1800552fa`
- name: `?_ReleaseTransaction@DBSession@@AEAAJJHPEAW4DB_TRANSACTION_STATE@@PEAH@Z`
- size: `750`
- prototype: `__int64 __usercall@<rax>(DBSession *__hidden this@<rcx>, int@<edx>, int@<r8d>, enum DB_TRANSACTION_STATE *@<r9>, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180054fc0`
- `0x1800ac940`

## callees

- `0x1800068f0`
- `0x1800069e8`
- `0x18000f530`
- `0x180011ed0`
- `0x180043bcc`
- `0x18005500c`
- `0x180055300`
- `0x180055328`
- `0x180055500`
- `0x180055588`
- `0x1800737b4`
- `0x180081398`
- `0x1800ad634`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005502c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005502c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800551b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800551b1`
- `ESENT!JetCommitTransaction2` at `0x1800550a4`
- `ESENT!JetCommitTransaction2` at `0x1800550a4`
- `ESENT!JetGetSessionParameter` at `0x1800550f2`
- `ESENT!JetGetSessionParameter` at `0x1800550f2`

## string_xrefs

- `0x180055212`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`

## pseudocode

```c
__int64 __fastcall DBSession::_ReleaseTransaction(DBSession *this, int a2, int a3, struct DBLockManager **a4, int *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // edi
  struct DBLockManager **v12; // r15
  int v13; // eax
  bool v14; // zf
  unsigned __int64 v15; // rcx
  unsigned int v16; // r14d
  BOOL v17; // ebp
  __int64 v18; // rdx
  __int64 v19; // rcx
  int HresultFromJetError; // esi
  __int64 v21; // rcx
  unsigned int v22; // edx
  unsigned __int64 v24; // rcx
  struct DBLockManager *v25; // [rsp+80h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 29) )
  {
    v11 = 0;
    if ( a2 != 1 && *((_DWORD *)this + 29) != a2 )
      Log_AssertionEvent_3(v10, v9, 1941);
    v12 = &v25;
    if ( a4 )
      v12 = a4;
    if ( *((_DWORD *)this + 28) || (v13 = 0, !a3) )
      v13 = 1;
    *((_DWORD *)this + 28) = v13;
    *(_DWORD *)v12 = 1;
    v14 = *((_DWORD *)this + 29) == a2;
    *((_DWORD *)this + 29) -= a2;
    if ( v14 )
    {
      if ( *((_DWORD *)this + 28) )
        DBSession::_InvalidateHandlesInSession(this);
      v15 = *((_QWORD *)this + 27);
      if ( *((_DWORD *)this + 28) )
      {
        v17 = 1;
        v16 = CommsESE_JetRollback(v15, v9);
      }
      else
      {
        v16 = JetCommitTransaction2(v15, 1, 120000, 0);
        CheckCorruption(v16);
        v17 = v16 == 0;
      }
      HresultFromJetError = MakeHresultFromJetError(v16);
      if ( !v16 )
      {
        v21 = *((_QWORD *)this + 27);
        LODWORD(v25) = 0;
        if ( !(unsigned int)JetGetSessionParameter(v21, 4099, &v25, 4, 0) )
        {
          if ( (_DWORD)v25 )
          {
            Log_AssertionEvent_3(v19, v18, 1984);
            __int2c();
          }
        }
      }
      if ( !v17 )
      {
        if ( *((_DWORD *)this + 28) )
          goto LABEL_32;
        if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x200) != 0 )
          McTemplateU0qq_EventWriteTransfer(
            v19,
            UnifiedStore_TransactionCommit_Error,
            (unsigned int)HresultFromJetError,
            *((unsigned int *)this + 54));
        v24 = *((_QWORD *)this + 27);
        v11 = HresultFromJetError;
        *((_DWORD *)this + 28) = 1;
        v16 = CommsESE_JetRollback(v24, v18);
        HresultFromJetError = MakeHresultFromJetError(v16);
        DBSession::_InvalidateHandlesInSession(this);
        v17 = v16 == 0;
        if ( v16 )
        {
LABEL_32:
          Log_AssertionEvent_3(v19, v18, 2004);
          if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x200) != 0 )
            McTemplateU0d_EventWriteTransfer(
              &MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context,
              UnifiedStore_FinalRollbackFailed,
              v16);
        }
      }
      *(_DWORD *)v12 = (*((_DWORD *)this + 28) != 0) + 2;
      DBSession::_PostEndTransaction(this, *((_DWORD *)this + 28) == 0);
      TxnHistory::EndTransaction((TxnHistory *)*((unsigned int *)this + 48), v22);
      if ( v17 && *((_BYTE *)this + 344) )
        DBSession::_TryCleanVersionStore(this);
      *((_BYTE *)this + 344) = 0;
      *((_DWORD *)this + 48) = 0;
      *((_DWORD *)this + 28) = 0;
      *((_QWORD *)this + 15) = 0;
      v25 = 0;
      if ( (int)DBLockManager::GetInstance(&v25) >= 0 )
        (*(void (__fastcall **)(struct DBLockManager *))(*(_QWORD *)v25 + 24LL))(v25);
      *a5 = 1;
      if ( v11 >= 0 && HresultFromJetError < 0 )
        v11 = HresultFromJetError;
    }
    else
    {
      *a5 = 0;
    }
  }
  else
  {
    Log_AssertionEvent_3(v10, v9, 1937);
    v11 = -2147018195;
    Log_UnistoreHREvent_0(
      2147949101LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1938);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005500c  push    rbx
0x18005500e  push    rbp
0x18005500f  push    rsi
0x180055010  push    rdi
0x180055011  push    r12
0x180055013  push    r13
0x180055015  push    r14
0x180055017  push    r15
0x180055019  sub     rsp, 38h
0x18005501d  mov     rbx, rcx
0x180055020  mov     rbp, r9
0x180055023  add     rcx, 40h ; '@'; lpCriticalSection
0x180055027  mov     r14d, r8d
0x18005502a  mov     esi, edx
0x18005502c  call    cs:__imp_EnterCriticalSection
0x180055032  xor     r13d, r13d
0x180055035  cmp     [rbx+74h], r13d
0x180055039  jz      loc_180055202
0x18005503f  mov     edi, r13d
0x180055042  cmp     esi, 1
0x180055045  jnz     loc_180055299
0x18005504b  test    rbp, rbp
0x18005504e  lea     r15, [rsp+78h+arg_0]
0x180055056  cmovnz  r15, rbp
0x18005505a  cmp     [rbx+70h], r13d
0x18005505e  jz      loc_1800551CA
0x180055064  mov     eax, 1
0x180055069  mov     [rbx+70h], eax
0x18005506c  mov     dword ptr [r15], 1
0x180055073  sub     [rbx+74h], esi
0x180055076  jnz     loc_1800551F5
0x18005507c  cmp     [rbx+70h], r13d
0x180055080  jnz     loc_1800552B2
0x180055086  mov     rcx, [rbx+0D8h]; unsigned __int64
0x18005508d  cmp     [rbx+70h], r13d
0x180055091  jnz     loc_1800551E3
0x180055097  xor     r9d, r9d
0x18005509a  mov     r8d, 1D4C0h
0x1800550a0  lea     edx, [r9+1]
0x1800550a4  call    cs:__imp_JetCommitTransaction2
0x1800550aa  mov     ecx, eax; int
0x1800550ac  mov     r14d, eax
0x1800550af  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x1800550b4  test    r14d, r14d
0x1800550b7  mov     ebp, r13d
0x1800550ba  setz    bpl
0x1800550be  mov     ecx, r14d; int
0x1800550c1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800550c6  mov     esi, eax
0x1800550c8  test    r14d, r14d
0x1800550cb  jnz     short loc_180055113
0x1800550cd  mov     rcx, [rbx+0D8h]
0x1800550d4  lea     r9d, [r14+4]
0x1800550d8  lea     r8, [rsp+78h+arg_0]
0x1800550e0  mov     dword ptr [rsp+78h+arg_0], r13d
0x1800550e8  mov     edx, 1003h
0x1800550ed  mov     [rsp+78h+var_58], r13
0x1800550f2  call    cs:__imp_JetGetSessionParameter
0x1800550f8  test    eax, eax
0x1800550fa  jnz     short loc_180055113
0x1800550fc  cmp     dword ptr [rsp+78h+arg_0], r13d
0x180055104  jz      short loc_180055113
0x180055106  mov     r8d, 7C0h
0x18005510c  call    Log_AssertionEvent_3
0x180055111  int     2Ch; Windows NT - assertion failure
0x180055113  test    ebp, ebp
0x180055115  jz      loc_1800552BF
0x18005511b  mov     eax, [rbx+70h]
0x18005511e  mov     edx, r13d
0x180055121  neg     eax
0x180055123  sbb     ecx, ecx
0x180055125  neg     ecx
0x180055127  add     ecx, 2
0x18005512a  mov     [r15], ecx
0x18005512d  mov     rcx, rbx; this
0x180055130  cmp     [rbx+70h], r13d
0x180055134  setz    dl; int
0x180055137  call    ?_PostEndTransaction@DBSession@@AEAAXH@Z; DBSession::_PostEndTransaction(int)
0x18005513c  mov     ecx, [rbx+0C0h]; this
0x180055142  call    ?EndTransaction@TxnHistory@@YAXK@Z; TxnHistory::EndTransaction(ulong)
0x180055147  test    ebp, ebp
0x180055149  jz      short loc_180055158
0x18005514b  cmp     [rbx+158h], r13b
0x180055152  jnz     loc_1800552ED
0x180055158  lea     rcx, [rsp+78h+arg_0]; struct DBLockManager **
0x180055160  mov     [rbx+158h], r13b
0x180055167  mov     [rbx+0C0h], r13d
0x18005516e  mov     [rbx+70h], r13d
0x180055172  mov     [rbx+78h], r13
0x180055176  mov     [rsp+78h+arg_0], r13
0x18005517e  call    ?GetInstance@DBLockManager@@SAJPEAPEAV1@@Z; DBLockManager::GetInstance(DBLockManager * *)
0x180055183  test    eax, eax
0x180055185  js      short loc_18005519B
0x180055187  mov     rcx, [rsp+78h+arg_0]
0x18005518f  mov     rax, [rcx]
0x180055192  mov     rax, [rax+18h]
0x180055196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005519b  mov     rax, [rsp+78h+arg_20]
0x1800551a3  mov     dword ptr [rax], 1
0x1800551a9  test    edi, edi
0x1800551ab  jns     short loc_1800551DB
0x1800551ad  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800551b1  call    cs:__imp_LeaveCriticalSection
0x1800551b7  mov     eax, edi
0x1800551b9  add     rsp, 38h
0x1800551bd  pop     r15
0x1800551bf  pop     r14
0x1800551c1  pop     r13
0x1800551c3  pop     r12
0x1800551c5  pop     rdi
0x1800551c6  pop     rsi
0x1800551c7  pop     rbp
0x1800551c8  pop     rbx
0x1800551c9  retn
0x1800551ca  mov     eax, r13d
0x1800551cd  test    r14d, r14d
0x1800551d0  jnz     loc_180055069
0x1800551d6  jmp     loc_180055064
0x1800551db  test    esi, esi
0x1800551dd  jns     short loc_1800551AD
0x1800551df  mov     edi, esi
0x1800551e1  jmp     short loc_1800551AD
0x1800551e3  mov     ebp, 1
0x1800551e8  call    ?CommsESE_JetRollback@@YAJ_KK@Z; CommsESE_JetRollback(unsigned __int64,ulong)
0x1800551ed  mov     r14d, eax
0x1800551f0  jmp     loc_1800550BE
0x1800551f5  mov     rdx, [rsp+78h+arg_20]
0x1800551fd  mov     [rdx], r13d
0x180055200  jmp     short loc_1800551AD
0x180055202  mov     r8d, 791h
0x180055208  call    Log_AssertionEvent_3
0x18005520d  mov     edi, 80071A2Dh
0x180055212  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180055219  mov     ecx, edi
0x18005521b  mov     r9d, 792h
0x180055221  xor     edx, edx
0x180055223  call    Log_UnistoreHREvent_0
0x180055228  jmp     short loc_1800551AD
0x18005522a  mov     rcx, [rbx+0D8h]; unsigned __int64
0x180055231  mov     edi, esi
0x180055233  mov     dword ptr [rbx+70h], 1
0x18005523a  call    ?CommsESE_JetRollback@@YAJ_KK@Z; CommsESE_JetRollback(unsigned __int64,ulong)
0x18005523f  mov     ecx, eax; int
0x180055241  mov     r14d, eax
0x180055244  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180055249  mov     rcx, rbx; this
0x18005524c  mov     esi, eax
0x18005524e  call    ?_InvalidateHandlesInSession@DBSession@@IEAAXXZ; DBSession::_InvalidateHandlesInSession(void)
0x180055253  test    r14d, r14d
0x180055256  mov     ebp, r13d
0x180055259  setz    bpl
0x18005525d  test    r14d, r14d
0x180055260  jz      loc_18005511B
0x180055266  mov     r8d, 7D4h
0x18005526c  call    Log_AssertionEvent_3
0x180055271  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, 2
0x180055278  jz      loc_18005511B
0x18005527e  mov     r8d, r14d
0x180055281  lea     rdx, UnifiedStore_FinalRollbackFailed
0x180055288  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context
0x18005528f  call    McTemplateU0d_EventWriteTransfer
0x180055294  jmp     loc_18005511B
0x180055299  cmp     [rbx+74h], esi
0x18005529c  jz      loc_18005504B
0x1800552a2  mov     r8d, 795h
0x1800552a8  call    Log_AssertionEvent_3
0x1800552ad  jmp     loc_18005504B
0x1800552b2  mov     rcx, rbx; this
0x1800552b5  call    ?_InvalidateHandlesInSession@DBSession@@IEAAXXZ; DBSession::_InvalidateHandlesInSession(void)
0x1800552ba  jmp     loc_180055086
0x1800552bf  cmp     [rbx+70h], r13d
0x1800552c3  jnz     short loc_180055266
0x1800552c5  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, 2
0x1800552cc  jz      loc_18005522A
0x1800552d2  mov     r9d, [rbx+0D8h]
0x1800552d9  lea     rdx, UnifiedStore_TransactionCommit_Error
0x1800552e0  mov     r8d, esi
0x1800552e3  call    McTemplateU0qq_EventWriteTransfer
0x1800552e8  jmp     loc_18005522A
0x1800552ed  mov     rcx, rbx; this
0x1800552f0  call    ?_TryCleanVersionStore@DBSession@@AEAAXXZ; DBSession::_TryCleanVersionStore(void)
0x1800552f5  jmp     loc_180055158
```
