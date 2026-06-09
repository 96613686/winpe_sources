# CVdsService::OnDiskLayoutChange(ushort *,_GUID &,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14001b6f0`
- end: `0x14001b94f`
- name: `?OnDiskLayoutChange@CVdsService@@SAXPEAGAEAU_GUID@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `607`
- prototype: `void __fastcall(unsigned __int16 *, struct _GUID *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004fa10`

## callees

- `0x140012c48`
- `0x140013298`
- `0x14001b6f0`
- `0x14003870c`
- `0x14003c424`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b926`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b926`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001b747`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001b747`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b76d`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b76d`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b786`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b786`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001b7bb`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001b7bb`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001b881`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001b881`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b739`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b739`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001b931`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001b931`
- `vdsutil!VdsTraceW` at `0x14001b7d0`
- `vdsutil!VdsTraceW` at `0x14001b827`
- `vdsutil!VdsTraceW` at `0x14001b86d`
- `vdsutil!VdsTraceW` at `0x14001b8dd`
- `vdsutil!VdsTraceW` at `0x14001b918`
- `vdsutil!VdsTraceW` at `0x14001b7d0`
- `vdsutil!VdsTraceW` at `0x14001b827`
- `vdsutil!VdsTraceW` at `0x14001b86d`
- `vdsutil!VdsTraceW` at `0x14001b8dd`
- `vdsutil!VdsTraceW` at `0x14001b918`

## string_xrefs

- `0x14001b729`: `CVdsService::OnDiskLayoutChange(2)`
- `0x14001b90f`: `CVdsService::OnDiskLayoutChange(2), 1, name=%s, Layout=%p`
- `0x14001b7c9`: `CVdsService::OnDiskLayoutChange(2), 1a`
- `0x14001b81e`: `CVdsService::OnDiskLayoutChange(2), 1b, hr=%1X`
- `0x14001b864`: `CVdsService::OnDiskLayoutChange(2), 2, name=%s, hr=%lX`
- `0x14001b8d4`: `CVdsService::OnDiskLayoutChange(2), 3, name=%s, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVdsService::OnDiskLayoutChange(
        unsigned __int16 *a1,
        struct _GUID *a2,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a3)
{
  unsigned int v6; // edi
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v8; // eax
  int v9; // eax
  struct CVdsRawDiskLun *RawDisk; // rax
  __int64 v11; // [rsp+30h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+38h] [rbp-11h] BYREF
  GUID Buf2; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v14[16]; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp+27h] BYREF
  unsigned int v16; // [rsp+B0h] [rbp+67h] BYREF
  unsigned __int16 *v17; // [rsp+C8h] [rbp+7Fh] BYREF

  Buf1 = 0;
  v17 = 0;
  v16 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsService::OnDiskLayoutChange(2)");
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( a1 && a3 )
  {
    v6 = 0;
    for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
          ;
          CRtlListIter::Next((CRtlListIter *)&Buf1) )
    {
      Buf2 = *(GUID *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v15);
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        break;
      v11 = 0;
      EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
      if ( EntryPointer )
      {
        v8 = (**EntryPointer)(EntryPointer, &IID_IVdsOwnershipChangeQuery, &v11);
        v6 = v8;
        if ( v8 >= 0 )
        {
          Buf2 = GUID_NULL;
          v9 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned __int16 *, struct _DRIVE_LAYOUT_INFORMATION_EX *))(*(_QWORD *)v11 + 24LL))(
                 v11,
                 &Buf2,
                 a1,
                 a3);
          v6 = v9;
          if ( !v9 )
          {
            Buf2 = *a2;
            CVdsService::RemoveRawDisk(&Buf2, 9u);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
            goto LABEL_20;
          }
          if ( v9 < 0 )
            VdsTraceW(0, L"CVdsService::OnDiskLayoutChange(2), 2, name=%s, hr=%lX", a1, (unsigned int)v9);
        }
        else
        {
          VdsLogError(0xC2000009, 0, 0, v8, 0x2000045u, 0);
          VdsTraceW(0, L"CVdsService::OnDiskLayoutChange(2), 1b, hr=%1X", v6);
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsService::OnDiskLayoutChange(2), 1a");
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
    }
    Buf2 = *a2;
    RawDisk = CVdsService::FindRawDisk(&Buf2, &v17, &v16);
    if ( RawDisk )
    {
      *((_DWORD *)RawDisk + 85) = 1;
      *((_DWORD *)RawDisk + 34) = 0;
    }
    else
    {
      VdsTraceW(0, L"CVdsService::OnDiskLayoutChange(2), 3, name=%s, hr=%lX", a1, v6);
    }
  }
  else
  {
    if ( !a1 )
      a1 = L"UNKNOWN";
    VdsTraceW(0, L"CVdsService::OnDiskLayoutChange(2), 1, name=%s, Layout=%p", a1, a3);
  }
LABEL_20:
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
}

```

## disassembly

```asm
0x14001b6f0  mov     [rsp-8+arg_8], rbx
0x14001b6f5  mov     [rsp-8+arg_10], rsi
0x14001b6fa  push    rbp
0x14001b6fb  push    rdi
0x14001b6fc  push    r14
0x14001b6fe  lea     rbp, [rsp-47h]
0x14001b703  sub     rsp, 90h
0x14001b70a  mov     rsi, r8
0x14001b70d  mov     r14, rdx
0x14001b710  mov     rbx, rcx
0x14001b713  xorps   xmm0, xmm0
0x14001b716  movups  [rbp+57h+Buf1], xmm0
0x14001b71a  mov     [rbp+57h+arg_18], 0
0x14001b722  mov     [rbp+57h+arg_0], 0
0x14001b729  lea     r8, aCvdsserviceOnd_12; "CVdsService::OnDiskLayoutChange(2)"
0x14001b730  mov     edx, 5Eh ; '^'
0x14001b735  lea     rcx, [rbp+57h+var_40]
0x14001b739  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001b73f  nop
0x14001b740  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001b747  call    cs:__imp_EnterCriticalSection
0x14001b74d  nop
0x14001b74e  test    rbx, rbx
0x14001b751  jz      loc_14001B8FB
0x14001b757  test    rsi, rsi
0x14001b75a  jz      loc_14001B8FB
0x14001b760  xor     edi, edi
0x14001b762  lea     rdx, [rbp+57h+Buf2]
0x14001b766  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14001b76d  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14001b773  movups  xmm0, xmmword ptr [rax]
0x14001b776  movdqu  [rbp+57h+Buf1], xmm0
0x14001b77b  lea     rdx, [rbp+57h+var_30]
0x14001b77f  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14001b786  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14001b78c  movups  xmm0, xmmword ptr [rax]
0x14001b78f  movdqu  [rbp+57h+Buf2], xmm0
0x14001b794  mov     r8d, 10h; Size
0x14001b79a  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14001b79e  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14001b7a2  call    memcmp_0
0x14001b7a7  test    eax, eax
0x14001b7a9  jz      loc_14001B8AF
0x14001b7af  mov     [rbp+57h+var_70], 0
0x14001b7b7  lea     rcx, [rbp+57h+Buf1]
0x14001b7bb  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14001b7c1  mov     rcx, rax
0x14001b7c4  test    rax, rax
0x14001b7c7  jnz     short loc_14001B7DC
0x14001b7c9  lea     rdx, aCvdsserviceOnd_0; "CVdsService::OnDiskLayoutChange(2), 1a"
0x14001b7d0  call    cs:__imp_VdsTraceW
0x14001b7d6  nop
0x14001b7d7  jmp     loc_14001B874
0x14001b7dc  mov     rax, [rax]
0x14001b7df  lea     r8, [rbp+57h+var_70]
0x14001b7e3  lea     rdx, IID_IVdsOwnershipChangeQuery
0x14001b7ea  mov     rax, [rax]
0x14001b7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b7f2  mov     edi, eax
0x14001b7f4  test    eax, eax
0x14001b7f6  jns     short loc_14001B830
0x14001b7f8  mov     [rsp+0A0h+var_78], 0; unsigned __int16 *
0x14001b801  mov     [rsp+0A0h+var_80], 2000045h; unsigned int
0x14001b809  mov     r9d, eax; unsigned int
0x14001b80c  xor     r8d, r8d; void *
0x14001b80f  xor     edx, edx; unsigned int
0x14001b811  mov     ecx, 0C2000009h; unsigned int
0x14001b816  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001b81b  mov     r8d, edi
0x14001b81e  lea     rdx, aCvdsserviceOnd_9; "CVdsService::OnDiskLayoutChange(2), 1b,"...
0x14001b825  xor     ecx, ecx
0x14001b827  call    cs:__imp_VdsTraceW
0x14001b82d  nop
0x14001b82e  jmp     short loc_14001B874
0x14001b830  mov     rcx, [rbp+57h+var_70]
0x14001b834  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001b83b  movdqu  [rbp+57h+Buf2], xmm0
0x14001b840  mov     rax, [rcx]
0x14001b843  mov     r9, rsi
0x14001b846  mov     r8, rbx
0x14001b849  lea     rdx, [rbp+57h+Buf2]
0x14001b84d  mov     rax, [rax+18h]
0x14001b851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b856  mov     edi, eax
0x14001b858  test    eax, eax
0x14001b85a  jz      short loc_14001B88C
0x14001b85c  jns     short loc_14001B874
0x14001b85e  mov     r9d, eax
0x14001b861  mov     r8, rbx
0x14001b864  lea     rdx, aCvdsserviceOnd_6; "CVdsService::OnDiskLayoutChange(2), 2, "...
0x14001b86b  xor     ecx, ecx
0x14001b86d  call    cs:__imp_VdsTraceW
0x14001b873  nop
0x14001b874  lea     rcx, [rbp+57h+var_70]
0x14001b878  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b87d  lea     rcx, [rbp+57h+Buf1]
0x14001b881  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14001b887  jmp     loc_14001B77B
0x14001b88c  movups  xmm0, xmmword ptr [r14]
0x14001b890  movdqu  [rbp+57h+Buf2], xmm0
0x14001b895  mov     edx, 9; unsigned int
0x14001b89a  lea     rcx, [rbp+57h+Buf2]; struct _GUID
0x14001b89e  call    ?RemoveRawDisk@CVdsService@@SAHU_GUID@@K@Z; CVdsService::RemoveRawDisk(_GUID,ulong)
0x14001b8a3  nop
0x14001b8a4  lea     rcx, [rbp+57h+var_70]
0x14001b8a8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001b8ad  jmp     short loc_14001B91F
0x14001b8af  movups  xmm0, xmmword ptr [r14]
0x14001b8b3  movdqu  [rbp+57h+Buf2], xmm0
0x14001b8b8  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x14001b8bc  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x14001b8c0  lea     rcx, [rbp+57h+Buf2]; struct _GUID
0x14001b8c4  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@U_GUID@@AEAPEAGAEAK@Z; CVdsService::FindRawDisk(_GUID,ushort * &,ulong &)
0x14001b8c9  test    rax, rax
0x14001b8cc  jnz     short loc_14001B8E5
0x14001b8ce  mov     r9d, edi
0x14001b8d1  mov     r8, rbx
0x14001b8d4  lea     rdx, aCvdsserviceOnd_5; "CVdsService::OnDiskLayoutChange(2), 3, "...
0x14001b8db  xor     ecx, ecx
0x14001b8dd  call    cs:__imp_VdsTraceW
0x14001b8e3  jmp     short loc_14001B91F
0x14001b8e5  mov     dword ptr [rax+154h], 1
0x14001b8ef  mov     dword ptr [rax+88h], 0
0x14001b8f9  jmp     short loc_14001B91F
0x14001b8fb  lea     rax, aUnknown_0; "UNKNOWN"
0x14001b902  test    rbx, rbx
0x14001b905  cmovz   rbx, rax
0x14001b909  mov     r9, rsi
0x14001b90c  mov     r8, rbx
0x14001b90f  lea     rdx, aCvdsserviceOnd_11; "CVdsService::OnDiskLayoutChange(2), 1, "...
0x14001b916  xor     ecx, ecx
0x14001b918  call    cs:__imp_VdsTraceW
0x14001b91e  nop
0x14001b91f  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001b926  call    cs:__imp_LeaveCriticalSection
0x14001b92c  nop
0x14001b92d  lea     rcx, [rbp+57h+var_40]
0x14001b931  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001b937  lea     r11, [rsp+0A0h+var_10]
0x14001b93f  mov     rbx, [r11+28h]
0x14001b943  mov     rsi, [r11+30h]
0x14001b947  mov     rsp, r11
0x14001b94a  pop     r14
0x14001b94c  pop     rdi
0x14001b94d  pop     rbp
0x14001b94e  retn
```
