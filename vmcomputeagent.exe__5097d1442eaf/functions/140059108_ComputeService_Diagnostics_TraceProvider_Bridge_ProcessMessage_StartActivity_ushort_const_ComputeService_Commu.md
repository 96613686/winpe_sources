# ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage::StartActivity<ushort const * &,ComputeService::Communication::MessageIdentifier const &,ushort const *>(ushort const * &,ComputeService::Communication::MessageIdentifier const &,ushort const * &&)

- ea: `0x140059108`
- end: `0x14005930d`
- name: `??$StartActivity@AEAPEBGAEBW4MessageIdentifier@Communication@ComputeService@@PEBG@Bridge_ProcessMessage@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAPEBGAEBW4MessageIdentifier@Communication@3@$$QEAPEBG@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400594dc`

## callees

- `0x1400016ec`
- `0x140005360`
- `0x14000aeec`
- `0x140031be8`
- `0x140033d28`
- `0x140059108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400591a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400591a3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140059184`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140059184`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400591ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400591ea`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage::StartActivity<unsigned short const * &,enum ComputeService::Communication::MessageIdentifier const &,unsigned short const *>(
        __int64 a1,
        const WCHAR **a2,
        unsigned int *a3,
        const WCHAR **a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdx
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // rbx
  const WCHAR *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  const GUID *v17; // r9
  __int64 v18; // rax
  int v19; // edx
  __int64 v20; // rcx
  int v21; // ecx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-89h] BYREF
  __int64 v23; // [rsp+38h] [rbp-81h] BYREF
  __int64 v24; // [rsp+40h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-49h]
  __int64 v27; // [rsp+78h] [rbp-41h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-39h]
  __int64 v29; // [rsp+88h] [rbp-31h]
  const WCHAR *v30; // [rsp+90h] [rbp-29h]
  int v31; // [rsp+98h] [rbp-21h]
  int v32; // [rsp+9Ch] [rbp-1Dh]
  __int64 *v33; // [rsp+A0h] [rbp-19h]
  __int64 v34; // [rsp+A8h] [rbp-11h]
  const WCHAR *v35; // [rsp+B0h] [rbp-9h]
  int v36; // [rsp+B8h] [rbp-1h]
  int v37; // [rsp+BCh] [rbp+3h]

  SRWLock = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v9 > 5u && (*(_QWORD *)(v9 + 16) & 4) != 0 && (*(_QWORD *)(v9 + 24) & 4LL) == *(_QWORD *)(v9 + 24) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  v10 = SRWLock;
  *(_DWORD *)v8 = 1;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v12 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v12 > 5u && (*(_QWORD *)(v12 + 16) & 4) != 0 && (*(_QWORD *)(v12 + 24) & 4LL) == *(_QWORD *)(v12 + 24) )
  {
    v13 = *a4;
    v14 = *a2;
    v23 = *a3;
    CurrentThreadId = GetCurrentThreadId();
    v16 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v24 = 0;
    if ( !*(_BYTE *)(v16 + 4)
      || (v17 = (const GUID *)(v16 + 24), !*(_DWORD *)(v16 + 24))
      && !*(_DWORD *)(v16 + 28)
      && !*(_DWORD *)(v16 + 32)
      && !*(_DWORD *)(v16 + 36) )
    {
      v17 = 0;
    }
    v18 = -1;
    v19 = 2;
    if ( v13 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v13[v20] );
      v21 = 2 * v20 + 2;
    }
    else
    {
      v13 = &szPassword;
      v21 = 2;
    }
    v36 = v21;
    v33 = &v23;
    v35 = v13;
    v37 = 0;
    v34 = 8;
    if ( v14 )
    {
      do
        ++v18;
      while ( v14[v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v14 = &szPassword;
    }
    v31 = v19;
    p_SRWLock = &SRWLock;
    v30 = v14;
    v26 = &v24;
    v32 = 0;
    v29 = 4;
    v27 = 8;
    tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)&byte_140134F21, (const GUID *)(v16 + 8), v17, 7u, &v25);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v11);
}

```

## disassembly

```asm
0x140059108  push    rbp
0x14005910a  push    rbx
0x14005910b  push    rsi
0x14005910c  push    rdi
0x14005910d  push    r12
0x14005910f  push    r13
0x140059111  push    r14
0x140059113  push    r15
0x140059115  lea     rbp, [rsp-1Fh]
0x14005911a  sub     rsp, 0D8h
0x140059121  mov     rax, cs:__security_cookie
0x140059128  xor     rax, rsp
0x14005912b  mov     [rbp+57h+var_50], rax
0x14005912f  mov     r15, rdx
0x140059132  xor     r12d, r12d
0x140059135  lea     rdx, [rsp+110h+SRWLock]
0x14005913a  mov     [rsp+110h+SRWLock], r12
0x14005913f  mov     rdi, r9
0x140059142  mov     r14, r8
0x140059145  mov     r13, rcx
0x140059148  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005914d  mov     rbx, [r13+110h]
0x140059154  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140059159  mov     rdx, [rax+8]
0x14005915d  mov     eax, [rdx]
0x14005915f  cmp     eax, 5
0x140059162  jbe     short loc_14005918C
0x140059164  mov     rcx, [rdx+18h]
0x140059168  mov     rax, [rdx+10h]
0x14005916c  test    al, 4
0x14005916e  jz      short loc_14005918C
0x140059170  mov     rax, rcx
0x140059173  and     eax, 4
0x140059176  cmp     rax, rcx
0x140059179  jnz     short loc_14005918C
0x14005917b  lea     rdx, [rbx+8]; ActivityId
0x14005917f  lea     ecx, [r12+3]; ControlCode
0x140059184  call    cs:__imp_EventActivityIdControl
0x14005918a  jmp     short loc_140059193
0x14005918c  xorps   xmm0, xmm0
0x14005918f  movups  xmmword ptr [rbx+8], xmm0
0x140059193  mov     rcx, [rsp+110h+SRWLock]; SRWLock
0x140059198  mov     dword ptr [rbx], 1
0x14005919e  test    rcx, rcx
0x1400591a1  jz      short loc_1400591A9
0x1400591a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400591a9  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400591ae  mov     rsi, [rax+8]
0x1400591b2  mov     eax, [rsi]
0x1400591b4  cmp     eax, 5
0x1400591b7  jbe     loc_1400592DB
0x1400591bd  mov     rcx, [rsi+18h]
0x1400591c1  mov     rax, [rsi+10h]
0x1400591c5  test    al, 4
0x1400591c7  jz      loc_1400592DB
0x1400591cd  mov     rax, rcx
0x1400591d0  and     eax, 4
0x1400591d3  cmp     rax, rcx
0x1400591d6  jnz     loc_1400592DB
0x1400591dc  mov     eax, [r14]
0x1400591df  mov     rbx, [rdi]
0x1400591e2  mov     rdi, [r15]
0x1400591e5  mov     [rsp+110h+var_D8], rax
0x1400591ea  call    cs:__imp_GetCurrentThreadId
0x1400591f0  mov     r8, [r13+110h]
0x1400591f7  mov     dword ptr [rsp+110h+SRWLock], eax
0x1400591fb  mov     [rbp+57h+var_D0], r12
0x1400591ff  cmp     [r8+4], r12b
0x140059203  jz      short loc_140059220
0x140059205  lea     r9, [r8+18h]
0x140059209  cmp     [r9], r12d
0x14005920c  jnz     short loc_140059223
0x14005920e  cmp     [r9+4], r12d
0x140059212  jnz     short loc_140059223
0x140059214  cmp     [r9+8], r12d
0x140059218  jnz     short loc_140059223
0x14005921a  cmp     [r9+0Ch], r12d
0x14005921e  jnz     short loc_140059223
0x140059220  mov     r9, r12; int
0x140059223  or      rax, 0FFFFFFFFFFFFFFFFh
0x140059227  mov     edx, 2
0x14005922c  test    rbx, rbx
0x14005922f  jz      short loc_140059247
0x140059231  mov     rcx, rax
0x140059234  inc     rcx
0x140059237  cmp     [rbx+rcx*2], r12w
0x14005923c  jnz     short loc_140059234
0x14005923e  lea     ecx, ds:2[rcx*2]
0x140059245  jmp     short loc_140059250
0x140059247  lea     rbx, szPassword
0x14005924e  mov     ecx, edx
0x140059250  mov     [rbp+57h+var_58], ecx
0x140059253  lea     rcx, [rsp+110h+var_D8]
0x140059258  mov     [rbp+57h+var_70], rcx
0x14005925c  mov     [rbp+57h+var_60], rbx
0x140059260  mov     [rbp+57h+var_54], r12d
0x140059264  mov     [rbp+57h+var_68], 8
0x14005926c  test    rdi, rdi
0x14005926f  jz      short loc_140059284
0x140059271  inc     rax
0x140059274  cmp     [rdi+rax*2], r12w
0x140059279  jnz     short loc_140059271
0x14005927b  lea     edx, ds:2[rax*2]
0x140059282  jmp     short loc_14005928B
0x140059284  lea     rdi, szPassword
0x14005928b  lea     rax, [rsp+110h+SRWLock]
0x140059290  mov     [rbp+57h+var_78], edx
0x140059293  mov     [rbp+57h+var_90], rax
0x140059297  lea     rdx, byte_140134F21; int
0x14005929e  lea     rax, [rbp+57h+var_D0]
0x1400592a2  mov     [rbp+57h+var_80], rdi
0x1400592a6  mov     [rbp+57h+var_A0], rax
0x1400592aa  add     r8, 8; int
0x1400592ae  lea     rax, [rbp+57h+var_C0]
0x1400592b2  mov     [rbp+57h+var_74], r12d
0x1400592b6  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x1400592bb  mov     rcx, rsi; int
0x1400592be  mov     [rsp+110h+var_F0], 7; ULONG
0x1400592c6  mov     [rbp+57h+var_88], 4
0x1400592ce  mov     [rbp+57h+var_98], 8
0x1400592d6  call    _tlgWriteTransfer_EventWriteTransfer
0x1400592db  lea     rcx, [r13+120h]; this
0x1400592e2  cmp     [rcx+18h], r12d
0x1400592e6  jnz     short loc_1400592ED
0x1400592e8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1400592ed  mov     rcx, [rbp+57h+var_50]
0x1400592f1  xor     rcx, rsp; StackCookie
0x1400592f4  call    __security_check_cookie
0x1400592f9  add     rsp, 0D8h
0x140059300  pop     r15
0x140059302  pop     r14
0x140059304  pop     r13
0x140059306  pop     r12
0x140059308  pop     rdi
0x140059309  pop     rsi
0x14005930a  pop     rbx
0x14005930b  pop     rbp
0x14005930c  retn
```
