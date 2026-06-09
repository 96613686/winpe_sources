# _WwanTxmDeinitInternal(WWAN_TXM *)

- ea: `0x18001e3d0`
- end: `0x18001e53a`
- name: `?_WwanTxmDeinitInternal@@YAXPEAUWWAN_TXM@@@Z`
- size: `362`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ce84`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x18001bfe4`
- `0x18001c9e8`
- `0x18001e3d0`
- `0x18001e558`
- `0x180085a50`
- `0x1800b6ac0`
- `0x1800c5d28`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e3f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e3f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e533`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e4fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e4fd`

## string_xrefs

- `0x18001e464`: `We are destroying a WWAN_TXM which was not in the global list. Either WWAN_TXM initialization failed or we are about to double-delete a WWAN_TXM`
- `0x18001e4d8`: `txRspTimer.DeleteTimer: handle=(0x%p)`
- `0x18001e50b`: `TXM Deinitialization Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _WwanTxmDeinitInternal(LPCRITICAL_SECTION lpCriticalSection)
{
  char *i; // r8
  const struct _GUID *p_LockCount; // rsi
  unsigned __int64 v4; // rax
  __int64 DispatchTable; // rax

  EnterCriticalSection(&g_TXMLock);
  if ( lpCriticalSection )
  {
    for ( i = (char *)g_Txm; i != (char *)xmmword_180153A38; i += 8 )
    {
      p_LockCount = (const struct _GUID *)&lpCriticalSection[2].LockCount;
      v4 = *(_QWORD *)(*(_QWORD *)i + 88LL) - *(_QWORD *)&lpCriticalSection[2].LockCount;
      if ( !v4 )
        v4 = *(_QWORD *)(*(_QWORD *)i + 96LL) - (unsigned __int64)lpCriticalSection[2].OwningThread;
      if ( !v4 )
      {
        std::_Move_unchecked<WWAN_TXM * *,WWAN_TXM * *>(i + 8, xmmword_180153A38, i);
        *(_QWORD *)&xmmword_180153A38 = xmmword_180153A38 - 8;
        goto LABEL_11;
      }
    }
    WwanLog::Warning(
      "_WwanTxmDeinitInternal",
      0,
      L"We are destroying a WWAN_TXM which was not in the global list. Either WWAN_TXM initialization failed or we are abo"
       "ut to double-delete a WWAN_TXM");
    p_LockCount = (const struct _GUID *)&lpCriticalSection[2].LockCount;
LABEL_11:
    if ( lpCriticalSection[2].SpinCount )
    {
      DispatchTable = GetDispatchTable(LODWORD(lpCriticalSection[2].LockSemaphore));
      if ( DispatchTable )
      {
        (*(void (__fastcall **)(ULONG_PTR))(DispatchTable + 8))(lpCriticalSection[2].SpinCount);
        lpCriticalSection[2].SpinCount = 0;
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        WwanLog::Error("_WwanTxmDeinitInternal", 0, L"GetDispatchTable returned nullptr - leaking pDimCtxt");
      }
    }
    destroyList(&lpCriticalSection[1].SpinCount);
    destroyList(&lpCriticalSection[1].OwningThread);
    WwanLog::Info(
      "_WwanTxmDeinitInternal",
      p_LockCount,
      L"txRspTimer.DeleteTimer: handle=(0x%p)",
      lpCriticalSection[3].DebugInfo);
    WwanTimerWrapper::DeleteTimer((WwanTimerWrapper *)&lpCriticalSection[3].LockCount);
    DeleteCriticalSection(lpCriticalSection);
    WwanMemFree(lpCriticalSection);
    WwanLog::Info("_WwanTxmDeinitInternal", 0, L"TXM Deinitialization Completed");
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    WwanLog::Error(
      "_WwanTxmDeinitInternal",
      0,
      L"pTxm is nullptr - The destructor for ref-counted WWAN_TXM object is being run with a nullptr object");
  }
  LeaveCriticalSection(&g_TXMLock);
}

```

## disassembly

```asm
0x18001e3d0  mov     [rsp+arg_8], rbx
0x18001e3d5  mov     [rsp+arg_10], rbp
0x18001e3da  push    rsi
0x18001e3db  sub     rsp, 20h
0x18001e3df  mov     rbx, rcx
0x18001e3e2  lea     rbp, ?g_TXMLock@@3VLock@@A; Lock g_TXMLock
0x18001e3e9  mov     [rsp+28h+arg_0], rbp
0x18001e3ee  mov     rcx, rbp; lpCriticalSection
0x18001e3f1  call    cs:__imp_EnterCriticalSection
0x18001e3f7  nop
0x18001e3f8  test    rbx, rbx
0x18001e3fb  jnz     short loc_18001E41C
0x18001e3fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e402  lea     r8, aPtxmIsNullptrT; "pTxm is nullptr - The destructor for re"...
0x18001e409  xor     edx, edx; struct _GUID *
0x18001e40b  lea     rcx, aWwantxmdeiniti; "_WwanTxmDeinitInternal"
0x18001e412  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001e417  jmp     loc_18001E521
0x18001e41c  mov     r8, cs:?g_Txm@@3V?$vector@PEAUWWAN_TXM@@V?$allocator@PEAUWWAN_TXM@@@std@@@std@@A; std::vector<WWAN_TXM *> g_Txm
0x18001e423  mov     rdx, qword ptr cs:xmmword_180153A38
0x18001e42a  cmp     r8, rdx
0x18001e42d  jz      short loc_18001E464
0x18001e42f  lea     rsi, [rbx+58h]
0x18001e433  mov     rcx, [r8]
0x18001e436  mov     rax, [rcx+58h]
0x18001e43a  sub     rax, [rsi]
0x18001e43d  jnz     short loc_18001E447
0x18001e43f  mov     rax, [rcx+60h]
0x18001e443  sub     rax, [rsi+8]
0x18001e447  lea     rcx, [r8+8]; Src
0x18001e44b  test    rax, rax
0x18001e44e  jz      short loc_18001E455
0x18001e450  mov     r8, rcx
0x18001e453  jmp     short loc_18001E42A
0x18001e455  call    ??$_Move_unchecked@PEAPEAUWWAN_TXM@@PEAPEAU1@@std@@YAPEAPEAUWWAN_TXM@@PEAPEAU1@00@Z; std::_Move_unchecked<WWAN_TXM * *,WWAN_TXM * *>(WWAN_TXM * *,WWAN_TXM * *,WWAN_TXM * *)
0x18001e45a  sub     qword ptr cs:xmmword_180153A38, 8
0x18001e462  jmp     short loc_18001E47D
0x18001e464  lea     r8, aWeAreDestroyin; "We are destroying a WWAN_TXM which was "...
0x18001e46b  xor     edx, edx; struct _GUID *
0x18001e46d  lea     rcx, aWwantxmdeiniti; "_WwanTxmDeinitInternal"
0x18001e474  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x18001e479  lea     rsi, [rbx+58h]
0x18001e47d  cmp     qword ptr [rbx+70h], 0
0x18001e482  jz      short loc_18001E4C2
0x18001e484  mov     ecx, [rbx+68h]
0x18001e487  call    ?GetDispatchTable@@YAPEAU_DIM_FUNCTION_DISPATCH@@W4_WWAN_DIM_TYPE@@@Z; GetDispatchTable(_WWAN_DIM_TYPE)
0x18001e48c  test    rax, rax
0x18001e48f  jnz     short loc_18001E4AD
0x18001e491  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e496  lea     r8, aGetdispatchtab; "GetDispatchTable returned nullptr - lea"...
0x18001e49d  xor     edx, edx; struct _GUID *
0x18001e49f  lea     rcx, aWwantxmdeiniti; "_WwanTxmDeinitInternal"
0x18001e4a6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001e4ab  jmp     short loc_18001E4C2
0x18001e4ad  mov     rcx, [rbx+70h]
0x18001e4b1  mov     rax, [rax+8]
0x18001e4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ba  mov     qword ptr [rbx+70h], 0
0x18001e4c2  lea     rcx, [rbx+48h]
0x18001e4c6  call    _destroyList
0x18001e4cb  lea     rcx, [rbx+38h]
0x18001e4cf  call    _destroyList
0x18001e4d4  mov     r9, [rbx+78h]
0x18001e4d8  lea     r8, aTxrsptimerDele; "txRspTimer.DeleteTimer: handle=(0x%p)"
0x18001e4df  mov     rdx, rsi; struct _GUID *
0x18001e4e2  lea     rcx, aWwantxmdeiniti; "_WwanTxmDeinitInternal"
0x18001e4e9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001e4ee  lea     rcx, [rbx+80h]; this
0x18001e4f5  call    ?DeleteTimer@WwanTimerWrapper@@QEAAXXZ; WwanTimerWrapper::DeleteTimer(void)
0x18001e4fa  mov     rcx, rbx; lpCriticalSection
0x18001e4fd  call    cs:__imp_DeleteCriticalSection
0x18001e503  mov     rcx, rbx
0x18001e506  call    WwanMemFree
0x18001e50b  lea     r8, aTxmDeinitializ; "TXM Deinitialization Completed"
0x18001e512  xor     edx, edx; struct _GUID *
0x18001e514  lea     rcx, aWwantxmdeiniti; "_WwanTxmDeinitInternal"
0x18001e51b  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001e520  nop
0x18001e521  mov     rcx, rbp
0x18001e524  mov     rbx, [rsp+28h+arg_8]
0x18001e529  mov     rbp, [rsp+28h+arg_10]
0x18001e52e  add     rsp, 20h
0x18001e532  pop     rsi
0x18001e533  jmp     cs:__imp_LeaveCriticalSection
```
