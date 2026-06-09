# CWdsTransportNamespaceManager::CreateNamespace(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003,ushort *,ushort *,ushort *,IWdsTransportNamespace * *)

- ea: `0x180010160`
- end: `0x180010284`
- name: `?CreateNamespace@CWdsTransportNamespaceManager@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@PEAG11PEAPEAUIWdsTransportNamespace@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceManager *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct IWdsTransportNamespace **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000aa34`
- `0x180010160`
- `0x180010984`
- `0x18001157c`
- `0x180012c84`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800101ac`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001024c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800101ac`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001024c`

## string_xrefs

- `0x180010199`: `-> CWdsTransportNamespaceManager::CreateNamespace(0x%p)`
- `0x180010239`: `<- CWdsTransportNamespaceManager::CreateNamespace(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceManager::CreateNamespace(
        CWdsTransportNamespaceManager *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWdsTransportNamespace **a6)
{
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int16 *v16; // [rsp+20h] [rbp-48h]
  _BYTE v17[16]; // [rsp+40h] [rbp-28h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v17, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespaceManager::CreateNamespace(0x%p)", this);
  if ( a5 && a6 )
  {
    v10 = (unsigned int)CWdsTransportNamespace::ValidateNamespaceName(a3);
    if ( (int)ElValidateHr_6(v10, v11, v12, 319) >= 0 )
    {
      v10 = (unsigned int)CWdsTransportSetupManager::ValidateContentProviderName(a4);
      if ( (int)ElValidateHr_6(v10, v13, v14, 325) >= 0 )
        LODWORD(v10) = CWdsTransportNamespace::CreateNewNamespace(
                         this,
                         *((struct CWdsTptMgmtClient **)this + 15),
                         a2,
                         a3,
                         a4,
                         a5,
                         a6);
    }
  }
  else
  {
    LODWORD(v10) = -2147024809;
  }
  LODWORD(v16) = v10;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceManager::CreateNamespace(0x%p) =%x",
    this,
    v16);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010160  mov     rax, rsp
0x180010163  mov     [rax+8], rbx
0x180010167  mov     [rax+10h], rbp
0x18001016b  mov     [rax+18h], rsi
0x18001016f  mov     [rax+20h], rdi
0x180010173  push    r12
0x180010175  push    r14
0x180010177  push    r15
0x180010179  sub     rsp, 50h
0x18001017d  mov     r12d, edx
0x180010180  mov     rdi, rcx
0x180010183  lea     rdx, [rcx+50h]
0x180010187  mov     rbp, r9
0x18001018a  lea     rcx, [rax-28h]
0x18001018e  mov     r14, r8
0x180010191  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180010196  mov     r9, rdi
0x180010199  lea     r8, aCwdstransportn_70; "-> CWdsTransportNamespaceManager::Creat"...
0x1800101a0  mov     edx, 10000h
0x1800101a5  lea     rcx, qword_18003B770
0x1800101ac  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800101b3  nop     dword ptr [rax+rax+00h]
0x1800101b8  mov     r15, [rsp+68h+arg_20]
0x1800101c0  test    r15, r15
0x1800101c3  jz      short loc_18001022D
0x1800101c5  mov     rsi, [rsp+68h+arg_28]
0x1800101cd  test    rsi, rsi
0x1800101d0  jz      short loc_18001022D
0x1800101d2  mov     rcx, r14; unsigned __int16 *
0x1800101d5  call    ?ValidateNamespaceName@CWdsTransportNamespace@@SAJPEAG@Z; CWdsTransportNamespace::ValidateNamespaceName(ushort *)
0x1800101da  mov     r9d, 13Fh
0x1800101e0  mov     ecx, eax
0x1800101e2  mov     ebx, eax
0x1800101e4  call    ElValidateHr_6
0x1800101e9  test    eax, eax
0x1800101eb  js      short loc_180010232
0x1800101ed  mov     rcx, rbp; unsigned __int16 *
0x1800101f0  call    ?ValidateContentProviderName@CWdsTransportSetupManager@@SAJPEAG@Z; CWdsTransportSetupManager::ValidateContentProviderName(ushort *)
0x1800101f5  mov     r9d, 145h
0x1800101fb  mov     ecx, eax
0x1800101fd  mov     ebx, eax
0x1800101ff  call    ElValidateHr_6
0x180010204  test    eax, eax
0x180010206  js      short loc_180010232
0x180010208  mov     rdx, [rdi+78h]; struct CWdsTptMgmtClient *
0x18001020c  mov     r9, r14; unsigned __int16 *
0x18001020f  mov     [rsp+68h+var_38], rsi; struct IWdsTransportNamespace **
0x180010214  mov     r8d, r12d; enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003
0x180010217  mov     [rsp+68h+var_40], r15; unsigned __int16 *
0x18001021c  mov     rcx, rdi; struct CWdsTransportNamespaceManager *
0x18001021f  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180010224  call    ?CreateNewNamespace@CWdsTransportNamespace@@SAJPEAVCWdsTransportNamespaceManager@@PEAVCWdsTptMgmtClient@@W4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@PEAG33PEAPEAUIWdsTransportNamespace@@@Z; CWdsTransportNamespace::CreateNewNamespace(CWdsTransportNamespaceManager *,CWdsTptMgmtClient *,__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003,ushort *,ushort *,ushort *,IWdsTransportNamespace * *)
0x180010229  mov     ebx, eax
0x18001022b  jmp     short loc_180010232
0x18001022d  mov     ebx, 80070057h
0x180010232  mov     r9, rdi
0x180010235  mov     dword ptr [rsp+68h+var_48], ebx
0x180010239  lea     r8, aCwdstransportn_39; "<- CWdsTransportNamespaceManager::Creat"...
0x180010240  mov     edx, 10000h
0x180010245  lea     rcx, qword_18003B770
0x18001024c  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010253  nop     dword ptr [rax+rax+00h]
0x180010258  lea     rcx, [rsp+68h+var_28]
0x18001025d  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180010262  lea     r11, [rsp+68h+var_18]
0x180010267  mov     eax, ebx
0x180010269  mov     rbx, [r11+20h]
0x18001026d  mov     rbp, [r11+28h]
0x180010271  mov     rsi, [r11+30h]
0x180010275  mov     rdi, [r11+38h]
0x180010279  mov     rsp, r11
0x18001027c  pop     r15
0x18001027e  pop     r14
0x180010280  pop     r12
0x180010282  retn
```
