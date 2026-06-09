# InputTraceLogging::PerfRegion::PerfRegion(char const *,InputTraceLogging::PerfRegion const *)

- ea: `0x180019dd0`
- end: `0x18001a0b9`
- name: `??0PerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z`
- size: `745`
- prototype: `__int64 __fastcall(InputTraceLogging::PerfRegion *__hidden this, const char *, const struct InputTraceLogging::PerfRegion *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017b00`
- `0x180018350`
- `0x18001ab80`
- `0x180031f04`

## callees

- `0x180019dd0`
- `0x1800217f0`
- `0x18005f330`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019e6b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019e6b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019f79`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019f79`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019f4a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019f4a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a094`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a094`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019f2f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019f2f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019e48`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019e48`

## pseudocode

```c
InputTraceLogging::PerfRegion *__fastcall InputTraceLogging::PerfRegion::PerfRegion(
        InputTraceLogging::PerfRegion *this,
        const char *a2,
        const struct InputTraceLogging::PerfRegion *a3)
{
  const struct _tlgProvider_t *v4; // rdx
  _QWORD *v5; // rdi
  ULONGLONG *v6; // r9
  __int64 v7; // r10
  const unsigned __int16 *v8; // rcx
  const GUID *v9; // r9
  __int64 v10; // rax
  int v11; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+38h] [rbp-70h] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-50h] BYREF
  char *v17; // [rsp+68h] [rbp-40h]
  int v18; // [rsp+70h] [rbp-38h]
  int v19; // [rsp+74h] [rbp-34h]
  const unsigned __int16 *v20; // [rsp+78h] [rbp-30h]
  int v21; // [rsp+80h] [rbp-28h]
  int v22; // [rsp+84h] [rbp-24h]

  *(_BYTE *)this = 0;
  *((_QWORD *)this + 1) = a2;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  v4 = InputTraceLogging::Provider();
  if ( *(_DWORD *)v4 > 6u && (*((_QWORD *)v4 + 2) & 1) != 0 && (*((_QWORD *)v4 + 3) & 1LL) == *((_QWORD *)v4 + 3) )
  {
    *(_BYTE *)this = 1;
    EventActivityIdControl(3u, (LPGUID)this + 1);
    *(_QWORD *)&Context.Id = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&Context)
      && fPending )
    {
      *(_QWORD *)&Context.Id = &qword_1801353C8;
      qword_1801353D0 = 0;
      byte_1801353D8 = 0;
      dword_1801353DC = 0;
      qword_1801353C8 = &PopupMenuTelemetry::`vftable';
      CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_a8e7baa2fca040c17c3e795f3590cb07_::_lambda_invoker_cdecl_);
      v5 = CallbackContext;
      qword_1801353D0 = (__int64)CallbackContext;
      byte_1801353D8 = 1;
      ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
      if ( *((_QWORD *)CallbackContext + 4) )
        __fastfail(5u);
      v6 = (ULONGLONG *)((char *)CallbackContext + 32);
      *((_QWORD *)CallbackContext + 5) = 0;
      v5[6] = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, v5, v6) )
        EventSetInformation(v5[4], 2, v5[1], *(unsigned __int16 *)v5[1]);
      dword_1801353DC = 1;
      (*(void (__fastcall **)(void *))(qword_1801353C8 + 8LL))(&qword_1801353C8);
      InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1801353C8);
    }
    v7 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
    if ( *(_DWORD *)v7 > 6u && (*(_QWORD *)(v7 + 16) & 1) != 0 && (*(_QWORD *)(v7 + 24) & 1LL) == *(_QWORD *)(v7 + 24) )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)this + 1);
      v9 = (const GUID *)*((_QWORD *)this + 6);
      if ( v8 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_BYTE *)v8 + v10) );
        v11 = v10 + 1;
      }
      else
      {
        v8 = &word_18010B172;
        v11 = 1;
      }
      v21 = v11;
      UserData.Ptr = *(_QWORD *)(v7 + 8);
      v20 = v8;
      v22 = 0;
      *(_QWORD *)&Context.Id = 0x1060B000000LL;
      Context.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v17 = byte_18011EAA5;
      UserData.Reserved = 2;
      v18 = 21;
      v19 = 1;
      fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v7 + 32), &Context, (LPCGUID)this + 1, v9, 3u, &UserData);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180019dd0  push    rbx
0x180019dd2  push    rbp
0x180019dd3  push    r14
0x180019dd5  sub     rsp, 90h
0x180019ddc  mov     rax, cs:__security_cookie
0x180019de3  xor     rax, rsp
0x180019de6  mov     [rsp+0A8h+var_20], rax
0x180019dee  xorps   xmm0, xmm0
0x180019df1  mov     byte ptr [rcx], 0
0x180019df4  mov     [rcx+8], rdx
0x180019df8  xor     r14d, r14d
0x180019dfb  movups  xmmword ptr [rcx+10h], xmm0
0x180019dff  mov     rbx, rcx
0x180019e02  movups  xmmword ptr [rcx+20h], xmm0
0x180019e06  mov     [rcx+30h], r14
0x180019e0a  call    ?Provider@InputTraceLogging@@SAPEBU_tlgProvider_t@@XZ; InputTraceLogging::Provider(void)
0x180019e0f  mov     rdx, rax
0x180019e12  mov     eax, [rax]
0x180019e14  cmp     eax, 6
0x180019e17  jbe     loc_18001A09A
0x180019e1d  mov     rcx, [rdx+18h]
0x180019e21  mov     rax, [rdx+10h]
0x180019e25  test    al, 1
0x180019e27  jz      loc_18001A09A
0x180019e2d  mov     rax, rcx
0x180019e30  and     eax, 1
0x180019e33  cmp     rax, rcx
0x180019e36  jnz     loc_18001A09A
0x180019e3c  lea     rdx, [rbx+10h]; ActivityId
0x180019e40  mov     byte ptr [rbx], 1
0x180019e43  mov     ecx, 3; ControlCode
0x180019e48  call    cs:__imp_EventActivityIdControl
0x180019e4e  lea     r9, [rsp+0A8h+Context]; lpContext
0x180019e53  mov     [rsp+0A8h+Context], r14
0x180019e58  lea     r8, [rsp+0A8h+fPending]; fPending
0x180019e5d  mov     [rsp+0A8h+fPending], r14d
0x180019e62  xor     edx, edx; dwFlags
0x180019e64  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180019e6b  call    cs:__imp_InitOnceBeginInitialize
0x180019e71  test    eax, eax
0x180019e73  jz      loc_180019F97
0x180019e79  cmp     [rsp+0A8h+fPending], r14d
0x180019e7e  jz      loc_180019F97
0x180019e84  mov     [rsp+0A8h+arg_8], rsi
0x180019e8c  lea     rax, ??_7PopupMenuTelemetry@@6B@; const PopupMenuTelemetry::`vftable'
0x180019e93  mov     [rsp+0A8h+arg_10], rdi
0x180019e9b  mov     [rsp+0A8h+arg_18], r15
0x180019ea3  lea     r15, qword_1801353C8
0x180019eaa  mov     [rsp+0A8h+Context], r15
0x180019eaf  mov     cs:qword_1801353D0, r14
0x180019eb6  mov     cs:byte_1801353D8, r14b
0x180019ebd  mov     cs:dword_1801353DC, r14d
0x180019ec4  mov     cs:qword_1801353C8, rax
0x180019ecb  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180019ed2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x180019ed9  mov     cs:CallbackContext, rax
0x180019ee0  call    atexit
0x180019ee5  mov     rdi, cs:CallbackContext
0x180019eec  mov     cs:qword_1801353D0, rdi
0x180019ef3  mov     cs:byte_1801353D8, 1
0x180019efa  mov     rax, [rdi+8]
0x180019efe  movups  xmm0, xmmword ptr [rax-10h]
0x180019f02  movups  xmmword ptr [rsp+0A8h+ProviderId.Data1], xmm0
0x180019f07  cmp     [rdi+20h], r14
0x180019f0b  jz      short loc_180019F14
0x180019f0d  mov     ecx, 5
0x180019f12  int     29h; Win8: RtlFailFast(ecx)
0x180019f14  lea     r9, [rdi+20h]; RegHandle
0x180019f18  mov     [rdi+28h], r14
0x180019f1c  mov     r8, rdi; CallbackContext
0x180019f1f  mov     [rdi+30h], r14
0x180019f23  lea     rdx, _tlgEnableCallback; EnableCallback
0x180019f2a  lea     rcx, [rsp+0A8h+ProviderId]; ProviderId
0x180019f2f  call    cs:__imp_EventRegister
0x180019f35  test    eax, eax
0x180019f37  jnz     short loc_180019F50
0x180019f39  mov     r8, [rdi+8]
0x180019f3d  mov     edx, 2
0x180019f42  mov     rcx, [rdi+20h]
0x180019f46  movzx   r9d, word ptr [r8]
0x180019f4a  call    cs:__imp_EventSetInformation
0x180019f50  mov     rax, cs:qword_1801353C8
0x180019f57  mov     rcx, r15
0x180019f5a  mov     cs:dword_1801353DC, 1
0x180019f64  mov     rax, [rax+8]
0x180019f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f6d  mov     r8, r15; lpContext
0x180019f70  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180019f77  xor     edx, edx; dwFlags
0x180019f79  call    cs:__imp_InitOnceComplete
0x180019f7f  mov     r15, [rsp+0A8h+arg_18]
0x180019f87  mov     rdi, [rsp+0A8h+arg_10]
0x180019f8f  mov     rsi, [rsp+0A8h+arg_8]
0x180019f97  mov     rax, [rsp+0A8h+Context]
0x180019f9c  mov     r10, [rax+8]
0x180019fa0  mov     eax, [r10]
0x180019fa3  cmp     eax, 6
0x180019fa6  jbe     loc_18001A09A
0x180019fac  mov     rcx, [r10+18h]
0x180019fb0  mov     rax, [r10+10h]
0x180019fb4  test    al, 1
0x180019fb6  jz      loc_18001A09A
0x180019fbc  mov     rax, rcx
0x180019fbf  and     eax, 1
0x180019fc2  cmp     rax, rcx
0x180019fc5  jnz     loc_18001A09A
0x180019fcb  mov     rcx, [rbx+8]
0x180019fcf  mov     r9, [rbx+30h]; RelatedActivityId
0x180019fd3  test    rcx, rcx
0x180019fd6  jz      short loc_180019FED
0x180019fd8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019fdf  nop
0x180019fe0  inc     rax
0x180019fe3  cmp     [rcx+rax], r14b
0x180019fe7  jnz     short loc_180019FE0
0x180019fe9  inc     eax
0x180019feb  jmp     short loc_180019FF9
0x180019fed  lea     rcx, word_18010B172
0x180019ff4  mov     eax, 1
0x180019ff9  mov     [rsp+0A8h+var_28], eax
0x18001a000  lea     rdx, _TraceLoggingMetadataEnd
0x18001a007  movzx   eax, cs:word_18011EA9B
0x18001a00e  lea     r8, [rbx+10h]; ActivityId
0x18001a012  mov     dword ptr [rsp+0A8h+Context+4], eax
0x18001a016  mov     rax, [r10+8]
0x18001a01a  mov     [rsp+0A8h+var_50.Ptr], rax
0x18001a01f  mov     [rsp+0A8h+var_30], rcx
0x18001a024  mov     [rsp+0A8h+var_24], r14d
0x18001a02c  mov     dword ptr [rsp+0A8h+Context], 0B000000h
0x18001a034  mov     [rsp+0A8h+var_68], 1
0x18001a03d  movzx   eax, word ptr [rax]
0x18001a040  mov     [rsp+0A8h+var_50.Size], eax
0x18001a044  lea     rax, byte_18011EAA5
0x18001a04b  mov     [rsp+0A8h+var_40], rax
0x18001a050  lea     rax, _TraceLoggingMetadata
0x18001a057  sub     edx, eax
0x18001a059  mov     dword ptr [rsp+0A8h+var_50.0Ch], 2
0x18001a061  mov     [rsp+0A8h+var_38], 15h
0x18001a069  lea     rax, [rsp+0A8h+var_50]
0x18001a06e  mov     [rsp+0A8h+var_34], 1
0x18001a076  mov     [rsp+0A8h+fPending], edx
0x18001a07a  mov     edx, [rsp+0A8h+fPending]
0x18001a07e  mov     rcx, [r10+20h]; RegHandle
0x18001a082  lea     rdx, [rsp+0A8h+Context]; EventDescriptor
0x18001a087  mov     [rsp+0A8h+UserData], rax; UserData
0x18001a08c  mov     [rsp+0A8h+UserDataCount], 3; UserDataCount
0x18001a094  call    cs:__imp_EventWriteTransfer
0x18001a09a  mov     rax, rbx
0x18001a09d  mov     rcx, [rsp+0A8h+var_20]
0x18001a0a5  xor     rcx, rsp; StackCookie
0x18001a0a8  call    __security_check_cookie
0x18001a0ad  add     rsp, 90h
0x18001a0b4  pop     r14
0x18001a0b6  pop     rbp
0x18001a0b7  pop     rbx
0x18001a0b8  retn
```
