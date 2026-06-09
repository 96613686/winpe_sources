# CMMAudioEnum::CreateEnumWasapi(void)

- ea: `0x1800bd820`
- end: `0x1800bde49`
- name: `?CreateEnumWasapi@CMMAudioEnum@@AEAAJXZ`
- size: `1577`
- prototype: `__int64 __fastcall(CMMAudioEnum *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800be040`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000cdb0`
- `0x180011cb0`
- `0x1800123c0`
- `0x180013ec0`
- `0x1800207f8`
- `0x18003c7e0`
- `0x1800bd820`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bdd74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bdd74`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800bdbaf`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800bdbaf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd85c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd8a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdb2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd85c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd8a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdb2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bdd7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bdda6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bdd7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bdda6`

## string_xrefs

- `0x1800bdbc6`: `CLSID`
- `0x1800bd952`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioOutput\TokenEnums\MMAudioOut\`
- `0x1800bdacb`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioOutput\TokenEnums\MMAudioOut\`
- `0x1800bd967`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioInput\TokenEnums\MMAudioIn\`
- `0x1800bdac0`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioInput\TokenEnums\MMAudioIn\`
- `0x1800bdd5c`: `Failed to create audio device (Name=%S, Id=%S), hr = 0x%X. Ignored the device.`
- `0x1800bddde`: `Default DMO audio device token id is %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CMMAudioEnum::CreateEnumWasapi(LPVOID *this)
{
  _QWORD *v2; // rsi
  HRESULT Instance; // ebx
  const wchar_t *v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // esi
  BOOL v7; // r14d
  unsigned __int16 *v8; // rax
  int v9; // ecx
  int v10; // edx
  wchar_t *v11; // r15
  __int64 v12; // rcx
  bool v13; // zf
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rdx
  GUID *v16; // rcx
  const wchar_t *v17; // r9
  const wchar_t *v18; // r8
  const wchar_t *v19; // r8
  const wchar_t *v21; // [rsp+30h] [rbp-59h] BYREF
  __int64 v22; // [rsp+38h] [rbp-51h] BYREF
  __int64 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  LPVOID v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-29h] BYREF
  LPOLESTR lpsz; // [rsp+68h] [rbp-21h] BYREF
  __int64 v29; // [rsp+70h] [rbp-19h] BYREF
  __int64 v30; // [rsp+78h] [rbp-11h] BYREF
  struct ISpDataKey *v31; // [rsp+80h] [rbp-9h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v33; // [rsp+98h] [rbp+Fh]
  unsigned __int16 *v34; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v35; // [rsp+F0h] [rbp+67h] BYREF
  unsigned __int16 *v36; // [rsp+F8h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+100h] [rbp+77h] BYREF
  const wchar_t *v38; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = this + 11;
  Instance = CoCreateInstance(&CLSID_SpObjectTokenEnum, 0, 0x17u, &GUID_06b64f9f_7fda_11d2_b4f2_00c04f797396, this + 11);
  if ( Instance >= 0 )
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v2 + 72LL))(*v2, 0, 0);
  ppv = 0;
  v26 = 0;
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(
                 &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                 0,
                 0x17u,
                 &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                 &ppv);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(LPVOID, bool, __int64, __int64 *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   *((_DWORD *)this + 20) != 0,
                   1,
                   &v26);
  }
  v35 = 0;
  if ( Instance >= 0 )
    Instance = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 24LL))(v26, &v35);
  v25 = 0;
  if ( Instance >= 0 )
  {
    v36 = 0;
    if ( (*(int (__fastcall **)(LPVOID, bool, _QWORD, unsigned __int16 **))(*(_QWORD *)ppv + 32LL))(
           ppv,
           *((_DWORD *)this + 20) != 0,
           0,
           &v36) < 0 )
      Instance = 0;
    else
      Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, LPVOID *))(*(_QWORD *)v36 + 40LL))(v36, &v25);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v36);
  }
  v31 = 0;
  if ( Instance >= 0 && v35 )
  {
    v36 = 0;
    v4 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\TokenEnums\\MMAudioIn\\";
    if ( !*((_DWORD *)this + 20) )
      v4 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioOutput\\TokenEnums\\MMAudioOut\\";
    if ( CSpDynamicString::operator=(&v36, v4) )
    {
      v5 = CSpDynamicString::Length((CSpDynamicString *)&v36);
      CSpDynamicString::TrimToSize((CSpDynamicString *)&v36, v5 - 1);
      Instance = SpSzRegPathToDataKey(HKEY_CURRENT_USER, v36, 1, &v31);
    }
    else
    {
      Instance = -2147024882;
    }
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v36);
  }
  v38 = 0;
  v21 = 0;
  v6 = 0;
  if ( Instance >= 0 )
  {
    while ( v6 < v35 )
    {
      v24 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, v6, &v24);
      v7 = 0;
      pv = 0;
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 40LL))(v24, &pv);
      v8 = (unsigned __int16 *)v25;
      if ( v25 )
      {
        do
        {
          v9 = *(unsigned __int16 *)((char *)v8 + (_BYTE *)pv - (_BYTE *)v25);
          v10 = *v8 - v9;
          if ( v10 )
            break;
          ++v8;
        }
        while ( v9 );
        v7 = v10 == 0;
      }
      *(_OWORD *)pvar = 0;
      v33 = 0;
      v11 = 0;
      v12 = 0;
      v30 = 0;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 32LL))(v24, 0, &v30);
        v12 = v30;
      }
      *(_OWORD *)pvar = 0;
      v33 = 0;
      v13 = Instance == 0;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v12 + 40LL))(
                     v12,
                     &PKEY_Device_FriendlyName,
                     pvar);
        if ( Instance >= 0 )
        {
          v11 = (wchar_t *)pvar[1];
          v23 = 0;
          v14 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\TokenEnums\\MMAudioIn\\";
          if ( !*((_DWORD *)this + 20) )
            v14 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioOutput\\TokenEnums\\MMAudioOut\\";
          CSpDynamicString::AppendHR((CSpDynamicString *)&v23, v14);
          CSpDynamicString::AppendHR((CSpDynamicString *)&v23, (const unsigned __int16 *)pv);
          v29 = 0;
          Instance = ((__int64 (__fastcall *)(struct ISpDataKey *, LPVOID, __int64 *))v31->lpVtbl->CreateKey)(
                       v31,
                       pv,
                       &v29);
          v36 = 0;
          if ( Instance >= 0 )
          {
            Instance = CoCreateInstance(
                         &CLSID_SpObjectToken,
                         0,
                         0x17u,
                         &GUID_b8aab0cf_346f_49d8_9499_c8b03f161d51,
                         (LPVOID *)&v36);
            if ( Instance >= 0 )
            {
              v15 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput";
              if ( !*((_DWORD *)this + 20) )
                v15 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioOutput";
              Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const unsigned __int16 *, __int64, __int64))(*(_QWORD *)v36 + 200LL))(
                           v36,
                           v15,
                           v23,
                           v29);
              if ( Instance >= 0 )
                Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, wchar_t *))(*(_QWORD *)v36 + 40LL))(
                             v36,
                             0,
                             v11);
            }
          }
          lpsz = 0;
          if ( Instance >= 0 )
          {
            v16 = &CLSID_SpMMAudioIn;
            if ( !*((_DWORD *)this + 20) )
              v16 = &CLSID_SpMMAudioOut;
            Instance = StringFromCLSID(v16, &lpsz);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const unsigned __int16 *, LPOLESTR))(*(_QWORD *)v36 + 40LL))(
                           v36,
                           L"CLSID",
                           lpsz);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const wchar_t *, wchar_t *))(*(_QWORD *)v36 + 40LL))(
                             v36,
                             L"DeviceName",
                             v11);
                if ( Instance >= 0 )
                  Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const wchar_t *, LPVOID))(*(_QWORD *)v36 + 40LL))(
                               v36,
                               L"DeviceId",
                               pv);
              }
            }
          }
          v22 = 0;
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const WCHAR *, __int64 *))(*(_QWORD *)v36 + 80LL))(
                         v36,
                         L"Attributes",
                         &v22);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v22 + 40LL))(
                           v22,
                           L"Vendor",
                           L"Microsoft");
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v22 + 40LL))(
                             v22,
                             L"Technology",
                             L"MMSys");
                if ( Instance >= 0 )
                {
                  v34 = v36;
                  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned __int16 **))(*(_QWORD *)this[11] + 80LL))(
                               this[11],
                               1,
                               &v34);
                  if ( Instance >= 0 )
                  {
                    if ( !v38 && v7 )
                      (*(void (__fastcall **)(unsigned __int16 *, const wchar_t **))(*(_QWORD *)v36 + 128LL))(v36, &v38);
                    if ( !v21 && v35 > 1 )
                      (*(void (__fastcall **)(unsigned __int16 *, const wchar_t **))(*(_QWORD *)v36 + 128LL))(v36, &v21);
                  }
                }
              }
            }
          }
          ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v22);
          SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpsz);
          ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v36);
          ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v29);
          SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v23);
        }
        v13 = Instance == 0;
      }
      if ( !v13 )
      {
        v17 = L"<NULL>";
        if ( pv )
          v17 = (const wchar_t *)pv;
        v18 = L"<NULL>";
        if ( v11 )
          v18 = v11;
        DoTraceMessage(
          4,
          "Failed to create audio device (Name=%S, Id=%S), hr = 0x%X. Ignored the device.",
          v18,
          v17,
          Instance);
        Instance = 0;
      }
      PropVariantClear(pvar);
      CoTaskMemFree(pv);
      pv = 0;
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v30);
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v24);
      ++v6;
    }
  }
  CoTaskMemFree(v25);
  v25 = 0;
  v19 = v38;
  if ( !v38 )
  {
    DoTraceMessage(4, "Could not find the audio device that matches the default device. Use the first available device");
    v19 = v21;
    v21 = 0;
    v38 = v19;
  }
  if ( Instance >= 0 && v19 )
  {
    DoTraceMessage(16, "Default DMO audio device token id is %S", v19);
    (*(void (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)this[11] + 104LL))(this[11], v38);
  }
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v21);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v38);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v31);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v26);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800bd820  push    rbp
0x1800bd822  push    rbx
0x1800bd823  push    rsi
0x1800bd824  push    rdi
0x1800bd825  push    r12
0x1800bd827  push    r14
0x1800bd829  push    r15
0x1800bd82b  lea     rbp, [rsp-27h]
0x1800bd830  sub     rsp, 0B0h
0x1800bd837  mov     rdi, rcx
0x1800bd83a  lea     rsi, [rcx+58h]
0x1800bd83e  mov     [rsp+0E0h+ppv], rsi; ppv
0x1800bd843  lea     r9, _GUID_06b64f9f_7fda_11d2_b4f2_00c04f797396; riid
0x1800bd84a  mov     r14d, 17h
0x1800bd850  mov     r8d, r14d; dwClsContext
0x1800bd853  xor     edx, edx; pUnkOuter
0x1800bd855  lea     rcx, CLSID_SpObjectTokenEnum; rclsid
0x1800bd85c  call    cs:__imp_CoCreateInstance
0x1800bd862  mov     ebx, eax
0x1800bd864  xor     r12d, r12d
0x1800bd867  test    eax, eax
0x1800bd869  js      short loc_1800BD881
0x1800bd86b  mov     rcx, [rsi]
0x1800bd86e  mov     rax, [rcx]
0x1800bd871  xor     r8d, r8d
0x1800bd874  xor     edx, edx
0x1800bd876  mov     rax, [rax+48h]
0x1800bd87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd87f  mov     ebx, eax
0x1800bd881  mov     [rbp+57h+var_80], r12
0x1800bd885  mov     [rbp+57h+var_88], r12
0x1800bd889  test    ebx, ebx
0x1800bd88b  js      short loc_1800BD8DB
0x1800bd88d  lea     rax, [rbp+57h+var_80]
0x1800bd891  mov     [rsp+0E0h+ppv], rax; ppv
0x1800bd896  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800bd89d  mov     r8d, r14d; dwClsContext
0x1800bd8a0  xor     edx, edx; pUnkOuter
0x1800bd8a2  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800bd8a9  call    cs:__imp_CoCreateInstance
0x1800bd8af  mov     ebx, eax
0x1800bd8b1  test    eax, eax
0x1800bd8b3  js      short loc_1800BD8DB
0x1800bd8b5  mov     rcx, [rbp+57h+var_80]
0x1800bd8b9  mov     rax, [rcx]
0x1800bd8bc  mov     edx, r12d
0x1800bd8bf  cmp     [rdi+50h], r12d
0x1800bd8c3  setnz   dl
0x1800bd8c6  lea     r9, [rbp+57h+var_88]
0x1800bd8ca  mov     r8d, 1
0x1800bd8d0  mov     rax, [rax+18h]
0x1800bd8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8d9  mov     ebx, eax
0x1800bd8db  mov     [rbp+57h+arg_0], r12d
0x1800bd8df  test    ebx, ebx
0x1800bd8e1  js      short loc_1800BD8F9
0x1800bd8e3  mov     rcx, [rbp+57h+var_88]
0x1800bd8e7  mov     rax, [rcx]
0x1800bd8ea  lea     rdx, [rbp+57h+arg_0]
0x1800bd8ee  mov     rax, [rax+18h]
0x1800bd8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8f7  mov     ebx, eax
0x1800bd8f9  mov     [rbp+57h+var_90], r12
0x1800bd8fd  test    ebx, ebx
0x1800bd8ff  js      short loc_1800BD94E
0x1800bd901  mov     [rbp+57h+arg_8], r12
0x1800bd905  mov     rcx, [rbp+57h+var_80]
0x1800bd909  mov     rax, [rcx]
0x1800bd90c  mov     edx, r12d
0x1800bd90f  cmp     [rdi+50h], r12d
0x1800bd913  setnz   dl
0x1800bd916  lea     r9, [rbp+57h+arg_8]
0x1800bd91a  xor     r8d, r8d
0x1800bd91d  mov     rax, [rax+20h]
0x1800bd921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd926  test    eax, eax
0x1800bd928  js      short loc_1800BD942
0x1800bd92a  mov     rcx, [rbp+57h+arg_8]
0x1800bd92e  mov     rax, [rcx]
0x1800bd931  lea     rdx, [rbp+57h+var_90]
0x1800bd935  mov     rax, [rax+28h]
0x1800bd939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd93e  mov     ebx, eax
0x1800bd940  jmp     short loc_1800BD945
0x1800bd942  mov     ebx, r12d
0x1800bd945  lea     rcx, [rbp+57h+arg_8]
0x1800bd949  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800bd94e  mov     [rbp+57h+var_60], r12
0x1800bd952  lea     rax, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd959  test    ebx, ebx
0x1800bd95b  js      short loc_1800BD9C5
0x1800bd95d  cmp     [rbp+57h+arg_0], 1
0x1800bd961  jb      short loc_1800BD9C5
0x1800bd963  mov     [rbp+57h+arg_8], r12
0x1800bd967  lea     rdx, aHkeyLocalMachi_9; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd96e  cmp     [rdi+50h], r12d
0x1800bd972  cmovz   rdx, rax
0x1800bd976  lea     rcx, [rbp+57h+arg_8]
0x1800bd97a  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800bd97f  test    rax, rax
0x1800bd982  jnz     short loc_1800BD98B
0x1800bd984  mov     ebx, 8007000Eh
0x1800bd989  jmp     short loc_1800BD9BC
0x1800bd98b  lea     rcx, [rbp+57h+arg_8]; this
0x1800bd98f  call    ?Length@CSpDynamicString@@QEBAIXZ; CSpDynamicString::Length(void)
0x1800bd994  lea     edx, [rax-1]; unsigned int
0x1800bd997  lea     rcx, [rbp+57h+arg_8]; this
0x1800bd99b  call    ?TrimToSize@CSpDynamicString@@QEAAXK@Z; CSpDynamicString::TrimToSize(ulong)
0x1800bd9a0  lea     r9, [rbp+57h+var_60]; struct ISpDataKey **
0x1800bd9a4  mov     r8d, 1; int
0x1800bd9aa  mov     rdx, [rbp+57h+arg_8]; unsigned __int16 *
0x1800bd9ae  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800bd9b5  call    ?SpSzRegPathToDataKey@@YAJPEAUHKEY__@@PEBGHPEAPEAUISpDataKey@@@Z; SpSzRegPathToDataKey(HKEY__ *,ushort const *,int,ISpDataKey * *)
0x1800bd9ba  mov     ebx, eax
0x1800bd9bc  lea     rcx, [rbp+57h+arg_8]; this
0x1800bd9c0  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800bd9c5  mov     [rbp+57h+arg_18], r12
0x1800bd9c9  mov     [rbp+57h+var_B0], r12
0x1800bd9cd  mov     esi, r12d
0x1800bd9d0  test    ebx, ebx
0x1800bd9d2  js      loc_1800BDDA2
0x1800bd9d8  cmp     esi, [rbp+57h+arg_0]
0x1800bd9db  jnb     loc_1800BDDA2
0x1800bd9e1  mov     [rbp+57h+var_98], r12
0x1800bd9e5  mov     rcx, [rbp+57h+var_88]
0x1800bd9e9  mov     rax, [rcx]
0x1800bd9ec  lea     r8, [rbp+57h+var_98]
0x1800bd9f0  mov     edx, esi
0x1800bd9f2  mov     rax, [rax+20h]
0x1800bd9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9fb  mov     ebx, eax
0x1800bd9fd  mov     r14d, r12d
0x1800bda00  mov     [rbp+57h+pv], r12
0x1800bda04  test    eax, eax
0x1800bda06  js      short loc_1800BDA1E
0x1800bda08  mov     rcx, [rbp+57h+var_98]
0x1800bda0c  mov     rax, [rcx]
0x1800bda0f  lea     rdx, [rbp+57h+pv]
0x1800bda13  mov     rax, [rax+28h]
0x1800bda17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda1c  mov     ebx, eax
0x1800bda1e  mov     rax, [rbp+57h+var_90]
0x1800bda22  test    rax, rax
0x1800bda25  jz      short loc_1800BDA4B
0x1800bda27  mov     r8, [rbp+57h+pv]
0x1800bda2b  sub     r8, rax
0x1800bda2e  movzx   edx, word ptr [rax]
0x1800bda31  movzx   ecx, word ptr [rax+r8]
0x1800bda36  sub     edx, ecx
0x1800bda38  jnz     short loc_1800BDA42
0x1800bda3a  add     rax, 2
0x1800bda3e  test    ecx, ecx
0x1800bda40  jnz     short loc_1800BDA2E
0x1800bda42  mov     r14d, r12d
0x1800bda45  test    edx, edx
0x1800bda47  setz    r14b
0x1800bda4b  xorps   xmm0, xmm0
0x1800bda4e  xor     eax, eax
0x1800bda50  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800bda54  mov     [rbp+57h+var_48], rax
0x1800bda58  mov     r15, r12
0x1800bda5b  mov     rcx, r12
0x1800bda5e  mov     [rbp+57h+var_68], rcx
0x1800bda62  test    ebx, ebx
0x1800bda64  js      short loc_1800BDA82
0x1800bda66  mov     rcx, [rbp+57h+var_98]
0x1800bda6a  mov     rax, [rcx]
0x1800bda6d  lea     r8, [rbp+57h+var_68]
0x1800bda71  xor     edx, edx
0x1800bda73  mov     rax, [rax+20h]
0x1800bda77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda7c  mov     ebx, eax
0x1800bda7e  mov     rcx, [rbp+57h+var_68]
0x1800bda82  xorps   xmm0, xmm0
0x1800bda85  xor     eax, eax
0x1800bda87  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800bda8b  mov     [rbp+57h+var_48], rax
0x1800bda8f  test    ebx, ebx
0x1800bda91  js      loc_1800BDD36
0x1800bda97  mov     rax, [rcx]
0x1800bda9a  lea     r8, [rbp+57h+pvar]
0x1800bda9e  lea     rdx, PKEY_Device_FriendlyName
0x1800bdaa5  mov     rax, [rax+28h]
0x1800bdaa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdaae  mov     ebx, eax
0x1800bdab0  test    eax, eax
0x1800bdab2  js      loc_1800BDD34
0x1800bdab8  mov     r15, [rbp+57h+pvar+8]
0x1800bdabc  mov     [rbp+57h+var_A0], r12
0x1800bdac0  lea     rdx, aHkeyLocalMachi_9; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bdac7  cmp     [rdi+50h], r12d
0x1800bdacb  lea     rax, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bdad2  cmovz   rdx, rax; Src
0x1800bdad6  lea     rcx, [rbp+57h+var_A0]; this
0x1800bdada  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x1800bdadf  mov     rdx, [rbp+57h+pv]; Src
0x1800bdae3  lea     rcx, [rbp+57h+var_A0]; this
0x1800bdae7  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x1800bdaec  mov     [rbp+57h+var_70], r12
0x1800bdaf0  mov     rcx, [rbp+57h+var_60]
0x1800bdaf4  mov     rax, [rcx]
0x1800bdaf7  lea     r8, [rbp+57h+var_70]
0x1800bdafb  mov     rdx, [rbp+57h+pv]
0x1800bdaff  mov     rax, [rax+50h]
0x1800bdb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdb08  mov     ebx, eax
0x1800bdb0a  mov     [rbp+57h+arg_8], r12
0x1800bdb0e  test    eax, eax
0x1800bdb10  js      short loc_1800BDB89
0x1800bdb12  lea     rax, [rbp+57h+arg_8]
0x1800bdb16  mov     [rsp+0E0h+ppv], rax; ppv
0x1800bdb1b  lea     r9, _GUID_b8aab0cf_346f_49d8_9499_c8b03f161d51; riid
0x1800bdb22  xor     edx, edx; pUnkOuter
0x1800bdb24  lea     r8d, [rdx+17h]; dwClsContext
0x1800bdb28  lea     rcx, CLSID_SpObjectToken; rclsid
0x1800bdb2f  call    cs:__imp_CoCreateInstance
0x1800bdb35  mov     ebx, eax
0x1800bdb37  test    eax, eax
0x1800bdb39  js      short loc_1800BDB89
0x1800bdb3b  mov     rcx, [rbp+57h+arg_8]
0x1800bdb3f  mov     rax, [rcx]
0x1800bdb42  lea     r8, aHkeyLocalMachi_12; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bdb49  lea     rdx, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bdb50  cmp     [rdi+50h], r12d
0x1800bdb54  cmovz   rdx, r8
0x1800bdb58  mov     r9, [rbp+57h+var_70]
0x1800bdb5c  mov     r8, [rbp+57h+var_A0]
0x1800bdb60  mov     rax, [rax+0C8h]
0x1800bdb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdb6c  mov     ebx, eax
0x1800bdb6e  test    eax, eax
0x1800bdb70  js      short loc_1800BDB89
0x1800bdb72  mov     rcx, [rbp+57h+arg_8]
0x1800bdb76  mov     rax, [rcx]
0x1800bdb79  mov     r8, r15
0x1800bdb7c  xor     edx, edx
0x1800bdb7e  mov     rax, [rax+28h]
0x1800bdb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdb87  mov     ebx, eax
0x1800bdb89  mov     [rbp+57h+lpsz], r12
0x1800bdb8d  test    ebx, ebx
0x1800bdb8f  js      loc_1800BDC19
0x1800bdb95  lea     rax, CLSID_SpMMAudioOut
0x1800bdb9c  lea     rcx, CLSID_SpMMAudioIn
0x1800bdba3  cmp     [rdi+50h], r12d
0x1800bdba7  cmovz   rcx, rax; rclsid
0x1800bdbab  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800bdbaf  call    cs:__imp_StringFromCLSID
0x1800bdbb5  mov     ebx, eax
0x1800bdbb7  test    eax, eax
0x1800bdbb9  js      short loc_1800BDC19
0x1800bdbbb  mov     rcx, [rbp+57h+arg_8]
0x1800bdbbf  mov     rax, [rcx]
0x1800bdbc2  mov     r8, [rbp+57h+lpsz]
0x1800bdbc6  lea     rdx, aClsid_0; "CLSID"
0x1800bdbcd  mov     rax, [rax+28h]
0x1800bdbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdbd6  mov     ebx, eax
0x1800bdbd8  test    eax, eax
0x1800bdbda  js      short loc_1800BDC19
0x1800bdbdc  mov     rcx, [rbp+57h+arg_8]
0x1800bdbe0  mov     rax, [rcx]
0x1800bdbe3  mov     r8, r15
0x1800bdbe6  lea     rdx, aDevicename; "DeviceName"
0x1800bdbed  mov     rax, [rax+28h]
0x1800bdbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdbf6  mov     ebx, eax
0x1800bdbf8  test    eax, eax
0x1800bdbfa  js      short loc_1800BDC19
0x1800bdbfc  mov     rcx, [rbp+57h+arg_8]
0x1800bdc00  mov     rax, [rcx]
0x1800bdc03  mov     r8, [rbp+57h+pv]
0x1800bdc07  lea     rdx, aDeviceid_0; "DeviceId"
0x1800bdc0e  mov     rax, [rax+28h]
0x1800bdc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc17  mov     ebx, eax
0x1800bdc19  mov     [rbp+57h+var_A8], r12
0x1800bdc1d  test    ebx, ebx
0x1800bdc1f  js      loc_1800BDD03
0x1800bdc25  mov     rcx, [rbp+57h+arg_8]
0x1800bdc29  mov     rax, [rcx]
0x1800bdc2c  lea     r8, [rbp+57h+var_A8]
0x1800bdc30  lea     rdx, aAttributes_0; "Attributes"
0x1800bdc37  mov     rax, [rax+50h]
0x1800bdc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc40  mov     ebx, eax
0x1800bdc42  test    eax, eax
0x1800bdc44  js      loc_1800BDD03
0x1800bdc4a  mov     rcx, [rbp+57h+var_A8]
0x1800bdc4e  mov     rax, [rcx]
0x1800bdc51  lea     r8, aMicrosoft; "Microsoft"
0x1800bdc58  lea     rdx, aVendor; "Vendor"
0x1800bdc5f  mov     rax, [rax+28h]
0x1800bdc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc68  mov     ebx, eax
0x1800bdc6a  test    eax, eax
0x1800bdc6c  js      loc_1800BDD03
0x1800bdc72  mov     rcx, [rbp+57h+var_A8]
0x1800bdc76  mov     rax, [rcx]
0x1800bdc79  lea     r8, aMmsys; "MMSys"
  ... truncated ...
```
