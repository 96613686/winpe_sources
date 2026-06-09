# wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18008bee8`
- end: `0x18008c065`
- name: `?Stop@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800890e0`

## callees

- `0x180001f10`
- `0x180008c90`
- `0x1800857a8`
- `0x18008bee8`
- `0x18008c454`
- `0x18008d138`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008bf40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008bf40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008bf86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008bfe9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008bf86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008bfe9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Telemetry::ServiceBase *__fastcall wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  struct Windows::Telemetry::ServiceBase *result; // rax
  __int64 v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rbx
  void *v9; // rdx
  unsigned int v10; // r8d
  struct Windows::Telemetry::ServiceBase **v11; // rcx
  const struct wil::FailureInfo *v12; // rdx
  int v13; // [rsp+20h] [rbp-E8h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C8h] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-C0h] BYREF
  int v16[2]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v17[168]; // [rsp+60h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset(v17, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v17, v12);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    result = Windows::Telemetry::ServiceBase::Instance();
    v6 = *((_QWORD *)result + 1);
    if ( *(_DWORD *)v6 > 5u && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 )
    {
      result = (struct Windows::Telemetry::ServiceBase *)(*(_QWORD *)(v6 + 24) & 0x400000000000LL);
      if ( result == *(struct Windows::Telemetry::ServiceBase **)(v6 + 24) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        *(_QWORD *)v16 = 0x1000000;
        result = (struct Windows::Telemetry::ServiceBase *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                                             v6,
                                                             (int)&word_18012FE5E,
                                                             (unsigned int)*(_QWORD *)(a1 + 272) + 8,
                                                             v7,
                                                             (__int64)v16,
                                                             (__int64)&SRWLock,
                                                             (__int64)&CurrentThreadId);
      }
    }
  }
  else
  {
    result = (struct Windows::Telemetry::ServiceBase *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v8 = a1 + 288;
    if ( *(_DWORD *)(v8 + 24) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v9, v10, (const char *)0x8007029CLL, v13);
    *(_DWORD *)(v8 + 24) = 0;
    v11 = *(struct Windows::Telemetry::ServiceBase ***)v8;
    while ( 1 )
    {
      result = *v11;
      if ( !*v11 )
        break;
      if ( result == (struct Windows::Telemetry::ServiceBase *)v8 )
      {
        result = *(struct Windows::Telemetry::ServiceBase **)(v8 + 16);
        *v11 = result;
        break;
      }
      v11 = (struct Windows::Telemetry::ServiceBase **)((char *)result + 16);
      *(_QWORD *)v8 = (char *)result + 16;
    }
    *(_QWORD *)v8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18008bee8  mov     [rsp+arg_8], rbx
0x18008beed  push    rdi
0x18008beee  sub     rsp, 100h
0x18008bef5  mov     rbx, rcx
0x18008bef8  mov     [rsp+108h+SRWLock], 0
0x18008bf01  lea     rdx, [rsp+108h+SRWLock]
0x18008bf06  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18008bf0b  mov     rax, [rbx+110h]
0x18008bf12  mov     edi, [rax+0F8h]
0x18008bf18  cmp     edi, 1
0x18008bf1b  jl      loc_18008C048
0x18008bf21  cmp     dword ptr [rax+48h], 0
0x18008bf25  jl      short loc_18008BF2E
0x18008bf27  mov     dword ptr [rax+48h], 0
0x18008bf2e  dec     edi
0x18008bf30  mov     [rax+0F8h], edi
0x18008bf36  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x18008bf3b  test    rcx, rcx
0x18008bf3e  jz      short loc_18008BF46
0x18008bf40  call    cs:__imp_ReleaseSRWLockExclusive
0x18008bf46  test    edi, edi
0x18008bf48  jnz     short loc_18008BF5B
0x18008bf4a  mov     rax, [rbx]
0x18008bf4d  mov     rcx, rbx
0x18008bf50  mov     rax, [rax+8]
0x18008bf54  call    _guard_dispatch_icall
0x18008bf59  jmp     short loc_18008BFD9
0x18008bf5b  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x18008bf60  mov     rdi, [rax+8]
0x18008bf64  cmp     dword ptr [rdi], 5
0x18008bf67  jbe     short loc_18008BFD9
0x18008bf69  mov     rcx, 400000000000h
0x18008bf73  test    [rdi+10h], rcx
0x18008bf77  jz      short loc_18008BFD9
0x18008bf79  mov     rax, [rdi+18h]
0x18008bf7d  and     rax, rcx
0x18008bf80  cmp     rax, [rdi+18h]
0x18008bf84  jnz     short loc_18008BFD9
0x18008bf86  call    cs:__imp_GetCurrentThreadId
0x18008bf8c  mov     [rsp+108h+var_C0], eax
0x18008bf90  mov     dword ptr [rsp+108h+SRWLock], 0
0x18008bf98  mov     qword ptr [rsp+108h+var_B8], 1000000h
0x18008bfa1  mov     r8, [rbx+110h]
0x18008bfa8  add     r8, 8
0x18008bfac  lea     rax, [rsp+108h+var_C0]
0x18008bfb1  mov     [rsp+108h+var_D8], rax
0x18008bfb6  lea     rax, [rsp+108h+SRWLock]
0x18008bfbb  mov     [rsp+108h+var_E0], rax
0x18008bfc0  lea     rax, [rsp+108h+var_B8]
0x18008bfc5  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18008bfca  lea     rdx, word_18012FE5E
0x18008bfd1  mov     rcx, rdi
0x18008bfd4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008bfd9  cmp     dword ptr [rbx+138h], 0
0x18008bfe0  jz      short loc_18008C037
0x18008bfe2  add     rbx, 120h
0x18008bfe9  call    cs:__imp_GetCurrentThreadId
0x18008bfef  cmp     [rbx+18h], eax
0x18008bff2  jz      short loc_18008C007
0x18008bff4  mov     rcx, [rsp+108h]; this
0x18008bffc  mov     r9d, 8007029Ch; char *
0x18008c002  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008c007  mov     dword ptr [rbx+18h], 0
0x18008c00e  mov     rcx, [rbx]
0x18008c011  jmp     short loc_18008C01F
0x18008c013  cmp     rax, rbx
0x18008c016  jz      short loc_18008C029
0x18008c018  lea     rcx, [rax+10h]
0x18008c01c  mov     [rbx], rcx
0x18008c01f  mov     rax, [rcx]
0x18008c022  test    rax, rax
0x18008c025  jnz     short loc_18008C013
0x18008c027  jmp     short loc_18008C030
0x18008c029  mov     rax, [rbx+10h]
0x18008c02d  mov     [rcx], rax
0x18008c030  mov     qword ptr [rbx], 0
0x18008c037  mov     rbx, [rsp+108h+arg_8]
0x18008c03f  add     rsp, 100h
0x18008c046  pop     rdi
0x18008c047  retn
0x18008c048  xor     edx, edx; Val
0x18008c04a  mov     r8d, 98h; Size
0x18008c050  lea     rcx, [rsp+108h+var_A8]; void *
0x18008c055  call    memset
0x18008c05a  lea     rcx, [rsp+108h+var_A8]; this
0x18008c05f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
