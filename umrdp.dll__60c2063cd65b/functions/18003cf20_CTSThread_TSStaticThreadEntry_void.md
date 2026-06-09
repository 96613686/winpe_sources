# CTSThread::TSStaticThreadEntry(void *)

- ea: `0x18003cf20`
- end: `0x18003d1db`
- name: `?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z`
- size: `699`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001550`
- `0x18000a118`
- `0x18000a37c`
- `0x18000b98c`
- `0x18001b394`
- `0x18001b580`
- `0x18001bae0`
- `0x1800391a8`
- `0x1800397a0`
- `0x180039ddc`
- `0x18003b7b4`
- `0x18003bd34`
- `0x18003cf20`
- `0x180049010`

## string_xrefs

- `0x18003d0e9`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18003cfb5`: `thread descriptor creation failed in bind path`
- `0x18003d052`: `Fail to add thread to thread descriptor`
- `0x18003d0de`: `TSStaticThreadEntry`
- `0x18003d18c`: `Failed to init in thread context`

## pseudocode

```c
__int64 __fastcall CTSThread::TSStaticThreadEntry(void (__fastcall **a1)(__int64), __int64 a2, int a3, int a4)
{
  void (__fastcall *v4)(__int64); // rbx
  void (__fastcall *v6)(__int64); // rdi
  void (__fastcall *v7)(__int64); // r15
  void (__fastcall *v8)(__int64); // r13
  void (__fastcall *v9)(__int64); // r12
  __int64 v10; // rcx
  int Id; // edi
  int ActivityIdPrefix; // eax
  int v13; // edx
  const char *v14; // rcx
  CTS_TLS_ThreadDescriptor *v16; // r14
  int v17; // edx
  __int64 (__fastcall *v18)(__int64); // rax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  void (__fastcall *v23)(__int64); // [rsp+50h] [rbp-28h] BYREF
  const char *v24; // [rsp+58h] [rbp-20h] BYREF
  const char *v25; // [rsp+60h] [rbp-18h] BYREF
  const char *v26; // [rsp+68h] [rbp-10h] BYREF
  int v27; // [rsp+C0h] [rbp+48h] BYREF
  int v28; // [rsp+C8h] [rbp+50h] BYREF
  CTS_TLS_ThreadDescriptor *v29; // [rsp+D0h] [rbp+58h] BYREF
  void (__fastcall *v30)(__int64); // [rsp+D8h] [rbp+60h] BYREF

  v4 = 0;
  v30 = 0;
  v29 = 0;
  v6 = a1[4];
  v7 = 0;
  v8 = *a1;
  v9 = a1[3];
  if ( v6 )
  {
    TCntPtr<CTSThread>::SafeRelease(&v30);
    v10 = *((_QWORD *)v6 + 5);
    v4 = v6;
    v30 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v7 = v6;
  }
  Id = CTS_TLS_ThreadDescriptor::CreateInstance(0, &v29, a3, a4);
  if ( Id < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_9;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v13 = 55;
    v14 = "thread descriptor creation failed in bind path";
    goto LABEL_8;
  }
  v16 = v29;
  Id = CTS_TLS_ThreadDescriptor::AddThreadToList(v29, (struct ITSThread *)v4);
  if ( Id < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_9;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v13 = 56;
    v14 = "Fail to add thread to thread descriptor";
    goto LABEL_8;
  }
  if ( v16 != *((CTS_TLS_ThreadDescriptor **)v7 + 81) )
  {
    TCntPtr<CTSBufferResult>::SafeRelease((char *)v7 + 648);
    *((_QWORD *)v7 + 81) = v16;
    if ( v16 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 + 4) + 8LL))(*((_QWORD *)v16 + 4));
  }
  Id = PAL_System_ThreadGetId((char *)a1[4] + 56);
  if ( Id < 0 )
    goto LABEL_9;
  v18 = (__int64 (__fastcall *)(__int64))a1[1];
  if ( v18 )
  {
    Id = v18((__int64)v9);
    if ( Id < 0 )
    {
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v23 = a1[1];
        v24 = "TSStaticThreadEntry";
        v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v26 = "pfnOnPreInit[%p] failed hr[0x%x]";
        v27 = 1015;
        v28 = Id;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v19,
          (unsigned int)&dword_18005544C,
          v20,
          v21,
          (__int64)&v26,
          (__int64)&v28,
          (__int64)&v25,
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&v23);
      }
      goto LABEL_9;
    }
  }
  Id = CTSThread::InitializeInThreadContext((CTSThread *)v4, v17);
  if ( Id < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_9;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    v13 = 57;
    v14 = "Failed to init in thread context";
LABEL_8:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v13,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)v14,
      Id);
    goto LABEL_9;
  }
  v22 = *((_QWORD *)v4 + 92);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
  Id = PAL_System_CondSignal(a1[2]);
  if ( Id >= 0 )
  {
    v8((__int64)v9);
    CTSThread::OnPostExitThreadProc((CTSThread *)v4);
    goto LABEL_12;
  }
LABEL_9:
  if ( v4 )
    CTSThread::ClearThreadDescriptor((CTSThread *)v4);
  *((_DWORD *)a1 + 10) = Id;
LABEL_12:
  TCntPtr<CTSBufferResult>::SafeRelease(&v29);
  TCntPtr<CTSThread>::SafeRelease(&v30);
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x18003cf20  push    rbp
0x18003cf22  push    rbx
0x18003cf23  push    rsi
0x18003cf24  push    rdi
0x18003cf25  push    r12
0x18003cf27  push    r13
0x18003cf29  push    r14
0x18003cf2b  push    r15
0x18003cf2d  mov     rbp, rsp
0x18003cf30  sub     rsp, 78h
0x18003cf34  xor     ebx, ebx
0x18003cf36  mov     rsi, rcx
0x18003cf39  mov     [rbp+arg_18], rbx
0x18003cf3d  mov     [rbp+arg_10], rbx
0x18003cf41  mov     rdi, [rcx+20h]
0x18003cf45  xor     r15d, r15d
0x18003cf48  mov     r13, [rcx]
0x18003cf4b  mov     r12, [rcx+18h]
0x18003cf4f  test    rdi, rdi
0x18003cf52  jz      short loc_18003CF77
0x18003cf54  lea     rcx, [rbp+arg_18]
0x18003cf58  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18003cf5d  mov     rcx, [rdi+28h]
0x18003cf61  mov     rbx, rdi
0x18003cf64  mov     [rbp+arg_18], rbx
0x18003cf68  mov     rax, [rcx]
0x18003cf6b  mov     rax, [rax+8]
0x18003cf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf74  mov     r15, rdi
0x18003cf77  lea     rdx, [rbp+arg_10]; struct CTS_TLS_ThreadDescriptor **
0x18003cf7b  xor     ecx, ecx; int
0x18003cf7d  call    ?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z; CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)
0x18003cf82  mov     edi, eax
0x18003cf84  test    eax, eax
0x18003cf86  jns     loc_18003D014
0x18003cf8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf93  lea     rax, WPP_GLOBAL_Control
0x18003cf9a  cmp     rcx, rax
0x18003cf9d  jz      short loc_18003CFDF
0x18003cf9f  test    byte ptr [rcx+1Ch], 8
0x18003cfa3  jz      short loc_18003CFDF
0x18003cfa5  cmp     byte ptr [rcx+19h], 2
0x18003cfa9  jb      short loc_18003CFDF
0x18003cfab  call    RdpX_GetActivityIdPrefix
0x18003cfb0  mov     edx, 37h ; '7'
0x18003cfb5  lea     rcx, aThreadDescript_0; "thread descriptor creation failed in bi"...
0x18003cfbc  mov     dword ptr [rsp+78h+var_50], edi
0x18003cfc0  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18003cfc7  mov     [rsp+78h+var_58], rcx
0x18003cfcc  mov     r9d, eax
0x18003cfcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfd6  mov     rcx, [rcx+10h]
0x18003cfda  call    WPP_SF_DsD
0x18003cfdf  test    rbx, rbx
0x18003cfe2  jz      short loc_18003CFEC
0x18003cfe4  mov     rcx, rbx; this
0x18003cfe7  call    ?ClearThreadDescriptor@CTSThread@@IEAAXXZ; CTSThread::ClearThreadDescriptor(void)
0x18003cfec  mov     [rsi+28h], edi
0x18003cfef  lea     rcx, [rbp+arg_10]
0x18003cff3  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x18003cff8  lea     rcx, [rbp+arg_18]
0x18003cffc  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18003d001  mov     eax, edi
0x18003d003  add     rsp, 78h
0x18003d007  pop     r15
0x18003d009  pop     r14
0x18003d00b  pop     r13
0x18003d00d  pop     r12
0x18003d00f  pop     rdi
0x18003d010  pop     rsi
0x18003d011  pop     rbx
0x18003d012  pop     rbp
0x18003d013  retn
0x18003d014  mov     r14, [rbp+arg_10]
0x18003d018  mov     rdx, rbx; struct ITSThread *
0x18003d01b  mov     rcx, r14; this
0x18003d01e  call    ?AddThreadToList@CTS_TLS_ThreadDescriptor@@AEAAJPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::AddThreadToList(ITSThread *)
0x18003d023  mov     edi, eax
0x18003d025  test    eax, eax
0x18003d027  jns     short loc_18003D05E
0x18003d029  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d030  lea     rax, WPP_GLOBAL_Control
0x18003d037  cmp     rcx, rax
0x18003d03a  jz      short loc_18003CFDF
0x18003d03c  test    byte ptr [rcx+1Ch], 8
0x18003d040  jz      short loc_18003CFDF
0x18003d042  cmp     byte ptr [rcx+19h], 2
0x18003d046  jb      short loc_18003CFDF
0x18003d048  call    RdpX_GetActivityIdPrefix
0x18003d04d  mov     edx, 38h ; '8'
0x18003d052  lea     rcx, aFailToAddThrea; "Fail to add thread to thread descriptor"
0x18003d059  jmp     loc_18003CFBC
0x18003d05e  lea     rdi, [r15+288h]
0x18003d065  cmp     r14, [rdi]
0x18003d068  jz      short loc_18003D08A
0x18003d06a  mov     rcx, rdi
0x18003d06d  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x18003d072  mov     [rdi], r14
0x18003d075  test    r14, r14
0x18003d078  jz      short loc_18003D08A
0x18003d07a  mov     rcx, [r14+20h]
0x18003d07e  mov     rax, [rcx]
0x18003d081  mov     rax, [rax+8]
0x18003d085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d08a  mov     rcx, [rsi+20h]
0x18003d08e  add     rcx, 38h ; '8'
0x18003d092  call    PAL_System_ThreadGetId
0x18003d097  mov     edi, eax
0x18003d099  test    eax, eax
0x18003d09b  js      loc_18003CFDF
0x18003d0a1  mov     rax, [rsi+8]
0x18003d0a5  test    rax, rax
0x18003d0a8  jz      loc_18003D149
0x18003d0ae  mov     rcx, r12
0x18003d0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0b6  mov     edi, eax
0x18003d0b8  test    eax, eax
0x18003d0ba  jns     loc_18003D149
0x18003d0c0  mov     eax, cs:dword_18005C008
0x18003d0c6  cmp     eax, 2
0x18003d0c9  jbe     loc_18003CFDF
0x18003d0cf  mov     rax, [rsi+8]
0x18003d0d3  lea     rdx, dword_18005544C
0x18003d0da  mov     [rbp+var_28], rax
0x18003d0de  lea     rax, aTsstaticthread; "TSStaticThreadEntry"
0x18003d0e5  mov     [rbp+var_20], rax
0x18003d0e9  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003d0f0  mov     [rbp+var_18], rax
0x18003d0f4  lea     rax, aPfnonpreinitPF; "pfnOnPreInit[%p] failed hr[0x%x]"
0x18003d0fb  mov     [rbp+var_10], rax
0x18003d0ff  lea     rax, [rbp+var_28]
0x18003d103  mov     [rsp+78h+var_30], rax
0x18003d108  lea     rax, [rbp+var_20]
0x18003d10c  mov     [rsp+78h+var_38], rax
0x18003d111  lea     rax, [rbp+arg_0]
0x18003d115  mov     [rsp+78h+var_40], rax
0x18003d11a  lea     rax, [rbp+var_18]
0x18003d11e  mov     [rsp+78h+var_48], rax
0x18003d123  lea     rax, [rbp+arg_8]
0x18003d127  mov     [rsp+78h+var_50], rax
0x18003d12c  lea     rax, [rbp+var_10]
0x18003d130  mov     [rsp+78h+var_58], rax
0x18003d135  mov     [rbp+arg_0], 3F7h
0x18003d13c  mov     [rbp+arg_8], edi
0x18003d13f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18003d144  jmp     loc_18003CFDF
0x18003d149  mov     rcx, rbx; this
0x18003d14c  call    ?InitializeInThreadContext@CTSThread@@AEAAJH@Z; CTSThread::InitializeInThreadContext(int)
0x18003d151  mov     edi, eax
0x18003d153  test    eax, eax
0x18003d155  jns     short loc_18003D198
0x18003d157  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d15e  lea     rax, WPP_GLOBAL_Control
0x18003d165  cmp     rcx, rax
0x18003d168  jz      loc_18003CFDF
0x18003d16e  test    byte ptr [rcx+1Ch], 8
0x18003d172  jz      loc_18003CFDF
0x18003d178  cmp     byte ptr [rcx+19h], 2
0x18003d17c  jb      loc_18003CFDF
0x18003d182  call    RdpX_GetActivityIdPrefix
0x18003d187  mov     edx, 39h ; '9'
0x18003d18c  lea     rcx, aFailedToInitIn; "Failed to init in thread context"
0x18003d193  jmp     loc_18003CFBC
0x18003d198  mov     rcx, [rbx+2E0h]
0x18003d19f  test    rcx, rcx
0x18003d1a2  jz      short loc_18003D1B0
0x18003d1a4  mov     rax, [rcx]
0x18003d1a7  mov     rax, [rax+18h]
0x18003d1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1b0  mov     rcx, [rsi+10h]
0x18003d1b4  call    PAL_System_CondSignal
0x18003d1b9  mov     edi, eax
0x18003d1bb  test    eax, eax
0x18003d1bd  js      loc_18003CFDF
0x18003d1c3  mov     rcx, r12
0x18003d1c6  mov     rax, r13
0x18003d1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1ce  mov     rcx, rbx; this
0x18003d1d1  call    ?OnPostExitThreadProc@CTSThread@@AEAAXXZ; CTSThread::OnPostExitThreadProc(void)
0x18003d1d6  jmp     loc_18003CFEF
```
