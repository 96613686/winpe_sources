# HcsClient::OperationTracker::SetClientCallback(HCS_EVENT_OPTIONS,void const *,void (*)(HCS_EVENT *,void *))

- ea: `0x18003eb10`
- end: `0x18003ecc0`
- name: `?SetClientCallback@OperationTracker@HcsClient@@QEAAXW4HCS_EVENT_OPTIONS@@PEBXP6AXPEAUHCS_EVENT@@PEAX@Z@Z`
- size: `432`
- prototype: `void __fastcall(HcsClient::OperationTracker *__hidden this, enum HCS_EVENT_OPTIONS, const void *, void (*)(struct HCS_EVENT *, void *))`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027560`
- `0x180027740`
- `0x180028790`
- `0x180028920`
- `0x180050c5c`

## callees

- `0x1800021a4`
- `0x180002f50`
- `0x18000d108`
- `0x18001ed48`
- `0x180038040`
- `0x180038710`
- `0x18003eb10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ec2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ec2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ec5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ec5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ec47`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ec47`

## string_xrefs

- `0x18003ec96`: `onecore\vm\compute\dll\lib\core\operationtracker.cpp`
- `0x18003ecae`: `onecore\vm\compute\dll\lib\core\operationtracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HcsClient::OperationTracker::SetClientCallback(
        PSRWLOCK *this,
        enum HCS_EVENT_OPTIONS a2,
        RTL_SRWLOCK *a3,
        RTL_SRWLOCK *a4)
{
  bool v8; // al
  _QWORD *v9; // rdi
  const struct _tlgProvider_t *v10; // rax
  PSRWLOCK v11; // rbx
  int v12; // [rsp+20h] [rbp-58h]
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-40h] BYREF
  char v15; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  CallbackManager::Enter(this[13]);
  if ( v15 )
  {
    if ( a4 )
    {
      v8 = this[9] != this[10] && !this[2];
      if ( (a2 & 2) != 0 )
      {
        *((_DWORD *)this + 40) = 2;
      }
      else if ( (a2 & 4) != 0 )
      {
        *((_DWORD *)this + 40) = 3;
      }
    }
    else
    {
      if ( a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\operationtracker.cpp",
          (const char *)0x80070057LL,
          v12);
      if ( a3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AB,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\operationtracker.cpp",
          (const char *)0x80070057LL,
          v12);
      v8 = 0;
      a4 = 0;
    }
    *((_DWORD *)this + 8) = a2;
    this[3] = a3;
    this[2] = a4;
    if ( v8 )
    {
      v9 = this + 14;
      if ( (unsigned __int64)this[17] > 7 )
        v9 = (_QWORD *)*v9;
      v10 = ComputeLib::Diagnostics::TraceProvider::Provider();
      if ( *(_DWORD *)v10 > 5u
        && (*((_QWORD *)v10 + 2) & 0x10000LL) != 0
        && (*((_QWORD *)v10 + 3) & 0x10000LL) == *((_QWORD *)v10 + 3) )
      {
        v13 = (__int64)v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (int)v10,
          (__int64)&v13);
      }
      *((_BYTE *)this + 96) = 1;
      v11 = this[13];
      AcquireSRWLockExclusive(v11 + 5);
      if ( !LODWORD(v11[7].Ptr) )
      {
        LODWORD(v11[7].Ptr) = 1;
        SubmitThreadpoolWork((PTP_WORK)v11[4].Ptr);
      }
      if ( v11 != (PSRWLOCK)-40LL )
        ReleaseSRWLockExclusive(v11 + 5);
    }
  }
  if ( v15 )
    CallbackReference::~CallbackReference((CallbackReference *)v14);
}

```

## disassembly

```asm
0x18003eb10  push    rbx
0x18003eb12  push    rbp
0x18003eb13  push    rsi
0x18003eb14  push    rdi
0x18003eb15  sub     rsp, 58h
0x18003eb19  mov     rax, cs:__security_cookie
0x18003eb20  xor     rax, rsp
0x18003eb23  mov     [rsp+78h+var_30], rax
0x18003eb28  mov     rsi, r9
0x18003eb2b  mov     rbp, r8
0x18003eb2e  mov     edi, edx
0x18003eb30  mov     rbx, rcx
0x18003eb33  lea     rdx, [rsp+78h+var_40]
0x18003eb38  mov     rcx, [rcx+68h]; SRWLock
0x18003eb3c  call    ?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ; CallbackManager::Enter(void)
0x18003eb41  nop
0x18003eb42  cmp     [rsp+78h+var_38], 0
0x18003eb47  jz      loc_18003EC68
0x18003eb4d  test    rsi, rsi
0x18003eb50  jz      short loc_18003EB8D
0x18003eb52  mov     rax, [rbx+50h]
0x18003eb56  cmp     [rbx+48h], rax
0x18003eb5a  jz      short loc_18003EB67
0x18003eb5c  cmp     qword ptr [rbx+10h], 0
0x18003eb61  jnz     short loc_18003EB67
0x18003eb63  mov     al, 1
0x18003eb65  jmp     short loc_18003EB69
0x18003eb67  xor     al, al
0x18003eb69  test    dil, 2
0x18003eb6d  jz      short loc_18003EB7B
0x18003eb6f  mov     dword ptr [rbx+0A0h], 2
0x18003eb79  jmp     short loc_18003EBAC
0x18003eb7b  test    dil, 4
0x18003eb7f  jz      short loc_18003EBAC
0x18003eb81  mov     dword ptr [rbx+0A0h], 3
0x18003eb8b  jmp     short loc_18003EBAC
0x18003eb8d  mov     rcx, [rsp+78h]; this
0x18003eb92  test    edi, edi
0x18003eb94  jnz     loc_18003ECA8
0x18003eb9a  mov     rcx, [rsp+78h]; this
0x18003eb9f  test    rbp, rbp
0x18003eba2  jnz     loc_18003EC90
0x18003eba8  xor     al, al
0x18003ebaa  xor     esi, esi
0x18003ebac  mov     [rbx+20h], edi
0x18003ebaf  mov     [rbx+18h], rbp
0x18003ebb3  mov     [rbx+10h], rsi
0x18003ebb7  test    al, al
0x18003ebb9  jz      loc_18003EC68
0x18003ebbf  lea     rdi, [rbx+70h]
0x18003ebc3  cmp     qword ptr [rdi+18h], 7
0x18003ebc8  jbe     short loc_18003EBCD
0x18003ebca  mov     rdi, [rdi]
0x18003ebcd  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003ebd2  mov     ecx, [rax]
0x18003ebd4  cmp     ecx, 5
0x18003ebd7  jbe     short loc_18003EC1B
0x18003ebd9  mov     rdx, [rax+18h]
0x18003ebdd  mov     rcx, [rax+10h]
0x18003ebe1  mov     r8d, 10000h
0x18003ebe7  test    r8, rcx
0x18003ebea  jz      short loc_18003EC1B
0x18003ebec  mov     rcx, rdx
0x18003ebef  and     rcx, r8
0x18003ebf2  cmp     rcx, rdx
0x18003ebf5  jnz     short loc_18003EC1B
0x18003ebf7  mov     [rsp+78h+var_48], rdi
0x18003ebfc  lea     rcx, [rsp+78h+var_48]
0x18003ec01  mov     qword ptr [rsp+78h+var_58], rcx; __int64
0x18003ec06  xor     r9d, r9d
0x18003ec09  xor     r8d, r8d
0x18003ec0c  lea     rdx, byte_18009FE71
0x18003ec13  mov     rcx, rax; int
0x18003ec16  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003ec1b  mov     byte ptr [rbx+60h], 1
0x18003ec1f  mov     rbx, [rbx+68h]
0x18003ec23  lea     rdi, [rbx+28h]
0x18003ec27  mov     rcx, rdi; SRWLock
0x18003ec2a  call    cs:__imp_AcquireSRWLockExclusive
0x18003ec31  nop     dword ptr [rax+rax+00h]
0x18003ec36  cmp     dword ptr [rbx+38h], 0
0x18003ec3a  jnz     short loc_18003EC53
0x18003ec3c  mov     dword ptr [rbx+38h], 1
0x18003ec43  mov     rcx, [rbx+20h]; pwk
0x18003ec47  call    cs:__imp_SubmitThreadpoolWork
0x18003ec4e  nop     dword ptr [rax+rax+00h]
0x18003ec53  test    rdi, rdi
0x18003ec56  jz      short loc_18003EC68
0x18003ec58  mov     rcx, rdi; SRWLock
0x18003ec5b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ec62  nop     dword ptr [rax+rax+00h]
0x18003ec67  nop
0x18003ec68  cmp     [rsp+78h+var_38], 0
0x18003ec6d  jz      short loc_18003EC79
0x18003ec6f  lea     rcx, [rsp+78h+var_40]; this
0x18003ec74  call    ??1CallbackReference@@QEAA@XZ; CallbackReference::~CallbackReference(void)
0x18003ec79  mov     rcx, [rsp+78h+var_30]
0x18003ec7e  xor     rcx, rsp; StackCookie
0x18003ec81  call    __security_check_cookie
0x18003ec86  add     rsp, 58h
0x18003ec8a  pop     rdi
0x18003ec8b  pop     rsi
0x18003ec8c  pop     rbp
0x18003ec8d  pop     rbx
0x18003ec8e  retn
0x18003ec90  mov     r9d, 80070057h; char *
0x18003ec96  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\core\\o"...
0x18003ec9d  mov     edx, 1ABh; void *
0x18003eca2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003eca8  mov     r9d, 80070057h; char *
0x18003ecae  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\core\\o"...
0x18003ecb5  mov     edx, 1AAh; void *
0x18003ecba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
