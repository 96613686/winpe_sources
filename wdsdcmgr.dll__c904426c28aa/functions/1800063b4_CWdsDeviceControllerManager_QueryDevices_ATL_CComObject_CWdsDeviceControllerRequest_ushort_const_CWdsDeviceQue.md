# CWdsDeviceControllerManager::QueryDevices(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,CWdsDeviceQuery *,CDynArray<ushort *,CDeallocateString> *,ulong,ulong)

- ea: `0x1800063b4`
- end: `0x1800068b0`
- name: `?QueryDevices@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBGPEAUCWdsDeviceQuery@@PEAV?$CDynArray@PEAGVCDeallocateString@@@@KK@Z`
- size: `1276`
- prototype: `__int64 __fastcall(CWdsDeviceControllerManager *this, CWdsDeviceControllerRequest *, unsigned __int16 *, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x1800013d0`
- `0x1800063b4`
- `0x1800068b8`
- `0x180006ab0`
- `0x180007310`
- `0x18000e194`
- `0x1800134f4`
- `0x18001381c`
- `0x180013dcc`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x180015cc0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000656d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000683c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000656d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000683c`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::QueryDevices(
        CWdsDeviceControllerManager *this,
        CWdsDeviceControllerRequest *a2,
        unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  void *v8; // r14
  __int64 v12; // r12
  int ManagementEntry; // ebx
  const char *v14; // rdx
  struct CWdsDeviceControllerManager::CManagementEntry *v15; // rdi
  unsigned int v16; // r15d
  const char *v17; // rdx
  int v18; // ecx
  int v19; // ecx
  int v20; // edi
  const char *v21; // rdx
  const char *v22; // rdx
  const char *v23; // rdx
  int v24; // edi
  const char *v25; // rdx
  int Instance; // edi
  const char *v27; // rdx
  const char *v28; // rdx
  int v29; // eax
  const char *v30; // rdx
  unsigned int v31; // r9d
  const char *v32; // rdx
  unsigned int v33; // edi
  int v34; // esi
  const char *v35; // rdx
  const char *v36; // rdx
  const char *v37; // rdx
  unsigned int v38; // eax
  const char *v39; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  __int64 v42; // [rsp+38h] [rbp-48h] BYREF
  struct CWdsDeviceControllerManager::CManagementEntry *v43; // [rsp+40h] [rbp-40h] BYREF
  __int64 v44; // [rsp+48h] [rbp-38h]
  void *Block; // [rsp+50h] [rbp-30h] BYREF
  CMRSWLock *v46; // [rsp+58h] [rbp-28h] BYREF
  int v47; // [rsp+60h] [rbp-20h]
  CMRSWLock *v48; // [rsp+68h] [rbp-18h] BYREF
  int v49; // [rsp+70h] [rbp-10h]
  unsigned int v50; // [rsp+B0h] [rbp+30h] BYREF

  v8 = 0;
  v48 = (CWdsDeviceControllerManager *)((char *)this + 40);
  v49 = 0;
  CAutoReaderLock::Lock((CAutoReaderLock *)&v48);
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v12 = 0;
  v50 = 0;
  bstrString = 0;
  Block = 0;
  ManagementEntry = CWdsDeviceControllerManager::GetManagementEntry(this, a3, &v43);
  if ( ElValidateWin32(
         ManagementEntry,
         v14,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0xAFBu) )
  {
    goto LABEL_63;
  }
  v15 = v43;
  v16 = a6;
  v47 = 0;
  v46 = (CMRSWLock *)(*((_QWORD *)v43 + 1) + 24LL);
  CAutoReaderLock::Lock((CAutoReaderLock *)&v46);
  if ( a4 )
    v18 = *(_DWORD *)(a4 + 80);
  else
    v18 = 0;
  if ( !v18 )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, __int64 *))(**(_QWORD **)v15 + 56LL))(
            *(_QWORD *)v15,
            a2,
            &v42);
    if ( (int)ElValidateHr(v20, v32, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB08u) < 0 )
      goto LABEL_12;
    v29 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
    v31 = 2827;
LABEL_34:
    v20 = v29;
    if ( (int)ElValidateHr(v29, v30, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", v31) >= 0 )
      goto LABEL_19;
LABEL_12:
    if ( v20 >= 0 || (ManagementEntry = (unsigned __int16)v20, (v20 & 0x1FFF0000) != 0x70000) )
      ManagementEntry = v20;
    goto LABEL_9;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
    Instance = CWdsComMetadata::CreateInstance((struct CWdsMetadata *)(a4 + 8));
    if ( (int)ElValidateHr(
                Instance,
                v27,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0xB20u) < 0 )
    {
      if ( Instance >= 0 || (ManagementEntry = (unsigned __int16)Instance, (Instance & 0x1FFF0000) != 0x70000) )
        ManagementEntry = Instance;
      if ( v47 == 1 )
        CMRSWLock::ReaderRelease(v46);
      v12 = v44;
      goto LABEL_63;
    }
    v12 = v44;
    v20 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, __int64, __int64 *))(**(_QWORD **)v43 + 64LL))(
            *(_QWORD *)v43,
            a2,
            v44,
            &v42);
    if ( (int)ElValidateHr(v20, v28, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB25u) < 0 )
      goto LABEL_12;
    v29 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
    v31 = 2856;
    goto LABEL_34;
  }
  if ( v19 != 1 )
  {
    ManagementEntry = 87;
    if ( ElValidateWin32(0x57u, v17, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB2Du) )
    {
LABEL_9:
      if ( v47 == 1 )
        CMRSWLock::ReaderRelease(v46);
      goto LABEL_63;
    }
    goto LABEL_19;
  }
  v20 = SysAllocStringHr(*(const unsigned __int16 **)a4, &bstrString);
  if ( (int)ElValidateHr(v20, v21, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB10u) < 0 )
    goto LABEL_12;
  v20 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, __int64 *))(**(_QWORD **)v43 + 72LL))(
          *(_QWORD *)v43,
          a2,
          bstrString,
          &v42);
  if ( (int)ElValidateHr(v20, v22, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB15u) < 0 )
    goto LABEL_12;
  v20 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
  if ( (int)ElValidateHr(v20, v23, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB18u) < 0 )
    goto LABEL_12;
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
LABEL_19:
  if ( v47 == 1 )
    CMRSWLock::ReaderRelease(v46);
  v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 24LL))(v42, &v50);
  if ( (int)ElValidateHr(v24, v25, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0xB32u) >= 0 )
  {
    v33 = a7;
    if ( a7 <= v50 )
    {
      if ( a7 == v50 )
      {
        ManagementEntry = 0;
      }
      else
      {
        if ( v16 + a7 > v50 )
          v16 = v50 - a7;
        v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 40LL))(v42, a7);
        if ( (int)ElValidateHr(
                    v34,
                    v35,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    0xB46u) >= 0 )
        {
          while ( v33 < v16 )
          {
            ManagementEntry = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v42 + 48LL))(v42, &bstrString);
            if ( (int)ElValidateHr(
                        ManagementEntry,
                        v36,
                        "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                        0xB4Du) < 0 )
            {
              if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
              {
                ManagementEntry = (unsigned __int16)ManagementEntry;
                break;
              }
LABEL_61:
              if ( v8 )
                operator delete(v8);
              break;
            }
            ManagementEntry = DuplicateStringW(bstrString, (unsigned __int16 **)&Block);
            v38 = ElValidateWin32(
                    ManagementEntry,
                    v37,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    0xB50u);
            v8 = Block;
            if ( v38 )
              goto LABEL_61;
            ManagementEntry = CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(a5, Block);
            if ( ElValidateWin32(
                   ManagementEntry,
                   v39,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0xB53u) )
            {
              goto LABEL_61;
            }
            v8 = 0;
            Block = 0;
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            ++v33;
          }
        }
        else if ( v34 < 0 && (v34 & 0x1FFF0000) == 0x70000 )
        {
          ManagementEntry = (unsigned __int16)v34;
        }
        else
        {
          ManagementEntry = v34;
        }
      }
    }
    else
    {
      ManagementEntry = 87;
    }
  }
  else if ( v24 < 0 && (v24 & 0x1FFF0000) == 0x70000 )
  {
    ManagementEntry = (unsigned __int16)v24;
  }
  else
  {
    ManagementEntry = v24;
  }
LABEL_63:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v49 == 1 )
    CMRSWLock::ReaderRelease(v48);
  return (unsigned int)ManagementEntry;
}

```

## disassembly

```asm
0x1800063b4  mov     [rsp-28h+arg_8], rbx
0x1800063b9  mov     [rsp-28h+arg_10], rsi
0x1800063be  mov     [rsp-28h+arg_18], rdi
0x1800063c3  push    rbp
0x1800063c4  push    r12
0x1800063c6  push    r13
0x1800063c8  push    r14
0x1800063ca  push    r15
0x1800063cc  mov     rbp, rsp
0x1800063cf  sub     rsp, 80h
0x1800063d6  lea     rax, [rcx+28h]
0x1800063da  mov     rbx, rcx
0x1800063dd  xor     r14d, r14d
0x1800063e0  mov     [rbp+var_18], rax
0x1800063e4  lea     rcx, [rbp+var_18]; this
0x1800063e8  mov     [rbp+var_10], r14d
0x1800063ec  mov     rsi, r9
0x1800063ef  mov     rdi, r8
0x1800063f2  mov     r13, rdx
0x1800063f5  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x1800063fa  lea     r8, [rbp+var_40]; struct CWdsDeviceControllerManager::CManagementEntry **
0x1800063fe  mov     [rbp+var_48], r14
0x180006402  mov     rdx, rdi; unsigned __int16 *
0x180006405  mov     [rbp+var_40], r14
0x180006409  mov     rcx, rbx; this
0x18000640c  mov     [rbp+var_38], r14
0x180006410  mov     r12d, r14d
0x180006413  mov     [rbp+arg_0], r14d
0x180006417  mov     [rbp+bstrString], r14
0x18000641b  mov     [rbp+Block], r14
0x18000641f  call    ?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z; CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)
0x180006424  mov     r9d, 0AFBh; unsigned int
0x18000642a  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006431  mov     ecx, eax; unsigned int
0x180006433  mov     ebx, eax
0x180006435  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000643a  test    eax, eax
0x18000643c  jnz     loc_180006833
0x180006442  mov     rdi, [rbp+var_40]
0x180006446  mov     r15d, [rbp+arg_28]
0x18000644a  and     [rbp+var_20], r12d
0x18000644e  mov     rcx, [rdi+8]
0x180006452  add     rcx, 18h
0x180006456  mov     [rbp+var_28], rcx
0x18000645a  lea     rcx, [rbp+var_28]; this
0x18000645e  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x180006463  test    rsi, rsi
0x180006466  jz      short loc_18000646D
0x180006468  mov     ecx, [rsi+50h]
0x18000646b  jmp     short loc_18000646F
0x18000646d  xor     ecx, ecx
0x18000646f  mov     eax, 57h ; 'W'
0x180006474  test    ecx, ecx
0x180006476  jz      loc_1800066A3
0x18000647c  sub     ecx, 1
0x18000647f  jz      loc_1800065DF
0x180006485  cmp     ecx, 1
0x180006488  jz      short loc_1800064CD
0x18000648a  lea     rsi, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006491  mov     r9d, 0B2Dh; unsigned int
0x180006497  mov     r8, rsi; char *
0x18000649a  mov     ecx, eax; unsigned int
0x18000649c  mov     ebx, eax
0x18000649e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800064a3  test    eax, eax
0x1800064a5  jz      loc_180006577
0x1800064ab  mov     eax, [rbp+var_20]
0x1800064ae  test    eax, eax
0x1800064b0  jz      loc_180006833
0x1800064b6  cmp     eax, 1
0x1800064b9  jnz     loc_180006833
0x1800064bf  mov     rcx, [rbp+var_28]; this
0x1800064c3  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x1800064c8  jmp     loc_180006833
0x1800064cd  mov     rcx, [rsi]; unsigned __int16 *
0x1800064d0  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x1800064d4  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800064d9  lea     rsi, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800064e0  mov     r9d, 0B10h; unsigned int
0x1800064e6  mov     r8, rsi; char *
0x1800064e9  mov     ecx, eax; int
0x1800064eb  mov     edi, eax
0x1800064ed  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800064f2  test    eax, eax
0x1800064f4  jns     short loc_180006511
0x1800064f6  test    edi, edi
0x1800064f8  jns     short loc_18000650D
0x1800064fa  mov     ecx, edi
0x1800064fc  movzx   ebx, di
0x1800064ff  and     ecx, 1FFF0000h
0x180006505  cmp     ecx, 70000h
0x18000650b  jz      short loc_1800064AB
0x18000650d  mov     ebx, edi
0x18000650f  jmp     short loc_1800064AB
0x180006511  mov     rcx, [rbp+var_40]
0x180006515  lea     r9, [rbp+var_48]
0x180006519  mov     r8, [rbp+bstrString]
0x18000651d  mov     rdx, r13
0x180006520  mov     rcx, [rcx]
0x180006523  mov     rax, [rcx]
0x180006526  mov     rax, [rax+48h]
0x18000652a  call    cs:__guard_dispatch_icall_fptr
0x180006530  mov     r9d, 0B15h; unsigned int
0x180006536  mov     r8, rsi; char *
0x180006539  mov     ecx, eax; int
0x18000653b  mov     edi, eax
0x18000653d  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006542  test    eax, eax
0x180006544  js      short loc_1800064F6
0x180006546  mov     rcx, r13; this
0x180006549  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x18000654e  mov     r9d, 0B18h; unsigned int
0x180006554  mov     r8, rsi; char *
0x180006557  mov     ecx, eax; int
0x180006559  mov     edi, eax
0x18000655b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006560  test    eax, eax
0x180006562  js      short loc_1800064F6
0x180006564  mov     rcx, [rbp+bstrString]; bstrString
0x180006568  test    rcx, rcx
0x18000656b  jz      short loc_180006577
0x18000656d  call    cs:__imp_SysFreeString
0x180006573  and     [rbp+bstrString], r12
0x180006577  mov     eax, [rbp+var_20]
0x18000657a  test    eax, eax
0x18000657c  jz      short loc_18000658C
0x18000657e  cmp     eax, 1
0x180006581  jnz     short loc_18000658C
0x180006583  mov     rcx, [rbp+var_28]; this
0x180006587  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000658c  mov     rcx, [rbp+var_48]
0x180006590  lea     rdx, [rbp+arg_0]
0x180006594  mov     rax, [rcx]
0x180006597  mov     rax, [rax+18h]
0x18000659b  call    cs:__guard_dispatch_icall_fptr
0x1800065a1  mov     r9d, 0B32h; unsigned int
0x1800065a7  mov     r8, rsi; char *
0x1800065aa  mov     ecx, eax; int
0x1800065ac  mov     edi, eax
0x1800065ae  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800065b3  test    eax, eax
0x1800065b5  jns     loc_1800066F2
0x1800065bb  test    edi, edi
0x1800065bd  jns     loc_1800066EB
0x1800065c3  mov     ecx, edi
0x1800065c5  and     ecx, 1FFF0000h
0x1800065cb  cmp     ecx, 70000h
0x1800065d1  jnz     loc_1800066EB
0x1800065d7  movzx   ebx, di
0x1800065da  jmp     loc_180006833
0x1800065df  lea     rcx, [rsi+8]; struct CWdsMetadata *
0x1800065e3  lea     rdx, [rbp+var_38]
0x1800065e7  call    ?CreateInstance@CWdsComMetadata@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadata@@@ATL@@@Z; CWdsComMetadata::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadata> * *)
0x1800065ec  lea     rsi, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800065f3  mov     r9d, 0B20h; unsigned int
0x1800065f9  mov     r8, rsi; char *
0x1800065fc  mov     ecx, eax; int
0x1800065fe  mov     edi, eax
0x180006600  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006605  test    eax, eax
0x180006607  jns     short loc_180006640
0x180006609  test    edi, edi
0x18000660b  jns     short loc_180006620
0x18000660d  mov     ecx, edi
0x18000660f  movzx   ebx, di
0x180006612  and     ecx, 1FFF0000h
0x180006618  cmp     ecx, 70000h
0x18000661e  jz      short loc_180006622
0x180006620  mov     ebx, edi
0x180006622  mov     eax, [rbp+var_20]
0x180006625  test    eax, eax
0x180006627  jz      short loc_180006637
0x180006629  cmp     eax, 1
0x18000662c  jnz     short loc_180006637
0x18000662e  mov     rcx, [rbp+var_28]; this
0x180006632  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006637  mov     r12, [rbp+var_38]
0x18000663b  jmp     loc_180006833
0x180006640  mov     rcx, [rbp+var_40]
0x180006644  lea     r9, [rbp+var_48]
0x180006648  mov     r12, [rbp+var_38]
0x18000664c  mov     rdx, r13
0x18000664f  mov     r8, r12
0x180006652  mov     rcx, [rcx]
0x180006655  mov     rax, [rcx]
0x180006658  mov     rax, [rax+40h]
0x18000665c  call    cs:__guard_dispatch_icall_fptr
0x180006662  mov     r9d, 0B25h; unsigned int
0x180006668  mov     r8, rsi; char *
0x18000666b  mov     ecx, eax; int
0x18000666d  mov     edi, eax
0x18000666f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006674  test    eax, eax
0x180006676  js      loc_1800064F6
0x18000667c  mov     rcx, r13; this
0x18000667f  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180006684  mov     r9d, 0B28h; unsigned int
0x18000668a  mov     r8, rsi; char *
0x18000668d  mov     ecx, eax; int
0x18000668f  mov     edi, eax
0x180006691  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006696  test    eax, eax
0x180006698  jns     loc_180006577
0x18000669e  jmp     loc_1800064F6
0x1800066a3  mov     rcx, [rdi]
0x1800066a6  lea     r8, [rbp+var_48]
0x1800066aa  mov     rdx, r13
0x1800066ad  mov     rax, [rcx]
0x1800066b0  mov     rax, [rax+38h]
0x1800066b4  call    cs:__guard_dispatch_icall_fptr
0x1800066ba  lea     rsi, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800066c1  mov     r9d, 0B08h; unsigned int
0x1800066c7  mov     r8, rsi; char *
0x1800066ca  mov     ecx, eax; int
0x1800066cc  mov     edi, eax
0x1800066ce  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800066d3  test    eax, eax
0x1800066d5  js      loc_1800064F6
0x1800066db  mov     rcx, r13; this
0x1800066de  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x1800066e3  mov     r9d, 0B0Bh
0x1800066e9  jmp     short loc_18000668A
0x1800066eb  mov     ebx, edi
0x1800066ed  jmp     loc_180006833
0x1800066f2  mov     edi, [rbp+arg_30]
0x1800066f5  mov     ecx, [rbp+arg_0]
0x1800066f8  cmp     edi, ecx
0x1800066fa  jbe     short loc_180006706
0x1800066fc  mov     ebx, 57h ; 'W'
0x180006701  jmp     loc_180006833
0x180006706  jnz     short loc_18000670F
0x180006708  xor     ebx, ebx
0x18000670a  jmp     loc_180006833
0x18000670f  lea     eax, [r15+rdi]
0x180006713  cmp     eax, ecx
0x180006715  jbe     short loc_18000671D
0x180006717  mov     r15d, ecx
0x18000671a  sub     r15d, edi
0x18000671d  mov     rcx, [rbp+var_48]
0x180006721  mov     edx, edi
0x180006723  mov     rax, [rcx]
0x180006726  mov     rax, [rax+28h]
0x18000672a  call    cs:__guard_dispatch_icall_fptr
0x180006730  lea     r13, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006737  mov     r9d, 0B46h; unsigned int
0x18000673d  mov     r8, r13; char *
0x180006740  mov     ecx, eax; int
0x180006742  mov     esi, eax
0x180006744  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006749  test    eax, eax
0x18000674b  jns     loc_180006804
0x180006751  test    esi, esi
0x180006753  jns     short loc_18000676D
0x180006755  mov     ecx, esi
0x180006757  and     ecx, 1FFF0000h
0x18000675d  cmp     ecx, 70000h
0x180006763  jnz     short loc_18000676D
0x180006765  movzx   ebx, si
0x180006768  jmp     loc_180006833
0x18000676d  mov     ebx, esi
0x18000676f  jmp     loc_180006833
0x180006774  mov     rcx, [rbp+var_48]
0x180006778  lea     rdx, [rbp+bstrString]
0x18000677c  mov     rax, [rcx]
0x18000677f  mov     rax, [rax+30h]
0x180006783  call    cs:__guard_dispatch_icall_fptr
0x180006789  mov     r9d, 0B4Dh; unsigned int
0x18000678f  mov     r8, r13; char *
0x180006792  mov     ecx, eax; int
0x180006794  mov     ebx, eax
0x180006796  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000679b  test    eax, eax
0x18000679d  js      short loc_18000680F
0x18000679f  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x1800067a3  lea     rdx, [rbp+Block]; unsigned __int16 **
0x1800067a7  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800067ac  mov     r9d, 0B50h; unsigned int
0x1800067b2  mov     r8, r13; char *
0x1800067b5  mov     ecx, eax; unsigned int
0x1800067b7  mov     ebx, eax
0x1800067b9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800067be  mov     r14, [rbp+Block]
0x1800067c2  test    eax, eax
0x1800067c4  jnz     short loc_180006826
0x1800067c6  mov     rcx, [rbp+arg_20]
0x1800067ca  mov     rdx, r14
0x1800067cd  call    ?AddItem@?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocateNone@@@@QEAAKPEAUCQueryEntry@CWdsDeviceControllerManager@@@Z; CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(CWdsDeviceControllerManager::CQueryEntry *)
0x1800067d2  mov     r9d, 0B53h; unsigned int
0x1800067d8  mov     r8, r13; char *
0x1800067db  mov     ecx, eax; unsigned int
0x1800067dd  mov     ebx, eax
0x1800067df  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800067e4  test    eax, eax
0x1800067e6  jnz     short loc_180006826
0x1800067e8  mov     rcx, [rbp+bstrString]; bstrString
0x1800067ec  xor     r14d, r14d
0x1800067ef  mov     [rbp+Block], r14
0x1800067f3  test    rcx, rcx
0x1800067f6  jz      short loc_180006802
0x1800067f8  call    cs:__imp_SysFreeString
  ... truncated ...
```
