# WFDSConMgr::CWFDConnectHelper::OpenSession(uchar const (&)[6],WFDSConMgr::IWFDDisconnectListener *,bool)

- ea: `0x18002d768`
- end: `0x18002da16`
- name: `?OpenSession@CWFDConnectHelper@WFDSConMgr@@QEAAXAEAY05$$CBEPEAVIWFDDisconnectListener@2@_N@Z`
- size: `686`
- prototype: `void __fastcall(WFDSConMgr::CWFDConnectHelper *__hidden this, const unsigned __int8 (*)[6], struct WFDSConMgr::IWFDDisconnectListener *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18005ad80`
- `0x18005be40`

## callees

- `0x180002600`
- `0x180004c7c`
- `0x180006740`
- `0x180006c60`
- `0x180008a10`
- `0x18002d768`
- `0x18002ddf0`
- `0x18005c888`
- `0x18005ddf4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d826`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d826`

## string_xrefs

- `0x18002d7ea`: `OpenSession was canceled`
- `0x18002d986`: `OpenSession was canceled`
- `0x18002d803`: `WFDSConMgr::CWFDConnectHelper::OpenSession`
- `0x18002d8d1`: `WFDSConMgr::CWFDConnectHelper::OpenSession`
- `0x18002d934`: `WFDSConMgr::CWFDConnectHelper::OpenSession`
- `0x18002d969`: `WFDSConMgr::CWFDConnectHelper::OpenSession`
- `0x18002d99f`: `WFDSConMgr::CWFDConnectHelper::OpenSession`
- `0x18002d8b8`: `Failure in WFDStartOpenSession, bailing out`
- `0x18002d91b`: `Failure in WFDStartOpenSession callback, bailing out`
- `0x18002d950`: `OpenSession should return a session handle, but handle is null`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CWFDConnectHelper::OpenSession(
        WFDSConMgr::CWFDConnectHelper *this,
        const unsigned __int8 (*a2)[6],
        struct WFDSConMgr::IWFDDisconnectListener *a3,
        char a4)
{
  int v8; // eax
  unsigned int v9; // edx
  int v10; // ecx
  _BYTE v11[16]; // [rsp+50h] [rbp-58h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+60h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_50fbb76679da3b44998e93d52156735e_Traceguids, this);
  }
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)SRWLock,
    (RTL_SRWLOCK *)this + 8);
  if ( *((_BYTE *)this + 96) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CWFDConnectHelper::OpenSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\wfdhelper.cpp",
      218,
      L"OpenSession was canceled",
      this);
  if ( LOBYTE(SRWLock[1]) && SRWLock[0] )
    ReleaseSRWLockShared(SRWLock[0]);
  WFDSConMgr::CWFDClientHandle::RegisterDisconnectListener(*((WFDSConMgr::CWFDClientHandle **)this + 4), a3);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v11,
    (RTL_SRWLOCK *)this + 8);
  memset(SRWLock, 0, 12);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int8 *, WFDSConMgr::CWFDConnectHelper *, void (__usercall *)(void *@<rcx>, WFDSConMgr::CWFDConnectHelper *@<rdx>, struct _GUID *__struct_ptr@<r8>, unsigned int@<r9d>, unsigned int), _QWORD, unsigned __int64, char *))(**(_QWORD **)this + 32LL))(
         *(_QWORD *)this,
         *(_QWORD *)(*((_QWORD *)this + 4) + 32LL),
         (const unsigned __int8 *)a2,
         this,
         WFDSConMgr::CWFDConnectHelper::OpenSessionCompleteCallback,
         0,
         (unsigned __int64)SRWLock & -(__int64)(a4 != 0),
         (char *)this + 88);
  if ( v8 )
    WFDSConMgr::CException::Throw(
      v8,
      "WFDSConMgr::CWFDConnectHelper::OpenSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\wfdhelper.cpp",
      241,
      L"Failure in WFDStartOpenSession, bailing out",
      this);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v11);
  WFDSConMgr::CEventWrapper::Wait((WFDSConMgr::CWFDConnectHelper *)((char *)this + 72), v9);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v11,
    (RTL_SRWLOCK *)this + 8);
  v10 = *((_DWORD *)this + 33);
  if ( v10 )
    WFDSConMgr::CException::Throw(
      v10,
      "WFDSConMgr::CWFDConnectHelper::OpenSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\wfdhelper.cpp",
      255,
      L"Failure in WFDStartOpenSession callback, bailing out",
      this);
  if ( !*((_QWORD *)this + 20) )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CWFDConnectHelper::OpenSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\wfdhelper.cpp",
      4,
      L"OpenSession should return a session handle, but handle is null",
      this);
  if ( *((_BYTE *)this + 96) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CWFDConnectHelper::OpenSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\wfdhelper.cpp",
      9,
      L"OpenSession was canceled",
      this);
  *((_QWORD *)this + 11) = 0;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_50fbb76679da3b44998e93d52156735e_Traceguids, this);
  }
}

```

## disassembly

```asm
0x18002d768  mov     [rsp+arg_18], rbx
0x18002d76d  push    rbp
0x18002d76e  push    rsi
0x18002d76f  push    rdi
0x18002d770  push    r12
0x18002d772  push    r14
0x18002d774  sub     rsp, 80h
0x18002d77b  mov     rax, cs:__security_cookie
0x18002d782  xor     rax, rsp
0x18002d785  mov     [rsp+0A8h+var_38], rax
0x18002d78a  mov     bpl, r9b
0x18002d78d  mov     rsi, r8
0x18002d790  mov     r14, rdx
0x18002d793  mov     rbx, rcx
0x18002d796  lea     r12, WPP_GLOBAL_Control
0x18002d79d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7a4  cmp     rcx, r12
0x18002d7a7  jz      short loc_18002D7CD
0x18002d7a9  cmp     byte ptr [rcx+19h], 4
0x18002d7ad  jb      short loc_18002D7CD
0x18002d7af  test    byte ptr [rcx+1Ch], 1
0x18002d7b3  jz      short loc_18002D7CD
0x18002d7b5  mov     edx, 31h ; '1'
0x18002d7ba  mov     r9, rbx
0x18002d7bd  lea     r8, WPP_50fbb76679da3b44998e93d52156735e_Traceguids
0x18002d7c4  mov     rcx, [rcx+10h]
0x18002d7c8  call    WPP_SF_q
0x18002d7cd  lea     rdi, [rbx+40h]
0x18002d7d1  mov     rdx, rdi
0x18002d7d4  lea     rcx, [rsp+0A8h+SRWLock]
0x18002d7d9  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x18002d7de  nop
0x18002d7df  cmp     byte ptr [rbx+60h], 0
0x18002d7e3  jz      short loc_18002D815
0x18002d7e5  mov     [rsp+0A8h+var_80], rbx; void *
0x18002d7ea  lea     rax, aOpensessionWas; "OpenSession was canceled"
0x18002d7f1  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x18002d7f6  mov     r9d, 2DAh; char
0x18002d7fc  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18002d803  lea     rdx, aWfdsconmgrCwfd_18; "WFDSConMgr::CWFDConnectHelper::OpenSess"...
0x18002d80a  mov     ecx, 800704C7h; char
0x18002d80f  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18002d815  cmp     [rsp+0A8h+var_40], 0
0x18002d81a  jz      short loc_18002D82C
0x18002d81c  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18002d821  test    rcx, rcx
0x18002d824  jz      short loc_18002D82C
0x18002d826  call    cs:__imp_ReleaseSRWLockShared
0x18002d82c  mov     rdx, rsi; struct WFDSConMgr::IWFDDisconnectListener *
0x18002d82f  mov     rcx, [rbx+20h]; this
0x18002d833  call    ?RegisterDisconnectListener@CWFDClientHandle@WFDSConMgr@@QEAAXPEAVIWFDDisconnectListener@2@@Z; WFDSConMgr::CWFDClientHandle::RegisterDisconnectListener(WFDSConMgr::IWFDDisconnectListener *)
0x18002d838  mov     rdx, rdi
0x18002d83b  lea     rcx, [rsp+0A8h+var_58]
0x18002d840  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x18002d845  nop
0x18002d846  mov     [rsp+0A8h+SRWLock+4], 0
0x18002d84f  mov     dword ptr [rsp+0A8h+SRWLock], 0
0x18002d857  mov     rcx, [rbx]
0x18002d85a  lea     rsi, [rbx+58h]
0x18002d85e  mov     rax, [rcx]
0x18002d861  neg     bpl
0x18002d864  sbb     r9, r9
0x18002d867  lea     rdx, [rsp+0A8h+SRWLock]
0x18002d86c  and     r9, rdx
0x18002d86f  mov     rdx, [rbx+20h]
0x18002d873  mov     [rsp+0A8h+var_70], rsi
0x18002d878  mov     [rsp+0A8h+var_78], r9
0x18002d87d  mov     [rsp+0A8h+var_80], 0
0x18002d886  lea     r8, ?OpenSessionCompleteCallback@CWFDConnectHelper@WFDSConMgr@@KAXPEAX0U_GUID@@KK@Z; WFDSConMgr::CWFDConnectHelper::OpenSessionCompleteCallback(void *,void *,_GUID,ulong,ulong)
0x18002d88d  mov     [rsp+0A8h+var_88], r8
0x18002d892  mov     r9, rbx
0x18002d895  mov     r8, r14
0x18002d898  mov     rdx, [rdx+20h]
0x18002d89c  mov     rax, [rax+20h]
0x18002d8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8a5  test    eax, eax
0x18002d8a7  jz      short loc_18002D8E0
0x18002d8a9  jle     short loc_18002D8B3
0x18002d8ab  movzx   eax, ax
0x18002d8ae  or      eax, 80070000h
0x18002d8b3  mov     [rsp+0A8h+var_80], rbx; void *
0x18002d8b8  lea     rcx, aFailureInWfdst; "Failure in WFDStartOpenSession, bailing"...
0x18002d8bf  mov     [rsp+0A8h+var_88], rcx; unsigned __int16 *
0x18002d8c4  mov     r9d, 2F1h; char
0x18002d8ca  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18002d8d1  lea     rdx, aWfdsconmgrCwfd_18; "WFDSConMgr::CWFDConnectHelper::OpenSess"...
0x18002d8d8  mov     ecx, eax; char
0x18002d8da  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18002d8e0  lea     rcx, [rsp+0A8h+var_58]
0x18002d8e5  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18002d8ea  lea     rcx, [rbx+48h]; this
0x18002d8ee  call    ?Wait@CEventWrapper@WFDSConMgr@@QEBAXK@Z; WFDSConMgr::CEventWrapper::Wait(ulong)
0x18002d8f3  mov     rdx, rdi
0x18002d8f6  lea     rcx, [rsp+0A8h+var_58]
0x18002d8fb  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x18002d900  nop
0x18002d901  mov     ecx, [rbx+84h]
0x18002d907  test    ecx, ecx
0x18002d909  jz      short loc_18002D941
0x18002d90b  jle     short loc_18002D916
0x18002d90d  movzx   ecx, cx
0x18002d910  or      ecx, 80070000h; char
0x18002d916  mov     [rsp+0A8h+var_80], rbx; void *
0x18002d91b  lea     rax, aFailureInWfdst_0; "Failure in WFDStartOpenSession callback"...
0x18002d922  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x18002d927  mov     r9d, 2FFh; char
0x18002d92d  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18002d934  lea     rdx, aWfdsconmgrCwfd_18; "WFDSConMgr::CWFDConnectHelper::OpenSess"...
0x18002d93b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18002d941  cmp     qword ptr [rbx+0A0h], 0
0x18002d949  jnz     short loc_18002D97B
0x18002d94b  mov     [rsp+0A8h+var_80], rbx; void *
0x18002d950  lea     rax, aOpensessionSho; "OpenSession should return a session han"...
0x18002d957  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x18002d95c  mov     r9d, 304h; char
0x18002d962  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18002d969  lea     rdx, aWfdsconmgrCwfd_18; "WFDSConMgr::CWFDConnectHelper::OpenSess"...
0x18002d970  mov     ecx, 80070057h; char
0x18002d975  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18002d97b  cmp     byte ptr [rbx+60h], 0
0x18002d97f  jz      short loc_18002D9B1
0x18002d981  mov     [rsp+0A8h+var_80], rbx; void *
0x18002d986  lea     rax, aOpensessionWas; "OpenSession was canceled"
0x18002d98d  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x18002d992  mov     r9d, 309h; char
0x18002d998  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18002d99f  lea     rdx, aWfdsconmgrCwfd_18; "WFDSConMgr::CWFDConnectHelper::OpenSess"...
0x18002d9a6  mov     ecx, 800704C7h; char
0x18002d9ab  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18002d9b1  mov     qword ptr [rsi], 0
0x18002d9b8  lea     rcx, [rsp+0A8h+var_58]
0x18002d9bd  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18002d9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9c9  cmp     rcx, r12
0x18002d9cc  jz      short loc_18002D9F2
0x18002d9ce  cmp     byte ptr [rcx+19h], 4
0x18002d9d2  jb      short loc_18002D9F2
0x18002d9d4  test    byte ptr [rcx+1Ch], 1
0x18002d9d8  jz      short loc_18002D9F2
0x18002d9da  mov     edx, 32h ; '2'
0x18002d9df  mov     r9, rbx
0x18002d9e2  lea     r8, WPP_50fbb76679da3b44998e93d52156735e_Traceguids
0x18002d9e9  mov     rcx, [rcx+10h]
0x18002d9ed  call    WPP_SF_q
0x18002d9f2  mov     rcx, [rsp+0A8h+var_38]
0x18002d9f7  xor     rcx, rsp; StackCookie
0x18002d9fa  call    __security_check_cookie
0x18002d9ff  mov     rbx, [rsp+0A8h+arg_18]
0x18002da07  add     rsp, 80h
0x18002da0e  pop     r14
0x18002da10  pop     r12
0x18002da12  pop     rdi
0x18002da13  pop     rsi
0x18002da14  pop     rbp
0x18002da15  retn
```
