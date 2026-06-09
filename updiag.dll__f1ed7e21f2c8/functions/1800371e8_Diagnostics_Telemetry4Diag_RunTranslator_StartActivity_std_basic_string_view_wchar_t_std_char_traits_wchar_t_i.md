# Diagnostics::Telemetry4Diag::RunTranslator::StartActivity(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,int)

- ea: `0x1800371e8`
- end: `0x1800373a2`
- name: `?StartActivity@RunTranslator@Telemetry4Diag@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@H@Z`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003befc`

## callees

- `0x180001350`
- `0x1800080f8`
- `0x18000bba4`
- `0x180015f28`
- `0x1800371e8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037263`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003736b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037263`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003736b`

## pseudocode

```c
int __fastcall Diagnostics::Telemetry4Diag::RunTranslator::StartActivity(__int64 a1, const wchar_t **a2, int a3)
{
  struct Diagnostics::Telemetry4Diag *Local; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rsi
  const wchar_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rbx
  int v18; // [rsp+38h] [rbp-49h] BYREF
  DWORD v19; // [rsp+3Ch] [rbp-45h] BYREF
  __int64 v20; // [rsp+40h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+48h] [rbp-39h] BYREF
  __int64 *v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  DWORD *v24; // [rsp+78h] [rbp-9h]
  __int64 v25; // [rsp+80h] [rbp-1h]
  const wchar_t *v26; // [rsp+88h] [rbp+7h]
  int v27; // [rsp+90h] [rbp+Fh]
  int v28; // [rsp+94h] [rbp+13h]
  int *v29; // [rsp+98h] [rbp+17h]
  __int64 v30; // [rsp+A0h] [rbp+1Fh]
  const char *v31; // [rsp+A8h] [rbp+27h]
  __int64 v32; // [rsp+B0h] [rbp+2Fh]

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
        v18 = a3;
        v10 = *a2;
        CurrentThreadId = GetCurrentThreadId();
        v12 = *(_QWORD *)(a1 + 272);
        v19 = CurrentThreadId;
        v20 = 0x1000000;
        if ( !*(_BYTE *)(v12 + 4)
          || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
          && !*(_DWORD *)(v12 + 28)
          && !*(_DWORD *)(v12 + 32)
          && !*(_DWORD *)(v12 + 36) )
        {
          v13 = 0;
        }
        v32 = 18;
        v31 = "1507.2603.28012.0";
        v29 = &v18;
        v30 = 4;
        if ( v10 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v10[v14] );
          v15 = 2 * v14 + 2;
        }
        else
        {
          v10 = &psz;
          v15 = 2;
        }
        v27 = v15;
        v26 = v10;
        v24 = &v19;
        v28 = 0;
        v22 = &v20;
        v25 = 4;
        v23 = 8;
        LODWORD(Local) = tlgWriteTransfer_EventWriteTransfer(v9, (int)&qword_1801722E0, (int)v12 + 8, v13, 7u, &v21);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v16 = a1 + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v7) = 1;
      Local = (struct Diagnostics::Telemetry4Diag *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                      v8,
                                                      v7);
      *(_QWORD *)v16 = Local;
      if ( Local )
      {
        *(_QWORD *)(v16 + 16) = *(_QWORD *)Local;
        *(_QWORD *)Local = v16;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(v16 + 24) = (_DWORD)Local;
      }
    }
    else
    {
      *(_QWORD *)v16 = 0;
    }
  }
  return (int)Local;
}

```

## disassembly

```asm
0x1800371e8  mov     rax, rsp
0x1800371eb  mov     [rax+10h], rbx
0x1800371ef  mov     [rax+18h], rsi
0x1800371f3  mov     [rax+20h], rdi
0x1800371f7  push    rbp
0x1800371f8  push    r14
0x1800371fa  push    r15
0x1800371fc  lea     rbp, [rax-5Fh]
0x180037200  sub     rsp, 0C0h
0x180037207  mov     rax, cs:__security_cookie
0x18003720e  xor     rax, rsp
0x180037211  mov     [rbp+57h+var_20], rax
0x180037215  mov     edi, r8d
0x180037218  mov     r14, rdx
0x18003721b  mov     rbx, rcx
0x18003721e  call    ?zInternalStart@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180037223  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180037228  xor     r15d, r15d
0x18003722b  mov     rsi, [rax+8]
0x18003722f  cmp     dword ptr [rsi], 5
0x180037232  jbe     loc_180037339
0x180037238  mov     rcx, 400000000000h
0x180037242  test    [rsi+10h], rcx
0x180037246  jz      loc_180037339
0x18003724c  mov     rax, [rsi+18h]
0x180037250  and     rax, rcx
0x180037253  cmp     rax, [rsi+18h]
0x180037257  jnz     loc_180037339
0x18003725d  mov     [rbp+57h+var_A0], edi
0x180037260  mov     rdi, [r14]
0x180037263  call    cs:__imp_GetCurrentThreadId
0x180037269  mov     r8, [rbx+110h]
0x180037270  mov     [rbp+57h+var_9C], eax
0x180037273  mov     [rbp+57h+var_98], 1000000h
0x18003727b  cmp     [r8+4], r15b
0x18003727f  jz      short loc_18003729C
0x180037281  lea     r9, [r8+18h]
0x180037285  cmp     [r9], r15d
0x180037288  jnz     short loc_18003729F
0x18003728a  cmp     [r9+4], r15d
0x18003728e  jnz     short loc_18003729F
0x180037290  cmp     [r9+8], r15d
0x180037294  jnz     short loc_18003729F
0x180037296  cmp     [r9+0Ch], r15d
0x18003729a  jnz     short loc_18003729F
0x18003729c  mov     r9, r15; int
0x18003729f  mov     [rbp+57h+var_28], 12h
0x1800372a7  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800372ae  mov     [rbp+57h+var_30], rax
0x1800372b2  lea     rax, [rbp+57h+var_A0]
0x1800372b6  mov     [rbp+57h+var_40], rax
0x1800372ba  mov     [rbp+57h+var_38], 4
0x1800372c2  test    rdi, rdi
0x1800372c5  jz      short loc_1800372DE
0x1800372c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800372cb  inc     rax
0x1800372ce  cmp     [rdi+rax*2], r15w
0x1800372d3  jnz     short loc_1800372CB
0x1800372d5  lea     eax, ds:2[rax*2]
0x1800372dc  jmp     short loc_1800372EA
0x1800372de  lea     rdi, psz
0x1800372e5  mov     eax, 2
0x1800372ea  mov     [rbp+57h+var_48], eax
0x1800372ed  lea     rdx, qword_1801722E0; int
0x1800372f4  lea     rax, [rbp+57h+var_9C]
0x1800372f8  mov     [rbp+57h+var_50], rdi
0x1800372fc  mov     [rbp+57h+var_60], rax
0x180037300  add     r8, 8; int
0x180037304  lea     rax, [rbp+57h+var_98]
0x180037308  mov     [rbp+57h+var_44], r15d
0x18003730c  mov     [rbp+57h+var_70], rax
0x180037310  mov     rcx, rsi; int
0x180037313  lea     rax, [rbp+57h+var_90]
0x180037317  mov     [rbp+57h+var_58], 4
0x18003731f  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180037324  mov     [rsp+0D0h+var_B0], 7; ULONG
0x18003732c  mov     [rbp+57h+var_68], 8
0x180037334  call    _tlgWriteTransfer_EventWriteTransfer
0x180037339  cmp     [rbx+138h], r15d
0x180037340  jnz     short loc_180037379
0x180037342  add     rbx, 120h
0x180037349  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180037350  jz      short loc_180037376
0x180037352  mov     dl, 1
0x180037354  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180037359  mov     [rbx], rax
0x18003735c  test    rax, rax
0x18003735f  jz      short loc_180037379
0x180037361  mov     rcx, [rax]
0x180037364  mov     [rbx+10h], rcx
0x180037368  mov     [rax], rbx
0x18003736b  call    cs:__imp_GetCurrentThreadId
0x180037371  mov     [rbx+18h], eax
0x180037374  jmp     short loc_180037379
0x180037376  mov     [rbx], r15
0x180037379  mov     rcx, [rbp+57h+var_20]
0x18003737d  xor     rcx, rsp; StackCookie
0x180037380  call    __security_check_cookie
0x180037385  lea     r11, [rsp+0D0h+var_10]
0x18003738d  mov     rbx, [r11+28h]
0x180037391  mov     rsi, [r11+30h]
0x180037395  mov     rdi, [r11+38h]
0x180037399  mov     rsp, r11
0x18003739c  pop     r15
0x18003739e  pop     r14
0x1800373a0  pop     rbp
0x1800373a1  retn
```
