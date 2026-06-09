# CSQLSatelliteConnection::OpenTcpConnection(wchar_t const *,ulong,CSQLSatelliteConnection *,SNI_Conn * *,_GUID *,bool)

- ea: `0x100473340`
- end: `0x100473616`
- name: `?OpenTcpConnection@CSQLSatelliteConnection@@SAJPEB_WKPEAV1@PEAPEAVSNI_Conn@@PEAU_GUID@@_N@Z`
- size: `726`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, struct CSQLSatelliteConnection *, struct SNI_Conn **, struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1004730b0`

## callees

- `0x10040d8a0`
- `0x100425000`
- `0x100455f90`
- `0x100473340`
- `0x1004737e0`
- `0x100473a60`
- `0x1004781c0`
- `0x100478330`
- `0x100486af0`
- `0x100487cd6`
- `0x10048823d`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x100473566`
- `KERNEL32!GetCurrentThreadId` at `0x100473566`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004735d9`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004735d9`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100473398`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100473398`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1004733ab`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1004733ab`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100473389`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100473389`

## string_xrefs

- `0x100473415`: `Attempting to connect to %s\n`
- `0x10047357b`: `CSQLSatelliteConnection::OpenTcpConnection`
- `0x1004735e2`: `Failed to create Tcp connection on port %d, at CSQLSatelliteConnection::OpenTcpConnection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSQLSatelliteConnection::OpenTcpConnection(
        const wchar_t *a1,
        unsigned int a2,
        struct CSQLSatelliteConnection *a3,
        struct SNI_Conn **a4,
        struct _GUID *a5,
        bool a6)
{
  struct CSessionTraceFlags *v10; // rax
  unsigned int v11; // edi
  unsigned int v12; // ebx
  int v13; // eax
  struct SNI_Conn *v14; // r14
  struct ISatelliteExecutor *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  DWORD CurrentThreadId; // eax
  __int64 v19; // rdi
  int v21; // [rsp+20h] [rbp-E0h]
  struct SNI_Conn *v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  struct CSQLSatelliteConnection *v24; // [rsp+58h] [rbp-A8h]
  void (*v25)(void *, struct SNI_Packet *, unsigned int); // [rsp+60h] [rbp-A0h]
  void (*v26)(void *, struct SNI_Packet *, unsigned int); // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  void *v28; // [rsp+78h] [rbp-88h]
  void *v29; // [rsp+80h] [rbp-80h]
  void (__fastcall *v30)(struct SNI_Conn *, void *); // [rsp+88h] [rbp-78h]
  int v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-30h]
  unsigned int v39; // [rsp+D8h] [rbp-28h]
  DWORD v40; // [rsp+DCh] [rbp-24h]
  const char *v41; // [rsp+E0h] [rbp-20h]
  int v42; // [rsp+E8h] [rbp-18h]
  _BYTE v43[216]; // [rsp+F0h] [rbp-10h] BYREF
  int v44; // [rsp+1C8h] [rbp+C8h]
  __int64 v45; // [rsp+1D0h] [rbp+D0h]
  wchar_t Buffer[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  if ( CSQLSatelliteConnection::sm_useSSLAuth
    || (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 1339) & 8) != 0
    || (v10 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v10, 0x29DBu)
    || (v11 = 3, CSQLSatelliteConnection::sm_useSSLAuth) )
  {
    v11 = 6;
  }
  memset_0(Buffer, 0, 0x1FEu);
  v22 = 0;
  v12 = StringCchPrintfW(Buffer, 0xFFu, L"tcp:%s,%d", a1, a2);
  if ( (v12 & 0x80000000) == 0 )
  {
    TracePrintSatellite(L"Attempting to connect to %s\n", Buffer);
    v25 = CSQLSatelliteConnection::ReadCallBackForTcpClient;
    v27 = 0;
    v26 = CSQLSatelliteConnection::WriteCallBack;
    v31 = 0;
    v30 = CSQLSatelliteConnection::AcceptCallBack;
    v32 = 0;
    v28 = &CSQLSatelliteConnection::AddProviderDoneCallback;
    v34 = 1;
    v29 = &CSQLSatelliteConnection::AddProviderDoneIOCPCallback;
    v35 = 0;
    v36 = 0;
    v23 = 0x10000;
    v33 = -1;
    v24 = a3;
    v13 = SNIOpenSync(&v23, Buffer, 0, &v22, a6, -1);
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      else
        v12 = v13;
    }
    else
    {
      v14 = v22;
      v15 = g_satelliteExecutor;
      *((_QWORD *)a3 + 8) = v22;
      v16 = _RTDynamicCast_0(
              v15,
              0,
              &ISatelliteExecutor `RTTI Type Descriptor',
              &CSatelliteSpeesExecutor `RTTI Type Descriptor',
              0);
      if ( v16 && (*(_BYTE *)(v16 + 3156) & 1) == 0
        || (LOBYTE(v21) = 0,
            (v17 = CSQLSatelliteConnection::AuthenticateConnection(
                     a3,
                     v14,
                     0,
                     v11,
                     v21,
                     &CSQLSatelliteConnection::sm_certificateHashList,
                     a5)) == 0) )
      {
        *a4 = v22;
        return v12;
      }
      if ( v17 > 0 )
        v12 = (unsigned __int16)v17 | 0x80070000;
      else
        v12 = v17;
    }
  }
  _mm_lfence();
  if ( g_extensibilityErrorRingBuffer )
  {
    CurrentThreadId = GetCurrentThreadId();
    v19 = g_extensibilityErrorRingBuffer;
    v40 = CurrentThreadId;
    v38 = 0;
    v41 = "CSQLSatelliteConnection::OpenTcpConnection";
    v37 = 0;
    v39 = v12;
    v42 = 4044;
    v44 = 0;
    v45 = 0;
    if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
      StackFrames<24>::CaptureCurrent(v43, 1);
    if ( (dword_1005113AC & 0x10) != 0 )
      ExtensibilityErrorRecord::FireMatchingEvent(&v37, v43);
    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v19, &v37, v43);
  }
  CSQLSatelliteConnection::AbortConnection(
    a3,
    L"Failed to create Tcp connection on port %d, at CSQLSatelliteConnection::OpenTcpConnection",
    a2);
  return v12;
}

```

## disassembly

```asm
0x100473340  push    rbp
0x100473342  push    rbx
0x100473343  push    rsi
0x100473344  push    rdi
0x100473345  push    r12
0x100473347  push    r13
0x100473349  push    r14
0x10047334b  push    r15
0x10047334d  lea     rbp, [rsp-2F8h]
0x100473355  sub     rsp, 3F8h
0x10047335c  mov     rax, cs:__security_cookie
0x100473363  xor     rax, rsp
0x100473366  mov     [rbp+330h+var_50], rax
0x10047336d  cmp     cs:?sm_useSSLAuth@CSQLSatelliteConnection@@2_NA, 0; bool CSQLSatelliteConnection::sm_useSSLAuth
0x100473374  mov     r12, r9
0x100473377  mov     r13, [rbp+330h+arg_20]
0x10047337e  mov     rsi, r8
0x100473381  mov     r15d, edx
0x100473384  mov     rbx, rcx
0x100473387  jnz     short loc_1004733C3
0x100473389  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10047338f  test    byte ptr [rax+53Bh], 8
0x100473396  jnz     short loc_1004733C3
0x100473398  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10047339e  test    rax, rax
0x1004733a1  jz      short loc_1004733B5
0x1004733a3  mov     edx, 29DBh
0x1004733a8  mov     rcx, rax
0x1004733ab  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1004733b1  test    eax, eax
0x1004733b3  jnz     short loc_1004733C3
0x1004733b5  cmp     cs:?sm_useSSLAuth@CSQLSatelliteConnection@@2_NA, 0; bool CSQLSatelliteConnection::sm_useSSLAuth
0x1004733bc  mov     edi, 3
0x1004733c1  jz      short loc_1004733C8
0x1004733c3  mov     edi, 6
0x1004733c8  xor     edx, edx; Val
0x1004733ca  lea     rcx, [rbp+330h+Buffer]; void *
0x1004733d1  mov     r8d, 1FEh; Size
0x1004733d7  call    memset_0
0x1004733dc  xor     r14d, r14d
0x1004733df  mov     [rsp+430h+var_410], r15d
0x1004733e4  mov     r9, rbx
0x1004733e7  mov     [rsp+430h+var_3E8], r14
0x1004733ec  lea     r8, aTcpSD; "tcp:%s,%d"
0x1004733f3  mov     edx, 0FFh; unsigned __int64
0x1004733f8  lea     rcx, [rbp+330h+Buffer]; Buffer
0x1004733ff  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100473404  mov     ebx, eax
0x100473406  test    eax, eax
0x100473408  js      loc_100473559
0x10047340e  lea     rdx, [rbp+330h+Buffer]
0x100473415  lea     rcx, aAttemptingToCo; "Attempting to connect to %s\n"
0x10047341c  call    ?TracePrintSatellite@@YAXPEB_WZZ; TracePrintSatellite(wchar_t const *,...)
0x100473421  lea     rax, ?ReadCallBackForTcpClient@CSQLSatelliteConnection@@SAXPEAXPEAVSNI_Packet@@K@Z; CSQLSatelliteConnection::ReadCallBackForTcpClient(void *,SNI_Packet *,ulong)
0x100473428  mov     dword ptr [rsp+430h+var_408], 0FFFFFFFFh
0x100473430  mov     [rsp+430h+var_3D0], rax
0x100473435  lea     r9, [rsp+430h+var_3E8]
0x10047343a  lea     rax, ?WriteCallBack@CSQLSatelliteConnection@@SAXPEAXPEAVSNI_Packet@@K@Z; CSQLSatelliteConnection::WriteCallBack(void *,SNI_Packet *,ulong)
0x100473441  mov     [rsp+430h+var_3C0], r14
0x100473446  mov     [rsp+430h+var_3C8], rax
0x10047344b  lea     rdx, [rbp+330h+Buffer]
0x100473452  lea     rax, ?AcceptCallBack@CSQLSatelliteConnection@@SAXPEAVSNI_Conn@@PEAX@Z; CSQLSatelliteConnection::AcceptCallBack(SNI_Conn *,void *)
0x100473459  mov     [rbp+330h+var_3A0], r14d
0x10047345d  mov     [rbp+330h+var_3A8], rax
0x100473461  lea     rcx, [rsp+430h+var_3E0]
0x100473466  lea     rax, ?AddProviderDoneCallback@CSQLSatelliteConnection@@SAXPEAXW4ProviderNum@@KW4SNIAuthErrOps@@W4SNIAuthErrStates@@@Z; CSQLSatelliteConnection::AddProviderDoneCallback(void *,ProviderNum,ulong,SNIAuthErrOps,SNIAuthErrStates)
0x10047346d  mov     [rbp+330h+var_398], r14
0x100473471  mov     [rsp+430h+var_3B8], rax
0x100473476  xor     r8d, r8d
0x100473479  lea     rax, ?AddProviderDoneIOCPCallback@CSQLSatelliteConnection@@SAXPEAXW4ProviderNum@@KKW4SNIAuthErrStates@@@Z; CSQLSatelliteConnection::AddProviderDoneIOCPCallback(void *,ProviderNum,ulong,ulong,SNIAuthErrStates)
0x100473480  mov     [rbp+330h+var_388], 1
0x100473488  mov     [rbp+330h+var_3B0], rax
0x10047348c  movzx   eax, [rbp+330h+arg_28]
0x100473493  mov     [rsp+430h+var_410], eax
0x100473497  mov     [rbp+330h+var_380], r14
0x10047349b  mov     [rbp+330h+var_378], r14
0x10047349f  mov     [rsp+430h+var_3E0], 10000h
0x1004734a7  mov     [rbp+330h+var_390], 0FFFFFFFFFFFFFFFFh
0x1004734af  mov     [rsp+430h+var_3D8], rsi
0x1004734b4  call    SNIOpenSync
0x1004734b9  test    eax, eax
0x1004734bb  jnz     short loc_100473538
0x1004734bd  mov     r14, [rsp+430h+var_3E8]
0x1004734c2  lea     r9, ??_R0?AVCSatelliteSpeesExecutor@@@8; CSatelliteSpeesExecutor `RTTI Type Descriptor'
0x1004734c9  mov     rcx, cs:?g_satelliteExecutor@@3PEAVISatelliteExecutor@@EA; ISatelliteExecutor * g_satelliteExecutor
0x1004734d0  lea     r8, ??_R0?AVISatelliteExecutor@@@8; ISatelliteExecutor `RTTI Type Descriptor'
0x1004734d7  xor     edx, edx
0x1004734d9  mov     [rsi+40h], r14
0x1004734dd  mov     [rsp+430h+var_410], eax
0x1004734e1  call    __RTDynamicCast_0
0x1004734e6  test    rax, rax
0x1004734e9  jz      short loc_1004734F6
0x1004734eb  movzx   eax, byte ptr [rax+0C54h]
0x1004734f2  and     al, 1
0x1004734f4  jz      short loc_10047354B
0x1004734f6  lea     rax, ?sm_certificateHashList@CSQLSatelliteConnection@@2VCertificateHashList@@A; CertificateHashList CSQLSatelliteConnection::sm_certificateHashList
0x1004734fd  mov     [rsp+430h+var_400], r13
0x100473502  mov     [rsp+430h+var_408], rax
0x100473507  mov     r9d, edi
0x10047350a  xor     r8d, r8d
0x10047350d  mov     byte ptr [rsp+430h+var_410], 0
0x100473512  mov     rdx, r14
0x100473515  mov     rcx, rsi
0x100473518  call    ?AuthenticateConnection@CSQLSatelliteConnection@@QEAAKPEAVSNI_Conn@@_NW4ProviderNum@@1PEAVCertificateHashList@@PEBU_GUID@@@Z; CSQLSatelliteConnection::AuthenticateConnection(SNI_Conn *,bool,ProviderNum,bool,CertificateHashList *,_GUID const *)
0x10047351d  test    eax, eax
0x10047351f  jz      short loc_10047354B
0x100473521  jg      short loc_10047352A
0x100473523  mov     ebx, eax
0x100473525  xor     r14d, r14d
0x100473528  jmp     short loc_100473547
0x10047352a  movzx   ebx, ax
0x10047352d  or      ebx, 80070000h
0x100473533  xor     r14d, r14d
0x100473536  jmp     short loc_100473547
0x100473538  jg      short loc_10047353E
0x10047353a  mov     ebx, eax
0x10047353c  jmp     short loc_100473547
0x10047353e  movzx   ebx, ax
0x100473541  or      ebx, 80070000h
0x100473547  test    ebx, ebx
0x100473549  js      short loc_100473559
0x10047354b  mov     rax, [rsp+430h+var_3E8]
0x100473550  mov     [r12], rax
0x100473554  jmp     loc_1004735F1
0x100473559  lfence
0x10047355c  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100473564  jz      short loc_1004735DF
0x100473566  call    cs:__imp_GetCurrentThreadId
0x10047356c  mov     rdi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100473573  xor     ecx, ecx
0x100473575  mov     [rbp+330h+var_354], eax
0x100473578  xorps   xmm0, xmm0
0x10047357b  lea     rax, aCsqlsatellitec_1; "CSQLSatelliteConnection::OpenTcpConnect"...
0x100473582  mov     [rbp+330h+var_360], rcx
0x100473586  mov     [rbp+330h+var_350], rax
0x10047358a  movups  [rbp+330h+var_370], xmm0
0x10047358e  mov     [rbp+330h+var_358], ebx
0x100473591  mov     [rbp+330h+var_348], 0FCCh
0x100473598  mov     [rbp+330h+var_268], r14d
0x10047359f  mov     [rbp+330h+var_260], r14
0x1004735a6  cmp     [rdi+40h], rcx
0x1004735aa  jz      short loc_1004735B8
0x1004735ac  lea     edx, [rcx+1]
0x1004735af  lea     rcx, [rbp+330h+var_340]
0x1004735b3  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004735b8  test    byte ptr cs:dword_1005113AC, 10h
0x1004735bf  jz      short loc_1004735CE
0x1004735c1  lea     rdx, [rbp+330h+var_340]
0x1004735c5  lea     rcx, [rbp+330h+var_370]
0x1004735c9  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004735ce  lea     r8, [rbp+330h+var_340]
0x1004735d2  mov     rcx, rdi
0x1004735d5  lea     rdx, [rbp+330h+var_370]
0x1004735d9  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004735df  mov     r8d, r15d
0x1004735e2  lea     rdx, aFailedToCreate_1; "Failed to create Tcp connection on port"...
0x1004735e9  mov     rcx, rsi; this
0x1004735ec  call    ?AbortConnection@CSQLSatelliteConnection@@QEAAXPEB_WZZ; CSQLSatelliteConnection::AbortConnection(wchar_t const *,...)
0x1004735f1  mov     eax, ebx
0x1004735f3  mov     rcx, [rbp+330h+var_50]
0x1004735fa  xor     rcx, rsp; StackCookie
0x1004735fd  call    __security_check_cookie
0x100473602  add     rsp, 3F8h
0x100473609  pop     r15
0x10047360b  pop     r14
0x10047360d  pop     r13
0x10047360f  pop     r12
0x100473611  pop     rdi
0x100473612  pop     rsi
0x100473613  pop     rbx
0x100473614  pop     rbp
0x100473615  retn
```
