# CTask::RunWizard(_GUID const *,ulong,ushort * const,void * const,ulong const *)

- ea: `0x180024074`
- end: `0x1800249e8`
- name: `?RunWizard@CTask@@QEAAJPEBU_GUID@@KQEAGQEAXPEBK@Z`
- size: `2420`
- prototype: `__int64 __usercall@<rax>(CTask *__hidden this@<rcx>, IID *rclsid@<rdx>, unsigned int@<r8d>, unsigned __int16 *const@<r9>, void *const, const unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001e180`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000ae44`
- `0x18000c3ac`
- `0x18000df3c`
- `0x18000e098`
- `0x180010b0c`
- `0x180020140`
- `0x180020348`
- `0x180021c98`
- `0x180021d04`
- `0x180024074`
- `0x180031b98`
- `0x180031d2c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180024579`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180024579`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024629`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800244b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800244bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800244b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800244bb`

## pseudocode

```c
__int64 __fastcall CTask::RunWizard(
        CTask *this,
        IID *rclsid,
        int a3,
        unsigned __int16 *const a4,
        void *const a5,
        const unsigned int *a6)
{
  PVOID *v10; // rcx
  __int64 v11; // r9
  unsigned int v13; // eax
  unsigned int *v14; // rsi
  unsigned int v15; // edi
  struct CUnknown *v16; // r14
  PVOID *v17; // rax
  PVOID *v18; // rcx
  int SpecifiedWizardModule; // eax
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // eax
  void *v26; // rcx
  PVOID *v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // eax
  int *v30; // rdx
  int v31; // r8d
  _QWORD *v32; // r14
  HRESULT Instance; // eax
  int v34; // eax
  int v35; // ecx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  unsigned int i; // eax
  __int64 v39; // rcx
  __int64 v40; // r9
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  int v44; // [rsp+40h] [rbp-38h]
  LPVOID v45; // [rsp+50h] [rbp-28h] BYREF
  struct CUnknown *v46; // [rsp+58h] [rbp-20h] BYREF
  LPVOID pv[3]; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v48; // [rsp+C0h] [rbp+48h] BYREF

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      *((unsigned int *)this + 4));
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = *(unsigned int *)this;
  if ( (int)v11 < 0 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
      WPP_SF_d(v10[2], 142, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v11);
    return *(unsigned int *)this;
  }
  *((_QWORD *)this + 51) = a6;
  *((_DWORD *)this + 104) = a3;
  *((_QWORD *)this + 53) = a4;
  CTask::ClearProcessedStack(this);
  v13 = *((_DWORD *)this + 55);
  v14 = (unsigned int *)((char *)this + 16);
  v45 = 0;
  v48 = v13;
  *((_DWORD *)this + 257) = IsFactoryRegisteredWizardComponent((const struct _GUID *)this + 1);
  while ( 1 )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, IID *, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, LPVOID *))(**((_QWORD **)this + 32) + 56LL))(
            *((_QWORD *)this + 32),
            *((_QWORD *)this + 1),
            rclsid,
            v48,
            *((_DWORD *)this + 104),
            *((_QWORD *)this + 53),
            **((_DWORD **)this + 51),
            *((_QWORD *)this + 35),
            &v45);
    if ( v15 != -2147467263 )
      break;
    if ( (**((_BYTE **)this + 51) & 0x10) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *, _QWORD))(**((_QWORD **)this + 36) + 152LL))(
        *((_QWORD *)this + 36),
        &v48,
        *((unsigned int *)this + 30));
      if ( *((_DWORD *)this + 55) != v48 )
        continue;
    }
    if ( *((_DWORD *)this + 257) )
      goto LABEL_28;
    v46 = 0;
    v15 = CWTask::CreateComponentInstance((const struct _GUID *)this + 1, 0, &v46);
    if ( (v15 & 0x80000000) != 0 )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v15);
LABEL_28:
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_29:
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
          WPP_SF_ddD(v17[2], 146, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14, v48, v15);
      }
      return 2147500033LL;
    }
    pv[0] = 0;
    v16 = v46;
    v15 = (**(__int64 (__fastcall ***)(struct CUnknown *, GUID *, LPVOID *))v46)(v46, &IID_IXWizardTaskEvent, pv);
    if ( (v15 & 0x80000000) != 0 )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v15);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v16 )
      {
        (*(void (__fastcall **)(struct CUnknown *, __int64))(*(_QWORD *)v16 + 24LL))(v16, 1);
        goto LABEL_28;
      }
      goto LABEL_29;
    }
    *((_DWORD *)this + 257) = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 16LL))(*((_QWORD *)this + 32));
    *((LPVOID *)this + 32) = pv[0];
    v48 = *((_DWORD *)this + 55);
    (*(void (__fastcall **)(struct CUnknown *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v15 == 1 )
  {
    if ( !v45 )
      goto LABEL_38;
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
LABEL_39:
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          WPP_SF_DD(v18[2], 148, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14, 1);
        return 1;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
LABEL_38:
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_39;
    }
    return 1;
  }
  if ( (v15 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14, v15);
    return v15;
  }
  SpecifiedWizardModule = HrGetSpecifiedWizardModule(
                            (char *)this + 16,
                            (unsigned int)(*((_DWORD *)this + 257) != 0) + 1,
                            (char *)this + 1032);
  v15 = SpecifiedWizardModule;
  if ( SpecifiedWizardModule < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        150,
        &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
        *((unsigned int *)this + 257),
        SpecifiedWizardModule);
    return v15;
  }
  if ( v45 )
  {
    v21 = *((_QWORD *)this + 36);
    v44 = *((_DWORD *)this + 30);
    v22 = *((_QWORD *)this + 1);
    v23 = *((_QWORD *)this + 37);
    v24 = *((unsigned int *)this + 55);
    pv[0] = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, LPVOID, char *, char *, LPVOID *, int))(*(_QWORD *)v21 + 64LL))(
            v21,
            v22,
            v23,
            v24,
            v45,
            (char *)this + 968,
            (char *)this + 440,
            pv,
            v44);
    v26 = pv[0];
    v15 = v25;
    if ( pv[0] )
    {
      *(_OWORD *)((char *)this + 188) = *(_OWORD *)pv[0];
      CoTaskMemFree(v26);
    }
    CoTaskMemFree(v45);
    if ( (v15 & 0x80000000) != 0 )
    {
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return v15;
      v28 = 152;
      goto LABEL_144;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      151,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      *v14,
      SpecifiedWizardModule);
  }
  if ( !*((_QWORD *)this + 55) )
  {
    v29 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 38) + 64LL))(
            *((_QWORD *)this + 38),
            (char *)this + 16,
            (char *)this + 440);
    if ( v29 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v29);
    }
    else
    {
      *((_DWORD *)this + 108) = 1;
    }
    if ( !*((_QWORD *)this + 55) )
    {
      v15 = StringFromCLSID((const IID *const)this + 1, (LPOLESTR *)this + 55);
      if ( (v15 & 0x80000000) != 0 )
      {
        v27 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return v15;
        v28 = 154;
        goto LABEL_144;
      }
      *((_DWORD *)this + 108) = 1;
    }
  }
  if ( !(unsigned int)CPXWizardSemaphoreLock::GetRefCount((CTask *)((char *)this + 976), v20) )
  {
LABEL_76:
    v15 = CPXWizardSemaphoreLock::AddRef((CTask *)((char *)this + 976), v30, v31);
    if ( (v15 & 0x80000000) != 0 )
    {
      if ( v15 == -2147024891 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            159,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            *v14,
            -2147024891);
        return v15;
      }
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return v15;
      v28 = 160;
LABEL_144:
      WPP_SF_d(v27[2], v28, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v15);
      return v15;
    }
    *((_DWORD *)this + 254) = 1;
    if ( rclsid )
    {
      v32 = (_QWORD *)((char *)this + 264);
      Instance = CoCreateInstance(rclsid, 0, 0x401u, &IID_IXWizardHostEvent, (LPVOID *)this + 33);
      v15 = Instance;
      if ( Instance < 0 )
      {
        if ( Instance != -2147221164 && Instance != -2147467262 )
        {
          v27 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            return v15;
          v28 = 164;
          goto LABEL_144;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            163,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            rclsid->Data1,
            Instance);
      }
      else
      {
        v34 = (*(__int64 (__fastcall **)(_QWORD, IID *, _QWORD, char *))(**((_QWORD **)this + 38) + 72LL))(
                *((_QWORD *)this + 38),
                rclsid,
                0,
                (char *)this + 112);
        v15 = v34;
        if ( v34 < 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 16LL))(*v32);
          v27 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            return v15;
          v28 = 162;
          goto LABEL_144;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            161,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            rclsid->Data1,
            v34);
        *((_DWORD *)this + 17) = *((_DWORD *)this + 104);
        *((_QWORD *)this + 9) = *((_QWORD *)this + 53);
        v35 = **((_DWORD **)this + 51);
        *((_QWORD *)this + 11) = a5;
        *((_DWORD *)this + 20) = v35;
      }
      if ( (*((_BYTE *)this + 112) & 0x40) != 0 )
        (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v32 + 40LL))(*v32, 1, (char *)this + 40);
    }
    for ( i = CTask::HrGetFirstPageToRun(this); ; i = CTask::HrGetNextPageToRun(this, 0, 0) )
    {
      v15 = i;
      if ( i != 262656 )
        break;
    }
    if ( (*((_BYTE *)this + 112) & 0x40) != 0 )
    {
      v39 = *((_QWORD *)this + 33);
      *((_DWORD *)this + 24) = i;
      *((_DWORD *)this + 25) = 0;
      *((_QWORD *)this + 13) = 0;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 40LL))(v39, 2);
    }
    if ( !v15 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 36) + 144LL))(
              *((_QWORD *)this + 36),
              *((_QWORD *)this + 121),
              *((unsigned int *)this + 30));
      if ( v15 == -2147021886 )
        v15 = 262658;
      goto LABEL_129;
    }
    v40 = 262657;
    if ( v15 == 262657 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_129;
      v42 = 165;
    }
    else
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_129;
      v42 = 166;
      v40 = v15;
    }
    WPP_SF_d(v41[2], v42, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v40);
LABEL_129:
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 32) + 88LL))(*((_QWORD *)this + 32), 0, 0);
    v27 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14);
      v27 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)this + 112) & 0x40) != 0 )
    {
      v43 = *((_QWORD *)this + 33);
      *((_DWORD *)this + 24) = v15;
      *((_DWORD *)this + 25) = 0;
      *((_QWORD *)this + 13) = 0;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 40LL))(v43, 6);
      v27 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v27 == &WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 0x10) == 0 )
      return v15;
    v28 = 168;
    goto LABEL_144;
  }
  if ( (*((_DWORD *)this + 29) & 0xF) == 0 )
  {
    if ( (unsigned int)CTask::FindDuplicateWizardAndSetToForeground((LPARAM)this) )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return 1;
      v37 = 156;
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return 1;
      v37 = 157;
    }
    WPP_SF_d(v36[2], v37, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14);
    return 1;
  }
  if ( (*((_DWORD *)this + 29) & 0xF) != 1 )
  {
    if ( (*((_DWORD *)this + 29) & 0xF) == 2
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v14);
    }
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      155,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      *v14,
      -2147221002);
  return 2147746294LL;
}

```

## disassembly

```asm
0x180024074  push    rbp
0x180024076  push    rbx
0x180024077  push    rsi
0x180024078  push    rdi
0x180024079  push    r12
0x18002407b  push    r13
0x18002407d  push    r14
0x18002407f  push    r15
0x180024081  mov     rbp, rsp
0x180024084  sub     rsp, 78h
0x180024088  mov     rdi, r9
0x18002408b  mov     esi, r8d
0x18002408e  mov     r15, rdx
0x180024091  mov     rbx, rcx
0x180024094  mov     rcx, cs:WPP_GLOBAL_Control
0x18002409b  lea     r12, WPP_GLOBAL_Control
0x1800240a2  lea     r13, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x1800240a9  cmp     rcx, r12
0x1800240ac  jz      short loc_1800240D0
0x1800240ae  test    byte ptr [rcx+1Ch], 8
0x1800240b2  jz      short loc_1800240D0
0x1800240b4  mov     r9d, [rbx+10h]
0x1800240b8  mov     edx, 8Dh
0x1800240bd  mov     rcx, [rcx+10h]
0x1800240c1  mov     r8, r13
0x1800240c4  call    WPP_SF_d
0x1800240c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240d0  mov     r9d, [rbx]
0x1800240d3  xor     r14d, r14d
0x1800240d6  test    r9d, r9d
0x1800240d9  jns     short loc_1800240FE
0x1800240db  cmp     rcx, r12
0x1800240de  jz      short loc_1800240F7
0x1800240e0  test    byte ptr [rcx+1Ch], 4
0x1800240e4  jz      short loc_1800240F7
0x1800240e6  mov     rcx, [rcx+10h]
0x1800240ea  mov     edx, 8Eh
0x1800240ef  mov     r8, r13
0x1800240f2  call    WPP_SF_d
0x1800240f7  mov     eax, [rbx]
0x1800240f9  jmp     loc_1800249D7
0x1800240fe  mov     rax, [rbp+arg_28]
0x180024102  mov     rcx, rbx; this
0x180024105  mov     [rbx+198h], rax
0x18002410c  mov     [rbx+1A0h], esi
0x180024112  mov     [rbx+1A8h], rdi
0x180024119  call    ?ClearProcessedStack@CTask@@AEAAXXZ; CTask::ClearProcessedStack(void)
0x18002411e  mov     eax, [rbx+0DCh]
0x180024124  lea     rsi, [rbx+10h]
0x180024128  mov     rcx, rsi; struct _GUID *
0x18002412b  mov     [rbp+var_28], r14
0x18002412f  mov     [rbp+arg_0], eax
0x180024132  call    ?IsFactoryRegisteredWizardComponent@@YAHPEBU_GUID@@@Z; IsFactoryRegisteredWizardComponent(_GUID const *)
0x180024137  mov     [rbx+404h], eax
0x18002413d  mov     r8, [rbx+198h]
0x180024144  lea     rdx, [rbp+var_28]
0x180024148  mov     rcx, [rbx+100h]
0x18002414f  mov     r9d, [rbp+arg_0]
0x180024153  mov     qword ptr [rsp+78h+var_38], rdx
0x180024158  mov     rdx, [rbx+118h]
0x18002415f  mov     rax, [rcx]
0x180024162  mov     [rsp+78h+var_40], rdx
0x180024167  mov     edx, [r8]
0x18002416a  mov     r8, r15
0x18002416d  mov     dword ptr [rsp+78h+var_48], edx
0x180024171  mov     rdx, [rbx+1A8h]
0x180024178  mov     rax, [rax+38h]
0x18002417c  mov     [rsp+78h+var_50], rdx
0x180024181  mov     edx, [rbx+1A0h]
0x180024187  mov     dword ptr [rsp+78h+ppv], edx
0x18002418b  mov     rdx, [rbx+8]
0x18002418f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024194  mov     edi, eax
0x180024196  cmp     eax, 80004001h
0x18002419b  jnz     loc_180024341
0x1800241a1  mov     rcx, [rbx+198h]
0x1800241a8  test    byte ptr [rcx], 10h
0x1800241ab  jz      short loc_1800241DA
0x1800241ad  mov     rcx, [rbx+120h]
0x1800241b4  mov     r8d, [rbx+78h]
0x1800241b8  mov     rdx, [rcx]
0x1800241bb  mov     rax, [rdx+98h]
0x1800241c2  lea     rdx, [rbp+arg_0]
0x1800241c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241cb  mov     eax, [rbp+arg_0]
0x1800241ce  cmp     [rbx+0DCh], eax
0x1800241d4  jnz     loc_18002413D
0x1800241da  cmp     [rbx+404h], r14d
0x1800241e1  jnz     loc_180024306
0x1800241e7  lea     r8, [rbp+var_20]; struct CUnknown **
0x1800241eb  mov     [rbp+var_20], r14
0x1800241ef  xor     edx, edx; struct IUnknown *
0x1800241f1  mov     rcx, rsi; struct _GUID *
0x1800241f4  call    ?CreateComponentInstance@CWTask@@SAJPEBU_GUID@@PEAUIUnknown@@PEAPEAVCUnknown@@@Z; CWTask::CreateComponentInstance(_GUID const *,IUnknown *,CUnknown * *)
0x1800241f9  mov     edi, eax
0x1800241fb  test    eax, eax
0x1800241fd  js      loc_1800242E0
0x180024203  mov     [rbp+pv], r14
0x180024207  lea     r8, [rbp+pv]
0x18002420b  mov     r14, [rbp+var_20]
0x18002420f  lea     rdx, IID_IXWizardTaskEvent
0x180024216  mov     rcx, r14
0x180024219  mov     rax, [r14]
0x18002421c  mov     rax, [rax]
0x18002421f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024224  mov     edi, eax
0x180024226  test    eax, eax
0x180024228  js      short loc_180024298
0x18002422a  mov     dword ptr [rbx+404h], 1
0x180024234  mov     rcx, cs:WPP_GLOBAL_Control
0x18002423b  cmp     rcx, r12
0x18002423e  jz      short loc_18002425A
0x180024240  test    byte ptr [rcx+1Ch], 8
0x180024244  jz      short loc_18002425A
0x180024246  mov     r9d, [rsi]
0x180024249  mov     edx, 8Fh
0x18002424e  mov     rcx, [rcx+10h]
0x180024252  mov     r8, r13
0x180024255  call    WPP_SF_d
0x18002425a  mov     rcx, [rbx+100h]
0x180024261  mov     rax, [rcx]
0x180024264  mov     rax, [rax+10h]
0x180024268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002426d  mov     rax, [rbp+pv]
0x180024271  mov     rcx, r14
0x180024274  mov     [rbx+100h], rax
0x18002427b  mov     eax, [rbx+0DCh]
0x180024281  mov     [rbp+arg_0], eax
0x180024284  mov     rax, [r14]
0x180024287  mov     rax, [rax+10h]
0x18002428b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024290  xor     r14d, r14d
0x180024293  jmp     loc_18002413D
0x180024298  mov     rax, cs:WPP_GLOBAL_Control
0x18002429f  cmp     rax, r12
0x1800242a2  jz      short loc_1800242C5
0x1800242a4  test    byte ptr [rax+1Ch], 4
0x1800242a8  jz      short loc_1800242C5
0x1800242aa  mov     rcx, [rax+10h]
0x1800242ae  mov     edx, 90h
0x1800242b3  mov     r9d, edi
0x1800242b6  mov     r8, r13
0x1800242b9  call    WPP_SF_d
0x1800242be  mov     rax, cs:WPP_GLOBAL_Control
0x1800242c5  test    r14, r14
0x1800242c8  jz      short loc_18002430D
0x1800242ca  mov     rax, [r14]
0x1800242cd  mov     edx, 1
0x1800242d2  mov     rcx, r14
0x1800242d5  mov     rax, [rax+18h]
0x1800242d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242de  jmp     short loc_180024306
0x1800242e0  mov     rax, cs:WPP_GLOBAL_Control
0x1800242e7  cmp     rax, r12
0x1800242ea  jz      short loc_180024337
0x1800242ec  test    byte ptr [rax+1Ch], 4
0x1800242f0  jz      short loc_18002430D
0x1800242f2  mov     rcx, [rax+10h]
0x1800242f6  mov     edx, 91h
0x1800242fb  mov     r9d, edi
0x1800242fe  mov     r8, r13
0x180024301  call    WPP_SF_d
0x180024306  mov     rax, cs:WPP_GLOBAL_Control
0x18002430d  cmp     rax, r12
0x180024310  jz      short loc_180024337
0x180024312  test    byte ptr [rax+1Ch], 8
0x180024316  jz      short loc_180024337
0x180024318  mov     ecx, [rbp+arg_0]
0x18002431b  mov     edx, 92h
0x180024320  mov     r9d, [rsi]
0x180024323  mov     r8, r13
0x180024326  mov     dword ptr [rsp+78h+var_50], edi
0x18002432a  mov     dword ptr [rsp+78h+ppv], ecx
0x18002432e  mov     rcx, [rax+10h]
0x180024332  call    WPP_SF_ddD
0x180024337  mov     eax, 80004001h
0x18002433c  jmp     loc_1800249D7
0x180024341  cmp     edi, 1
0x180024344  jnz     short loc_1800243AE
0x180024346  cmp     [rbp+var_28], r14
0x18002434a  jz      short loc_180024373
0x18002434c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024353  cmp     rcx, r12
0x180024356  jz      loc_18002475E
0x18002435c  test    byte ptr [rcx+1Ch], 8
0x180024360  jz      short loc_18002437A
0x180024362  mov     rcx, [rcx+10h]
0x180024366  mov     edx, 93h
0x18002436b  mov     r8, r13
0x18002436e  call    WPP_SF_
0x180024373  mov     rcx, cs:WPP_GLOBAL_Control
0x18002437a  cmp     rcx, r12
0x18002437d  jz      loc_18002475E
0x180024383  test    byte ptr [rcx+1Ch], 8
0x180024387  jz      loc_18002475E
0x18002438d  mov     r9d, [rsi]
0x180024390  mov     edx, 94h
0x180024395  mov     rcx, [rcx+10h]
0x180024399  mov     r8, r13
0x18002439c  mov     dword ptr [rsp+78h+ppv], 1
0x1800243a4  call    WPP_SF_DD
0x1800243a9  jmp     loc_18002475E
0x1800243ae  test    edi, edi
0x1800243b0  jns     short loc_1800243DA
0x1800243b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243b9  cmp     rcx, r12
0x1800243bc  jz      loc_1800249D5
0x1800243c2  test    byte ptr [rcx+1Ch], 8
0x1800243c6  jz      loc_1800249D5
0x1800243cc  mov     edx, 95h
0x1800243d1  mov     dword ptr [rsp+78h+ppv], edi
0x1800243d5  jmp     loc_18002499E
0x1800243da  mov     eax, [rbx+404h]
0x1800243e0  lea     r8, [rbx+408h]
0x1800243e7  neg     eax
0x1800243e9  mov     rcx, rsi
0x1800243ec  sbb     edx, edx
0x1800243ee  neg     edx
0x1800243f0  inc     edx
0x1800243f2  call    ?HrGetSpecifiedWizardModule@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAUHINSTANCE__@@@Z; HrGetSpecifiedWizardModule(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,HINSTANCE__ * *)
0x1800243f7  mov     edi, eax
0x1800243f9  test    eax, eax
0x1800243fb  jns     short loc_180024438
0x1800243fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180024404  cmp     rcx, r12
0x180024407  jz      loc_1800249D5
0x18002440d  test    byte ptr [rcx+1Ch], 4
0x180024411  jz      loc_1800249D5
0x180024417  mov     r9d, [rbx+404h]
0x18002441e  mov     edx, 96h
0x180024423  mov     rcx, [rcx+10h]
0x180024427  mov     r8, r13
0x18002442a  mov     dword ptr [rsp+78h+ppv], eax
0x18002442e  call    WPP_SF_DD
0x180024433  jmp     loc_1800249D5
0x180024438  mov     r10, [rbp+var_28]
0x18002443c  test    r10, r10
0x18002443f  jz      loc_1800244E9
0x180024445  mov     edx, [rbx+78h]
0x180024448  lea     r9, [rbx+3C8h]
0x18002444f  mov     rcx, [rbx+120h]
0x180024456  lea     r8, [rbx+1B8h]
0x18002445d  mov     [rsp+78h+var_38], edx
0x180024461  lea     rdx, [rbp+pv]
0x180024465  mov     [rsp+78h+var_40], rdx
0x18002446a  mov     rdx, [rbx+8]
0x18002446e  mov     [rsp+78h+var_48], r8
0x180024473  mov     r8, [rbx+128h]
0x18002447a  mov     [rsp+78h+var_50], r9
0x18002447f  mov     r9d, [rbx+0DCh]
0x180024486  mov     [rbp+pv], r14
0x18002448a  mov     rax, [rcx]
0x18002448d  mov     [rsp+78h+ppv], r10
0x180024492  mov     rax, [rax+40h]
0x180024496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002449b  mov     rcx, [rbp+pv]; pv
0x18002449f  mov     edi, eax
0x1800244a1  test    rcx, rcx
0x1800244a4  jz      short loc_1800244B7
0x1800244a6  movups  xmm0, xmmword ptr [rcx]
0x1800244a9  movdqu  xmmword ptr [rbx+0BCh], xmm0
0x1800244b1  call    cs:__imp_CoTaskMemFree
0x1800244b7  mov     rcx, [rbp+var_28]; pv
0x1800244bb  call    cs:__imp_CoTaskMemFree
0x1800244c1  test    edi, edi
0x1800244c3  jns     short loc_180024513
0x1800244c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244cc  cmp     rcx, r12
0x1800244cf  jz      loc_1800249D5
0x1800244d5  test    byte ptr [rcx+1Ch], 4
0x1800244d9  jz      loc_1800249D5
0x1800244df  mov     edx, 98h
0x1800244e4  jmp     loc_1800249C6
0x1800244e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244f0  cmp     rcx, r12
0x1800244f3  jz      short loc_180024513
0x1800244f5  test    byte ptr [rcx+1Ch], 8
0x1800244f9  jz      short loc_180024513
0x1800244fb  mov     r9d, [rsi]
0x1800244fe  mov     edx, 97h
0x180024503  mov     rcx, [rcx+10h]
0x180024507  mov     r8, r13
0x18002450a  mov     dword ptr [rsp+78h+ppv], edi
0x18002450e  call    WPP_SF_DD
0x180024513  lea     rdi, [rbx+1B8h]
0x18002451a  cmp     [rdi], r14
0x18002451d  jnz     short loc_180024593
0x18002451f  mov     rcx, [rbx+130h]
0x180024526  mov     r8, rdi
0x180024529  mov     rdx, rsi
0x18002452c  mov     rax, [rcx]
0x18002452f  mov     rax, [rax+40h]
0x180024533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024538  test    eax, eax
0x18002453a  jnz     short loc_180024548
0x18002453c  mov     dword ptr [rbx+1B0h], 1
0x180024546  jmp     short loc_18002456E
0x180024548  mov     rcx, cs:WPP_GLOBAL_Control
0x18002454f  cmp     rcx, r12
0x180024552  jz      short loc_18002456E
  ... truncated ...
```
