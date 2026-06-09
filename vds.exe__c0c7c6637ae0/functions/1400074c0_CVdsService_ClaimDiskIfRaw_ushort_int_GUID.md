# CVdsService::ClaimDiskIfRaw(ushort *,int *,_GUID &)

- ea: `0x1400074c0`
- end: `0x140007894`
- name: `?ClaimDiskIfRaw@CVdsService@@SAKPEAGPEAHAEAU_GUID@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(unsigned __int16 *lpFileName, int *, struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1400070c0`
- `0x14004fd50`

## callees

- `0x1400074c0`
- `0x14000d0f0`
- `0x14000f930`
- `0x140013298`
- `0x14002e123`
- `0x140037a0c`
- `0x140038618`
- `0x14003ca88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400075e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400075e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000762d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000762d`
- `vdsutil!OpenDevice` at `0x140007534`
- `vdsutil!OpenDevice` at `0x140007534`
- `vdsutil!GetDeviceAndMediaType` at `0x140007614`
- `vdsutil!GetDeviceAndMediaType` at `0x140007614`
- `vdsutil!GetDiskLayout` at `0x140007698`
- `vdsutil!GetDiskLayout` at `0x140007698`
- `vdsutil!GetPartitionInformation` at `0x14000771a`
- `vdsutil!GetPartitionInformation` at `0x14000771a`
- `vdsutil!VdsHeapFree` at `0x1400075cf`
- `vdsutil!VdsHeapFree` at `0x1400075cf`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140007520`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140007520`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400075b0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400077d7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007871`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400075b0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400077d7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007871`
- `vdsutil!VdsTraceW` at `0x140007564`
- `vdsutil!VdsTraceW` at `0x140007580`
- `vdsutil!VdsTraceW` at `0x14000766d`
- `vdsutil!VdsTraceW` at `0x140007777`
- `vdsutil!VdsTraceW` at `0x140007865`
- `vdsutil!VdsTraceW` at `0x140007564`
- `vdsutil!VdsTraceW` at `0x140007580`
- `vdsutil!VdsTraceW` at `0x14000766d`
- `vdsutil!VdsTraceW` at `0x140007777`
- `vdsutil!VdsTraceW` at `0x140007865`

## string_xrefs

- `0x14000750f`: `CVdsService::ClaimDiskIfRaw()`
- `0x140007558`: `CVdsService::ClaimDiskIfRaw, 1, name=%s, error=%ld`
- `0x140007577`: `CVdsService::ClaimDiskIfRaw, 2, error=%ld`
- `0x140007664`: `CVdsService::ClaimDiskIfRaw, 3, name=%s, error=%ld`
- `0x14000776e`: `CVdsService::ClaimDiskIfRaw, 4, name=%s, error=%ld`
- `0x14000785c`: `CVdsService::ClaimDiskIfRaw, 5, name=%s, error=%ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::ClaimDiskIfRaw(unsigned __int16 *lpFileName, int *a2, struct _GUID *a3)
{
  unsigned int v6; // edi
  const wchar_t *v7; // r8
  _DWORD *v8; // rbx
  HANDLE ProcessHeap; // rax
  int v11; // r15d
  unsigned int DeviceAndMediaType; // eax
  unsigned int DiskLayout; // eax
  struct CVdsRawDiskLun *RawDisk; // r15
  int v15; // r14d
  int v16; // eax
  unsigned int PartitionInformation; // edi
  int v18; // r8d
  unsigned int v19; // edi
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v24[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]

  hObject = (HANDLE)-1LL;
  v22 = 0;
  v23 = 0;
  memset_0(v25, 0, 0x90u);
  v21 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsService::ClaimDiskIfRaw()");
  *a2 = 0;
  v6 = OpenDevice(lpFileName, 0, &hObject);
  if ( v6 )
  {
    v7 = lpFileName;
    if ( !lpFileName )
      v7 = L"UNKNOWN";
    VdsTraceW(1, L"CVdsService::ClaimDiskIfRaw, 1, name=%s, error=%ld", v7, v6);
    if ( v6 != 2 && v6 != 55 )
    {
      VdsTraceW(0, L"CVdsService::ClaimDiskIfRaw, 2, error=%ld", v6);
      VdsLogError(0xC2000008, 0, 0, v6, 0x2000017u, lpFileName, 0);
    }
    goto LABEL_7;
  }
  v11 = 0;
  do
  {
    DeviceAndMediaType = GetDeviceAndMediaType(lpFileName, hObject, &v22, &v23);
    v6 = DeviceAndMediaType;
    if ( DeviceAndMediaType != 21 && DeviceAndMediaType != 170 )
      break;
    Sleep(0x32u);
    ++v11;
    if ( v6 != 21 && v6 != 170 )
      break;
  }
  while ( v11 < 200 );
  if ( v6 )
  {
    if ( !lpFileName )
      lpFileName = L"UNKNOWN";
    VdsTraceW(0, L"CVdsService::ClaimDiskIfRaw, 3, name=%s, error=%ld", lpFileName, v6);
    goto LABEL_7;
  }
  if ( v22 != 7 || v23 != 12 )
  {
LABEL_52:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v21);
    CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hObject);
    return 0;
  }
  DiskLayout = GetDiskLayout(hObject, &v21);
  v6 = DiskLayout;
  if ( DiskLayout )
  {
    if ( DiskLayout != 55 )
      goto LABEL_30;
LABEL_7:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
    v8 = v21;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v8);
      v21 = 0;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    return v6;
  }
  if ( *v21 == 1 || !*v21 && v21[2] )
    goto LABEL_7;
LABEL_30:
  RawDisk = CVdsService::FindRawDisk(lpFileName);
  if ( RawDisk )
  {
    v15 = 0;
    if ( v6 == 21 || (v16 = 1, v6 == 170) )
      v16 = 2;
    if ( *((_DWORD *)RawDisk + 34) != v16 )
    {
      *((_DWORD *)RawDisk + 34) = v16;
      v15 = 1;
    }
    PartitionInformation = GetPartitionInformation(hObject, v25);
    if ( PartitionInformation )
    {
      if ( PartitionInformation == 1167
        || PartitionInformation == 55
        || PartitionInformation == 21
        || PartitionInformation == 170 )
      {
        if ( *((_DWORD *)RawDisk + 34) != 2 )
        {
          *((_DWORD *)RawDisk + 34) = 2;
          v15 = 1;
        }
      }
      else
      {
        if ( !lpFileName )
          lpFileName = L"UNKNOWN";
        VdsTraceW(0, L"CVdsService::ClaimDiskIfRaw, 4, name=%s, error=%ld", lpFileName, PartitionInformation);
      }
      VdsLogError(0xC2000001, 0, 0, PartitionInformation, 0x2000018u, 0);
    }
    else if ( *((_QWORD *)RawDisk + 20) != v26 )
    {
      *((_QWORD *)RawDisk + 20) = v26;
      goto LABEL_50;
    }
    if ( !v15 )
    {
LABEL_51:
      *a2 = 1;
      goto LABEL_52;
    }
LABEL_50:
    CVdsService::SendDiskNotification(0xAu, (struct _GUID *)((char *)RawDisk + 120));
    goto LABEL_51;
  }
  if ( v6 == 21 || (v18 = 0, v6 == 170) )
    v18 = 1;
  v19 = CVdsService::ClaimRawDisk(lpFileName, a3, v18, 0);
  if ( !v19 )
  {
    *a2 = 1;
    CVdsService::SendDiskNotification(8u, a3);
    goto LABEL_52;
  }
  if ( !lpFileName )
    lpFileName = L"UNKNOWN";
  VdsTraceW(0, L"CVdsService::ClaimDiskIfRaw, 5, name=%s, error=%ld", lpFileName, v19);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v21);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hObject);
  return v19;
}

```

## disassembly

```asm
0x1400074c0  push    rbp
0x1400074c2  push    rbx
0x1400074c3  push    rsi
0x1400074c4  push    rdi
0x1400074c5  push    r12
0x1400074c7  push    r13
0x1400074c9  push    r14
0x1400074cb  push    r15
0x1400074cd  lea     rbp, [rsp-8]
0x1400074d2  sub     rsp, 108h
0x1400074d9  mov     r14, r8
0x1400074dc  mov     rsi, rdx
0x1400074df  mov     rbx, rcx
0x1400074e2  mov     [rsp+140h+hObject], 0FFFFFFFFFFFFFFFFh
0x1400074eb  xor     r13d, r13d
0x1400074ee  mov     [rsp+140h+var_F0], r13d
0x1400074f3  mov     [rsp+140h+var_EC], r13d
0x1400074f8  xor     edx, edx; Val
0x1400074fa  mov     r8d, 90h; Size
0x140007500  lea     rcx, [rsp+140h+var_D0]; void *
0x140007505  call    memset_0
0x14000750a  mov     [rsp+140h+var_F8], r13
0x14000750f  lea     r8, aCvdsserviceCla_2; "CVdsService::ClaimDiskIfRaw()"
0x140007516  mov     edx, 5Eh ; '^'
0x14000751b  lea     rcx, [rsp+140h+var_E8]
0x140007520  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140007526  nop
0x140007527  mov     [rsi], r13d
0x14000752a  lea     r8, [rsp+140h+hObject]
0x14000752f  xor     edx, edx
0x140007531  mov     rcx, rbx
0x140007534  call    cs:__imp_OpenDevice
0x14000753a  mov     edi, eax
0x14000753c  test    eax, eax
0x14000753e  jz      loc_1400075FF
0x140007544  lea     rax, aUnknown_0; "UNKNOWN"
0x14000754b  mov     r8, rbx
0x14000754e  test    rbx, rbx
0x140007551  cmovz   r8, rax
0x140007555  mov     r9d, edi
0x140007558  lea     rdx, aCvdsserviceCla_14; "CVdsService::ClaimDiskIfRaw, 1, name=%s"...
0x14000755f  mov     ecx, 1
0x140007564  call    cs:__imp_VdsTraceW
0x14000756a  cmp     edi, 2
0x14000756d  jz      short loc_1400075AB
0x14000756f  cmp     edi, 37h ; '7'
0x140007572  jz      short loc_1400075AB
0x140007574  mov     r8d, edi
0x140007577  lea     rdx, aCvdsserviceCla_12; "CVdsService::ClaimDiskIfRaw, 2, error=%"...
0x14000757e  xor     ecx, ecx
0x140007580  call    cs:__imp_VdsTraceW
0x140007586  mov     [rsp+140h+var_110], r13
0x14000758b  mov     [rsp+140h+var_118], rbx; unsigned __int16 *
0x140007590  mov     [rsp+140h+var_120], 2000017h; unsigned int
0x140007598  mov     r9d, edi; unsigned int
0x14000759b  xor     r8d, r8d; void *
0x14000759e  xor     edx, edx; unsigned int
0x1400075a0  mov     ecx, 0C2000008h; unsigned int
0x1400075a5  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400075aa  nop
0x1400075ab  lea     rcx, [rsp+140h+var_E8]
0x1400075b0  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400075b6  nop
0x1400075b7  mov     rbx, [rsp+140h+var_F8]
0x1400075bc  test    rbx, rbx
0x1400075bf  jz      short loc_1400075DA
0x1400075c1  call    cs:__imp_GetProcessHeap
0x1400075c7  mov     r8, rbx
0x1400075ca  xor     edx, edx
0x1400075cc  mov     rcx, rax
0x1400075cf  call    cs:__imp_VdsHeapFree
0x1400075d5  mov     [rsp+140h+var_F8], r13
0x1400075da  mov     rcx, [rsp+140h+hObject]; hObject
0x1400075df  lea     rax, [rcx-1]
0x1400075e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400075e7  ja      short loc_1400075F8
0x1400075e9  call    cs:__imp_CloseHandle
0x1400075ef  mov     [rsp+140h+hObject], 0FFFFFFFFFFFFFFFFh
0x1400075f8  mov     eax, edi
0x1400075fa  jmp     loc_1400077F5
0x1400075ff  mov     r15d, r13d
0x140007602  lea     r9, [rsp+140h+var_EC]
0x140007607  lea     r8, [rsp+140h+var_F0]
0x14000760c  mov     rdx, [rsp+140h+hObject]
0x140007611  mov     rcx, rbx
0x140007614  call    cs:__imp_GetDeviceAndMediaType
0x14000761a  mov     edi, eax
0x14000761c  cmp     eax, 15h
0x14000761f  jz      short loc_140007628
0x140007621  cmp     eax, 0AAh
0x140007626  jnz     short loc_14000764C
0x140007628  mov     ecx, 32h ; '2'; dwMilliseconds
0x14000762d  call    cs:__imp_Sleep
0x140007633  inc     r15d
0x140007636  cmp     edi, 15h
0x140007639  jz      short loc_140007643
0x14000763b  cmp     edi, 0AAh
0x140007641  jnz     short loc_14000764C
0x140007643  cmp     r15d, 0C8h
0x14000764a  jl      short loc_140007602
0x14000764c  test    edi, edi
0x14000764e  jz      short loc_140007678
0x140007650  lea     rax, aUnknown_0; "UNKNOWN"
0x140007657  test    rbx, rbx
0x14000765a  cmovz   rbx, rax
0x14000765e  mov     r9d, edi
0x140007661  mov     r8, rbx
0x140007664  lea     rdx, aCvdsserviceCla_16; "CVdsService::ClaimDiskIfRaw, 3, name=%s"...
0x14000766b  xor     ecx, ecx
0x14000766d  call    cs:__imp_VdsTraceW
0x140007673  jmp     loc_1400075AB
0x140007678  cmp     [rsp+140h+var_F0], 7
0x14000767d  jnz     loc_1400077D2
0x140007683  cmp     [rsp+140h+var_EC], 0Ch
0x140007688  jnz     loc_1400077D2
0x14000768e  lea     rdx, [rsp+140h+var_F8]
0x140007693  mov     rcx, [rsp+140h+hObject]
0x140007698  call    cs:__imp_GetDiskLayout
0x14000769e  mov     edi, eax
0x1400076a0  test    eax, eax
0x1400076a2  jz      short loc_1400076AF
0x1400076a4  cmp     eax, 37h ; '7'
0x1400076a7  jz      loc_1400075AB
0x1400076ad  jmp     short loc_1400076CC
0x1400076af  mov     rax, [rsp+140h+var_F8]
0x1400076b4  mov     ecx, [rax]
0x1400076b6  cmp     ecx, 1
0x1400076b9  jz      loc_1400075AB
0x1400076bf  test    ecx, ecx
0x1400076c1  jnz     short loc_1400076CC
0x1400076c3  cmp     [rax+8], ecx
0x1400076c6  jnz     loc_1400075AB
0x1400076cc  mov     rcx, rbx; String1
0x1400076cf  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@PEAG@Z; CVdsService::FindRawDisk(ushort *)
0x1400076d4  mov     r15, rax
0x1400076d7  test    rax, rax
0x1400076da  jz      loc_140007809
0x1400076e0  mov     r14d, r13d
0x1400076e3  cmp     edi, 15h
0x1400076e6  jz      short loc_1400076F5
0x1400076e8  cmp     edi, 0AAh
0x1400076ee  mov     eax, 1
0x1400076f3  jnz     short loc_1400076FA
0x1400076f5  mov     eax, 2
0x1400076fa  cmp     [r15+88h], eax
0x140007701  jz      short loc_140007710
0x140007703  mov     [r15+88h], eax
0x14000770a  mov     r14d, 1
0x140007710  lea     rdx, [rsp+140h+var_D0]
0x140007715  mov     rcx, [rsp+140h+hObject]
0x14000771a  call    cs:__imp_GetPartitionInformation
0x140007720  mov     edi, eax
0x140007722  test    eax, eax
0x140007724  jnz     short loc_140007740
0x140007726  mov     rax, [rbp+40h+var_C0]
0x14000772a  cmp     [r15+0A0h], rax
0x140007731  jz      loc_1400077B9
0x140007737  mov     [r15+0A0h], rax
0x14000773e  jmp     short loc_1400077BE
0x140007740  cmp     edi, 48Fh
0x140007746  jz      short loc_14000777F
0x140007748  cmp     edi, 37h ; '7'
0x14000774b  jz      short loc_14000777F
0x14000774d  cmp     edi, 15h
0x140007750  jz      short loc_14000777F
0x140007752  cmp     edi, 0AAh
0x140007758  jz      short loc_14000777F
0x14000775a  lea     rax, aUnknown_0; "UNKNOWN"
0x140007761  test    rbx, rbx
0x140007764  cmovz   rbx, rax
0x140007768  mov     r9d, edi
0x14000776b  mov     r8, rbx
0x14000776e  lea     rdx, aCvdsserviceCla; "CVdsService::ClaimDiskIfRaw, 4, name=%s"...
0x140007775  xor     ecx, ecx
0x140007777  call    cs:__imp_VdsTraceW
0x14000777d  jmp     short loc_14000779A
0x14000777f  cmp     dword ptr [r15+88h], 2
0x140007787  jz      short loc_14000779A
0x140007789  mov     dword ptr [r15+88h], 2
0x140007794  mov     r14d, 1
0x14000779a  mov     [rsp+140h+var_118], r13; unsigned __int16 *
0x14000779f  mov     [rsp+140h+var_120], 2000018h; unsigned int
0x1400077a7  mov     r9d, edi; unsigned int
0x1400077aa  xor     r8d, r8d; void *
0x1400077ad  xor     edx, edx; unsigned int
0x1400077af  mov     ecx, 0C2000001h; unsigned int
0x1400077b4  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400077b9  test    r14d, r14d
0x1400077bc  jz      short loc_1400077CC
0x1400077be  lea     rdx, [r15+78h]; struct _GUID *
0x1400077c2  mov     ecx, 0Ah; unsigned int
0x1400077c7  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x1400077cc  mov     dword ptr [rsi], 1
0x1400077d2  lea     rcx, [rsp+140h+var_E8]
0x1400077d7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400077dd  nop
0x1400077de  lea     rcx, [rsp+140h+var_F8]
0x1400077e3  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x1400077e8  nop
0x1400077e9  lea     rcx, [rsp+140h+hObject]
0x1400077ee  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x1400077f3  xor     eax, eax
0x1400077f5  add     rsp, 108h
0x1400077fc  pop     r15
0x1400077fe  pop     r14
0x140007800  pop     r13
0x140007802  pop     r12
0x140007804  pop     rdi
0x140007805  pop     rsi
0x140007806  pop     rbx
0x140007807  pop     rbp
0x140007808  retn
0x140007809  cmp     edi, 15h
0x14000780c  jz      short loc_140007819
0x14000780e  cmp     edi, 0AAh
0x140007814  mov     r8d, r13d
0x140007817  jnz     short loc_14000781F
0x140007819  mov     r8d, 1; int
0x14000781f  xor     r9d, r9d; int
0x140007822  mov     rdx, r14; struct _GUID *
0x140007825  mov     rcx, rbx; lpFileName
0x140007828  call    ?ClaimRawDisk@CVdsService@@SAKPEAGAEAU_GUID@@HH@Z; CVdsService::ClaimRawDisk(ushort *,_GUID &,int,int)
0x14000782d  mov     edi, eax
0x14000782f  test    eax, eax
0x140007831  jnz     short loc_140007848
0x140007833  mov     dword ptr [rsi], 1
0x140007839  mov     rdx, r14; struct _GUID *
0x14000783c  mov     ecx, 8; unsigned int
0x140007841  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x140007846  jmp     short loc_1400077D2
0x140007848  lea     rax, aUnknown_0; "UNKNOWN"
0x14000784f  test    rbx, rbx
0x140007852  cmovz   rbx, rax
0x140007856  mov     r9d, edi
0x140007859  mov     r8, rbx
0x14000785c  lea     rdx, aCvdsserviceCla_13; "CVdsService::ClaimDiskIfRaw, 5, name=%s"...
0x140007863  xor     ecx, ecx
0x140007865  call    cs:__imp_VdsTraceW
0x14000786b  nop
0x14000786c  lea     rcx, [rsp+140h+var_E8]
0x140007871  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007877  nop
0x140007878  lea     rcx, [rsp+140h+var_F8]
0x14000787d  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140007882  nop
0x140007883  lea     rcx, [rsp+140h+hObject]
0x140007888  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14000788d  mov     eax, edi
0x14000788f  jmp     loc_1400077F5
```
