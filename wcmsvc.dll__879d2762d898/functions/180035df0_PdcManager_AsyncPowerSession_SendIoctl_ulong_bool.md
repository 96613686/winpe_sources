# PdcManager::AsyncPowerSession::SendIoctl(ulong,bool)

- ea: `0x180035df0`
- end: `0x18003633b`
- name: `?SendIoctl@AsyncPowerSession@PdcManager@@AEAAJK_N@Z`
- size: `1355`
- prototype: `int(PdcManager::AsyncPowerSession *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035d3c`
- `0x180041588`

## callees

- `0x180002a8c`
- `0x180027250`
- `0x180033afc`
- `0x180035bc4`
- `0x180035df0`
- `0x18003a08c`
- `0x180041a20`
- `0x180084f50`
- `0x18008534c`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800361c3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800361c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036169`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003617c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003617c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036174`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036174`
- `ntdll!EtwEventWriteTransfer` at `0x1800362ff`
- `ntdll!EtwEventWriteTransfer` at `0x1800362ff`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180035f01`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180035f01`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003611e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003611e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180035f89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180035f89`

## string_xrefs

- `0x1800361d5`: `onecoreuap\net\wcm\service\base\server\pdcasyncpowersession.cpp`
- `0x180035fc5`: `ERROR_NDIS_ADAPTER_NOT_FOUND: failed to find the network interface or network interface is not ready`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall PdcManager::AsyncPowerSession::SendIoctl(PdcManager::AsyncPowerSession *this, DWORD a2, char a3)
{
  struct _OVERLAPPED *lpOverlapped; // rsi
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  BOOL v9; // ebx
  DWORD LastError; // eax
  int v11; // r8d
  int v12; // r9d
  DWORD v13; // r14d
  const char *v14; // rcx
  const char *v15; // rcx
  const char *v16; // rcx
  const union _NET_LUID_LH *v17; // rdx
  ULONG_PTR Internal; // rcx
  char *v19; // rsi
  DWORD v20; // ebx
  int v21; // ebx
  const char *v23; // rcx
  __int64 v24; // rbx
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-118h]
  unsigned int v26; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v27[2]; // [rsp+48h] [rbp-F0h] BYREF
  const char *v28; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD v29[2]; // [rsp+58h] [rbp-E0h] BYREF
  int v30; // [rsp+68h] [rbp-D0h]
  char v31; // [rsp+6Ch] [rbp-CCh]
  __int16 v32; // [rsp+6Dh] [rbp-CBh]
  char v33; // [rsp+6Fh] [rbp-C9h]
  _QWORD *v34; // [rsp+90h] [rbp-A8h]
  _QWORD InBuffer[3]; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-80h]
  int *v38; // [rsp+C0h] [rbp-78h] BYREF
  int v39; // [rsp+C8h] [rbp-70h]
  int v40; // [rsp+CCh] [rbp-6Ch]
  void *v41; // [rsp+D0h] [rbp-68h]
  int v42; // [rsp+D8h] [rbp-60h]
  int v43; // [rsp+DCh] [rbp-5Ch]
  const char *v44; // [rsp+E0h] [rbp-58h]
  int v45; // [rsp+E8h] [rbp-50h]
  int v46; // [rsp+ECh] [rbp-4Ch]
  char *v47; // [rsp+F0h] [rbp-48h]
  __int64 v48; // [rsp+F8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v29[0] = off_1800F8640;
  v29[1] = this;
  v30 = *((_DWORD *)this + 22);
  v31 = a3;
  v32 = *(_WORD *)((char *)&v37 + 5);
  v33 = HIBYTE(v37);
  v34 = v29;
  v36 = (__int64)v29;
  lpOverlapped = (struct _OVERLAPPED *)operator new(0x68u);
  *(_OWORD *)&lpOverlapped->Internal = 0;
  *(_OWORD *)&lpOverlapped->Offset = 0;
  lpOverlapped[1].Internal = 0;
  lpOverlapped[3].Internal = 0;
  if ( v34 )
  {
    if ( v34 == v29 )
    {
      lpOverlapped[3].Internal = (*(__int64 (__fastcall **)(_QWORD *, ULONG_PTR *))(*v34 + 8LL))(
                                   v34,
                                   &lpOverlapped[1].InternalHigh);
      if ( !v34 )
        goto LABEL_7;
      v7 = v29;
      LOBYTE(v7) = v34 != v29;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v34 + 32LL))(v34, v7);
    }
    else
    {
      lpOverlapped[3].Internal = (ULONG_PTR)v34;
    }
    v34 = 0;
  }
LABEL_7:
  *(_OWORD *)&lpOverlapped->Internal = 0;
  *(_OWORD *)&lpOverlapped->Offset = 0;
  ++*((_DWORD *)this + 26);
  StartThreadpoolIo(*((PTP_IO *)this + 12));
  *(_OWORD *)&lpOverlapped->Internal = 0;
  *(_OWORD *)&lpOverlapped->Offset = 0;
  if ( v34 )
  {
    v8 = v29;
    LOBYTE(v8) = v34 != v29;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v34 + 32LL))(v34, v8);
    v34 = 0;
  }
  InBuffer[0] = 1311104;
  InBuffer[2] = 15;
  InBuffer[1] = *((_QWORD *)this + 4);
  v9 = DeviceIoControl(*((HANDLE *)this + 1), a2, InBuffer, 0x18u, 0, 0, 0, lpOverlapped);
  LastError = GetLastError();
  v13 = LastError;
  if ( v9 || LastError == 997 )
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v23 = "Release";
      if ( *((_DWORD *)this + 22) != 3 )
        v23 = "Acquire";
      v47 = (char *)this + 16;
      v48 = 16;
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v44 = v23;
      v45 = v24 + 1;
      v46 = 0;
      v36 = 0x50B000000LL;
      v37 = 0;
      v38 = off_18013A128;
      v39 = *(unsigned __int16 *)off_18013A128;
      v40 = 2;
      v41 = &unk_180114CA0;
      v42 = 84;
      v43 = 1;
      v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v36, 0, 0, 4, &v38);
    }
    return 0;
  }
  if ( LastError == -2144075770 )
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v28 = "ERROR_NDIS_ADAPTER_NOT_FOUND: failed to find the network interface or network interface is not ready";
      v26 = -2144075770;
      *(_QWORD *)v27 = (char *)this + 16;
      v14 = "Release";
      if ( *((_DWORD *)this + 22) != 3 )
        v14 = "Acquire";
      v36 = (__int64)v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v14,
        (unsigned int)byte_180114BD3,
        v11,
        v12,
        (__int64)&v36,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v28);
    }
  }
  else if ( LastError == -2144075589 )
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v36 = (__int64)"ERROR_NDIS_NOT_SUPPORTED: Network interface does not support this request";
      v26 = -2144075589;
      *(_QWORD *)v27 = (char *)this + 16;
      v15 = "Release";
      if ( *((_DWORD *)this + 22) != 3 )
        v15 = "Acquire";
      v28 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v15,
        (unsigned int)&dword_180114C34,
        v11,
        v12,
        (__int64)&v28,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v36);
    }
  }
  else if ( (unsigned int)dword_18013A120 > 5 )
  {
    v26 = LastError;
    v36 = (__int64)this + 16;
    v16 = "Release";
    if ( *((_DWORD *)this + 22) != 3 )
      v16 = "Acquire";
    *(_QWORD *)v27 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (_DWORD)v16,
      (unsigned int)byte_180114B7B,
      v11,
      v12,
      (__int64)v27,
      (__int64)&v36,
      (__int64)&v26);
  }
  CancelThreadpoolIo(*((PTP_IO *)this + 12));
  if ( lpOverlapped )
  {
    Internal = lpOverlapped[3].Internal;
    if ( Internal )
    {
      LOBYTE(v17) = Internal != (_QWORD)lpOverlapped + 40;
      (*(void (__fastcall **)(ULONG_PTR, const union _NET_LUID_LH *))(*(_QWORD *)Internal + 32LL))(Internal, v17);
      lpOverlapped[3].Internal = 0;
    }
    operator delete(lpOverlapped, (const struct std::nothrow_t *)0x68);
  }
  --*((_DWORD *)this + 26);
  v19 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v20 = GetLastError();
    CloseHandle(v19);
    SetLastError(v20);
  }
  *((_QWORD *)this + 1) = -1;
  SleepStudy::StopTrackingInterface((PdcManager::AsyncPowerSession *)((char *)this + 32), v17);
  if ( !v13 )
    return 0;
  if ( a3 )
  {
    v21 = _InterlockedDecrement(&dword_18013F420);
    if ( v21 >= 0 )
    {
      if ( !v21 )
        SetEvent(hEvent);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xCC,
           (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdcasyncpowersession.cpp",
           (const char *)v13,
           lpOutBuffer);
}

```

## disassembly

```asm
0x180035df0  mov     r11, rsp
0x180035df3  mov     [r11+18h], rbx
0x180035df7  mov     [r11+20h], rsi
0x180035dfb  push    rdi
0x180035dfc  push    r12
0x180035dfe  push    r13
0x180035e00  push    r14
0x180035e02  push    r15
0x180035e04  sub     rsp, 110h
0x180035e0b  mov     rax, cs:__security_cookie
0x180035e12  xor     rax, rsp
0x180035e15  mov     [rsp+138h+var_38], rax
0x180035e1d  movzx   r12d, r8b
0x180035e21  mov     ebx, edx
0x180035e23  mov     rdi, rcx
0x180035e26  lea     rax, off_1800F8640
0x180035e2d  mov     [rsp+138h+var_E0], rax
0x180035e32  mov     [rsp+138h+var_D8], rcx
0x180035e37  mov     eax, [rcx+58h]
0x180035e3a  mov     [rsp+138h+var_D0], eax
0x180035e3e  mov     [rsp+138h+var_CC], r8b
0x180035e43  movzx   eax, word ptr [r11-7Bh]
0x180035e48  mov     [rsp+138h+var_CB], ax
0x180035e4d  movzx   eax, byte ptr [r11-79h]
0x180035e52  mov     [rsp+138h+var_C9], al
0x180035e56  lea     rax, [rsp+138h+var_E0]
0x180035e5b  mov     [r11-0A8h], rax
0x180035e62  lea     rax, [rsp+138h+var_E0]
0x180035e67  mov     [r11-88h], rax
0x180035e6e  mov     ecx, 68h ; 'h'; Size
0x180035e73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035e78  mov     rsi, rax
0x180035e7b  xorps   xmm0, xmm0
0x180035e7e  movups  xmmword ptr [rax], xmm0
0x180035e81  movups  xmmword ptr [rax+10h], xmm0
0x180035e85  xor     r14d, r14d
0x180035e88  mov     [rax+20h], r14
0x180035e8c  lea     r15, [rax+28h]
0x180035e90  mov     [r15+38h], r14
0x180035e94  mov     rcx, [rsp+138h+var_A8]
0x180035e9c  test    rcx, rcx
0x180035e9f  jz      short loc_180035EF0
0x180035ea1  lea     rax, [rsp+138h+var_E0]
0x180035ea6  cmp     rcx, rax
0x180035ea9  jnz     short loc_180035EE4
0x180035eab  mov     rax, [rcx]
0x180035eae  mov     rdx, r15
0x180035eb1  mov     rax, [rax+8]
0x180035eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035eba  mov     [r15+38h], rax
0x180035ebe  mov     rcx, [rsp+138h+var_A8]
0x180035ec6  test    rcx, rcx
0x180035ec9  jz      short loc_180035EF0
0x180035ecb  mov     rax, [rcx]
0x180035ece  lea     rdx, [rsp+138h+var_E0]
0x180035ed3  cmp     rcx, rdx
0x180035ed6  setnz   dl
0x180035ed9  mov     rax, [rax+20h]
0x180035edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ee2  jmp     short loc_180035EE8
0x180035ee4  mov     [r15+38h], rcx
0x180035ee8  mov     [rsp+138h+var_A8], r14
0x180035ef0  xorps   xmm0, xmm0
0x180035ef3  movups  xmmword ptr [rsi], xmm0
0x180035ef6  movups  xmmword ptr [rsi+10h], xmm0
0x180035efa  inc     dword ptr [rdi+68h]
0x180035efd  mov     rcx, [rdi+60h]; pio
0x180035f01  call    cs:__imp_StartThreadpoolIo
0x180035f07  xorps   xmm0, xmm0
0x180035f0a  movups  xmmword ptr [rsi], xmm0
0x180035f0d  movups  xmmword ptr [rsi+10h], xmm0
0x180035f11  mov     rcx, [rsp+138h+var_A8]
0x180035f19  test    rcx, rcx
0x180035f1c  jz      short loc_180035F3D
0x180035f1e  mov     rax, [rcx]
0x180035f21  lea     rdx, [rsp+138h+var_E0]
0x180035f26  cmp     rcx, rdx
0x180035f29  setnz   dl
0x180035f2c  mov     rax, [rax+20h]
0x180035f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f35  mov     [rsp+138h+var_A8], r14
0x180035f3d  mov     [rsp+138h+InBuffer], 140180h
0x180035f49  mov     [rsp+138h+var_90], 0Fh
0x180035f55  mov     rax, [rdi+20h]
0x180035f59  mov     [rsp+138h+var_98], rax
0x180035f61  mov     [rsp+138h+lpOverlapped], rsi; lpOverlapped
0x180035f66  mov     [rsp+138h+lpBytesReturned], r14; lpBytesReturned
0x180035f6b  mov     [rsp+138h+nOutBufferSize], r14d; nOutBufferSize
0x180035f70  mov     [rsp+138h+lpOutBuffer], r14; lpOutBuffer
0x180035f75  mov     r9d, 18h; nInBufferSize
0x180035f7b  lea     r8, [rsp+138h+InBuffer]; lpInBuffer
0x180035f83  mov     edx, ebx; dwIoControlCode
0x180035f85  mov     rcx, [rdi+8]; hDevice
0x180035f89  call    cs:__imp_DeviceIoControl
0x180035f8f  mov     ebx, eax
0x180035f91  call    cs:__imp_GetLastError
0x180035f97  mov     r14d, eax
0x180035f9a  test    ebx, ebx
0x180035f9c  jnz     loc_1800361EB
0x180035fa2  cmp     eax, 3E5h
0x180035fa7  jz      loc_1800361EB
0x180035fad  mov     eax, cs:dword_18013A120
0x180035fb3  cmp     r14d, 80340006h
0x180035fba  jnz     short loc_180036039
0x180035fbc  cmp     eax, 5
0x180035fbf  jbe     loc_18003611A
0x180035fc5  lea     rax, aErrorNdisAdapt; "ERROR_NDIS_ADAPTER_NOT_FOUND: failed to"...
0x180035fcc  mov     [rsp+138h+var_E8], rax
0x180035fd1  mov     [rsp+138h+var_F8], r14d
0x180035fd6  lea     rax, [rdi+10h]
0x180035fda  mov     qword ptr [rsp+138h+var_F0], rax
0x180035fdf  lea     rdx, aAcquire; "Acquire"
0x180035fe6  lea     rcx, aRelease; "Release"
0x180035fed  cmp     dword ptr [rdi+58h], 3
0x180035ff1  cmovnz  rcx, rdx
0x180035ff5  mov     [rsp+138h+var_88], rcx
0x180035ffd  lea     rax, [rsp+138h+var_E8]
0x180036002  mov     [rsp+138h+lpOverlapped], rax
0x180036007  lea     rax, [rsp+138h+var_F8]
0x18003600c  mov     [rsp+138h+lpBytesReturned], rax
0x180036011  lea     rax, [rsp+138h+var_F0]
0x180036016  mov     qword ptr [rsp+138h+nOutBufferSize], rax
0x18003601b  lea     rax, [rsp+138h+var_88]
0x180036023  mov     [rsp+138h+lpOutBuffer], rax
0x180036028  lea     rdx, byte_180114BD3
0x18003602f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036034  jmp     loc_18003611A
0x180036039  cmp     r14d, 803400BBh
0x180036040  jnz     short loc_1800360BC
0x180036042  cmp     eax, 5
0x180036045  jbe     loc_18003611A
0x18003604b  lea     rax, aErrorNdisNotSu; "ERROR_NDIS_NOT_SUPPORTED: Network inter"...
0x180036052  mov     [rsp+138h+var_88], rax
0x18003605a  mov     [rsp+138h+var_F8], r14d
0x18003605f  lea     rax, [rdi+10h]
0x180036063  mov     qword ptr [rsp+138h+var_F0], rax
0x180036068  lea     rdx, aAcquire; "Acquire"
0x18003606f  lea     rcx, aRelease; "Release"
0x180036076  cmp     dword ptr [rdi+58h], 3
0x18003607a  cmovnz  rcx, rdx
0x18003607e  mov     [rsp+138h+var_E8], rcx
0x180036083  lea     rax, [rsp+138h+var_88]
0x18003608b  mov     [rsp+138h+lpOverlapped], rax
0x180036090  lea     rax, [rsp+138h+var_F8]
0x180036095  mov     [rsp+138h+lpBytesReturned], rax
0x18003609a  lea     rax, [rsp+138h+var_F0]
0x18003609f  mov     qword ptr [rsp+138h+nOutBufferSize], rax
0x1800360a4  lea     rax, [rsp+138h+var_E8]
0x1800360a9  mov     [rsp+138h+lpOutBuffer], rax
0x1800360ae  lea     rdx, dword_180114C34
0x1800360b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800360ba  jmp     short loc_18003611A
0x1800360bc  cmp     eax, 5
0x1800360bf  jbe     short loc_18003611A
0x1800360c1  mov     [rsp+138h+var_F8], r14d
0x1800360c6  lea     rax, [rdi+10h]
0x1800360ca  mov     [rsp+138h+var_88], rax
0x1800360d2  lea     rdx, aAcquire; "Acquire"
0x1800360d9  lea     rcx, aRelease; "Release"
0x1800360e0  cmp     dword ptr [rdi+58h], 3
0x1800360e4  cmovnz  rcx, rdx
0x1800360e8  mov     qword ptr [rsp+138h+var_F0], rcx
0x1800360ed  lea     rax, [rsp+138h+var_F8]
0x1800360f2  mov     [rsp+138h+lpBytesReturned], rax
0x1800360f7  lea     rax, [rsp+138h+var_88]
0x1800360ff  mov     qword ptr [rsp+138h+nOutBufferSize], rax
0x180036104  lea     rax, [rsp+138h+var_F0]
0x180036109  mov     [rsp+138h+lpOutBuffer], rax; unsigned int
0x18003610e  lea     rdx, byte_180114B7B
0x180036115  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003611a  mov     rcx, [rdi+60h]; pio
0x18003611e  call    cs:__imp_CancelThreadpoolIo
0x180036124  test    rsi, rsi
0x180036127  jz      short loc_180036158
0x180036129  mov     rcx, [r15+38h]
0x18003612d  test    rcx, rcx
0x180036130  jz      short loc_18003614B
0x180036132  mov     rax, [rcx]
0x180036135  cmp     rcx, r15
0x180036138  setnz   dl
0x18003613b  mov     rax, [rax+20h]
0x18003613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036144  xor     r8d, r8d
0x180036147  mov     [r15+38h], r8
0x18003614b  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x180036150  mov     rcx, rsi; void *
0x180036153  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036158  dec     dword ptr [rdi+68h]
0x18003615b  mov     rsi, [rdi+8]
0x18003615f  lea     rax, [rsi-1]
0x180036163  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036167  ja      short loc_180036182
0x180036169  call    cs:__imp_GetLastError
0x18003616f  mov     ebx, eax
0x180036171  mov     rcx, rsi; hObject
0x180036174  call    cs:__imp_CloseHandle
0x18003617a  mov     ecx, ebx; dwErrCode
0x18003617c  call    cs:__imp_SetLastError
0x180036182  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180036189  mov     [rdi+8], rbx
0x18003618d  lea     rcx, [rdi+20h]; this
0x180036191  call    ?StopTrackingInterface@SleepStudy@@YAXAEBT_NET_LUID_LH@@@Z; SleepStudy::StopTrackingInterface(_NET_LUID_LH const &)
0x180036196  test    r14d, r14d
0x180036199  jz      loc_180036305
0x18003619f  test    r12b, r12b
0x1800361a2  jz      short loc_1800361CA
0x1800361a4  lock xadd cs:dword_18013F420, ebx
0x1800361ac  sub     ebx, 1
0x1800361af  jns     short loc_1800361B8
0x1800361b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800361b6  jmp     short loc_1800361CA
0x1800361b8  test    ebx, ebx
0x1800361ba  jnz     short loc_1800361CA
0x1800361bc  mov     rcx, cs:hEvent; hEvent
0x1800361c3  call    cs:__imp_SetEvent
0x1800361c9  nop
0x1800361ca  mov     rcx, [rsp+138h]; this
0x1800361d2  mov     r9d, r14d; char *
0x1800361d5  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800361dc  mov     edx, 0CCh; void *
0x1800361e1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800361e6  jmp     loc_18003630D
0x1800361eb  mov     eax, cs:dword_18013A120
0x1800361f1  cmp     eax, 5
0x1800361f4  jbe     loc_180036305
0x1800361fa  lea     rax, [rdi+10h]
0x1800361fe  lea     rdx, aAcquire; "Acquire"
0x180036205  lea     rcx, aRelease; "Release"
0x18003620c  cmp     dword ptr [rdi+58h], 3
0x180036210  cmovnz  rcx, rdx
0x180036214  mov     [rsp+138h+var_48], rax
0x18003621c  mov     [rsp+138h+var_40], 10h
0x180036228  xor     r8d, r8d
0x18003622b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180036232  lea     rbx, [rbx+1]
0x180036236  cmp     [rcx+rbx], r8b
0x18003623a  jnz     short loc_180036232
0x18003623c  mov     [rsp+138h+var_58], rcx
0x180036244  lea     eax, [rbx+1]
0x180036247  mov     [rsp+138h+var_50], eax
0x18003624e  mov     [rsp+138h+var_4C], r8d
0x180036256  mov     dword ptr [rsp+138h+var_88], 0B000000h
0x180036261  movzx   eax, cs:word_180114C96
0x180036268  mov     dword ptr [rsp+138h+var_88+4], eax
0x18003626f  mov     [rsp+138h+var_80], r8
0x180036277  mov     rax, cs:off_18013A128
0x18003627e  mov     [rsp+138h+var_78], rax
0x180036286  movzx   eax, word ptr [rax]
0x180036289  mov     [rsp+138h+var_70], eax
0x180036290  mov     [rsp+138h+var_6C], 2
0x18003629b  lea     rax, unk_180114CA0
0x1800362a2  mov     [rsp+138h+var_68], rax
0x1800362aa  mov     [rsp+138h+var_60], 54h ; 'T'
0x1800362b5  mov     [rsp+138h+var_5C], 1
0x1800362c0  lea     rax, _TraceLoggingMetadataEnd
0x1800362c7  lea     rcx, _TraceLoggingMetadata
0x1800362ce  sub     eax, ecx
0x1800362d0  mov     [rsp+138h+var_F8], eax
0x1800362d4  mov     eax, [rsp+138h+var_F8]
0x1800362d8  lea     rax, [rsp+138h+var_78]
0x1800362e0  mov     qword ptr [rsp+138h+nOutBufferSize], rax
0x1800362e5  mov     dword ptr [rsp+138h+lpOutBuffer], 4
0x1800362ed  xor     r9d, r9d
0x1800362f0  lea     rdx, [rsp+138h+var_88]
0x1800362f8  mov     rcx, cs:RegHandle
0x1800362ff  call    cs:__imp_EtwEventWriteTransfer
0x180036305  xor     eax, eax
0x180036307  jmp     short loc_18003630D
0x180036309  mov     eax, [rsp+138h+var_F8]
0x18003630d  mov     rcx, [rsp+138h+var_38]
0x180036315  xor     rcx, rsp; StackCookie
0x180036318  call    __security_check_cookie
0x18003631d  lea     r11, [rsp+138h+var_28]
0x180036325  mov     rbx, [r11+40h]
0x180036329  mov     rsi, [r11+48h]
0x18003632d  mov     rsp, r11
0x180036330  pop     r15
0x180036332  pop     r14
0x180036334  pop     r13
0x180036336  pop     r12
0x180036338  pop     rdi
0x180036339  retn
```
