# CVdsVolume::PostExtendVolumeHandler(void *)

- ea: `0x140024720`
- end: `0x140024b67`
- name: `?PostExtendVolumeHandler@CVdsVolume@@SAKPEAX@Z`
- size: `1095`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14000d0f0`
- `0x14000e270`
- `0x14000e6bc`
- `0x14000f930`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x140013298`
- `0x140024720`
- `0x140035bd4`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002482f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024905`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024ae2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002482f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024905`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024ae2`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400249ee`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400249ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024a75`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140024a6b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140024a6b`
- `vdsutil!OpenDevice` at `0x140024973`
- `vdsutil!OpenDevice` at `0x140024973`
- `vdsutil!VdsTraceEx` at `0x140024822`
- `vdsutil!VdsTraceEx` at `0x140024869`
- `vdsutil!VdsTraceEx` at `0x1400248b0`
- `vdsutil!VdsTraceEx` at `0x14002491c`
- `vdsutil!VdsTraceEx` at `0x140024941`
- `vdsutil!VdsTraceEx` at `0x1400249a4`
- `vdsutil!VdsTraceEx` at `0x140024a09`
- `vdsutil!VdsTraceEx` at `0x140024a9d`
- `vdsutil!VdsTraceEx` at `0x140024ab1`
- `vdsutil!VdsTraceEx` at `0x140024822`
- `vdsutil!VdsTraceEx` at `0x140024869`
- `vdsutil!VdsTraceEx` at `0x1400248b0`
- `vdsutil!VdsTraceEx` at `0x14002491c`
- `vdsutil!VdsTraceEx` at `0x140024941`
- `vdsutil!VdsTraceEx` at `0x1400249a4`
- `vdsutil!VdsTraceEx` at `0x140024a09`
- `vdsutil!VdsTraceEx` at `0x140024a9d`
- `vdsutil!VdsTraceEx` at `0x140024ab1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002475a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002475a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140024b43`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140024b43`

## string_xrefs

- `0x140024998`: `CVdsVolume::PostExtendVolumeHandler,3: Failed to open handle to the volume: %lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CVdsVolume::PostExtendVolumeHandler(__int64 *Parameter)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  int v4; // eax
  int v5; // ebx
  CVdsServiceModule *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // esi
  unsigned __int16 *v11; // rbx
  int v12; // eax
  unsigned int v13; // esi
  unsigned int v14; // r9d
  NTSTATUS v15; // eax
  NTSTATUS v16; // ebx
  unsigned int v17; // ebx
  signed int LastError; // eax
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  CVdsServiceModule *v21; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 InBuffer; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[16]; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v31[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v32; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v33; // [rsp+D8h] [rbp-28h]
  __int128 v34; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v35; // [rsp+F8h] [rbp-8h]
  __int128 FsInformation; // [rsp+100h] [rbp+0h] BYREF
  __int64 v37; // [rsp+110h] [rbp+10h]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v30, 0x5Eu, "CVdsVolume::PostExtendVolumeHandler()");
  v21 = 0;
  InBuffer = 0;
  v20 = -2147467259;
  BytesReturned = 0;
  v24 = 0;
  v28 = 0;
  FileHandle = (HANDLE)-1LL;
  v27 = 0;
  memset(v31, 0, sizeof(v31));
  FsInformation = 0;
  v37 = 0;
  IoStatusBlock = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v26 = Parameter;
  ATL::CComPtrBase<CVdsEnumObject>::Attach(&v24, *Parameter);
  v2 = Parameter[1];
  v28 = v2;
  v3 = v24;
  v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, CVdsServiceModule **))(v24 + 64))(
         *(_QWORD *)(v24 + 64),
         &IID_IVdsAsync,
         &v21);
  v5 = v4;
  if ( v4 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler: pAsync QueryInterface failed: %lX", v4);
    *(_DWORD *)(v3 + 104) = v5;
    SetEvent(*(HANDLE *)(v3 + 96));
LABEL_37:
    v21 = 0;
    goto LABEL_38;
  }
  v7 = (*(__int64 (__fastcall **)(CVdsServiceModule *, int *, struct _GUID *))(*(_QWORD *)v21 + 32LL))(v21, &v20, v31);
  v8 = v7;
  if ( v7 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler: pAsync->Wait failed: %lX", v7);
    VdsLogError(0xC2000009, 0, 0, v8, 0x20A0001u, 0);
LABEL_5:
    *(_DWORD *)(v3 + 104) = -2147467259;
    goto LABEL_34;
  }
  if ( v20 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler: pAsync->Wait returned error: %lX", v20);
LABEL_8:
    *(_DWORD *)(v3 + 104) = v20;
    goto LABEL_34;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v2 + 24LL))(v2, &v32);
  v10 = v9;
  if ( v9 < 0 )
  {
    VdsLogError(0xC2000009, 0, 0, v9, 0x20A0002u, 0);
    *(_DWORD *)(v3 + 104) = -2147467259;
    SetEvent(*(HANDLE *)(v3 + 96));
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler,1: Failed to get volume properties returned error: %lX", v20);
    goto LABEL_35;
  }
  v11 = v35;
  if ( !v35 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler,2: Volume properties invalid: %lX", v20);
    VdsLogError(0xC2000010, 0, 0, v10, 0x20A0003u, 0);
    goto LABEL_5;
  }
  v27 = v35;
  v12 = OpenDevice(v35, 3221225472LL, &FileHandle);
  v13 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v14 = (unsigned __int16)v12 | 0x80070000;
    else
      v14 = v12;
    v20 = v14;
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler,3: Failed to open handle to the volume: %lX", v14);
    VdsLogError(0xC2000008, 0, 0, v13, 0x20A0004u, v11, 0);
    goto LABEL_8;
  }
  v15 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
  v16 = v15;
  if ( v15 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler: NtQueryVolumeInformationFile (2) failed: %ld", v15);
    if ( v16 == -1073741801 )
      v17 = -2147024882;
    else
      v17 = v16 | 0x10000000;
    v20 = v17;
  }
  else
  {
    InBuffer = (unsigned __int64)v34 / HIDWORD(v37);
    if ( DeviceIoControl(FileHandle, 0x900F0u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
    {
      if ( v20 == 1 )
        CVdsService::SendFileSystemNotification(0xCBu, &v32, 0x64u);
      *(_DWORD *)(v3 + 104) = 0;
      goto LABEL_34;
    }
    LastError = GetLastError();
    if ( !LastError )
    {
      VdsTraceEx(94, 0, "CVdsVolume::PostExtendVolumeHandler, 101: DeviceIoControl (FSCTL_EXTEND_VOLUME) failed.");
      *(_DWORD *)(v3 + 104) = -2147212186;
      goto LABEL_34;
    }
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    else
      v17 = LastError;
    VdsTraceEx(
      94,
      0,
      "CVdsVolume::PostExtendVolumeHandler, 100: DeviceIoControl (FSCTL_EXTEND_VOLUME) failed: %lX",
      LastError);
  }
  *(_DWORD *)(v3 + 104) = v17;
LABEL_34:
  SetEvent(*(HANDLE *)(v3 + 96));
LABEL_35:
  v6 = v21;
  if ( v21 )
  {
    (*(void (__fastcall **)(CVdsServiceModule *))(*(_QWORD *)v21 + 16LL))(v21);
    goto LABEL_37;
  }
LABEL_38:
  CVdsServiceModule::ResumeAcceptingStop(v6);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v26);
  CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v27);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&FileHandle);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v24);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v30);
  return 0;
}

```

## disassembly

```asm
0x140024720  push    rbp
0x140024722  push    rbx
0x140024723  push    rsi
0x140024724  push    rdi
0x140024725  push    r14
0x140024727  push    r15
0x140024729  lea     rbp, [rsp-28h]
0x14002472e  sub     rsp, 128h
0x140024735  mov     rax, cs:__security_cookie
0x14002473c  xor     rax, rsp
0x14002473f  mov     [rbp+50h+var_38], rax
0x140024743  mov     rbx, rcx
0x140024746  lea     r8, aCvdsvolumePost; "CVdsVolume::PostExtendVolumeHandler()"
0x14002474d  mov     r15d, 5Eh ; '^'
0x140024753  mov     edx, r15d
0x140024756  lea     rcx, [rbp+50h+var_B8]
0x14002475a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140024760  nop
0x140024761  xor     r14d, r14d
0x140024764  mov     [rsp+150h+var_108], r14
0x140024769  mov     [rsp+150h+InBuffer], r14
0x14002476e  mov     [rsp+150h+var_110], 80004005h
0x140024776  mov     [rsp+150h+BytesReturned], r14d
0x14002477b  xorps   xmm0, xmm0
0x14002477e  xor     eax, eax
0x140024780  movups  xmmword ptr [rbp+50h+var_88.Data1], xmm0
0x140024784  movups  [rbp+50h+var_78], xmm0
0x140024788  movups  [rbp+50h+var_68], xmm0
0x14002478c  mov     [rbp+50h+var_58], rax
0x140024790  mov     [rsp+150h+var_F0], r14
0x140024795  mov     [rbp+50h+var_D0], r14
0x140024799  mov     [rsp+150h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400247a2  mov     [rsp+150h+var_D8], r14
0x1400247a7  movups  [rbp+50h+var_A8], xmm0
0x1400247ab  movups  [rbp+50h+var_98], xmm0
0x1400247af  xorps   xmm1, xmm1
0x1400247b2  movups  [rbp+50h+FsInformation], xmm1
0x1400247b6  mov     [rbp+50h+var_40], rax
0x1400247ba  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400247be  mov     [rsp+150h+var_E0], r14
0x1400247c3  movups  xmmword ptr [rbp+50h+var_88.Data1], xmm0
0x1400247c7  movups  [rbp+50h+var_78], xmm0
0x1400247cb  movups  [rbp+50h+var_68], xmm0
0x1400247cf  mov     [rbp+50h+var_58], rax
0x1400247d3  mov     [rsp+150h+var_E0], rbx
0x1400247d8  mov     rdx, [rbx]
0x1400247db  lea     rcx, [rsp+150h+var_F0]
0x1400247e0  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x1400247e5  mov     rsi, [rbx+8]
0x1400247e9  mov     [rbp+50h+var_D0], rsi
0x1400247ed  mov     rdi, [rsp+150h+var_F0]
0x1400247f2  mov     rcx, [rdi+40h]
0x1400247f6  mov     rax, [rcx]
0x1400247f9  lea     r8, [rsp+150h+var_108]
0x1400247fe  lea     rdx, IID_IVdsAsync
0x140024805  mov     rax, [rax]
0x140024808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002480d  mov     ebx, eax
0x14002480f  test    eax, eax
0x140024811  jns     short loc_14002483A
0x140024813  mov     r9d, eax
0x140024816  lea     r8, aCvdsvolumePost_0; "CVdsVolume::PostExtendVolumeHandler: pA"...
0x14002481d  xor     edx, edx
0x14002481f  mov     ecx, r15d
0x140024822  call    cs:__imp_VdsTraceEx
0x140024828  mov     [rdi+68h], ebx
0x14002482b  mov     rcx, [rdi+60h]; hEvent
0x14002482f  call    cs:__imp_SetEvent
0x140024835  jmp     loc_140024AFE
0x14002483a  mov     rcx, [rsp+150h+var_108]
0x14002483f  mov     rax, [rcx]
0x140024842  lea     r8, [rbp+50h+var_A8]
0x140024846  lea     rdx, [rsp+150h+var_110]
0x14002484b  mov     rax, [rax+20h]
0x14002484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024854  mov     ebx, eax
0x140024856  test    eax, eax
0x140024858  jns     short loc_14002489A
0x14002485a  mov     r9d, eax
0x14002485d  lea     r8, aCvdsvolumePost_5; "CVdsVolume::PostExtendVolumeHandler: pA"...
0x140024864  xor     edx, edx
0x140024866  mov     ecx, r15d
0x140024869  call    cs:__imp_VdsTraceEx
0x14002486f  mov     qword ptr [rsp+150h+nOutBufferSize], r14; unsigned __int16 *
0x140024874  mov     [rsp+150h+FsInformationClass], 20A0001h; unsigned int
0x14002487c  mov     r9d, ebx; unsigned int
0x14002487f  mov     ecx, 0C2000009h; unsigned int
0x140024884  xor     r8d, r8d; void *
0x140024887  xor     edx, edx; unsigned int
0x140024889  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14002488e  mov     dword ptr [rdi+68h], 80004005h
0x140024895  jmp     loc_140024ADE
0x14002489a  mov     r9d, [rsp+150h+var_110]
0x14002489f  test    r9d, r9d
0x1400248a2  jns     short loc_1400248C2
0x1400248a4  lea     r8, aCvdsvolumePost_3; "CVdsVolume::PostExtendVolumeHandler: pA"...
0x1400248ab  xor     edx, edx
0x1400248ad  mov     ecx, r15d
0x1400248b0  call    cs:__imp_VdsTraceEx
0x1400248b6  mov     eax, [rsp+150h+var_110]
0x1400248ba  mov     [rdi+68h], eax
0x1400248bd  jmp     loc_140024ADE
0x1400248c2  mov     rax, [rsi]
0x1400248c5  lea     rdx, [rbp+50h+var_88]
0x1400248c9  mov     rcx, rsi
0x1400248cc  mov     rax, [rax+18h]
0x1400248d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400248d5  mov     esi, eax
0x1400248d7  test    eax, eax
0x1400248d9  jns     short loc_140024927
0x1400248db  mov     qword ptr [rsp+150h+nOutBufferSize], r14; unsigned __int16 *
0x1400248e0  mov     [rsp+150h+FsInformationClass], 20A0002h; unsigned int
0x1400248e8  mov     r9d, eax; unsigned int
0x1400248eb  xor     r8d, r8d; void *
0x1400248ee  xor     edx, edx; unsigned int
0x1400248f0  mov     ecx, 0C2000009h; unsigned int
0x1400248f5  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400248fa  mov     dword ptr [rdi+68h], 80004005h
0x140024901  mov     rcx, [rdi+60h]; hEvent
0x140024905  call    cs:__imp_SetEvent
0x14002490b  mov     r9d, [rsp+150h+var_110]
0x140024910  lea     r8, aCvdsvolumePost_4; "CVdsVolume::PostExtendVolumeHandler,1: "...
0x140024917  xor     edx, edx
0x140024919  mov     ecx, r15d
0x14002491c  call    cs:__imp_VdsTraceEx
0x140024922  jmp     loc_140024AE8
0x140024927  mov     rbx, [rbp+50h+var_58]
0x14002492b  test    rbx, rbx
0x14002492e  jnz     short loc_140024961
0x140024930  mov     r9d, [rsp+150h+var_110]
0x140024935  lea     r8, aCvdsvolumePost_8; "CVdsVolume::PostExtendVolumeHandler,2: "...
0x14002493c  xor     edx, edx
0x14002493e  mov     ecx, r15d
0x140024941  call    cs:__imp_VdsTraceEx
0x140024947  mov     qword ptr [rsp+150h+nOutBufferSize], r14
0x14002494c  mov     [rsp+150h+FsInformationClass], 20A0003h
0x140024954  mov     r9d, esi
0x140024957  mov     ecx, 0C2000010h
0x14002495c  jmp     loc_140024884
0x140024961  mov     [rsp+150h+var_D8], rbx
0x140024966  lea     r8, [rsp+150h+FileHandle]
0x14002496b  mov     edx, 0C0000000h
0x140024970  mov     rcx, rbx
0x140024973  call    cs:__imp_OpenDevice
0x140024979  mov     esi, eax
0x14002497b  test    eax, eax
0x14002497d  jz      short loc_1400249D3
0x14002497f  test    eax, eax
0x140024981  jg      short loc_140024988
0x140024983  mov     r9d, eax
0x140024986  jmp     short loc_140024993
0x140024988  movzx   r9d, si
0x14002498c  or      r9d, 80070000h
0x140024993  mov     [rsp+150h+var_110], r9d
0x140024998  lea     r8, aCvdsvolumePost_7; "CVdsVolume::PostExtendVolumeHandler,3: "...
0x14002499f  xor     edx, edx
0x1400249a1  mov     ecx, r15d
0x1400249a4  call    cs:__imp_VdsTraceEx
0x1400249aa  mov     [rsp+150h+lpBytesReturned], r14
0x1400249af  mov     qword ptr [rsp+150h+nOutBufferSize], rbx; unsigned __int16 *
0x1400249b4  mov     [rsp+150h+FsInformationClass], 20A0004h; unsigned int
0x1400249bc  mov     r9d, esi; unsigned int
0x1400249bf  xor     r8d, r8d; void *
0x1400249c2  xor     edx, edx; unsigned int
0x1400249c4  mov     ecx, 0C2000008h; unsigned int
0x1400249c9  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400249ce  jmp     loc_1400248B6
0x1400249d3  mov     [rsp+150h+FsInformationClass], 3; FsInformationClass
0x1400249db  mov     r9d, 18h; Length
0x1400249e1  lea     r8, [rbp+50h+FsInformation]; FsInformation
0x1400249e5  lea     rdx, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400249e9  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400249ee  call    cs:__imp_NtQueryVolumeInformationFile
0x1400249f4  mov     ebx, eax
0x1400249f6  xor     edx, edx
0x1400249f8  test    eax, eax
0x1400249fa  jz      short loc_140024A2E
0x1400249fc  mov     r9d, eax
0x1400249ff  lea     r8, aCvdsvolumePost_1; "CVdsVolume::PostExtendVolumeHandler: Nt"...
0x140024a06  mov     ecx, r15d
0x140024a09  call    cs:__imp_VdsTraceEx
0x140024a0f  cmp     ebx, 0C0000017h
0x140024a15  jz      short loc_140024A1D
0x140024a17  bts     ebx, 1Ch
0x140024a1b  jmp     short loc_140024A22
0x140024a1d  mov     ebx, 8007000Eh
0x140024a22  mov     [rsp+150h+var_110], ebx
0x140024a26  mov     [rdi+68h], ebx
0x140024a29  jmp     loc_140024ADE
0x140024a2e  mov     ecx, dword ptr [rbp+50h+var_40+4]
0x140024a31  mov     rax, qword ptr [rbp+50h+var_68]
0x140024a35  div     rcx
0x140024a38  mov     [rsp+150h+InBuffer], rax
0x140024a3d  mov     [rsp+150h+lpOverlapped], r14; lpOverlapped
0x140024a42  lea     rax, [rsp+150h+BytesReturned]
0x140024a47  mov     [rsp+150h+lpBytesReturned], rax; lpBytesReturned
0x140024a4c  mov     [rsp+150h+nOutBufferSize], r14d; nOutBufferSize
0x140024a51  mov     qword ptr [rsp+150h+FsInformationClass], r14; lpOutBuffer
0x140024a56  mov     r9d, 8; nInBufferSize
0x140024a5c  lea     r8, [rsp+150h+InBuffer]; lpInBuffer
0x140024a61  mov     edx, 900F0h; dwIoControlCode
0x140024a66  mov     rcx, [rsp+150h+FileHandle]; hDevice
0x140024a6b  call    cs:__imp_DeviceIoControl
0x140024a71  test    eax, eax
0x140024a73  jnz     short loc_140024AC0
0x140024a75  call    cs:__imp_GetLastError
0x140024a7b  test    eax, eax
0x140024a7d  jz      short loc_140024AA5
0x140024a7f  jg      short loc_140024A85
0x140024a81  mov     ebx, eax
0x140024a83  jmp     short loc_140024A8E
0x140024a85  movzx   ebx, ax
0x140024a88  or      ebx, 80070000h
0x140024a8e  mov     r9d, eax
0x140024a91  lea     r8, aCvdsvolumePost_6; "CVdsVolume::PostExtendVolumeHandler, 10"...
0x140024a98  xor     edx, edx
0x140024a9a  mov     ecx, r15d
0x140024a9d  call    cs:__imp_VdsTraceEx
0x140024aa3  jmp     short loc_140024A26
0x140024aa5  lea     r8, aCvdsvolumePost_2; "CVdsVolume::PostExtendVolumeHandler, 10"...
0x140024aac  xor     edx, edx
0x140024aae  mov     ecx, r15d
0x140024ab1  call    cs:__imp_VdsTraceEx
0x140024ab7  mov     dword ptr [rdi+68h], 80042466h
0x140024abe  jmp     short loc_140024ADE
0x140024ac0  cmp     [rsp+150h+var_110], 1
0x140024ac5  jnz     short loc_140024ADA
0x140024ac7  mov     r8d, 64h ; 'd'; unsigned int
0x140024acd  lea     rdx, [rbp+50h+var_88]; struct _GUID *
0x140024ad1  lea     ecx, [r8+67h]; unsigned int
0x140024ad5  call    ?SendFileSystemNotification@CVdsService@@SAXKAEAU_GUID@@K@Z; CVdsService::SendFileSystemNotification(ulong,_GUID &,ulong)
0x140024ada  mov     [rdi+68h], r14d
0x140024ade  mov     rcx, [rdi+60h]; hEvent
0x140024ae2  call    cs:__imp_SetEvent
0x140024ae8  mov     rcx, [rsp+150h+var_108]
0x140024aed  test    rcx, rcx
0x140024af0  jz      short loc_140024B03
0x140024af2  mov     rax, [rcx]
0x140024af5  mov     rax, [rax+10h]
0x140024af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024afe  mov     [rsp+150h+var_108], r14
0x140024b03  call    ?ResumeAcceptingStop@CVdsServiceModule@@QEAAXXZ; CVdsServiceModule::ResumeAcceptingStop(void)
0x140024b08  nop
0x140024b09  lea     rcx, [rsp+150h+var_E0]
0x140024b0e  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140024b13  nop
0x140024b14  lea     rcx, [rsp+150h+var_D8]
0x140024b19  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x140024b1e  nop
0x140024b1f  lea     rcx, [rsp+150h+FileHandle]
0x140024b24  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140024b29  nop
0x140024b2a  lea     rcx, [rbp+50h+var_D0]
0x140024b2e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140024b33  nop
0x140024b34  lea     rcx, [rsp+150h+var_F0]
0x140024b39  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140024b3e  nop
0x140024b3f  lea     rcx, [rbp+50h+var_B8]
0x140024b43  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140024b49  xor     eax, eax
0x140024b4b  mov     rcx, [rbp+50h+var_38]
0x140024b4f  xor     rcx, rsp; StackCookie
0x140024b52  call    __security_check_cookie
0x140024b57  add     rsp, 128h
0x140024b5e  pop     r15
0x140024b60  pop     r14
0x140024b62  pop     rdi
0x140024b63  pop     rsi
0x140024b64  pop     rbx
0x140024b65  pop     rbp
0x140024b66  retn
```
