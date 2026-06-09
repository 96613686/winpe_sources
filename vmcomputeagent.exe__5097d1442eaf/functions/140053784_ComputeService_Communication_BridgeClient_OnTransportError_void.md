# ComputeService::Communication::BridgeClient::OnTransportError(void)

- ea: `0x140053784`
- end: `0x1400538d0`
- name: `?OnTransportError@BridgeClient@Communication@ComputeService@@AEAAXXZ`
- size: `332`
- prototype: `void __fastcall(ComputeService::Communication::BridgeClient *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400523f0`
- `0x140053060`
- `0x1400f7955`

## callees

- `0x1400016ec`
- `0x140005360`
- `0x14000aeec`
- `0x140052a44`
- `0x140053784`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400537fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400537fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400537ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400537ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400537b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400537b2`

## string_xrefs

- `0x1400538ba`: `onecore\vm\compute\common\bridge\bridgeclient.cpp`

## pseudocode

```c
void __fastcall ComputeService::Communication::BridgeClient::OnTransportError(RTL_SRWLOCK *this)
{
  char v2; // di
  int Ptr; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  const char *v6; // [rsp+20h] [rbp-98h]
  char v7; // [rsp+30h] [rbp-88h] BYREF
  int v8; // [rsp+34h] [rbp-84h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-78h] BYREF
  int *v10; // [rsp+60h] [rbp-58h]
  __int64 v11; // [rsp+68h] [rbp-50h]
  char *v12; // [rsp+70h] [rbp-48h]
  __int64 v13; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v2 = 0;
  AcquireSRWLockExclusive(this + 13);
  LODWORD(this[14].Ptr) = GetCurrentThreadId();
  Ptr = (int)this[15].Ptr;
  if ( Ptr )
  {
    if ( Ptr == 1 || Ptr == 2 )
    {
      HIDWORD(this[15].Ptr) = 1;
      v2 = 1;
      LODWORD(this[15].Ptr) = 3;
    }
    else if ( Ptr != 3 && Ptr != 5 )
    {
      LODWORD(v6) = this[15].Ptr;
      wil::details::in1diag3::FailFast_UnexpectedMsg(
        retaddr,
        (void *)0x465,
        (unsigned int)"onecore\\vm\\compute\\common\\bridge\\bridgeclient.cpp",
        "unexpected state %d",
        v6);
    }
  }
  LODWORD(this[14].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 13);
  v5 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v5 > 4u )
  {
    v4 = *(_QWORD *)(v5 + 24);
    if ( (*(_QWORD *)(v5 + 16) & 4) != 0 && (*(_QWORD *)(v5 + 24) & 4LL) == v4 )
    {
      v7 = v2;
      v12 = &v7;
      v8 = Ptr;
      v10 = &v8;
      v13 = 1;
      v11 = 4;
      tlgWriteTransfer_EventWriteTransfer(v5, (int)&byte_1401344A1, 0, 0, 4u, &v9);
    }
  }
  if ( v2 )
    (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[3].Ptr + 40LL))(this[3].Ptr, v4);
}

```

## disassembly

```asm
0x140053784  push    rbx
0x140053786  push    rbp
0x140053787  push    rsi
0x140053788  push    rdi
0x140053789  sub     rsp, 98h
0x140053790  mov     rax, cs:__security_cookie
0x140053797  xor     rax, rsp
0x14005379a  mov     [rsp+0B8h+var_38], rax
0x1400537a2  mov     rbx, rcx
0x1400537a5  xor     dil, dil
0x1400537a8  add     rcx, 68h ; 'h'; SRWLock
0x1400537ac  call    cs:__imp_AcquireSRWLockExclusive
0x1400537b2  call    cs:__imp_GetCurrentThreadId
0x1400537b8  mov     [rbx+70h], eax
0x1400537bb  mov     esi, [rbx+78h]
0x1400537be  mov     ecx, esi
0x1400537c0  test    esi, esi
0x1400537c2  jz      short loc_1400537EF
0x1400537c4  sub     ecx, 1
0x1400537c7  jz      short loc_1400537DE
0x1400537c9  sub     ecx, 1
0x1400537cc  jz      short loc_1400537DE
0x1400537ce  sub     ecx, 1
0x1400537d1  jz      short loc_1400537EF
0x1400537d3  cmp     ecx, 2
0x1400537d6  jnz     loc_1400538AB
0x1400537dc  jmp     short loc_1400537EF
0x1400537de  mov     dword ptr [rbx+7Ch], 1
0x1400537e5  mov     dil, 1
0x1400537e8  mov     dword ptr [rbx+78h], 3
0x1400537ef  lea     rcx, [rbx+68h]; SRWLock
0x1400537f3  mov     dword ptr [rbx+70h], 0
0x1400537fa  call    cs:__imp_ReleaseSRWLockExclusive
0x140053800  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140053805  mov     rcx, [rax+8]; int
0x140053809  mov     eax, [rcx]
0x14005380b  cmp     eax, 4
0x14005380e  jbe     short loc_14005387A
0x140053810  mov     rdx, [rcx+18h]
0x140053814  mov     rax, [rcx+10h]
0x140053818  test    al, 4
0x14005381a  jz      short loc_14005387A
0x14005381c  mov     rax, rdx
0x14005381f  and     eax, 4
0x140053822  cmp     rax, rdx
0x140053825  jnz     short loc_14005387A
0x140053827  lea     rax, [rsp+0B8h+var_88]
0x14005382c  mov     [rsp+0B8h+var_88], dil
0x140053831  mov     [rsp+0B8h+var_48], rax
0x140053836  lea     rdx, byte_1401344A1; int
0x14005383d  lea     rax, [rsp+0B8h+var_84]
0x140053842  mov     [rsp+0B8h+var_84], esi
0x140053846  mov     [rsp+0B8h+var_58], rax
0x14005384b  xor     r9d, r9d; int
0x14005384e  lea     rax, [rsp+0B8h+var_78]
0x140053853  mov     [rsp+0B8h+var_40], 1
0x14005385c  mov     [rsp+0B8h+var_90], rax; PEVENT_DATA_DESCRIPTOR
0x140053861  xor     r8d, r8d; int
0x140053864  mov     dword ptr [rsp+0B8h+var_98], 4; ULONG
0x14005386c  mov     [rsp+0B8h+var_50], 4
0x140053875  call    _tlgWriteTransfer_EventWriteTransfer
0x14005387a  test    dil, dil
0x14005387d  jz      short loc_14005388F
0x14005387f  mov     rcx, [rbx+18h]
0x140053883  mov     rax, [rcx]
0x140053886  mov     rax, [rax+28h]
0x14005388a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005388f  mov     rcx, [rsp+0B8h+var_38]
0x140053897  xor     rcx, rsp; StackCookie
0x14005389a  call    __security_check_cookie
0x14005389f  add     rsp, 98h
0x1400538a6  pop     rdi
0x1400538a7  pop     rsi
0x1400538a8  pop     rbp
0x1400538a9  pop     rbx
0x1400538aa  retn
0x1400538ab  mov     rcx, [rsp+0B8h]; this
0x1400538b3  lea     r9, aUnexpectedStat; "unexpected state %d"
0x1400538ba  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\common\\bridge\\b"...
0x1400538c1  mov     dword ptr [rsp+0B8h+var_98], esi; char *
0x1400538c5  mov     edx, 465h; void *
0x1400538ca  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
