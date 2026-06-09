# DataPackageTracing::DelayedRenderActivity::StartActivity(void)

- ea: `0x18004e118`
- end: `0x18004e2b9`
- name: `?StartActivity@DelayedRenderActivity@DataPackageTracing@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(DataPackageTracing::DelayedRenderActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005dcac`

## callees

- `0x180001d2c`
- `0x180002ad0`
- `0x1800314ac`
- `0x18003a774`
- `0x18003daf8`
- `0x18004e118`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004e182`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004e182`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e1a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e1a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e1d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e28e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e1d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e28e`

## pseudocode

```c
void __fastcall DataPackageTracing::DelayedRenderActivity::StartActivity(
        DataPackageTracing::DelayedRenderActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = DataPackageTracing::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x400000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = DataPackageTracing::Provider();
  v6 = v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 )
  {
    v8 = *((_QWORD *)v4 + 3);
    v7 = *((_QWORD *)v6 + 2);
    if ( (v7 & 0x400000000000LL) != 0 )
    {
      v7 = v8 & 0x400000000000LL;
      if ( (v8 & 0x400000000000LL) == v8 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v14 = 0;
        v9 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v9 + 4)
          || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
          && !*(_DWORD *)(v9 + 28)
          && !*(_DWORD *)(v9 + 32)
          && !*(_DWORD *)(v9 + 36) )
        {
          v10 = 0;
        }
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        tlgWriteTransfer_EventWriteTransfer(v6, &unk_18009AA48, v9 + 8, v10, 4, v15);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v11 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          v5);
      *(_QWORD *)v11 = Local;
      if ( Local )
      {
        *((_QWORD *)v11 + 2) = *Local;
        *Local = v11;
        *((_DWORD *)v11 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v11 = 0;
    }
  }
}

```

## disassembly

```asm
0x18004e118  push    rbp
0x18004e11a  push    rbx
0x18004e11b  push    rdi
0x18004e11c  push    r14
0x18004e11e  lea     rbp, [rsp-3Fh]
0x18004e123  sub     rsp, 98h
0x18004e12a  mov     rax, cs:__security_cookie
0x18004e131  xor     rax, rsp
0x18004e134  mov     [rbp+57h+var_30], rax
0x18004e138  mov     rbx, rcx
0x18004e13b  lea     rdx, [rbp+57h+SRWLock]
0x18004e13f  call    ?LockExclusive@?$ActivityBase@VDataPackageTracing@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004e144  mov     rdi, [rbx+110h]
0x18004e14b  call    ?Provider@DataPackageTracing@@SAPEBU_tlgProvider_t@@XZ; DataPackageTracing::Provider(void)
0x18004e150  mov     edx, [rax]
0x18004e152  mov     r14, 400000000000h
0x18004e15c  cmp     edx, 5
0x18004e15f  jbe     short loc_18004E18A
0x18004e161  mov     rcx, [rax+18h]
0x18004e165  mov     rax, [rax+10h]
0x18004e169  test    r14, rax
0x18004e16c  jz      short loc_18004E18A
0x18004e16e  mov     rax, rcx
0x18004e171  and     rax, r14
0x18004e174  cmp     rax, rcx
0x18004e177  jnz     short loc_18004E18A
0x18004e179  lea     rdx, [rdi+8]; ActivityId
0x18004e17d  mov     ecx, 3; ControlCode
0x18004e182  call    cs:__imp_EventActivityIdControl
0x18004e188  jmp     short loc_18004E191
0x18004e18a  xorps   xmm0, xmm0
0x18004e18d  movups  xmmword ptr [rdi+8], xmm0
0x18004e191  mov     dword ptr [rdi], 1
0x18004e197  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004e19b  test    rcx, rcx
0x18004e19e  jz      short loc_18004E1A6
0x18004e1a0  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e1a6  call    ?Provider@DataPackageTracing@@SAPEBU_tlgProvider_t@@XZ; DataPackageTracing::Provider(void)
0x18004e1ab  mov     rdi, rax
0x18004e1ae  mov     ecx, [rax]
0x18004e1b0  cmp     ecx, 5
0x18004e1b3  jbe     loc_18004E25B
0x18004e1b9  mov     rax, [rax+18h]
0x18004e1bd  mov     rcx, [rdi+10h]
0x18004e1c1  test    r14, rcx
0x18004e1c4  jz      loc_18004E25B
0x18004e1ca  mov     rcx, rax
0x18004e1cd  and     rcx, r14
0x18004e1d0  cmp     rcx, rax
0x18004e1d3  jnz     loc_18004E25B
0x18004e1d9  call    cs:__imp_GetCurrentThreadId
0x18004e1df  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004e1e2  mov     [rbp+57h+var_78], 0
0x18004e1ea  mov     r8, [rbx+110h]
0x18004e1f1  cmp     byte ptr [r8+4], 0
0x18004e1f6  jz      short loc_18004E217
0x18004e1f8  lea     r9, [r8+18h]
0x18004e1fc  cmp     dword ptr [r9], 0
0x18004e200  jnz     short loc_18004E21A
0x18004e202  cmp     dword ptr [r9+4], 0
0x18004e207  jnz     short loc_18004E21A
0x18004e209  cmp     dword ptr [r9+8], 0
0x18004e20e  jnz     short loc_18004E21A
0x18004e210  cmp     dword ptr [r9+0Ch], 0
0x18004e215  jnz     short loc_18004E21A
0x18004e217  xor     r9d, r9d
0x18004e21a  lea     rax, [rbp+57h+SRWLock]
0x18004e21e  mov     [rbp+57h+var_40], rax
0x18004e222  mov     ecx, 4
0x18004e227  mov     [rbp+57h+var_38], rcx
0x18004e22b  lea     rax, [rbp+57h+var_78]
0x18004e22f  mov     [rbp+57h+var_50], rax
0x18004e233  mov     [rbp+57h+var_48], 8
0x18004e23b  add     r8, 8
0x18004e23f  lea     rax, [rbp+57h+var_70]
0x18004e243  mov     [rsp+0B0h+var_88], rax
0x18004e248  mov     [rsp+0B0h+var_90], ecx
0x18004e24c  lea     rdx, unk_18009AA48
0x18004e253  mov     rcx, rdi
0x18004e256  call    _tlgWriteTransfer_EventWriteTransfer
0x18004e25b  cmp     dword ptr [rbx+138h], 0
0x18004e262  jnz     short loc_18004E2A0
0x18004e264  add     rbx, 120h
0x18004e26b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004e273  jz      short loc_18004E299
0x18004e275  mov     dl, 1
0x18004e277  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004e27c  mov     [rbx], rax
0x18004e27f  test    rax, rax
0x18004e282  jz      short loc_18004E2A0
0x18004e284  mov     rcx, [rax]
0x18004e287  mov     [rbx+10h], rcx
0x18004e28b  mov     [rax], rbx
0x18004e28e  call    cs:__imp_GetCurrentThreadId
0x18004e294  mov     [rbx+18h], eax
0x18004e297  jmp     short loc_18004E2A0
0x18004e299  mov     qword ptr [rbx], 0
0x18004e2a0  mov     rcx, [rbp+57h+var_30]
0x18004e2a4  xor     rcx, rsp; StackCookie
0x18004e2a7  call    __security_check_cookie
0x18004e2ac  add     rsp, 98h
0x18004e2b3  pop     r14
0x18004e2b5  pop     rdi
0x18004e2b6  pop     rbx
0x18004e2b7  pop     rbp
0x18004e2b8  retn
```
