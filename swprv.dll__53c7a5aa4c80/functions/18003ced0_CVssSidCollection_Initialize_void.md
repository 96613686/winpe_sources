# CVssSidCollection::Initialize(void)

- ea: `0x18003ced0`
- end: `0x18003d783`
- name: `?Initialize@CVssSidCollection@@QEAAXXZ`
- size: `2227`
- prototype: `void __fastcall(CVssSidCollection *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000aa5c`

## callees

- `0x18000212c`
- `0x1800036e8`
- `0x180003718`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x180033df4`
- `0x180034038`
- `0x1800358f4`
- `0x18003649c`
- `0x180037080`
- `0x180037e24`
- `0x180038118`
- `0x180038704`
- `0x1800389c0`
- `0x180038d40`
- `0x180038dec`
- `0x180038f00`
- `0x18003a05c`
- `0x18003c090`
- `0x18003c4ac`
- `0x18003c8d8`
- `0x18003cdf4`
- `0x18003ced0`
- `0x18003db28`
- `0x18003dc30`

## string_xrefs

- `0x18003ceef`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d0ee`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d16e`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d1ee`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d28f`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d30f`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d38f`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003d4a8`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003cefb`: `CVssSidCollection::Initialize`
- `0x18003d059`: `CVssSidCollection::Initialize`
- `0x18003d0fa`: `CVssSidCollection::Initialize`
- `0x18003d17a`: `CVssSidCollection::Initialize`
- `0x18003d1fa`: `CVssSidCollection::Initialize`
- `0x18003d29b`: `CVssSidCollection::Initialize`
- `0x18003d31b`: `CVssSidCollection::Initialize`
- `0x18003d39b`: `CVssSidCollection::Initialize`
- `0x18003d4af`: `CVssSidCollection::Initialize`
- `0x18003cfb3`: `m_SDWriters.Initialize() failed`
- `0x18003d464`: `SYSTEM\CurrentControlSet\Services\VSS\VssAccessControl`
- `0x18003d522`: `SYSTEM\CurrentControlSet\Services\VSS\VssAccessControl`
- `0x18003d5cd`: `SYSTEM\CurrentControlSet\Services\VSS\VssAccessControl`
- `0x18003d6a9`: `SYSTEM\CurrentControlSet\Services\VSS\VssAccessControl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssSidCollection::Initialize(CVssSidCollection *this)
{
  int v2; // edi
  int v3; // edi
  int v4; // edi
  void *v5; // r12
  int v6; // r8d
  int v7; // edi
  int v8; // r8d
  int v9; // edi
  int v10; // r8d
  int v11; // edi
  void *v12; // r12
  int v13; // r8d
  int v14; // edi
  int v15; // r8d
  int v16; // edi
  int v17; // r8d
  int v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // ecx
  CVssDebugInfo *v21; // rax
  unsigned __int16 *CurrentValueName; // rax
  struct CVssDebugInfo *v23; // rax
  CVssDebugInfo *v24; // rax
  unsigned int v25; // edi
  unsigned __int16 *v26; // rax
  struct CVssDebugInfo *v27; // rax
  struct CVssDebugInfo *v28; // rax
  __int64 v29; // rax
  const WCHAR *v30; // rax
  const unsigned __int16 *v31; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v32; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v33; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+38h] [rbp-C8h]
  int v35; // [rsp+3Ch] [rbp-C4h]
  int v36; // [rsp+40h] [rbp-C0h]
  _BYTE v37[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+C0h] [rbp-40h]
  _BYTE v39[8]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v40; // [rsp+D0h] [rbp-30h]
  unsigned int v41; // [rsp+D4h] [rbp-2Ch]
  int v42; // [rsp+D8h] [rbp-28h]
  _QWORD v43[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v44; // [rsp+F4h] [rbp-Ch]
  char v45; // [rsp+F8h] [rbp-8h]
  void **v46; // [rsp+100h] [rbp+0h] BYREF
  void *v47; // [rsp+108h] [rbp+8h]
  void **v48; // [rsp+110h] [rbp+10h] BYREF
  void *v49; // [rsp+118h] [rbp+18h]
  _QWORD v50[4]; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v51; // [rsp+140h] [rbp+40h] BYREF
  int v52; // [rsp+148h] [rbp+48h]
  _BYTE v53[168]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v54[168]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v55[240]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int v56; // [rsp+400h] [rbp+300h] BYREF

  v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v32 = L"CVssSidCollection::Initialize";
  v33 = L"SECSECRC";
  v34 = 1569;
  v35 = 11;
  v36 = 255;
  v38 = 0x1000000;
  memset_0(v37, 0, sizeof(v37));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v51, (__int64)&v31, 0);
  if ( !*(_BYTE *)this )
  {
    v2 = CVssSecurityDescriptor::Initialize((CVssSidCollection *)((char *)this + 8));
    v52 = v2;
    if ( v2 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1583;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::Throw(&v51, &v31, (unsigned int)v2, L"m_SDWriters.Initialize() failed");
    }
    v3 = CVssSecurityDescriptor::Initialize((CVssSidCollection *)((char *)this + 40));
    v52 = v3;
    if ( v3 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1591;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::Throw(&v51, &v31, (unsigned int)v3, L"m_SDRequestors.Initialize() failed");
    }
    v4 = CVssSecurityDescriptor::Initialize((CVssSidCollection *)((char *)this + 72));
    v52 = v4;
    if ( v4 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1599;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::Throw(&v51, &v31, (unsigned int)v4, L"m_SDBoth.Initialize() failed");
    }
    v49 = 0;
    v48 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    CAutoSid::CreateBasicSid((CAutoSid *)&v48, WinLocalSystemSid);
    v5 = v49;
    v7 = CVssSecurityDescriptor::SetOwner((CVssSidCollection *)((char *)this + 8), v49, v6);
    v52 = v7;
    if ( v7 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1613;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateGenericError(&v51, &v31, (unsigned int)v7, L"SetOwner");
    }
    v9 = CVssSecurityDescriptor::SetOwner((CVssSidCollection *)((char *)this + 40), v5, v8);
    v52 = v9;
    if ( v9 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1616;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateGenericError(&v51, &v31, (unsigned int)v9, L"SetOwner");
    }
    v11 = CVssSecurityDescriptor::SetOwner((CVssSidCollection *)((char *)this + 72), v5, v10);
    v52 = v11;
    if ( v11 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1619;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateGenericError(&v51, &v31, (unsigned int)v11, L"SetOwner");
    }
    v47 = 0;
    v46 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    CAutoSid::CreateBasicSid((CAutoSid *)&v46, WinBuiltinAdministratorsSid);
    v12 = v47;
    v14 = CVssSecurityDescriptor::SetGroup((CVssSidCollection *)((char *)this + 8), v47, v13);
    v52 = v14;
    if ( v14 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1630;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateGenericError(&v51, &v31, (unsigned int)v14, L"SetGroup");
    }
    v16 = CVssSecurityDescriptor::SetGroup((CVssSidCollection *)((char *)this + 40), v12, v15);
    v52 = v16;
    if ( v16 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1633;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateGenericError(&v51, &v31, (unsigned int)v16, L"SetGroup");
    }
    v18 = CVssSecurityDescriptor::SetGroup((CVssSidCollection *)((char *)this + 72), v12, v17);
    v52 = v18;
    if ( v18 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1636;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateGenericError(&v51, &v31, (unsigned int)v18, L"SetGroup");
    }
    CVssSidCollection::AddWellKnownSid((__int64)this, WinBuiltinAdministratorsSid, 3);
    CVssSidCollection::AddWellKnownSid((__int64)this, WinLocalSystemSid, 3);
    CVssSidCollection::AddWellKnownSid((__int64)this, WinBuiltinBackupOperatorsSid, 3);
    CVssSidCollection::AddWellKnownSid((__int64)this, WinNetworkServiceSid, 1);
    CVssSidCollection::AddWellKnownSid((__int64)this, WinLocalServiceSid, 1);
    v50[3] = 0;
    v50[2] = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v50[1] = 0;
    v50[0] = 131097;
    if ( CVssRegistryKey::Open(
           (CVssRegistryKey *)v50,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\VSS\\VssAccessControl") )
    {
      v43[1] = 0;
      v43[0] = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
      CVssRegistryValueIterator::Detach((CVssRegistryValueIterator *)v39);
      CVssRegistryValueIterator::Attach((CVssRegistryValueIterator *)v39, (struct CVssRegistryKey *)v50);
      v19 = v41;
      v20 = v40;
      while ( 1 )
      {
        if ( v19 >= v20 )
        {
LABEL_35:
          CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v43);
          goto LABEL_36;
        }
        if ( !(unsigned int)CVssRegistryValueIterator::GetCurrentValueNameLen((CVssRegistryValueIterator *)v39)
          && (unsigned int)CVssRegistryValueIterator::GetCurrentValueType((CVssRegistryValueIterator *)v39) == 4 )
        {
          break;
        }
        if ( (unsigned int)CVssRegistryValueIterator::GetCurrentValueType((CVssRegistryValueIterator *)v39) != 4 )
        {
          v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
          v32 = L"CVssSidCollection::Initialize";
          v33 = L"SECSECRC";
          v34 = 1673;
          v35 = 11;
          v36 = 255;
          v38 = 0x1000000;
          memset_0(v37, 0, sizeof(v37));
          CurrentValueName = CVssRegistryValueIterator::GetCurrentValueName((CVssRegistryValueIterator *)v39);
          v23 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v31, (CVssDebugInfo *)v54, CurrentValueName);
          v24 = CVssDebugInfo::operator<<(
                  v23,
                  (CVssDebugInfo *)v53,
                  L"SYSTEM\\CurrentControlSet\\Services\\VSS\\VssAccessControl");
          CVssFunctionTracer::LogError(&v51, 16, v24);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v54);
          goto LABEL_26;
        }
        v56 = 0;
        CVssRegistryValueIterator::GetCurrentValueContent((CVssRegistryValueIterator *)v39, &v56);
        v25 = v56;
        if ( v56 >= 2 && v56 - 2 >= 2 )
        {
          v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
          v32 = L"CVssSidCollection::Initialize";
          v33 = L"SECSECRC";
          v34 = 1693;
          v35 = 11;
          v36 = 255;
          v38 = 0x1000000;
          memset_0(v37, 0, sizeof(v37));
          v26 = CVssRegistryValueIterator::GetCurrentValueName((CVssRegistryValueIterator *)v39);
          v27 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v31, (CVssDebugInfo *)v55, v26);
          v28 = CVssDebugInfo::operator<<(
                  v27,
                  (CVssDebugInfo *)v53,
                  L"SYSTEM\\CurrentControlSet\\Services\\VSS\\VssAccessControl");
          v29 = CVssDebugInfo::operator<<(v28, (CVssDebugInfo *)v54);
          CVssFunctionTracer::LogError(&v51, 17, v29);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v53);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v55);
          goto LABEL_26;
        }
        v30 = CVssRegistryValueIterator::GetCurrentValueName((CVssRegistryValueIterator *)v39);
        CVssSidCollection::AddUser((__int64)this, v30, v25);
LABEL_33:
        v20 = v40;
        if ( v41 >= v40 )
          goto LABEL_35;
        v45 = 0;
        v42 = 0;
        v44 = 0;
        v19 = ++v41;
      }
      v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v32 = L"CVssSidCollection::Initialize";
      v33 = L"SECSECRC";
      v34 = 1666;
      v35 = 11;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      v21 = CVssDebugInfo::operator<<(
              (struct CVssDebugInfo *)&v31,
              (CVssDebugInfo *)v53,
              L"SYSTEM\\CurrentControlSet\\Services\\VSS\\VssAccessControl");
      CVssFunctionTracer::LogError(&v51, 23, v21);
LABEL_26:
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v31);
      goto LABEL_33;
    }
LABEL_36:
    *(_BYTE *)this = 1;
    CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v50);
    CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v46);
    CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v48);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v51);
}

```

## disassembly

```asm
0x18003ced0  push    rbp
0x18003ced2  push    rbx
0x18003ced3  push    rsi
0x18003ced4  push    rdi
0x18003ced5  push    r12
0x18003ced7  push    r13
0x18003ced9  push    r14
0x18003cedb  push    r15
0x18003cedd  lea     rbp, [rsp-2B8h]
0x18003cee5  sub     rsp, 3B8h
0x18003ceec  mov     rbx, rcx
0x18003ceef  lea     r12, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003cef6  mov     [rsp+3F0h+var_3D0], r12
0x18003cefb  lea     r14, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003cf02  mov     [rsp+3F0h+var_3C8], r14
0x18003cf07  lea     rsi, aSecsecrc; "SECSECRC"
0x18003cf0e  mov     [rsp+3F0h+var_3C0], rsi
0x18003cf13  mov     [rsp+3F0h+var_3B8], 621h
0x18003cf1b  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003cf23  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003cf2b  xor     r13d, r13d
0x18003cf2e  mov     [rbp+2F0h+var_330], 1000000h
0x18003cf35  xor     edx, edx; Val
0x18003cf37  lea     r8d, [r13+78h]; Size
0x18003cf3b  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003cf40  call    memset_0
0x18003cf45  xor     r8d, r8d
0x18003cf48  lea     rdx, [rsp+3F0h+var_3D0]
0x18003cf4d  lea     rcx, [rbp+2F0h+var_2B0]
0x18003cf51  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003cf56  nop
0x18003cf57  cmp     [rbx], r13b
0x18003cf5a  jnz     loc_18003D766
0x18003cf60  lea     r15, [rbx+8]
0x18003cf64  mov     rcx, r15; this
0x18003cf67  call    ?Initialize@CVssSecurityDescriptor@@QEAAJXZ; CVssSecurityDescriptor::Initialize(void)
0x18003cf6c  mov     edi, eax
0x18003cf6e  mov     [rbp+2F0h+var_2A8], eax
0x18003cf71  test    eax, eax
0x18003cf73  jns     short loc_18003CFCC
0x18003cf75  mov     [rsp+3F0h+var_3D0], r12
0x18003cf7a  mov     [rsp+3F0h+var_3C8], r14
0x18003cf7f  mov     [rsp+3F0h+var_3C0], rsi
0x18003cf84  mov     [rsp+3F0h+var_3B8], 62Fh
0x18003cf8c  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003cf94  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003cf9c  mov     [rbp+2F0h+var_330], 1000000h
0x18003cfa3  xor     edx, edx; Val
0x18003cfa5  lea     r8d, [r13+78h]; Size
0x18003cfa9  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003cfae  call    memset_0
0x18003cfb3  lea     r9, aMSdwritersInit; "m_SDWriters.Initialize() failed"
0x18003cfba  mov     r8d, edi
0x18003cfbd  lea     rdx, [rsp+3F0h+var_3D0]
0x18003cfc2  lea     rcx, [rbp+2F0h+var_2B0]
0x18003cfc6  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003cfcc  lea     rsi, [rbx+28h]
0x18003cfd0  mov     rcx, rsi; this
0x18003cfd3  call    ?Initialize@CVssSecurityDescriptor@@QEAAJXZ; CVssSecurityDescriptor::Initialize(void)
0x18003cfd8  mov     edi, eax
0x18003cfda  mov     [rbp+2F0h+var_2A8], eax
0x18003cfdd  test    eax, eax
0x18003cfdf  jns     short loc_18003D03F
0x18003cfe1  mov     [rsp+3F0h+var_3D0], r12
0x18003cfe6  mov     [rsp+3F0h+var_3C8], r14
0x18003cfeb  lea     r12, aSecsecrc; "SECSECRC"
0x18003cff2  mov     [rsp+3F0h+var_3C0], r12
0x18003cff7  mov     [rsp+3F0h+var_3B8], 637h
0x18003cfff  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d007  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d00f  mov     [rbp+2F0h+var_330], 1000000h
0x18003d016  xor     edx, edx; Val
0x18003d018  lea     r8d, [rdx+78h]; Size
0x18003d01c  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d021  call    memset_0
0x18003d026  lea     r9, aMSdrequestorsI; "m_SDRequestors.Initialize() failed"
0x18003d02d  mov     r8d, edi
0x18003d030  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d035  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d039  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003d03f  lea     r14, [rbx+48h]
0x18003d043  mov     rcx, r14; this
0x18003d046  call    ?Initialize@CVssSecurityDescriptor@@QEAAJXZ; CVssSecurityDescriptor::Initialize(void)
0x18003d04b  mov     edi, eax
0x18003d04d  mov     [rbp+2F0h+var_2A8], eax
0x18003d050  test    eax, eax
0x18003d052  jns     short loc_18003D0B9
0x18003d054  mov     [rsp+3F0h+var_3D0], r12
0x18003d059  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d060  mov     [rsp+3F0h+var_3C8], r15
0x18003d065  lea     r12, aSecsecrc; "SECSECRC"
0x18003d06c  mov     [rsp+3F0h+var_3C0], r12
0x18003d071  mov     [rsp+3F0h+var_3B8], 63Fh
0x18003d079  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d081  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d089  mov     [rbp+2F0h+var_330], 1000000h
0x18003d090  xor     edx, edx; Val
0x18003d092  lea     r8d, [rdx+78h]; Size
0x18003d096  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d09b  call    memset_0
0x18003d0a0  lea     r9, aMSdbothInitial; "m_SDBoth.Initialize() failed"
0x18003d0a7  mov     r8d, edi
0x18003d0aa  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d0af  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d0b3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003d0b9  mov     [rbp+2F0h+var_2D8], r13
0x18003d0bd  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003d0c4  mov     [rbp+2F0h+var_2E0], rax
0x18003d0c8  mov     edx, 16h; enum WELL_KNOWN_SID_TYPE
0x18003d0cd  lea     rcx, [rbp+2F0h+var_2E0]; this
0x18003d0d1  call    ?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z; CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)
0x18003d0d6  mov     r12, [rbp+2F0h+var_2D8]
0x18003d0da  mov     rdx, r12; void *
0x18003d0dd  mov     rcx, r15; this
0x18003d0e0  call    ?SetOwner@CVssSecurityDescriptor@@QEAAJPEAXH@Z; CVssSecurityDescriptor::SetOwner(void *,int)
0x18003d0e5  mov     edi, eax
0x18003d0e7  mov     [rbp+2F0h+var_2A8], eax
0x18003d0ea  test    eax, eax
0x18003d0ec  jns     short loc_18003D15A
0x18003d0ee  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d0f5  mov     [rsp+3F0h+var_3D0], r14
0x18003d0fa  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d101  mov     [rsp+3F0h+var_3C8], r15
0x18003d106  lea     r12, aSecsecrc; "SECSECRC"
0x18003d10d  mov     [rsp+3F0h+var_3C0], r12
0x18003d112  mov     [rsp+3F0h+var_3B8], 64Dh
0x18003d11a  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d122  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d12a  mov     [rbp+2F0h+var_330], 1000000h
0x18003d131  xor     edx, edx; Val
0x18003d133  lea     r8d, [rdx+78h]; Size
0x18003d137  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d13c  call    memset_0
0x18003d141  lea     r9, aSetowner; "SetOwner"
0x18003d148  mov     r8d, edi
0x18003d14b  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d150  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d154  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003d15a  mov     rdx, r12; void *
0x18003d15d  mov     rcx, rsi; this
0x18003d160  call    ?SetOwner@CVssSecurityDescriptor@@QEAAJPEAXH@Z; CVssSecurityDescriptor::SetOwner(void *,int)
0x18003d165  mov     edi, eax
0x18003d167  mov     [rbp+2F0h+var_2A8], eax
0x18003d16a  test    eax, eax
0x18003d16c  jns     short loc_18003D1DA
0x18003d16e  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d175  mov     [rsp+3F0h+var_3D0], r14
0x18003d17a  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d181  mov     [rsp+3F0h+var_3C8], r15
0x18003d186  lea     r12, aSecsecrc; "SECSECRC"
0x18003d18d  mov     [rsp+3F0h+var_3C0], r12
0x18003d192  mov     [rsp+3F0h+var_3B8], 650h
0x18003d19a  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d1a2  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d1aa  mov     [rbp+2F0h+var_330], 1000000h
0x18003d1b1  xor     edx, edx; Val
0x18003d1b3  lea     r8d, [rdx+78h]; Size
0x18003d1b7  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d1bc  call    memset_0
0x18003d1c1  lea     r9, aSetowner; "SetOwner"
0x18003d1c8  mov     r8d, edi
0x18003d1cb  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d1d0  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d1d4  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003d1da  mov     rdx, r12; void *
0x18003d1dd  mov     rcx, r14; this
0x18003d1e0  call    ?SetOwner@CVssSecurityDescriptor@@QEAAJPEAXH@Z; CVssSecurityDescriptor::SetOwner(void *,int)
0x18003d1e5  mov     edi, eax
0x18003d1e7  mov     [rbp+2F0h+var_2A8], eax
0x18003d1ea  test    eax, eax
0x18003d1ec  jns     short loc_18003D25A
0x18003d1ee  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d1f5  mov     [rsp+3F0h+var_3D0], r14
0x18003d1fa  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d201  mov     [rsp+3F0h+var_3C8], r15
0x18003d206  lea     r12, aSecsecrc; "SECSECRC"
0x18003d20d  mov     [rsp+3F0h+var_3C0], r12
0x18003d212  mov     [rsp+3F0h+var_3B8], 653h
0x18003d21a  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d222  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d22a  mov     [rbp+2F0h+var_330], 1000000h
0x18003d231  xor     edx, edx; Val
0x18003d233  lea     r8d, [rdx+78h]; Size
0x18003d237  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d23c  call    memset_0
0x18003d241  lea     r9, aSetowner; "SetOwner"
0x18003d248  mov     r8d, edi
0x18003d24b  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d250  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d254  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003d25a  mov     [rbp+2F0h+var_2E8], r13
0x18003d25e  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003d265  mov     [rbp+2F0h+var_2F0], rax
0x18003d269  mov     edx, 1Ah; enum WELL_KNOWN_SID_TYPE
0x18003d26e  lea     rcx, [rbp+2F0h+var_2F0]; this
0x18003d272  call    ?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z; CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)
0x18003d277  mov     r12, [rbp+2F0h+var_2E8]
0x18003d27b  mov     rdx, r12; void *
0x18003d27e  mov     rcx, r15; this
0x18003d281  call    ?SetGroup@CVssSecurityDescriptor@@QEAAJPEAXH@Z; CVssSecurityDescriptor::SetGroup(void *,int)
0x18003d286  mov     edi, eax
0x18003d288  mov     [rbp+2F0h+var_2A8], eax
0x18003d28b  test    eax, eax
0x18003d28d  jns     short loc_18003D2FB
0x18003d28f  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d296  mov     [rsp+3F0h+var_3D0], r14
0x18003d29b  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d2a2  mov     [rsp+3F0h+var_3C8], r15
0x18003d2a7  lea     r12, aSecsecrc; "SECSECRC"
0x18003d2ae  mov     [rsp+3F0h+var_3C0], r12
0x18003d2b3  mov     [rsp+3F0h+var_3B8], 65Eh
0x18003d2bb  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d2c3  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d2cb  mov     [rbp+2F0h+var_330], 1000000h
0x18003d2d2  xor     edx, edx; Val
0x18003d2d4  lea     r8d, [rdx+78h]; Size
0x18003d2d8  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d2dd  call    memset_0
0x18003d2e2  lea     r9, aSetgroup; "SetGroup"
0x18003d2e9  mov     r8d, edi
0x18003d2ec  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d2f1  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d2f5  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003d2fb  mov     rdx, r12; void *
0x18003d2fe  mov     rcx, rsi; this
0x18003d301  call    ?SetGroup@CVssSecurityDescriptor@@QEAAJPEAXH@Z; CVssSecurityDescriptor::SetGroup(void *,int)
0x18003d306  mov     edi, eax
0x18003d308  mov     [rbp+2F0h+var_2A8], eax
0x18003d30b  test    eax, eax
0x18003d30d  jns     short loc_18003D37B
0x18003d30f  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d316  mov     [rsp+3F0h+var_3D0], r14
0x18003d31b  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d322  mov     [rsp+3F0h+var_3C8], r15
0x18003d327  lea     r12, aSecsecrc; "SECSECRC"
0x18003d32e  mov     [rsp+3F0h+var_3C0], r12
0x18003d333  mov     [rsp+3F0h+var_3B8], 661h
0x18003d33b  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d343  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d34b  mov     [rbp+2F0h+var_330], 1000000h
0x18003d352  xor     edx, edx; Val
0x18003d354  lea     r8d, [rdx+78h]; Size
0x18003d358  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d35d  call    memset_0
0x18003d362  lea     r9, aSetgroup; "SetGroup"
0x18003d369  mov     r8d, edi
0x18003d36c  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d371  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d375  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003d37b  mov     rdx, r12; void *
0x18003d37e  mov     rcx, r14; this
0x18003d381  call    ?SetGroup@CVssSecurityDescriptor@@QEAAJPEAXH@Z; CVssSecurityDescriptor::SetGroup(void *,int)
0x18003d386  mov     edi, eax
0x18003d388  mov     [rbp+2F0h+var_2A8], eax
0x18003d38b  test    eax, eax
0x18003d38d  jns     short loc_18003D3FB
0x18003d38f  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003d396  mov     [rsp+3F0h+var_3D0], r14
0x18003d39b  lea     r15, aCvsssidcollect_2; "CVssSidCollection::Initialize"
0x18003d3a2  mov     [rsp+3F0h+var_3C8], r15
0x18003d3a7  lea     r12, aSecsecrc; "SECSECRC"
0x18003d3ae  mov     [rsp+3F0h+var_3C0], r12
0x18003d3b3  mov     [rsp+3F0h+var_3B8], 664h
0x18003d3bb  mov     [rsp+3F0h+var_3B4], 0Bh
0x18003d3c3  mov     [rsp+3F0h+var_3B0], 0FFh
0x18003d3cb  mov     [rbp+2F0h+var_330], 1000000h
0x18003d3d2  xor     edx, edx; Val
0x18003d3d4  lea     r8d, [rdx+78h]; Size
0x18003d3d8  lea     rcx, [rsp+3F0h+var_3A8]; void *
0x18003d3dd  call    memset_0
0x18003d3e2  lea     r9, aSetgroup; "SetGroup"
0x18003d3e9  mov     r8d, edi
0x18003d3ec  lea     rdx, [rsp+3F0h+var_3D0]
0x18003d3f1  lea     rcx, [rbp+2F0h+var_2B0]
0x18003d3f5  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003d3fb  mov     edi, 3
0x18003d400  mov     r8d, edi
0x18003d403  lea     edx, [rdi+17h]
0x18003d406  mov     rcx, rbx
0x18003d409  call    ?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)
0x18003d40e  mov     r8d, edi
0x18003d411  lea     edx, [rdi+13h]
0x18003d414  mov     rcx, rbx
0x18003d417  call    ?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)
0x18003d41c  mov     r8d, edi
0x18003d41f  lea     edx, [rdi+1Eh]
0x18003d422  mov     rcx, rbx
0x18003d425  call    ?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)
0x18003d42a  lea     esi, [rdi-2]
0x18003d42d  mov     r8d, esi
0x18003d430  lea     edx, [rdi+15h]
0x18003d433  mov     rcx, rbx
0x18003d436  call    ?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)
0x18003d43b  mov     r8d, esi
0x18003d43e  lea     edx, [rdi+14h]
0x18003d441  mov     rcx, rbx
0x18003d444  call    ?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)
0x18003d449  mov     [rbp+2F0h+var_2B8], r13
0x18003d44d  lea     rdi, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18003d454  mov     [rbp+2F0h+var_2C0], rdi
  ... truncated ...
```
