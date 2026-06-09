# Telemetry4UpdateCli::RunCmd::StartActivity(wchar_t const *,wchar_t const *)

- ea: `0x18000acf4`
- end: `0x18000af35`
- name: `?StartActivity@RunCmd@Telemetry4UpdateCli@@QEAAXPEB_W0@Z`
- size: `577`
- prototype: `void __fastcall(Telemetry4UpdateCli::RunCmd *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800084bc`

## callees

- `0x180001350`
- `0x180004158`
- `0x1800070ac`
- `0x18000acf4`
- `0x18000d038`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad97`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ad79`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ad79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000addb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aefa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000addb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aefa`

## pseudocode

```c
void __fastcall Telemetry4UpdateCli::RunCmd::StartActivity(
        Telemetry4UpdateCli::RunCmd *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdi
  char *v11; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ecx
  _QWORD *v19; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-59h] BYREF
  __int64 v22; // [rsp+40h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+48h] [rbp-49h] BYREF
  __int64 *v24; // [rsp+68h] [rbp-29h]
  __int64 v25; // [rsp+70h] [rbp-21h]
  PSRWLOCK *p_SRWLock; // [rsp+78h] [rbp-19h]
  __int64 v27; // [rsp+80h] [rbp-11h]
  const wchar_t *v28; // [rsp+88h] [rbp-9h]
  int v29; // [rsp+90h] [rbp-1h]
  int v30; // [rsp+94h] [rbp+3h]
  char *v31; // [rsp+98h] [rbp+7h]
  int v32; // [rsp+A0h] [rbp+Fh]
  int v33; // [rsp+A4h] [rbp+13h]
  const char *v34; // [rsp+A8h] [rbp+17h]
  __int64 v35; // [rsp+B0h] [rbp+1Fh]

  SRWLock = 0;
  wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
  if ( *(_DWORD *)v7 > 5u
    && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
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
  v10 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
  if ( *(_DWORD *)v10 > 5u
    && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
  {
    v11 = byte_180018020;
    if ( a3 )
      v11 = (char *)a3;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v22 = 0x1000000;
    if ( !*(_BYTE *)(v13 + 4)
      || (v14 = v13 + 24, !*(_DWORD *)(v13 + 24))
      && !*(_DWORD *)(v13 + 28)
      && !*(_DWORD *)(v13 + 32)
      && !*(_DWORD *)(v13 + 36) )
    {
      v14 = 0;
    }
    v35 = 18;
    v34 = "1507.2603.28012.0";
    v15 = 2;
    v16 = -1;
    if ( v11 )
    {
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v11[2 * v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v11 = byte_180018020;
      v18 = 2;
    }
    v31 = v11;
    v32 = v18;
    v33 = 0;
    if ( a2 )
    {
      do
        ++v16;
      while ( a2[v16] );
      v15 = 2 * v16 + 2;
    }
    else
    {
      a2 = (const wchar_t *)byte_180018020;
    }
    v29 = v15;
    p_SRWLock = &SRWLock;
    v28 = a2;
    v24 = &v22;
    v30 = 0;
    v27 = 4;
    v25 = 8;
    tlgWriteTransfer_EventWriteTransfer(v10, (int)&word_18001A9D2, v13 + 8, v14, 7u, &v23);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v19 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v9,
                          1);
      *v19 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v19;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v19 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000acf4  mov     rax, rsp
0x18000acf7  mov     [rax+10h], rbx
0x18000acfb  mov     [rax+18h], rsi
0x18000acff  mov     [rax+20h], rdi
0x18000ad03  push    rbp
0x18000ad04  push    r12
0x18000ad06  push    r13
0x18000ad08  push    r14
0x18000ad0a  push    r15
0x18000ad0c  lea     rbp, [rax-5Fh]
0x18000ad10  sub     rsp, 0C0h
0x18000ad17  mov     rax, cs:__security_cookie
0x18000ad1e  xor     rax, rsp
0x18000ad21  mov     [rbp+57h+var_30], rax
0x18000ad25  mov     r14, rdx
0x18000ad28  xor     r12d, r12d
0x18000ad2b  lea     rdx, [rbp+57h+SRWLock]
0x18000ad2f  mov     [rbp+57h+SRWLock], r12
0x18000ad33  mov     r15, r8
0x18000ad36  mov     rsi, rcx
0x18000ad39  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ad3e  mov     rbx, [rsi+110h]
0x18000ad45  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000ad4a  mov     r13, 400000000000h
0x18000ad54  mov     rcx, [rax+8]
0x18000ad58  cmp     dword ptr [rcx], 5
0x18000ad5b  jbe     short loc_18000AD81
0x18000ad5d  test    [rcx+10h], r13
0x18000ad61  jz      short loc_18000AD81
0x18000ad63  mov     rax, [rcx+18h]
0x18000ad67  and     rax, r13
0x18000ad6a  cmp     rax, [rcx+18h]
0x18000ad6e  jnz     short loc_18000AD81
0x18000ad70  lea     rdx, [rbx+8]; ActivityId
0x18000ad74  lea     ecx, [r12+3]; ControlCode
0x18000ad79  call    cs:__imp_EventActivityIdControl
0x18000ad7f  jmp     short loc_18000AD88
0x18000ad81  xorps   xmm0, xmm0
0x18000ad84  movups  xmmword ptr [rbx+8], xmm0
0x18000ad88  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000ad8c  mov     dword ptr [rbx], 1
0x18000ad92  test    rcx, rcx
0x18000ad95  jz      short loc_18000AD9D
0x18000ad97  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad9d  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000ada2  mov     rdi, [rax+8]
0x18000ada6  cmp     dword ptr [rdi], 5
0x18000ada9  jbe     loc_18000AEC8
0x18000adaf  test    [rdi+10h], r13
0x18000adb3  jz      loc_18000AEC8
0x18000adb9  mov     rax, [rdi+18h]
0x18000adbd  and     rax, r13
0x18000adc0  cmp     rax, [rdi+18h]
0x18000adc4  jnz     loc_18000AEC8
0x18000adca  lea     r13, byte_180018020
0x18000add1  test    r15, r15
0x18000add4  mov     rbx, r13
0x18000add7  cmovnz  rbx, r15
0x18000addb  call    cs:__imp_GetCurrentThreadId
0x18000ade1  mov     r8, [rsi+110h]
0x18000ade8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000adeb  mov     [rbp+57h+var_A8], 1000000h
0x18000adf3  cmp     [r8+4], r12b
0x18000adf7  jz      short loc_18000AE14
0x18000adf9  lea     r9, [r8+18h]
0x18000adfd  cmp     [r9], r12d
0x18000ae00  jnz     short loc_18000AE17
0x18000ae02  cmp     [r9+4], r12d
0x18000ae06  jnz     short loc_18000AE17
0x18000ae08  cmp     [r9+8], r12d
0x18000ae0c  jnz     short loc_18000AE17
0x18000ae0e  cmp     [r9+0Ch], r12d
0x18000ae12  jnz     short loc_18000AE17
0x18000ae14  mov     r9, r12; int
0x18000ae17  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18000ae1e  mov     [rbp+57h+var_38], 12h
0x18000ae26  mov     [rbp+57h+var_40], rax
0x18000ae2a  mov     edx, 2
0x18000ae2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae33  test    rbx, rbx
0x18000ae36  jz      short loc_18000AE4E
0x18000ae38  mov     rcx, rax
0x18000ae3b  inc     rcx
0x18000ae3e  cmp     [rbx+rcx*2], r12w
0x18000ae43  jnz     short loc_18000AE3B
0x18000ae45  lea     ecx, ds:2[rcx*2]
0x18000ae4c  jmp     short loc_18000AE53
0x18000ae4e  mov     rbx, r13
0x18000ae51  mov     ecx, edx
0x18000ae53  mov     [rbp+57h+var_50], rbx
0x18000ae57  mov     [rbp+57h+var_48], ecx
0x18000ae5a  mov     [rbp+57h+var_44], r12d
0x18000ae5e  test    r14, r14
0x18000ae61  jz      short loc_18000AE76
0x18000ae63  inc     rax
0x18000ae66  cmp     [r14+rax*2], r12w
0x18000ae6b  jnz     short loc_18000AE63
0x18000ae6d  lea     edx, ds:2[rax*2]
0x18000ae74  jmp     short loc_18000AE79
0x18000ae76  mov     r14, r13
0x18000ae79  lea     rax, [rbp+57h+SRWLock]
0x18000ae7d  mov     [rbp+57h+var_58], edx
0x18000ae80  mov     [rbp+57h+var_70], rax
0x18000ae84  lea     rdx, word_18001A9D2; int
0x18000ae8b  lea     rax, [rbp+57h+var_A8]
0x18000ae8f  mov     [rbp+57h+var_60], r14
0x18000ae93  mov     [rbp+57h+var_80], rax
0x18000ae97  add     r8, 8; int
0x18000ae9b  lea     rax, [rbp+57h+var_A0]
0x18000ae9f  mov     [rbp+57h+var_54], r12d
0x18000aea3  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x18000aea8  mov     rcx, rdi; int
0x18000aeab  mov     [rsp+0E0h+var_C0], 7; ULONG
0x18000aeb3  mov     [rbp+57h+var_68], 4
0x18000aebb  mov     [rbp+57h+var_78], 8
0x18000aec3  call    _tlgWriteTransfer_EventWriteTransfer
0x18000aec8  cmp     [rsi+138h], r12d
0x18000aecf  jnz     short loc_18000AF08
0x18000aed1  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r12; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000aed8  lea     rbx, [rsi+120h]
0x18000aedf  jz      short loc_18000AF05
0x18000aee1  mov     dl, 1
0x18000aee3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000aee8  mov     [rbx], rax
0x18000aeeb  test    rax, rax
0x18000aeee  jz      short loc_18000AF08
0x18000aef0  mov     rcx, [rax]
0x18000aef3  mov     [rbx+10h], rcx
0x18000aef7  mov     [rax], rbx
0x18000aefa  call    cs:__imp_GetCurrentThreadId
0x18000af00  mov     [rbx+18h], eax
0x18000af03  jmp     short loc_18000AF08
0x18000af05  mov     [rbx], r12
0x18000af08  mov     rcx, [rbp+57h+var_30]
0x18000af0c  xor     rcx, rsp; StackCookie
0x18000af0f  call    __security_check_cookie
0x18000af14  lea     r11, [rsp+0E0h+var_20]
0x18000af1c  mov     rbx, [r11+38h]
0x18000af20  mov     rsi, [r11+40h]
0x18000af24  mov     rdi, [r11+48h]
0x18000af28  mov     rsp, r11
0x18000af2b  pop     r15
0x18000af2d  pop     r14
0x18000af2f  pop     r13
0x18000af31  pop     r12
0x18000af33  pop     rbp
0x18000af34  retn
```
