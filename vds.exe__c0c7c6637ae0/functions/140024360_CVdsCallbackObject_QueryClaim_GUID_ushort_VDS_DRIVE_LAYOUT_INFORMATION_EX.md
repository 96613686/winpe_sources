# CVdsCallbackObject::QueryClaim(_GUID,ushort *,_VDS_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140024360`
- end: `0x140024715`
- name: `?QueryClaim@CVdsCallbackObject@@UEAAJU_GUID@@PEAGPEAU_VDS_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `949`
- prototype: `int(CVdsCallbackObject *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *, struct _VDS_DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000fa00`
- `0x140012c48`
- `0x140013298`
- `0x140024360`
- `0x14002e123`
- `0x140037a0c`
- `0x140038618`
- `0x14003ca88`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400246ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400246e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400246ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400246e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400243ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400243ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002451b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002451b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024532`
- `vdsutil!VdsTraceExW` at `0x1400244ca`
- `vdsutil!VdsTraceExW` at `0x1400245ce`
- `vdsutil!VdsTraceExW` at `0x14002469f`
- `vdsutil!VdsTraceExW` at `0x1400244ca`
- `vdsutil!VdsTraceExW` at `0x1400245ce`
- `vdsutil!VdsTraceExW` at `0x14002469f`
- `vdsutil!VdsTraceEx` at `0x14002448d`
- `vdsutil!VdsTraceEx` at `0x140024591`
- `vdsutil!VdsTraceEx` at `0x14002461d`
- `vdsutil!VdsTraceEx` at `0x14002448d`
- `vdsutil!VdsTraceEx` at `0x140024591`
- `vdsutil!VdsTraceEx` at `0x14002461d`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140024408`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140024408`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140024421`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140024421`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140024456`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140024456`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x1400244de`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x1400244de`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002439e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002439e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400246b8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400246ef`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400246b8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400246ef`

## string_xrefs

- `0x14002468b`: `CVdsCallbackObject::QueryClaim, 2, hr=%lX, pwszDevicePath=%s`
- `0x1400243c9`: `CVdsCallbackObject::QueryClaim, 1, hr=%lX, pwszDevicePath=%s`
- `0x1400244be`: `CVdsCallbackObject::QueryClaim, 3, hr=%lX, pwszDevicePath=%s`
- `0x1400245c2`: `CVdsCallbackObject::QueryClaim, 4, hr=%lX, pwszDevicePath=%s`
- `0x140024642`: `CVdsCallbackObject::QueryClaim, 4, hr=%lX, pwszDevicePath=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CVdsCallbackObject::QueryClaim(
        CVdsCallbackObject *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        struct _VDS_DRIVE_LAYOUT_INFORMATION_EX *a4)
{
  unsigned int v7; // ebx
  signed int v8; // esi
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // r15
  int v10; // eax
  int v11; // eax
  int v12; // eax
  const wchar_t *v13; // r8
  int v14; // eax
  CVdsCallbackObject *v16; // rcx
  __int64 v17; // [rsp+30h] [rbp-79h] BYREF
  __int64 v18; // [rsp+38h] [rbp-71h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v21[16]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v22[16]; // [rsp+70h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-29h]
  LPVOID v24; // [rsp+98h] [rbp-11h]
  GUID Buf2; // [rsp+B0h] [rbp+7h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v20, 0x5Eu, "CVdsCallbackObject::QueryClaim()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( !a3 )
  {
    v7 = -2147024809;
    VdsTraceExW(95, 0, L"CVdsCallbackObject::QueryClaim, 1, hr=%lX, pwszDevicePath=%s", 2147942487LL, L"UNKNOWN");
    goto LABEL_32;
  }
  if ( a4 && (*(_DWORD *)a4 || *((_DWORD *)a4 + 2)) )
  {
    v7 = 1;
    v8 = 1;
    Buf1 = 0;
    for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
          ;
          CRtlListIter::Next((CRtlListIter *)&Buf1) )
    {
      Buf2 = *(GUID *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v21);
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        if ( v8 >= 0 )
          goto LABEL_32;
        v7 = -2147467259;
        v13 = L"CVdsCallbackObject::QueryClaim, 4, hr=%lX, pwszDevicePath=%s";
LABEL_31:
        VdsTraceExW(95, 0, v13, v7, a3);
LABEL_32:
        LeaveCriticalSection(&g_GlobalCriticalSection);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v20);
        return v7;
      }
      v17 = 0;
      EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
      v10 = (**EntryPointer)(EntryPointer, &IID_IVdsProvider, &v17);
      v8 = v10;
      if ( v10 < 0 )
        break;
      memset_0(v22, 0, 0x40u);
      v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 24LL))(v17, v22);
      if ( v8 < 0 )
        goto LABEL_10;
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v24 )
      {
        CoTaskMemFree(v24);
        v24 = 0;
      }
      if ( memcmp_0(v22, a2, 0x10u) )
      {
        v18 = 0;
        v11 = (**EntryPointer)(EntryPointer, &IID_IVdsOwnershipChangeQuery, &v18);
        v8 = v11;
        if ( v11 >= 0 )
        {
          Buf2 = *a2;
          v12 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned __int16 *, struct _VDS_DRIVE_LAYOUT_INFORMATION_EX *))(*(_QWORD *)v18 + 24LL))(
                  v18,
                  &Buf2,
                  a3,
                  a4);
          v7 = v12;
          if ( v12 < 0 )
            VdsTraceEx(94, 0, "CVdsCallbackObject::QueryClaim, 3.75, hr=%lX", v12);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
          goto LABEL_32;
        }
        VdsTraceEx(94, 0, "CVdsCallbackObject::QueryClaim, 3.5, hr=%lX", v11);
        VdsLogError(0xC2000009, 0, 0, v8, 0x2020003u, 0);
        VdsTraceExW(95, 0, L"CVdsCallbackObject::QueryClaim, 4, hr=%lX, pwszDevicePath=%s", (unsigned int)v8, a3);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
      }
LABEL_11:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
    }
    VdsTraceEx(94, 0, "CVdsCallbackObject::QueryClaim, 2.5, hr=%lX", v10);
    VdsLogError(0xC2000009, 0, 0, v8, 0x2020002u, 0);
LABEL_10:
    VdsTraceExW(95, 0, L"CVdsCallbackObject::QueryClaim, 3, hr=%lX, pwszDevicePath=%s", (unsigned int)v8, a3);
    goto LABEL_11;
  }
  Buf2 = GUID_NULL;
  if ( CVdsService::FindRawDisk(a3) )
  {
    v7 = 0;
    goto LABEL_32;
  }
  v14 = CVdsService::ClaimRawDisk(a3, &Buf2, 0, 0);
  v7 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    v13 = L"CVdsCallbackObject::QueryClaim, 2, hr=%lX, pwszDevicePath=%s";
    goto LABEL_31;
  }
  CVdsService::SendDiskNotification(8u, &Buf2);
  CVdsCallbackObject::InitiateSecondAuctionIfLayoutChanged(v16, a3, &Buf2);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v20);
  return 0;
}

```

## disassembly

```asm
0x140024360  push    rbp
0x140024362  push    rbx
0x140024363  push    rsi
0x140024364  push    rdi
0x140024365  push    r12
0x140024367  push    r14
0x140024369  push    r15
0x14002436b  lea     rbp, [rsp-27h]
0x140024370  sub     rsp, 0D0h
0x140024377  mov     rax, cs:__security_cookie
0x14002437e  xor     rax, rsp
0x140024381  mov     [rbp+57h+var_38], rax
0x140024385  mov     r14, r9
0x140024388  mov     rdi, r8
0x14002438b  mov     r12, rdx
0x14002438e  lea     r8, aCvdscallbackob_24; "CVdsCallbackObject::QueryClaim()"
0x140024395  mov     edx, 5Eh ; '^'
0x14002439a  lea     rcx, [rbp+57h+var_B0]
0x14002439e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400243a4  nop
0x1400243a5  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400243ac  call    cs:__imp_EnterCriticalSection
0x1400243b2  nop
0x1400243b3  test    rdi, rdi
0x1400243b6  jnz     short loc_1400243D5
0x1400243b8  lea     rax, aUnknown_0; "UNKNOWN"
0x1400243bf  mov     qword ptr [rsp+100h+var_E0], rax
0x1400243c4  mov     ebx, 80070057h
0x1400243c9  lea     r8, aCvdscallbackob_34; "CVdsCallbackObject::QueryClaim, 1, hr=%"...
0x1400243d0  jmp     loc_140024697
0x1400243d5  test    r14, r14
0x1400243d8  jz      loc_14002464B
0x1400243de  cmp     dword ptr [r14], 0
0x1400243e2  jnz     short loc_1400243EF
0x1400243e4  cmp     dword ptr [r14+8], 0
0x1400243e9  jz      loc_14002464B
0x1400243ef  mov     ebx, 1
0x1400243f4  mov     esi, ebx
0x1400243f6  xorps   xmm0, xmm0
0x1400243f9  movups  [rbp+57h+Buf1], xmm0
0x1400243fd  lea     rdx, [rbp+57h+Buf2]
0x140024401  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140024408  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14002440e  movups  xmm0, xmmword ptr [rax]
0x140024411  movdqu  [rbp+57h+Buf1], xmm0
0x140024416  lea     rdx, [rbp+57h+var_A0]
0x14002441a  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140024421  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x140024427  movups  xmm0, xmmword ptr [rax]
0x14002442a  movdqu  xmmword ptr [rbp+57h+Buf2.Data1], xmm0
0x14002442f  mov     r8d, 10h; Size
0x140024435  lea     rdx, [rbp+57h+Buf2]; Buf2
0x140024439  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14002443d  call    memcmp_0
0x140024442  test    eax, eax
0x140024444  jz      loc_140024639
0x14002444a  mov     [rbp+57h+var_D0], 0
0x140024452  lea     rcx, [rbp+57h+Buf1]
0x140024456  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14002445c  mov     r15, rax
0x14002445f  mov     rcx, [rax]
0x140024462  mov     rax, [rcx]
0x140024465  lea     r8, [rbp+57h+var_D0]
0x140024469  lea     rdx, IID_IVdsProvider
0x140024470  mov     rcx, r15
0x140024473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024478  mov     esi, eax
0x14002447a  test    eax, eax
0x14002447c  jns     short loc_1400244E9
0x14002447e  mov     r9d, eax
0x140024481  lea     r8, aCvdscallbackob_42; "CVdsCallbackObject::QueryClaim, 2.5, hr"...
0x140024488  xor     edx, edx
0x14002448a  lea     ecx, [rdx+5Eh]
0x14002448d  call    cs:__imp_VdsTraceEx
0x140024493  mov     [rsp+100h+var_D8], 0; unsigned __int16 *
0x14002449c  mov     [rsp+100h+var_E0], 2020002h; unsigned int
0x1400244a4  mov     r9d, esi; unsigned int
0x1400244a7  xor     r8d, r8d; void *
0x1400244aa  xor     edx, edx; unsigned int
0x1400244ac  mov     ecx, 0C2000009h; unsigned int
0x1400244b1  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400244b6  mov     qword ptr [rsp+100h+var_E0], rdi
0x1400244bb  mov     r9d, esi
0x1400244be  lea     r8, aCvdscallbackob_15; "CVdsCallbackObject::QueryClaim, 3, hr=%"...
0x1400244c5  xor     edx, edx
0x1400244c7  lea     ecx, [rdx+5Fh]
0x1400244ca  call    cs:__imp_VdsTraceExW
0x1400244d0  nop
0x1400244d1  lea     rcx, [rbp+57h+var_D0]
0x1400244d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400244da  lea     rcx, [rbp+57h+Buf1]
0x1400244de  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x1400244e4  jmp     loc_140024416
0x1400244e9  xor     edx, edx; Val
0x1400244eb  lea     r8d, [rdx+40h]; Size
0x1400244ef  lea     rcx, [rbp+57h+var_90]; void *
0x1400244f3  call    memset_0
0x1400244f8  mov     rcx, [rbp+57h+var_D0]
0x1400244fc  mov     rax, [rcx]
0x1400244ff  lea     rdx, [rbp+57h+var_90]
0x140024503  mov     rax, [rax+18h]
0x140024507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002450c  mov     esi, eax
0x14002450e  test    eax, eax
0x140024510  js      short loc_1400244B6
0x140024512  mov     rcx, [rbp+57h+pv]; pv
0x140024516  test    rcx, rcx
0x140024519  jz      short loc_140024529
0x14002451b  call    cs:__imp_CoTaskMemFree
0x140024521  mov     [rbp+57h+pv], 0
0x140024529  mov     rcx, [rbp+57h+var_68]; pv
0x14002452d  test    rcx, rcx
0x140024530  jz      short loc_140024540
0x140024532  call    cs:__imp_CoTaskMemFree
0x140024538  mov     [rbp+57h+var_68], 0
0x140024540  mov     r8d, 10h; Size
0x140024546  mov     rdx, r12; Buf2
0x140024549  lea     rcx, [rbp+57h+var_90]; Buf1
0x14002454d  call    memcmp_0
0x140024552  test    eax, eax
0x140024554  jnz     short loc_14002455B
0x140024556  jmp     loc_1400244D1
0x14002455b  mov     [rbp+57h+var_C8], 0
0x140024563  mov     rax, [r15]
0x140024566  lea     r8, [rbp+57h+var_C8]
0x14002456a  lea     rdx, IID_IVdsOwnershipChangeQuery
0x140024571  mov     rcx, r15
0x140024574  mov     rax, [rax]
0x140024577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002457c  mov     esi, eax
0x14002457e  test    eax, eax
0x140024580  jns     short loc_1400245E4
0x140024582  mov     r9d, eax
0x140024585  lea     r8, aCvdscallbackob_41; "CVdsCallbackObject::QueryClaim, 3.5, hr"...
0x14002458c  xor     edx, edx
0x14002458e  lea     ecx, [rdx+5Eh]
0x140024591  call    cs:__imp_VdsTraceEx
0x140024597  mov     [rsp+100h+var_D8], 0; unsigned __int16 *
0x1400245a0  mov     [rsp+100h+var_E0], 2020003h; unsigned int
0x1400245a8  mov     r9d, esi; unsigned int
0x1400245ab  xor     r8d, r8d; void *
0x1400245ae  xor     edx, edx; unsigned int
0x1400245b0  mov     ecx, 0C2000009h; unsigned int
0x1400245b5  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400245ba  mov     qword ptr [rsp+100h+var_E0], rdi
0x1400245bf  mov     r9d, esi
0x1400245c2  lea     r8, aCvdscallbackob_32; "CVdsCallbackObject::QueryClaim, 4, hr=%"...
0x1400245c9  xor     edx, edx
0x1400245cb  lea     ecx, [rdx+5Fh]
0x1400245ce  call    cs:__imp_VdsTraceExW
0x1400245d4  nop
0x1400245d5  lea     rcx, [rbp+57h+var_C8]
0x1400245d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400245de  nop
0x1400245df  jmp     loc_1400244D1
0x1400245e4  mov     rcx, [rbp+57h+var_C8]
0x1400245e8  movups  xmm0, xmmword ptr [r12]
0x1400245ed  movdqu  xmmword ptr [rbp+57h+Buf2.Data1], xmm0
0x1400245f2  mov     rax, [rcx]
0x1400245f5  mov     r9, r14
0x1400245f8  mov     r8, rdi
0x1400245fb  lea     rdx, [rbp+57h+Buf2]
0x1400245ff  mov     rax, [rax+18h]
0x140024603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024608  mov     ebx, eax
0x14002460a  test    eax, eax
0x14002460c  jns     short loc_140024624
0x14002460e  mov     r9d, eax
0x140024611  lea     r8, aCvdscallbackob_6; "CVdsCallbackObject::QueryClaim, 3.75, h"...
0x140024618  xor     edx, edx
0x14002461a  lea     ecx, [rdx+5Eh]
0x14002461d  call    cs:__imp_VdsTraceEx
0x140024623  nop
0x140024624  lea     rcx, [rbp+57h+var_C8]
0x140024628  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14002462d  nop
0x14002462e  lea     rcx, [rbp+57h+var_D0]
0x140024632  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140024637  jmp     short loc_1400246A6
0x140024639  test    esi, esi
0x14002463b  jns     short loc_1400246A6
0x14002463d  mov     ebx, 80004005h
0x140024642  lea     r8, aCvdscallbackob_32; "CVdsCallbackObject::QueryClaim, 4, hr=%"...
0x140024649  jmp     short loc_140024692
0x14002464b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140024652  movdqu  xmmword ptr [rbp+57h+Buf2.Data1], xmm0
0x140024657  mov     rcx, rdi; String1
0x14002465a  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@PEAG@Z; CVdsService::FindRawDisk(ushort *)
0x14002465f  test    rax, rax
0x140024662  jz      short loc_140024668
0x140024664  xor     ebx, ebx
0x140024666  jmp     short loc_1400246A6
0x140024668  xor     r9d, r9d; int
0x14002466b  xor     r8d, r8d; int
0x14002466e  lea     rdx, [rbp+57h+Buf2]; struct _GUID *
0x140024672  mov     rcx, rdi; lpFileName
0x140024675  call    ?ClaimRawDisk@CVdsService@@SAKPEAGAEAU_GUID@@HH@Z; CVdsService::ClaimRawDisk(ushort *,_GUID &,int,int)
0x14002467a  mov     ebx, eax
0x14002467c  test    eax, eax
0x14002467e  jz      short loc_1400246C2
0x140024680  jle     short loc_14002468B
0x140024682  movzx   ebx, ax
0x140024685  or      ebx, 80070000h
0x14002468b  lea     r8, aCvdscallbackob_22; "CVdsCallbackObject::QueryClaim, 2, hr=%"...
0x140024692  mov     qword ptr [rsp+100h+var_E0], rdi
0x140024697  mov     r9d, ebx
0x14002469a  xor     edx, edx
0x14002469c  lea     ecx, [rdx+5Fh]
0x14002469f  call    cs:__imp_VdsTraceExW
0x1400246a5  nop
0x1400246a6  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400246ad  call    cs:__imp_LeaveCriticalSection
0x1400246b3  nop
0x1400246b4  lea     rcx, [rbp+57h+var_B0]
0x1400246b8  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400246be  mov     eax, ebx
0x1400246c0  jmp     short loc_1400246F7
0x1400246c2  lea     rdx, [rbp+57h+Buf2]; struct _GUID *
0x1400246c6  mov     ecx, 8; unsigned int
0x1400246cb  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x1400246d0  lea     r8, [rbp+57h+Buf2]; struct _GUID *
0x1400246d4  mov     rdx, rdi; unsigned __int16 *
0x1400246d7  call    ?InitiateSecondAuctionIfLayoutChanged@CVdsCallbackObject@@AEAAXPEAGAEAU_GUID@@@Z; CVdsCallbackObject::InitiateSecondAuctionIfLayoutChanged(ushort *,_GUID &)
0x1400246dc  nop
0x1400246dd  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400246e4  call    cs:__imp_LeaveCriticalSection
0x1400246ea  nop
0x1400246eb  lea     rcx, [rbp+57h+var_B0]
0x1400246ef  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400246f5  xor     eax, eax
0x1400246f7  mov     rcx, [rbp+57h+var_38]
0x1400246fb  xor     rcx, rsp; StackCookie
0x1400246fe  call    __security_check_cookie
0x140024703  add     rsp, 0D0h
0x14002470a  pop     r15
0x14002470c  pop     r14
0x14002470e  pop     r12
0x140024710  pop     rdi
0x140024711  pop     rsi
0x140024712  pop     rbx
0x140024713  pop     rbp
0x140024714  retn
```
