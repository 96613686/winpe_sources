# CServerVCChannel::Initialize(IWTSVirtualChannelCallback *,void *,char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int,IAPCThread *,ChannelType)

- ea: `0x180005694`
- end: `0x180005b7b`
- name: `?Initialize@CServerVCChannel@@QEAAJPEAUIWTSVirtualChannelCallback@@PEAXPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@HPEAVIAPCThread@@W4ChannelType@@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(__int64, const char *, __int64, const char *, unsigned int, unsigned int, int, __int64, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000539c`
- `0x180005520`

## callees

- `0x180005694`
- `0x180008514`
- `0x180009410`
- `0x18000abc0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd04`
- `0x18000bd44`
- `0x18000f79c`
- `0x18001ba64`
- `0x18002c600`
- `0x18002d0e0`
- `0x18002d148`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800058fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800058fd`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800058f2`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800058f2`
- `KERNEL32!ProcessIdToSessionId` at `0x18000590a`
- `KERNEL32!ProcessIdToSessionId` at `0x18000590a`
- `WTSAPI32!WTSVirtualChannelClose` at `0x180005ae6`
- `WTSAPI32!WTSVirtualChannelClose` at `0x180005ae6`

## string_xrefs

- `0x180005785`: `StringCbCopyA failed`
- `0x1800059e4`: `CServerVCChannel::CreateDynamicChannel`
- `0x180005a47`: `CServerVCChannel::CreateStaticChannel`
- `0x180005ac9`: `pAPCThread->PostAPC(static_IssueARead) failed`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::Initialize(
        __int64 a1,
        const char *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        int a9)
{
  const char **v14; // rsi
  WCHAR *v15; // r12
  __int64 v16; // rbx
  _QWORD *v17; // r14
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v20; // edx
  const char *v21; // rcx
  void *v22; // rax
  unsigned int v23; // eax
  int v24; // edx
  const char *v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rax
  int v28; // r15d
  DWORD CurrentProcessId; // eax
  unsigned int v30; // eax
  __int64 v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  int v35; // eax
  DWORD pSessionId[22]; // [rsp+30h] [rbp-58h] BYREF
  ULONG BytesInUnicodeString; // [rsp+90h] [rbp+8h] BYREF

  if ( !*(_DWORD *)(a1 + 64) )
  {
    *(_DWORD *)(a1 + 64) = 1;
    if ( (int)PAL_System_CritSecInit(a1 + 56) < 0 )
      *(_DWORD *)(a1 + 64) = 0;
  }
  if ( !*(_DWORD *)(a1 + 64) )
    return 2147500037LL;
  v14 = (const char **)(a1 + 72);
  v15 = 0;
  if ( a2 != *(const char **)(a1 + 72) )
  {
    TCntPtr<IDispatch>::SafeRelease(a1 + 72);
    *v14 = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(a1 + 72);
  }
  v16 = a8;
  v17 = (_QWORD *)(a1 + 400);
  if ( a8 != *(_QWORD *)(a1 + 400) )
  {
    TCntPtr<IDispatch>::SafeRelease(a1 + 400);
    *v17 = v16;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  }
  if ( a4 )
  {
    LastError = StringCbCopyA((char *)(a1 + 80), 0x104u, a4);
    if ( LastError < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 20;
        v21 = "StringCbCopyA failed";
LABEL_17:
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v20,
          (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v21,
          LastError);
        goto LABEL_66;
      }
      goto LABEL_66;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 80) = 0;
  }
  *(_DWORD *)(a1 + 36) |= 2u;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 344) = a3;
    *(_DWORD *)(a1 + 360) = 1;
  }
  else if ( a9 == 1 )
  {
    v26 = -1;
    v27 = -1;
    do
      ++v27;
    while ( a4[v27] );
    v28 = v27 + 1;
    v15 = (WCHAR *)operator new(saturated_mul((unsigned int)(v27 + 1), 2u));
    if ( !v15 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_35;
      }
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 22;
      v25 = "WCHAR[]";
      goto LABEL_34;
    }
    BytesInUnicodeString = 0;
    do
      ++v26;
    while ( a4[v26] );
    RtlMultiByteToUnicodeN(v15, 2 * v28, &BytesInUnicodeString, a4, v26 + 1);
    pSessionId[0] = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, pSessionId) )
    {
      LastError = GetLastError();
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          23,
          WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v30,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      goto LABEL_66;
    }
    LastError = CServerVCChannel::CreateDynamicChannel_WTSAPI(a1, a4, a5, a6, a7);
    if ( LastError < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 24;
        v21 = "CServerVCChannel::CreateDynamicChannel";
        goto LABEL_17;
      }
LABEL_66:
      v32 = *(void **)(a1 + 352);
      if ( v32 )
      {
        WTSVirtualChannelClose(v32);
        *(_QWORD *)(a1 + 352) = 0;
      }
      else
      {
        v33 = *(void **)(a1 + 344);
        if ( !v33 )
        {
LABEL_71:
          if ( *v17 )
          {
            TCntPtr<IDispatch>::SafeRelease(a1 + 400);
            *v17 = 0;
          }
          if ( *v14 )
          {
            TCntPtr<IDispatch>::SafeRelease(a1 + 72);
            *v14 = 0;
            TCntPtr<ITSAsyncCallback>::SafeAddRef(a1 + 72);
          }
          v34 = *(void **)(a1 + 368);
          if ( v34 )
          {
            operator delete(v34);
            *(_QWORD *)(a1 + 368) = 0;
          }
          v35 = *(_DWORD *)(a1 + 36);
          if ( (v35 & 2) != 0 )
            *(_DWORD *)(a1 + 36) = v35 | 4;
          goto LABEL_79;
        }
        CloseHandle(v33);
      }
      *(_QWORD *)(a1 + 344) = 0;
      goto LABEL_71;
    }
  }
  else
  {
    if ( a9 )
    {
      LastError = -2147024809;
      goto LABEL_66;
    }
    LastError = CServerVCChannel::CreateStaticChannel((CServerVCChannel *)a1, a2, a5);
    if ( LastError < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 25;
        v21 = "CServerVCChannel::CreateStaticChannel";
        goto LABEL_17;
      }
      goto LABEL_66;
    }
  }
  v22 = operator new(0x648u);
  *(_QWORD *)(a1 + 368) = v22;
  if ( !v22 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_35;
    }
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    v24 = 26;
    v25 = "BYTE[]";
LABEL_34:
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v24,
      (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v23,
      (__int64)v25);
LABEL_35:
    LastError = -2147024882;
    goto LABEL_66;
  }
  v31 = *(_QWORD *)(a1 + 40);
  *(_DWORD *)(a1 + 376) = 1608;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  LastError = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(unsigned __int64), __int64))(*(_QWORD *)*v17 + 24LL))(
                *v17,
                CServerVCChannel::static_IssueARead,
                a1);
  if ( LastError )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 16LL))(*(_QWORD *)(a1 + 40));
    if ( LastError < 0
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 27;
      v21 = "pAPCThread->PostAPC(static_IssueARead) failed";
      goto LABEL_17;
    }
    goto LABEL_66;
  }
LABEL_79:
  if ( v15 )
    operator delete(v15);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180005694  push    rbx
0x180005696  push    rbp
0x180005697  push    rsi
0x180005698  push    rdi
0x180005699  push    r12
0x18000569b  push    r13
0x18000569d  push    r14
0x18000569f  push    r15
0x1800056a1  sub     rsp, 48h
0x1800056a5  xor     r13d, r13d
0x1800056a8  mov     rbp, r9
0x1800056ab  mov     r15, r8
0x1800056ae  mov     r14, rdx
0x1800056b1  mov     rdi, rcx
0x1800056b4  cmp     [rcx+40h], r13d
0x1800056b8  jnz     short loc_1800056D2
0x1800056ba  mov     dword ptr [rcx+40h], 1
0x1800056c1  add     rcx, 38h ; '8'
0x1800056c5  call    PAL_System_CritSecInit
0x1800056ca  test    eax, eax
0x1800056cc  jns     short loc_1800056D2
0x1800056ce  mov     [rdi+40h], r13d
0x1800056d2  cmp     [rdi+40h], r13d
0x1800056d6  jnz     short loc_1800056E2
0x1800056d8  mov     eax, 80004005h
0x1800056dd  jmp     loc_180005B6A
0x1800056e2  lea     rsi, [rdi+48h]
0x1800056e6  mov     r12, r13
0x1800056e9  cmp     r14, [rsi]
0x1800056ec  jz      short loc_180005701
0x1800056ee  mov     rcx, rsi
0x1800056f1  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x1800056f6  mov     rcx, rsi
0x1800056f9  mov     [rsi], r14
0x1800056fc  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180005701  mov     rbx, [rsp+88h+arg_38]
0x180005709  lea     r14, [rdi+190h]
0x180005710  cmp     rbx, [r14]
0x180005713  jz      short loc_180005734
0x180005715  mov     rcx, r14
0x180005718  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18000571d  mov     [r14], rbx
0x180005720  test    rbx, rbx
0x180005723  jz      short loc_180005734
0x180005725  mov     rax, [rbx]
0x180005728  mov     rcx, rbx
0x18000572b  mov     rax, [rax+8]
0x18000572f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005734  test    rbp, rbp
0x180005737  jz      short loc_1800057B4
0x180005739  mov     r8, rbp; char *
0x18000573c  lea     rcx, [rdi+50h]; char *
0x180005740  mov     edx, 104h; unsigned __int64
0x180005745  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18000574a  mov     ebx, eax
0x18000574c  test    eax, eax
0x18000574e  jns     short loc_1800057B8
0x180005750  mov     rcx, cs:WPP_GLOBAL_Control
0x180005757  lea     rax, WPP_GLOBAL_Control
0x18000575e  cmp     rcx, rax
0x180005761  jz      loc_180005ADA
0x180005767  test    byte ptr [rcx+1Ch], 8
0x18000576b  jz      loc_180005ADA
0x180005771  cmp     byte ptr [rcx+19h], 2
0x180005775  jb      loc_180005ADA
0x18000577b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005780  mov     edx, 14h
0x180005785  lea     rcx, aStringcbcopyaF; "StringCbCopyA failed"
0x18000578c  mov     [rsp+88h+var_60], ebx
0x180005790  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x180005797  mov     qword ptr [rsp+88h+BytesInMultiByteString], rcx
0x18000579c  mov     r9d, eax
0x18000579f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057a6  mov     rcx, [rcx+10h]
0x1800057aa  call    WPP_SF_DsD
0x1800057af  jmp     loc_180005ADA
0x1800057b4  mov     [rdi+50h], r13b
0x1800057b8  or      dword ptr [rdi+24h], 2
0x1800057bc  test    r15, r15
0x1800057bf  jz      short loc_18000582C
0x1800057c1  mov     [rdi+158h], r15
0x1800057c8  mov     dword ptr [rdi+168h], 1
0x1800057d2  mov     ebx, 648h
0x1800057d7  mov     ecx, ebx; Size
0x1800057d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800057de  mov     [rdi+170h], rax
0x1800057e5  test    rax, rax
0x1800057e8  jnz     loc_180005A53
0x1800057ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057f5  lea     rax, WPP_GLOBAL_Control
0x1800057fc  cmp     rcx, rax
0x1800057ff  jz      loc_1800058BE
0x180005805  test    byte ptr [rcx+1Ch], 8
0x180005809  jz      loc_1800058BE
0x18000580f  cmp     byte ptr [rcx+19h], 2
0x180005813  jb      loc_1800058BE
0x180005819  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000581e  mov     edx, 1Ah
0x180005823  lea     rcx, aByte; "BYTE[]"
0x18000582a  jmp     short loc_18000589F
0x18000582c  mov     eax, [rsp+88h+arg_40]
0x180005833  cmp     eax, 1
0x180005836  jnz     loc_1800059F0
0x18000583c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005840  mov     rax, rbx
0x180005843  inc     rax
0x180005846  cmp     [rax+rbp], r13b
0x18000584a  jnz     short loc_180005843
0x18000584c  lea     r15d, [rax+1]
0x180005850  mov     eax, 2
0x180005855  mov     ecx, r15d
0x180005858  mul     rcx
0x18000585b  cmovb   rax, rbx
0x18000585f  mov     rcx, rax; Size
0x180005862  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005867  mov     r12, rax
0x18000586a  test    rax, rax
0x18000586d  jnz     short loc_1800058C8
0x18000586f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005876  lea     rax, WPP_GLOBAL_Control
0x18000587d  cmp     rcx, rax
0x180005880  jz      short loc_1800058BE
0x180005882  test    byte ptr [rcx+1Ch], 8
0x180005886  jz      short loc_1800058BE
0x180005888  cmp     byte ptr [rcx+19h], 2
0x18000588c  jb      short loc_1800058BE
0x18000588e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005893  lea     edx, [r12+16h]
0x180005898  lea     rcx, aWchar; "WCHAR[]"
0x18000589f  mov     qword ptr [rsp+88h+BytesInMultiByteString], rcx
0x1800058a4  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1800058ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058b2  mov     r9d, eax
0x1800058b5  mov     rcx, [rcx+10h]
0x1800058b9  call    WPP_SF_Ds
0x1800058be  mov     ebx, 8007000Eh
0x1800058c3  jmp     loc_180005ADA
0x1800058c8  mov     [rsp+88h+BytesInUnicodeString], r13d
0x1800058d0  inc     rbx
0x1800058d3  cmp     [rbx+rbp], r13b
0x1800058d7  jnz     short loc_1800058D0
0x1800058d9  lea     eax, [rbx+1]
0x1800058dc  mov     r9, rbp; MultiByteString
0x1800058df  lea     edx, [r15+r15]; MaxBytesInUnicodeString
0x1800058e3  mov     [rsp+88h+BytesInMultiByteString], eax; BytesInMultiByteString
0x1800058e7  lea     r8, [rsp+88h+BytesInUnicodeString]; BytesInUnicodeString
0x1800058ef  mov     rcx, r12; UnicodeString
0x1800058f2  call    cs:__imp_RtlMultiByteToUnicodeN
0x1800058f8  mov     [rsp+88h+pSessionId], r13d
0x1800058fd  call    cs:__imp_GetCurrentProcessId
0x180005903  mov     ecx, eax; dwProcessId
0x180005905  lea     rdx, [rsp+88h+pSessionId]; pSessionId
0x18000590a  call    cs:__imp_ProcessIdToSessionId
0x180005910  test    eax, eax
0x180005912  jnz     short loc_18000597F
0x180005914  call    cs:__imp_GetLastError
0x18000591a  mov     ebx, eax
0x18000591c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005923  lea     rax, WPP_GLOBAL_Control
0x18000592a  cmp     rcx, rax
0x18000592d  jz      short loc_180005963
0x18000592f  test    byte ptr [rcx+1Ch], 8
0x180005933  jz      short loc_180005963
0x180005935  cmp     byte ptr [rcx+19h], 2
0x180005939  jb      short loc_180005963
0x18000593b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005940  mov     rcx, cs:WPP_GLOBAL_Control
0x180005947  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18000594e  mov     edx, 17h
0x180005953  mov     [rsp+88h+BytesInMultiByteString], ebx
0x180005957  mov     r9d, eax
0x18000595a  mov     rcx, [rcx+10h]
0x18000595e  call    WPP_SF_Dd
0x180005963  test    ebx, ebx
0x180005965  jle     short loc_180005970
0x180005967  movzx   ebx, bx
0x18000596a  or      ebx, 80070000h
0x180005970  test    ebx, ebx
0x180005972  mov     eax, 80004005h
0x180005977  cmovns  ebx, eax
0x18000597a  jmp     loc_180005ADA
0x18000597f  mov     eax, [rsp+88h+arg_30]
0x180005986  mov     rdx, rbp
0x180005989  mov     r9d, [rsp+88h+arg_28]
0x180005991  mov     rcx, rdi
0x180005994  mov     r8d, [rsp+88h+arg_20]
0x18000599c  mov     [rsp+88h+BytesInMultiByteString], eax
0x1800059a0  call    ?CreateDynamicChannel_WTSAPI@CServerVCChannel@@QEAAJPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@H@Z; CServerVCChannel::CreateDynamicChannel_WTSAPI(char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int)
0x1800059a5  mov     ebx, eax
0x1800059a7  test    eax, eax
0x1800059a9  jns     loc_1800057D2
0x1800059af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b6  lea     rax, WPP_GLOBAL_Control
0x1800059bd  cmp     rcx, rax
0x1800059c0  jz      loc_180005ADA
0x1800059c6  test    byte ptr [rcx+1Ch], 8
0x1800059ca  jz      loc_180005ADA
0x1800059d0  cmp     byte ptr [rcx+19h], 2
0x1800059d4  jb      loc_180005ADA
0x1800059da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800059df  mov     edx, 18h
0x1800059e4  lea     rcx, aCservervcchann_0; "CServerVCChannel::CreateDynamicChannel"
0x1800059eb  jmp     loc_18000578C
0x1800059f0  test    eax, eax
0x1800059f2  jnz     loc_180005AD5
0x1800059f8  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x180005a00  mov     rcx, rdi; this
0x180005a03  call    ?CreateStaticChannel@CServerVCChannel@@QEAAJPEBDK@Z; CServerVCChannel::CreateStaticChannel(char const *,ulong)
0x180005a08  mov     ebx, eax
0x180005a0a  test    eax, eax
0x180005a0c  jns     loc_1800057D2
0x180005a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a19  lea     rax, WPP_GLOBAL_Control
0x180005a20  cmp     rcx, rax
0x180005a23  jz      loc_180005ADA
0x180005a29  test    byte ptr [rcx+1Ch], 8
0x180005a2d  jz      loc_180005ADA
0x180005a33  cmp     byte ptr [rcx+19h], 2
0x180005a37  jb      loc_180005ADA
0x180005a3d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005a42  mov     edx, 19h
0x180005a47  lea     rcx, aCservervcchann; "CServerVCChannel::CreateStaticChannel"
0x180005a4e  jmp     loc_18000578C
0x180005a53  mov     rcx, [rdi+28h]
0x180005a57  mov     [rdi+178h], ebx
0x180005a5d  mov     rax, [rcx]
0x180005a60  mov     rax, [rax+8]
0x180005a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a69  mov     rcx, [r14]
0x180005a6c  lea     rdx, ?static_IssueARead@CServerVCChannel@@CAX_K@Z; CServerVCChannel::static_IssueARead(unsigned __int64)
0x180005a73  mov     r8, rdi
0x180005a76  mov     rax, [rcx]
0x180005a79  mov     rax, [rax+18h]
0x180005a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a82  mov     ebx, eax
0x180005a84  test    eax, eax
0x180005a86  jz      loc_180005B5B
0x180005a8c  mov     rcx, [rdi+28h]
0x180005a90  mov     rax, [rcx]
0x180005a93  mov     rax, [rax+10h]
0x180005a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a9c  test    ebx, ebx
0x180005a9e  jns     short loc_180005ADA
0x180005aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aa7  lea     rax, WPP_GLOBAL_Control
0x180005aae  cmp     rcx, rax
0x180005ab1  jz      short loc_180005ADA
0x180005ab3  test    byte ptr [rcx+1Ch], 8
0x180005ab7  jz      short loc_180005ADA
0x180005ab9  cmp     byte ptr [rcx+19h], 2
0x180005abd  jb      short loc_180005ADA
0x180005abf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005ac4  mov     edx, 1Bh
0x180005ac9  lea     rcx, aPapcthreadPost; "pAPCThread->PostAPC(static_IssueARead) "...
0x180005ad0  jmp     loc_18000578C
0x180005ad5  mov     ebx, 80070057h
0x180005ada  mov     rcx, [rdi+160h]; hChannelHandle
0x180005ae1  test    rcx, rcx
0x180005ae4  jz      short loc_180005AF5
0x180005ae6  call    cs:__imp_WTSVirtualChannelClose
0x180005aec  mov     [rdi+160h], r13
0x180005af3  jmp     short loc_180005B07
0x180005af5  mov     rcx, [rdi+158h]; hObject
0x180005afc  test    rcx, rcx
0x180005aff  jz      short loc_180005B0E
0x180005b01  call    cs:__imp_CloseHandle
0x180005b07  mov     [rdi+158h], r13
0x180005b0e  cmp     [r14], r13
0x180005b11  jz      short loc_180005B1E
0x180005b13  mov     rcx, r14
0x180005b16  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180005b1b  mov     [r14], r13
0x180005b1e  cmp     [rsi], r13
0x180005b21  jz      short loc_180005B36
0x180005b23  mov     rcx, rsi
0x180005b26  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180005b2b  mov     rcx, rsi
0x180005b2e  mov     [rsi], r13
0x180005b31  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180005b36  mov     rcx, [rdi+170h]; Block
0x180005b3d  test    rcx, rcx
0x180005b40  jz      short loc_180005B4E
0x180005b42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005b47  mov     [rdi+170h], r13
0x180005b4e  mov     eax, [rdi+24h]
0x180005b51  test    al, 2
0x180005b53  jz      short loc_180005B5B
0x180005b55  or      eax, 4
0x180005b58  mov     [rdi+24h], eax
0x180005b5b  test    r12, r12
0x180005b5e  jz      short loc_180005B68
0x180005b60  mov     rcx, r12; Block
0x180005b63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005b68  mov     eax, ebx
0x180005b6a  add     rsp, 48h
0x180005b6e  pop     r15
0x180005b70  pop     r14
0x180005b72  pop     r13
0x180005b74  pop     r12
0x180005b76  pop     rdi
  ... truncated ...
```
