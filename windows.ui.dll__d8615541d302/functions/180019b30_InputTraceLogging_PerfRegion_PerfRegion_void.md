# InputTraceLogging::PerfRegion::~PerfRegion(void)

- ea: `0x180019b30`
- end: `0x180019dca`
- name: `??1PerfRegion@InputTraceLogging@@QEAA@XZ`
- size: `666`
- prototype: `void __fastcall(InputTraceLogging::PerfRegion *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017b00`
- `0x180018350`
- `0x18001ab80`
- `0x180031f04`
- `0x1800c7740`
- `0x1800c7760`
- `0x1800c7780`
- `0x1800c77c4`
- `0x1800c837e`

## callees

- `0x180019b30`
- `0x18005f330`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019b78`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019b78`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019c84`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019c84`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019c55`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019c55`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019da3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019da3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019c3a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019c3a`

## pseudocode

```c
void __fastcall InputTraceLogging::PerfRegion::~PerfRegion(InputTraceLogging::PerfRegion *this)
{
  _QWORD *v2; // rbx
  ULONGLONG *v3; // r9
  __int64 v4; // r10
  const unsigned __int16 *v5; // rcx
  const GUID *v6; // r9
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // [rsp+30h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-50h] BYREF
  int *v13; // [rsp+68h] [rbp-40h]
  int v14; // [rsp+70h] [rbp-38h]
  int v15; // [rsp+74h] [rbp-34h]
  const unsigned __int16 *v16; // [rsp+78h] [rbp-30h]
  int v17; // [rsp+80h] [rbp-28h]
  int v18; // [rsp+84h] [rbp-24h]

  if ( *(_BYTE *)this )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    v9 = 0;
    if ( InitOnceBeginInitialize(
           &`InputTraceLogging::Instance'::`2'::wrapper,
           0,
           (PBOOL)&v9,
           (LPVOID *)&EventDescriptor)
      && v9 )
    {
      *(_QWORD *)&EventDescriptor.Id = &qword_1801353C8;
      qword_1801353D0 = 0;
      byte_1801353D8 = 0;
      dword_1801353DC = 0;
      qword_1801353C8 = &PopupMenuTelemetry::`vftable';
      CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_a8e7baa2fca040c17c3e795f3590cb07_::_lambda_invoker_cdecl_);
      v2 = CallbackContext;
      qword_1801353D0 = (__int64)CallbackContext;
      byte_1801353D8 = 1;
      ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
      if ( *((_QWORD *)CallbackContext + 4) )
        __fastfail(5u);
      v3 = (ULONGLONG *)((char *)CallbackContext + 32);
      *((_QWORD *)CallbackContext + 5) = 0;
      v2[6] = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, v2, v3) )
        EventSetInformation(v2[4], 2, v2[1], *(unsigned __int16 *)v2[1]);
      dword_1801353DC = 1;
      (*(void (__fastcall **)(void *))(qword_1801353C8 + 8LL))(&qword_1801353C8);
      InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1801353C8);
    }
    v4 = *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id + 8LL);
    if ( *(_DWORD *)v4 > 6u && (*(_QWORD *)(v4 + 16) & 1) != 0 && (*(_QWORD *)(v4 + 24) & 1LL) == *(_QWORD *)(v4 + 24) )
    {
      v5 = (const unsigned __int16 *)*((_QWORD *)this + 1);
      v6 = (const GUID *)*((_QWORD *)this + 6);
      if ( v5 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *((_BYTE *)v5 + v7) );
        v8 = v7 + 1;
      }
      else
      {
        v5 = &word_18010B172;
        v8 = 1;
      }
      v17 = v8;
      *(_DWORD *)&EventDescriptor.Level = 518;
      UserData.Ptr = *(_QWORD *)(v4 + 8);
      v16 = v5;
      v18 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v13 = &dword_18011EA84;
      UserData.Reserved = 2;
      v14 = 21;
      v15 = 1;
      v9 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v4 + 32), &EventDescriptor, (LPCGUID)this + 1, v6, 3u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x180019b30  mov     r11, rsp
0x180019b33  push    rdi
0x180019b34  sub     rsp, 0A0h
0x180019b3b  mov     rax, cs:__security_cookie
0x180019b42  xor     rax, rsp
0x180019b45  mov     [rsp+0A8h+var_20], rax
0x180019b4d  cmp     byte ptr [rcx], 0
0x180019b50  mov     rdi, rcx
0x180019b53  jz      loc_180019DB1
0x180019b59  mov     [r11+18h], rbp
0x180019b5d  lea     r9, [r11-70h]; lpContext
0x180019b61  xor     ebp, ebp
0x180019b63  lea     r8, [r11-78h]; fPending
0x180019b67  xor     edx, edx; dwFlags
0x180019b69  mov     [r11-70h], rbp
0x180019b6d  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180019b74  mov     [rsp+0A8h+var_78], ebp
0x180019b78  call    cs:__imp_InitOnceBeginInitialize
0x180019b7e  test    eax, eax
0x180019b80  jz      loc_180019CA2
0x180019b86  cmp     [rsp+0A8h+var_78], ebp
0x180019b8a  jz      loc_180019CA2
0x180019b90  mov     [rsp+0A8h+arg_8], rbx
0x180019b98  lea     rax, ??_7PopupMenuTelemetry@@6B@; const PopupMenuTelemetry::`vftable'
0x180019b9f  mov     [rsp+0A8h+var_10], rsi
0x180019ba7  mov     [rsp+0A8h+var_18], r14
0x180019baf  lea     r14, qword_1801353C8
0x180019bb6  mov     qword ptr [rsp+0A8h+EventDescriptor.Id], r14
0x180019bbb  mov     cs:qword_1801353D0, rbp
0x180019bc2  mov     cs:byte_1801353D8, bpl
0x180019bc9  mov     cs:dword_1801353DC, ebp
0x180019bcf  mov     cs:qword_1801353C8, rax
0x180019bd6  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180019bdd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x180019be4  mov     cs:CallbackContext, rax
0x180019beb  call    atexit
0x180019bf0  mov     rbx, cs:CallbackContext
0x180019bf7  mov     cs:qword_1801353D0, rbx
0x180019bfe  mov     cs:byte_1801353D8, 1
0x180019c05  mov     rax, [rbx+8]
0x180019c09  movups  xmm0, xmmword ptr [rax-10h]
0x180019c0d  movups  xmmword ptr [rsp+0A8h+ProviderId.Data1], xmm0
0x180019c12  cmp     [rbx+20h], rbp
0x180019c16  jz      short loc_180019C1F
0x180019c18  mov     ecx, 5
0x180019c1d  int     29h; Win8: RtlFailFast(ecx)
0x180019c1f  lea     r9, [rbx+20h]; RegHandle
0x180019c23  mov     [rbx+28h], rbp
0x180019c27  mov     r8, rbx; CallbackContext
0x180019c2a  mov     [rbx+30h], rbp
0x180019c2e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180019c35  lea     rcx, [rsp+0A8h+ProviderId]; ProviderId
0x180019c3a  call    cs:__imp_EventRegister
0x180019c40  test    eax, eax
0x180019c42  jnz     short loc_180019C5B
0x180019c44  mov     r8, [rbx+8]
0x180019c48  mov     edx, 2
0x180019c4d  mov     rcx, [rbx+20h]
0x180019c51  movzx   r9d, word ptr [r8]
0x180019c55  call    cs:__imp_EventSetInformation
0x180019c5b  mov     rax, cs:qword_1801353C8
0x180019c62  mov     rcx, r14
0x180019c65  mov     cs:dword_1801353DC, 1
0x180019c6f  mov     rax, [rax+8]
0x180019c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c78  mov     r8, r14; lpContext
0x180019c7b  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x180019c82  xor     edx, edx; dwFlags
0x180019c84  call    cs:__imp_InitOnceComplete
0x180019c8a  mov     r14, [rsp+0A8h+var_18]
0x180019c92  mov     rsi, [rsp+0A8h+var_10]
0x180019c9a  mov     rbx, [rsp+0A8h+arg_8]
0x180019ca2  mov     rax, qword ptr [rsp+0A8h+EventDescriptor.Id]
0x180019ca7  mov     r10, [rax+8]
0x180019cab  mov     eax, [r10]
0x180019cae  cmp     eax, 6
0x180019cb1  jbe     loc_180019DA9
0x180019cb7  mov     rcx, [r10+18h]
0x180019cbb  mov     rax, [r10+10h]
0x180019cbf  test    al, 1
0x180019cc1  jz      loc_180019DA9
0x180019cc7  mov     rax, rcx
0x180019cca  and     eax, 1
0x180019ccd  cmp     rax, rcx
0x180019cd0  jnz     loc_180019DA9
0x180019cd6  mov     rcx, [rdi+8]
0x180019cda  mov     r9, [rdi+30h]; RelatedActivityId
0x180019cde  test    rcx, rcx
0x180019ce1  jz      short loc_180019CFD
0x180019ce3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019cea  nop     word ptr [rax+rax+00h]
0x180019cf0  inc     rax
0x180019cf3  cmp     [rcx+rax], bpl
0x180019cf7  jnz     short loc_180019CF0
0x180019cf9  inc     eax
0x180019cfb  jmp     short loc_180019D09
0x180019cfd  lea     rcx, word_18010B172
0x180019d04  mov     eax, 1
0x180019d09  mov     [rsp+0A8h+var_28], eax
0x180019d10  lea     r8, [rdi+10h]; ActivityId
0x180019d14  movzx   eax, cs:word_18011EA7A
0x180019d1b  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x180019d20  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x180019d24  mov     rax, [r10+8]
0x180019d28  mov     [rsp+0A8h+var_50.Ptr], rax
0x180019d2d  mov     [rsp+0A8h+var_30], rcx
0x180019d32  lea     rcx, _TraceLoggingMetadata
0x180019d39  mov     [rsp+0A8h+var_24], ebp
0x180019d40  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x180019d48  mov     [rsp+0A8h+EventDescriptor.Keyword], 1
0x180019d51  movzx   eax, word ptr [rax]
0x180019d54  mov     [rsp+0A8h+var_50.Size], eax
0x180019d58  lea     rax, dword_18011EA84
0x180019d5f  mov     [rsp+0A8h+var_40], rax
0x180019d64  lea     rax, _TraceLoggingMetadataEnd
0x180019d6b  sub     eax, ecx
0x180019d6d  mov     dword ptr [rsp+0A8h+var_50.0Ch], 2
0x180019d75  mov     [rsp+0A8h+var_38], 15h
0x180019d7d  mov     [rsp+0A8h+var_34], 1
0x180019d85  mov     [rsp+0A8h+var_78], eax
0x180019d89  mov     eax, [rsp+0A8h+var_78]
0x180019d8d  mov     rcx, [r10+20h]; RegHandle
0x180019d91  lea     rax, [rsp+0A8h+var_50]
0x180019d96  mov     [rsp+0A8h+UserData], rax; UserData
0x180019d9b  mov     [rsp+0A8h+UserDataCount], 3; UserDataCount
0x180019da3  call    cs:__imp_EventWriteTransfer
0x180019da9  mov     rbp, [rsp+0A8h+arg_10]
0x180019db1  mov     rcx, [rsp+0A8h+var_20]
0x180019db9  xor     rcx, rsp; StackCookie
0x180019dbc  call    __security_check_cookie
0x180019dc1  add     rsp, 0A0h
0x180019dc8  pop     rdi
0x180019dc9  retn
```
