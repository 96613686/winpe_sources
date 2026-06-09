# ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi::StartActivity(char const *,void *)

- ea: `0x180020a94`
- end: `0x180020c69`
- name: `?StartActivity@HcsClientApi@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXPEBDPEAX@Z`
- size: `469`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi *__hidden this, const char *, void *)`
- caller_count: `31`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800252f0`
- `0x1800253d0`
- `0x180025510`
- `0x180025750`
- `0x180025950`
- `0x180025d00`
- `0x180025f00`
- `0x180026180`
- `0x1800263d0`
- `0x180026640`
- `0x1800268a0`
- `0x180026ad0`
- `0x180026e20`
- `0x180026fb0`
- `0x1800270f0`
- `0x180027370`
- `0x180027560`
- `0x180027740`
- `0x180027920`
- `0x180027b10`
- `0x180027d00`
- `0x180027f40`
- `0x180028260`
- `0x180028450`
- `0x180028520`
- `0x180028790`
- `0x180028920`
- `0x180037800`
- `0x180037970`
- `0x180037a40`
- `0x180037b60`

## callees

- `0x180001700`
- `0x180002f50`
- `0x18000a41c`
- `0x18001c384`
- `0x180020a94`
- `0x180020fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020b37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020b7b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020b12`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020b12`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi::StartActivity(
        ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi *this,
        const char *a2,
        void *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rcx
  int v9; // edi
  __int64 v10; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-79h] BYREF
  void *v16; // [rsp+38h] [rbp-71h] BYREF
  __int64 v17; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v19; // [rsp+70h] [rbp-39h]
  __int64 v20; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v22; // [rsp+88h] [rbp-21h]
  const char *v23; // [rsp+90h] [rbp-19h]
  int v24; // [rsp+98h] [rbp-11h]
  int v25; // [rsp+9Ch] [rbp-Dh]
  void **v26; // [rsp+A0h] [rbp-9h]
  __int64 v27; // [rsp+A8h] [rbp-1h]

  SRWLock = 0;
  wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 4u
    && (*(_QWORD *)(v7 + 16) & 0x20000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x20000LL) == *(_QWORD *)(v7 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  v9 = 1;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v10 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v10 > 4u
    && (*(_QWORD *)(v10 + 16) & 0x20000LL) != 0
    && (*(_QWORD *)(v10 + 24) & 0x20000LL) == *(_QWORD *)(v10 + 24) )
  {
    v16 = a3;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v12 + 4)
      || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
      && !*(_DWORD *)(v12 + 28)
      && !*(_DWORD *)(v12 + 32)
      && !*(_DWORD *)(v12 + 36) )
    {
      v13 = 0;
    }
    v27 = 8;
    v26 = &v16;
    if ( a2 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      v9 = v14 + 1;
    }
    else
    {
      a2 = (const char *)&byte_18008E1AD;
    }
    v23 = a2;
    p_SRWLock = &SRWLock;
    v24 = v9;
    v19 = &v17;
    v25 = 0;
    v22 = 4;
    v20 = 8;
    tlgWriteTransfer_EventWriteTransfer(v10, (int)&qword_18009D0D0, v12 + 8, v13, 6u, &v18);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi *)((char *)this + 288));
}

```

## disassembly

```asm
0x180020a94  push    rbp
0x180020a96  push    rbx
0x180020a97  push    rsi
0x180020a98  push    rdi
0x180020a99  push    r12
0x180020a9b  push    r13
0x180020a9d  push    r14
0x180020a9f  push    r15
0x180020aa1  lea     rbp, [rsp-1Fh]
0x180020aa6  sub     rsp, 0C8h
0x180020aad  mov     rax, cs:__security_cookie
0x180020ab4  xor     rax, rsp
0x180020ab7  mov     [rbp+57h+var_50], rax
0x180020abb  mov     rsi, rdx
0x180020abe  xor     r12d, r12d
0x180020ac1  lea     rdx, [rbp+57h+SRWLock]
0x180020ac5  mov     [rbp+57h+SRWLock], r12
0x180020ac9  mov     r15, r8
0x180020acc  mov     r14, rcx
0x180020acf  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020ad4  mov     rbx, [r14+110h]
0x180020adb  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180020ae0  mov     r13d, 20000h
0x180020ae6  mov     rdx, [rax+8]
0x180020aea  mov     eax, [rdx]
0x180020aec  cmp     eax, 4
0x180020aef  jbe     short loc_180020B20
0x180020af1  mov     rcx, [rdx+18h]
0x180020af5  mov     rax, [rdx+10h]
0x180020af9  test    r13, rax
0x180020afc  jz      short loc_180020B20
0x180020afe  mov     rax, rcx
0x180020b01  and     rax, r13
0x180020b04  cmp     rax, rcx
0x180020b07  jnz     short loc_180020B20
0x180020b09  lea     rdx, [rbx+8]; ActivityId
0x180020b0d  lea     ecx, [r12+3]; ControlCode
0x180020b12  call    cs:__imp_EventActivityIdControl
0x180020b19  nop     dword ptr [rax+rax+00h]
0x180020b1e  jmp     short loc_180020B27
0x180020b20  xorps   xmm0, xmm0
0x180020b23  movups  xmmword ptr [rbx+8], xmm0
0x180020b27  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180020b2b  mov     edi, 1
0x180020b30  mov     [rbx], edi
0x180020b32  test    rcx, rcx
0x180020b35  jz      short loc_180020B43
0x180020b37  call    cs:__imp_ReleaseSRWLockExclusive
0x180020b3e  nop     dword ptr [rax+rax+00h]
0x180020b43  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180020b48  mov     rbx, [rax+8]
0x180020b4c  mov     eax, [rbx]
0x180020b4e  cmp     eax, 4
0x180020b51  jbe     loc_180020C36
0x180020b57  mov     rcx, [rbx+18h]
0x180020b5b  mov     rax, [rbx+10h]
0x180020b5f  test    r13, rax
0x180020b62  jz      loc_180020C36
0x180020b68  mov     rax, rcx
0x180020b6b  and     rax, r13
0x180020b6e  cmp     rax, rcx
0x180020b71  jnz     loc_180020C36
0x180020b77  mov     [rbp+57h+var_C8], r15
0x180020b7b  call    cs:__imp_GetCurrentThreadId
0x180020b82  nop     dword ptr [rax+rax+00h]
0x180020b87  mov     r8, [r14+110h]
0x180020b8e  mov     dword ptr [rbp+57h+SRWLock], eax
0x180020b91  mov     [rbp+57h+var_C0], r12
0x180020b95  cmp     [r8+4], r12b
0x180020b99  jz      short loc_180020BB6
0x180020b9b  lea     r9, [r8+18h]
0x180020b9f  cmp     [r9], r12d
0x180020ba2  jnz     short loc_180020BB9
0x180020ba4  cmp     [r9+4], r12d
0x180020ba8  jnz     short loc_180020BB9
0x180020baa  cmp     [r9+8], r12d
0x180020bae  jnz     short loc_180020BB9
0x180020bb0  cmp     [r9+0Ch], r12d
0x180020bb4  jnz     short loc_180020BB9
0x180020bb6  mov     r9, r12; int
0x180020bb9  mov     [rbp+57h+var_58], 8
0x180020bc1  lea     rax, [rbp+57h+var_C8]
0x180020bc5  mov     [rbp+57h+var_60], rax
0x180020bc9  test    rsi, rsi
0x180020bcc  jz      short loc_180020BE0
0x180020bce  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020bd2  inc     rax
0x180020bd5  cmp     [rsi+rax], r12b
0x180020bd9  jnz     short loc_180020BD2
0x180020bdb  lea     edi, [rax+1]
0x180020bde  jmp     short loc_180020BE7
0x180020be0  lea     rsi, byte_18008E1AD
0x180020be7  lea     rax, [rbp+57h+SRWLock]
0x180020beb  mov     [rbp+57h+var_70], rsi
0x180020bef  mov     [rbp+57h+var_80], rax
0x180020bf3  lea     rdx, qword_18009D0D0; int
0x180020bfa  lea     rax, [rbp+57h+var_C0]
0x180020bfe  mov     [rbp+57h+var_68], edi
0x180020c01  mov     [rbp+57h+var_90], rax
0x180020c05  add     r8, 8; int
0x180020c09  lea     rax, [rbp+57h+var_B0]
0x180020c0d  mov     [rbp+57h+var_64], r12d
0x180020c11  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x180020c16  mov     rcx, rbx; int
0x180020c19  mov     [rsp+100h+var_E0], 6; ULONG
0x180020c21  mov     [rbp+57h+var_78], 4
0x180020c29  mov     [rbp+57h+var_88], 8
0x180020c31  call    _tlgWriteTransfer_EventWriteTransfer
0x180020c36  lea     rcx, [r14+120h]; this
0x180020c3d  cmp     [rcx+18h], r12d
0x180020c41  jnz     short loc_180020C48
0x180020c43  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180020c48  mov     rcx, [rbp+57h+var_50]
0x180020c4c  xor     rcx, rsp; StackCookie
0x180020c4f  call    __security_check_cookie
0x180020c54  add     rsp, 0C8h
0x180020c5b  pop     r15
0x180020c5d  pop     r14
0x180020c5f  pop     r13
0x180020c61  pop     r12
0x180020c63  pop     rdi
0x180020c64  pop     rsi
0x180020c65  pop     rbx
0x180020c66  pop     rbp
0x180020c67  retn
```
