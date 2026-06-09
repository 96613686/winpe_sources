# Diagnostics::Telemetry4Diag::RunAnalyzer::StartActivity(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wchar_t const *)

- ea: `0x1800360f8`
- end: `0x1800362db`
- name: `?StartActivity@RunAnalyzer@Telemetry4Diag@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEB_W@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180038fe8`

## callees

- `0x180001350`
- `0x1800080f8`
- `0x18000bba4`
- `0x180015f28`
- `0x1800360f8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003617e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800362a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003617e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800362a5`

## pseudocode

```c
int __fastcall Diagnostics::Telemetry4Diag::RunAnalyzer::StartActivity(
        __int64 a1,
        const wchar_t **a2,
        const wchar_t *a3)
{
  struct Diagnostics::Telemetry4Diag *Local; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r15
  const wchar_t *v10; // rbx
  const wchar_t *v11; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ecx
  struct Diagnostics::Telemetry4Diag **v19; // rbx
  DWORD v21; // [rsp+30h] [rbp-59h] BYREF
  __int64 v22; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v24; // [rsp+60h] [rbp-29h]
  __int64 v25; // [rsp+68h] [rbp-21h]
  DWORD *v26; // [rsp+70h] [rbp-19h]
  __int64 v27; // [rsp+78h] [rbp-11h]
  const wchar_t *v28; // [rsp+80h] [rbp-9h]
  int v29; // [rsp+88h] [rbp-1h]
  int v30; // [rsp+8Ch] [rbp+3h]
  const wchar_t *v31; // [rsp+90h] [rbp+7h]
  int v32; // [rsp+98h] [rbp+Fh]
  int v33; // [rsp+9Ch] [rbp+13h]
  const char *v34; // [rsp+A0h] [rbp+17h]
  __int64 v35; // [rsp+A8h] [rbp+1Fh]

  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  Local = Diagnostics::Telemetry4Diag::Instance();
  v9 = *((_QWORD *)Local + 1);
  if ( *(_DWORD *)v9 > 5u )
  {
    v8 = 0x400000000000LL;
    if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 )
    {
      Local = (struct Diagnostics::Telemetry4Diag *)(*(_QWORD *)(v9 + 24) & 0x400000000000LL);
      if ( Local == *(struct Diagnostics::Telemetry4Diag **)(v9 + 24) )
      {
        v10 = &psz;
        if ( a3 )
          v10 = a3;
        v11 = *a2;
        CurrentThreadId = GetCurrentThreadId();
        v13 = *(_QWORD *)(a1 + 272);
        v21 = CurrentThreadId;
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
        if ( v10 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v10[v17] );
          v18 = 2 * v17 + 2;
        }
        else
        {
          v10 = &psz;
          v18 = 2;
        }
        v31 = v10;
        v32 = v18;
        v33 = 0;
        if ( v11 )
        {
          do
            ++v16;
          while ( v11[v16] );
          v15 = 2 * v16 + 2;
        }
        else
        {
          v11 = &psz;
        }
        v29 = v15;
        v26 = &v21;
        v28 = v11;
        v24 = &v22;
        v30 = 0;
        v27 = 4;
        v25 = 8;
        LODWORD(Local) = tlgWriteTransfer_EventWriteTransfer(v9, (int)&qword_180172A60, (int)v13 + 8, v14, 7u, &v23);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v19 = (struct Diagnostics::Telemetry4Diag **)(a1 + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v7) = 1;
      Local = (struct Diagnostics::Telemetry4Diag *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                      v8,
                                                      v7);
      *v19 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *(_QWORD *)Local;
        *(_QWORD *)Local = v19;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(a1 + 312) = (_DWORD)Local;
      }
    }
    else
    {
      *v19 = 0;
    }
  }
  return (int)Local;
}

```

## disassembly

```asm
0x1800360f8  mov     [rsp-8+arg_8], rbx
0x1800360fd  mov     [rsp-8+arg_10], rsi
0x180036102  push    rbp
0x180036103  push    rdi
0x180036104  push    r12
0x180036106  push    r14
0x180036108  push    r15
0x18003610a  lea     rbp, [rsp-37h]
0x18003610f  sub     rsp, 0C0h
0x180036116  mov     rax, cs:__security_cookie
0x18003611d  xor     rax, rsp
0x180036120  mov     [rbp+57h+var_30], rax
0x180036124  mov     rsi, r8
0x180036127  mov     r14, rdx
0x18003612a  mov     rdi, rcx
0x18003612d  call    ?zInternalStart@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180036132  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036137  xor     r12d, r12d
0x18003613a  mov     r15, [rax+8]
0x18003613e  cmp     dword ptr [r15], 5
0x180036142  jbe     loc_180036273
0x180036148  mov     rcx, 400000000000h
0x180036152  test    [r15+10h], rcx
0x180036156  jz      loc_180036273
0x18003615c  mov     rax, [r15+18h]
0x180036160  and     rax, rcx
0x180036163  cmp     rax, [r15+18h]
0x180036167  jnz     loc_180036273
0x18003616d  test    rsi, rsi
0x180036170  lea     rbx, psz
0x180036177  cmovnz  rbx, rsi
0x18003617b  mov     rsi, [r14]
0x18003617e  call    cs:__imp_GetCurrentThreadId
0x180036184  mov     r8, [rdi+110h]
0x18003618b  mov     [rbp+57h+var_B0], eax
0x18003618e  mov     [rbp+57h+var_A8], 1000000h
0x180036196  cmp     [r8+4], r12b
0x18003619a  jz      short loc_1800361B7
0x18003619c  lea     r9, [r8+18h]
0x1800361a0  cmp     [r9], r12d
0x1800361a3  jnz     short loc_1800361BA
0x1800361a5  cmp     [r9+4], r12d
0x1800361a9  jnz     short loc_1800361BA
0x1800361ab  cmp     [r9+8], r12d
0x1800361af  jnz     short loc_1800361BA
0x1800361b1  cmp     [r9+0Ch], r12d
0x1800361b5  jnz     short loc_1800361BA
0x1800361b7  mov     r9, r12; int
0x1800361ba  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800361c1  mov     [rbp+57h+var_38], 12h
0x1800361c9  mov     [rbp+57h+var_40], rax
0x1800361cd  mov     edx, 2
0x1800361d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800361d6  test    rbx, rbx
0x1800361d9  jz      short loc_1800361F1
0x1800361db  mov     rcx, rax
0x1800361de  inc     rcx
0x1800361e1  cmp     [rbx+rcx*2], r12w
0x1800361e6  jnz     short loc_1800361DE
0x1800361e8  lea     ecx, ds:2[rcx*2]
0x1800361ef  jmp     short loc_1800361FA
0x1800361f1  lea     rbx, psz
0x1800361f8  mov     ecx, edx
0x1800361fa  mov     [rbp+57h+var_50], rbx
0x1800361fe  mov     [rbp+57h+var_48], ecx
0x180036201  mov     [rbp+57h+var_44], r12d
0x180036205  test    rsi, rsi
0x180036208  jz      short loc_18003621D
0x18003620a  inc     rax
0x18003620d  cmp     [rsi+rax*2], r12w
0x180036212  jnz     short loc_18003620A
0x180036214  lea     edx, ds:2[rax*2]
0x18003621b  jmp     short loc_180036224
0x18003621d  lea     rsi, psz
0x180036224  lea     rax, [rbp+57h+var_B0]
0x180036228  mov     [rbp+57h+var_58], edx
0x18003622b  mov     [rbp+57h+var_70], rax
0x18003622f  lea     rdx, qword_180172A60; int
0x180036236  lea     rax, [rbp+57h+var_A8]
0x18003623a  mov     [rbp+57h+var_60], rsi
0x18003623e  mov     [rbp+57h+var_80], rax
0x180036242  add     r8, 8; int
0x180036246  lea     rax, [rbp+57h+var_A0]
0x18003624a  mov     [rbp+57h+var_54], r12d
0x18003624e  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x180036253  mov     rcx, r15; int
0x180036256  mov     [rsp+0E0h+var_C0], 7; ULONG
0x18003625e  mov     [rbp+57h+var_68], 4
0x180036266  mov     [rbp+57h+var_78], 8
0x18003626e  call    _tlgWriteTransfer_EventWriteTransfer
0x180036273  cmp     [rdi+138h], r12d
0x18003627a  jnz     short loc_1800362B3
0x18003627c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r12; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180036283  lea     rbx, [rdi+120h]
0x18003628a  jz      short loc_1800362B0
0x18003628c  mov     dl, 1
0x18003628e  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180036293  mov     [rbx], rax
0x180036296  test    rax, rax
0x180036299  jz      short loc_1800362B3
0x18003629b  mov     rcx, [rax]
0x18003629e  mov     [rbx+10h], rcx
0x1800362a2  mov     [rax], rbx
0x1800362a5  call    cs:__imp_GetCurrentThreadId
0x1800362ab  mov     [rbx+18h], eax
0x1800362ae  jmp     short loc_1800362B3
0x1800362b0  mov     [rbx], r12
0x1800362b3  mov     rcx, [rbp+57h+var_30]
0x1800362b7  xor     rcx, rsp; StackCookie
0x1800362ba  call    __security_check_cookie
0x1800362bf  lea     r11, [rsp+0E0h+var_20]
0x1800362c7  mov     rbx, [r11+38h]
0x1800362cb  mov     rsi, [r11+40h]
0x1800362cf  mov     rsp, r11
0x1800362d2  pop     r15
0x1800362d4  pop     r14
0x1800362d6  pop     r12
0x1800362d8  pop     rdi
0x1800362d9  pop     rbp
0x1800362da  retn
```
