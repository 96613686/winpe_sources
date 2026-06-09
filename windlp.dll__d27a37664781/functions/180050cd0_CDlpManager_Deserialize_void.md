# CDlpManager::Deserialize(void)

- ea: `0x180050cd0`
- end: `0x180051b7b`
- name: `?Deserialize@CDlpManager@@AEAAJXZ`
- size: `3755`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180063bb0`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002aee4`
- `0x180047440`
- `0x1800475b0`
- `0x180047c30`
- `0x180047db4`
- `0x18004d6f0`
- `0x180050cd0`
- `0x180061d1c`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005104e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005108a`
- `OLEAUT32!__imp_SysFreeString` at `0x180051157`
- `OLEAUT32!__imp_SysFreeString` at `0x18005124b`
- `OLEAUT32!__imp_SysFreeString` at `0x180051ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180051ad6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005104e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005108a`
- `OLEAUT32!__imp_SysFreeString` at `0x180051157`
- `OLEAUT32!__imp_SysFreeString` at `0x18005124b`
- `OLEAUT32!__imp_SysFreeString` at `0x180051ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180051ad6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051ae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051ae5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051af4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051af4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051b0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051b0c`

## string_xrefs

- `0x180050e49`: `TaskCount`
- `0x180050e08`: `CDlpManager::Deserialize`
- `0x1800519d0`: `CDlpManager::Deserialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDlpManager::Deserialize(CDlpManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  unsigned __int16 *v3; // r14
  __int64 v4; // rcx
  int XmlFilePaths; // edi
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // esi
  unsigned int v10; // esi
  unsigned int v11; // esi
  unsigned int v12; // esi
  int v13; // eax
  unsigned __int16 **v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  HANDLE ProcessHeap; // rax
  int v21; // [rsp+20h] [rbp-59h]
  int v22; // [rsp+28h] [rbp-51h]
  _QWORD *v23; // [rsp+30h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h] BYREF
  BSTR v26; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp-21h] BYREF
  struct CDlpTask *v30; // [rsp+60h] [rbp-19h] BYREF
  __int64 v31; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v32[3]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v33; // [rsp+88h] [rbp+Fh]
  __int64 v34; // [rsp+90h] [rbp+17h]
  unsigned int v35; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v36; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v37; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v38; // [rsp+F8h] [rbp+7Fh] BYREF

  v34 = 0;
  v32[2] = (char *)this + 304;
  v32[1] = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 312);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v33 = 1;
  v3 = 0;
  v29 = 0;
  bstrString = 0;
  v26 = 0;
  v31 = 0;
  v25 = 0;
  v23 = 0;
  v30 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v27 = 0;
  v32[0] = 0;
  v28 = 0;
  v4 = *((_QWORD *)this + 83);
  if ( !v4 )
  {
    XmlFilePaths = 0;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      goto LABEL_146;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v6 = 0;
    goto LABEL_4;
  }
  XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(v4 + 8))(
                   v4 + 8,
                   L"State",
                   &v28);
  if ( XmlFilePaths >= 0 )
  {
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"TaskCount",
                     &v38);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( !v7 )
        goto LABEL_4;
      v22 = XmlFilePaths;
      v21 = 2376;
      goto LABEL_9;
    }
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"StringCount",
                     &v35);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( !v7 )
        goto LABEL_4;
      v22 = XmlFilePaths;
      v21 = 2379;
      goto LABEL_9;
    }
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"DwordCount",
                     &v36);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( !v7 )
        goto LABEL_4;
      v22 = XmlFilePaths;
      v21 = 2382;
      goto LABEL_9;
    }
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"QuadwordCount",
                     &v37);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( !v7 )
        goto LABEL_4;
      v22 = XmlFilePaths;
      v21 = 2385;
      goto LABEL_9;
    }
    v9 = 0;
    if ( v35 )
    {
      while ( 1 )
      {
        if ( v23 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          v23 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD **))(**((_QWORD **)this + 83)
                                                                                             + 32LL))(
                         *((_QWORD *)this + 83),
                         L"StringProperty",
                         v9,
                         &v23);
        if ( XmlFilePaths < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v23[1] + 16LL))(
                         v23 + 1,
                         L"Name",
                         &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2395;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        if ( v26 )
        {
          SysFreeString(v26);
          v26 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v23[1] + 16LL))(
                         v23 + 1,
                         L"Value",
                         &v26);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2398;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 544, &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2402;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 560, &v26);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2403;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        if ( ++v9 >= v35 )
          goto LABEL_40;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( v7 )
      {
        v22 = XmlFilePaths;
        v21 = 2392;
        goto LABEL_9;
      }
      goto LABEL_4;
    }
LABEL_40:
    v10 = 0;
    if ( v36 )
    {
      while ( 1 )
      {
        if ( v23 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          v23 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD **))(**((_QWORD **)this + 83)
                                                                                             + 32LL))(
                         *((_QWORD *)this + 83),
                         L"DwordProperty",
                         v10,
                         &v23);
        if ( XmlFilePaths < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v23[1] + 16LL))(
                         v23 + 1,
                         L"Name",
                         &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2414;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, unsigned int *))v23[1])(
                         v23 + 1,
                         L"Value",
                         &v27);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2416;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 576, &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2420;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::Append(
                         (char *)this + 592,
                         v27);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2421;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        if ( ++v10 >= v36 )
          goto LABEL_51;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( v7 )
      {
        v22 = XmlFilePaths;
        v21 = 2411;
        goto LABEL_9;
      }
      goto LABEL_4;
    }
LABEL_51:
    v11 = 0;
    if ( v37 )
    {
      while ( 1 )
      {
        if ( v23 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          v23 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD **))(**((_QWORD **)this + 83)
                                                                                             + 32LL))(
                         *((_QWORD *)this + 83),
                         L"QuadwordProperty",
                         v11,
                         &v23);
        if ( XmlFilePaths < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v23[1] + 16LL))(
                         v23 + 1,
                         L"Name",
                         &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2432;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD *))(v23[1] + 8LL))(
                         v23 + 1,
                         L"Value",
                         v32);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2434;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 608, &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2438;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        XmlFilePaths = CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Append(
                         (char *)this + 624,
                         v32[0]);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_146;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v6 = 0;
          if ( v7 )
          {
            v22 = XmlFilePaths;
            v21 = 2439;
            goto LABEL_9;
          }
          goto LABEL_4;
        }
        if ( ++v11 >= v37 )
          goto LABEL_62;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( v7 )
      {
        v22 = XmlFilePaths;
        v21 = 2429;
        goto LABEL_9;
      }
      goto LABEL_4;
    }
LABEL_62:
    if ( (*((_BYTE *)this + 856) & 4) == 0 )
    {
      v12 = 0;
      if ( v38 )
      {
        while ( 1 )
        {
          if ( v25 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            v25 = 0;
          }
          XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, __int64 *))(**((_QWORD **)this + 83)
                                                                                               + 32LL))(
                           *((_QWORD *)this + 83),
                           L"TASK",
                           v12,
                           &v25);
          if ( XmlFilePaths < 0 )
            break;
          XmlFilePaths = CDlpTask::CreateInstance(this, v12, &v30);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_146;
            v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v6 = 0;
            if ( v7 )
            {
              v22 = XmlFilePaths;
              v21 = 2453;
              goto LABEL_9;
            }
            goto LABEL_4;
          }
          XmlFilePaths = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)v30 + 1) + 8LL))((char *)v30 + 8, v25);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_146;
            v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v6 = 0;
            if ( v7 )
            {
              v22 = XmlFilePaths;
              v21 = 2457;
              goto LABEL_9;
            }
            goto LABEL_4;
          }
          XmlFilePaths = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
                           (char *)this + 528,
                           &v30);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_146;
            v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v6 = 0;
            if ( v7 )
            {
              v22 = XmlFilePaths;
              v21 = 2461;
              goto LABEL_9;
            }
            goto LABEL_4;
          }
          if ( ++v12 >= v38 )
            goto LABEL_71;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_146;
        v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v6 = 0;
        if ( v7 )
        {
          v22 = XmlFilePaths;
          v21 = 2449;
          goto LABEL_9;
        }
        goto LABEL_4;
      }
    }
LABEL_71:
    v13 = CDlpState::Set((char *)this + 128, v28, 0);
    XmlFilePaths = v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)XmlFilePaths);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_146;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v6 = 0;
      if ( !v7 )
        goto LABEL_4;
      v22 = XmlFilePaths;
      v21 = 2465;
      goto LABEL_9;
    }
    if ( *((_DWORD *)this + 215) )
      goto LABEL_146;
    XmlFilePaths = CDlpStateXml::GetXmlFilePaths(*((CDlpStateXml **)this + 83), &v29, v14);
    if ( XmlFilePaths < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      {
        v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v16 = 0;
        if ( v15 )
        {
          v17 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v15,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpManager::Deserialize",
                  2472,
                  XmlFilePaths);
          v16 = (unsigned int)v17;
          if ( v17 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
      }
      v3 = v29;
      goto LABEL_146;
    }
    v18 = (*(__int64 (__fastcall **)(CDlpManager *, __int64 *))(*(_QWORD *)this + 152LL))(this, &v31);
    v3 = v29;
    if ( v18 >= 0 )
    {
      XmlFilePaths = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v31 + 40LL))(v31, v29);
      if ( XmlFilePaths == -2147467263 )
      {
        XmlFilePaths = 1;
      }
      else if ( XmlFilePaths < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_146;
        v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v6 = 0;
        if ( !v7 )
          goto LABEL_4;
        v22 = XmlFilePaths;
        v21 = 2475;
LABEL_9:
        v8 = CDlpLogT<CEmptyType>::DlpLogFormat(v7, 4, L"%s(%d): Result = 0x%X", L"CDlpManager::Deserialize", v21, v22);
        v6 = (unsigned int)v8;
        if ( v8 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
        goto LABEL_4;
      }
    }
    *((_DWORD *)this + 215) = 1;
    goto LABEL_146;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v6 = 0;
    if ( v7 )
    {
      v22 = XmlFilePaths;
      v21 = 2373;
      goto LABEL_9;
    }
LABEL_4:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  }
LABEL_146:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)XmlFilePaths);
  if ( v30 )
    (*(void (__fastcall **)(struct CDlpTask *))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v23 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v26 )
  {
    SysFreeString(v26);
    v26 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( (_DWORD)v33 )
  {
    LeaveCriticalSection(v2);
    LODWORD(v33) = 0;
  }
  return (unsigned int)XmlFilePaths;
}

```

## disassembly

```asm
0x180050cd0  push    rbp
0x180050cd2  push    rbx
0x180050cd3  push    rsi
0x180050cd4  push    rdi
0x180050cd5  push    r12
0x180050cd7  push    r14
0x180050cd9  push    r15
0x180050cdb  lea     rbp, [rsp-27h]
0x180050ce0  sub     rsp, 0A0h
0x180050ce7  mov     rbx, rcx
0x180050cea  xor     r12d, r12d
0x180050ced  mov     [rbp+57h+var_40], r12
0x180050cf1  xorps   xmm0, xmm0
0x180050cf4  xor     eax, eax
0x180050cf6  movups  [rbp+57h+var_58], xmm0
0x180050cfa  mov     [rbp+57h+var_48], rax
0x180050cfe  lea     rax, [rcx+130h]
0x180050d05  mov     qword ptr [rbp+57h+var_58+8], rax
0x180050d09  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180050d10  mov     qword ptr [rbp+57h+var_58], rcx
0x180050d14  lea     r15, [rax+8]
0x180050d18  mov     rcx, r15; lpCriticalSection
0x180050d1b  call    cs:__imp_EnterCriticalSection
0x180050d21  mov     dword ptr [rbp+57h+var_48], 1
0x180050d28  mov     r14d, r12d
0x180050d2b  mov     [rbp+57h+var_78], r12
0x180050d2f  mov     [rbp+57h+bstrString], r12
0x180050d33  mov     [rbp+57h+var_88], r12
0x180050d37  mov     [rbp+57h+var_68], r12
0x180050d3b  mov     [rbp+57h+var_90], r12
0x180050d3f  mov     [rbp+57h+var_A0], r12
0x180050d43  mov     [rbp+57h+var_70], r12
0x180050d47  mov     [rbp+57h+arg_18], r12d
0x180050d4b  mov     [rbp+57h+arg_0], r12d
0x180050d4f  mov     [rbp+57h+arg_8], r12d
0x180050d53  mov     [rbp+57h+arg_10], r12d
0x180050d57  mov     [rbp+57h+var_80], r12d
0x180050d5b  mov     [rbp+57h+var_60], r12
0x180050d5f  mov     [rbp+57h+var_7C], r12d
0x180050d63  mov     rcx, [rbx+298h]
0x180050d6a  test    rcx, rcx
0x180050d6d  jnz     short loc_180050DA9
0x180050d6f  mov     edi, r12d
0x180050d72  mov     rax, [rbx+50h]
0x180050d76  lea     rcx, [rbx+50h]
0x180050d7a  mov     rax, [rax+10h]
0x180050d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d83  test    rax, rax
0x180050d86  jz      loc_180051A4E
0x180050d8c  mov     rax, [rbx+50h]
0x180050d90  lea     rcx, [rbx+50h]
0x180050d94  mov     rax, [rax+10h]
0x180050d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d9d  xor     ecx, ecx
0x180050d9f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180050da4  jmp     loc_180051A4E
0x180050da9  add     rcx, 8
0x180050dad  mov     rax, [rcx]
0x180050db0  lea     r8, [rbp+57h+var_7C]
0x180050db4  lea     rdx, aState; "State"
0x180050dbb  mov     rax, [rax]
0x180050dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dc3  mov     edi, eax
0x180050dc5  test    eax, eax
0x180050dc7  jns     short loc_180050E37
0x180050dc9  mov     rdx, [rbx+50h]
0x180050dcd  lea     rcx, [rbx+50h]
0x180050dd1  mov     rax, [rdx+10h]
0x180050dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dda  test    rax, rax
0x180050ddd  jz      loc_180051A4E
0x180050de3  mov     rax, [rbx+50h]
0x180050de7  lea     rcx, [rbx+50h]
0x180050deb  mov     rax, [rax+10h]
0x180050def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050df4  mov     ecx, r12d
0x180050df7  test    rax, rax
0x180050dfa  jz      short loc_180050D9F
0x180050dfc  mov     [rsp+0D0h+var_A8], edi
0x180050e00  mov     [rsp+0D0h+var_B0], 945h
0x180050e08  lea     r9, aCdlpmanagerDes; "CDlpManager::Deserialize"
0x180050e0f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180050e16  mov     edx, 4
0x180050e1b  mov     rcx, rax
0x180050e1e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180050e23  mov     ecx, eax
0x180050e25  test    eax, eax
0x180050e27  jns     loc_180050D9F
0x180050e2d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180050e32  jmp     loc_180050D9F
0x180050e37  mov     rcx, [rbx+298h]
0x180050e3e  add     rcx, 8
0x180050e42  mov     rax, [rcx]
0x180050e45  lea     r8, [rbp+57h+arg_18]
0x180050e49  lea     rdx, aTaskcount; "TaskCount"
0x180050e50  mov     rax, [rax]
0x180050e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e58  mov     edi, eax
0x180050e5a  test    eax, eax
0x180050e5c  jns     short loc_180050EA6
0x180050e5e  mov     rax, [rbx+50h]
0x180050e62  lea     rcx, [rbx+50h]
0x180050e66  mov     rax, [rax+10h]
0x180050e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e6f  test    rax, rax
0x180050e72  jz      loc_180051A4E
0x180050e78  mov     rax, [rbx+50h]
0x180050e7c  lea     rcx, [rbx+50h]
0x180050e80  mov     rax, [rax+10h]
0x180050e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e89  mov     ecx, r12d
0x180050e8c  test    rax, rax
0x180050e8f  jz      loc_180050D9F
0x180050e95  mov     [rsp+0D0h+var_A8], edi
0x180050e99  mov     [rsp+0D0h+var_B0], 948h
0x180050ea1  jmp     loc_180050E08
0x180050ea6  mov     rcx, [rbx+298h]
0x180050ead  add     rcx, 8
0x180050eb1  mov     rax, [rcx]
0x180050eb4  lea     r8, [rbp+57h+arg_0]
0x180050eb8  lea     rdx, aStringcount; "StringCount"
0x180050ebf  mov     rax, [rax]
0x180050ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ec7  mov     edi, eax
0x180050ec9  test    eax, eax
0x180050ecb  jns     short loc_180050F15
0x180050ecd  mov     rax, [rbx+50h]
0x180050ed1  lea     rcx, [rbx+50h]
0x180050ed5  mov     rax, [rax+10h]
0x180050ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ede  test    rax, rax
0x180050ee1  jz      loc_180051A4E
0x180050ee7  mov     rax, [rbx+50h]
0x180050eeb  lea     rcx, [rbx+50h]
0x180050eef  mov     rax, [rax+10h]
0x180050ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ef8  mov     ecx, r12d
0x180050efb  test    rax, rax
0x180050efe  jz      loc_180050D9F
0x180050f04  mov     [rsp+0D0h+var_A8], edi
0x180050f08  mov     [rsp+0D0h+var_B0], 94Bh
0x180050f10  jmp     loc_180050E08
0x180050f15  mov     rcx, [rbx+298h]
0x180050f1c  add     rcx, 8
0x180050f20  mov     rax, [rcx]
0x180050f23  lea     r8, [rbp+57h+arg_8]
0x180050f27  lea     rdx, aDwordcount; "DwordCount"
0x180050f2e  mov     rax, [rax]
0x180050f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f36  mov     edi, eax
0x180050f38  test    eax, eax
0x180050f3a  jns     short loc_180050F84
0x180050f3c  mov     rax, [rbx+50h]
0x180050f40  lea     rcx, [rbx+50h]
0x180050f44  mov     rax, [rax+10h]
0x180050f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f4d  test    rax, rax
0x180050f50  jz      loc_180051A4E
0x180050f56  mov     rax, [rbx+50h]
0x180050f5a  lea     rcx, [rbx+50h]
0x180050f5e  mov     rax, [rax+10h]
0x180050f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f67  mov     ecx, r12d
0x180050f6a  test    rax, rax
0x180050f6d  jz      loc_180050D9F
0x180050f73  mov     [rsp+0D0h+var_A8], edi
0x180050f77  mov     [rsp+0D0h+var_B0], 94Eh
0x180050f7f  jmp     loc_180050E08
0x180050f84  mov     rcx, [rbx+298h]
0x180050f8b  add     rcx, 8
0x180050f8f  mov     rax, [rcx]
0x180050f92  lea     r8, [rbp+57h+arg_10]
0x180050f96  lea     rdx, aQuadwordcount; "QuadwordCount"
0x180050f9d  mov     rax, [rax]
0x180050fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fa5  mov     edi, eax
0x180050fa7  test    eax, eax
0x180050fa9  jns     short loc_180050FF3
0x180050fab  mov     rax, [rbx+50h]
0x180050faf  lea     rcx, [rbx+50h]
0x180050fb3  mov     rax, [rax+10h]
0x180050fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fbc  test    rax, rax
0x180050fbf  jz      loc_180051A4E
0x180050fc5  mov     rax, [rbx+50h]
0x180050fc9  lea     rcx, [rbx+50h]
0x180050fcd  mov     rax, [rax+10h]
0x180050fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fd6  mov     ecx, r12d
0x180050fd9  test    rax, rax
0x180050fdc  jz      loc_180050D9F
0x180050fe2  mov     [rsp+0D0h+var_A8], edi
0x180050fe6  mov     [rsp+0D0h+var_B0], 951h
0x180050fee  jmp     loc_180050E08
0x180050ff3  mov     esi, r12d
0x180050ff6  cmp     [rbp+57h+arg_0], r12d
0x180050ffa  jbe     loc_1800510FC
0x180051000  mov     rcx, [rbp+57h+var_A0]
0x180051004  test    rcx, rcx
0x180051007  jz      short loc_18005101A
0x180051009  mov     rax, [rcx]
0x18005100c  mov     rax, [rax+10h]
0x180051010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051015  nop
0x180051016  mov     [rbp+57h+var_A0], r12
0x18005101a  mov     rcx, [rbx+298h]
0x180051021  mov     rax, [rcx]
0x180051024  lea     r9, [rbp+57h+var_A0]
0x180051028  mov     r8d, esi
0x18005102b  lea     rdx, aStringproperty; "StringProperty"
0x180051032  mov     rax, [rax+20h]
0x180051036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005103b  mov     edi, eax
0x18005103d  test    eax, eax
0x18005103f  js      loc_18005153A
0x180051045  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180051049  test    rcx, rcx
0x18005104c  jz      short loc_180051058
0x18005104e  call    cs:__imp_SysFreeString
0x180051054  mov     [rbp+57h+bstrString], r12
0x180051058  mov     rcx, [rbp+57h+var_A0]
0x18005105c  add     rcx, 8
0x180051060  mov     rax, [rcx]
0x180051063  lea     r8, [rbp+57h+bstrString]
0x180051067  lea     rdx, aName; "Name"
0x18005106e  mov     rax, [rax+10h]
0x180051072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051077  mov     edi, eax
0x180051079  test    eax, eax
0x18005107b  js      loc_1800514F2
0x180051081  mov     rcx, [rbp+57h+var_88]; bstrString
0x180051085  test    rcx, rcx
0x180051088  jz      short loc_180051094
0x18005108a  call    cs:__imp_SysFreeString
0x180051090  mov     [rbp+57h+var_88], r12
0x180051094  mov     rcx, [rbp+57h+var_A0]
0x180051098  add     rcx, 8
0x18005109c  mov     rax, [rcx]
0x18005109f  lea     r8, [rbp+57h+var_88]
0x1800510a3  lea     rdx, aValue; "Value"
0x1800510aa  mov     rax, [rax+10h]
0x1800510ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510b3  mov     edi, eax
0x1800510b5  test    eax, eax
0x1800510b7  js      loc_1800514AA
0x1800510bd  lea     rcx, [rbx+220h]
0x1800510c4  lea     rdx, [rbp+57h+bstrString]
0x1800510c8  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x1800510cd  mov     edi, eax
0x1800510cf  test    eax, eax
0x1800510d1  js      loc_180051462
0x1800510d7  lea     rcx, [rbx+230h]
0x1800510de  lea     rdx, [rbp+57h+var_88]
0x1800510e2  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x1800510e7  mov     edi, eax
0x1800510e9  test    eax, eax
0x1800510eb  js      loc_18005141A
0x1800510f1  inc     esi
0x1800510f3  cmp     esi, [rbp+57h+arg_0]
0x1800510f6  jb      loc_180051000
0x1800510fc  mov     esi, r12d
0x1800510ff  cmp     [rbp+57h+arg_8], r12d
0x180051103  jbe     loc_1800511F0
0x180051109  mov     rcx, [rbp+57h+var_A0]
0x18005110d  test    rcx, rcx
0x180051110  jz      short loc_180051123
0x180051112  mov     rax, [rcx]
0x180051115  mov     rax, [rax+10h]
0x180051119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005111e  nop
0x18005111f  mov     [rbp+57h+var_A0], r12
0x180051123  mov     rcx, [rbx+298h]
0x18005112a  mov     rax, [rcx]
0x18005112d  lea     r9, [rbp+57h+var_A0]
0x180051131  mov     r8d, esi
0x180051134  lea     rdx, aDwordproperty; "DwordProperty"
0x18005113b  mov     rax, [rax+20h]
0x18005113f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051144  mov     edi, eax
0x180051146  test    eax, eax
0x180051148  js      loc_1800516A2
0x18005114e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180051152  test    rcx, rcx
0x180051155  jz      short loc_180051161
0x180051157  call    cs:__imp_SysFreeString
0x18005115d  mov     [rbp+57h+bstrString], r12
0x180051161  mov     rcx, [rbp+57h+var_A0]
0x180051165  add     rcx, 8
0x180051169  mov     rax, [rcx]
0x18005116c  lea     r8, [rbp+57h+bstrString]
0x180051170  lea     rdx, aName; "Name"
0x180051177  mov     rax, [rax+10h]
0x18005117b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051180  mov     edi, eax
0x180051182  test    eax, eax
0x180051184  js      loc_18005165A
0x18005118a  mov     rcx, [rbp+57h+var_A0]
0x18005118e  add     rcx, 8
0x180051192  mov     rax, [rcx]
0x180051195  lea     r8, [rbp+57h+var_80]
  ... truncated ...
```
