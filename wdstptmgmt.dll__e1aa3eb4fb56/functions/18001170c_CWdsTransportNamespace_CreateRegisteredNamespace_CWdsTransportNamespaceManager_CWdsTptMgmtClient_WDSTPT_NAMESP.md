# CWdsTransportNamespace::CreateRegisteredNamespace(CWdsTransportNamespaceManager *,CWdsTptMgmtClient *,_WDSTPT_NAMESPACE *,IWdsTransportNamespace * *)

- ea: `0x18001170c`
- end: `0x18001186c`
- name: `?CreateRegisteredNamespace@CWdsTransportNamespace@@SAJPEAVCWdsTransportNamespaceManager@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_NAMESPACE@@PEAPEAUIWdsTransportNamespace@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct CWdsTransportNamespaceManager *, struct CWdsTptMgmtClient *, struct _WDSTPT_NAMESPACE *, struct IWdsTransportNamespace **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800105e0`
- `0x180010710`

## callees

- `0x180011448`
- `0x18001170c`
- `0x180011c44`
- `0x180011f2c`
- `0x1800137c4`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001174c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011844`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001174c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011844`

## string_xrefs

- `0x18001172d`: `-> CWdsTransportNamespace::CreateRegisteredNamespace`
- `0x180011831`: `<- CWdsTransportNamespace::CreateRegisteredNamespace=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::CreateRegisteredNamespace(
        struct CWdsTransportNamespaceManager *a1,
        struct CWdsTptMgmtClient *a2,
        struct _WDSTPT_NAMESPACE *a3,
        struct IWdsTransportNamespace **a4)
{
  CWdsTransportNamespace *v7; // rbx
  __int64 NamespaceTypeFromServerData; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  struct CWdsTransportNamespace *v18; // [rsp+20h] [rbp-28h] BYREF
  __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003 v19; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  v19 = WdsTptNamespaceTypeUnknown;
  v18 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::CreateRegisteredNamespace");
  if ( a1 && a2 && a3 && a4 )
  {
    NamespaceTypeFromServerData = (unsigned int)CWdsTransportNamespace::GetNamespaceTypeFromServerData(a3, &v19);
    if ( (int)ElValidateHr_7(NamespaceTypeFromServerData, v10, v11, 284) < 0 )
      goto LABEL_12;
    NamespaceTypeFromServerData = (unsigned int)CWdsTransportNamespace::CreateNamespace(v19, &v18);
    v14 = ElValidateHr_7(NamespaceTypeFromServerData, v12, v13, 291);
    v7 = v18;
    if ( v14 >= 0 )
    {
      (*(void (__fastcall **)(struct CWdsTransportNamespace *))(*(_QWORD *)v18 + 8LL))(v18);
      NamespaceTypeFromServerData = (unsigned int)CWdsTransportNamespace::InitializeRegisteredNamespace(v7, a1, a2, a3);
      if ( (int)ElValidateHr_7(NamespaceTypeFromServerData, v15, v16, 301) >= 0 )
        LODWORD(NamespaceTypeFromServerData) = (**(__int64 (__fastcall ***)(CWdsTransportNamespace *, GUID *, struct IWdsTransportNamespace **))v7)(
                                                 v7,
                                                 &IID_IWdsTransportNamespace,
                                                 a4);
    }
  }
  else
  {
    LODWORD(NamespaceTypeFromServerData) = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(CWdsTransportNamespace *))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_12:
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespace::CreateRegisteredNamespace=%x",
    (unsigned int)NamespaceTypeFromServerData);
  return (unsigned int)NamespaceTypeFromServerData;
}

```

## disassembly

```asm
0x18001170c  mov     rax, rsp
0x18001170f  mov     [rax+10h], rbx
0x180011713  mov     [rax+18h], rbp
0x180011717  mov     [rax+20h], rsi
0x18001171b  push    rdi
0x18001171c  push    r14
0x18001171e  push    r15
0x180011720  sub     rsp, 30h
0x180011724  mov     rsi, r8
0x180011727  mov     r14, rdx
0x18001172a  mov     r15, rcx
0x18001172d  lea     r8, aCwdstransportn_22; "-> CWdsTransportNamespace::CreateRegist"...
0x180011734  xor     ebx, ebx
0x180011736  lea     rcx, qword_18003B770
0x18001173d  and     [rax+8], ebx
0x180011740  mov     edx, 10000h
0x180011745  mov     [rax-28h], rbx
0x180011749  mov     rbp, r9
0x18001174c  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180011753  nop     dword ptr [rax+rax+00h]
0x180011758  test    r15, r15
0x18001175b  jz      loc_180011815
0x180011761  test    r14, r14
0x180011764  jz      loc_180011815
0x18001176a  test    rsi, rsi
0x18001176d  jz      loc_180011815
0x180011773  test    rbp, rbp
0x180011776  jz      loc_180011815
0x18001177c  lea     rdx, [rsp+48h+arg_0]; enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003 *
0x180011781  mov     rcx, rsi; struct _WDSTPT_NAMESPACE *
0x180011784  call    ?GetNamespaceTypeFromServerData@CWdsTransportNamespace@@SAJPEAU_WDSTPT_NAMESPACE@@PEAW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@@Z; CWdsTransportNamespace::GetNamespaceTypeFromServerData(_WDSTPT_NAMESPACE *,__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003 *)
0x180011789  mov     r9d, 11Ch
0x18001178f  mov     ecx, eax
0x180011791  mov     edi, eax
0x180011793  call    ElValidateHr_7
0x180011798  test    eax, eax
0x18001179a  js      loc_18001182E
0x1800117a0  mov     ecx, [rsp+48h+arg_0]; enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003
0x1800117a4  lea     rdx, [rsp+48h+var_28]; struct CWdsTransportNamespace **
0x1800117a9  call    ?CreateNamespace@CWdsTransportNamespace@@CAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@PEAPEAV1@@Z; CWdsTransportNamespace::CreateNamespace(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003,CWdsTransportNamespace * *)
0x1800117ae  mov     r9d, 123h
0x1800117b4  mov     ecx, eax
0x1800117b6  mov     edi, eax
0x1800117b8  call    ElValidateHr_7
0x1800117bd  mov     rbx, [rsp+48h+var_28]
0x1800117c2  test    eax, eax
0x1800117c4  js      short loc_18001181A
0x1800117c6  mov     rax, [rbx]
0x1800117c9  mov     rcx, rbx
0x1800117cc  mov     rax, [rax+8]
0x1800117d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117d5  mov     r9, rsi; struct _WDSTPT_NAMESPACE *
0x1800117d8  mov     r8, r14; struct CWdsTptMgmtClient *
0x1800117db  mov     rdx, r15; struct CWdsTransportNamespaceManager *
0x1800117de  mov     rcx, rbx; this
0x1800117e1  call    ?InitializeRegisteredNamespace@CWdsTransportNamespace@@AEAAJPEAVCWdsTransportNamespaceManager@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_NAMESPACE@@@Z; CWdsTransportNamespace::InitializeRegisteredNamespace(CWdsTransportNamespaceManager *,CWdsTptMgmtClient *,_WDSTPT_NAMESPACE *)
0x1800117e6  mov     r9d, 12Dh
0x1800117ec  mov     ecx, eax
0x1800117ee  mov     edi, eax
0x1800117f0  call    ElValidateHr_7
0x1800117f5  test    eax, eax
0x1800117f7  js      short loc_18001181A
0x1800117f9  mov     rax, [rbx]
0x1800117fc  lea     rdx, IID_IWdsTransportNamespace
0x180011803  mov     r8, rbp
0x180011806  mov     rcx, rbx
0x180011809  mov     rax, [rax]
0x18001180c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011811  mov     edi, eax
0x180011813  jmp     short loc_18001181A
0x180011815  mov     edi, 80070057h
0x18001181a  test    rbx, rbx
0x18001181d  jz      short loc_18001182E
0x18001181f  mov     rax, [rbx]
0x180011822  mov     rcx, rbx
0x180011825  mov     rax, [rax+10h]
0x180011829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001182e  mov     r9d, edi
0x180011831  lea     r8, aCwdstransportn_63; "<- CWdsTransportNamespace::CreateRegist"...
0x180011838  mov     edx, 10000h
0x18001183d  lea     rcx, qword_18003B770
0x180011844  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001184b  nop     dword ptr [rax+rax+00h]
0x180011850  mov     rbx, [rsp+48h+arg_8]
0x180011855  mov     eax, edi
0x180011857  mov     rbp, [rsp+48h+arg_10]
0x18001185c  mov     rsi, [rsp+48h+arg_18]
0x180011861  add     rsp, 30h
0x180011865  pop     r15
0x180011867  pop     r14
0x180011869  pop     rdi
0x18001186a  retn
```
