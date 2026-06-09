# MixedContentTelemetry::MixedContentFileInfo<wchar_t const * const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &>(wchar_t const * const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &)

- ea: `0x18000e034`
- end: `0x18000e225`
- name: `??$MixedContentFileInfo@AEBQEB_WAEB_KAEB_KAEB_KAEB_K@MixedContentTelemetry@@SAXAEBQEB_WAEB_K111@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014030`

## callees

- `0x18000163c`
- `0x180001e40`
- `0x180002284`
- `0x18000e034`
- `0x180014948`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e080`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e080`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e0f5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e0f5`

## pseudocode

```c
int __fastcall MixedContentTelemetry::MixedContentFileInfo<wchar_t const * const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &>(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4,
        __int64 *a5)
{
  void (*v8)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  __int64 v9; // r10
  __int64 v10; // rax
  __int64 v11; // rcx
  int *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  LPVOID Context; // [rsp+30h] [rbp-A1h] BYREF
  BOOL fPending[2]; // [rsp+38h] [rbp-99h] BYREF
  __int64 v18; // [rsp+40h] [rbp-91h] BYREF
  __int64 v19; // [rsp+48h] [rbp-89h] BYREF
  __int64 v20; // [rsp+50h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+60h] [rbp-71h] BYREF
  int *v22; // [rsp+80h] [rbp-51h]
  int v23; // [rsp+88h] [rbp-49h]
  int v24; // [rsp+8Ch] [rbp-45h]
  __int64 *v25; // [rsp+90h] [rbp-41h]
  __int64 v26; // [rsp+98h] [rbp-39h]
  __int64 *v27; // [rsp+A0h] [rbp-31h]
  __int64 v28; // [rsp+A8h] [rbp-29h]
  __int64 *v29; // [rsp+B0h] [rbp-21h]
  __int64 v30; // [rsp+B8h] [rbp-19h]
  BOOL *v31; // [rsp+C0h] [rbp-11h]
  __int64 v32; // [rsp+C8h] [rbp-9h]
  LPVOID *p_Context; // [rsp+D0h] [rbp-1h]
  __int64 v34; // [rsp+D8h] [rbp+7h]

  Context = 0;
  fPending[0] = 0;
  if ( InitOnceBeginInitialize(&`MixedContentLogging::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
  {
    qword_1800239F8 = 0;
    Context = &qword_1800239F0;
    qword_1800239F0 = &SearchIndexerTraceProvider::`vftable';
    byte_180023A00 = 0;
    dword_180023A04 = 0;
    qword_180023A08 = (struct _tlgProvider_t *)&`MixedContentLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8662061d6f2ff692cec6a717bc60066d_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800239F0, qword_180023A08, v8);
    InitOnceComplete(&`MixedContentLogging::Instance'::`2'::wrapper, 0, &qword_1800239F0);
  }
  v9 = *((_QWORD *)Context + 1);
  LODWORD(v10) = *(_DWORD *)v9;
  if ( *(_DWORD *)v9 > 5u )
  {
    v10 = *(_QWORD *)(v9 + 16);
    if ( (v10 & 0x400000000000LL) != 0 )
    {
      LODWORD(v10) = 0;
      if ( (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
      {
        Context = (LPVOID)0x1000000;
        v34 = 8;
        v32 = 8;
        v11 = *a5;
        v18 = *a4;
        v19 = *a3;
        v20 = *a2;
        p_Context = &Context;
        v31 = fPending;
        v29 = &v18;
        *(_QWORD *)fPending = v11;
        v12 = (int *)L".rtf";
        v27 = &v19;
        v25 = &v20;
        v30 = 8;
        v28 = 8;
        v26 = 8;
        if ( L".rtf" )
        {
          v13 = -1;
          do
            ++v13;
          while ( aRtf[v13] );
          v14 = 2 * v13 + 2;
        }
        else
        {
          v12 = &dword_18001CFD4;
          v14 = 2;
        }
        v23 = v14;
        v22 = v12;
        v24 = 0;
        LODWORD(v10) = tlgWriteTransfer_EventWriteTransfer(v9, (unsigned __int8 *)word_18001EFBA, 0, 0, 8u, &v21);
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000e034  push    rbp
0x18000e036  push    rbx
0x18000e037  push    rsi
0x18000e038  push    rdi
0x18000e039  push    r14
0x18000e03b  push    r15
0x18000e03d  lea     rbp, [rsp-27h]
0x18000e042  sub     rsp, 0F8h
0x18000e049  mov     rax, cs:__security_cookie
0x18000e050  xor     rax, rsp
0x18000e053  mov     [rbp+4Fh+var_40], rax
0x18000e057  mov     rbx, r9
0x18000e05a  lea     rcx, ?wrapper@?1??Instance@MixedContentLogging@@KAPEAV2@XZ@4V?$static_lazy@VMixedContentLogging@@@details@wil@@A; lpInitOnce
0x18000e061  mov     rdi, r8
0x18000e064  lea     r9, [rsp+120h+Context]; lpContext
0x18000e069  mov     rsi, rdx
0x18000e06c  lea     r8, [rsp+120h+fPending]; fPending
0x18000e071  xor     r15d, r15d
0x18000e074  xor     edx, edx; dwFlags
0x18000e076  mov     [rsp+120h+Context], r15
0x18000e07b  mov     [rsp+120h+fPending], r15d
0x18000e080  call    cs:__imp_InitOnceBeginInitialize
0x18000e086  test    eax, eax
0x18000e088  jz      short loc_18000E0FB
0x18000e08a  cmp     [rsp+120h+fPending], r15d
0x18000e08f  jz      short loc_18000E0FB
0x18000e091  lea     r14, qword_1800239F0
0x18000e098  mov     cs:qword_1800239F8, r15
0x18000e09f  lea     rax, ??_7SearchIndexerTraceProvider@@6B@; const SearchIndexerTraceProvider::`vftable'
0x18000e0a6  mov     [rsp+120h+Context], r14
0x18000e0ab  mov     cs:qword_1800239F0, rax
0x18000e0b2  mov     cs:byte_180023A00, r15b
0x18000e0b9  mov     cs:dword_180023A04, r15d
0x18000e0c0  lea     rax, ?__hInner@?1???0StaticHandle@MixedContentLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MixedContentLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e0c7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8662061d6f2ff692cec6a717bc60066d_@@CA@XZ; void (__cdecl *)()
0x18000e0ce  mov     cs:qword_180023A08, rax
0x18000e0d5  call    atexit
0x18000e0da  mov     rdx, cs:qword_180023A08; struct _tlgProvider_t *
0x18000e0e1  mov     rcx, r14; this
0x18000e0e4  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000e0e9  mov     r8, r14; lpContext
0x18000e0ec  lea     rcx, ?wrapper@?1??Instance@MixedContentLogging@@KAPEAV2@XZ@4V?$static_lazy@VMixedContentLogging@@@details@wil@@A; lpInitOnce
0x18000e0f3  xor     edx, edx; dwFlags
0x18000e0f5  call    cs:__imp_InitOnceComplete
0x18000e0fb  mov     rax, [rsp+120h+Context]
0x18000e100  mov     r10, [rax+8]
0x18000e104  mov     eax, [r10]
0x18000e107  cmp     eax, 5
0x18000e10a  jbe     loc_18000E209
0x18000e110  mov     rcx, [r10+18h]
0x18000e114  mov     rdx, 400000000000h
0x18000e11e  mov     rax, [r10+10h]
0x18000e122  test    rdx, rax
0x18000e125  jz      loc_18000E209
0x18000e12b  mov     rax, rcx
0x18000e12e  and     rax, rdx
0x18000e131  cmp     rax, rcx
0x18000e134  jnz     loc_18000E209
0x18000e13a  mov     rax, [rbp+4Fh+arg_20]
0x18000e13e  mov     edx, 8
0x18000e143  mov     [rsp+120h+Context], 1000000h
0x18000e14c  mov     [rbp+4Fh+var_48], rdx
0x18000e150  mov     [rbp+4Fh+var_58], rdx
0x18000e154  mov     rcx, [rax]
0x18000e157  mov     rax, [rbx]
0x18000e15a  mov     [rsp+120h+var_E0], rax
0x18000e15f  mov     rax, [rdi]
0x18000e162  mov     [rsp+120h+var_D8], rax
0x18000e167  mov     rax, [rsi]
0x18000e16a  mov     [rsp+120h+var_D0], rax
0x18000e16f  lea     rax, [rsp+120h+Context]
0x18000e174  mov     [rbp+4Fh+var_50], rax
0x18000e178  lea     rax, [rsp+120h+fPending]
0x18000e17d  mov     [rbp+4Fh+var_60], rax
0x18000e181  lea     rax, [rsp+120h+var_E0]
0x18000e186  mov     [rbp+4Fh+var_70], rax
0x18000e18a  lea     rax, [rsp+120h+var_D8]
0x18000e18f  mov     qword ptr [rsp+120h+fPending], rcx
0x18000e194  mov     rcx, cs:off_18001C4C0; ".rtf"
0x18000e19b  mov     [rbp+4Fh+var_80], rax
0x18000e19f  lea     rax, [rsp+120h+var_D0]
0x18000e1a4  mov     [rbp+4Fh+var_90], rax
0x18000e1a8  mov     [rbp+4Fh+var_68], rdx
0x18000e1ac  mov     [rbp+4Fh+var_78], rdx
0x18000e1b0  mov     [rbp+4Fh+var_88], rdx
0x18000e1b4  test    rcx, rcx
0x18000e1b7  jz      short loc_18000E1D0
0x18000e1b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e1bd  inc     rax
0x18000e1c0  cmp     [rcx+rax*2], r15w
0x18000e1c5  jnz     short loc_18000E1BD
0x18000e1c7  lea     eax, ds:2[rax*2]
0x18000e1ce  jmp     short loc_18000E1DC
0x18000e1d0  lea     rcx, dword_18001CFD4
0x18000e1d7  mov     eax, 2
0x18000e1dc  mov     [rbp+4Fh+var_98], eax
0x18000e1df  xor     r9d, r9d
0x18000e1e2  lea     rax, [rbp+4Fh+var_C0]
0x18000e1e6  mov     [rbp+4Fh+var_A0], rcx
0x18000e1ea  mov     [rsp+120h+var_F8], rax
0x18000e1ef  xor     r8d, r8d
0x18000e1f2  mov     [rsp+120h+var_100], edx
0x18000e1f6  mov     rcx, r10
0x18000e1f9  lea     rdx, word_18001EFBA
0x18000e200  mov     [rbp+4Fh+var_94], r15d
0x18000e204  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e209  mov     rcx, [rbp+4Fh+var_40]
0x18000e20d  xor     rcx, rsp; StackCookie
0x18000e210  call    __security_check_cookie
0x18000e215  add     rsp, 0F8h
0x18000e21c  pop     r15
0x18000e21e  pop     r14
0x18000e220  pop     rdi
0x18000e221  pop     rsi
0x18000e222  pop     rbx
0x18000e223  pop     rbp
0x18000e224  retn
```
