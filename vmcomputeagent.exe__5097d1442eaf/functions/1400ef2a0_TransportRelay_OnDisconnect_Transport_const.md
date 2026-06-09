# TransportRelay::OnDisconnect(Transport const *)

- ea: `0x1400ef2a0`
- end: `0x1400ef3c0`
- name: `?OnDisconnect@TransportRelay@@EEAAXPEBVTransport@@@Z`
- size: `288`
- prototype: `void __fastcall(TransportRelay *__hidden this, const struct Transport *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002988`
- `0x1400083bc`
- `0x14000aeec`
- `0x14000ea60`
- `0x1400ef2a0`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400ef2f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400ef2f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ef2b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ef2b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ef2bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ef2bf`

## string_xrefs

- `0x1400ef3ab`: `onecore\vm\compute\common\transport\transportrelay.cpp`

## pseudocode

```c
void __fastcall TransportRelay::OnDisconnect(RTL_SRWLOCK *this, const struct Transport *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  RTL_SRWLOCK *v6; // rax
  const struct Transport *Ptr; // rcx
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(this + 15);
  LODWORD(this[16].Ptr) = GetCurrentThreadId();
  if ( (unsigned int)(LODWORD(this[17].Ptr) - 4) <= 1 )
    LODWORD(this[17].Ptr) = 6;
  LODWORD(this[16].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 15);
  v5 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v5 > 4u )
  {
    v4 = *(_QWORD *)(v5 + 24);
    if ( (*(_QWORD *)(v5 + 16) & 0x80u) != 0LL && (*(_QWORD *)(v5 + 24) & 0x80LL) == v4 )
    {
      v6 = this + 25;
      v11 = (__int64)a2;
      if ( this[28].Ptr > (PVOID)7 )
        v6 = (RTL_SRWLOCK *)v6->Ptr;
      v12 = (__int64)v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v5,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
  Ptr = (const struct Transport *)this[1].Ptr;
  if ( a2 == Ptr )
  {
    Ptr = (const struct Transport *)this[3].Ptr;
    HIDWORD(this[11].Ptr) = 3;
  }
  else
  {
    if ( a2 != this[3].Ptr )
    {
      v8 = wil::verify_hresult<long>(2147549183LL, v4);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x303,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\transportrelay.cpp",
        (const char *)v8,
        v9);
    }
    LODWORD(this[12].Ptr) = 3;
  }
  (*(void (__fastcall **)(const struct Transport *, __int64))(*(_QWORD *)Ptr + 40LL))(Ptr, v4);
}

```

## disassembly

```asm
0x1400ef2a0  mov     [rsp+arg_10], rbx
0x1400ef2a5  mov     [rsp+arg_18], rsi
0x1400ef2aa  push    rdi
0x1400ef2ab  sub     rsp, 30h
0x1400ef2af  mov     rbx, rcx
0x1400ef2b2  mov     rdi, rdx
0x1400ef2b5  add     rcx, 78h ; 'x'; SRWLock
0x1400ef2b9  call    cs:__imp_AcquireSRWLockExclusive
0x1400ef2bf  call    cs:__imp_GetCurrentThreadId
0x1400ef2c5  mov     [rbx+80h], eax
0x1400ef2cb  mov     eax, [rbx+88h]
0x1400ef2d1  sub     eax, 4
0x1400ef2d4  cmp     eax, 1
0x1400ef2d7  ja      short loc_1400EF2E3
0x1400ef2d9  mov     dword ptr [rbx+88h], 6
0x1400ef2e3  lea     rcx, [rbx+78h]; SRWLock
0x1400ef2e7  mov     dword ptr [rbx+80h], 0
0x1400ef2f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1400ef2f7  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400ef2fc  mov     rcx, [rax+8]; int
0x1400ef300  mov     eax, [rcx]
0x1400ef302  cmp     eax, 4
0x1400ef305  jbe     short loc_1400EF35E
0x1400ef307  mov     rdx, [rcx+18h]
0x1400ef30b  mov     rax, [rcx+10h]
0x1400ef30f  test    al, al
0x1400ef311  jns     short loc_1400EF35E
0x1400ef313  mov     rax, rdx
0x1400ef316  and     eax, 80h
0x1400ef31b  cmp     rax, rdx
0x1400ef31e  jnz     short loc_1400EF35E
0x1400ef320  lea     rax, [rbx+0C8h]
0x1400ef327  mov     [rsp+38h+arg_0], rdi
0x1400ef32c  cmp     qword ptr [rax+18h], 7
0x1400ef331  jbe     short loc_1400EF336
0x1400ef333  mov     rax, [rax]
0x1400ef336  mov     [rsp+38h+arg_8], rax
0x1400ef33b  lea     rdx, word_14013C29E
0x1400ef342  lea     rax, [rsp+38h+arg_0]
0x1400ef347  xor     r8d, r8d
0x1400ef34a  mov     [rsp+38h+var_10], rax; __int64
0x1400ef34f  lea     rax, [rsp+38h+arg_8]
0x1400ef354  mov     [rsp+38h+var_18], rax; int
0x1400ef359  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1400ef35e  mov     rcx, [rbx+8]
0x1400ef362  cmp     rdi, rcx
0x1400ef365  jnz     short loc_1400EF374
0x1400ef367  mov     rcx, [rbx+18h]
0x1400ef36b  mov     dword ptr [rbx+5Ch], 3
0x1400ef372  jmp     short loc_1400EF381
0x1400ef374  cmp     rdi, [rbx+18h]
0x1400ef378  jnz     short loc_1400EF39C
0x1400ef37a  mov     dword ptr [rbx+60h], 3
0x1400ef381  mov     rax, [rcx]
0x1400ef384  mov     rax, [rax+28h]
0x1400ef388  mov     rbx, [rsp+38h+arg_10]
0x1400ef38d  mov     rsi, [rsp+38h+arg_18]
0x1400ef392  add     rsp, 30h
0x1400ef396  pop     rdi
0x1400ef397  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef39c  mov     ecx, 8000FFFFh
0x1400ef3a1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400ef3a6  mov     rcx, [rsp+38h]; this
0x1400ef3ab  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\common\\transport"...
0x1400ef3b2  mov     r9d, eax; char *
0x1400ef3b5  mov     edx, 303h; void *
0x1400ef3ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
