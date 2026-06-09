# CRADCApiWorkspaceManager::GetWorkspaceIDs(tagSAFEARRAY * *)

- ea: `0x1800714a0`
- end: `0x180071818`
- name: `?GetWorkspaceIDs@CRADCApiWorkspaceManager@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `888`
- prototype: `__int64 __fastcall(CRADCApiWorkspaceManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180005500`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000fed8`
- `0x18000ff00`
- `0x18001e7e4`
- `0x18001f320`
- `0x1800294b4`
- `0x1800302a0`
- `0x1800714a0`
- `0x18009a520`

## import_xrefs

- `ole32!StringFromIID` at `0x180071699`
- `ole32!StringFromIID` at `0x180071699`
- `ole32!CoTaskMemFree` at `0x1800716e2`
- `ole32!CoTaskMemFree` at `0x1800717d8`
- `ole32!CoTaskMemFree` at `0x1800716e2`
- `ole32!CoTaskMemFree` at `0x1800717d8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800715fd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800715fd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800717c2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800717c2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800716c9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800716c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRADCApiWorkspaceManager::GetWorkspaceIDs(CRADCApiWorkspaceManager *this, struct tagSAFEARRAY **a2)
{
  CWorkspaceManager *v4; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT ValueAt; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // r14d
  SAFEARRAY *v10; // rsi
  unsigned int v11; // eax
  unsigned int i; // ecx
  _QWORD *v13; // r8
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  LONG rgIndices; // [rsp+38h] [rbp-29h] BYREF
  IID *v19; // [rsp+40h] [rbp-21h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-19h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-11h] BYREF
  _QWORD v22[2]; // [rsp+58h] [rbp-9h] BYREF
  __int64 v23; // [rsp+68h] [rbp+7h]
  int v24; // [rsp+70h] [rbp+Fh]
  _BYTE v25[8]; // [rsp+78h] [rbp+17h] BYREF
  __int64 v26; // [rsp+80h] [rbp+1Fh]
  IID rclsid; // [rsp+88h] [rbp+27h] BYREF

  v26 = -2;
  v22[1] = 0;
  v23 = 0;
  v24 = 0;
  v22[0] = &CTSSimpleComPtrArray<CWorkspace>::`vftable';
  lpsz = 0;
  rclsid = 0;
  v19 = 0;
  v4 = (CWorkspaceManager *)*((_QWORD *)this + 8);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_229912884ca53c71a5c455d6e8d327e0_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147220971);
    }
    ValueAt = -2147220971;
    goto LABEL_44;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 19;
LABEL_12:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_229912884ca53c71a5c455d6e8d327e0_Traceguids, v7, -2147024809);
LABEL_13:
    ValueAt = -2147024809;
    goto LABEL_44;
  }
  CWorkspaceManager::BuildConfiguredWorkspacesList(v4);
  CWorkspaceManager::GetWorkspaces(*((_QWORD *)this + 8), v22);
  v9 = HIDWORD(v23);
  rgsabound.cElements = HIDWORD(v23);
  rgsabound.lLbound = 0;
  v10 = SafeArrayCreate(8u, 1u, &rgsabound);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 20;
    goto LABEL_12;
  }
  v11 = 0;
  for ( i = 0; ; i = rgIndices + 1 )
  {
    rgIndices = v11;
    if ( i >= v9 )
      break;
    if ( v19 )
    {
      TCntPtr<CConfigManager>::SafeRelease(&v19);
      v19 = 0;
      TCntPtr<CConfigManager>::SafeAddRef(&v19);
      v11 = rgIndices;
    }
    ValueAt = CTSSimpleComPtrArray<CWorkspaceFtaAppRegistration>::GetValueAt(v22, v11, &v19);
    if ( ValueAt < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 21;
        v16 = "GetValueAt failed";
LABEL_41:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)WPP_229912884ca53c71a5c455d6e8d327e0_Traceguids,
          v14,
          (__int64)v16,
          ValueAt);
      }
LABEL_42:
      SafeArrayDestroy(v10);
      goto LABEL_44;
    }
    rclsid = v19[3];
    ValueAt = StringFromIID(&rclsid, &lpsz);
    if ( ValueAt < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 22;
        v16 = "StringFromIID failed";
        goto LABEL_41;
      }
      goto LABEL_42;
    }
    v13 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v25, lpsz);
    if ( v13 )
      v13 = (_QWORD *)*v13;
    ValueAt = SafeArrayPutElement(v10, &rgIndices, v13);
    _bstr_t::_Free((_bstr_t *)v25);
    if ( ValueAt < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 23;
        v16 = "SafeArrayPutElement failed";
        goto LABEL_41;
      }
      goto LABEL_42;
    }
    CoTaskMemFree(lpsz);
    lpsz = 0;
    v11 = rgIndices + 1;
  }
  *a2 = v10;
  ValueAt = 0;
LABEL_44:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v19);
  CTSSimpleComPtrArray<CWorkspace>::~CTSSimpleComPtrArray<CWorkspace>(v22);
  return (unsigned int)ValueAt;
}

```

## disassembly

```asm
0x1800714a0  mov     rax, rsp
0x1800714a3  push    rbp
0x1800714a4  push    rdi
0x1800714a5  push    r14
0x1800714a7  lea     rbp, [rax-5Fh]
0x1800714ab  sub     rsp, 0A0h
0x1800714b2  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800714ba  mov     [rax+18h], rbx
0x1800714be  mov     [rax+20h], rsi
0x1800714c2  mov     rax, cs:__security_cookie
0x1800714c9  xor     rax, rsp
0x1800714cc  mov     [rbp+57h+var_20], rax
0x1800714d0  mov     rdi, rdx
0x1800714d3  mov     rbx, rcx
0x1800714d6  lea     rax, ??_7?$CTSSimpleArray@PEAVCWorkspace@@$0BA@@@6B@; const CTSSimpleArray<CWorkspace *,16>::`vftable'
0x1800714dd  mov     [rbp+57h+var_60], rax
0x1800714e1  mov     [rbp+57h+var_58], 0
0x1800714e9  mov     [rbp+57h+var_50], 0
0x1800714f1  mov     [rbp+57h+var_48], 0
0x1800714f8  lea     rax, ??_7?$CTSSimpleComPtrArray@VCWorkspace@@@@6B@; const CTSSimpleComPtrArray<CWorkspace>::`vftable'
0x1800714ff  mov     [rbp+57h+var_60], rax
0x180071503  mov     [rbp+57h+lpsz], 0
0x18007150b  xorps   xmm0, xmm0
0x18007150e  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180071512  mov     [rbp+57h+var_78], 0
0x18007151a  mov     rcx, [rcx+40h]; this
0x18007151e  test    rcx, rcx
0x180071521  jnz     short loc_180071578
0x180071523  lea     rax, WPP_GLOBAL_Control
0x18007152a  mov     rcx, cs:WPP_GLOBAL_Control
0x180071531  cmp     rcx, rax
0x180071534  jz      short loc_18007156E
0x180071536  test    byte ptr [rcx+1Ch], 8
0x18007153a  jz      short loc_18007156E
0x18007153c  cmp     byte ptr [rcx+19h], 2
0x180071540  jb      short loc_18007156E
0x180071542  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180071547  mov     edx, 12h
0x18007154c  mov     [rsp+0B0h+var_90], 80040215h
0x180071554  mov     r9d, eax
0x180071557  lea     r8, WPP_229912884ca53c71a5c455d6e8d327e0_Traceguids
0x18007155e  mov     rcx, cs:WPP_GLOBAL_Control
0x180071565  mov     rcx, [rcx+10h]
0x180071569  call    WPP_SF_Dd
0x18007156e  mov     ebx, 80040215h
0x180071573  jmp     loc_1800717CF
0x180071578  test    rdi, rdi
0x18007157b  jnz     short loc_1800715D0
0x18007157d  lea     rax, WPP_GLOBAL_Control
0x180071584  mov     rcx, cs:WPP_GLOBAL_Control
0x18007158b  cmp     rcx, rax
0x18007158e  jz      short loc_1800715C6
0x180071590  test    byte ptr [rcx+1Ch], 8
0x180071594  jz      short loc_1800715C6
0x180071596  cmp     byte ptr [rcx+19h], 2
0x18007159a  jb      short loc_1800715C6
0x18007159c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800715a1  lea     edx, [rdi+13h]
0x1800715a4  mov     [rsp+0B0h+var_90], 80070057h
0x1800715ac  mov     r9d, eax
0x1800715af  lea     r8, WPP_229912884ca53c71a5c455d6e8d327e0_Traceguids
0x1800715b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800715bd  mov     rcx, [rcx+10h]
0x1800715c1  call    WPP_SF_Dd
0x1800715c6  mov     ebx, 80070057h
0x1800715cb  jmp     loc_1800717CF
0x1800715d0  call    ?BuildConfiguredWorkspacesList@CWorkspaceManager@@IEAAXXZ; CWorkspaceManager::BuildConfiguredWorkspacesList(void)
0x1800715d5  lea     rdx, [rbp+57h+var_60]
0x1800715d9  mov     rcx, [rbx+40h]
0x1800715dd  call    ?GetWorkspaces@CWorkspaceManager@@QEAAXPEAV?$CTSSimpleComPtrArray@VCWorkspace@@@@@Z; CWorkspaceManager::GetWorkspaces(CTSSimpleComPtrArray<CWorkspace> *)
0x1800715e2  mov     r14d, dword ptr [rbp+57h+var_50+4]
0x1800715e6  mov     [rbp+57h+rgsabound.cElements], r14d
0x1800715ea  mov     [rbp+57h+rgsabound.lLbound], 0
0x1800715f1  mov     ecx, 8; vt
0x1800715f6  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800715fa  lea     edx, [rcx-7]; cDims
0x1800715fd  call    cs:__imp_SafeArrayCreate
0x180071603  mov     rsi, rax
0x180071606  test    rax, rax
0x180071609  jnz     short loc_180071637
0x18007160b  lea     rax, WPP_GLOBAL_Control
0x180071612  mov     rcx, cs:WPP_GLOBAL_Control
0x180071619  cmp     rcx, rax
0x18007161c  jz      short loc_1800715C6
0x18007161e  test    byte ptr [rcx+1Ch], 8
0x180071622  jz      short loc_1800715C6
0x180071624  cmp     byte ptr [rcx+19h], 2
0x180071628  jb      short loc_1800715C6
0x18007162a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007162f  lea     edx, [rsi+14h]
0x180071632  jmp     loc_1800715A4
0x180071637  xor     eax, eax
0x180071639  xor     ecx, ecx
0x18007163b  mov     [rbp+57h+rgIndices], eax
0x18007163e  cmp     ecx, r14d
0x180071641  jnb     loc_1800717CA
0x180071647  cmp     [rbp+57h+var_78], 0
0x18007164c  jz      short loc_18007166B
0x18007164e  lea     rcx, [rbp+57h+var_78]
0x180071652  call    ?SafeRelease@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeRelease(void)
0x180071657  mov     [rbp+57h+var_78], 0
0x18007165f  lea     rcx, [rbp+57h+var_78]
0x180071663  call    ?SafeAddRef@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeAddRef(void)
0x180071668  mov     eax, [rbp+57h+rgIndices]
0x18007166b  lea     r8, [rbp+57h+var_78]
0x18007166f  mov     edx, eax
0x180071671  lea     rcx, [rbp+57h+var_60]
0x180071675  call    ?GetValueAt@?$CTSSimpleComPtrArray@VCWorkspaceFtaAppRegistration@@@@UEBAJIPEAPEAVCWorkspaceFtaAppRegistration@@@Z; CTSSimpleComPtrArray<CWorkspaceFtaAppRegistration>::GetValueAt(uint,CWorkspaceFtaAppRegistration * *)
0x18007167a  mov     ebx, eax
0x18007167c  test    eax, eax
0x18007167e  js      loc_18007176C
0x180071684  mov     rax, [rbp+57h+var_78]
0x180071688  movups  xmm0, xmmword ptr [rax+30h]
0x18007168c  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180071691  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180071695  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180071699  call    cs:__imp_StringFromIID
0x18007169f  mov     ebx, eax
0x1800716a1  test    eax, eax
0x1800716a3  js      loc_18007173A
0x1800716a9  mov     rdx, [rbp+57h+lpsz]; unsigned __int16 *
0x1800716ad  lea     rcx, [rbp+57h+var_40]; this
0x1800716b1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800716b6  nop
0x1800716b7  mov     r8, [rax]
0x1800716ba  test    r8, r8
0x1800716bd  jz      short loc_1800716C2
0x1800716bf  mov     r8, [r8]; pv
0x1800716c2  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x1800716c6  mov     rcx, rsi; psa
0x1800716c9  call    cs:__imp_SafeArrayPutElement
0x1800716cf  mov     ebx, eax
0x1800716d1  lea     rcx, [rbp+57h+var_40]; this
0x1800716d5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800716da  test    ebx, ebx
0x1800716dc  js      short loc_1800716FC
0x1800716de  mov     rcx, [rbp+57h+lpsz]; pv
0x1800716e2  call    cs:__imp_CoTaskMemFree
0x1800716e8  mov     [rbp+57h+lpsz], 0
0x1800716f0  mov     eax, [rbp+57h+rgIndices]
0x1800716f3  inc     eax
0x1800716f5  mov     ecx, eax
0x1800716f7  jmp     loc_18007163B
0x1800716fc  lea     rax, WPP_GLOBAL_Control
0x180071703  mov     rcx, cs:WPP_GLOBAL_Control
0x18007170a  cmp     rcx, rax
0x18007170d  jz      loc_1800717BF
0x180071713  test    byte ptr [rcx+1Ch], 8
0x180071717  jz      loc_1800717BF
0x18007171d  cmp     byte ptr [rcx+19h], 2
0x180071721  jb      loc_1800717BF
0x180071727  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007172c  mov     edx, 17h
0x180071731  lea     rcx, aSafearrayputel; "SafeArrayPutElement failed"
0x180071738  jmp     short loc_18007179C
0x18007173a  lea     rax, WPP_GLOBAL_Control
0x180071741  mov     rcx, cs:WPP_GLOBAL_Control
0x180071748  cmp     rcx, rax
0x18007174b  jz      short loc_1800717BF
0x18007174d  test    byte ptr [rcx+1Ch], 8
0x180071751  jz      short loc_1800717BF
0x180071753  cmp     byte ptr [rcx+19h], 2
0x180071757  jb      short loc_1800717BF
0x180071759  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007175e  mov     edx, 16h
0x180071763  lea     rcx, aStringfromiidF; "StringFromIID failed"
0x18007176a  jmp     short loc_18007179C
0x18007176c  lea     rax, WPP_GLOBAL_Control
0x180071773  mov     rcx, cs:WPP_GLOBAL_Control
0x18007177a  cmp     rcx, rax
0x18007177d  jz      short loc_1800717BF
0x18007177f  test    byte ptr [rcx+1Ch], 8
0x180071783  jz      short loc_1800717BF
0x180071785  cmp     byte ptr [rcx+19h], 2
0x180071789  jb      short loc_1800717BF
0x18007178b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180071790  mov     edx, 15h
0x180071795  lea     rcx, aGetvalueatFail; "GetValueAt failed"
0x18007179c  mov     [rsp+0B0h+var_88], ebx
0x1800717a0  mov     qword ptr [rsp+0B0h+var_90], rcx
0x1800717a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717ac  mov     r9d, eax
0x1800717af  lea     r8, WPP_229912884ca53c71a5c455d6e8d327e0_Traceguids
0x1800717b6  mov     rcx, [rcx+10h]
0x1800717ba  call    WPP_SF_DsD
0x1800717bf  mov     rcx, rsi; psa
0x1800717c2  call    cs:__imp_SafeArrayDestroy
0x1800717c8  jmp     short loc_1800717CF
0x1800717ca  mov     [rdi], rsi
0x1800717cd  xor     ebx, ebx
0x1800717cf  mov     rcx, [rbp+57h+lpsz]; pv
0x1800717d3  test    rcx, rcx
0x1800717d6  jz      short loc_1800717DF
0x1800717d8  call    cs:__imp_CoTaskMemFree
0x1800717de  nop
0x1800717df  lea     rcx, [rbp+57h+var_78]
0x1800717e3  call    ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
0x1800717e8  nop
0x1800717e9  lea     rcx, [rbp+57h+var_60]
0x1800717ed  call    ??1?$CTSSimpleComPtrArray@VCWorkspace@@@@UEAA@XZ; CTSSimpleComPtrArray<CWorkspace>::~CTSSimpleComPtrArray<CWorkspace>(void)
0x1800717f2  mov     eax, ebx
0x1800717f4  mov     rcx, [rbp+57h+var_20]
0x1800717f8  xor     rcx, rsp; StackCookie
0x1800717fb  call    __security_check_cookie
0x180071800  lea     r11, [rsp+0B0h+var_10]
0x180071808  mov     rbx, [r11+30h]
0x18007180c  mov     rsi, [r11+38h]
0x180071810  mov     rsp, r11
0x180071813  pop     r14
0x180071815  pop     rdi
0x180071816  pop     rbp
0x180071817  retn
```
