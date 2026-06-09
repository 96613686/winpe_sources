# CWdsDeviceControllerManager::AddDevice(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,CWdsMetadata const *,ushort * *)

- ea: `0x180005430`
- end: `0x180005633`
- name: `?AddDevice@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBGPEBVCWdsMetadata@@PEAPEAG@Z`
- size: `515`
- prototype: `__int64 __fastcall(CWdsDeviceControllerManager *this, CWdsDeviceControllerRequest *, unsigned __int16 *, struct CWdsMetadata *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x1800013d0`
- `0x180004f98`
- `0x180005430`
- `0x1800068b8`
- `0x180007310`
- `0x18000e194`
- `0x180013314`
- `0x1800133ec`
- `0x1800134f4`
- `0x180013dcc`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `WDSSRV!WdsPerfCounterAdd` at `0x1800055ae`
- `WDSSRV!WdsPerfCounterAdd` at `0x1800055ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055e3`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::AddDevice(
        CWdsDeviceControllerManager *this,
        CWdsDeviceControllerRequest *a2,
        unsigned __int16 *a3,
        struct CWdsMetadata *a4,
        unsigned __int16 **a5)
{
  int ManagementEntry; // esi
  const char *v10; // rdx
  const char *v11; // rdx
  struct CWdsDeviceControllerManager::CManagementEntry *v12; // rdi
  __int64 v13; // rbx
  CWdsDeviceControllerManager *v14; // rcx
  const unsigned __int16 *v15; // r9
  const char *v16; // rdx
  const char *v17; // rdx
  const unsigned __int16 *v18; // rcx
  const char *v19; // rdx
  struct CWdsDeviceControllerManager::CManagementEntry *v21; // [rsp+48h] [rbp-18h] BYREF
  CMRSWLock *v22; // [rsp+50h] [rbp-10h] BYREF
  int v23; // [rsp+58h] [rbp-8h]
  BSTR bstrString; // [rsp+90h] [rbp+30h] BYREF

  v23 = 0;
  v22 = (CWdsDeviceControllerManager *)((char *)this + 40);
  CAutoReaderLock::Lock((CAutoReaderLock *)&v22);
  v21 = 0;
  bstrString = 0;
  ManagementEntry = CWdsDeviceControllerManager::GetManagementEntry(this, a3, &v21);
  if ( !ElValidateWin32(
          ManagementEntry,
          v10,
          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
          0x8B7u) )
  {
    ManagementEntry = CWdsComMetadata::CreateInstance(a4);
    if ( (int)ElValidateHr(
                ManagementEntry,
                v11,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0x8BBu) >= 0 )
    {
      v12 = v21;
      v13 = *((_QWORD *)v21 + 1);
      CMRSWLock::WriterLock((LPCRITICAL_SECTION)(v13 + 24));
      ManagementEntry = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, _QWORD, BSTR *))(**(_QWORD **)v12 + 24LL))(
                          *(_QWORD *)v12,
                          a2,
                          0,
                          &bstrString);
      CMRSWLock::WriterRelease((CMRSWLock *)(v13 + 24));
      v15 = bstrString;
      if ( !bstrString )
        v15 = &word_18001870C;
      CWdsDeviceControllerManager::LogDeviceManagement(
        v14,
        4u,
        *(const unsigned __int16 **)(*((_QWORD *)v12 + 1) + 8LL),
        v15,
        0,
        0,
        ManagementEntry);
      if ( (int)ElValidateHr(
                  ManagementEntry,
                  v16,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x8CBu) < 0
        || (ManagementEntry = CWdsDeviceControllerRequest::CleanupImpersonation(a2),
            (int)ElValidateHr(
                   ManagementEntry,
                   v17,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0x8CEu) < 0) )
      {
        if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
          ManagementEntry = (unsigned __int16)ManagementEntry;
      }
      else
      {
        WdsPerfCounterAdd(54);
        v18 = bstrString;
        if ( !bstrString )
          v18 = &word_18001870C;
        ManagementEntry = DuplicateStringW(v18, a5);
        ElValidateWin32(
          ManagementEntry,
          v19,
          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
          0x8D5u);
      }
    }
    else if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
    {
      ManagementEntry = (unsigned __int16)ManagementEntry;
    }
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v23 == 1 )
    CMRSWLock::ReaderRelease(v22);
  return (unsigned int)ManagementEntry;
}

```

## disassembly

```asm
0x180005430  mov     [rsp-28h+arg_8], rbx
0x180005435  mov     [rsp-28h+arg_10], rsi
0x18000543a  push    rbp
0x18000543b  push    rdi
0x18000543c  push    r12
0x18000543e  push    r14
0x180005440  push    r15
0x180005442  mov     rbp, rsp
0x180005445  sub     rsp, 60h
0x180005449  and     [rbp+var_8], 0
0x18000544d  lea     rax, [rcx+28h]
0x180005451  mov     rbx, rcx
0x180005454  mov     [rbp+var_10], rax
0x180005458  lea     rcx, [rbp+var_10]; this
0x18000545c  mov     r12, r9
0x18000545f  mov     rdi, r8
0x180005462  mov     r15, rdx
0x180005465  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x18000546a  xor     r14d, r14d
0x18000546d  lea     r8, [rbp+var_18]; struct CWdsDeviceControllerManager::CManagementEntry **
0x180005471  and     [rbp+var_18], r14
0x180005475  mov     rdx, rdi; unsigned __int16 *
0x180005478  and     [rbp+bstrString], r14
0x18000547c  mov     rcx, rbx; this
0x18000547f  mov     [rbp+var_20], r14
0x180005483  call    ?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z; CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)
0x180005488  mov     r9d, 8B7h; unsigned int
0x18000548e  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005495  mov     ecx, eax; unsigned int
0x180005497  mov     esi, eax
0x180005499  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000549e  test    eax, eax
0x1800054a0  jnz     loc_1800055DA
0x1800054a6  lea     rdx, [rbp+var_20]
0x1800054aa  mov     rcx, r12; struct CWdsMetadata *
0x1800054ad  call    ?CreateInstance@CWdsComMetadata@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadata@@@ATL@@@Z; CWdsComMetadata::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadata> * *)
0x1800054b2  mov     r9d, 8BBh; unsigned int
0x1800054b8  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800054bf  mov     ecx, eax; int
0x1800054c1  mov     esi, eax
0x1800054c3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800054c8  test    eax, eax
0x1800054ca  jns     short loc_1800054EA
0x1800054cc  test    esi, esi
0x1800054ce  jns     short loc_1800054E1
0x1800054d0  mov     eax, esi
0x1800054d2  and     eax, 1FFF0000h
0x1800054d7  cmp     eax, 70000h
0x1800054dc  jnz     short loc_1800054E1
0x1800054de  movzx   esi, si
0x1800054e1  mov     r14, [rbp+var_20]
0x1800054e5  jmp     loc_1800055DA
0x1800054ea  mov     rdi, [rbp+var_18]
0x1800054ee  mov     rbx, [rdi+8]
0x1800054f2  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800054f6  call    ?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x1800054fb  mov     rcx, [rdi]
0x1800054fe  lea     r9, [rbp+bstrString]
0x180005502  mov     r14, [rbp+var_20]
0x180005506  mov     rdx, r15
0x180005509  mov     r8, r14
0x18000550c  mov     rax, [rcx]
0x18000550f  mov     rax, [rax+18h]
0x180005513  call    cs:__guard_dispatch_icall_fptr
0x180005519  lea     rcx, [rbx+18h]; this
0x18000551d  mov     esi, eax
0x18000551f  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005524  mov     r9, [rbp+bstrString]
0x180005528  lea     r12, word_18001870C
0x18000552f  mov     r8, [rdi+8]
0x180005533  test    r9, r9
0x180005536  mov     [rsp+60h+var_30], esi; int
0x18000553a  mov     edx, 4; unsigned int
0x18000553f  cmovz   r9, r12; unsigned __int16 *
0x180005543  and     [rsp+60h+var_38], 0
0x180005548  mov     [rsp+60h+var_40], r14; struct CWdsComMetadataBuilder *
0x18000554d  mov     r8, [r8+8]; unsigned __int16 *
0x180005551  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x180005556  lea     rbx, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000555d  mov     r9d, 8CBh; unsigned int
0x180005563  mov     r8, rbx; char *
0x180005566  mov     ecx, esi; int
0x180005568  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000556d  test    eax, eax
0x18000556f  jns     short loc_180005588
0x180005571  test    esi, esi
0x180005573  jns     short loc_1800055DA
0x180005575  mov     eax, esi
0x180005577  and     eax, 1FFF0000h
0x18000557c  cmp     eax, 70000h
0x180005581  jnz     short loc_1800055DA
0x180005583  movzx   esi, si
0x180005586  jmp     short loc_1800055DA
0x180005588  mov     rcx, r15; this
0x18000558b  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180005590  mov     r9d, 8CEh; unsigned int
0x180005596  mov     r8, rbx; char *
0x180005599  mov     ecx, eax; int
0x18000559b  mov     esi, eax
0x18000559d  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800055a2  test    eax, eax
0x1800055a4  js      short loc_180005571
0x1800055a6  mov     edx, 1
0x1800055ab  lea     ecx, [rdx+35h]
0x1800055ae  call    cs:__imp_WdsPerfCounterAdd
0x1800055b4  mov     rcx, [rbp+bstrString]
0x1800055b8  mov     rdx, [rbp+arg_20]; unsigned __int16 **
0x1800055bc  test    rcx, rcx
0x1800055bf  cmovz   rcx, r12; unsigned __int16 *
0x1800055c3  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800055c8  mov     r9d, 8D5h; unsigned int
0x1800055ce  mov     r8, rbx; char *
0x1800055d1  mov     ecx, eax; unsigned int
0x1800055d3  mov     esi, eax
0x1800055d5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800055da  mov     rcx, [rbp+bstrString]; bstrString
0x1800055de  test    rcx, rcx
0x1800055e1  jz      short loc_1800055EE
0x1800055e3  call    cs:__imp_SysFreeString
0x1800055e9  and     [rbp+bstrString], 0
0x1800055ee  test    r14, r14
0x1800055f1  jz      short loc_180005603
0x1800055f3  mov     rax, [r14]
0x1800055f6  mov     rcx, r14
0x1800055f9  mov     rax, [rax+10h]
0x1800055fd  call    cs:__guard_dispatch_icall_fptr
0x180005603  mov     eax, [rbp+var_8]
0x180005606  test    eax, eax
0x180005608  jz      short loc_180005618
0x18000560a  cmp     eax, 1
0x18000560d  jnz     short loc_180005618
0x18000560f  mov     rcx, [rbp+var_10]; this
0x180005613  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180005618  lea     r11, [rsp+60h+var_s0]
0x18000561d  mov     eax, esi
0x18000561f  mov     rbx, [r11+38h]
0x180005623  mov     rsi, [r11+40h]
0x180005627  mov     rsp, r11
0x18000562a  pop     r15
0x18000562c  pop     r14
0x18000562e  pop     r12
0x180005630  pop     rdi
0x180005631  pop     rbp
0x180005632  retn
```
