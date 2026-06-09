# CacheStorageTraceLogging::CS_CacheStorage_open::StartActivity(void *,gsl::basic_string_span<ushort const,-1>)

- ea: `0x18003867c`
- end: `0x1800387db`
- name: `?StartActivity@CS_CacheStorage_open@CacheStorageTraceLogging@@QEAAXPEAXV?$basic_string_span@$$CBG$0?0@gsl@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180038480`

## callees

- `0x180001008`
- `0x18000126c`
- `0x180037d40`
- `0x18003867c`
- `0x18004ae00`
- `0x18005107c`
- `0x18005dcb0`
- `0x18006aa90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038742`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800386fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800386fa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800386d8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800386d8`

## pseudocode

```c
void __fastcall CacheStorageTraceLogging::CS_CacheStorage_open::StartActivity(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ebx
  __int64 v15; // r9
  __int64 *v16; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  int v19; // ecx
  __int64 v20; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-30h] BYREF
  PSRWLOCK SRWLock; // [rsp+80h] [rbp+8h] BYREF
  __int64 v23; // [rsp+98h] [rbp+20h] BYREF

  wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v6 = *(_QWORD *)(a1 + 272);
  v7 = StorageServerProvider::Provider();
  v9 = *(unsigned int *)v7;
  if ( (unsigned int)v9 > 4 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000002LL, v8, v9) )
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  else
    *(_OWORD *)(v6 + 8) = 0;
  v10 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = StorageServerProvider::Provider();
  v14 = (int)v11;
  if ( *(_DWORD *)v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000002LL, v12, v13) )
  {
    v16 = (__int64 *)_tlgWrapBinary<unsigned short,2>(v21, *((_QWORD *)a3 + 1), *a3, v15);
    v23 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v18 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v20 = 0;
    if ( !*(_BYTE *)(v18 + 4) || _tlgGuidIsZero((const struct _GUID *)(v18 + 24)) )
      v19 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>>(
      v14,
      (int)&byte_1800E53AF,
      v18 + 8,
      v19,
      (__int64)&v20,
      (__int64)&SRWLock,
      (__int64)&v23,
      v16);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18003867c  mov     rax, rsp
0x18003867f  mov     [rax+10h], rbx
0x180038683  mov     [rax+18h], rbp
0x180038687  push    rsi
0x180038688  push    rdi
0x180038689  push    r15
0x18003868b  sub     rsp, 60h
0x18003868f  mov     rbp, rdx
0x180038692  mov     rsi, r8
0x180038695  lea     rdx, [rax+8]
0x180038699  mov     rdi, rcx
0x18003869c  call    ?LockExclusive@?$ActivityBase@VStorageServerProvider@@$00$0EAAAAAAAAAAC@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800386a1  mov     rbx, [rdi+110h]
0x1800386a8  call    ?Provider@StorageServerProvider@@SAPEBU_tlgProvider_t@@XZ; StorageServerProvider::Provider(void)
0x1800386ad  mov     r15, 400000000002h
0x1800386b7  mov     r9d, [rax]
0x1800386ba  cmp     r9d, 4
0x1800386be  jbe     short loc_1800386E0
0x1800386c0  mov     rdx, r15
0x1800386c3  mov     rcx, rax
0x1800386c6  call    _tlgKeywordOn
0x1800386cb  test    al, al
0x1800386cd  jz      short loc_1800386E0
0x1800386cf  lea     rdx, [rbx+8]; ActivityId
0x1800386d3  mov     ecx, 3; ControlCode
0x1800386d8  call    cs:__imp_EventActivityIdControl
0x1800386de  jmp     short loc_1800386E7
0x1800386e0  xorps   xmm0, xmm0
0x1800386e3  movups  xmmword ptr [rbx+8], xmm0
0x1800386e7  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x1800386ef  mov     dword ptr [rbx], 1
0x1800386f5  test    rcx, rcx
0x1800386f8  jz      short loc_180038700
0x1800386fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180038700  call    ?Provider@StorageServerProvider@@SAPEBU_tlgProvider_t@@XZ; StorageServerProvider::Provider(void)
0x180038705  mov     rbx, rax
0x180038708  mov     ecx, [rax]
0x18003870a  cmp     ecx, 4
0x18003870d  jbe     loc_1800387B4
0x180038713  mov     rdx, r15
0x180038716  mov     rcx, rax
0x180038719  call    _tlgKeywordOn
0x18003871e  test    al, al
0x180038720  jz      loc_1800387B4
0x180038726  mov     r8d, [rsi]
0x180038729  lea     rcx, [rsp+78h+var_30]
0x18003872e  mov     rdx, [rsi+8]
0x180038732  call    ??$_tlgWrapBinary@G$01@@YA?AU?$_tlgWrapperArray@$00@@PEBG_K@Z; _tlgWrapBinary<ushort,2>(ushort const *,unsigned __int64)
0x180038737  mov     rsi, rax
0x18003873a  mov     [rsp+78h+arg_18], rbp
0x180038742  call    cs:__imp_GetCurrentThreadId
0x180038748  mov     r8, [rdi+110h]
0x18003874f  mov     dword ptr [rsp+78h+SRWLock], eax
0x180038756  mov     [rsp+78h+var_38], 0
0x18003875f  cmp     byte ptr [r8+4], 0
0x180038764  jz      short loc_180038773
0x180038766  lea     rcx, [r8+18h]; struct _GUID *
0x18003876a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003876f  test    al, al
0x180038771  jz      short loc_180038775
0x180038773  xor     ecx, ecx
0x180038775  mov     [rsp+78h+var_40], rsi; __int64
0x18003877a  lea     rax, [rsp+78h+arg_18]
0x180038782  mov     [rsp+78h+var_48], rax; __int64
0x180038787  lea     rdx, byte_1800E53AF
0x18003878e  lea     rax, [rsp+78h+SRWLock]
0x180038796  mov     r9, rcx
0x180038799  mov     [rsp+78h+var_50], rax; __int64
0x18003879e  add     r8, 8
0x1800387a2  lea     rax, [rsp+78h+var_38]
0x1800387a7  mov     rcx, rbx; int
0x1800387aa  mov     [rsp+78h+var_58], rax; __int64
0x1800387af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &)
0x1800387b4  lea     rcx, [rdi+120h]; this
0x1800387bb  cmp     dword ptr [rcx+18h], 0
0x1800387bf  jnz     short loc_1800387C6
0x1800387c1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800387c6  lea     r11, [rsp+78h+var_18]
0x1800387cb  mov     rbx, [r11+28h]
0x1800387cf  mov     rbp, [r11+30h]
0x1800387d3  mov     rsp, r11
0x1800387d6  pop     r15
0x1800387d8  pop     rdi
0x1800387d9  pop     rsi
0x1800387da  retn
```
