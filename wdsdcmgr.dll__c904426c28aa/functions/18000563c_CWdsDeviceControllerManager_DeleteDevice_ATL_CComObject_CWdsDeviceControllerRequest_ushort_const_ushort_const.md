# CWdsDeviceControllerManager::DeleteDevice(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,ushort const *)

- ea: `0x18000563c`
- end: `0x18000580f`
- name: `?DeleteDevice@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBG1@Z`
- size: `467`
- prototype: `__int64 __fastcall(CWdsDeviceControllerManager *this, CWdsDeviceControllerRequest *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x1800013d0`
- `0x180004f98`
- `0x18000563c`
- `0x1800068b8`
- `0x180007310`
- `0x180013314`
- `0x1800133ec`
- `0x1800134f4`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `WDSSRV!WdsPerfCounterAdd` at `0x1800057bd`
- `WDSSRV!WdsPerfCounterAdd` at `0x1800057bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057d6`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::DeleteDevice(
        CWdsDeviceControllerManager *this,
        CWdsDeviceControllerRequest *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned int ManagementEntry; // esi
  const char *v9; // rdx
  int v10; // ebx
  const char *v11; // rdx
  struct CWdsDeviceControllerManager::CManagementEntry *v12; // rdi
  __int64 v13; // rbx
  int v14; // ebp
  CWdsDeviceControllerManager *v15; // rcx
  const char *v16; // rdx
  const char *v17; // rdx
  struct CWdsDeviceControllerManager::CManagementEntry *v19; // [rsp+40h] [rbp-38h] BYREF
  CMRSWLock *v20; // [rsp+48h] [rbp-30h] BYREF
  int v21; // [rsp+50h] [rbp-28h]
  BSTR bstrString; // [rsp+80h] [rbp+8h] BYREF

  v20 = (CWdsDeviceControllerManager *)((char *)this + 40);
  v21 = 0;
  CAutoReaderLock::Lock((CAutoReaderLock *)&v20);
  v19 = 0;
  bstrString = 0;
  ManagementEntry = CWdsDeviceControllerManager::GetManagementEntry(this, a3, &v19);
  if ( ElValidateWin32(
         ManagementEntry,
         v9,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0x902u) )
  {
    goto LABEL_16;
  }
  v10 = SysAllocStringHr(a4, &bstrString);
  if ( (int)ElValidateHr(v10, v11, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x905u) < 0 )
  {
LABEL_3:
    if ( v10 < 0 && (v10 & 0x1FFF0000) == 0x70000 )
      ManagementEntry = (unsigned __int16)v10;
    else
      ManagementEntry = v10;
    goto LABEL_14;
  }
  v12 = v19;
  v13 = *((_QWORD *)v19 + 1);
  CMRSWLock::WriterLock((LPCRITICAL_SECTION)(v13 + 24));
  v14 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR))(**(_QWORD **)v12 + 32LL))(
          *(_QWORD *)v12,
          a2,
          bstrString);
  CMRSWLock::WriterRelease((CMRSWLock *)(v13 + 24));
  CWdsDeviceControllerManager::LogDeviceManagement(
    v15,
    5u,
    *(const unsigned __int16 **)(*((_QWORD *)v12 + 1) + 8LL),
    a4,
    0,
    0,
    v14);
  if ( (int)ElValidateHr(v14, v16, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x914u) >= 0 )
  {
    v10 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
    if ( (int)ElValidateHr(v10, v17, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x917u) >= 0 )
    {
      WdsPerfCounterAdd(56);
      goto LABEL_14;
    }
    goto LABEL_3;
  }
  if ( v14 < 0 && (v14 & 0x1FFF0000) == 0x70000 )
    ManagementEntry = (unsigned __int16)v14;
  else
    ManagementEntry = v14;
LABEL_14:
  if ( bstrString )
    SysFreeString(bstrString);
LABEL_16:
  if ( v21 == 1 )
    CMRSWLock::ReaderRelease(v20);
  return ManagementEntry;
}

```

## disassembly

```asm
0x18000563c  mov     r11, rsp
0x18000563f  mov     [r11+10h], rbx
0x180005643  mov     [r11+18h], rbp
0x180005647  mov     [r11+20h], rsi
0x18000564b  push    rdi
0x18000564c  push    r12
0x18000564e  push    r15
0x180005650  sub     rsp, 60h
0x180005654  lea     rax, [rcx+28h]
0x180005658  mov     rbx, rcx
0x18000565b  mov     [r11-30h], rax
0x18000565f  lea     rcx, [r11-30h]; this
0x180005663  and     [rsp+78h+var_28], 0
0x180005668  mov     r12, r9
0x18000566b  mov     rdi, r8
0x18000566e  mov     r15, rdx
0x180005671  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x180005676  and     [rsp+78h+var_38], 0
0x18000567c  lea     r8, [rsp+78h+var_38]; struct CWdsDeviceControllerManager::CManagementEntry **
0x180005681  and     [rsp+78h+bstrString], 0
0x18000568a  mov     rdx, rdi; unsigned __int16 *
0x18000568d  mov     rcx, rbx; this
0x180005690  call    ?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z; CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)
0x180005695  mov     r9d, 902h; unsigned int
0x18000569b  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800056a2  mov     ecx, eax; unsigned int
0x1800056a4  mov     esi, eax
0x1800056a6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800056ab  test    eax, eax
0x1800056ad  jnz     loc_1800057DC
0x1800056b3  lea     rdx, [rsp+78h+bstrString]; unsigned __int16 **
0x1800056bb  mov     rcx, r12; unsigned __int16 *
0x1800056be  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800056c3  mov     r9d, 905h; unsigned int
0x1800056c9  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800056d0  mov     ecx, eax; int
0x1800056d2  mov     ebx, eax
0x1800056d4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800056d9  test    eax, eax
0x1800056db  jns     short loc_180005700
0x1800056dd  test    ebx, ebx
0x1800056df  jns     short loc_1800056F9
0x1800056e1  mov     ecx, ebx
0x1800056e3  and     ecx, 1FFF0000h
0x1800056e9  cmp     ecx, 70000h
0x1800056ef  jnz     short loc_1800056F9
0x1800056f1  movzx   esi, bx
0x1800056f4  jmp     loc_1800057C3
0x1800056f9  mov     esi, ebx
0x1800056fb  jmp     loc_1800057C3
0x180005700  mov     rdi, [rsp+78h+var_38]
0x180005705  mov     rbx, [rdi+8]
0x180005709  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000570d  call    ?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x180005712  mov     rcx, [rdi]
0x180005715  mov     rdx, r15
0x180005718  mov     r8, [rsp+78h+bstrString]
0x180005720  mov     rax, [rcx]
0x180005723  mov     rax, [rax+20h]
0x180005727  call    cs:__guard_dispatch_icall_fptr
0x18000572d  lea     rcx, [rbx+18h]; this
0x180005731  mov     ebp, eax
0x180005733  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005738  mov     r8, [rdi+8]
0x18000573c  mov     r9, r12; unsigned __int16 *
0x18000573f  mov     [rsp+78h+var_48], ebp; int
0x180005743  mov     edx, 5; unsigned int
0x180005748  and     [rsp+78h+var_50], 0
0x18000574d  and     [rsp+78h+var_58], 0
0x180005753  mov     r8, [r8+8]; unsigned __int16 *
0x180005757  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x18000575c  mov     r9d, 914h; unsigned int
0x180005762  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005769  mov     ecx, ebp; int
0x18000576b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005770  test    eax, eax
0x180005772  jns     short loc_18000578F
0x180005774  test    ebp, ebp
0x180005776  jns     short loc_18000578B
0x180005778  mov     eax, ebp
0x18000577a  and     eax, 1FFF0000h
0x18000577f  cmp     eax, 70000h
0x180005784  jnz     short loc_18000578B
0x180005786  movzx   esi, bp
0x180005789  jmp     short loc_1800057C3
0x18000578b  mov     esi, ebp
0x18000578d  jmp     short loc_1800057C3
0x18000578f  mov     rcx, r15; this
0x180005792  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180005797  mov     r9d, 917h; unsigned int
0x18000579d  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800057a4  mov     ecx, eax; int
0x1800057a6  mov     ebx, eax
0x1800057a8  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800057ad  test    eax, eax
0x1800057af  js      loc_1800056DD
0x1800057b5  mov     edx, 1
0x1800057ba  lea     ecx, [rdx+37h]
0x1800057bd  call    cs:__imp_WdsPerfCounterAdd
0x1800057c3  cmp     [rsp+78h+bstrString], 0
0x1800057cc  jz      short loc_1800057DC
0x1800057ce  mov     rcx, [rsp+78h+bstrString]; bstrString
0x1800057d6  call    cs:__imp_SysFreeString
0x1800057dc  mov     eax, [rsp+78h+var_28]
0x1800057e0  test    eax, eax
0x1800057e2  jz      short loc_1800057F3
0x1800057e4  cmp     eax, 1
0x1800057e7  jnz     short loc_1800057F3
0x1800057e9  mov     rcx, [rsp+78h+var_30]; this
0x1800057ee  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x1800057f3  lea     r11, [rsp+78h+var_18]
0x1800057f8  mov     eax, esi
0x1800057fa  mov     rbx, [r11+28h]
0x1800057fe  mov     rbp, [r11+30h]
0x180005802  mov     rsi, [r11+38h]
0x180005806  mov     rsp, r11
0x180005809  pop     r15
0x18000580b  pop     r12
0x18000580d  pop     rdi
0x18000580e  retn
```
