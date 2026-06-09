# DrvGetRegistryHandleFromDeviceMap(tagGRAPHICS_DEVICE *,_DISP_DRIVER_REGISTRY_TYPE,ulong const *,ushort *,ulong,long *)

- ea: `0x1400d5750`
- end: `0x1400d6178`
- name: `?DrvGetRegistryHandleFromDeviceMap@@YAPEAXPEAUtagGRAPHICS_DEVICE@@W4_DISP_DRIVER_REGISTRY_TYPE@@PEBKPEAGKPEAJ@Z`
- size: `2600`
- prototype: `HANDLE __fastcall(unsigned __int16 *, int, unsigned int *, unsigned __int16 *, unsigned int, NTSTATUS *)`
- caller_count: `11`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000e5e0`
- `0x140019410`
- `0x1400d27e0`
- `0x1400d4fc8`
- `0x1400d565c`
- `0x14015355c`
- `0x140167bd8`
- `0x14016e6b4`
- `0x140176e58`
- `0x14017cc28`
- `0x14018f010`

## callees

- `0x14006a6d0`
- `0x14007ab04`
- `0x14007b930`
- `0x1400972fc`
- `0x1400a2b80`
- `0x1400d5750`
- `0x1400d62d0`
- `0x140111520`
- `0x14016cc8c`
- `0x1401ad940`
- `0x1401ad994`
- `0x1401c4f5c`
- `0x1401c5198`
- `0x1401c55b4`
- `0x1401c5624`
- `0x1402388e0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400d5b64`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d5b64`
- `ntoskrnl!ZwOpenKey` at `0x1400d58c3`
- `ntoskrnl!ZwOpenKey` at `0x1400d5afa`
- `ntoskrnl!ZwOpenKey` at `0x1400d5e82`
- `ntoskrnl!ZwOpenKey` at `0x1400d58c3`
- `ntoskrnl!ZwOpenKey` at `0x1400d5afa`
- `ntoskrnl!ZwOpenKey` at `0x1400d5e82`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d5939`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d5ee2`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d5939`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d5ee2`
- `ntoskrnl!ZwClose` at `0x1400d59a9`
- `ntoskrnl!ZwClose` at `0x1400d5f98`
- `ntoskrnl!ZwClose` at `0x1400d60d3`
- `ntoskrnl!ZwClose` at `0x1400d59a9`
- `ntoskrnl!ZwClose` at `0x1400d5f98`
- `ntoskrnl!ZwClose` at `0x1400d60d3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5a92`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5ae0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5ce5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5d0f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d6014`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d6041`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d60bd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5a92`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5ae0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5ce5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d5d0f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d6014`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d6041`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400d60bd`
- `ntoskrnl!ZwCreateKey` at `0x1400d6082`
- `ntoskrnl!ZwCreateKey` at `0x1400d60fc`
- `ntoskrnl!ZwCreateKey` at `0x1400d6082`
- `ntoskrnl!ZwCreateKey` at `0x1400d60fc`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400d6020`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400d6020`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d5886`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d590c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d5e42`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d5ea7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d5886`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d590c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d5e42`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d5ea7`
- `watchdog!WdLogSingleEntry3` at `0x1400d57fb`
- `watchdog!WdLogSingleEntry3` at `0x1400d57fb`
- `watchdog!WdLogSingleEntry1` at `0x1400d59d4`
- `watchdog!WdLogSingleEntry1` at `0x1400d6130`
- `watchdog!WdLogSingleEntry1` at `0x1400d59d4`
- `watchdog!WdLogSingleEntry1` at `0x1400d6130`
- `WIN32K!W32GetSessionState` at `0x1400d57da`
- `WIN32K!W32GetSessionState` at `0x1400d5b8d`
- `WIN32K!W32GetSessionState` at `0x1400d57da`
- `WIN32K!W32GetSessionState` at `0x1400d5b8d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d5b54`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d5b54`

## string_xrefs

- `0x1400d587a`: `\Registry\Machine\Hardware\DeviceMap\Video`
- `0x1400d5a79`: `\Registry\Machine\System\CurrentControlSet`
- `0x1400d5cd1`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server\Video\`
- `0x1400d5e9b`: `Service`
- `0x1400d5d52`: `\SERVICES`

## pseudocode

```c
HANDLE __fastcall DrvGetRegistryHandleFromDeviceMap(
        unsigned __int16 *a1,
        int a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        NTSTATUS *a6)
{
  __int64 v6; // rbx
  unsigned int *v9; // r14
  __int64 v11; // rcx
  __int64 v12; // r13
  __int64 v13; // rdx
  int v14; // esi
  NTSTATUS v15; // ebx
  const WCHAR *v16; // rdx
  unsigned __int16 *v17; // rsi
  WCHAR *v18; // rbx
  ULONG v19; // r15d
  WCHAR *v20; // rdi
  HANDLE result; // rax
  wchar_t *v22; // rsi
  __int64 v23; // r13
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int16 *v35; // rax
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  const WCHAR *v45; // rdx
  __int64 v46; // rcx
  int v47; // r12d
  char *v48; // rcx
  __int64 v49; // rax
  unsigned __int64 Length; // r15
  unsigned __int16 *v51; // rax
  unsigned __int16 *v52; // rbx
  __int64 v53; // r11
  __int64 v54; // rdx
  unsigned __int16 *i; // rcx
  unsigned __int16 *v56; // r15
  unsigned __int16 v57; // ax
  int v58; // ecx
  wchar_t *v59; // r15
  wchar_t *v60; // r13
  wchar_t *v61; // rbx
  wchar_t *v62; // rax
  wchar_t *v63; // rdi
  WCHAR *v65; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v66; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v68; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str1; // [rsp+68h] [rbp-98h]
  size_t Size; // [rsp+70h] [rbp-90h]
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  ULONG ResultLength; // [rsp+C0h] [rbp-40h] BYREF
  ULONG v75[2]; // [rsp+C8h] [rbp-38h] BYREF
  ULONG v76; // [rsp+D0h] [rbp-30h]
  HANDLE Handle; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v78; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v79; // [rsp+E8h] [rbp-18h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  unsigned int *v81; // [rsp+F8h] [rbp-8h]
  NTSTATUS *v82; // [rsp+100h] [rbp+0h]
  unsigned __int16 v83[152]; // [rsp+110h] [rbp+10h] BYREF

  v6 = a2;
  v82 = a6;
  v81 = a3;
  v68 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  v78 = a4;
  v9 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(v83, 0, sizeof(v83));
  v12 = *(_QWORD *)(W32GetSessionState(v11) + 88);
  v80 = v12;
  WdLogSingleEntry3(5, a1, v6, a3);
  WdLogGlobalForLineNumber = 2078;
  if ( a4 && !a5 )
  {
    v20 = 0;
LABEL_16:
    v15 = -1073741811;
    goto LABEL_17;
  }
  v14 = 0;
  if ( *(_DWORD *)(v12 + 3000) )
  {
    v28 = *(_QWORD *)(W32GetSessionState(0) + 88);
    if ( (unsigned int)UserIsRemoteAndNotDisconnectConnection(v30, v29, v31, v32) )
    {
      if ( *(_QWORD *)(v28 + 3016) )
      {
        v25 = *(_QWORD *)(W32GetUserGdiSessionState(0) + 40);
        if ( PsGetCurrentProcess(v26) != v25
          && !UserIsCurrentProcessDwm(v27, v13)
          && (*((_DWORD *)a1 + 40) & 0x4000000) != 0 )
        {
          v34 = 2;
          v35 = v83;
          do
          {
            v36 = *((_OWORD *)a1 + 1);
            *(_OWORD *)v35 = *(_OWORD *)a1;
            v37 = *((_OWORD *)a1 + 2);
            *((_OWORD *)v35 + 1) = v36;
            v38 = *((_OWORD *)a1 + 3);
            *((_OWORD *)v35 + 2) = v37;
            v39 = *((_OWORD *)a1 + 4);
            *((_OWORD *)v35 + 3) = v38;
            v40 = *((_OWORD *)a1 + 5);
            *((_OWORD *)v35 + 4) = v39;
            v41 = *((_OWORD *)a1 + 6);
            *((_OWORD *)v35 + 5) = v40;
            v42 = *((_OWORD *)a1 + 7);
            a1 += 64;
            *((_OWORD *)v35 + 6) = v41;
            *((_OWORD *)v35 + 7) = v42;
            v35 += 64;
            --v34;
          }
          while ( v34 );
          v43 = *((_OWORD *)a1 + 1);
          *(_OWORD *)v35 = *(_OWORD *)a1;
          v44 = *((_OWORD *)a1 + 2);
          a1 = v83;
          *((_OWORD *)v35 + 1) = v43;
          *((_OWORD *)v35 + 2) = v44;
          StringCchCopyW(v83, 0x20u, (unsigned __int16 *)(v12 + 3024));
          *(_DWORD *)&v83[80] &= ~0x4000000u;
        }
      }
    }
    LODWORD(v6) = a2;
  }
  if ( (*((_DWORD *)a1 + 40) & 8) != 0 )
  {
    v33 = (unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
    Str1 = (wchar_t *)(unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
    if ( (Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState & 0x10) == 0 )
    {
      v66 = __PAIR64__(HIDWORD(Str1), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u);
      wil_details_FeatureReporting_ReportUsageToService(
        Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor,
        __PAIR64__(HIDWORD(Str1), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u),
        3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
        v66,
        3,
        Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor);
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v33, v13);
    v14 = 1;
  }
  v65 = (WCHAR *)PALLOCMEM(512, 1886221383);
  if ( !v65 )
  {
    v15 = -1073741670;
    v20 = 0;
    goto LABEL_17;
  }
  if ( (*((_DWORD *)a1 + 40) & 0x4000000) == 0 || v14 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Hardware\\DeviceMap\\Video");
  }
  else
  {
    if ( (unsigned int)(v6 - 1) <= 1 )
    {
      v15 = -1073741766;
      v20 = v65;
      goto LABEL_17;
    }
    DestinationString.Buffer = v65;
    *(_DWORD *)&DestinationString.Length = 33423360;
    RtlAppendUnicodeToString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server\\Video\\");
    v45 = L"vgastub";
    if ( *(_QWORD *)(v80 + 2976) )
      v45 = *(const WCHAR **)(v80 + 2976);
    RtlAppendUnicodeToString(&DestinationString, v45);
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v15 < 0 )
    goto LABEL_106;
  v9 = (unsigned int *)PALLOCMEM(1024, 1886221383);
  if ( !v9 )
  {
    v15 = -1073741670;
    goto LABEL_36;
  }
  if ( (*((_DWORD *)a1 + 40) & 0x4000000) == 0 || (v16 = L"\\Device\\Video0", v14) )
    v16 = a1;
  RtlInitUnicodeString(&DestinationString, v16);
  v15 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, v9, 0x200u, &ResultLength);
  if ( v15 < 0 )
  {
LABEL_106:
    WdLogSingleEntry1(5, v15);
    WdLogGlobalForLineNumber = 2623;
    goto LABEL_36;
  }
  v17 = (unsigned __int16 *)((char *)v9 + v9[2]);
  Destination = 0;
  if ( a2 != 3 )
  {
    v18 = (WCHAR *)(v9 + 128);
    v76 = 0;
    v19 = 0;
    while ( *v17 )
    {
      *v17 = toupper(*v17);
      ++v17;
    }
    v22 = wcsstr((const wchar_t *)((char *)v9 + v9[2]), L"\\CONTROL\\");
    if ( !v22 )
      v22 = wcsstr((const wchar_t *)((char *)v9 + v9[2]), L"\\SERVICES");
    v23 = -1;
    if ( v78 )
    {
      v46 = v9[2];
      v47 = a5 - 1;
      Str1 = v78;
      Handle = 0;
      if ( a5 - 1 > 0x1F )
        v47 = 31;
      v48 = (char *)v9 + v46;
      v49 = -1;
      do
        ++v49;
      while ( *(_WORD *)&v48[2 * v49] );
      *(_QWORD *)v75 = (int)v49;
      Length = 2LL * (int)v49 + 12;
      if ( Length <= 0x66 )
        LODWORD(Length) = 102;
      v51 = (unsigned __int16 *)PALLOCMEM((unsigned int)Length, 1936876615);
      v79 = v51;
      v52 = v51;
      if ( v51 )
      {
        Size = (int)Length;
        memset(v51, 0, (int)Length);
        StringCchCopyW(v52, Size >> 1, (unsigned __int16 *)((char *)v9 + v9[2]));
        v54 = 92;
        for ( i = &v52[*(_QWORD *)v75 - 1]; i > v52; --i )
        {
          if ( *i == 92 )
            goto LABEL_76;
        }
        if ( *i != 92 )
          goto LABEL_90;
LABEL_76:
        StringCchCopyW(i + 1, v53 - *(_QWORD *)v75, L"Video");
        RtlInitUnicodeString(&DestinationString, v52);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          v75[0] = 0;
          RtlInitUnicodeString(&DestinationString, L"Service");
          memset(v52, 0, Size);
          if ( ZwQueryValueKey(Handle, &DestinationString, KeyValueFullInformation, v52, Length, v75) >= 0 )
          {
            v56 = (unsigned __int16 *)((char *)v52 + *((unsigned int *)v52 + 2));
            v57 = *v56;
            if ( *v56 )
            {
              do
              {
                *v56++ = toupper(v57);
                v57 = *v56;
              }
              while ( *v56 );
              v52 = v79;
            }
            v58 = v47;
            v59 = (unsigned __int16 *)((char *)v52 + *((unsigned int *)v52 + 2));
            LODWORD(Size) = v47;
            if ( v47 )
            {
              v60 = Str1;
              v61 = Str1;
              do
              {
                if ( !*v59 )
                  break;
                *v60 = *v59;
                --v47;
                Str1 = ++v60;
                if ( v47 == v58 - 3 )
                {
                  if ( !wcsnicmp(v61, L"VGA", 3u) )
                    break;
                  v58 = Size;
                }
                ++v59;
              }
              while ( v47 );
              v52 = v79;
              v23 = -1;
            }
          }
          ZwClose(Handle);
        }
LABEL_90:
        GreDeleteFastMutex(v52, v54);
      }
      v18 = (WCHAR *)(v9 + 128);
      v19 = v76;
      *Str1 = 0;
    }
    if ( v81 )
    {
      do
        ++v23;
      while ( v22[v23] );
      StringCchPrintfW(
        &v22[v23],
        512 - ((unsigned int)(((char *)v22 - (char *)v9) >> 1) >> 1) - (unsigned int)v23,
        L"\\Mon%08X",
        *v81);
    }
    Destination.Buffer = v18;
    *(_DWORD *)&Destination.Length = 33423360;
    RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet");
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      if ( (*((_DWORD *)a1 + 40) & 0x800000) != 0 )
      {
        RtlAppendUnicodeToString(&Destination, L"\\Control\\UnitedVideo");
        v19 = (unsigned __int8)RtlIsStateSeparationEnabled() != 0;
      }
      else
      {
        RtlAppendUnicodeToString(&Destination, L"\\Hardware Profiles\\Current\\System\\CurrentControlSet");
      }
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &Destination;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    if ( a2 == 2 )
    {
      ObjectAttributes.SecurityDescriptor = *(PVOID *)(v80 + 1824);
      ObjectAttributes.SecurityQualityOfService = 0;
      v15 = ZwCreateKey(&v68, 0, &ObjectAttributes, 0, 0, v19, 0);
      if ( v15 >= 0 )
      {
        while ( 1 )
        {
          v62 = wcschr(v22 + 1, 0x5Cu);
          v63 = v62;
          if ( v62 )
            *v62 = 0;
          RtlAppendUnicodeToString(&Destination, v22);
          if ( v68 )
            ZwClose(v68);
          v15 = ZwCreateKey(&v68, 0, &ObjectAttributes, 0, 0, v19, 0);
          if ( v15 < 0 )
            break;
          if ( !v63 )
            goto LABEL_36;
          *v63 = 92;
          v22 = v63;
        }
      }
      v68 = 0;
    }
    else
    {
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      RtlAppendUnicodeToString(&Destination, v22);
      v15 = ZwOpenKey(&v68, 0x20019u, &ObjectAttributes);
      if ( v15 >= 0 )
      {
LABEL_36:
        v20 = v65;
        goto LABEL_17;
      }
      v15 = -1073741438;
    }
    goto LABEL_106;
  }
  if ( !a4 )
    goto LABEL_36;
  v24 = StringCchCopyNW(a4, a5, v17, 0x7Fu);
  v13 = 0x80000000LL;
  if ( (int)(v24 + 0x80000000) < 0 )
    goto LABEL_36;
  v20 = v65;
  if ( v24 != -2147024774 )
    goto LABEL_16;
LABEL_17:
  if ( v82 )
    *v82 = v15;
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v20 )
    GreDeleteFastMutex(v20, v13);
  if ( v9 )
    GreDeleteFastMutex(v9, v13);
  WdLogSingleEntry1(5, v15);
  result = v68;
  WdLogGlobalForLineNumber = 2647;
  return result;
}

```

## disassembly

```asm
0x1400d5750  push    rbp
0x1400d5752  push    rbx
0x1400d5753  push    rsi
0x1400d5754  push    rdi
0x1400d5755  push    r12
0x1400d5757  push    r13
0x1400d5759  push    r14
0x1400d575b  push    r15
0x1400d575d  lea     rbp, [rsp-158h]
0x1400d5765  sub     rsp, 258h
0x1400d576c  mov     rax, cs:__security_cookie
0x1400d5773  xor     rax, rsp
0x1400d5776  mov     [rbp+190h+var_50], rax
0x1400d577d  mov     rax, [rbp+190h+arg_28]
0x1400d5784  xorps   xmm1, xmm1
0x1400d5787  movsxd  rbx, edx
0x1400d578a  mov     rsi, r8
0x1400d578d  mov     [rbp+190h+var_190], rax
0x1400d5791  mov     rdi, rcx
0x1400d5794  xor     eax, eax
0x1400d5796  mov     [rbp+190h+var_198], r8
0x1400d579a  xorps   xmm0, xmm0
0x1400d579d  mov     [rsp+290h+var_230], rax
0x1400d57a2  xor     edx, edx; Val
0x1400d57a4  mov     [rsp+290h+KeyHandle], rax
0x1400d57a9  mov     r8d, 130h; Size
0x1400d57af  mov     [rbp+190h+var_1D0], eax
0x1400d57b2  lea     rcx, [rbp+190h+var_180]; void *
0x1400d57b6  mov     [rbp+190h+var_1B0], r9
0x1400d57ba  mov     r14d, eax
0x1400d57bd  mov     [rsp+290h+var_250], ebx
0x1400d57c1  mov     r15, r9
0x1400d57c4  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x1400d57c9  movups  xmmword ptr [rbp+190h+ObjectAttributes.Length], xmm1
0x1400d57cd  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm1
0x1400d57d1  movups  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400d57d5  call    memset
0x1400d57da  call    cs:__imp_W32GetSessionState
0x1400d57e1  nop     dword ptr [rax+rax+00h]
0x1400d57e6  mov     r13, [rax+58h]
0x1400d57ea  mov     [rbp+190h+var_1A0], r13
0x1400d57ee  mov     r8, rbx
0x1400d57f1  lea     ecx, [r14+5]
0x1400d57f5  mov     r9, rsi
0x1400d57f8  mov     rdx, rdi
0x1400d57fb  call    cs:__imp_WdLogSingleEntry3
0x1400d5802  nop     dword ptr [rax+rax+00h]
0x1400d5807  mov     r12d, dword ptr [rbp+190h+arg_20]
0x1400d580e  xor     ecx, ecx
0x1400d5810  mov     cs:WdLogGlobalForLineNumber, 81Eh
0x1400d581a  test    r15, r15
0x1400d581d  jnz     loc_1400D597E
0x1400d5823  mov     esi, ecx
0x1400d5825  cmp     [r13+0BB8h], ecx
0x1400d582c  jnz     loc_1400D5B8D
0x1400d5832  mov     eax, [rdi+0A0h]
0x1400d5838  mov     r13d, 1
0x1400d583e  test    al, 8
0x1400d5840  jnz     loc_1400D5BB3
0x1400d5846  mov     r13d, 200h
0x1400d584c  mov     edx, 706D7447h
0x1400d5851  mov     ecx, r13d
0x1400d5854  call    PALLOCMEM
0x1400d5859  mov     [rsp+290h+var_248], rax
0x1400d585e  mov     rcx, rax
0x1400d5861  test    rax, rax
0x1400d5864  jz      loc_1400D5A13
0x1400d586a  test    dword ptr [rdi+0A0h], 4000000h
0x1400d5874  jnz     loc_1400D5CBC
0x1400d587a  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Hardware\\DeviceMa"...
0x1400d5881  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1400d5886  call    cs:__imp_RtlInitUnicodeString
0x1400d588d  nop     dword ptr [rax+rax+00h]
0x1400d5892  lea     rax, [rsp+290h+DestinationString]
0x1400d5897  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400d589e  xorps   xmm0, xmm0
0x1400d58a1  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x1400d58a5  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x1400d58a9  mov     [rbp+190h+ObjectAttributes.RootDirectory], r14
0x1400d58ad  mov     edx, 20019h; DesiredAccess
0x1400d58b2  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x1400d58b9  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1400d58be  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d58c3  call    cs:__imp_ZwOpenKey
0x1400d58ca  nop     dword ptr [rax+rax+00h]
0x1400d58cf  mov     ebx, eax
0x1400d58d1  test    eax, eax
0x1400d58d3  js      loc_1400D6152
0x1400d58d9  mov     edx, 706D7447h
0x1400d58de  mov     ecx, 400h
0x1400d58e3  call    PALLOCMEM
0x1400d58e8  mov     r14, rax
0x1400d58eb  test    rax, rax
0x1400d58ee  jz      loc_1400D5D2D
0x1400d58f4  test    dword ptr [rdi+0A0h], 4000000h
0x1400d58fe  jnz     loc_1400D5D3A
0x1400d5904  mov     rdx, rdi; SourceString
0x1400d5907  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1400d590c  call    cs:__imp_RtlInitUnicodeString
0x1400d5913  nop     dword ptr [rax+rax+00h]
0x1400d5918  mov     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1400d591d  lea     rax, [rbp+190h+var_1D0]
0x1400d5921  mov     [rsp+290h+ResultLength], rax; ResultLength
0x1400d5926  lea     rdx, [rsp+290h+DestinationString]; ValueName
0x1400d592b  mov     r9, r14; KeyValueInformation
0x1400d592e  mov     [rsp+290h+Length], r13d; Length
0x1400d5933  mov     r8d, 1; KeyValueInformationClass
0x1400d5939  call    cs:__imp_ZwQueryValueKey
0x1400d5940  nop     dword ptr [rax+rax+00h]
0x1400d5945  xor     r13d, r13d
0x1400d5948  mov     ebx, eax
0x1400d594a  test    eax, eax
0x1400d594c  js      loc_1400D6128
0x1400d5952  mov     esi, [r14+8]
0x1400d5956  xorps   xmm0, xmm0
0x1400d5959  add     rsi, r14
0x1400d595c  cmp     [rsp+290h+var_250], 3
0x1400d5961  movups  xmmword ptr [rbp+190h+Destination.Length], xmm0
0x1400d5965  jz      loc_1400D5B1A
0x1400d596b  lea     rbx, [r14+200h]
0x1400d5972  mov     [rbp+190h+var_1C0], r13d
0x1400d5976  mov     r15d, r13d
0x1400d5979  jmp     loc_1400D5A32
0x1400d597e  test    r12d, r12d
0x1400d5981  jnz     loc_1400D5823
0x1400d5987  xor     r13d, r13d
0x1400d598a  mov     edi, r13d
0x1400d598d  mov     ebx, 0C000000Dh
0x1400d5992  mov     rax, [rbp+190h+var_190]
0x1400d5996  test    rax, rax
0x1400d5999  jnz     loc_1400D6157
0x1400d599f  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x1400d59a4  test    rcx, rcx
0x1400d59a7  jz      short loc_1400D59BA
0x1400d59a9  call    cs:__imp_ZwClose
0x1400d59b0  nop     dword ptr [rax+rax+00h]
0x1400d59b5  mov     [rsp+290h+KeyHandle], r13
0x1400d59ba  test    rdi, rdi
0x1400d59bd  jnz     loc_1400D615E
0x1400d59c3  test    r14, r14
0x1400d59c6  jnz     loc_1400D616B
0x1400d59cc  movsxd  rdx, ebx
0x1400d59cf  mov     ecx, 5
0x1400d59d4  call    cs:__imp_WdLogSingleEntry1
0x1400d59db  nop     dword ptr [rax+rax+00h]
0x1400d59e0  mov     rax, [rsp+290h+var_230]
0x1400d59e5  mov     cs:WdLogGlobalForLineNumber, 0A57h
0x1400d59ef  mov     rcx, [rbp+190h+var_50]
0x1400d59f6  xor     rcx, rsp; StackCookie
0x1400d59f9  call    __security_check_cookie
0x1400d59fe  add     rsp, 258h
0x1400d5a05  pop     r15
0x1400d5a07  pop     r14
0x1400d5a09  pop     r13
0x1400d5a0b  pop     r12
0x1400d5a0d  pop     rdi
0x1400d5a0e  pop     rsi
0x1400d5a0f  pop     rbx
0x1400d5a10  pop     rbp
0x1400d5a11  retn
0x1400d5a13  mov     ebx, 0C000009Ah
0x1400d5a18  mov     rdi, rax
0x1400d5a1b  xor     r13d, r13d
0x1400d5a1e  jmp     loc_1400D5992
0x1400d5a23  movzx   ecx, ax; C
0x1400d5a26  call    toupper
0x1400d5a2b  mov     [rsi], ax
0x1400d5a2e  lea     rsi, [rsi+2]
0x1400d5a32  movzx   eax, word ptr [rsi]
0x1400d5a35  test    ax, ax
0x1400d5a38  jnz     short loc_1400D5A23
0x1400d5a3a  mov     ecx, [r14+8]
0x1400d5a3e  lea     rdx, aControl; "\\CONTROL\\"
0x1400d5a45  add     rcx, r14; Str
0x1400d5a48  call    wcsstr
0x1400d5a4d  mov     rsi, rax
0x1400d5a50  test    rax, rax
0x1400d5a53  jz      loc_1400D5D4E
0x1400d5a59  mov     rax, [rbp+190h+var_1B0]
0x1400d5a5d  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400d5a61  xor     edx, edx
0x1400d5a63  test    rax, rax
0x1400d5a66  jnz     loc_1400D5D69
0x1400d5a6c  mov     r9, [rbp+190h+var_198]
0x1400d5a70  test    r9, r9
0x1400d5a73  jnz     loc_1400D5FC6
0x1400d5a79  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400d5a80  mov     [rbp+190h+Destination.Buffer], rbx
0x1400d5a84  lea     rcx, [rbp+190h+Destination]; Destination
0x1400d5a88  mov     dword ptr [rbp+190h+Destination.Length], 1FE0000h
0x1400d5a8f  xor     r13d, r13d
0x1400d5a92  call    cs:__imp_RtlAppendUnicodeToString
0x1400d5a99  nop     dword ptr [rax+rax+00h]
0x1400d5a9e  mov     ebx, [rsp+290h+var_250]
0x1400d5aa2  lea     eax, [rbx-1]
0x1400d5aa5  cmp     eax, 1
0x1400d5aa8  jbe     loc_1400D5FFD
0x1400d5aae  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400d5ab5  lea     rax, [rbp+190h+Destination]
0x1400d5ab9  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x1400d5abd  mov     [rbp+190h+ObjectAttributes.RootDirectory], r13
0x1400d5ac1  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x1400d5ac8  cmp     ebx, 2
0x1400d5acb  jz      loc_1400D6052
0x1400d5ad1  xorps   xmm0, xmm0
0x1400d5ad4  lea     rcx, [rbp+190h+Destination]; Destination
0x1400d5ad8  mov     rdx, rsi; Source
0x1400d5adb  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d5ae0  call    cs:__imp_RtlAppendUnicodeToString
0x1400d5ae7  nop     dword ptr [rax+rax+00h]
0x1400d5aec  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x1400d5af0  mov     edx, 20019h; DesiredAccess
0x1400d5af5  lea     rcx, [rsp+290h+var_230]; KeyHandle
0x1400d5afa  call    cs:__imp_ZwOpenKey
0x1400d5b01  nop     dword ptr [rax+rax+00h]
0x1400d5b06  mov     ebx, eax
0x1400d5b08  test    eax, eax
0x1400d5b0a  js      loc_1400D614B
0x1400d5b10  mov     rdi, [rsp+290h+var_248]
0x1400d5b15  jmp     loc_1400D5992
0x1400d5b1a  test    r15, r15
0x1400d5b1d  jz      short loc_1400D5B10
0x1400d5b1f  mov     rdx, r12; unsigned __int64
0x1400d5b22  mov     r9d, 7Fh; unsigned __int64
0x1400d5b28  mov     r8, rsi; unsigned __int16 *
0x1400d5b2b  mov     rcx, r15; unsigned __int16 *
0x1400d5b2e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400d5b33  mov     edx, 80000000h
0x1400d5b38  lea     ecx, [rax+rdx]
0x1400d5b3b  test    edx, ecx
0x1400d5b3d  jnz     short loc_1400D5B10
0x1400d5b3f  mov     rdi, [rsp+290h+var_248]
0x1400d5b44  cmp     eax, 8007007Ah
0x1400d5b49  jz      loc_1400D5992
0x1400d5b4f  jmp     loc_1400D598D
0x1400d5b54  call    cs:__imp_W32GetUserGdiSessionState
0x1400d5b5b  nop     dword ptr [rax+rax+00h]
0x1400d5b60  mov     rbx, [rax+28h]
0x1400d5b64  call    cs:__imp_PsGetCurrentProcess
0x1400d5b6b  nop     dword ptr [rax+rax+00h]
0x1400d5b70  cmp     rax, rbx
0x1400d5b73  jz      loc_1400D5C6F
0x1400d5b79  call    UserIsCurrentProcessDwm
0x1400d5b7e  xor     ecx, ecx
0x1400d5b80  test    eax, eax
0x1400d5b82  jz      short loc_1400D5BD8
0x1400d5b84  mov     ebx, [rsp+290h+var_250]
0x1400d5b88  jmp     loc_1400D5832
0x1400d5b8d  call    cs:__imp_W32GetSessionState
0x1400d5b94  nop     dword ptr [rax+rax+00h]
0x1400d5b99  mov     rbx, [rax+58h]
0x1400d5b9d  call    UserIsRemoteAndNotDisconnectConnection
0x1400d5ba2  xor     ecx, ecx
0x1400d5ba4  test    eax, eax
0x1400d5ba6  jz      short loc_1400D5B84
0x1400d5ba8  cmp     [rbx+0BC8h], rcx
0x1400d5baf  jz      short loc_1400D5B84
0x1400d5bb1  jmp     short loc_1400D5B54
0x1400d5bb3  mov     [rsp+290h+Str1], rcx
0x1400d5bb8  mov     ecx, cs:Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState
0x1400d5bbe  mov     dword ptr [rsp+290h+Str1], ecx
0x1400d5bc2  test    cl, 10h
0x1400d5bc5  jz      loc_1400D5C76
0x1400d5bcb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400d5bd0  mov     esi, r13d
0x1400d5bd3  jmp     loc_1400D5846
0x1400d5bd8  test    dword ptr [rdi+0A0h], 4000000h
0x1400d5be2  jz      short loc_1400D5B84
0x1400d5be4  mov     ecx, 2
0x1400d5be9  lea     rax, [rbp+190h+var_180]
0x1400d5bed  lea     edx, [rcx+7Eh]
0x1400d5bf0  movups  xmm0, xmmword ptr [rdi]
0x1400d5bf3  movups  xmm1, xmmword ptr [rdi+10h]
0x1400d5bf7  movups  xmmword ptr [rax], xmm0
0x1400d5bfa  movups  xmm0, xmmword ptr [rdi+20h]
0x1400d5bfe  movups  xmmword ptr [rax+10h], xmm1
0x1400d5c02  movups  xmm1, xmmword ptr [rdi+30h]
0x1400d5c06  movups  xmmword ptr [rax+20h], xmm0
0x1400d5c0a  movups  xmm0, xmmword ptr [rdi+40h]
0x1400d5c0e  movups  xmmword ptr [rax+30h], xmm1
0x1400d5c12  movups  xmm1, xmmword ptr [rdi+50h]
0x1400d5c16  movups  xmmword ptr [rax+40h], xmm0
0x1400d5c1a  movups  xmm0, xmmword ptr [rdi+60h]
0x1400d5c1e  movups  xmmword ptr [rax+50h], xmm1
0x1400d5c22  movups  xmm1, xmmword ptr [rdi+70h]
0x1400d5c26  add     rdi, rdx
0x1400d5c29  movups  xmmword ptr [rax+60h], xmm0
0x1400d5c2d  movups  xmmword ptr [rax+70h], xmm1
0x1400d5c31  add     rax, rdx
0x1400d5c34  sub     rcx, 1
0x1400d5c38  jnz     short loc_1400D5BF0
0x1400d5c3a  movups  xmm0, xmmword ptr [rdi]
0x1400d5c3d  lea     edx, [rcx+20h]; unsigned __int64
0x1400d5c40  movups  xmm1, xmmword ptr [rdi+10h]
0x1400d5c44  lea     r8, [r13+0BD0h]; unsigned __int16 *
0x1400d5c4b  movups  xmmword ptr [rax], xmm0
0x1400d5c4e  lea     rcx, [rbp+190h+var_180]; unsigned __int16 *
0x1400d5c52  movups  xmm0, xmmword ptr [rdi+20h]
0x1400d5c56  lea     rdi, [rbp+190h+var_180]
0x1400d5c5a  movups  xmmword ptr [rax+10h], xmm1
  ... truncated ...
```
