# WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWorkWithResults_unsigned_long__PdcManager::PdcHandler::NotifyRrasAdaptersGoingToDx_::_3_::_lambda_1___

- ea: `0x180008aac`
- end: `0x180008c25`
- name: `WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWorkWithResults_unsigned_long__PdcManager::PdcHandler::NotifyRrasAdaptersGoingToDx_::_3_::_lambda_1___`
- size: `377`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053a54`

## callees

- `0x180008aac`
- `0x180008c2c`
- `0x180008d38`
- `0x180008db0`
- `0x180010080`
- `0x180085bc4`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008afc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008afc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bea`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008bf9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008bf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWorkWithResults_unsigned_long__PdcManager::PdcHandler::NotifyRrasAdaptersGoingToDx_::_3_::_lambda_1___(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *a2)
{
  __int64 *v4; // rax
  __int64 v5; // r14
  __int64 v6; // rsi
  __int64 v7; // r12
  _QWORD *v8; // rcx
  _QWORD v10[6]; // [rsp+40h] [rbp-19h] BYREF
  __int64 (__fastcall **v11)(); // [rsp+70h] [rbp+17h]
  char *v12; // [rsp+78h] [rbp+1Fh]
  _BYTE v13[8]; // [rsp+80h] [rbp+27h] BYREF
  std::_Ref_count_base *v14; // [rsp+88h] [rbp+2Fh]

  if ( (unsigned __int8)WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady() )
  {
    *a2 = 0;
    a2[1] = 0;
    return a2;
  }
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[5].OwningThread) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return a2;
  }
  v4 = (__int64 *)std::make_shared_WcmCommon::ThreadPoolWaitableResult_unsigned_long___PdcManager::PdcHandler::NotifyRrasAdaptersGoingToDx_::_3_::_lambda_1___(v13);
  v5 = *v4;
  v6 = v4[1];
  *v4 = 0;
  v4[1] = 0;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  v7 = *(_QWORD *)&lpCriticalSection[5].LockCount;
  memset_0(v10, 0, 0x40u);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v10[0] = v5;
  v10[1] = v6;
  v11 = std::_Any_small_RTTI_obj<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>;
  v12 = (char *)&std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor' + 2;
  std::any::operator=((std::any *)&lpCriticalSection[3].SpinCount);
  if ( ((unsigned __int8)v12 & 3) == 1 )
  {
    v8 = (_QWORD *)v10[5];
    goto LABEL_14;
  }
  if ( ((unsigned __int8)v12 & 3) == 2 )
  {
    v8 = v10;
LABEL_14:
    ((void (__fastcall *)(_QWORD *))*v11)(v8);
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( !v7 )
    SubmitThreadpoolWork((PTP_WORK)lpCriticalSection[3].DebugInfo);
  *a2 = v5;
  a2[1] = v6;
  return a2;
}

```

## disassembly

```asm
0x180008aac  mov     [rsp-8+arg_10], rbx
0x180008ab1  mov     [rsp-8+arg_18], rsi
0x180008ab6  push    rbp
0x180008ab7  push    rdi
0x180008ab8  push    r12
0x180008aba  push    r14
0x180008abc  push    r15
0x180008abe  lea     rbp, [rsp-37h]
0x180008ac3  sub     rsp, 90h
0x180008aca  mov     rbx, rdx
0x180008acd  mov     rdi, rcx
0x180008ad0  mov     [rbp+57h+var_88], rdx
0x180008ad4  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady(void)
0x180008ad9  test    al, al
0x180008adb  jz      short loc_180008AF1
0x180008add  mov     qword ptr [rbx], 0
0x180008ae4  mov     qword ptr [rbx+8], 0
0x180008aec  jmp     loc_180008C06
0x180008af1  xorps   xmm1, xmm1
0x180008af4  movdqu  [rbp+57h+var_80], xmm1
0x180008af9  mov     rcx, rdi; lpCriticalSection
0x180008afc  call    cs:__imp_EnterCriticalSection
0x180008b02  mov     [rbp+57h+var_88], rdi
0x180008b06  lea     r15, [rdi+98h]
0x180008b0d  cmp     byte ptr [r15+40h], 0
0x180008b12  jz      short loc_180008B3A
0x180008b14  mov     qword ptr [rbx], 0
0x180008b1b  mov     qword ptr [rbx+8], 0
0x180008b23  test    rdi, rdi
0x180008b26  jz      loc_180008C06
0x180008b2c  mov     rcx, rdi; lpCriticalSection
0x180008b2f  call    cs:__imp_LeaveCriticalSection
0x180008b35  jmp     loc_180008C06
0x180008b3a  lea     rcx, [rbp+57h+var_30]
0x180008b3e  call    std__make_shared_WcmCommon__ThreadPoolWaitableResult_unsigned_long___PdcManager__PdcHandler__NotifyRrasAdaptersGoingToDx____3____lambda_1___
0x180008b43  mov     r14, [rax]
0x180008b46  mov     rsi, [rax+8]
0x180008b4a  mov     qword ptr [rax], 0
0x180008b51  mov     qword ptr [rax+8], 0
0x180008b59  mov     qword ptr [rbp+57h+var_80], r14
0x180008b5d  mov     qword ptr [rbp+57h+var_80+8], rsi
0x180008b61  mov     rcx, [rbp+57h+var_28]; this
0x180008b65  test    rcx, rcx
0x180008b68  jz      short loc_180008B6F
0x180008b6a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008b6f  mov     r12, [rdi+0D0h]
0x180008b76  xor     edx, edx; Val
0x180008b78  lea     r8d, [rdx+40h]; Size
0x180008b7c  lea     rcx, [rbp+57h+var_70]; void *
0x180008b80  call    memset_0
0x180008b85  test    rsi, rsi
0x180008b88  jz      short loc_180008B8E
0x180008b8a  lock inc dword ptr [rsi+8]
0x180008b8e  mov     [rbp+57h+var_70], r14
0x180008b92  mov     [rbp+57h+var_68], rsi
0x180008b96  lea     rax, ??$_Any_small_RTTI_obj@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@std@@3U_Any_small_RTTI@1@B; _Any_small_RTTI::_Any_small_RTTI const std::_Any_small_RTTI_obj<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>
0x180008b9d  mov     [rbp+57h+var_40], rax
0x180008ba1  lea     rax, ??_R0?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@8; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor'
0x180008ba8  or      rax, 2
0x180008bac  mov     [rbp+57h+var_38], rax
0x180008bb0  lea     rdx, [rbp+57h+var_70]
0x180008bb4  mov     rcx, r15; this
0x180008bb7  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180008bbc  nop
0x180008bbd  mov     rax, [rbp+57h+var_38]
0x180008bc1  and     eax, 3
0x180008bc4  sub     rax, 1
0x180008bc8  jz      short loc_180008BD6
0x180008bca  cmp     rax, 1
0x180008bce  jnz     short loc_180008BE7
0x180008bd0  lea     rcx, [rbp+57h+var_70]
0x180008bd4  jmp     short loc_180008BDA
0x180008bd6  mov     rcx, [rbp+57h+var_48]
0x180008bda  mov     rax, [rbp+57h+var_40]
0x180008bde  mov     rax, [rax]
0x180008be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be6  nop
0x180008be7  mov     rcx, rdi; lpCriticalSection
0x180008bea  call    cs:__imp_LeaveCriticalSection
0x180008bf0  test    r12, r12
0x180008bf3  jnz     short loc_180008BFF
0x180008bf5  mov     rcx, [rdi+78h]; pwk
0x180008bf9  call    cs:__imp_SubmitThreadpoolWork
0x180008bff  mov     [rbx], r14
0x180008c02  mov     [rbx+8], rsi
0x180008c06  mov     rax, rbx
0x180008c09  lea     r11, [rsp+0B0h+var_20]
0x180008c11  mov     rbx, [r11+40h]
0x180008c15  mov     rsi, [r11+48h]
0x180008c19  mov     rsp, r11
0x180008c1c  pop     r15
0x180008c1e  pop     r14
0x180008c20  pop     r12
0x180008c22  pop     rdi
0x180008c23  pop     rbp
0x180008c24  retn
```
