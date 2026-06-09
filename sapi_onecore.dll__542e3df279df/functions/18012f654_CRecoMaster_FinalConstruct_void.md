# CRecoMaster::FinalConstruct(void)

- ea: `0x18012f654`
- end: `0x18012fc27`
- name: `?FinalConstruct@CRecoMaster@@QEAAJXZ`
- size: `1491`
- prototype: `__int64 __fastcall(CRecoMaster *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008cf14`
- `0x180090818`

## callees

- `0x18000e518`
- `0x18001f27c`
- `0x1800243e8`
- `0x180026508`
- `0x18002895c`
- `0x180061c40`
- `0x18006e710`
- `0x18007a374`
- `0x180094190`
- `0x1800b6dc8`
- `0x18012cf3c`
- `0x18012ea20`
- `0x18012eb34`
- `0x18012f654`
- `0x1801306b8`
- `0x18015f73c`
- `0x18018d400`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18012fbdc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18012fbdc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012f730`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012f788`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012f730`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012f788`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18012f9b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18012f9b3`

## string_xrefs

- `0x18012fa85`: `ServiceSideEndpointing`
- `0x18012f685`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f6c0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f6f8`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f744`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f79c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f7e7`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f825`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f85e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f8d4`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f912`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f98d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012f9ef`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012fa22`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012fa55`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012faa0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012fb03`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012fb51`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012fb9f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x18012fbf0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecoMaster::FinalConstruct(CRecoMaster *this, struct _SECURITY_ATTRIBUTES *a2)
{
  int inited; // eax
  struct _SECURITY_ATTRIBUTES *v4; // rdx
  unsigned int v5; // ebx
  __int64 result; // rax
  int v7; // eax
  struct _SECURITY_ATTRIBUTES *v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  HRESULT Instance; // eax
  unsigned int v13; // ebx
  struct IUnknown **v14; // r14
  HRESULT v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  LARGE_INTEGER v24; // rbx
  CSpEngineProxy *v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  _QWORD *v28; // rbx
  int v29; // eax
  unsigned int v30; // esi
  struct IUnknown **v31; // rcx
  int v32; // eax
  unsigned int v33; // ebx
  void *v34; // r8
  int v35; // eax
  void *v36; // r8
  unsigned int v37; // ebx
  int v38; // eax
  void *v39; // r8
  unsigned int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  OneSettingsPolicyWrapper **v43; // rax
  int DWORDValue; // eax
  OneSettingsPolicyWrapper **v45; // rax
  int v46; // eax
  OneSettingsPolicyWrapper **v47; // rax
  int v48; // eax
  OneSettingsPolicyWrapper **v49; // rax
  int v50; // eax
  IUnknown *v51; // rax
  HRESULT FreeThreadedMarshaler; // eax
  unsigned int v53; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-38h]
  LPVOID *ppva; // [rsp+20h] [rbp-38h]
  LPVOID *ppvb; // [rsp+20h] [rbp-38h]
  int ppvc; // [rsp+20h] [rbp-38h]
  int ppvd; // [rsp+20h] [rbp-38h]
  int ppve; // [rsp+20h] [rbp-38h]
  int ppvf; // [rsp+20h] [rbp-38h]
  _BYTE v61[8]; // [rsp+30h] [rbp-28h] BYREF
  std::_Ref_count_base *v62; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LARGE_INTEGER Frequency; // [rsp+60h] [rbp+8h] BYREF
  __int64 v65; // [rsp+68h] [rbp+10h] BYREF

  inited = CSpAutoEvent::InitEvent((CRecoMaster *)((char *)this + 336), a2, 1, 0, (const unsigned __int16 *)ppv);
  v5 = inited;
  if ( inited >= 0 )
  {
    v7 = CSpAutoEvent::InitEvent((CRecoMaster *)((char *)this + 872), v4, 1, 1, (const unsigned __int16 *)ppva);
    v9 = v7;
    if ( v7 >= 0 )
    {
      v10 = CSpAutoEvent::InitEvent((CRecoMaster *)((char *)this + 352), v8, 0, 0, (const unsigned __int16 *)ppvb);
      v11 = v10;
      if ( v10 >= 0 )
      {
        Instance = CoCreateInstance(
                     &CLSID_SpCFGEngine,
                     0,
                     0x17u,
                     &GUID_c83212d3_d5c9_408c_b353_311896878897,
                     (LPVOID *)this + 97);
        v13 = Instance;
        if ( Instance >= 0 )
        {
          try
          {
            *((_QWORD *)CEntityStore::Instance() + 1) = *((_QWORD *)this + 97);
            v14 = (struct IUnknown **)((char *)this + 760);
            v15 = CoCreateInstance(
                    &CLSID_SpResourceManager,
                    0,
                    0x17u,
                    &GUID_2baeef81_2ca3_4331_98f3_26ec5abefb03,
                    (LPVOID *)this + 95);
            v16 = v15;
            if ( v15 >= 0 )
            {
              ppvf = (_DWORD)this + 768;
              v18 = ((__int64 (__fastcall *)(struct IUnknown *, char *, _QWORD, _QWORD))(*v14)->lpVtbl[2].AddRef)(
                      *v14,
                      (char *)this + 8,
                      0,
                      0);
              v19 = v18;
              if ( v18 >= 0 )
              {
                v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 96) + 32LL))(
                        *((_QWORD *)this + 96),
                        0,
                        (char *)this + 1032);
                v21 = v20;
                if ( v20 >= 0 )
                {
                  Frequency.QuadPart = 0;
                  v22 = ATL::CComObject<CRecoMasterSite>::CreateInstance(&Frequency);
                  v23 = v22;
                  if ( v22 >= 0 )
                  {
                    v24 = Frequency;
                    if ( *((_QWORD *)this + 98) != Frequency.QuadPart )
                      ATL::AtlComPtrAssign((struct IUnknown **)this + 98, (struct IUnknown *)Frequency.QuadPart);
                    *(_QWORD *)(v24.QuadPart + 88) = this;
                    Frequency.QuadPart = (LONGLONG)operator new(0x68u);
                    v25 = CSpEngineProxy::CSpEngineProxy((CSpEngineProxy *)Frequency.QuadPart);
                    std::shared_ptr<CSpEngineProxy>::reset<CSpEngineProxy,0>((char *)this + 792, v25);
                    v26 = CPhoneCallHandler::Initialize((CRecoMaster *)((char *)this + 1608));
                    v27 = v26;
                    if ( v26 >= 0 )
                    {
                      v65 = 0;
                      v28 = (_QWORD *)((char *)this + 848);
                      v29 = ATL::CComObject<CNotifyProxy>::CreateInstance((char *)this + 848);
                      v30 = v29;
                      if ( v29 >= 0 )
                      {
                        if ( !*v28 )
                          goto LABEL_28;
                        *(_QWORD *)(*v28 + 64LL) = (char *)this + 16;
                        *(_QWORD *)(*v28 + 72LL) = &CRecoMaster::AudioEventId;
                        *(_DWORD *)(*v28 + 80LL) = *((_DWORD *)this + 26);
                        v31 = (struct IUnknown **)(*v28 + 88LL);
                        if ( *v31 != *v14 )
                          ATL::AtlComPtrAssign(v31, *v14);
                        v32 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v28)(
                                *v28,
                                &GUID_259684dc_37c3_11d2_9603_00c04f8ee628,
                                &v65);
                        v33 = v32;
                        if ( v32 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xE1,
                            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                            (const char *)(unsigned int)v32,
                            ppvf);
                          result = v33;
                        }
                        else
                        {
LABEL_28:
                          Frequency.QuadPart = 0;
                          QueryPerformanceFrequency(&Frequency);
                          *((double *)this + 36) = 10000000.0 / (double)(int)Frequency.LowPart;
                          v35 = CRecoMaster::AddCategory(this, SPCT_COMMAND, v34);
                          v37 = v35;
                          if ( v35 >= 0 )
                          {
                            v38 = CRecoMaster::AddCategory(this, SPCT_DICTATION, v36);
                            v40 = v38;
                            if ( v38 >= 0 )
                            {
                              v41 = CRecoMaster::AddCategory(this, SPCT_SLEEP, v39);
                              v42 = v41;
                              if ( v41 >= 0 )
                              {
                                Frequency.LowPart = 0;
                                v43 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(v61);
                                DWORDValue = OneSettingsPolicyWrapper::GetDWORDValue(
                                               *v43,
                                               L"ServiceSideEndpointing",
                                               (unsigned int *)&Frequency);
                                if ( DWORDValue < 0 )
                                  wil::details::in1diag3::_Log_Hr(
                                    retaddr,
                                    (void *)0xF2,
                                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                    (const char *)(unsigned int)DWORDValue,
                                    ppvf);
                                if ( v62 )
                                  std::_Ref_count_base::_Decref(v62);
                                *((_BYTE *)this + 964) = Frequency.LowPart != 0;
                                *((_BYTE *)this + 965) = 1;
                                v45 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(v61);
                                v46 = OneSettingsPolicyWrapper::GetDWORDValue(
                                        *v45,
                                        L"MaxAvailabilityAssuranceDuration",
                                        (unsigned int *)this + 243);
                                if ( v46 < 0 )
                                  wil::details::in1diag3::_Log_Hr(
                                    retaddr,
                                    (void *)0xF7,
                                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                    (const char *)(unsigned int)v46,
                                    ppvf);
                                if ( v62 )
                                  std::_Ref_count_base::_Decref(v62);
                                v47 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(v61);
                                v48 = OneSettingsPolicyWrapper::GetDWORDValue(
                                        *v47,
                                        L"AvailabilityAssuranceEnabled",
                                        (unsigned int *)this + 244);
                                if ( v48 < 0 )
                                  wil::details::in1diag3::_Log_Hr(
                                    retaddr,
                                    (void *)0xF8,
                                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                    (const char *)(unsigned int)v48,
                                    ppvf);
                                if ( v62 )
                                  std::_Ref_count_base::_Decref(v62);
                                v49 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(v61);
                                v50 = OneSettingsPolicyWrapper::GetDWORDValue(
                                        *v49,
                                        L"EndAvailabilityAssuranceTimerDueTime",
                                        (unsigned int *)this + 245);
                                if ( v50 < 0 )
                                  wil::details::in1diag3::_Log_Hr(
                                    retaddr,
                                    (void *)0xF9,
                                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                    (const char *)(unsigned int)v50,
                                    ppvf);
                                if ( v62 )
                                  std::_Ref_count_base::_Decref(v62);
                                v51 = (IUnknown *)(*(__int64 (__fastcall **)(CRecoMaster *))(*(_QWORD *)this + 376LL))(this);
                                FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v51, (LPUNKNOWN *)this + 130);
                                v53 = FreeThreadedMarshaler;
                                if ( FreeThreadedMarshaler >= 0 )
                                {
                                  *((_DWORD *)this + 31) = CRecoMaster::GetDeviceFamily(this);
                                  result = 0;
                                }
                                else
                                {
                                  wil::details::in1diag3::Return_Hr(
                                    retaddr,
                                    (void *)0xFC,
                                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                    (const char *)(unsigned int)FreeThreadedMarshaler,
                                    ppvf);
                                  result = v53;
                                }
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0xEE,
                                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                  (const char *)(unsigned int)v41,
                                  ppvf);
                                result = v42;
                              }
                            }
                            else
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0xED,
                                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                (const char *)(unsigned int)v38,
                                ppvf);
                              result = v40;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0xEC,
                              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                              (const char *)(unsigned int)v35,
                              ppvf);
                            result = v37;
                          }
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xDA,
                          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                          (const char *)(unsigned int)v29,
                          ppvf);
                        result = v30;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xD6,
                        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                        (const char *)(unsigned int)v26,
                        ppvf);
                      result = v27;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xD0,
                      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                      (const char *)(unsigned int)v22,
                      ppvf);
                    result = v23;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xCD,
                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                    (const char *)(unsigned int)v20,
                    ppvf);
                  result = v21;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xCC,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                  (const char *)(unsigned int)v18,
                  ppvf);
                result = v19;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                (const char *)(unsigned int)v15,
                ppve);
              result = v16;
            }
          }
          catch ( ... )
          {
            return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                   retaddr,
                                   (void *)0x102,
                                   (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
                                   v17);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC8,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
            (const char *)(unsigned int)Instance,
            ppvd);
          return v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
          (const char *)(unsigned int)v10,
          ppvc);
        return v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
        (const char *)(unsigned int)v7,
        (int)ppvb);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
      (const char *)(unsigned int)inited,
      (int)ppva);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18012f654  mov     [rsp+arg_10], rbx
0x18012f659  push    rsi
0x18012f65a  push    rdi
0x18012f65b  push    r14
0x18012f65d  sub     rsp, 40h
0x18012f661  mov     rdi, rcx
0x18012f664  add     rcx, 150h; this
0x18012f66b  xor     r9d, r9d; int
0x18012f66e  lea     r8d, [r9+1]; int
0x18012f672  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18012f677  mov     ebx, eax
0x18012f679  test    eax, eax
0x18012f67b  jns     short loc_18012F69D
0x18012f67d  mov     rcx, [rsp+58h]; this
0x18012f682  mov     r9d, eax; char *
0x18012f685  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f68c  mov     edx, 0C2h; void *
0x18012f691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f696  mov     eax, ebx
0x18012f698  jmp     loc_18012FC18
0x18012f69d  lea     rcx, [rdi+368h]; this
0x18012f6a4  mov     r9d, 1; int
0x18012f6aa  mov     r8d, r9d; int
0x18012f6ad  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18012f6b2  mov     ebx, eax
0x18012f6b4  test    eax, eax
0x18012f6b6  jns     short loc_18012F6D8
0x18012f6b8  mov     rcx, [rsp+58h]; this
0x18012f6bd  mov     r9d, eax; char *
0x18012f6c0  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f6c7  mov     edx, 0C4h; void *
0x18012f6cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f6d1  mov     eax, ebx
0x18012f6d3  jmp     loc_18012FC18
0x18012f6d8  lea     rcx, [rdi+160h]; this
0x18012f6df  xor     r9d, r9d; int
0x18012f6e2  xor     r8d, r8d; int
0x18012f6e5  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18012f6ea  mov     ebx, eax
0x18012f6ec  test    eax, eax
0x18012f6ee  jns     short loc_18012F710
0x18012f6f0  mov     rcx, [rsp+58h]; this
0x18012f6f5  mov     r9d, eax; char *
0x18012f6f8  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f6ff  mov     edx, 0C6h; void *
0x18012f704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f709  mov     eax, ebx
0x18012f70b  jmp     loc_18012FC18
0x18012f710  lea     rsi, [rdi+308h]
0x18012f717  mov     [rsp+58h+ppv], rsi; int
0x18012f71c  lea     r9, _GUID_c83212d3_d5c9_408c_b353_311896878897; riid
0x18012f723  xor     edx, edx; pUnkOuter
0x18012f725  lea     r8d, [rdx+17h]; dwClsContext
0x18012f729  lea     rcx, CLSID_SpCFGEngine; rclsid
0x18012f730  call    cs:__imp_CoCreateInstance
0x18012f736  mov     ebx, eax
0x18012f738  test    eax, eax
0x18012f73a  jns     short loc_18012F75C
0x18012f73c  mov     rcx, [rsp+58h]; this
0x18012f741  mov     r9d, eax; char *
0x18012f744  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f74b  mov     edx, 0C8h; void *
0x18012f750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f755  mov     eax, ebx
0x18012f757  jmp     loc_18012FC18
0x18012f75c  call    ?Instance@CEntityStore@@SAAEAV1@XZ; CEntityStore::Instance(void)
0x18012f761  mov     rcx, [rsi]
0x18012f764  mov     [rax+8], rcx
0x18012f768  lea     r14, [rdi+2F8h]
0x18012f76f  mov     [rsp+58h+ppv], r14; int
0x18012f774  lea     r9, _GUID_2baeef81_2ca3_4331_98f3_26ec5abefb03; riid
0x18012f77b  xor     edx, edx; pUnkOuter
0x18012f77d  lea     r8d, [rdx+17h]; dwClsContext
0x18012f781  lea     rcx, CLSID_SpResourceManager; rclsid
0x18012f788  call    cs:__imp_CoCreateInstance
0x18012f78e  mov     ebx, eax
0x18012f790  test    eax, eax
0x18012f792  jns     short loc_18012F7B4
0x18012f794  mov     rcx, [rsp+58h]; this
0x18012f799  mov     r9d, eax; char *
0x18012f79c  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f7a3  mov     edx, 0CBh; void *
0x18012f7a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f7ad  mov     eax, ebx
0x18012f7af  jmp     loc_18012FC18
0x18012f7b4  mov     rcx, [r14]
0x18012f7b7  lea     rsi, [rdi+300h]
0x18012f7be  mov     rax, [rcx]
0x18012f7c1  lea     rdx, [rdi+8]
0x18012f7c5  mov     [rsp+58h+ppv], rsi; int
0x18012f7ca  xor     r9d, r9d
0x18012f7cd  xor     r8d, r8d
0x18012f7d0  mov     rax, [rax+38h]
0x18012f7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f7d9  mov     ebx, eax
0x18012f7db  test    eax, eax
0x18012f7dd  jns     short loc_18012F7FF
0x18012f7df  mov     rcx, [rsp+58h]; this
0x18012f7e4  mov     r9d, eax; char *
0x18012f7e7  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f7ee  mov     edx, 0CCh; void *
0x18012f7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f7f8  mov     eax, ebx
0x18012f7fa  jmp     loc_18012FC18
0x18012f7ff  mov     rcx, [rsi]
0x18012f802  mov     rax, [rcx]
0x18012f805  lea     r8, [rdi+408h]
0x18012f80c  xor     edx, edx
0x18012f80e  mov     rax, [rax+20h]
0x18012f812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f817  mov     ebx, eax
0x18012f819  test    eax, eax
0x18012f81b  jns     short loc_18012F83D
0x18012f81d  mov     rcx, [rsp+58h]; this
0x18012f822  mov     r9d, eax; char *
0x18012f825  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f82c  mov     edx, 0CDh; void *
0x18012f831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f836  mov     eax, ebx
0x18012f838  jmp     loc_18012FC18
0x18012f83d  mov     qword ptr [rsp+58h+Frequency], 0
0x18012f846  lea     rcx, [rsp+58h+Frequency]
0x18012f84b  call    ?CreateInstance@?$CComObject@VCRecoMasterSite@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CRecoMasterSite>::CreateInstance(ATL::CComObject<CRecoMasterSite> * *)
0x18012f850  mov     ebx, eax
0x18012f852  test    eax, eax
0x18012f854  jns     short loc_18012F876
0x18012f856  mov     rcx, [rsp+58h]; this
0x18012f85b  mov     r9d, eax; char *
0x18012f85e  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f865  mov     edx, 0D0h; void *
0x18012f86a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f86f  mov     eax, ebx
0x18012f871  jmp     loc_18012FC18
0x18012f876  mov     rbx, qword ptr [rsp+58h+Frequency]
0x18012f87b  lea     rcx, [rdi+310h]; struct IUnknown **
0x18012f882  cmp     [rcx], rbx
0x18012f885  jz      short loc_18012F88F
0x18012f887  mov     rdx, rbx; struct IUnknown *
0x18012f88a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18012f88f  mov     [rbx+58h], rdi
0x18012f893  mov     ecx, 68h ; 'h'; Size
0x18012f898  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012f89d  mov     qword ptr [rsp+58h+Frequency], rax
0x18012f8a2  mov     rcx, rax; this
0x18012f8a5  call    ??0CSpEngineProxy@@QEAA@XZ; CSpEngineProxy::CSpEngineProxy(void)
0x18012f8aa  nop
0x18012f8ab  mov     rdx, rax
0x18012f8ae  lea     rcx, [rdi+318h]
0x18012f8b5  call    ??$reset@VCSpEngineProxy@@$0A@@?$shared_ptr@VCSpEngineProxy@@@std@@QEAAXPEAVCSpEngineProxy@@@Z; std::shared_ptr<CSpEngineProxy>::reset<CSpEngineProxy,0>(CSpEngineProxy *)
0x18012f8ba  lea     rcx, [rdi+648h]; this
0x18012f8c1  call    ?Initialize@CPhoneCallHandler@@QEAAJXZ; CPhoneCallHandler::Initialize(void)
0x18012f8c6  mov     ebx, eax
0x18012f8c8  test    eax, eax
0x18012f8ca  jns     short loc_18012F8EC
0x18012f8cc  mov     rcx, [rsp+58h]; this
0x18012f8d1  mov     r9d, eax; char *
0x18012f8d4  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f8db  mov     edx, 0D6h; void *
0x18012f8e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f8e5  mov     eax, ebx
0x18012f8e7  jmp     loc_18012FC18
0x18012f8ec  mov     [rsp+58h+arg_8], 0
0x18012f8f5  lea     rbx, [rdi+350h]
0x18012f8fc  mov     rcx, rbx
0x18012f8ff  call    ?CreateInstance@?$CComObject@VCNotifyProxy@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CNotifyProxy>::CreateInstance(ATL::CComObject<CNotifyProxy> * *)
0x18012f904  mov     esi, eax
0x18012f906  test    eax, eax
0x18012f908  jns     short loc_18012F92A
0x18012f90a  mov     rcx, [rsp+58h]; this
0x18012f90f  mov     r9d, eax; char *
0x18012f912  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f919  mov     edx, 0DAh; void *
0x18012f91e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f923  mov     eax, esi
0x18012f925  jmp     loc_18012FC18
0x18012f92a  mov     rcx, [rbx]
0x18012f92d  test    rcx, rcx
0x18012f930  jz      short loc_18012F9A5
0x18012f932  lea     rax, [rdi+10h]
0x18012f936  mov     [rcx+40h], rax
0x18012f93a  mov     rax, [rbx]
0x18012f93d  lea     rcx, ?AudioEventId@CRecoMaster@@2W4CompletionPortTaskId@1@B; CRecoMaster::CompletionPortTaskId const CRecoMaster::AudioEventId
0x18012f944  mov     [rax+48h], rcx
0x18012f948  mov     rcx, [rbx]
0x18012f94b  mov     eax, [rdi+68h]
0x18012f94e  mov     [rcx+50h], eax
0x18012f951  mov     rcx, [rbx]
0x18012f954  add     rcx, 58h ; 'X'; struct IUnknown **
0x18012f958  mov     rdx, [r14]; struct IUnknown *
0x18012f95b  cmp     [rcx], rdx
0x18012f95e  jz      short loc_18012F965
0x18012f960  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18012f965  mov     rcx, [rbx]
0x18012f968  mov     rax, [rcx]
0x18012f96b  lea     r8, [rsp+58h+arg_8]
0x18012f970  lea     rdx, _GUID_259684dc_37c3_11d2_9603_00c04f8ee628
0x18012f977  mov     rax, [rax]
0x18012f97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f97f  mov     ebx, eax
0x18012f981  test    eax, eax
0x18012f983  jns     short loc_18012F9A5
0x18012f985  mov     rcx, [rsp+58h]; this
0x18012f98a  mov     r9d, eax; char *
0x18012f98d  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f994  mov     edx, 0E1h; void *
0x18012f999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f99e  mov     eax, ebx
0x18012f9a0  jmp     loc_18012FC18
0x18012f9a5  mov     qword ptr [rsp+58h+Frequency], 0
0x18012f9ae  lea     rcx, [rsp+58h+Frequency]; lpFrequency
0x18012f9b3  call    cs:__imp_QueryPerformanceFrequency
0x18012f9b9  xorps   xmm0, xmm0
0x18012f9bc  cvtsi2sd xmm0, qword ptr [rsp+58h+Frequency]
0x18012f9c3  movsd   xmm1, cs:__real@416312d000000000
0x18012f9cb  divsd   xmm1, xmm0
0x18012f9cf  movsd   qword ptr [rdi+120h], xmm1
0x18012f9d7  xor     edx, edx; enum SPCATEGORYTYPE
0x18012f9d9  mov     rcx, rdi; this
0x18012f9dc  call    ?AddCategory@CRecoMaster@@AEAAJW4SPCATEGORYTYPE@@PEAX@Z; CRecoMaster::AddCategory(SPCATEGORYTYPE,void *)
0x18012f9e1  mov     ebx, eax
0x18012f9e3  test    eax, eax
0x18012f9e5  jns     short loc_18012FA07
0x18012f9e7  mov     rcx, [rsp+58h]; this
0x18012f9ec  mov     r9d, eax; char *
0x18012f9ef  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012f9f6  mov     edx, 0ECh; void *
0x18012f9fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fa00  mov     eax, ebx
0x18012fa02  jmp     loc_18012FC18
0x18012fa07  mov     edx, 1; enum SPCATEGORYTYPE
0x18012fa0c  mov     rcx, rdi; this
0x18012fa0f  call    ?AddCategory@CRecoMaster@@AEAAJW4SPCATEGORYTYPE@@PEAX@Z; CRecoMaster::AddCategory(SPCATEGORYTYPE,void *)
0x18012fa14  mov     ebx, eax
0x18012fa16  test    eax, eax
0x18012fa18  jns     short loc_18012FA3A
0x18012fa1a  mov     rcx, [rsp+58h]; this
0x18012fa1f  mov     r9d, eax; char *
0x18012fa22  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012fa29  mov     edx, 0EDh; void *
0x18012fa2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fa33  mov     eax, ebx
0x18012fa35  jmp     loc_18012FC18
0x18012fa3a  mov     edx, 2; enum SPCATEGORYTYPE
0x18012fa3f  mov     rcx, rdi; this
0x18012fa42  call    ?AddCategory@CRecoMaster@@AEAAJW4SPCATEGORYTYPE@@PEAX@Z; CRecoMaster::AddCategory(SPCATEGORYTYPE,void *)
0x18012fa47  mov     ebx, eax
0x18012fa49  test    eax, eax
0x18012fa4b  jns     short loc_18012FA6D
0x18012fa4d  mov     rcx, [rsp+58h]; this
0x18012fa52  mov     r9d, eax; char *
0x18012fa55  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012fa5c  mov     edx, 0EEh; void *
0x18012fa61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fa66  mov     eax, ebx
0x18012fa68  jmp     loc_18012FC18
0x18012fa6d  mov     dword ptr [rsp+58h+Frequency], 0
0x18012fa75  lea     rcx, [rsp+58h+var_28]
0x18012fa7a  call    ?Instance@SRCloudPolicy@@SA?AV?$shared_ptr@VOneSettingsPolicyWrapper@@@std@@XZ; SRCloudPolicy::Instance(void)
0x18012fa7f  nop
0x18012fa80  lea     r8, [rsp+58h+Frequency]; unsigned int *
0x18012fa85  lea     rdx, aServicesideend; "ServiceSideEndpointing"
0x18012fa8c  mov     rcx, [rax]; this
0x18012fa8f  call    ?GetDWORDValue@OneSettingsPolicyWrapper@@QEAAJPEBGPEAK@Z; OneSettingsPolicyWrapper::GetDWORDValue(ushort const *,ulong *)
0x18012fa94  mov     rcx, [rsp+58h]; this
0x18012fa99  test    eax, eax
0x18012fa9b  jns     short loc_18012FAB2
0x18012fa9d  mov     r9d, eax; char *
0x18012faa0  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012faa7  mov     edx, 0F2h; void *
0x18012faac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18012fab1  nop
0x18012fab2  mov     rcx, [rsp+58h+var_20]; this
0x18012fab7  test    rcx, rcx
0x18012faba  jz      short loc_18012FAC1
0x18012fabc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012fac1  cmp     dword ptr [rsp+58h+Frequency], 0
0x18012fac6  setnz   al
0x18012fac9  mov     [rdi+3C4h], al
0x18012facf  mov     byte ptr [rdi+3C5h], 1
0x18012fad6  lea     rcx, [rsp+58h+var_28]
0x18012fadb  call    ?Instance@SRCloudPolicy@@SA?AV?$shared_ptr@VOneSettingsPolicyWrapper@@@std@@XZ; SRCloudPolicy::Instance(void)
0x18012fae0  nop
0x18012fae1  lea     r8, [rdi+3CCh]; unsigned int *
0x18012fae8  lea     rdx, aMaxavailabilit; "MaxAvailabilityAssuranceDuration"
0x18012faef  mov     rcx, [rax]; this
0x18012faf2  call    ?GetDWORDValue@OneSettingsPolicyWrapper@@QEAAJPEBGPEAK@Z; OneSettingsPolicyWrapper::GetDWORDValue(ushort const *,ulong *)
0x18012faf7  mov     rcx, [rsp+58h]; this
0x18012fafc  test    eax, eax
0x18012fafe  jns     short loc_18012FB15
0x18012fb00  mov     r9d, eax; char *
0x18012fb03  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18012fb0a  mov     edx, 0F7h; void *
0x18012fb0f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18012fb14  nop
0x18012fb15  mov     rcx, [rsp+58h+var_20]; this
0x18012fb1a  test    rcx, rcx
0x18012fb1d  jz      short loc_18012FB24
0x18012fb1f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012fb24  lea     rcx, [rsp+58h+var_28]
0x18012fb29  call    ?Instance@SRCloudPolicy@@SA?AV?$shared_ptr@VOneSettingsPolicyWrapper@@@std@@XZ; SRCloudPolicy::Instance(void)
  ... truncated ...
```
