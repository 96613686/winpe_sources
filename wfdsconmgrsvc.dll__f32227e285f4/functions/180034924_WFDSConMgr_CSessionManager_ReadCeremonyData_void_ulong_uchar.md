# WFDSConMgr::CSessionManager::ReadCeremonyData(void *,ulong *,uchar * *)

- ea: `0x180034924`
- end: `0x180034ace`
- name: `?ReadCeremonyData@CSessionManager@WFDSConMgr@@QEAAXPEAXPEAKPEAPEAE@Z`
- size: `426`
- prototype: `void __fastcall(WFDSConMgr::CSessionManager *__hidden this, void *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c9d4`

## callees

- `0x18000475c`
- `0x180004c7c`
- `0x180006740`
- `0x180009ff4`
- `0x180032038`
- `0x180033428`
- `0x180034924`
- `0x180039e78`
- `0x1800411c8`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180034a8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180034a8b`

## string_xrefs

- `0x180034aa3`: `Missing required parameter to read ceremony data`
- `0x1800349e3`: `WFDSConMgr::CSessionManager::ReadCeremonyData`
- `0x180034abc`: `WFDSConMgr::CSessionManager::ReadCeremonyData`
- `0x1800349ca`: `Can't read ceremony data with unassociated handle`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CSessionManager::ReadCeremonyData(
        RTL_SRWLOCK *this,
        void *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  struct WFDSConMgr::CPairContext *Context; // rax
  RTL_SRWLOCK *CeremonyManager; // rax
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // [rsp+30h] [rbp-38h] BYREF
  WFDSConMgr::CRemoteDevice *v12; // [rsp+38h] [rbp-30h] BYREF
  std::_Ref_count_base *v13; // [rsp+40h] [rbp-28h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-20h] BYREF
  char v15; // [rsp+50h] [rbp-18h]
  unsigned int v16; // [rsp+B0h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this);
  }
  if ( !a3 || !a4 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CSessionManager::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      130,
      L"Missing required parameter to read ceremony data",
      this);
  *a3 = 0;
  *a4 = 0;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    this + 2);
  Context = WFDSConMgr::CSessionManager::GetContext((WFDSConMgr::CSessionManager *)this, a2);
  WFDSConMgr::CPairContext::GetRemoteDevice(Context, &v12);
  if ( !v12 )
    WFDSConMgr::CException::Throw(
      6,
      "WFDSConMgr::CSessionManager::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      143,
      L"Can't read ceremony data with unassociated handle",
      this);
  v16 = 0;
  v11 = 0;
  CeremonyManager = (RTL_SRWLOCK *)WFDSConMgr::CRemoteDevice::GetCeremonyManager(v12);
  WFDSConMgr::CCeremonyManager::ReadCeremonyData(CeremonyManager, 1, &v16, (void **)&v11);
  *a3 = v16;
  v10 = v11;
  v11 = 0;
  *a4 = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this);
  }
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>((void **)&v11);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  if ( v15 )
  {
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
  }
}

```

## disassembly

```asm
0x180034924  push    rbp
0x180034926  push    rbx
0x180034927  push    rsi
0x180034928  push    rdi
0x180034929  push    r12
0x18003492b  push    r14
0x18003492d  mov     rbp, rsp
0x180034930  sub     rsp, 68h
0x180034934  mov     rdi, r9
0x180034937  mov     rsi, r8
0x18003493a  mov     r14, rdx
0x18003493d  mov     rbx, rcx
0x180034940  lea     r12, WPP_GLOBAL_Control
0x180034947  mov     rcx, cs:WPP_GLOBAL_Control
0x18003494e  cmp     rcx, r12
0x180034951  jz      short loc_180034977
0x180034953  cmp     byte ptr [rcx+19h], 4
0x180034957  jb      short loc_180034977
0x180034959  test    byte ptr [rcx+1Ch], 1
0x18003495d  jz      short loc_180034977
0x18003495f  mov     edx, 1Bh
0x180034964  mov     r9, rbx
0x180034967  lea     r8, WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids
0x18003496e  mov     rcx, [rcx+10h]
0x180034972  call    WPP_SF_q
0x180034977  test    rsi, rsi
0x18003497a  jz      loc_180034A9E
0x180034980  test    rdi, rdi
0x180034983  jz      loc_180034A9E
0x180034989  mov     dword ptr [rsi], 0
0x18003498f  mov     qword ptr [rdi], 0
0x180034996  lea     rdx, [rbx+10h]
0x18003499a  lea     rcx, [rbp+SRWLock]
0x18003499e  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x1800349a3  nop
0x1800349a4  mov     rdx, r14; void *
0x1800349a7  mov     rcx, rbx; this
0x1800349aa  call    ?GetContext@CSessionManager@WFDSConMgr@@AEBAPEAVCPairContext@2@PEAX@Z; WFDSConMgr::CSessionManager::GetContext(void *)
0x1800349af  lea     rdx, [rbp+var_30]
0x1800349b3  mov     rcx, rax
0x1800349b6  call    ?GetRemoteDevice@CPairContext@WFDSConMgr@@QEAA?AV?$shared_ptr@VCRemoteDevice@WFDSConMgr@@@std@@XZ; WFDSConMgr::CPairContext::GetRemoteDevice(void)
0x1800349bb  nop
0x1800349bc  mov     rcx, [rbp+var_30]; this
0x1800349c0  test    rcx, rcx
0x1800349c3  jnz     short loc_1800349F5
0x1800349c5  mov     [rsp+68h+var_40], rbx; void *
0x1800349ca  lea     rax, aCanTReadCeremo; "Can't read ceremony data with unassocia"...
0x1800349d1  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800349d6  mov     r9d, 28Fh; char
0x1800349dc  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800349e3  lea     rdx, aWfdsconmgrCses_21; "WFDSConMgr::CSessionManager::ReadCeremo"...
0x1800349ea  mov     ecx, 80070006h; char
0x1800349ef  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800349f5  mov     [rbp+arg_10], 0
0x1800349fc  mov     [rbp+var_38], 0
0x180034a04  call    ?GetCeremonyManager@CRemoteDevice@WFDSConMgr@@QEAAAEAVCCeremonyManager@2@XZ; WFDSConMgr::CRemoteDevice::GetCeremonyManager(void)
0x180034a09  lea     r9, [rbp+var_38]
0x180034a0d  lea     r8, [rbp+arg_10]
0x180034a11  mov     edx, 1
0x180034a16  mov     rcx, rax; void *
0x180034a19  call    ?ReadCeremonyData@CCeremonyManager@WFDSConMgr@@QEAAXW4Source@12@PEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z; WFDSConMgr::CCeremonyManager::ReadCeremonyData(WFDSConMgr::CCeremonyManager::Source,ulong *,std::unique_ptr<uchar [0]> &)
0x180034a1e  mov     eax, [rbp+arg_10]
0x180034a21  mov     [rsi], eax
0x180034a23  mov     rax, [rbp+var_38]
0x180034a27  mov     [rbp+var_38], 0
0x180034a2f  mov     [rdi], rax
0x180034a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a39  cmp     rcx, r12
0x180034a3c  jz      short loc_180034A63
0x180034a3e  cmp     byte ptr [rcx+19h], 4
0x180034a42  jb      short loc_180034A63
0x180034a44  test    byte ptr [rcx+1Ch], 1
0x180034a48  jz      short loc_180034A63
0x180034a4a  mov     edx, 1Ch
0x180034a4f  mov     r9, rbx
0x180034a52  lea     r8, WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids
0x180034a59  mov     rcx, [rcx+10h]
0x180034a5d  call    WPP_SF_q
0x180034a62  nop
0x180034a63  lea     rcx, [rbp+var_38]
0x180034a67  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x180034a6c  nop
0x180034a6d  mov     rcx, [rbp+var_28]; this
0x180034a71  test    rcx, rcx
0x180034a74  jz      short loc_180034A7C
0x180034a76  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034a7b  nop
0x180034a7c  cmp     [rbp+var_18], 0
0x180034a80  jz      short loc_180034A91
0x180034a82  mov     rcx, [rbp+SRWLock]; SRWLock
0x180034a86  test    rcx, rcx
0x180034a89  jz      short loc_180034A91
0x180034a8b  call    cs:__imp_ReleaseSRWLockShared
0x180034a91  add     rsp, 68h
0x180034a95  pop     r14
0x180034a97  pop     r12
0x180034a99  pop     rdi
0x180034a9a  pop     rsi
0x180034a9b  pop     rbx
0x180034a9c  pop     rbp
0x180034a9d  retn
0x180034a9e  mov     [rsp+68h+var_40], rbx; void *
0x180034aa3  lea     rax, aMissingRequire_1; "Missing required parameter to read cere"...
0x180034aaa  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180034aaf  mov     r9d, 282h; char
0x180034ab5  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180034abc  lea     rdx, aWfdsconmgrCses_21; "WFDSConMgr::CSessionManager::ReadCeremo"...
0x180034ac3  mov     ecx, 80070057h; char
0x180034ac8  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
