# AppEndpoint::DoCallbackWithCachedUri(ushort const *,IWpnChannelRequest *,IWNSChannelDetails *)

- ea: `0x18002c258`
- end: `0x18002c59c`
- name: `?DoCallbackWithCachedUri@AppEndpoint@@AEAAJPEBGPEAUIWpnChannelRequest@@PEAUIWNSChannelDetails@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(AppEndpoint *__hidden this, const unsigned __int16 *, struct IWpnChannelRequest *, struct IWNSChannelDetails *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d8c4`
- `0x18009f8a8`

## callees

- `0x180011618`
- `0x18001bf30`
- `0x18002c22c`
- `0x18002c258`
- `0x18002d610`
- `0x18002e210`
- `0x180065b08`
- `0x180067de0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c359`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c455`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c455`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4fe`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002c408`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002c408`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002c377`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002c377`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002c3ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002c3ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002c41d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002c41d`

## pseudocode

```c
__int64 __fastcall AppEndpoint::DoCallbackWithCachedUri(
        AppEndpoint *this,
        const unsigned __int16 *a2,
        struct IWpnChannelRequest *a3,
        struct IWNSChannelDetails *a4)
{
  int v6; // r13d
  wil::details *v7; // r15
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rdi
  int v11; // eax
  wil::details *v12; // rbx
  wil::details *v13; // r14
  int v14; // eax
  unsigned int v15; // esi
  int v16; // esi
  int v17; // r14d
  unsigned int v18; // eax
  void *v19; // rdx
  int v20; // ecx
  __int64 v22; // rdx
  void *v23; // rdx
  int DueTime; // [rsp+20h] [rbp-49h]
  int *DueTimea; // [rsp+20h] [rbp-49h]
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-21h] BYREF
  wil::details *v28[2]; // [rsp+50h] [rbp-19h] BYREF
  int v29[4]; // [rsp+60h] [rbp-9h] BYREF
  DWORD Parameter; // [rsp+70h] [rbp+7h] BYREF
  char v31; // [rsp+74h] [rbp+Bh]
  HRESULT v32; // [rsp+78h] [rbp+Fh]
  void *phNewTimer; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LPVOID pv; // [rsp+D0h] [rbp+67h] BYREF
  LPCCH lpMultiByteStr; // [rsp+E0h] [rbp+77h] BYREF

  pv = this;
  v6 = (int)a2;
  v7 = 0;
  if ( !a3 )
  {
    v22 = 3786;
LABEL_28:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
      (const char *)0x80070057LL,
      DueTime);
    return v9;
  }
  if ( !a4 )
  {
    v22 = 3787;
    goto LABEL_28;
  }
  lpMultiByteStr = 0;
  v8 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, LPCCH *))(*(_QWORD *)a4 + 32LL))(a4, &lpMultiByteStr);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
      (const char *)(unsigned int)v8,
      DueTime);
LABEL_45:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpMultiByteStr);
    return v9;
  }
  v10 = 0;
  v27 = 0;
  if ( lpMultiByteStr )
  {
    v27 = 0;
    WpnUtf8ToUtf16(lpMultiByteStr, &v27);
    v10 = v27;
  }
  pv = 0;
  v11 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, LPVOID *))(*(_QWORD *)a4 + 40LL))(a4, &pv);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
      (const char *)(unsigned int)v11,
      DueTime);
LABEL_44:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
    wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(&v27, 0);
    goto LABEL_45;
  }
  v12 = 0;
  v28[0] = 0;
  if ( pv )
  {
    v28[0] = 0;
    WpnUtf8ToUtf16((LPCCH)pv, (unsigned __int16 **)v28);
    v12 = v28[0];
    v13 = v28[0];
    v7 = v28[0];
  }
  else
  {
    v13 = 0;
  }
  v26 = 0;
  v14 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, __int64 *))(*(_QWORD *)a4 + 56LL))(a4, &v26);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v16 = v26;
    v17 = HIDWORD(v26);
    Parameter = GetCurrentThreadId();
    v31 = 0;
    v32 = -2147467259;
    phNewTimer = 0;
    v32 = CoEnableCallCancellation(0);
    if ( v32 >= 0 )
      CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x3A98u, 0x3E8u, 0);
    v29[0] = 1;
    v29[1] = v16;
    v29[2] = v17;
    DueTimea = v29;
    v18 = (*(__int64 (__fastcall **)(struct IWpnChannelRequest *, _QWORD, unsigned __int16 *, wil::details *))(*(_QWORD *)a3 + 24LL))(
            a3,
            0,
            v10,
            v12);
    v9 = v18;
    if ( (byte_18015DE45 & 4) != 0 )
      McTemplateU0zzd_EventWriteTransfer(v20, (unsigned int)WPNEND_CHANNEL_CACHED, (_DWORD)v10, v6, v18);
    if ( (v9 & 0x80000000) == 0 )
    {
      if ( v32 >= 0 )
      {
        v32 = -2147467259;
        CoDisableCallCancellation(0);
        v19 = phNewTimer;
        if ( phNewTimer )
          DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
      if ( v7 )
        wil::details::FreeProcessHeap(v7, v19);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v10 )
        wil::details::FreeProcessHeap((wil::details *)v10, v19);
      if ( lpMultiByteStr )
        CoTaskMemFree((LPVOID)lpMultiByteStr);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEEB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
      (const char *)v9,
      (int)DueTimea);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(v28, 0);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xED8,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
    (const char *)(unsigned int)v14,
    DueTime);
  if ( v13 )
    wil::details::FreeProcessHeap(v13, v23);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v10 )
    wil::details::FreeProcessHeap((wil::details *)v10, v23);
  if ( lpMultiByteStr )
    CoTaskMemFree((LPVOID)lpMultiByteStr);
  return v15;
}

```

## disassembly

```asm
0x18002c258  mov     [rsp-8+arg_8], rbx
0x18002c25d  mov     [rsp-8+pv], rcx
0x18002c262  push    rbp
0x18002c263  push    rsi
0x18002c264  push    rdi
0x18002c265  push    r12
0x18002c267  push    r13
0x18002c269  push    r14
0x18002c26b  push    r15
0x18002c26d  lea     rbp, [rsp-27h]
0x18002c272  sub     rsp, 90h
0x18002c279  mov     rsi, r9
0x18002c27c  mov     r12, r8
0x18002c27f  mov     r13, rdx
0x18002c282  xor     r15d, r15d
0x18002c285  test    r8, r8
0x18002c288  jz      loc_18002C493
0x18002c28e  test    r9, r9
0x18002c291  jz      loc_18002C50B
0x18002c297  mov     [rbp+57h+lpMultiByteStr], r15
0x18002c29b  mov     rax, [r9]
0x18002c29e  lea     rdx, [rbp+57h+lpMultiByteStr]
0x18002c2a2  mov     rcx, r9
0x18002c2a5  mov     rax, [rax+20h]
0x18002c2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2ae  mov     ebx, eax
0x18002c2b0  test    eax, eax
0x18002c2b2  js      loc_18002C512
0x18002c2b8  mov     rcx, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x18002c2bc  mov     edi, r15d
0x18002c2bf  mov     [rbp+57h+var_78], r15
0x18002c2c3  test    rcx, rcx
0x18002c2c6  jz      short loc_18002C2DD
0x18002c2c8  mov     [rbp+57h+var_78], r15
0x18002c2cc  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x18002c2d0  call    ?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z; WpnUtf8ToUtf16(char const *,ushort * *)
0x18002c2d5  mov     rdi, [rbp+57h+var_78]
0x18002c2d9  mov     [rbp+57h+var_78], rdi
0x18002c2dd  mov     [rbp+57h+pv], r15
0x18002c2e1  mov     rax, [rsi]
0x18002c2e4  lea     rdx, [rbp+57h+pv]
0x18002c2e8  mov     rcx, rsi
0x18002c2eb  mov     rax, [rax+28h]
0x18002c2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2f4  mov     ebx, eax
0x18002c2f6  test    eax, eax
0x18002c2f8  js      loc_18002C52C
0x18002c2fe  mov     rcx, [rbp+57h+pv]; lpMultiByteStr
0x18002c302  mov     rbx, r15
0x18002c305  mov     [rbp+57h+var_70], rbx
0x18002c309  test    rcx, rcx
0x18002c30c  jz      loc_18002C546
0x18002c312  mov     [rbp+57h+var_70], r15
0x18002c316  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x18002c31a  call    ?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z; WpnUtf8ToUtf16(char const *,ushort * *)
0x18002c31f  mov     rbx, [rbp+57h+var_70]
0x18002c323  mov     [rbp+57h+var_70], rbx
0x18002c327  mov     r14, rbx
0x18002c32a  mov     r15, rbx
0x18002c32d  mov     [rbp+57h+var_80], 0
0x18002c335  mov     rax, [rsi]
0x18002c338  lea     rdx, [rbp+57h+var_80]
0x18002c33c  mov     rcx, rsi
0x18002c33f  mov     rax, [rax+38h]
0x18002c343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c348  mov     esi, eax
0x18002c34a  test    eax, eax
0x18002c34c  js      loc_18002C4B4
0x18002c352  mov     esi, dword ptr [rbp+57h+var_80]
0x18002c355  mov     r14d, dword ptr [rbp+57h+var_80+4]
0x18002c359  call    cs:__imp_GetCurrentThreadId
0x18002c35f  mov     [rbp+57h+Parameter], eax
0x18002c362  mov     [rbp+57h+var_4C], 0
0x18002c366  mov     [rbp+57h+var_48], 80004005h
0x18002c36d  mov     [rbp+57h+phNewTimer], 0
0x18002c375  xor     ecx, ecx; pReserved
0x18002c377  call    cs:__imp_CoEnableCallCancellation
0x18002c37d  mov     [rbp+57h+var_48], eax
0x18002c380  test    eax, eax
0x18002c382  js      short loc_18002C3B3
0x18002c384  mov     [rsp+0C0h+Flags], 0; Flags
0x18002c38c  mov     [rsp+0C0h+Period], 3E8h; Period
0x18002c394  mov     [rsp+0C0h+DueTime], 3A98h; DueTime
0x18002c39c  lea     r9, [rbp+57h+Parameter]; Parameter
0x18002c3a0  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18002c3a7  xor     edx, edx; TimerQueue
0x18002c3a9  lea     rcx, [rbp+57h+phNewTimer]; phNewTimer
0x18002c3ad  call    cs:__imp_CreateTimerQueueTimer
0x18002c3b3  mov     [rbp+57h+var_60], 1
0x18002c3ba  mov     [rbp+57h+var_5C], esi
0x18002c3bd  mov     [rbp+57h+var_58], r14d
0x18002c3c1  mov     rax, [r12]
0x18002c3c5  lea     rcx, [rbp+57h+var_60]
0x18002c3c9  mov     qword ptr [rsp+0C0h+DueTime], rcx; int
0x18002c3ce  mov     r9, rbx
0x18002c3d1  mov     r8, rdi
0x18002c3d4  xor     edx, edx
0x18002c3d6  mov     rcx, r12
0x18002c3d9  mov     rax, [rax+18h]
0x18002c3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3e2  mov     ebx, eax
0x18002c3e4  test    cs:byte_18015DE45, 4
0x18002c3eb  jnz     loc_18002C478
0x18002c3f1  test    ebx, ebx
0x18002c3f3  js      loc_18002C54E
0x18002c3f9  cmp     [rbp+57h+var_48], 0
0x18002c3fd  jl      short loc_18002C423
0x18002c3ff  mov     [rbp+57h+var_48], 80004005h
0x18002c406  xor     ecx, ecx; pReserved
0x18002c408  call    cs:__imp_CoDisableCallCancellation
0x18002c40e  mov     rdx, [rbp+57h+phNewTimer]; Timer
0x18002c412  test    rdx, rdx
0x18002c415  jz      short loc_18002C423
0x18002c417  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002c41b  xor     ecx, ecx; TimerQueue
0x18002c41d  call    cs:__imp_DeleteTimerQueueTimer
0x18002c423  test    r15, r15
0x18002c426  jz      short loc_18002C430
0x18002c428  mov     rcx, r15; this
0x18002c42b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002c430  mov     rcx, [rbp+57h+pv]; pv
0x18002c434  test    rcx, rcx
0x18002c437  jz      short loc_18002C43F
0x18002c439  call    cs:__imp_CoTaskMemFree
0x18002c43f  test    rdi, rdi
0x18002c442  jz      short loc_18002C44C
0x18002c444  mov     rcx, rdi; this
0x18002c447  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002c44c  mov     rcx, [rbp+57h+lpMultiByteStr]; pv
0x18002c450  test    rcx, rcx
0x18002c453  jz      short loc_18002C45B
0x18002c455  call    cs:__imp_CoTaskMemFree
0x18002c45b  xor     eax, eax
0x18002c45d  mov     rbx, [rsp+0C0h+arg_8]
0x18002c465  add     rsp, 90h
0x18002c46c  pop     r15
0x18002c46e  pop     r14
0x18002c470  pop     r13
0x18002c472  pop     r12
0x18002c474  pop     rdi
0x18002c475  pop     rsi
0x18002c476  pop     rbp
0x18002c477  retn
0x18002c478  mov     [rsp+0C0h+DueTime], ebx
0x18002c47c  mov     r9, r13
0x18002c47f  mov     r8, rdi
0x18002c482  lea     rdx, WPNEND_CHANNEL_CACHED
0x18002c489  call    McTemplateU0zzd_EventWriteTransfer
0x18002c48e  jmp     loc_18002C3F1
0x18002c493  mov     edx, 0ECAh; void *
0x18002c498  mov     ebx, 80070057h
0x18002c49d  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c4a4  mov     r9d, ebx; char *
0x18002c4a7  mov     rcx, [rbp+5Fh]; this
0x18002c4ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4b0  mov     eax, ebx
0x18002c4b2  jmp     short loc_18002C45D
0x18002c4b4  mov     rcx, [rbp+5Fh]; this
0x18002c4b8  mov     r9d, esi; char *
0x18002c4bb  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c4c2  mov     edx, 0ED8h; void *
0x18002c4c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4cc  test    r14, r14
0x18002c4cf  jz      short loc_18002C4D9
0x18002c4d1  mov     rcx, r14; this
0x18002c4d4  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002c4d9  mov     rcx, [rbp+57h+pv]; pv
0x18002c4dd  test    rcx, rcx
0x18002c4e0  jz      short loc_18002C4E8
0x18002c4e2  call    cs:__imp_CoTaskMemFree
0x18002c4e8  test    rdi, rdi
0x18002c4eb  jz      short loc_18002C4F5
0x18002c4ed  mov     rcx, rdi; this
0x18002c4f0  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002c4f5  mov     rcx, [rbp+57h+lpMultiByteStr]; pv
0x18002c4f9  test    rcx, rcx
0x18002c4fc  jz      short loc_18002C504
0x18002c4fe  call    cs:__imp_CoTaskMemFree
0x18002c504  mov     eax, esi
0x18002c506  jmp     loc_18002C45D
0x18002c50b  mov     edx, 0ECBh
0x18002c510  jmp     short loc_18002C498
0x18002c512  mov     rcx, [rbp+5Fh]; this
0x18002c516  mov     r9d, eax; char *
0x18002c519  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c520  mov     edx, 0ED0h; void *
0x18002c525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c52a  jmp     short loc_18002C58E
0x18002c52c  mov     rcx, [rbp+5Fh]; this
0x18002c530  mov     r9d, eax; char *
0x18002c533  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c53a  mov     edx, 0ED4h; void *
0x18002c53f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c544  jmp     short loc_18002C57A
0x18002c546  mov     r14, r15
0x18002c549  jmp     loc_18002C32D
0x18002c54e  mov     rcx, [rbp+5Fh]; this
0x18002c552  mov     r9d, ebx; char *
0x18002c555  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c55c  mov     edx, 0EEBh; void *
0x18002c561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c566  lea     rcx, [rbp+57h+Parameter]; this
0x18002c56a  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18002c56f  xor     edx, edx
0x18002c571  lea     rcx, [rbp+57h+var_70]
0x18002c575  call    ?reset@?$unique_ptr@U_GUID@@Uprocess_heap_deleter@wil@@@wistd@@QEAAXPEAU_GUID@@@Z; wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(_GUID *)
0x18002c57a  lea     rcx, [rbp+57h+pv]
0x18002c57e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c583  xor     edx, edx
0x18002c585  lea     rcx, [rbp+57h+var_78]
0x18002c589  call    ?reset@?$unique_ptr@U_GUID@@Uprocess_heap_deleter@wil@@@wistd@@QEAAXPEAU_GUID@@@Z; wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(_GUID *)
0x18002c58e  lea     rcx, [rbp+57h+lpMultiByteStr]
0x18002c592  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c597  jmp     loc_18002C4B0
```
