# WhesvcTelemetryProvider::WhesvcModuleActivity::StartActivity(char const *,char const *)

- ea: `0x1800238cc`
- end: `0x180023adf`
- name: `?StartActivity@WhesvcModuleActivity@WhesvcTelemetryProvider@@QEAAXPEBD0@Z`
- size: `531`
- prototype: `void __fastcall(WhesvcTelemetryProvider::WhesvcModuleActivity *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001b290`

## callees

- `0x1800018dc`
- `0x1800032e0`
- `0x1800084d0`
- `0x18000a9ac`
- `0x18000ae4c`
- `0x1800238cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023aa9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023969`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180023948`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180023948`

## pseudocode

```c
void __fastcall WhesvcTelemetryProvider::WhesvcModuleActivity::StartActivity(
        WhesvcTelemetryProvider::WhesvcModuleActivity *this,
        const char *a2,
        const char *a3)
{
  __int64 v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  RTL_SRWLOCK *v8; // rcx
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // eax
  _QWORD *v20; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-49h] BYREF
  __int64 v23; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v24[32]; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v25; // [rsp+60h] [rbp-19h]
  __int64 v26; // [rsp+68h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-9h]
  __int64 v28; // [rsp+78h] [rbp-1h]
  const char *v29; // [rsp+80h] [rbp+7h]
  int v30; // [rsp+88h] [rbp+Fh]
  int v31; // [rsp+8Ch] [rbp+13h]
  const char *v32; // [rsp+90h] [rbp+17h]
  int v33; // [rsp+98h] [rbp+1Fh]
  int v34; // [rsp+9Ch] [rbp+23h]

  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = WhesvcTelemetryProvider::Provider();
  if ( *(_DWORD *)v7 > 5u
    && (*((_QWORD *)v7 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v7 + 3) & 0x200000000000LL) == *((_QWORD *)v7 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v9 = WhesvcTelemetryProvider::Provider();
  v10 = v9;
  v11 = *(unsigned int *)v9;
  if ( (unsigned int)v11 > 5 )
  {
    v12 = *((_QWORD *)v9 + 3);
    v11 = *((_QWORD *)v9 + 2);
    if ( (v11 & 0x200000000000LL) != 0 )
    {
      v11 = v12 & 0x200000000000LL;
      if ( (v12 & 0x200000000000LL) == v12 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v14 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v23 = 0;
        if ( !*(_BYTE *)(v14 + 4)
          || (v15 = v14 + 24, !*(_DWORD *)(v14 + 24))
          && !*(_DWORD *)(v14 + 28)
          && !*(_DWORD *)(v14 + 32)
          && !*(_DWORD *)(v14 + 36) )
        {
          v15 = 0;
        }
        v16 = -1;
        if ( a3 )
        {
          v17 = -1;
          do
            ++v17;
          while ( a3[v17] );
          v18 = v17 + 1;
        }
        else
        {
          a3 = (const char *)&byte_18002B291;
          v18 = 1;
        }
        v32 = a3;
        v33 = v18;
        v34 = 0;
        if ( a2 )
        {
          do
            ++v16;
          while ( a2[v16] );
          v19 = v16 + 1;
        }
        else
        {
          a2 = (const char *)&byte_18002B291;
          v19 = 1;
        }
        v30 = v19;
        v29 = a2;
        p_SRWLock = &SRWLock;
        v31 = 0;
        v25 = &v23;
        v28 = 4;
        v26 = 8;
        tlgWriteTransfer_EventWriteTransfer(v10, &byte_18002DA17, v14 + 8, v15, 6, v24);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v20 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v11,
                          1);
      *v20 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v20;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v20 = 0;
    }
  }
}

```

## disassembly

```asm
0x1800238cc  mov     [rsp-8+arg_8], rbx
0x1800238d1  mov     [rsp-8+arg_10], rsi
0x1800238d6  push    rbp
0x1800238d7  push    rdi
0x1800238d8  push    r12
0x1800238da  push    r14
0x1800238dc  push    r15
0x1800238de  lea     rbp, [rsp-37h]
0x1800238e3  sub     rsp, 0B0h
0x1800238ea  mov     rax, cs:__security_cookie
0x1800238f1  xor     rax, rsp
0x1800238f4  mov     [rbp+57h+var_30], rax
0x1800238f8  mov     r14, rdx
0x1800238fb  mov     rsi, r8
0x1800238fe  lea     rdx, [rbp+57h+SRWLock]
0x180023902  mov     rdi, rcx
0x180023905  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002390a  mov     rbx, [rdi+110h]
0x180023911  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x180023916  mov     r12, 200000000000h
0x180023920  mov     edx, [rax]
0x180023922  cmp     edx, 5
0x180023925  jbe     short loc_180023950
0x180023927  mov     rcx, [rax+18h]
0x18002392b  mov     rax, [rax+10h]
0x18002392f  test    r12, rax
0x180023932  jz      short loc_180023950
0x180023934  mov     rax, rcx
0x180023937  and     rax, r12
0x18002393a  cmp     rax, rcx
0x18002393d  jnz     short loc_180023950
0x18002393f  lea     rdx, [rbx+8]; ActivityId
0x180023943  mov     ecx, 3; ControlCode
0x180023948  call    cs:__imp_EventActivityIdControl
0x18002394e  jmp     short loc_180023957
0x180023950  xorps   xmm0, xmm0
0x180023953  movups  xmmword ptr [rbx+8], xmm0
0x180023957  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002395b  xor     r15d, r15d
0x18002395e  mov     dword ptr [rbx], 1
0x180023964  test    rcx, rcx
0x180023967  jz      short loc_18002396F
0x180023969  call    cs:__imp_ReleaseSRWLockExclusive
0x18002396f  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x180023974  mov     rbx, rax
0x180023977  mov     ecx, [rax]
0x180023979  cmp     ecx, 5
0x18002397c  jbe     loc_180023A77
0x180023982  mov     rdx, [rax+18h]
0x180023986  mov     rcx, [rax+10h]
0x18002398a  test    r12, rcx
0x18002398d  jz      loc_180023A77
0x180023993  mov     rcx, rdx
0x180023996  and     rcx, r12
0x180023999  cmp     rcx, rdx
0x18002399c  jnz     loc_180023A77
0x1800239a2  call    cs:__imp_GetCurrentThreadId
0x1800239a8  mov     r8, [rdi+110h]
0x1800239af  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800239b2  mov     [rbp+57h+var_98], r15
0x1800239b6  cmp     [r8+4], r15b
0x1800239ba  jz      short loc_1800239D7
0x1800239bc  lea     r9, [r8+18h]
0x1800239c0  cmp     [r9], r15d
0x1800239c3  jnz     short loc_1800239DA
0x1800239c5  cmp     [r9+4], r15d
0x1800239c9  jnz     short loc_1800239DA
0x1800239cb  cmp     [r9+8], r15d
0x1800239cf  jnz     short loc_1800239DA
0x1800239d1  cmp     [r9+0Ch], r15d
0x1800239d5  jnz     short loc_1800239DA
0x1800239d7  mov     r9, r15
0x1800239da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800239de  test    rsi, rsi
0x1800239e1  jz      short loc_1800239F3
0x1800239e3  mov     rcx, rax
0x1800239e6  inc     rcx
0x1800239e9  cmp     [rsi+rcx], r15b
0x1800239ed  jnz     short loc_1800239E6
0x1800239ef  inc     ecx
0x1800239f1  jmp     short loc_1800239FF
0x1800239f3  lea     rsi, byte_18002B291
0x1800239fa  mov     ecx, 1
0x1800239ff  mov     [rbp+57h+var_40], rsi
0x180023a03  mov     [rbp+57h+var_38], ecx
0x180023a06  mov     [rbp+57h+var_34], r15d
0x180023a0a  test    r14, r14
0x180023a0d  jz      short loc_180023A1C
0x180023a0f  inc     rax
0x180023a12  cmp     [r14+rax], r15b
0x180023a16  jnz     short loc_180023A0F
0x180023a18  inc     eax
0x180023a1a  jmp     short loc_180023A28
0x180023a1c  lea     r14, byte_18002B291
0x180023a23  mov     eax, 1
0x180023a28  mov     [rbp+57h+var_48], eax
0x180023a2b  lea     rdx, byte_18002DA17
0x180023a32  lea     rax, [rbp+57h+SRWLock]
0x180023a36  mov     [rbp+57h+var_50], r14
0x180023a3a  mov     [rbp+57h+var_60], rax
0x180023a3e  add     r8, 8
0x180023a42  lea     rax, [rbp+57h+var_98]
0x180023a46  mov     [rbp+57h+var_44], r15d
0x180023a4a  mov     [rbp+57h+var_70], rax
0x180023a4e  mov     rcx, rbx
0x180023a51  lea     rax, [rbp+57h+var_90]
0x180023a55  mov     [rbp+57h+var_58], 4
0x180023a5d  mov     [rsp+0D0h+var_A8], rax
0x180023a62  mov     [rsp+0D0h+var_B0], 6
0x180023a6a  mov     [rbp+57h+var_68], 8
0x180023a72  call    _tlgWriteTransfer_EventWriteTransfer
0x180023a77  cmp     [rdi+138h], r15d
0x180023a7e  jnz     short loc_180023AB7
0x180023a80  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180023a87  lea     rbx, [rdi+120h]
0x180023a8e  jz      short loc_180023AB4
0x180023a90  mov     dl, 1
0x180023a92  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180023a97  mov     [rbx], rax
0x180023a9a  test    rax, rax
0x180023a9d  jz      short loc_180023AB7
0x180023a9f  mov     rcx, [rax]
0x180023aa2  mov     [rbx+10h], rcx
0x180023aa6  mov     [rax], rbx
0x180023aa9  call    cs:__imp_GetCurrentThreadId
0x180023aaf  mov     [rbx+18h], eax
0x180023ab2  jmp     short loc_180023AB7
0x180023ab4  mov     [rbx], r15
0x180023ab7  mov     rcx, [rbp+57h+var_30]
0x180023abb  xor     rcx, rsp; StackCookie
0x180023abe  call    __security_check_cookie
0x180023ac3  lea     r11, [rsp+0D0h+var_20]
0x180023acb  mov     rbx, [r11+38h]
0x180023acf  mov     rsi, [r11+40h]
0x180023ad3  mov     rsp, r11
0x180023ad6  pop     r15
0x180023ad8  pop     r14
0x180023ada  pop     r12
0x180023adc  pop     rdi
0x180023add  pop     rbp
0x180023ade  retn
```
