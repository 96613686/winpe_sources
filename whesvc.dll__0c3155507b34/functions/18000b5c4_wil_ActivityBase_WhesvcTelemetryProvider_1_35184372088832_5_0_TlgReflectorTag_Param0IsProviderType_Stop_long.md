# wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000b5c4`
- end: `0x18000b73b`
- name: `?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b380`
- `0x18001b908`
- `0x1800221ec`

## callees

- `0x1800018dc`
- `0x1800032e0`
- `0x180003da4`
- `0x18000626c`
- `0x18000a920`
- `0x18000a9ac`
- `0x18000ae4c`
- `0x18000b5c4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b680`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b629`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b629`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  const struct wil::FailureInfo *v8; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v11; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12[2]; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v13; // [rsp+70h] [rbp-39h]
  __int64 v14; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v16; // [rsp+88h] [rbp-21h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-19h]
  __int64 v18; // [rsp+98h] [rbp-11h]

  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v2 = a1[34];
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v8);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = WhesvcTelemetryProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0 && (v7 & 0x200000000000LL) == v7 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v11 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v18 = 4;
        p_SRWLock = &SRWLock;
        v16 = 4;
        v13 = &v11;
        v14 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v6,
          (unsigned __int8 *)&dword_18002D1EC,
          (const GUID *)(a1[34] + 8LL),
          0,
          5u,
          v12);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000b5c4  mov     [rsp-8+arg_8], rbx
0x18000b5c9  mov     [rsp-8+arg_10], rdi
0x18000b5ce  push    rbp
0x18000b5cf  lea     rbp, [rsp-57h]
0x18000b5d4  sub     rsp, 100h
0x18000b5db  mov     rax, cs:__security_cookie
0x18000b5e2  xor     rax, rsp
0x18000b5e5  mov     [rbp+57h+var_10], rax
0x18000b5e9  mov     rbx, rcx
0x18000b5ec  lea     rdx, [rbp+57h+SRWLock]
0x18000b5f0  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b5f5  mov     rax, [rbx+110h]
0x18000b5fc  mov     edi, [rax+0F8h]
0x18000b602  cmp     edi, 1
0x18000b605  jl      loc_18000B720
0x18000b60b  cmp     dword ptr [rax+48h], 0
0x18000b60f  jl      short loc_18000B618
0x18000b611  mov     dword ptr [rax+48h], 0
0x18000b618  dec     edi
0x18000b61a  mov     [rax+0F8h], edi
0x18000b620  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000b624  test    rcx, rcx
0x18000b627  jz      short loc_18000B62F
0x18000b629  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b62f  test    edi, edi
0x18000b631  jnz     short loc_18000B647
0x18000b633  mov     rax, [rbx]
0x18000b636  mov     rcx, rbx
0x18000b639  mov     rax, [rax+8]
0x18000b63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b642  jmp     loc_18000B6F6
0x18000b647  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18000b64c  mov     rdi, rax
0x18000b64f  mov     ecx, [rax]
0x18000b651  cmp     ecx, 5
0x18000b654  jbe     loc_18000B6F6
0x18000b65a  mov     rax, [rax+18h]
0x18000b65e  mov     rcx, [rdi+10h]
0x18000b662  mov     rdx, 200000000000h
0x18000b66c  test    rdx, rcx
0x18000b66f  jz      loc_18000B6F6
0x18000b675  mov     rcx, rax
0x18000b678  and     rcx, rdx
0x18000b67b  cmp     rcx, rax
0x18000b67e  jnz     short loc_18000B6F6
0x18000b680  call    cs:__imp_GetCurrentThreadId
0x18000b686  mov     [rbp+57h+var_D0], eax
0x18000b689  mov     dword ptr [rbp+57h+SRWLock], 0
0x18000b690  mov     [rbp+57h+var_C0], 1000000h
0x18000b698  lea     rax, [rbp+57h+var_D0]
0x18000b69c  mov     [rbp+57h+var_70], rax
0x18000b6a0  mov     [rbp+57h+var_68], 4
0x18000b6a8  lea     rax, [rbp+57h+SRWLock]
0x18000b6ac  mov     [rbp+57h+var_80], rax
0x18000b6b0  mov     [rbp+57h+var_78], 4
0x18000b6b8  lea     rax, [rbp+57h+var_C0]
0x18000b6bc  mov     [rbp+57h+var_90], rax
0x18000b6c0  mov     [rbp+57h+var_88], 8
0x18000b6c8  mov     r8, [rbx+110h]
0x18000b6cf  add     r8, 8
0x18000b6d3  lea     rax, [rbp+57h+var_B0]
0x18000b6d7  mov     [rsp+100h+var_D8], rax
0x18000b6dc  mov     [rsp+100h+var_E0], 5
0x18000b6e4  xor     r9d, r9d
0x18000b6e7  lea     rdx, dword_18002D1EC
0x18000b6ee  mov     rcx, rdi
0x18000b6f1  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b6f6  mov     rcx, rbx
0x18000b6f9  call    ?IgnoreCurrentThread@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b6fe  nop
0x18000b6ff  mov     rcx, [rbp+57h+var_10]
0x18000b703  xor     rcx, rsp; StackCookie
0x18000b706  call    __security_check_cookie
0x18000b70b  lea     r11, [rsp+100h+var_s0]
0x18000b713  mov     rbx, [r11+18h]
0x18000b717  mov     rdi, [r11+20h]
0x18000b71b  mov     rsp, r11
0x18000b71e  pop     rbp
0x18000b71f  retn
0x18000b720  xor     edx, edx; Val
0x18000b722  mov     r8d, 98h; Size
0x18000b728  lea     rcx, [rbp+57h+var_B0]; void *
0x18000b72c  call    memset_0
0x18000b731  lea     rcx, [rbp+57h+var_B0]; this
0x18000b735  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
