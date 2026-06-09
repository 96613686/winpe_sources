# InputTraceLogging::Delivery::ReceiveMessage(HWND__ *,uint,unsigned __int64,__int64,bool)

- ea: `0x18001a0c0`
- end: `0x18001a3b0`
- name: `?ReceiveMessage@Delivery@InputTraceLogging@@SAXPEAUHWND__@@I_K_J_N@Z`
- size: `752`
- prototype: `void __fastcall(HWND, unsigned int, unsigned __int64, __int64, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017b00`
- `0x180018350`
- `0x18001ab80`

## callees

- `0x18001a0c0`
- `0x18005f330`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a118`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a118`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a21e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a21e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001a1e7`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001a1e7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a381`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a381`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001a1cc`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001a1cc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageTime` at `0x18001a267`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageTime` at `0x18001a267`

## pseudocode

```c
void __fastcall InputTraceLogging::Delivery::ReceiveMessage(HWND a1, int a2, __int64 a3, __int64 a4, bool a5)
{
  _QWORD *v9; // rbx
  ULONGLONG *v10; // r9
  __int64 v11; // rbx
  LONG MessageTime; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  LONG v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  HWND v20; // [rsp+60h] [rbp-A0h] BYREF
  GUID ProviderId; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  char *v23; // [rsp+90h] [rbp-70h]
  int v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+9Ch] [rbp-64h]
  int *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  int *v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  HWND *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  __int64 *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  __int64 *v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+E8h] [rbp-18h]
  LONG *v36; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  WINBOOL *p_fPending; // [rsp+100h] [rbp+0h]
  __int64 v39; // [rsp+108h] [rbp+8h]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_1801353C8;
    qword_1801353C8 = &PopupMenuTelemetry::`vftable';
    qword_1801353D0 = 0;
    byte_1801353D8 = 0;
    dword_1801353DC = 0;
    CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_a8e7baa2fca040c17c3e795f3590cb07_::_lambda_invoker_cdecl_);
    v9 = CallbackContext;
    qword_1801353D0 = (__int64)CallbackContext;
    byte_1801353D8 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v10 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v9[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v9, v10) )
      EventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
    dword_1801353DC = 1;
    (*(void (__fastcall **)(void *))(qword_1801353C8 + 8LL))(&qword_1801353C8);
    InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1801353C8);
  }
  v11 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v11 > 4u
    && (*(_QWORD *)(v11 + 16) & 0x10) != 0
    && (*(_QWORD *)(v11 + 24) & 0x10LL) == *(_QWORD *)(v11 + 24) )
  {
    fPending = a5;
    MessageTime = GetMessageTime();
    v18 = a4;
    v15 = MessageTime;
    v19 = a3;
    p_fPending = &fPending;
    v20 = a1;
    v36 = &v15;
    v16 = a2;
    v34 = &v18;
    v32 = &v19;
    v30 = &v20;
    v28 = &v16;
    v26 = &v17;
    *(_DWORD *)&ProviderId.Data2 = 4;
    UserData.Ptr = *(_QWORD *)(v11 + 8);
    v17 = a2;
    v39 = 4;
    v37 = 4;
    v35 = 8;
    v33 = 8;
    v31 = 8;
    v29 = 4;
    v27 = 4;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 16;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v23 = &byte_18011EBAF;
    UserData.Reserved = 2;
    v24 = 121;
    v25 = 1;
    LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v11 + 32), (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 9u, &UserData);
  }
}

```

## disassembly

```asm
0x18001a0c0  mov     [rsp-8+arg_8], rbx
0x18001a0c5  mov     [rsp-8+arg_10], rsi
0x18001a0ca  push    rbp
0x18001a0cb  push    r12
0x18001a0cd  push    r13
0x18001a0cf  push    r14
0x18001a0d1  push    r15
0x18001a0d3  lea     rbp, [rsp-20h]
0x18001a0d8  sub     rsp, 120h
0x18001a0df  mov     rax, cs:__security_cookie
0x18001a0e6  xor     rax, rsp
0x18001a0e9  mov     [rbp+40h+var_30], rax
0x18001a0ed  mov     r14, r9
0x18001a0f0  mov     r15, r8
0x18001a0f3  mov     esi, edx
0x18001a0f5  lea     r9, [rsp+140h+Context]; lpContext
0x18001a0fa  mov     r12, rcx
0x18001a0fd  lea     r8, [rsp+140h+fPending]; fPending
0x18001a102  xor     r13d, r13d
0x18001a105  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18001a10c  xor     edx, edx; dwFlags
0x18001a10e  mov     [rsp+140h+Context], r13
0x18001a113  mov     [rsp+140h+fPending], r13d
0x18001a118  call    cs:__imp_InitOnceBeginInitialize
0x18001a11e  test    eax, eax
0x18001a120  jz      loc_18001A22C
0x18001a126  cmp     [rsp+140h+fPending], r13d
0x18001a12b  jz      loc_18001A22C
0x18001a131  lea     rax, qword_1801353C8
0x18001a138  mov     [rsp+140h+arg_0], rdi
0x18001a140  mov     [rsp+140h+Context], rax
0x18001a145  lea     rax, ??_7PopupMenuTelemetry@@6B@; const PopupMenuTelemetry::`vftable'
0x18001a14c  mov     cs:qword_1801353C8, rax
0x18001a153  mov     cs:qword_1801353D0, r13
0x18001a15a  mov     cs:byte_1801353D8, r13b
0x18001a161  mov     cs:dword_1801353DC, r13d
0x18001a168  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001a16f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x18001a176  mov     cs:CallbackContext, rax
0x18001a17d  call    atexit
0x18001a182  mov     rbx, cs:CallbackContext
0x18001a189  mov     cs:qword_1801353D0, rbx
0x18001a190  mov     cs:byte_1801353D8, 1
0x18001a197  mov     rax, [rbx+8]
0x18001a19b  movups  xmm0, xmmword ptr [rax-10h]
0x18001a19f  movups  xmmword ptr [rsp+140h+ProviderId.Data1], xmm0
0x18001a1a4  cmp     [rbx+20h], r13
0x18001a1a8  jz      short loc_18001A1B1
0x18001a1aa  mov     ecx, 5
0x18001a1af  int     29h; Win8: RtlFailFast(ecx)
0x18001a1b1  lea     r9, [rbx+20h]; RegHandle
0x18001a1b5  mov     [rbx+28h], r13
0x18001a1b9  mov     r8, rbx; CallbackContext
0x18001a1bc  mov     [rbx+30h], r13
0x18001a1c0  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001a1c7  lea     rcx, [rsp+140h+ProviderId]; ProviderId
0x18001a1cc  call    cs:__imp_EventRegister
0x18001a1d2  test    eax, eax
0x18001a1d4  jnz     short loc_18001A1ED
0x18001a1d6  mov     r8, [rbx+8]
0x18001a1da  mov     edx, 2
0x18001a1df  mov     rcx, [rbx+20h]
0x18001a1e3  movzx   r9d, word ptr [r8]
0x18001a1e7  call    cs:__imp_EventSetInformation
0x18001a1ed  mov     rax, cs:qword_1801353C8
0x18001a1f4  lea     rcx, qword_1801353C8
0x18001a1fb  mov     cs:dword_1801353DC, 1
0x18001a205  mov     rax, [rax+8]
0x18001a209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a20e  lea     r8, qword_1801353C8; lpContext
0x18001a215  xor     edx, edx; dwFlags
0x18001a217  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18001a21e  call    cs:__imp_InitOnceComplete
0x18001a224  mov     rdi, [rsp+140h+arg_0]
0x18001a22c  mov     rax, [rsp+140h+Context]
0x18001a231  mov     rbx, [rax+8]
0x18001a235  mov     eax, [rbx]
0x18001a237  cmp     eax, 4
0x18001a23a  jbe     loc_18001A387
0x18001a240  mov     rcx, [rbx+18h]
0x18001a244  mov     rax, [rbx+10h]
0x18001a248  test    al, 10h
0x18001a24a  jz      loc_18001A387
0x18001a250  mov     rax, rcx
0x18001a253  and     eax, 10h
0x18001a256  cmp     rax, rcx
0x18001a259  jnz     loc_18001A387
0x18001a25f  movzx   eax, [rbp+40h+arg_20]
0x18001a263  mov     [rsp+140h+fPending], eax
0x18001a267  call    cs:__imp_GetMessageTime
0x18001a26d  mov     [rsp+140h+var_F0], r14
0x18001a272  lea     rcx, _TraceLoggingMetadata
0x18001a279  mov     [rsp+140h+var_100], eax
0x18001a27d  lea     rdx, [rsp+140h+ProviderId]; EventDescriptor
0x18001a282  mov     [rsp+140h+var_E8], r15
0x18001a287  lea     rax, [rsp+140h+fPending]
0x18001a28c  mov     [rbp+40h+var_40], rax
0x18001a290  xor     r9d, r9d; RelatedActivityId
0x18001a293  mov     [rsp+140h+var_E0], r12
0x18001a298  lea     rax, [rsp+140h+var_100]
0x18001a29d  mov     [rbp+40h+var_50], rax
0x18001a2a1  xor     r8d, r8d; ActivityId
0x18001a2a4  mov     [rsp+140h+var_FC], esi
0x18001a2a8  lea     rax, [rsp+140h+var_F0]
0x18001a2ad  mov     [rbp+40h+var_60], rax
0x18001a2b1  lea     rax, [rsp+140h+var_E8]
0x18001a2b6  mov     [rbp+40h+var_70], rax
0x18001a2ba  lea     rax, [rsp+140h+var_E0]
0x18001a2bf  mov     [rbp+40h+var_80], rax
0x18001a2c3  lea     rax, [rsp+140h+var_FC]
0x18001a2c8  mov     [rbp+40h+var_90], rax
0x18001a2cc  lea     rax, [rsp+140h+var_F8]
0x18001a2d1  mov     [rbp+40h+var_A0], rax
0x18001a2d5  movzx   eax, cs:word_18011EBA5
0x18001a2dc  mov     dword ptr [rsp+140h+ProviderId.Data2], eax
0x18001a2e0  mov     rax, [rbx+8]
0x18001a2e4  mov     [rbp+40h+var_C0.Ptr], rax
0x18001a2e8  mov     [rsp+140h+var_F8], esi
0x18001a2ec  mov     [rbp+40h+var_38], 4
0x18001a2f4  mov     [rbp+40h+var_48], 4
0x18001a2fc  mov     [rbp+40h+var_58], 8
0x18001a304  mov     [rbp+40h+var_68], 8
0x18001a30c  mov     [rbp+40h+var_78], 8
0x18001a314  mov     [rbp+40h+var_88], 4
0x18001a31c  mov     [rbp+40h+var_98], 4
0x18001a324  mov     [rsp+140h+ProviderId.Data1], 0B000000h
0x18001a32c  mov     qword ptr [rsp+140h+ProviderId.Data4], 10h
0x18001a335  movzx   eax, word ptr [rax]
0x18001a338  mov     [rbp+40h+var_C0.Size], eax
0x18001a33b  lea     rax, byte_18011EBAF
0x18001a342  mov     [rbp+40h+var_B0], rax
0x18001a346  lea     rax, _TraceLoggingMetadataEnd
0x18001a34d  sub     eax, ecx
0x18001a34f  mov     dword ptr [rbp+40h+var_C0.0Ch], 2
0x18001a356  mov     [rbp+40h+var_A8], 79h ; 'y'
0x18001a35d  mov     [rbp+40h+var_A4], 1
0x18001a364  mov     dword ptr [rsp+140h+Context], eax
0x18001a368  mov     eax, dword ptr [rsp+140h+Context]
0x18001a36c  mov     rcx, [rbx+20h]; RegHandle
0x18001a370  lea     rax, [rbp+40h+var_C0]
0x18001a374  mov     [rsp+140h+UserData], rax; UserData
0x18001a379  mov     [rsp+140h+UserDataCount], 9; UserDataCount
0x18001a381  call    cs:__imp_EventWriteTransfer
0x18001a387  mov     rcx, [rbp+40h+var_30]
0x18001a38b  xor     rcx, rsp; StackCookie
0x18001a38e  call    __security_check_cookie
0x18001a393  lea     r11, [rsp+140h+var_20]
0x18001a39b  mov     rbx, [r11+38h]
0x18001a39f  mov     rsi, [r11+40h]
0x18001a3a3  mov     rsp, r11
0x18001a3a6  pop     r15
0x18001a3a8  pop     r14
0x18001a3aa  pop     r13
0x18001a3ac  pop     r12
0x18001a3ae  pop     rbp
0x18001a3af  retn
```
