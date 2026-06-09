# CVdsService::AssignOneDiskToProviders(ushort *,int,uchar)

- ea: `0x1400078a0`
- end: `0x140007ba1`
- name: `?AssignOneDiskToProviders@CVdsService@@SAJPEAGHE@Z`
- size: `769`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, int, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400070c0`
- `0x14004fd50`

## callees

- `0x1400078a0`
- `0x140012c48`
- `0x140013298`
- `0x140037320`
- `0x140037a0c`
- `0x14003ca88`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140007937`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140007937`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140007954`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140007954`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140007984`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140007984`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140007a28`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140007a28`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400078e6`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400078e6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007a41`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007b1e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007b6e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007b91`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007a41`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007b1e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007b6e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140007b91`
- `vdsutil!VdsTraceW` at `0x140007926`
- `vdsutil!VdsTraceW` at `0x140007998`
- `vdsutil!VdsTraceW` at `0x140007b59`
- `vdsutil!VdsTraceW` at `0x140007926`
- `vdsutil!VdsTraceW` at `0x140007998`
- `vdsutil!VdsTraceW` at `0x140007b59`

## string_xrefs

- `0x1400078d6`: `CVdsService::AssignOneDiskToProviders()`
- `0x14000791a`: `CVdsService::AssignOneDiskToProviders, 0, name=%s, hr=%lX`
- `0x14000798f`: `CVdsService::AssignOneDiskToProviders, 1`
- `0x140007b4d`: `CVdsService::AssignOneDiskToProviders, 2, name=%s`

## pseudocode

```c
__int64 __fastcall CVdsService::AssignOneDiskToProviders(WCHAR *lpFileName, int a2, char a3)
{
  int v6; // r14d
  int v7; // edi
  unsigned int v8; // eax
  signed int v9; // ebx
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int v15; // r8d
  unsigned int v16; // eax
  __int64 *v17; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v18[16]; // [rsp+48h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v20[24]; // [rsp+68h] [rbp-1h] BYREF
  GUID Buf2; // [rsp+80h] [rbp+17h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "CVdsService::AssignOneDiskToProviders()");
  Buf1 = 0;
  v6 = 0;
  v7 = 1;
  if ( !a3 && dword_14009B190 )
  {
    v8 = CVdsService::AddLunIdToMap(lpFileName);
    VdsTraceW(3, L"CVdsService::AssignOneDiskToProviders, 0, name=%s, hr=%lX", lpFileName, v8);
  }
  Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
  v9 = -2147467259;
  while ( 1 )
  {
    Buf2 = *(GUID *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v20);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      goto LABEL_24;
    v17 = 0;
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    if ( !EntryPointer )
    {
      VdsTraceW(0, L"CVdsService::AssignOneDiskToProviders, 1");
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
      goto LABEL_19;
    }
    v11 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivate, (__int64 *)&v17);
    if ( v11 < 0 )
    {
      VdsLogError(0xC2000009, 0, 0, v11, 0x2000010u, 0);
      VdsTraceW(3, L"CVdsService::AssignOneDiskToProviders, 2, name=%s", lpFileName);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
      return 2147755074LL;
    }
    v12 = *v17;
    v13 = v7 == 1
        ? (*(__int64 (__fastcall **)(__int64 *, WCHAR *))(v12 + 24))(v17, lpFileName)
        : (*(unsigned __int64 (__fastcall **)(__int64 *, WCHAR *))(v12 + 32))(v17, lpFileName);
    v9 = v13;
    if ( v13 < 0 )
      break;
    if ( v13 || v7 != 1 )
    {
      if ( v17 )
        (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    }
    else
    {
      if ( !a2 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
        goto LABEL_21;
      }
      v6 = 1;
      v7 = 0;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
    }
LABEL_19:
    CRtlListIter::Next((CRtlListIter *)&Buf1);
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
LABEL_24:
  if ( v6 )
  {
LABEL_21:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
    return 0;
  }
  if ( v9 == -2147024894 || v9 == -2147024841 )
    goto LABEL_35;
  Buf2 = GUID_NULL;
  if ( v9 == -2147024875 || (v15 = 0, v9 == -2147024726) )
    v15 = 1;
  v16 = CVdsService::ClaimRawDisk(lpFileName, &Buf2, v15, 1);
  v9 = v16;
  if ( v16 )
  {
    if ( v16 == 55 || v16 == 2 || (VdsLogError(0xC2000006, 0, 0, v16, 0x2000011u, lpFileName, 0), v9 > 0) )
      v9 = (unsigned __int16)v9 | 0x80070000;
LABEL_35:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
    return (unsigned int)v9;
  }
  else
  {
    CVdsService::SendDiskNotification(8u, &Buf2);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
    return 1;
  }
}

```

## disassembly

```asm
0x1400078a0  mov     [rsp-8+arg_8], rbx
0x1400078a5  mov     [rsp-8+arg_10], rsi
0x1400078aa  push    rbp
0x1400078ab  push    rdi
0x1400078ac  push    r12
0x1400078ae  push    r14
0x1400078b0  push    r15
0x1400078b2  lea     rbp, [rsp-37h]
0x1400078b7  sub     rsp, 0A0h
0x1400078be  mov     rax, cs:__security_cookie
0x1400078c5  xor     rax, rsp
0x1400078c8  mov     [rbp+57h+var_30], rax
0x1400078cc  movzx   ebx, r8b
0x1400078d0  mov     r15d, edx
0x1400078d3  mov     rsi, rcx
0x1400078d6  lea     r8, aCvdsserviceAss_3; "CVdsService::AssignOneDiskToProviders()"
0x1400078dd  mov     edx, 5Eh ; '^'
0x1400078e2  lea     rcx, [rbp+57h+var_78]
0x1400078e6  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400078ec  nop
0x1400078ed  xorps   xmm0, xmm0
0x1400078f0  movups  [rbp+57h+Buf1], xmm0
0x1400078f4  xor     r12d, r12d
0x1400078f7  mov     r14d, r12d
0x1400078fa  mov     edi, 1
0x1400078ff  test    bl, bl
0x140007901  jnz     short loc_14000792C
0x140007903  cmp     cs:dword_14009B190, r12d
0x14000790a  jz      short loc_14000792C
0x14000790c  mov     rcx, rsi; lpFileName
0x14000790f  call    ?AddLunIdToMap@CVdsService@@CAJPEAG@Z; CVdsService::AddLunIdToMap(ushort *)
0x140007914  mov     r9d, eax
0x140007917  mov     r8, rsi
0x14000791a  lea     rdx, aCvdsserviceAss_6; "CVdsService::AssignOneDiskToProviders, "...
0x140007921  mov     ecx, 3
0x140007926  call    cs:__imp_VdsTraceW
0x14000792c  lea     rdx, [rbp+57h+Buf2]
0x140007930  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140007937  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14000793d  movups  xmm0, xmmword ptr [rax]
0x140007940  movups  [rbp+57h+Buf1], xmm0
0x140007944  mov     ebx, 80004005h
0x140007949  lea     rdx, [rbp+57h+var_58]
0x14000794d  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140007954  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14000795a  movups  xmm0, xmmword ptr [rax]
0x14000795d  movaps  [rbp+57h+Buf2], xmm0
0x140007961  mov     r8d, 10h; Size
0x140007967  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14000796b  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14000796f  call    memcmp_0
0x140007974  test    eax, eax
0x140007976  jz      loc_140007A86
0x14000797c  mov     [rbp+57h+var_80], r12
0x140007980  lea     rcx, [rbp+57h+Buf1]
0x140007984  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14000798a  test    rax, rax
0x14000798d  jnz     short loc_1400079AA
0x14000798f  lea     rdx, aCvdsserviceAss_0; "CVdsService::AssignOneDiskToProviders, "...
0x140007996  xor     ecx, ecx
0x140007998  call    cs:__imp_VdsTraceW
0x14000799e  nop
0x14000799f  lea     rcx, [rbp+57h+var_80]
0x1400079a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400079a8  jmp     short loc_140007A24
0x1400079aa  mov     rcx, [rax]
0x1400079ad  mov     r9, [rcx]
0x1400079b0  lea     r8, [rbp+57h+var_80]
0x1400079b4  lea     rdx, IID_IVdsSwProviderPrivate
0x1400079bb  mov     rcx, rax
0x1400079be  mov     rax, r9
0x1400079c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079c6  test    eax, eax
0x1400079c8  js      loc_140007B2B
0x1400079ce  mov     rcx, [rbp+57h+var_80]
0x1400079d2  mov     rdx, rsi
0x1400079d5  mov     rax, [rcx]
0x1400079d8  cmp     edi, 1
0x1400079db  jnz     short loc_1400079E3
0x1400079dd  mov     rax, [rax+18h]
0x1400079e1  jmp     short loc_1400079E7
0x1400079e3  mov     rax, [rax+20h]
0x1400079e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079ec  mov     ebx, eax
0x1400079ee  test    eax, eax
0x1400079f0  js      short loc_140007A71
0x1400079f2  jnz     short loc_140007A0F
0x1400079f4  cmp     edi, 1
0x1400079f7  jnz     short loc_140007A0F
0x1400079f9  test    r15d, r15d
0x1400079fc  jz      short loc_140007A33
0x1400079fe  mov     r14d, edi
0x140007a01  mov     edi, r12d
0x140007a04  lea     rcx, [rbp+57h+var_80]
0x140007a08  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140007a0d  jmp     short loc_140007A24
0x140007a0f  mov     rcx, [rbp+57h+var_80]
0x140007a13  test    rcx, rcx
0x140007a16  jz      short loc_140007A24
0x140007a18  mov     rax, [rcx]
0x140007a1b  mov     rax, [rax+10h]
0x140007a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a24  lea     rcx, [rbp+57h+Buf1]
0x140007a28  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x140007a2e  jmp     loc_140007949
0x140007a33  lea     rcx, [rbp+57h+var_80]
0x140007a37  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140007a3c  nop
0x140007a3d  lea     rcx, [rbp+57h+var_78]
0x140007a41  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007a47  xor     eax, eax
0x140007a49  mov     rcx, [rbp+57h+var_30]
0x140007a4d  xor     rcx, rsp; StackCookie
0x140007a50  call    __security_check_cookie
0x140007a55  lea     r11, [rsp+0C0h+var_20]
0x140007a5d  mov     rbx, [r11+38h]
0x140007a61  mov     rsi, [r11+40h]
0x140007a65  mov     rsp, r11
0x140007a68  pop     r15
0x140007a6a  pop     r14
0x140007a6c  pop     r12
0x140007a6e  pop     rdi
0x140007a6f  pop     rbp
0x140007a70  retn
0x140007a71  mov     rcx, [rbp+57h+var_80]
0x140007a75  test    rcx, rcx
0x140007a78  jz      short loc_140007A86
0x140007a7a  mov     rax, [rcx]
0x140007a7d  mov     rax, [rax+10h]
0x140007a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a86  test    r14d, r14d
0x140007a89  jnz     short loc_140007A3D
0x140007a8b  cmp     ebx, 80070002h
0x140007a91  jz      loc_140007B1A
0x140007a97  cmp     ebx, 80070037h
0x140007a9d  jz      short loc_140007B1A
0x140007a9f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140007aa6  movups  [rbp+57h+Buf2], xmm0
0x140007aaa  cmp     ebx, 80070015h
0x140007ab0  jz      short loc_140007ABD
0x140007ab2  cmp     ebx, 800700AAh
0x140007ab8  mov     r8d, r12d
0x140007abb  jnz     short loc_140007AC3
0x140007abd  mov     r8d, 1; int
0x140007ac3  mov     r9d, 1; int
0x140007ac9  lea     rdx, [rbp+57h+Buf2]; struct _GUID *
0x140007acd  mov     rcx, rsi; lpFileName
0x140007ad0  call    ?ClaimRawDisk@CVdsService@@SAKPEAGAEAU_GUID@@HH@Z; CVdsService::ClaimRawDisk(ushort *,_GUID &,int,int)
0x140007ad5  mov     ebx, eax
0x140007ad7  test    eax, eax
0x140007ad9  jz      loc_140007B7E
0x140007adf  cmp     eax, 37h ; '7'
0x140007ae2  jz      short loc_140007B11
0x140007ae4  cmp     eax, 2
0x140007ae7  jz      short loc_140007B11
0x140007ae9  mov     [rsp+0C0h+var_90], r12
0x140007aee  mov     [rsp+0C0h+var_98], rsi; unsigned __int16 *
0x140007af3  mov     [rsp+0C0h+var_A0], 2000011h; unsigned int
0x140007afb  mov     r9d, eax; unsigned int
0x140007afe  xor     r8d, r8d; void *
0x140007b01  xor     edx, edx; unsigned int
0x140007b03  mov     ecx, 0C2000006h; unsigned int
0x140007b08  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140007b0d  test    ebx, ebx
0x140007b0f  jle     short loc_140007B1A
0x140007b11  movzx   ebx, bx
0x140007b14  or      ebx, 80070000h
0x140007b1a  lea     rcx, [rbp+57h+var_78]
0x140007b1e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007b24  mov     eax, ebx
0x140007b26  jmp     loc_140007A49
0x140007b2b  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x140007b30  mov     [rsp+0C0h+var_A0], 2000010h; unsigned int
0x140007b38  mov     r9d, eax; unsigned int
0x140007b3b  xor     r8d, r8d; void *
0x140007b3e  xor     edx, edx; unsigned int
0x140007b40  mov     ecx, 0C2000009h; unsigned int
0x140007b45  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140007b4a  mov     r8, rsi
0x140007b4d  lea     rdx, aCvdsserviceAss_2; "CVdsService::AssignOneDiskToProviders, "...
0x140007b54  mov     ecx, 3
0x140007b59  call    cs:__imp_VdsTraceW
0x140007b5f  nop
0x140007b60  lea     rcx, [rbp+57h+var_80]
0x140007b64  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140007b69  nop
0x140007b6a  lea     rcx, [rbp+57h+var_78]
0x140007b6e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007b74  mov     eax, 80042442h
0x140007b79  jmp     loc_140007A49
0x140007b7e  lea     rdx, [rbp+57h+Buf2]; struct _GUID *
0x140007b82  mov     ecx, 8; unsigned int
0x140007b87  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x140007b8c  nop
0x140007b8d  lea     rcx, [rbp+57h+var_78]
0x140007b91  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140007b97  mov     eax, 1
0x140007b9c  jmp     loc_140007A49
```
