# TraceLog::Providers::Reliability::NamedCallContextActivity::StartActivity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400177f4`
- end: `0x140017976`
- name: `?StartActivity@NamedCallContextActivity@Reliability@Providers@TraceLog@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012f74`

## callees

- `0x140001e2c`
- `0x140005530`
- `0x140012bd4`
- `0x1400146cc`
- `0x1400177f4`
- `0x140018138`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140017849`
- `ADVAPI32!EventActivityIdControl` at `0x140017849`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001786a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001786a`
- `KERNEL32!GetCurrentThreadId` at `0x14001788d`
- `KERNEL32!GetCurrentThreadId` at `0x14001788d`

## pseudocode

```c
void __fastcall TraceLog::Providers::Reliability::NamedCallContextActivity::StartActivity(__int64 a1, const WCHAR *a2)
{
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // rdx
  const struct _tlgProvider_t *v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  const GUID *v10; // r9
  __int64 v11; // rax
  int v12; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]
  const WCHAR *v20; // [rsp+80h] [rbp+27h]
  int v21; // [rsp+88h] [rbp+2Fh]
  int v22; // [rsp+8Ch] [rbp+33h]

  wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  if ( *(_DWORD *)TraceLog::Providers::Reliability::Provider() <= 4u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  v5 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v7 = TraceLog::Providers::Reliability::Provider();
  if ( *(_DWORD *)v7 > 4u )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v14 = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = (const GUID *)(v9 + 24), !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    if ( a2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      a2 = &SubKey;
      v12 = 2;
    }
    v21 = v12;
    v20 = a2;
    p_SRWLock = &SRWLock;
    v22 = 0;
    v16 = &v14;
    v19 = 4;
    v17 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v7,
      (unsigned __int8 *)word_1400D503A,
      (const GUID *)(v9 + 8),
      v10,
      5u,
      &v15);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v6);
}

```

## disassembly

```asm
0x1400177f4  mov     [rsp-8+arg_8], rbx
0x1400177f9  mov     [rsp-8+arg_10], rsi
0x1400177fe  push    rbp
0x1400177ff  push    rdi
0x140017800  push    r14
0x140017802  lea     rbp, [rsp-47h]
0x140017807  sub     rsp, 0A0h
0x14001780e  mov     rax, cs:__security_cookie
0x140017815  xor     rax, rsp
0x140017818  mov     [rbp+57h+var_20], rax
0x14001781c  mov     rbx, rdx
0x14001781f  mov     rsi, rcx
0x140017822  lea     rdx, [rbp+57h+SRWLock]
0x140017826  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001782b  mov     rdi, [rsi+110h]
0x140017832  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x140017837  mov     r8d, [rax]
0x14001783a  cmp     r8d, 4
0x14001783e  jbe     short loc_140017851
0x140017840  lea     rdx, [rdi+8]; ActivityId
0x140017844  mov     ecx, 3; ControlCode
0x140017849  call    cs:__imp_EventActivityIdControl
0x14001784f  jmp     short loc_140017858
0x140017851  xorps   xmm0, xmm0
0x140017854  movups  xmmword ptr [rdi+8], xmm0
0x140017858  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14001785c  xor     r14d, r14d
0x14001785f  mov     dword ptr [rdi], 1
0x140017865  test    rcx, rcx
0x140017868  jz      short loc_140017870
0x14001786a  call    cs:__imp_ReleaseSRWLockExclusive
0x140017870  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x140017875  mov     rdi, rax
0x140017878  mov     ecx, [rax]
0x14001787a  cmp     ecx, 4
0x14001787d  jbe     loc_140017940
0x140017883  cmp     qword ptr [rbx+18h], 7
0x140017888  jbe     short loc_14001788D
0x14001788a  mov     rbx, [rbx]
0x14001788d  call    cs:__imp_GetCurrentThreadId
0x140017893  mov     r8, [rsi+110h]
0x14001789a  mov     dword ptr [rbp+57h+SRWLock], eax
0x14001789d  mov     [rbp+57h+var_78], 1000000h
0x1400178a5  cmp     [r8+4], r14b
0x1400178a9  jz      short loc_1400178C6
0x1400178ab  lea     r9, [r8+18h]
0x1400178af  cmp     [r9], r14d
0x1400178b2  jnz     short loc_1400178C9
0x1400178b4  cmp     [r9+4], r14d
0x1400178b8  jnz     short loc_1400178C9
0x1400178ba  cmp     [r9+8], r14d
0x1400178be  jnz     short loc_1400178C9
0x1400178c0  cmp     [r9+0Ch], r14d
0x1400178c4  jnz     short loc_1400178C9
0x1400178c6  mov     r9, r14
0x1400178c9  test    rbx, rbx
0x1400178cc  jz      short loc_1400178E5
0x1400178ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400178d2  inc     rax
0x1400178d5  cmp     [rbx+rax*2], r14w
0x1400178da  jnz     short loc_1400178D2
0x1400178dc  lea     eax, ds:2[rax*2]
0x1400178e3  jmp     short loc_1400178F1
0x1400178e5  lea     rbx, SubKey
0x1400178ec  mov     eax, 2
0x1400178f1  mov     [rbp+57h+var_28], eax
0x1400178f4  lea     rdx, word_1400D503A
0x1400178fb  lea     rax, [rbp+57h+SRWLock]
0x1400178ff  mov     [rbp+57h+var_30], rbx
0x140017903  mov     [rbp+57h+var_40], rax
0x140017907  add     r8, 8
0x14001790b  lea     rax, [rbp+57h+var_78]
0x14001790f  mov     [rbp+57h+var_24], r14d
0x140017913  mov     [rbp+57h+var_50], rax
0x140017917  mov     rcx, rdi
0x14001791a  lea     rax, [rbp+57h+var_70]
0x14001791e  mov     [rbp+57h+var_38], 4
0x140017926  mov     [rsp+0B0h+var_88], rax
0x14001792b  mov     [rsp+0B0h+var_90], 5
0x140017933  mov     [rbp+57h+var_48], 8
0x14001793b  call    _tlgWriteTransfer_EventWriteTransfer
0x140017940  lea     rcx, [rsi+120h]; this
0x140017947  cmp     [rcx+18h], r14d
0x14001794b  jnz     short loc_140017952
0x14001794d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140017952  mov     rcx, [rbp+57h+var_20]
0x140017956  xor     rcx, rsp; StackCookie
0x140017959  call    __security_check_cookie
0x14001795e  lea     r11, [rsp+0B0h+var_10]
0x140017966  mov     rbx, [r11+28h]
0x14001796a  mov     rsi, [r11+30h]
0x14001796e  mov     rsp, r11
0x140017971  pop     r14
0x140017973  pop     rdi
0x140017974  pop     rbp
0x140017975  retn
```
