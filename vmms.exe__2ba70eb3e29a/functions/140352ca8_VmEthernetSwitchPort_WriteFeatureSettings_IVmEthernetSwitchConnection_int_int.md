# VmEthernetSwitchPort::WriteFeatureSettings(IVmEthernetSwitchConnection *,int,int)

- ea: `0x140352ca8`
- end: `0x1403537eb`
- name: `?WriteFeatureSettings@VmEthernetSwitchPort@@AEAAXPEAUIVmEthernetSwitchConnection@@HH@Z`
- size: `2883`
- prototype: `void __fastcall(VmEthernetSwitchPort *__hidden this, struct IVmEthernetSwitchConnection *, int, int)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140352ca8`
- `0x1403eaedc`

## callees

- `0x14001a000`
- `0x140034404`
- `0x14005c630`
- `0x140071534`
- `0x1400720d4`
- `0x140073a48`
- `0x1400a9c24`
- `0x1400a9dc8`
- `0x1400acf04`
- `0x1400e2a70`
- `0x14017902c`
- `0x140188e18`
- `0x140228fa4`
- `0x1402407a4`
- `0x140352ca8`
- `0x1403537f4`
- `0x1403538d8`
- `0x14041f938`
- `0x1404828e0`
- `0x1404835a0`
- `0x1404f2cd0`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140353003`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140353003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140352f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140352fb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1403537b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140352f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140352fb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1403537b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140352e01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140352e01`
- `vmsif!VmsIfPortPropertyRemove` at `0x14035331a`
- `vmsif!VmsIfPortPropertyRemove` at `0x14035331a`
- `vmsif!VmsIfPortPropertyUpdate` at `0x140353548`
- `vmsif!VmsIfPortPropertyUpdate` at `0x140353548`
- `vmsif!VmsIfPortPropertyAdd` at `0x1403536b2`
- `vmsif!VmsIfPortPropertyAdd` at `0x1403536b2`
- `vmsif!VmsIfPortSetRequiredExtensions` at `0x140352f37`
- `vmsif!VmsIfPortSetRequiredExtensions` at `0x140352f37`
- `vmsif!VmsIfPortPropertyQuery` at `0x14035323c`
- `vmsif!VmsIfPortPropertyQuery` at `0x14035343d`
- `vmsif!VmsIfPortPropertyQuery` at `0x14035323c`
- `vmsif!VmsIfPortPropertyQuery` at `0x14035343d`
- `vmsif!VmsIfPortPropertyFree` at `0x1403533b5`
- `vmsif!VmsIfPortPropertyFree` at `0x1403533b5`

## string_xrefs

- `0x14035301e`: `onecore\vm\common\vml\VmCom.h`
- `0x140352e1d`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall VmEthernetSwitchPort::WriteFeatureSettings(
        VmEthernetSwitchPort *this,
        struct IVmEthernetSwitchConnection *a2,
        int a3,
        int a4)
{
  int v4; // r14d
  int v5; // r13d
  struct IVmEthernetSwitchConnection *v6; // r12
  VmEthernetSwitchPort *v7; // r15
  unsigned int v8; // ebx
  struct _VMS_ENUM_PORT_INFO_OUT *v9; // rsi
  _OWORD *v10; // rdi
  const char *v11; // r9
  int v12; // eax
  const char *v13; // r9
  unsigned int v14; // edx
  _OWORD *v15; // rax
  unsigned int v16; // r15d
  char v17; // r12
  unsigned int v18; // esi
  struct _VMS_ENUM_PORT_INFO_OUT *v19; // r13
  __int64 v20; // r14
  struct VmSwitchFeatureInfo *FeatureById; // rbx
  VmEthernetSwitchPort *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  VmEthernetSwitchPort *v25; // rcx
  unsigned int v26; // r8d
  HRESULT Instance; // eax
  int v28; // eax
  unsigned int i; // r14d
  __int64 v30; // rdi
  char *v31; // r9
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  VmEthernetSwitchPort *v35; // rcx
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rcx
  const struct Vml::ExceptionTraceParameters *v39; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-388h]
  struct VmSwitchFeatureInfo *v41; // [rsp+60h] [rbp-348h] BYREF
  int v42; // [rsp+68h] [rbp-340h]
  int v43; // [rsp+6Ch] [rbp-33Ch]
  VmSwitchExtensionRegistrar *v44; // [rsp+70h] [rbp-338h] BYREF
  VmEthernetSwitchPort *v45; // [rsp+78h] [rbp-330h]
  struct _VMS_ENUM_PORT_INFO_OUT *v46; // [rsp+80h] [rbp-328h]
  struct IVmEthernetSwitchConnection *v47; // [rsp+88h] [rbp-320h]
  __int128 v48; // [rsp+90h] [rbp-318h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-308h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-2F8h]
  __int64 v51; // [rsp+C0h] [rbp-2E8h]
  _QWORD v52[4]; // [rsp+C8h] [rbp-2E0h] BYREF
  __int64 v53; // [rsp+E8h] [rbp-2C0h] BYREF
  unsigned int v54; // [rsp+F0h] [rbp-2B8h] BYREF
  struct IVmEthernetSwitchConnection *v55; // [rsp+F8h] [rbp-2B0h] BYREF
  __int128 v56; // [rsp+100h] [rbp-2A8h]
  __int64 v57; // [rsp+110h] [rbp-298h]
  unsigned int v58; // [rsp+118h] [rbp-290h] BYREF
  HLOCAL v59[2]; // [rsp+120h] [rbp-288h] BYREF
  HLOCAL hMem[4]; // [rsp+130h] [rbp-278h] BYREF
  _BYTE v61[544]; // [rsp+150h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v4 = a4;
  v42 = a4;
  v5 = a3;
  v43 = a3;
  v6 = a2;
  v47 = a2;
  v7 = this;
  v45 = this;
  *(_OWORD *)v59 = 0;
  v59[0] = 0;
  v58 = 0;
  v53 = 0;
  VmsIfHandle::VmsIfHandle((VmsIfHandle *)&v53);
  v8 = 0;
  LODWORD(v41) = 0;
  v9 = (VmEthernetSwitchPort *)((char *)v7 + 72);
  v46 = (VmEthernetSwitchPort *)((char *)v7 + 72);
  if ( (*((_DWORD *)v7 + 2399) & 0x10000) == 0 )
  {
    v54 = 0;
    *(_OWORD *)hMem = 0u;
    v44 = 0;
    v10 = 0;
    v56 = 0u;
    if ( !(unsigned __int8)Vml::VmSingletonObject<VmSwitchExtensionRegistrar,VmSwitchExtensionRegistrar>::TryOpenShared(&v44) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB02,
        (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
        v11);
    v12 = (*(__int64 (__fastcall **)(struct IVmEthernetSwitchConnection *, unsigned int *, HLOCAL *))(*(_QWORD *)v6 + 24LL))(
            v6,
            &v54,
            hMem);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB07,
        (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
        (const char *)(unsigned int)v12,
        (int)ppv);
    v14 = v54;
    if ( v54 )
    {
      v15 = LocalAlloc(0x40u, 16LL * v54);
      v10 = v15;
      if ( !v15 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x355,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          v13);
      *(_QWORD *)&v56 = v15;
      v14 = v54;
    }
    v16 = 0;
    v17 = 0;
    v18 = 0;
    if ( v14 )
    {
      v19 = v46;
      do
      {
        v20 = (__int64)hMem[0] + 532 * v18;
        if ( (*(_BYTE *)(v20 + 16) & 1) != 0 )
        {
          v41 = 0;
          FeatureById = VmSwitchExtensionRegistrar::FindFeatureById(
                          v44,
                          (const struct _GUID *)((char *)hMem[0] + 532 * v18));
          Vml::VmReferencePtr<VmmsMigratedVm,Vml::VmUserReferenceTraits>::Reset(&v41, 0);
          v41 = FeatureById;
          if ( FeatureById )
          {
            v23 = *((_QWORD *)FeatureById + 12) - *(_QWORD *)&BUILTIN_EXTENSIONID.Data1;
            if ( !v23 )
              v23 = *((_QWORD *)FeatureById + 13) - *(_QWORD *)BUILTIN_EXTENSIONID.Data4;
            if ( v23 )
              v10[v16++] = *((_OWORD *)FeatureById + 6);
          }
          else
          {
            if ( v42 )
              VmEthernetSwitchPort::LogMissingRequiredFeatureError(
                v22,
                v19,
                (const struct __MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0010_0002 *)v20);
            v17 = 1;
          }
          Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v41);
          v14 = v54;
        }
        ++v18;
      }
      while ( v18 < v14 );
      v5 = v43;
      v4 = v42;
    }
    LODWORD(ppv) = v16;
    LOBYTE(v13) = v17;
    v9 = v46;
    v24 = VmsIfPortSetRequiredExtensions(v53, (char *)v45 + 840, v46, v13);
    v8 = v24;
    LODWORD(v41) = v24;
    if ( v24 )
    {
      if ( v4 )
      {
        if ( v24 > 0 )
          v26 = (unsigned __int16)v24 | 0x80070000;
        else
          v26 = v24;
        VmEthernetSwitchPort::LogRequiredExtensionSetError(v25, v9, v26);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xB49,
        (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
        (const char *)v8,
        v16);
    }
    if ( v10 )
      LocalFree(v10);
    Vml::VmReferencePtr<FrCtSmartBitmapManager,Vml::VmUserReferenceTraits>::~VmReferencePtr<FrCtSmartBitmapManager,Vml::VmUserReferenceTraits>(&v44);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    v6 = v47;
    v7 = v45;
  }
  v55 = 0;
  if ( v5 )
  {
    Instance = CoCreateInstance(
                 &CLSID_VmEthernetSwitchConnection,
                 0,
                 0x17u,
                 &GUID_87afe986_6a6e_498e_9779_34faea7bc1b3,
                 (LPVOID *)&v55);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95F,
        (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
        (const char *)(unsigned int)Instance,
        (int)ppv);
  }
  v28 = (*(__int64 (__fastcall **)(struct IVmEthernetSwitchConnection *, GUID *, unsigned int *, HLOCAL *))(*(_QWORD *)v6 + 48LL))(
          v6,
          &GUID_NULL,
          &v58,
          v59);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5B,
      (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
      (const char *)(unsigned int)v28,
      (int)ppv);
  for ( i = 0; i < v58; ++i )
  {
    v30 = 56LL * i;
    v31 = (char *)v59[0] + v30;
    if ( !*(_DWORD *)((char *)v59[0] + v30 + 36) )
      continue;
    memset(v52, 0, sizeof(v52));
    memset(hMem, 0, 28);
    v32 = *((_DWORD *)v31 + 9);
    if ( !v32 )
      goto LABEL_50;
    v33 = v32 - 1;
    if ( v33 )
    {
      v34 = v33 - 1;
      if ( v34 )
      {
        if ( v34 != 1 )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0xC1A,
            (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
            (const char *)0x8000FFFFLL,
            (int)ppv);
          if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
          {
            ppv = (LPVOID *)"featureSettings[idx].Disposition";
            VmlDebugTrace(
              0,
              L"%hs(%u) : unexpected integer value : %hs == %d\n",
              "onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
              3098);
          }
          goto LABEL_50;
        }
        v48 = 0;
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v57 = 0;
        *(_QWORD *)&v56 = 0;
        v36 = v53;
        *((_QWORD *)&v56 + 1) = v53;
        if ( v5 )
        {
          if ( !(unsigned int)VmsIfPortPropertyQuery(v53, (char *)v7 + 840, v9) )
          {
            v49 = *(_OWORD *)((char *)v59[0] + v30 + 16);
            v48 = *(_OWORD *)((char *)v59[0] + v30);
            LOWORD(v50) = *(_WORD *)((char *)v59[0] + v30 + 32);
            DWORD2(v50) = *(_DWORD *)(v56 + 20);
            v51 = *(_QWORD *)(v56 + 24);
            DWORD1(v50) = 0;
          }
          v36 = v53;
        }
        LODWORD(v52[0]) = *(_DWORD *)((char *)v59[0] + v30 + 16);
        *(_QWORD *)((char *)v52 + 4) = *(_QWORD *)((char *)v59[0] + v30 + 20);
        HIDWORD(v52[1]) = *(_DWORD *)((char *)v59[0] + v30 + 28);
        ppv = (LPVOID *)v52;
        v37 = VmsIfPortPropertyRemove(v36, (char *)v7 + 840, v9);
        v8 = v37;
        LODWORD(v41) = v37;
        if ( v37 == 1168 || v37 == 2 )
        {
          v8 = 0;
          LODWORD(v41) = 0;
        }
        else if ( !v37
               && v5
               && (_QWORD)v56
               && (*(int (__fastcall **)(struct IVmEthernetSwitchConnection *, __int128 *))(*(_QWORD *)v55 + 64LL))(
                    v55,
                    &v48) >= 0 )
        {
          (*(void (__fastcall **)(struct IVmEthernetSwitchConnection *, __int128 *, __int128 *, _QWORD))(*(_QWORD *)v55 + 72LL))(
            v55,
            &v48,
            &v49,
            v8 + 1);
        }
      }
      else
      {
        v48 = 0;
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v57 = 0;
        *(_QWORD *)&v56 = 0;
        v38 = v53;
        *((_QWORD *)&v56 + 1) = v53;
        if ( v5 )
        {
          if ( !(unsigned int)VmsIfPortPropertyQuery(v53, (char *)v7 + 840, v9) )
          {
            v49 = *(_OWORD *)((char *)v59[0] + v30 + 16);
            v48 = *(_OWORD *)((char *)v59[0] + v30);
            LOWORD(v50) = *(_WORD *)((char *)v59[0] + v30 + 32);
            DWORD2(v50) = *(_DWORD *)(v56 + 20);
            v51 = *(_QWORD *)(v56 + 24);
            DWORD1(v50) = 0;
          }
          v38 = v53;
        }
        LODWORD(v52[0]) = *(_DWORD *)((char *)v59[0] + v30 + 16);
        *(_QWORD *)((char *)v52 + 4) = *(_QWORD *)((char *)v59[0] + v30 + 20);
        HIDWORD(v52[1]) = *(_DWORD *)((char *)v59[0] + v30 + 28);
        HIDWORD(v52[2]) = *(_DWORD *)((char *)v59[0] + v30 + 40);
        v52[3] = *(_QWORD *)((char *)v59[0] + v30 + 48);
        LOWORD(ppv) = *(_WORD *)((char *)v59[0] + v30 + 32);
        v8 = VmsIfPortPropertyUpdate(v38, (char *)v7 + 840, v9);
        LODWORD(v41) = v8;
        if ( !v8
          && v5
          && (_QWORD)v56
          && (*(int (__fastcall **)(struct IVmEthernetSwitchConnection *, __int128 *))(*(_QWORD *)v55 + 64LL))(
               v55,
               &v48) >= 0 )
        {
          (*(void (__fastcall **)(struct IVmEthernetSwitchConnection *, __int128 *, __int128 *, _QWORD))(*(_QWORD *)v55 + 72LL))(
            v55,
            &v48,
            &v49,
            v8 + 2);
        }
      }
      if ( (_QWORD)v56 )
        VmsIfPortPropertyFree(*((_QWORD *)&v56 + 1));
LABEL_50:
      if ( v8 )
        goto LABEL_51;
      continue;
    }
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    if ( v5 )
    {
      v49 = *((_OWORD *)v31 + 1);
      v48 = *(_OWORD *)v31;
      LOWORD(v50) = *((_WORD *)v31 + 16);
      *(_QWORD *)((char *)&v50 + 4) = 0;
      v51 = 0;
    }
    LODWORD(v52[0]) = *((_DWORD *)v31 + 4);
    *(_QWORD *)((char *)v52 + 4) = *(_QWORD *)(v31 + 20);
    HIDWORD(v52[1]) = *((_DWORD *)v31 + 7);
    HIDWORD(v52[2]) = *((_DWORD *)v31 + 10);
    v52[3] = *((_QWORD *)v31 + 6);
    LOWORD(ppv) = *((_WORD *)v31 + 16);
    v8 = VmsIfPortPropertyAdd(v53, (char *)v7 + 840, v9);
    LODWORD(v41) = v8;
    if ( v8 )
    {
LABEL_51:
      if ( v42 )
      {
        memset_0(v61, 0, 0x214u);
        if ( (*(int (__fastcall **)(struct IVmEthernetSwitchConnection *, char *, _BYTE *))(*(_QWORD *)v6 + 32LL))(
               v6,
               (char *)v59[0] + v30,
               v61) >= 0 )
        {
          if ( (int)v8 > 0 )
            v35 = (VmEthernetSwitchPort *)((unsigned __int16)v8 | 0x80070000);
          else
            v35 = (VmEthernetSwitchPort *)v8;
          VmEthernetSwitchPort::LogFeatureSettingError(
            v35,
            v9,
            (const struct __MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0010_0002 *)v61,
            (const struct __MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0010_0003 *)((char *)v59[0] + v30),
            (int)v35);
        }
      }
      if ( v5 )
      {
        try
        {
          VmEthernetSwitchPort::WriteFeatureSettings(v7, v55, 0, 0);
        }
        catch ( ... )
        {
          Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x8061, (unsigned __int16)&off_140904AF8, v39);
          v8 = (unsigned int)v41;
        }
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xC3C,
        (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchport.cpp",
        (const char *)v8,
        (unsigned int)ppv);
    }
    if ( v5
      && (*(int (__fastcall **)(struct IVmEthernetSwitchConnection *, __int128 *))(*(_QWORD *)v55 + 64LL))(v55, &v48) >= 0 )
    {
      (*(void (__fastcall **)(struct IVmEthernetSwitchConnection *, __int128 *, __int128 *, _QWORD))(*(_QWORD *)v55 + 72LL))(
        v55,
        &v48,
        &v49,
        v8 + 3);
    }
  }
  Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v55);
  VmsIfHandle::~VmsIfHandle((VmsIfHandle *)&v53);
  if ( v59[0] )
    LocalFree(v59[0]);
}

```

## disassembly

```asm
0x140352ca8  mov     r11, rsp
0x140352cab  mov     [r11+18h], rbx
0x140352caf  mov     [r11+20h], rsi
0x140352cb3  push    rdi
0x140352cb4  push    r12
0x140352cb6  push    r13
0x140352cb8  push    r14
0x140352cba  push    r15
0x140352cbc  sub     rsp, 380h
0x140352cc3  mov     rax, cs:__security_cookie
0x140352cca  xor     rax, rsp
0x140352ccd  mov     [rsp+3A8h+var_38], rax
0x140352cd5  mov     r14d, r9d
0x140352cd8  mov     [rsp+3A8h+var_340], r9d
0x140352cdd  mov     r13d, r8d
0x140352ce0  mov     [rsp+3A8h+var_33C], r8d
0x140352ce5  mov     r12, rdx
0x140352ce8  mov     [rsp+3A8h+var_320], rdx
0x140352cf0  mov     r15, rcx
0x140352cf3  mov     [rsp+3A8h+var_330], rcx
0x140352cf8  xorps   xmm0, xmm0
0x140352cfb  movups  xmmword ptr [rsp+3A8h+var_288], xmm0
0x140352d03  mov     qword ptr [r11-288h], 0
0x140352d0e  mov     [rsp+3A8h+var_290], 0
0x140352d19  mov     qword ptr [r11-2C0h], 0
0x140352d24  lea     rcx, [r11-2C0h]; this
0x140352d2b  call    ??0VmsIfHandle@@QEAA@XZ; VmsIfHandle::VmsIfHandle(void)
0x140352d30  nop
0x140352d31  xor     ebx, ebx
0x140352d33  mov     dword ptr [rsp+3A8h+var_348], ebx
0x140352d37  lea     rsi, [r15+48h]
0x140352d3b  mov     [rsp+3A8h+var_328], rsi
0x140352d43  test    dword ptr [rsi+2534h], 10000h
0x140352d4d  jnz     loc_140352FD1
0x140352d53  mov     [rsp+3A8h+var_2B8], ebx
0x140352d5a  xorps   xmm0, xmm0
0x140352d5d  movups  xmmword ptr [rsp+3A8h+hMem], xmm0
0x140352d65  mov     [rsp+3A8h+hMem], rbx
0x140352d6d  mov     [rsp+3A8h+var_338], rbx
0x140352d72  movups  [rsp+3A8h+var_2A8], xmm0
0x140352d7a  xor     edi, edi
0x140352d7c  mov     qword ptr [rsp+3A8h+var_2A8], rdi
0x140352d84  lea     rcx, [rsp+3A8h+var_338]
0x140352d89  call    ?TryOpenShared@?$VmSingletonObject@VVmSwitchExtensionRegistrar@@V1@@Vml@@SA_NPEAPEAVVmSwitchExtensionRegistrar@@@Z; Vml::VmSingletonObject<VmSwitchExtensionRegistrar,VmSwitchExtensionRegistrar>::TryOpenShared(VmSwitchExtensionRegistrar * *)
0x140352d8e  mov     rcx, [rsp+3A8h]; this
0x140352d96  test    al, al
0x140352d98  jnz     short loc_140352DAC
0x140352d9a  lea     r8, aOnecoreVmVmmsE_0; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x140352da1  mov     edx, 0B02h; void *
0x140352da6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140352dac  mov     rax, [r12]
0x140352db0  lea     r8, [rsp+3A8h+hMem]
0x140352db8  lea     rdx, [rsp+3A8h+var_2B8]
0x140352dc0  mov     rcx, r12
0x140352dc3  mov     rax, [rax+18h]
0x140352dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140352dcc  mov     rcx, [rsp+3A8h]; this
0x140352dd4  test    eax, eax
0x140352dd6  jns     short loc_140352DED
0x140352dd8  mov     r9d, eax; char *
0x140352ddb  lea     r8, aOnecoreVmVmmsE_0; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x140352de2  mov     edx, 0B07h; void *
0x140352de7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140352ded  mov     edx, [rsp+3A8h+var_2B8]
0x140352df4  test    edx, edx
0x140352df6  jz      short loc_140352E3E
0x140352df8  shl     rdx, 4; uBytes
0x140352dfc  mov     ecx, 40h ; '@'; uFlags
0x140352e01  call    cs:__imp_LocalAlloc
0x140352e08  nop     dword ptr [rax+rax+00h]
0x140352e0d  mov     rdi, rax
0x140352e10  test    rax, rax
0x140352e13  jnz     short loc_140352E2F
0x140352e15  mov     rcx, [rsp+3A8h]; this
0x140352e1d  lea     r8, aOnecoreVmCommo_37; "onecore\\vm\\common\\vml\\VmMemory.h"
0x140352e24  mov     edx, 355h; void *
0x140352e29  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140352e2f  mov     qword ptr [rsp+3A8h+var_2A8], rax
0x140352e37  mov     edx, [rsp+3A8h+var_2B8]
0x140352e3e  xor     r15d, r15d
0x140352e41  xor     r12b, r12b
0x140352e44  xor     esi, esi
0x140352e46  test    edx, edx
0x140352e48  jz      loc_140352F0B
0x140352e4e  mov     r13, [rsp+3A8h+var_328]
0x140352e56  mov     eax, esi
0x140352e58  imul    r14, rax, 214h
0x140352e5f  add     r14, [rsp+3A8h+hMem]
0x140352e67  test    byte ptr [r14+10h], 1
0x140352e6c  jz      loc_140352EF7
0x140352e72  mov     [rsp+3A8h+var_348], 0
0x140352e7b  mov     rdx, r14; struct _GUID *
0x140352e7e  mov     rcx, [rsp+3A8h+var_338]; this
0x140352e83  call    ?FindFeatureById@VmSwitchExtensionRegistrar@@QEBAPEAVVmSwitchFeatureInfo@@AEBU_GUID@@@Z; VmSwitchExtensionRegistrar::FindFeatureById(_GUID const &)
0x140352e88  mov     rbx, rax
0x140352e8b  xor     edx, edx
0x140352e8d  lea     rcx, [rsp+3A8h+var_348]
0x140352e92  call    ?Reset@?$VmReferencePtr@VVmmsMigratedVm@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVmmsMigratedVm@@@Z; Vml::VmReferencePtr<VmmsMigratedVm,Vml::VmUserReferenceTraits>::Reset(VmmsMigratedVm *)
0x140352e97  mov     [rsp+3A8h+var_348], rbx
0x140352e9c  test    rbx, rbx
0x140352e9f  jnz     short loc_140352EB7
0x140352ea1  cmp     [rsp+3A8h+var_340], ebx
0x140352ea5  jz      short loc_140352EB2
0x140352ea7  mov     r8, r14; struct __MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0010_0002 *
0x140352eaa  mov     rdx, r13; struct _VMS_ENUM_PORT_INFO_OUT *
0x140352ead  call    ?LogMissingRequiredFeatureError@VmEthernetSwitchPort@@AEAAXQEAU_VMS_ENUM_PORT_INFO_OUT@@PEBU__MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0010_0002@@@Z; VmEthernetSwitchPort::LogMissingRequiredFeatureError(_VMS_ENUM_PORT_INFO_OUT * const,__MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0010_0002 const *)
0x140352eb2  mov     r12b, 1
0x140352eb5  jmp     short loc_140352EE6
0x140352eb7  mov     rax, [rbx+60h]
0x140352ebb  sub     rax, qword ptr cs:BUILTIN_EXTENSIONID.Data1
0x140352ec2  jnz     short loc_140352ECF
0x140352ec4  mov     rax, [rbx+68h]
0x140352ec8  sub     rax, qword ptr cs:BUILTIN_EXTENSIONID.Data4
0x140352ecf  test    rax, rax
0x140352ed2  jz      short loc_140352EE6
0x140352ed4  movups  xmm0, xmmword ptr [rbx+60h]
0x140352ed8  mov     eax, r15d
0x140352edb  add     rax, rax
0x140352ede  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x140352ee3  inc     r15d
0x140352ee6  lea     rcx, [rsp+3A8h+var_348]
0x140352eeb  call    ??1?$VmReferencePtr@V?$VmMethodDelegate@VVmmsRealizedVirtualMachine@@XPEAUIVmTask@@AEBU_REFERENCE_POINT_CREATE_PARAMS@@@Vml@@VVmUserReferenceTraits@2@@Vml@@QEAA@XZ; Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(void)
0x140352ef0  mov     edx, [rsp+3A8h+var_2B8]
0x140352ef7  inc     esi
0x140352ef9  cmp     esi, edx
0x140352efb  jb      loc_140352E56
0x140352f01  mov     r13d, [rsp+3A8h+var_33C]
0x140352f06  mov     r14d, [rsp+3A8h+var_340]
0x140352f0b  mov     rdx, [rsp+3A8h+var_330]
0x140352f10  add     rdx, 348h
0x140352f17  mov     [rsp+3A8h+var_380], rdi
0x140352f1c  mov     dword ptr [rsp+3A8h+ppv], r15d; int
0x140352f21  mov     r9b, r12b
0x140352f24  mov     rsi, [rsp+3A8h+var_328]
0x140352f2c  mov     r8, rsi
0x140352f2f  mov     rcx, [rsp+3A8h+var_2C0]
0x140352f37  call    cs:__imp_VmsIfPortSetRequiredExtensions
0x140352f3e  nop     dword ptr [rax+rax+00h]
0x140352f43  mov     ebx, eax
0x140352f45  mov     dword ptr [rsp+3A8h+var_348], eax
0x140352f49  test    eax, eax
0x140352f4b  jz      short loc_140352F8B
0x140352f4d  test    r14d, r14d
0x140352f50  jz      short loc_140352F6E
0x140352f52  test    eax, eax
0x140352f54  jg      short loc_140352F5B
0x140352f56  mov     r8d, eax
0x140352f59  jmp     short loc_140352F66
0x140352f5b  movzx   r8d, bx
0x140352f5f  or      r8d, 80070000h; int
0x140352f66  mov     rdx, rsi; struct _VMS_ENUM_PORT_INFO_OUT *
0x140352f69  call    ?LogRequiredExtensionSetError@VmEthernetSwitchPort@@AEAAXQEAU_VMS_ENUM_PORT_INFO_OUT@@J@Z; VmEthernetSwitchPort::LogRequiredExtensionSetError(_VMS_ENUM_PORT_INFO_OUT * const,long)
0x140352f6e  mov     rcx, [rsp+3A8h]; this
0x140352f76  mov     r9d, ebx; char *
0x140352f79  lea     r8, aOnecoreVmVmmsE_0; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x140352f80  mov     edx, 0B49h; void *
0x140352f85  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140352f8b  test    rdi, rdi
0x140352f8e  jz      short loc_140352FA0
0x140352f90  mov     rcx, rdi; hMem
0x140352f93  call    cs:__imp_LocalFree
0x140352f9a  nop     dword ptr [rax+rax+00h]
0x140352f9f  nop
0x140352fa0  lea     rcx, [rsp+3A8h+var_338]
0x140352fa5  call    ??1?$VmReferencePtr@VFrCtSmartBitmapManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<FrCtSmartBitmapManager,Vml::VmUserReferenceTraits>::~VmReferencePtr<FrCtSmartBitmapManager,Vml::VmUserReferenceTraits>(void)
0x140352faa  nop
0x140352fab  mov     rcx, [rsp+3A8h+hMem]; hMem
0x140352fb3  test    rcx, rcx
0x140352fb6  jz      short loc_140352FC4
0x140352fb8  call    cs:__imp_LocalFree
0x140352fbf  nop     dword ptr [rax+rax+00h]
0x140352fc4  mov     r12, [rsp+3A8h+var_320]
0x140352fcc  mov     r15, [rsp+3A8h+var_330]
0x140352fd1  mov     [rsp+3A8h+var_2B0], 0
0x140352fdd  test    r13d, r13d
0x140352fe0  jz      short loc_140353030
0x140352fe2  lea     rax, [rsp+3A8h+var_2B0]
0x140352fea  mov     [rsp+3A8h+ppv], rax; int
0x140352fef  lea     r9, _GUID_87afe986_6a6e_498e_9779_34faea7bc1b3; riid
0x140352ff6  xor     edx, edx; pUnkOuter
0x140352ff8  lea     r8d, [rdx+17h]; dwClsContext
0x140352ffc  lea     rcx, CLSID_VmEthernetSwitchConnection; rclsid
0x140353003  call    cs:__imp_CoCreateInstance
0x14035300a  nop     dword ptr [rax+rax+00h]
0x14035300f  mov     rcx, [rsp+3A8h]; this
0x140353017  test    eax, eax
0x140353019  jns     short loc_140353030
0x14035301b  mov     r9d, eax; char *
0x14035301e  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\vml\\VmCom.h"
0x140353025  mov     edx, 95Fh; void *
0x14035302a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140353030  mov     rax, [r12]
0x140353034  lea     r9, [rsp+3A8h+var_288]
0x14035303c  lea     r8, [rsp+3A8h+var_290]
0x140353044  lea     rdx, GUID_NULL
0x14035304b  mov     rcx, r12
0x14035304e  mov     rax, [rax+30h]
0x140353052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140353057  mov     rcx, [rsp+3A8h]; this
0x14035305f  test    eax, eax
0x140353061  jns     short loc_140353078
0x140353063  mov     r9d, eax; char *
0x140353066  lea     r8, aOnecoreVmVmmsE_0; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x14035306d  mov     edx, 0B5Bh; void *
0x140353072  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140353078  xor     r14d, r14d
0x14035307b  mov     r10d, 100h
0x140353081  cmp     r14d, [rsp+3A8h+var_290]
0x140353089  jnb     loc_140353788
0x14035308f  mov     eax, r14d
0x140353092  imul    rdi, rax, 38h ; '8'
0x140353096  mov     r9, [rsp+3A8h+var_288]
0x14035309e  add     r9, rdi
0x1403530a1  cmp     dword ptr [r9+24h], 0
0x1403530a6  jz      loc_140353719
0x1403530ac  mov     [rsp+3A8h+var_2E0], 0
0x1403530b7  xorps   xmm0, xmm0
0x1403530ba  xor     eax, eax
0x1403530bc  movups  [rsp+3A8h+var_2DC], xmm0
0x1403530c4  movups  [rsp+3A8h+var_2DC+0Ch], xmm0
0x1403530cc  xorps   xmm1, xmm1
0x1403530cf  movups  xmmword ptr [rsp+3A8h+hMem], xmm1
0x1403530d7  movups  xmmword ptr [rsp+3A8h+hMem+0Ch], xmm1
0x1403530df  mov     ecx, [r9+24h]
0x1403530e3  test    ecx, ecx
0x1403530e5  jz      short loc_140353163
0x1403530e7  sub     ecx, 1
0x1403530ea  jz      loc_1403535BC
0x1403530f0  sub     ecx, 1
0x1403530f3  jz      loc_1403533C6
0x1403530f9  cmp     ecx, 1
0x1403530fc  jz      loc_1403531C5
0x140353102  mov     rcx, [rsp+3A8h]; this
0x14035310a  mov     r9d, 8000FFFFh; char *
0x140353110  lea     r8, aOnecoreVmVmmsE_0; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x140353117  mov     edx, 0C1Ah; void *
0x14035311c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140353121  xor     ecx, ecx
0x140353123  call    VmlIsDebugTraceEnabled
0x140353128  test    eax, eax
0x14035312a  jz      short loc_140353163
0x14035312c  mov     rax, [rsp+3A8h+var_288]
0x140353134  mov     ecx, [rdi+rax+24h]
0x140353138  mov     dword ptr [rsp+3A8h+var_380], ecx
0x14035313c  lea     rax, aFeaturesetting_0; "featureSettings[idx].Disposition"
0x140353143  mov     [rsp+3A8h+ppv], rax
0x140353148  mov     r9d, 0C1Ah
0x14035314e  lea     r8, aOnecoreVmVmmsE_0; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x140353155  lea     rdx, aHsUUnexpectedI; "%hs(%u) : unexpected integer value : %h"...
0x14035315c  xor     ecx, ecx
0x14035315e  call    VmlDebugTrace
0x140353163  test    ebx, ebx
0x140353165  jz      loc_140353719
0x14035316b  cmp     [rsp+3A8h+var_340], 0
0x140353170  jz      loc_140353749
0x140353176  xor     edx, edx; Val
0x140353178  mov     r8d, 214h; Size
0x14035317e  lea     rcx, [rsp+3A8h+var_258]; void *
0x140353186  call    memset_0
0x14035318b  mov     rcx, [r12]
0x14035318f  mov     rdx, [rsp+3A8h+var_288]
0x140353197  add     rdx, rdi
0x14035319a  mov     rax, [rcx+20h]
0x14035319e  lea     r8, [rsp+3A8h+var_258]
0x1403531a6  mov     rcx, r12
0x1403531a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1403531ae  test    eax, eax
0x1403531b0  js      loc_140353749
0x1403531b6  test    ebx, ebx
0x1403531b8  jg      loc_140353721
0x1403531be  mov     ecx, ebx
0x1403531c0  jmp     loc_14035372A
0x1403531c5  movups  [rsp+3A8h+var_318], xmm0
0x1403531cd  movups  [rsp+3A8h+var_308], xmm0
0x1403531d5  movups  [rsp+3A8h+var_2F8], xmm0
0x1403531dd  mov     [rsp+3A8h+var_2E8], rax
0x1403531e5  movups  [rsp+3A8h+var_2A8], xmm0
0x1403531ed  mov     [rsp+3A8h+var_298], rax
0x1403531f5  mov     qword ptr [rsp+3A8h+var_2A8], rax
0x1403531fd  mov     rcx, [rsp+3A8h+var_2C0]
0x140353205  mov     qword ptr [rsp+3A8h+var_2A8+8], rcx
0x14035320d  test    r13d, r13d
0x140353210  jz      loc_1403532AD
0x140353216  lea     rax, [r9+10h]
0x14035321a  lea     rdx, [r15+348h]
0x140353221  lea     r8, [rsp+3A8h+var_2A8]
0x140353229  mov     [rsp+3A8h+var_378], r8
0x14035322e  mov     [rsp+3A8h+var_380], rax
0x140353233  mov     word ptr [rsp+3A8h+ppv], r10w
0x140353239  mov     r8, rsi
0x14035323c  call    cs:__imp_VmsIfPortPropertyQuery
0x140353243  nop     dword ptr [rax+rax+00h]
0x140353248  test    eax, eax
0x14035324a  jnz     short loc_1403532A5
0x14035324c  mov     rax, [rsp+3A8h+var_288]
0x140353254  movups  xmm0, xmmword ptr [rdi+rax+10h]
0x140353259  movdqu  [rsp+3A8h+var_308], xmm0
0x140353262  movups  xmm1, xmmword ptr [rdi+rax]
0x140353266  movdqu  [rsp+3A8h+var_318], xmm1
0x14035326f  movzx   eax, word ptr [rdi+rax+20h]
  ... truncated ...
```
