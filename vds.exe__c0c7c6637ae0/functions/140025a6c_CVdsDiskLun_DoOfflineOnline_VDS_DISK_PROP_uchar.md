# CVdsDiskLun::DoOfflineOnline(_VDS_DISK_PROP *,uchar)

- ea: `0x140025a6c`
- end: `0x140025e19`
- name: `?DoOfflineOnline@CVdsDiskLun@@AEAAJPEAU_VDS_DISK_PROP@@E@Z`
- size: `941`
- prototype: `int(CVdsDiskLun *__hidden this, struct _VDS_DISK_PROP *, unsigned __int8)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x140049840`
- `0x140049b00`

## callees

- `0x140025a6c`
- `0x140027cd8`
- `0x140029050`
- `0x140038618`
- `0x14003ca88`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025beb`
- `vdsutil!OpenDevice` at `0x140025b18`
- `vdsutil!OpenDevice` at `0x140025b18`
- `vdsutil!VdsTraceExW` at `0x140025b5a`
- `vdsutil!VdsTraceExW` at `0x140025c76`
- `vdsutil!VdsTraceExW` at `0x140025b5a`
- `vdsutil!VdsTraceExW` at `0x140025c76`
- `vdsutil!GetDeviceNumber` at `0x140025c8f`
- `vdsutil!GetDeviceNumber` at `0x140025c8f`
- `vdsutil!VdsTraceEx` at `0x140025b00`
- `vdsutil!VdsTraceEx` at `0x140025b00`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140025ccc`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140025ccc`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140025ce5`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140025ce5`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140025d12`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140025d12`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140025ded`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140025ded`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140025ad6`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140025ad6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140025bfd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140025bfd`
- `vdsutil!VdsTraceW` at `0x140025ba5`
- `vdsutil!VdsTraceW` at `0x140025d6c`
- `vdsutil!VdsTraceW` at `0x140025e0d`
- `vdsutil!VdsTraceW` at `0x140025ba5`
- `vdsutil!VdsTraceW` at `0x140025d6c`
- `vdsutil!VdsTraceW` at `0x140025e0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsDiskLun::DoOfflineOnline(CVdsDiskLun *this, struct _VDS_DISK_PROP *a2, char a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  LPWSTR v7; // r14
  const wchar_t *v8; // r8
  LPWSTR v9; // r9
  int v10; // eax
  CVdsRawDiskLun *RawDisk; // rax
  LPWSTR pwszDevicePath; // r9
  int DeviceNumber; // eax
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rsi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // [rsp+30h] [rbp-59h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-51h] BYREF
  __int64 v21; // [rsp+40h] [rbp-49h] BYREF
  __int64 v22; // [rsp+48h] [rbp-41h] BYREF
  __int64 v23; // [rsp+50h] [rbp-39h]
  __int128 Buf1; // [rsp+58h] [rbp-31h] BYREF
  __int128 Buf2; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v26[16]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v27[16]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+17h] BYREF
  int v29; // [rsp+A8h] [rbp+1Fh]

  v19 = -2147467259;
  hObject = 0;
  v21 = 0;
  v22 = 0;
  v28 = 0;
  v29 = 0;
  Buf1 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v26, 0x5Eu, "CVdsDiskLun::Offline()");
  v23 = 0;
  v28 = 0;
  v29 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    VdsTraceEx(94, 0, "CVdsDiskLun::DoOfflineOnline, 1");
    goto LABEL_21;
  }
  v6 = OpenDevice(a2->pwszDevicePath, 3221225472LL, &hObject);
  v5 = v6;
  v7 = L"UNKNOWN";
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    hObject = 0;
    v8 = L"CVdsDiskLun::DoOfflineOnline, 2 Name=%s, hr=%lX";
  }
  else
  {
    RawDisk = CVdsService::FindRawDisk(a2->pwszDevicePath);
    if ( RawDisk )
    {
      if ( a3 )
        v10 = CVdsRawDiskLun::Offline(RawDisk, hObject);
      else
        v10 = CVdsRawDiskLun::Online(RawDisk, hObject);
      v19 = v10;
      if ( v10 < 0 )
      {
        pwszDevicePath = L"UNKNOWN";
        if ( a2->pwszDevicePath )
          pwszDevicePath = a2->pwszDevicePath;
        VdsTraceExW(94, 0, L"CVdsDiskLun::DoOfflineOnline, 3 Name=%s, hr=%lX", pwszDevicePath, v10);
        v10 = v19;
      }
      v5 = 0;
      goto LABEL_12;
    }
    DeviceNumber = GetDeviceNumber(hObject, &v28);
    v5 = DeviceNumber;
    if ( !DeviceNumber )
    {
      v5 = 1;
      LODWORD(v23) = HIDWORD(v28);
      BYTE4(v23) = a3;
      for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
            ;
            CRtlListIter::Next((CRtlListIter *)&Buf1) )
      {
        Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v27);
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
          break;
        EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
        if ( !EntryPointer )
        {
          v5 = -2147212216;
          VdsTraceW(0, L"CVdsDiskLun::DoOfflineOnline, 5, disk number=%ld, hr=%lX", HIDWORD(v28), 2147755080LL);
          goto LABEL_21;
        }
        if ( v22 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          v22 = 0;
        }
        v16 = (**EntryPointer)(EntryPointer, &IID_IVdsProvider, &v22);
        v5 = v16;
        if ( v16 >= 0 )
        {
          if ( v21 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            v21 = 0;
          }
          v17 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivateOffline, &v21);
          v5 = v17;
          if ( v17 >= 0 )
          {
            v19 = -2147467259;
            v18 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v21 + 24LL))(v21, v23, &v19);
            v5 = v18;
            if ( v18 >= 0 )
            {
              if ( !v18 )
                goto LABEL_11;
            }
            else
            {
              VdsTraceW(0, L"CVdsDiskLun::DoOfflineOnline, 8, disk number=%ld, hr=%lX", HIDWORD(v28), (unsigned int)v18);
            }
          }
          else
          {
            VdsTraceW(0, L"CVdsDiskLun::DoOfflineOnline, 7, disk number=%ld, hr=%lX", HIDWORD(v28), (unsigned int)v17);
          }
        }
        else
        {
          VdsTraceW(0, L"CVdsDiskLun::DoOfflineOnline, 6, disk number=%ld, hr=%lX", HIDWORD(v28), (unsigned int)v16);
        }
      }
      goto LABEL_10;
    }
    if ( DeviceNumber > 0 )
      v5 = (unsigned __int16)DeviceNumber | 0x80070000;
    v8 = L"CVdsDiskLun::DoOfflineOnline, 4 Name=%s, hr=%lX";
  }
  v9 = L"UNKNOWN";
  if ( a2->pwszDevicePath )
    v9 = a2->pwszDevicePath;
  VdsTraceExW(94, 0, v8, v9, v5);
LABEL_10:
  if ( v5 )
    goto LABEL_17;
LABEL_11:
  v10 = v19;
LABEL_12:
  if ( !v10 )
  {
    CVdsService::SendDiskNotification(0xAu, &a2->id);
    v10 = v19;
  }
  if ( !v5 )
  {
    if ( !v10 )
      goto LABEL_21;
    v5 = v10;
  }
LABEL_17:
  if ( v5 == 1 )
  {
    v5 = -2147212283;
    if ( a2->pwszDevicePath )
      v7 = a2->pwszDevicePath;
    VdsTraceW(0, L"CVdsDiskLun::DoOfflineOnline, 9 Name=%s, hr=%lX", v7, 2147755013LL);
  }
LABEL_21:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v26);
  return v5;
}

```

## disassembly

```asm
0x140025a6c  mov     [rsp-8+arg_0], rbx
0x140025a71  mov     [rsp-8+arg_18], rsi
0x140025a76  push    rbp
0x140025a77  push    rdi
0x140025a78  push    r12
0x140025a7a  push    r14
0x140025a7c  push    r15
0x140025a7e  lea     rbp, [rsp-37h]
0x140025a83  sub     rsp, 0C0h
0x140025a8a  mov     rax, cs:__security_cookie
0x140025a91  xor     rax, rsp
0x140025a94  mov     [rbp+57h+var_30], rax
0x140025a98  mov     sil, r8b
0x140025a9b  mov     rdi, rdx
0x140025a9e  mov     [rbp+57h+var_B0], 80004005h
0x140025aa5  xor     r15d, r15d
0x140025aa8  mov     [rbp+57h+hObject], r15
0x140025aac  mov     [rbp+57h+var_A0], r15
0x140025ab0  mov     [rbp+57h+var_98], r15
0x140025ab4  xor     eax, eax
0x140025ab6  mov     [rbp+57h+var_40], rax
0x140025aba  mov     [rbp+57h+var_38], eax
0x140025abd  xorps   xmm0, xmm0
0x140025ac0  movups  [rbp+57h+Buf1], xmm0
0x140025ac4  lea     r8, aCvdsdisklunOff_10; "CVdsDiskLun::Offline()"
0x140025acb  lea     r12d, [r15+5Eh]
0x140025acf  mov     edx, r12d
0x140025ad2  lea     rcx, [rbp+57h+var_60]
0x140025ad6  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140025adc  nop
0x140025add  mov     [rbp+57h+var_90], r15
0x140025ae1  xor     eax, eax
0x140025ae3  mov     [rbp+57h+var_40], rax
0x140025ae7  mov     [rbp+57h+var_38], eax
0x140025aea  test    rdi, rdi
0x140025aed  jnz     short loc_140025B0B
0x140025aef  mov     ebx, 80070057h
0x140025af4  lea     r8, aCvdsdisklunDoo_5; "CVdsDiskLun::DoOfflineOnline, 1"
0x140025afb  xor     edx, edx
0x140025afd  mov     ecx, r12d
0x140025b00  call    cs:__imp_VdsTraceEx
0x140025b06  jmp     loc_140025BAB
0x140025b0b  lea     r8, [rbp+57h+hObject]
0x140025b0f  mov     edx, 0C0000000h
0x140025b14  mov     rcx, [rdi+78h]
0x140025b18  call    cs:__imp_OpenDevice
0x140025b1e  mov     ebx, eax
0x140025b20  lea     r14, aUnknown_0; "UNKNOWN"
0x140025b27  test    eax, eax
0x140025b29  jz      loc_140025C2D
0x140025b2f  jle     short loc_140025B3A
0x140025b31  movzx   ebx, ax
0x140025b34  or      ebx, 80070000h
0x140025b3a  mov     [rbp+57h+hObject], r15
0x140025b3e  lea     r8, aCvdsdisklunDoo_2; "CVdsDiskLun::DoOfflineOnline, 2 Name=%s"...
0x140025b45  mov     r9, r14
0x140025b48  cmp     [rdi+78h], r15
0x140025b4c  mov     [rsp+0E0h+var_C0], ebx
0x140025b50  cmovnz  r9, [rdi+78h]
0x140025b55  xor     edx, edx
0x140025b57  mov     ecx, r12d
0x140025b5a  call    cs:__imp_VdsTraceExW
0x140025b60  test    ebx, ebx
0x140025b62  jnz     short loc_140025B83
0x140025b64  mov     eax, [rbp+57h+var_B0]
0x140025b67  test    eax, eax
0x140025b69  jnz     short loc_140025B79
0x140025b6b  mov     rdx, rdi; struct _GUID *
0x140025b6e  lea     ecx, [rax+0Ah]; unsigned int
0x140025b71  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x140025b76  mov     eax, [rbp+57h+var_B0]
0x140025b79  test    ebx, ebx
0x140025b7b  jnz     short loc_140025B83
0x140025b7d  test    eax, eax
0x140025b7f  jz      short loc_140025BAB
0x140025b81  mov     ebx, eax
0x140025b83  cmp     ebx, 1
0x140025b86  jnz     short loc_140025BAB
0x140025b88  mov     ebx, 80042405h
0x140025b8d  cmp     [rdi+78h], r15
0x140025b91  cmovnz  r14, [rdi+78h]
0x140025b96  mov     r9d, ebx
0x140025b99  mov     r8, r14
0x140025b9c  lea     rdx, aCvdsdisklunDoo_0; "CVdsDiskLun::DoOfflineOnline, 9 Name=%s"...
0x140025ba3  xor     ecx, ecx
0x140025ba5  call    cs:__imp_VdsTraceW
0x140025bab  mov     rcx, [rbp+57h+var_A0]
0x140025baf  test    rcx, rcx
0x140025bb2  jz      short loc_140025BC4
0x140025bb4  mov     rax, [rcx]
0x140025bb7  mov     rax, [rax+10h]
0x140025bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025bc0  mov     [rbp+57h+var_A0], r15
0x140025bc4  mov     rcx, [rbp+57h+var_98]
0x140025bc8  test    rcx, rcx
0x140025bcb  jz      short loc_140025BDD
0x140025bcd  mov     rax, [rcx]
0x140025bd0  mov     rax, [rax+10h]
0x140025bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025bd9  mov     [rbp+57h+var_98], r15
0x140025bdd  mov     rcx, [rbp+57h+hObject]; hObject
0x140025be1  lea     rax, [rcx-1]
0x140025be5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140025be9  ja      short loc_140025BF9
0x140025beb  call    cs:__imp_CloseHandle
0x140025bf1  mov     [rbp+57h+hObject], 0FFFFFFFFFFFFFFFFh
0x140025bf9  lea     rcx, [rbp+57h+var_60]
0x140025bfd  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140025c03  mov     eax, ebx
0x140025c05  mov     rcx, [rbp+57h+var_30]
0x140025c09  xor     rcx, rsp; StackCookie
0x140025c0c  call    __security_check_cookie
0x140025c11  lea     r11, [rsp+0E0h+var_20]
0x140025c19  mov     rbx, [r11+30h]
0x140025c1d  mov     rsi, [r11+48h]
0x140025c21  mov     rsp, r11
0x140025c24  pop     r15
0x140025c26  pop     r14
0x140025c28  pop     r12
0x140025c2a  pop     rdi
0x140025c2b  pop     rbp
0x140025c2c  retn
0x140025c2d  mov     rcx, [rdi+78h]; String1
0x140025c31  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@PEAG@Z; CVdsService::FindRawDisk(ushort *)
0x140025c36  test    rax, rax
0x140025c39  jz      short loc_140025C87
0x140025c3b  mov     rdx, [rbp+57h+hObject]; void *
0x140025c3f  mov     rcx, rax; this
0x140025c42  test    sil, sil
0x140025c45  jz      short loc_140025C4E
0x140025c47  call    ?Offline@CVdsRawDiskLun@@QEAAJPEAX@Z; CVdsRawDiskLun::Offline(void *)
0x140025c4c  jmp     short loc_140025C53
0x140025c4e  call    ?Online@CVdsRawDiskLun@@QEAAJPEAX@Z; CVdsRawDiskLun::Online(void *)
0x140025c53  mov     [rbp+57h+var_B0], eax
0x140025c56  test    eax, eax
0x140025c58  jns     short loc_140025C7F
0x140025c5a  mov     r9, r14
0x140025c5d  cmp     [rdi+78h], r15
0x140025c61  cmovnz  r9, [rdi+78h]
0x140025c66  mov     [rsp+0E0h+var_C0], eax
0x140025c6a  lea     r8, aCvdsdisklunDoo_6; "CVdsDiskLun::DoOfflineOnline, 3 Name=%s"...
0x140025c71  xor     edx, edx
0x140025c73  mov     ecx, r12d
0x140025c76  call    cs:__imp_VdsTraceExW
0x140025c7c  mov     eax, [rbp+57h+var_B0]
0x140025c7f  mov     ebx, r15d
0x140025c82  jmp     loc_140025B67
0x140025c87  lea     rdx, [rbp+57h+var_40]
0x140025c8b  mov     rcx, [rbp+57h+hObject]
0x140025c8f  call    cs:__imp_GetDeviceNumber
0x140025c95  mov     ebx, eax
0x140025c97  test    eax, eax
0x140025c99  jz      short loc_140025CB2
0x140025c9b  jle     short loc_140025CA6
0x140025c9d  movzx   ebx, ax
0x140025ca0  or      ebx, 80070000h
0x140025ca6  lea     r8, aCvdsdisklunDoo_7; "CVdsDiskLun::DoOfflineOnline, 4 Name=%s"...
0x140025cad  jmp     loc_140025B45
0x140025cb2  mov     ebx, 1
0x140025cb7  mov     eax, dword ptr [rbp+57h+var_40+4]
0x140025cba  mov     dword ptr [rbp+57h+var_90], eax
0x140025cbd  mov     byte ptr [rbp+57h+var_90+4], sil
0x140025cc1  lea     rdx, [rbp+57h+Buf2]
0x140025cc5  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140025ccc  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x140025cd2  movups  xmm0, xmmword ptr [rax]
0x140025cd5  movdqu  [rbp+57h+Buf1], xmm0
0x140025cda  lea     rdx, [rbp+57h+var_50]
0x140025cde  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140025ce5  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x140025ceb  movups  xmm0, xmmword ptr [rax]
0x140025cee  movdqu  [rbp+57h+Buf2], xmm0
0x140025cf3  mov     r8d, 10h; Size
0x140025cf9  lea     rdx, [rbp+57h+Buf2]; Buf2
0x140025cfd  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140025d01  call    memcmp_0
0x140025d06  test    eax, eax
0x140025d08  jz      loc_140025B60
0x140025d0e  lea     rcx, [rbp+57h+Buf1]
0x140025d12  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x140025d18  mov     rsi, rax
0x140025d1b  test    rax, rax
0x140025d1e  jz      loc_140025DF8
0x140025d24  mov     rcx, [rbp+57h+var_98]
0x140025d28  test    rcx, rcx
0x140025d2b  jz      short loc_140025D3D
0x140025d2d  mov     rax, [rcx]
0x140025d30  mov     rax, [rax+10h]
0x140025d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025d39  mov     [rbp+57h+var_98], r15
0x140025d3d  mov     rax, [rsi]
0x140025d40  lea     r8, [rbp+57h+var_98]
0x140025d44  lea     rdx, IID_IVdsProvider
0x140025d4b  mov     rcx, rsi
0x140025d4e  mov     rax, [rax]
0x140025d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025d56  mov     ebx, eax
0x140025d58  test    eax, eax
0x140025d5a  jns     short loc_140025D74
0x140025d5c  lea     rdx, aCvdsdisklunDoo_1; "CVdsDiskLun::DoOfflineOnline, 6, disk n"...
0x140025d63  mov     r9d, eax
0x140025d66  mov     r8d, dword ptr [rbp+57h+var_40+4]
0x140025d6a  xor     ecx, ecx
0x140025d6c  call    cs:__imp_VdsTraceW
0x140025d72  jmp     short loc_140025DE9
0x140025d74  mov     rcx, [rbp+57h+var_A0]
0x140025d78  test    rcx, rcx
0x140025d7b  jz      short loc_140025D8D
0x140025d7d  mov     rax, [rcx]
0x140025d80  mov     rax, [rax+10h]
0x140025d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025d89  mov     [rbp+57h+var_A0], r15
0x140025d8d  mov     rax, [rsi]
0x140025d90  lea     r8, [rbp+57h+var_A0]
0x140025d94  lea     rdx, IID_IVdsSwProviderPrivateOffline
0x140025d9b  mov     rcx, rsi
0x140025d9e  mov     rax, [rax]
0x140025da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025da6  mov     ebx, eax
0x140025da8  test    eax, eax
0x140025daa  jns     short loc_140025DB5
0x140025dac  lea     rdx, aCvdsdisklunDoo_4; "CVdsDiskLun::DoOfflineOnline, 7, disk n"...
0x140025db3  jmp     short loc_140025D63
0x140025db5  mov     [rbp+57h+var_B0], 80004005h
0x140025dbc  mov     rcx, [rbp+57h+var_A0]
0x140025dc0  mov     rax, [rcx]
0x140025dc3  lea     r8, [rbp+57h+var_B0]
0x140025dc7  mov     rdx, [rbp+57h+var_90]
0x140025dcb  mov     rax, [rax+18h]
0x140025dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025dd4  mov     ebx, eax
0x140025dd6  test    eax, eax
0x140025dd8  jns     short loc_140025DE3
0x140025dda  lea     rdx, aCvdsdisklunDoo; "CVdsDiskLun::DoOfflineOnline, 8, disk n"...
0x140025de1  jmp     short loc_140025D63
0x140025de3  jz      loc_140025B64
0x140025de9  lea     rcx, [rbp+57h+Buf1]
0x140025ded  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x140025df3  jmp     loc_140025CDA
0x140025df8  mov     ebx, 80042448h
0x140025dfd  mov     r9d, ebx
0x140025e00  mov     r8d, dword ptr [rbp+57h+var_40+4]
0x140025e04  lea     rdx, aCvdsdisklunDoo_3; "CVdsDiskLun::DoOfflineOnline, 5, disk n"...
0x140025e0b  xor     ecx, ecx
0x140025e0d  call    cs:__imp_VdsTraceW
0x140025e13  jmp     loc_140025BAB
```
