# DrvGetRegistryHandleFromDeviceMap(tagGRAPHICS_DEVICE *,_DISP_DRIVER_REGISTRY_TYPE,ulong const *,ushort *,ulong,long *)

- ea: `0x1400abe40`
- end: `0x1400ac868`
- name: `?DrvGetRegistryHandleFromDeviceMap@@YAPEAXPEAUtagGRAPHICS_DEVICE@@W4_DISP_DRIVER_REGISTRY_TYPE@@PEBKPEAGKPEAJ@Z`
- size: `2600`
- prototype: ``
- caller_count: `11`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14005d990`
- `0x1400a8ed0`
- `0x1400ab6b8`
- `0x1400abd4c`
- `0x1400ad874`
- `0x1400ae89c`
- `0x1400fd3b0`
- `0x140153fe4`
- `0x140165648`
- `0x14016c794`
- `0x14017ac18`

## callees

- `0x140032170`
- `0x1400492a4`
- `0x14004a0d0`
- `0x14005f5bc`
- `0x1400abe40`
- `0x1400ac9c0`
- `0x1400b14e0`
- `0x140110520`
- `0x14016a5dc`
- `0x1401b3aec`
- `0x1401b9ce0`
- `0x1401c3e2c`
- `0x1401c4068`
- `0x1401c4484`
- `0x1401c44f4`
- `0x140238160`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400ac254`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ac254`
- `ntoskrnl!ZwOpenKey` at `0x1400abfb3`
- `ntoskrnl!ZwOpenKey` at `0x1400ac1ea`
- `ntoskrnl!ZwOpenKey` at `0x1400ac572`
- `ntoskrnl!ZwOpenKey` at `0x1400abfb3`
- `ntoskrnl!ZwOpenKey` at `0x1400ac1ea`
- `ntoskrnl!ZwOpenKey` at `0x1400ac572`
- `ntoskrnl!ZwQueryValueKey` at `0x1400ac029`
- `ntoskrnl!ZwQueryValueKey` at `0x1400ac5d2`
- `ntoskrnl!ZwQueryValueKey` at `0x1400ac029`
- `ntoskrnl!ZwQueryValueKey` at `0x1400ac5d2`
- `ntoskrnl!ZwClose` at `0x1400ac099`
- `ntoskrnl!ZwClose` at `0x1400ac688`
- `ntoskrnl!ZwClose` at `0x1400ac7c3`
- `ntoskrnl!ZwClose` at `0x1400ac099`
- `ntoskrnl!ZwClose` at `0x1400ac688`
- `ntoskrnl!ZwClose` at `0x1400ac7c3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac182`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac1d0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac3d5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac3ff`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac704`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac731`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac7ad`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac182`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac1d0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac3d5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac3ff`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac704`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac731`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400ac7ad`
- `ntoskrnl!ZwCreateKey` at `0x1400ac772`
- `ntoskrnl!ZwCreateKey` at `0x1400ac7ec`
- `ntoskrnl!ZwCreateKey` at `0x1400ac772`
- `ntoskrnl!ZwCreateKey` at `0x1400ac7ec`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400ac710`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400ac710`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400abf76`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400abffc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac532`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac597`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400abf76`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400abffc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac532`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac597`
- `watchdog!WdLogSingleEntry3` at `0x1400abeeb`
- `watchdog!WdLogSingleEntry3` at `0x1400abeeb`
- `watchdog!WdLogSingleEntry1` at `0x1400ac0c4`
- `watchdog!WdLogSingleEntry1` at `0x1400ac820`
- `watchdog!WdLogSingleEntry1` at `0x1400ac0c4`
- `watchdog!WdLogSingleEntry1` at `0x1400ac820`
- `WIN32K!W32GetSessionState` at `0x1400abeca`
- `WIN32K!W32GetSessionState` at `0x1400ac27d`
- `WIN32K!W32GetSessionState` at `0x1400abeca`
- `WIN32K!W32GetSessionState` at `0x1400ac27d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400ac244`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400ac244`

## string_xrefs

- `0x1400abf6a`: `\Registry\Machine\Hardware\DeviceMap\Video`
- `0x1400ac169`: `\Registry\Machine\System\CurrentControlSet`
- `0x1400ac3c1`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server\Video\`
- `0x1400ac442`: `\SERVICES`
- `0x1400ac58b`: `Service`

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
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  const WCHAR *v39; // rdx
  __int64 v40; // rcx
  int v41; // r12d
  char *v42; // rcx
  __int64 v43; // rax
  unsigned __int64 Length; // r15
  unsigned __int16 *v45; // rax
  unsigned __int16 *v46; // rbx
  __int64 v47; // r11
  unsigned __int16 *i; // rcx
  unsigned __int16 *v49; // r15
  unsigned __int16 v50; // ax
  int v51; // ecx
  wchar_t *v52; // r15
  wchar_t *v53; // r13
  wchar_t *v54; // rbx
  wchar_t *v55; // rax
  wchar_t *v56; // rdi
  WCHAR *v58; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v59; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v61; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str1; // [rsp+68h] [rbp-98h]
  size_t Size; // [rsp+70h] [rbp-90h]
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  ULONG ResultLength; // [rsp+C0h] [rbp-40h] BYREF
  ULONG v68[2]; // [rsp+C8h] [rbp-38h] BYREF
  ULONG v69; // [rsp+D0h] [rbp-30h]
  HANDLE Handle; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v71; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v72; // [rsp+E8h] [rbp-18h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  unsigned int *v74; // [rsp+F8h] [rbp-8h]
  NTSTATUS *v75; // [rsp+100h] [rbp+0h]
  unsigned __int16 v76[152]; // [rsp+110h] [rbp+10h] BYREF

  v6 = a2;
  v75 = a6;
  v74 = a3;
  v61 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  v71 = a4;
  v9 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(v76, 0, sizeof(v76));
  v12 = *(_QWORD *)(W32GetSessionState(v11) + 88);
  v73 = v12;
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
    v26 = *(_QWORD *)(W32GetSessionState(0) + 88);
    if ( (unsigned int)UserIsRemoteAndNotDisconnectConnection() )
    {
      if ( *(_QWORD *)(v26 + 3016) )
      {
        v25 = *(_QWORD *)(W32GetUserGdiSessionState() + 40);
        if ( PsGetCurrentProcess() != v25
          && !(unsigned int)UserIsCurrentProcessDwm()
          && (*((_DWORD *)a1 + 40) & 0x4000000) != 0 )
        {
          v28 = 2;
          v29 = v76;
          do
          {
            v30 = *((_OWORD *)a1 + 1);
            *(_OWORD *)v29 = *(_OWORD *)a1;
            v31 = *((_OWORD *)a1 + 2);
            *((_OWORD *)v29 + 1) = v30;
            v32 = *((_OWORD *)a1 + 3);
            *((_OWORD *)v29 + 2) = v31;
            v33 = *((_OWORD *)a1 + 4);
            *((_OWORD *)v29 + 3) = v32;
            v34 = *((_OWORD *)a1 + 5);
            *((_OWORD *)v29 + 4) = v33;
            v35 = *((_OWORD *)a1 + 6);
            *((_OWORD *)v29 + 5) = v34;
            v36 = *((_OWORD *)a1 + 7);
            a1 += 64;
            *((_OWORD *)v29 + 6) = v35;
            *((_OWORD *)v29 + 7) = v36;
            v29 += 64;
            --v28;
          }
          while ( v28 );
          v37 = *((_OWORD *)a1 + 1);
          *(_OWORD *)v29 = *(_OWORD *)a1;
          v38 = *((_OWORD *)a1 + 2);
          a1 = v76;
          *((_OWORD *)v29 + 1) = v37;
          *((_OWORD *)v29 + 2) = v38;
          StringCchCopyW(v76, 0x20u, (const unsigned __int16 *)(v12 + 3024));
          *(_DWORD *)&v76[80] &= ~0x4000000u;
        }
      }
    }
    LODWORD(v6) = a2;
  }
  if ( (*((_DWORD *)a1 + 40) & 8) != 0 )
  {
    v27 = (unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
    Str1 = (wchar_t *)(unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
    if ( (Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState & 0x10) == 0 )
    {
      v59 = __PAIR64__(HIDWORD(Str1), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u);
      wil_details_FeatureReporting_ReportUsageToService(
        Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor,
        __PAIR64__(HIDWORD(Str1), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u),
        3,
        1);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
        v59,
        3,
        Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor);
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v27, v13);
    v14 = 1;
  }
  v58 = (WCHAR *)PALLOCMEM(512, 1886221383);
  if ( !v58 )
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
      v20 = v58;
      goto LABEL_17;
    }
    DestinationString.Buffer = v58;
    *(_DWORD *)&DestinationString.Length = 33423360;
    RtlAppendUnicodeToString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server\\Video\\");
    v39 = L"vgastub";
    if ( *(_QWORD *)(v73 + 2976) )
      v39 = *(const WCHAR **)(v73 + 2976);
    RtlAppendUnicodeToString(&DestinationString, v39);
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
    v69 = 0;
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
    if ( v71 )
    {
      v40 = v9[2];
      v41 = a5 - 1;
      Str1 = v71;
      Handle = 0;
      if ( a5 - 1 > 0x1F )
        v41 = 31;
      v42 = (char *)v9 + v40;
      v43 = -1;
      do
        ++v43;
      while ( *(_WORD *)&v42[2 * v43] );
      *(_QWORD *)v68 = (int)v43;
      Length = 2LL * (int)v43 + 12;
      if ( Length <= 0x66 )
        LODWORD(Length) = 102;
      v45 = (unsigned __int16 *)PALLOCMEM((unsigned int)Length, 1936876615);
      v72 = v45;
      v46 = v45;
      if ( v45 )
      {
        Size = (int)Length;
        memset(v45, 0, (int)Length);
        StringCchCopyW(v46, Size >> 1, (const unsigned __int16 *)((char *)v9 + v9[2]));
        for ( i = &v46[*(_QWORD *)v68 - 1]; i > v46; --i )
        {
          if ( *i == 92 )
            goto LABEL_76;
        }
        if ( *i != 92 )
          goto LABEL_90;
LABEL_76:
        StringCchCopyW(i + 1, v47 - *(_QWORD *)v68, L"Video");
        RtlInitUnicodeString(&DestinationString, v46);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          v68[0] = 0;
          RtlInitUnicodeString(&DestinationString, L"Service");
          memset(v46, 0, Size);
          if ( ZwQueryValueKey(Handle, &DestinationString, KeyValueFullInformation, v46, Length, v68) >= 0 )
          {
            v49 = (unsigned __int16 *)((char *)v46 + *((unsigned int *)v46 + 2));
            v50 = *v49;
            if ( *v49 )
            {
              do
              {
                *v49++ = toupper(v50);
                v50 = *v49;
              }
              while ( *v49 );
              v46 = v72;
            }
            v51 = v41;
            v52 = (unsigned __int16 *)((char *)v46 + *((unsigned int *)v46 + 2));
            LODWORD(Size) = v41;
            if ( v41 )
            {
              v53 = Str1;
              v54 = Str1;
              do
              {
                if ( !*v52 )
                  break;
                *v53 = *v52;
                --v41;
                Str1 = ++v53;
                if ( v41 == v51 - 3 )
                {
                  if ( !wcsnicmp(v54, L"VGA", 3u) )
                    break;
                  v51 = Size;
                }
                ++v52;
              }
              while ( v41 );
              v46 = v72;
              v23 = -1;
            }
          }
          ZwClose(Handle);
        }
LABEL_90:
        GreDeleteFastMutex(v46);
      }
      v18 = (WCHAR *)(v9 + 128);
      v19 = v69;
      *Str1 = 0;
    }
    if ( v74 )
    {
      do
        ++v23;
      while ( v22[v23] );
      StringCchPrintfW(
        &v22[v23],
        512 - ((unsigned int)(((char *)v22 - (char *)v9) >> 1) >> 1) - (unsigned int)v23,
        L"\\Mon%08X",
        *v74);
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
      ObjectAttributes.SecurityDescriptor = *(PVOID *)(v73 + 1824);
      ObjectAttributes.SecurityQualityOfService = 0;
      v15 = ZwCreateKey(&v61, 0, &ObjectAttributes, 0, 0, v19, 0);
      if ( v15 >= 0 )
      {
        while ( 1 )
        {
          v55 = wcschr(v22 + 1, 0x5Cu);
          v56 = v55;
          if ( v55 )
            *v55 = 0;
          RtlAppendUnicodeToString(&Destination, v22);
          if ( v61 )
            ZwClose(v61);
          v15 = ZwCreateKey(&v61, 0, &ObjectAttributes, 0, 0, v19, 0);
          if ( v15 < 0 )
            break;
          if ( !v56 )
            goto LABEL_36;
          *v56 = 92;
          v22 = v56;
        }
      }
      v61 = 0;
    }
    else
    {
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      RtlAppendUnicodeToString(&Destination, v22);
      v15 = ZwOpenKey(&v61, 0x20019u, &ObjectAttributes);
      if ( v15 >= 0 )
      {
LABEL_36:
        v20 = v58;
        goto LABEL_17;
      }
      v15 = -1073741438;
    }
    goto LABEL_106;
  }
  if ( !a4 )
    goto LABEL_36;
  v24 = StringCchCopyNW(a4, a5, v17, 0x7Fu);
  if ( (int)(v24 + 0x80000000) < 0 )
    goto LABEL_36;
  v20 = v58;
  if ( v24 != -2147024774 )
    goto LABEL_16;
LABEL_17:
  if ( v75 )
    *v75 = v15;
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v20 )
    GreDeleteFastMutex(v20);
  if ( v9 )
    GreDeleteFastMutex(v9);
  WdLogSingleEntry1(5, v15);
  result = v61;
  WdLogGlobalForLineNumber = 2647;
  return result;
}

```

## disassembly

```asm
0x1400abe40  push    rbp
0x1400abe42  push    rbx
0x1400abe43  push    rsi
0x1400abe44  push    rdi
0x1400abe45  push    r12
0x1400abe47  push    r13
0x1400abe49  push    r14
0x1400abe4b  push    r15
0x1400abe4d  lea     rbp, [rsp-158h]
0x1400abe55  sub     rsp, 258h
0x1400abe5c  mov     rax, cs:__security_cookie
0x1400abe63  xor     rax, rsp
0x1400abe66  mov     [rbp+190h+var_50], rax
0x1400abe6d  mov     rax, [rbp+190h+arg_28]
0x1400abe74  xorps   xmm1, xmm1
0x1400abe77  movsxd  rbx, edx
0x1400abe7a  mov     rsi, r8
0x1400abe7d  mov     [rbp+190h+var_190], rax
0x1400abe81  mov     rdi, rcx
0x1400abe84  xor     eax, eax
0x1400abe86  mov     [rbp+190h+var_198], r8
0x1400abe8a  xorps   xmm0, xmm0
0x1400abe8d  mov     [rsp+290h+var_230], rax
0x1400abe92  xor     edx, edx; Val
0x1400abe94  mov     [rsp+290h+KeyHandle], rax
0x1400abe99  mov     r8d, 130h; Size
0x1400abe9f  mov     [rbp+190h+var_1D0], eax
0x1400abea2  lea     rcx, [rbp+190h+var_180]; void *
0x1400abea6  mov     [rbp+190h+var_1B0], r9
0x1400abeaa  mov     r14d, eax
0x1400abead  mov     [rsp+290h+var_250], ebx
0x1400abeb1  mov     r15, r9
0x1400abeb4  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x1400abeb9  movups  xmmword ptr [rbp+190h+ObjectAttributes.Length], xmm1
0x1400abebd  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm1
0x1400abec1  movups  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400abec5  call    memset
0x1400abeca  call    cs:__imp_W32GetSessionState
0x1400abed1  nop     dword ptr [rax+rax+00h]
0x1400abed6  mov     r13, [rax+58h]
0x1400abeda  mov     [rbp+190h+var_1A0], r13
0x1400abede  mov     r8, rbx
0x1400abee1  lea     ecx, [r14+5]
0x1400abee5  mov     r9, rsi
0x1400abee8  mov     rdx, rdi
0x1400abeeb  call    cs:__imp_WdLogSingleEntry3
0x1400abef2  nop     dword ptr [rax+rax+00h]
0x1400abef7  mov     r12d, dword ptr [rbp+190h+arg_20]
0x1400abefe  xor     ecx, ecx
0x1400abf00  mov     cs:WdLogGlobalForLineNumber, 81Eh
0x1400abf0a  test    r15, r15
0x1400abf0d  jnz     loc_1400AC06E
0x1400abf13  mov     esi, ecx
0x1400abf15  cmp     [r13+0BB8h], ecx
0x1400abf1c  jnz     loc_1400AC27D
0x1400abf22  mov     eax, [rdi+0A0h]
0x1400abf28  mov     r13d, 1
0x1400abf2e  test    al, 8
0x1400abf30  jnz     loc_1400AC2A3
0x1400abf36  mov     r13d, 200h
0x1400abf3c  mov     edx, 706D7447h
0x1400abf41  mov     ecx, r13d
0x1400abf44  call    PALLOCMEM
0x1400abf49  mov     [rsp+290h+var_248], rax
0x1400abf4e  mov     rcx, rax
0x1400abf51  test    rax, rax
0x1400abf54  jz      loc_1400AC103
0x1400abf5a  test    dword ptr [rdi+0A0h], 4000000h
0x1400abf64  jnz     loc_1400AC3AC
0x1400abf6a  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Hardware\\DeviceMa"...
0x1400abf71  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1400abf76  call    cs:__imp_RtlInitUnicodeString
0x1400abf7d  nop     dword ptr [rax+rax+00h]
0x1400abf82  lea     rax, [rsp+290h+DestinationString]
0x1400abf87  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400abf8e  xorps   xmm0, xmm0
0x1400abf91  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x1400abf95  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x1400abf99  mov     [rbp+190h+ObjectAttributes.RootDirectory], r14
0x1400abf9d  mov     edx, 20019h; DesiredAccess
0x1400abfa2  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x1400abfa9  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1400abfae  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400abfb3  call    cs:__imp_ZwOpenKey
0x1400abfba  nop     dword ptr [rax+rax+00h]
0x1400abfbf  mov     ebx, eax
0x1400abfc1  test    eax, eax
0x1400abfc3  js      loc_1400AC842
0x1400abfc9  mov     edx, 706D7447h
0x1400abfce  mov     ecx, 400h
0x1400abfd3  call    PALLOCMEM
0x1400abfd8  mov     r14, rax
0x1400abfdb  test    rax, rax
0x1400abfde  jz      loc_1400AC41D
0x1400abfe4  test    dword ptr [rdi+0A0h], 4000000h
0x1400abfee  jnz     loc_1400AC42A
0x1400abff4  mov     rdx, rdi; SourceString
0x1400abff7  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1400abffc  call    cs:__imp_RtlInitUnicodeString
0x1400ac003  nop     dword ptr [rax+rax+00h]
0x1400ac008  mov     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1400ac00d  lea     rax, [rbp+190h+var_1D0]
0x1400ac011  mov     [rsp+290h+ResultLength], rax; ResultLength
0x1400ac016  lea     rdx, [rsp+290h+DestinationString]; ValueName
0x1400ac01b  mov     r9, r14; KeyValueInformation
0x1400ac01e  mov     [rsp+290h+Length], r13d; Length
0x1400ac023  mov     r8d, 1; KeyValueInformationClass
0x1400ac029  call    cs:__imp_ZwQueryValueKey
0x1400ac030  nop     dword ptr [rax+rax+00h]
0x1400ac035  xor     r13d, r13d
0x1400ac038  mov     ebx, eax
0x1400ac03a  test    eax, eax
0x1400ac03c  js      loc_1400AC818
0x1400ac042  mov     esi, [r14+8]
0x1400ac046  xorps   xmm0, xmm0
0x1400ac049  add     rsi, r14
0x1400ac04c  cmp     [rsp+290h+var_250], 3
0x1400ac051  movups  xmmword ptr [rbp+190h+Destination.Length], xmm0
0x1400ac055  jz      loc_1400AC20A
0x1400ac05b  lea     rbx, [r14+200h]
0x1400ac062  mov     [rbp+190h+var_1C0], r13d
0x1400ac066  mov     r15d, r13d
0x1400ac069  jmp     loc_1400AC122
0x1400ac06e  test    r12d, r12d
0x1400ac071  jnz     loc_1400ABF13
0x1400ac077  xor     r13d, r13d
0x1400ac07a  mov     edi, r13d
0x1400ac07d  mov     ebx, 0C000000Dh
0x1400ac082  mov     rax, [rbp+190h+var_190]
0x1400ac086  test    rax, rax
0x1400ac089  jnz     loc_1400AC847
0x1400ac08f  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x1400ac094  test    rcx, rcx
0x1400ac097  jz      short loc_1400AC0AA
0x1400ac099  call    cs:__imp_ZwClose
0x1400ac0a0  nop     dword ptr [rax+rax+00h]
0x1400ac0a5  mov     [rsp+290h+KeyHandle], r13
0x1400ac0aa  test    rdi, rdi
0x1400ac0ad  jnz     loc_1400AC84E
0x1400ac0b3  test    r14, r14
0x1400ac0b6  jnz     loc_1400AC85B
0x1400ac0bc  movsxd  rdx, ebx
0x1400ac0bf  mov     ecx, 5
0x1400ac0c4  call    cs:__imp_WdLogSingleEntry1
0x1400ac0cb  nop     dword ptr [rax+rax+00h]
0x1400ac0d0  mov     rax, [rsp+290h+var_230]
0x1400ac0d5  mov     cs:WdLogGlobalForLineNumber, 0A57h
0x1400ac0df  mov     rcx, [rbp+190h+var_50]
0x1400ac0e6  xor     rcx, rsp; StackCookie
0x1400ac0e9  call    __security_check_cookie
0x1400ac0ee  add     rsp, 258h
0x1400ac0f5  pop     r15
0x1400ac0f7  pop     r14
0x1400ac0f9  pop     r13
0x1400ac0fb  pop     r12
0x1400ac0fd  pop     rdi
0x1400ac0fe  pop     rsi
0x1400ac0ff  pop     rbx
0x1400ac100  pop     rbp
0x1400ac101  retn
0x1400ac103  mov     ebx, 0C000009Ah
0x1400ac108  mov     rdi, rax
0x1400ac10b  xor     r13d, r13d
0x1400ac10e  jmp     loc_1400AC082
0x1400ac113  movzx   ecx, ax; C
0x1400ac116  call    toupper
0x1400ac11b  mov     [rsi], ax
0x1400ac11e  lea     rsi, [rsi+2]
0x1400ac122  movzx   eax, word ptr [rsi]
0x1400ac125  test    ax, ax
0x1400ac128  jnz     short loc_1400AC113
0x1400ac12a  mov     ecx, [r14+8]
0x1400ac12e  lea     rdx, aControl; "\\CONTROL\\"
0x1400ac135  add     rcx, r14; Str
0x1400ac138  call    wcsstr
0x1400ac13d  mov     rsi, rax
0x1400ac140  test    rax, rax
0x1400ac143  jz      loc_1400AC43E
0x1400ac149  mov     rax, [rbp+190h+var_1B0]
0x1400ac14d  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400ac151  xor     edx, edx
0x1400ac153  test    rax, rax
0x1400ac156  jnz     loc_1400AC459
0x1400ac15c  mov     r9, [rbp+190h+var_198]
0x1400ac160  test    r9, r9
0x1400ac163  jnz     loc_1400AC6B6
0x1400ac169  lea     rdx, Src; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400ac170  mov     [rbp+190h+Destination.Buffer], rbx
0x1400ac174  lea     rcx, [rbp+190h+Destination]; Destination
0x1400ac178  mov     dword ptr [rbp+190h+Destination.Length], 1FE0000h
0x1400ac17f  xor     r13d, r13d
0x1400ac182  call    cs:__imp_RtlAppendUnicodeToString
0x1400ac189  nop     dword ptr [rax+rax+00h]
0x1400ac18e  mov     ebx, [rsp+290h+var_250]
0x1400ac192  lea     eax, [rbx-1]
0x1400ac195  cmp     eax, 1
0x1400ac198  jbe     loc_1400AC6ED
0x1400ac19e  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400ac1a5  lea     rax, [rbp+190h+Destination]
0x1400ac1a9  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x1400ac1ad  mov     [rbp+190h+ObjectAttributes.RootDirectory], r13
0x1400ac1b1  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x1400ac1b8  cmp     ebx, 2
0x1400ac1bb  jz      loc_1400AC742
0x1400ac1c1  xorps   xmm0, xmm0
0x1400ac1c4  lea     rcx, [rbp+190h+Destination]; Destination
0x1400ac1c8  mov     rdx, rsi; Source
0x1400ac1cb  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ac1d0  call    cs:__imp_RtlAppendUnicodeToString
0x1400ac1d7  nop     dword ptr [rax+rax+00h]
0x1400ac1dc  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x1400ac1e0  mov     edx, 20019h; DesiredAccess
0x1400ac1e5  lea     rcx, [rsp+290h+var_230]; KeyHandle
0x1400ac1ea  call    cs:__imp_ZwOpenKey
0x1400ac1f1  nop     dword ptr [rax+rax+00h]
0x1400ac1f6  mov     ebx, eax
0x1400ac1f8  test    eax, eax
0x1400ac1fa  js      loc_1400AC83B
0x1400ac200  mov     rdi, [rsp+290h+var_248]
0x1400ac205  jmp     loc_1400AC082
0x1400ac20a  test    r15, r15
0x1400ac20d  jz      short loc_1400AC200
0x1400ac20f  mov     rdx, r12; unsigned __int64
0x1400ac212  mov     r9d, 7Fh; unsigned __int64
0x1400ac218  mov     r8, rsi; unsigned __int16 *
0x1400ac21b  mov     rcx, r15; unsigned __int16 *
0x1400ac21e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400ac223  mov     edx, 80000000h
0x1400ac228  lea     ecx, [rax+rdx]
0x1400ac22b  test    edx, ecx
0x1400ac22d  jnz     short loc_1400AC200
0x1400ac22f  mov     rdi, [rsp+290h+var_248]
0x1400ac234  cmp     eax, 8007007Ah
0x1400ac239  jz      loc_1400AC082
0x1400ac23f  jmp     loc_1400AC07D
0x1400ac244  call    cs:__imp_W32GetUserGdiSessionState
0x1400ac24b  nop     dword ptr [rax+rax+00h]
0x1400ac250  mov     rbx, [rax+28h]
0x1400ac254  call    cs:__imp_PsGetCurrentProcess
0x1400ac25b  nop     dword ptr [rax+rax+00h]
0x1400ac260  cmp     rax, rbx
0x1400ac263  jz      loc_1400AC35F
0x1400ac269  call    UserIsCurrentProcessDwm
0x1400ac26e  xor     ecx, ecx
0x1400ac270  test    eax, eax
0x1400ac272  jz      short loc_1400AC2C8
0x1400ac274  mov     ebx, [rsp+290h+var_250]
0x1400ac278  jmp     loc_1400ABF22
0x1400ac27d  call    cs:__imp_W32GetSessionState
0x1400ac284  nop     dword ptr [rax+rax+00h]
0x1400ac289  mov     rbx, [rax+58h]
0x1400ac28d  call    UserIsRemoteAndNotDisconnectConnection
0x1400ac292  xor     ecx, ecx
0x1400ac294  test    eax, eax
0x1400ac296  jz      short loc_1400AC274
0x1400ac298  cmp     [rbx+0BC8h], rcx
0x1400ac29f  jz      short loc_1400AC274
0x1400ac2a1  jmp     short loc_1400AC244
0x1400ac2a3  mov     [rsp+290h+Str1], rcx
0x1400ac2a8  mov     ecx, cs:Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState
0x1400ac2ae  mov     dword ptr [rsp+290h+Str1], ecx
0x1400ac2b2  test    cl, 10h
0x1400ac2b5  jz      loc_1400AC366
0x1400ac2bb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400ac2c0  mov     esi, r13d
0x1400ac2c3  jmp     loc_1400ABF36
0x1400ac2c8  test    dword ptr [rdi+0A0h], 4000000h
0x1400ac2d2  jz      short loc_1400AC274
0x1400ac2d4  mov     ecx, 2
0x1400ac2d9  lea     rax, [rbp+190h+var_180]
0x1400ac2dd  lea     edx, [rcx+7Eh]
0x1400ac2e0  movups  xmm0, xmmword ptr [rdi]
0x1400ac2e3  movups  xmm1, xmmword ptr [rdi+10h]
0x1400ac2e7  movups  xmmword ptr [rax], xmm0
0x1400ac2ea  movups  xmm0, xmmword ptr [rdi+20h]
0x1400ac2ee  movups  xmmword ptr [rax+10h], xmm1
0x1400ac2f2  movups  xmm1, xmmword ptr [rdi+30h]
0x1400ac2f6  movups  xmmword ptr [rax+20h], xmm0
0x1400ac2fa  movups  xmm0, xmmword ptr [rdi+40h]
0x1400ac2fe  movups  xmmword ptr [rax+30h], xmm1
0x1400ac302  movups  xmm1, xmmword ptr [rdi+50h]
0x1400ac306  movups  xmmword ptr [rax+40h], xmm0
0x1400ac30a  movups  xmm0, xmmword ptr [rdi+60h]
0x1400ac30e  movups  xmmword ptr [rax+50h], xmm1
0x1400ac312  movups  xmm1, xmmword ptr [rdi+70h]
0x1400ac316  add     rdi, rdx
0x1400ac319  movups  xmmword ptr [rax+60h], xmm0
0x1400ac31d  movups  xmmword ptr [rax+70h], xmm1
0x1400ac321  add     rax, rdx
0x1400ac324  sub     rcx, 1
0x1400ac328  jnz     short loc_1400AC2E0
0x1400ac32a  movups  xmm0, xmmword ptr [rdi]
0x1400ac32d  lea     edx, [rcx+20h]; unsigned __int64
0x1400ac330  movups  xmm1, xmmword ptr [rdi+10h]
0x1400ac334  lea     r8, [r13+0BD0h]; unsigned __int16 *
0x1400ac33b  movups  xmmword ptr [rax], xmm0
0x1400ac33e  lea     rcx, [rbp+190h+var_180]; unsigned __int16 *
0x1400ac342  movups  xmm0, xmmword ptr [rdi+20h]
0x1400ac346  lea     rdi, [rbp+190h+var_180]
0x1400ac34a  movups  xmmword ptr [rax+10h], xmm1
  ... truncated ...
```
