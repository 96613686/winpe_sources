# SampRegistryLookupIdByKey

- ea: `0x180013ee0`
- end: `0x180014a92`
- name: `SampRegistryLookupIdByKey`
- size: `2994`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001760`
- `0x180002b40`
- `0x180060eec`

## callees

- `0x180002360`
- `0x180004fa0`
- `0x180006170`
- `0x1800066f0`
- `0x180013ee0`
- `0x1800153e0`
- `0x18001b4e0`
- `0x1800213d0`
- `0x180024ee8`
- `0x180027e24`
- `0x18002cd80`
- `0x1800372ac`
- `0x180053e84`
- `0x180059a74`
- `0x1800bb77c`
- `0x1800bb788`
- `0x1800bc010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800142f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800142f5`
- `ntdll!RtlpNtEnumerateSubKey` at `0x1800141ee`
- `ntdll!RtlpNtEnumerateSubKey` at `0x18001424c`
- `ntdll!RtlpNtEnumerateSubKey` at `0x1800141ee`
- `ntdll!RtlpNtEnumerateSubKey` at `0x18001424c`
- `ntdll!RtlEqualUnicodeString` at `0x180014758`
- `ntdll!RtlEqualUnicodeString` at `0x180014758`
- `ntdll!RtlAllocateHeap` at `0x180014273`
- `ntdll!RtlAllocateHeap` at `0x180014273`
- `ntdll!RtlValidSid` at `0x180013fee`
- `ntdll!RtlValidSid` at `0x180013fee`
- `ntdll!RtlEqualSid` at `0x180014808`
- `ntdll!RtlEqualSid` at `0x180014808`
- `ntdll!NtClose` at `0x180014a3f`
- `ntdll!NtClose` at `0x180014a3f`
- `ntdll!RtlpNtOpenKey` at `0x18001419b`
- `ntdll!RtlpNtOpenKey` at `0x18001419b`
- `ntdll!RtlInitUnicodeString` at `0x180013f7b`
- `ntdll!RtlInitUnicodeString` at `0x18001404c`
- `ntdll!RtlInitUnicodeString` at `0x1800147cd`
- `ntdll!RtlInitUnicodeString` at `0x180013f7b`
- `ntdll!RtlInitUnicodeString` at `0x18001404c`
- `ntdll!RtlInitUnicodeString` at `0x1800147cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800141c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014225`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800141c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014819`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001484c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800149dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800149f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014819`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001484c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800149dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800149f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a2c`

## pseudocode

```c
__int64 __fastcall SampRegistryLookupIdByKey(
        __int64 a1,
        __int16 a2,
        PSID *a3,
        unsigned int *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  _BYTE *v8; // rdi
  PUNICODE_STRING v9; // rcx
  __int64 v10; // rdx
  __int16 v11; // r14
  int v12; // esi
  int v13; // r14d
  wchar_t *v15; // rsi
  unsigned int v16; // r8d
  int v17; // edx
  USHORT Length; // cx
  int ExtendedAttribute; // ebx
  WCHAR *v20; // rax
  ULONG v21; // ebx
  NTSTATUS v22; // eax
  SIZE_T v23; // rdx
  WCHAR *v24; // rax
  PVOID Heap; // rax
  _BYTE *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // r12d
  unsigned int AccountContext2; // eax
  PUNICODE_STRING v30; // r10
  __int64 v31; // rax
  bool v32; // zf
  char *v33; // r15
  __int64 v34; // rsi
  int *v35; // r14
  __int64 (__fastcall *v36)(_BYTE *, unsigned int *, _QWORD); // r13
  int v37; // eax
  __int64 v38; // r12
  __int64 v39; // rbx
  unsigned int *v40; // r8
  int v41; // edi
  int v42; // eax
  _BYTE *v43; // r15
  __int64 v44; // rdx
  char v45; // di
  int *v46; // r14
  _BYTE *v47; // rsi
  unsigned int v48; // eax
  BOOLEAN v49; // al
  PSID v50; // rdi
  PVOID HandleId; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING SubKeyName; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v53; // [rsp+88h] [rbp-78h]
  unsigned int *v54; // [rsp+90h] [rbp-70h]
  _DWORD *v55; // [rsp+98h] [rbp-68h]
  HLOCAL hMem[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v57; // [rsp+B0h] [rbp-50h] BYREF
  ULONG v58; // [rsp+B4h] [rbp-4Ch]
  UNICODE_STRING String1; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE KeyHandle; // [rsp+C8h] [rbp-38h] BYREF
  int v61; // [rsp+D0h] [rbp-30h]
  int v62; // [rsp+D4h] [rbp-2Ch]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL v64[2]; // [rsp+E8h] [rbp-18h] BYREF
  ULONG Unused[2]; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD *v66; // [rsp+100h] [rbp+0h]
  PSID Sid2[2]; // [rsp+108h] [rbp+8h] BYREF
  PSID *v68; // [rsp+118h] [rbp+18h]
  struct _GUID Buf2; // [rsp+120h] [rbp+20h] BYREF
  struct _UNICODE_STRING v70; // [rsp+130h] [rbp+30h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+140h] [rbp+40h] BYREF
  __int128 Buf1; // [rsp+170h] [rbp+70h] BYREF
  __int128 v73; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v74[24]; // [rsp+190h] [rbp+90h] BYREF

  v55 = a5;
  v66 = a6;
  v54 = a4;
  v68 = a3;
  KeyHandle = 0;
  String1 = 0;
  *(_QWORD *)Unused = 0;
  v8 = 0;
  v70 = 0;
  HandleId = 0;
  DestinationString = 0;
  v73 = 0;
  Buf2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_OWORD *)Sid2 = 0;
  *(_OWORD *)v64 = 0;
  SubKeyName = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  Buf1 = 0;
  if ( !SampValidateRpcUnicodeString((struct _RPC_UNICODE_STRING *)a3) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 117;
LABEL_12:
      WPP_SF_Dd(v9[3].Buffer, v10, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, 3221225485LL, -1073741811);
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  v11 = a2;
  v12 = a2 & 0x8000;
  v13 = v11 & 0x4000;
  v62 = v12;
  v61 = v13;
  if ( v13 )
  {
    if ( !v12 )
      goto LABEL_14;
  }
  else if ( !v12 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 118;
      goto LABEL_12;
    }
    return 3221225485LL;
  }
  if ( !RtlValidSid(a3[1]) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 119;
      goto LABEL_12;
    }
    return 3221225485LL;
  }
LABEL_14:
  v15 = 0;
  if ( v13 )
  {
    RtlInitUnicodeString(&v70, L"\\");
    v16 = *(unsigned __int16 *)a3;
    v17 = 0;
    *(_OWORD *)hMem = *(_OWORD *)a3;
    String1 = *(UNICODE_STRING *)hMem;
    while ( 1 )
    {
      if ( v17 >= v16 )
        goto LABEL_22;
      if ( *v70.Buffer == *((_WORD *)a3[1] + ((unsigned __int64)(unsigned int)v17 >> 1)) )
        break;
      v17 += 2;
    }
    if ( v17 < 0 )
    {
LABEL_22:
      LOWORD(v17) = 0;
      String1.MaximumLength = String1.Length;
      Length = String1.Length;
      LODWORD(hMem[0]) = 0;
      goto LABEL_23;
    }
    LOWORD(hMem[0]) = v17;
    WORD1(hMem[0]) = v17;
    String1.Buffer += (int)(((unsigned __int64)v17 >> 1) + 1);
    Length = -2 - v17 + String1.Length;
    String1.Length = Length;
    String1.MaximumLength = Length;
    if ( (_WORD)v17 )
      goto LABEL_24;
LABEL_23:
    hMem[1] = 0;
LABEL_24:
    if ( !Length )
      String1.Buffer = 0;
    if ( (_WORD)v17
      && (unsigned int)SampLookupInternetProviderGUIDByName((struct _UNICODE_STRING *)hMem, &Buf2) == -1073741275 )
    {
      ExtendedAttribute = -1073741772;
      *v54 = 0;
      *v55 = 8;
      goto LABEL_122;
    }
  }
  ExtendedAttribute = SampBuildAccountKeyName(4, v64, 0);
  if ( ExtendedAttribute < 0
    || (LOWORD(v64[0]) -= SampBackSlash.Length + SampNameDomainUsersNames.Length,
        ObjectAttributes.RootDirectory = SampKey,
        ObjectAttributes.Length = 48,
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v64,
        ObjectAttributes.Attributes = 64,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        ExtendedAttribute = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0),
        ExtendedAttribute < 0) )
  {
LABEL_119:
    *v54 = 0;
    *v55 = 8;
    if ( ExtendedAttribute >= 0 || ExtendedAttribute == -1073741724 )
      ExtendedAttribute = -1073741772;
    goto LABEL_122;
  }
  *(_DWORD *)&SubKeyName.Length = 0x200000;
  v20 = (WCHAR *)LocalAlloc(0x40u, 0x20u);
  SubKeyName.Buffer = v20;
  if ( v20 )
  {
    v21 = 0;
    *v20 = 0;
    while ( 1 )
    {
      v58 = v21;
      v22 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, v21, (ULONG)Unused);
      if ( v22 == -2147483643 )
      {
        if ( SubKeyName.Buffer )
        {
          LocalFree(SubKeyName.Buffer);
          SubKeyName.Buffer = 0;
        }
        SubKeyName.MaximumLength = SubKeyName.Length;
        v23 = SubKeyName.Length;
        SubKeyName.Length = 0;
        v24 = (WCHAR *)LocalAlloc(0x40u, v23);
        SubKeyName.Buffer = v24;
        if ( !v24 )
        {
          ExtendedAttribute = -1073741670;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              59,
              WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
              3221225626LL,
              -1073741670);
          v15 = 0;
          goto LABEL_116;
        }
        *v24 = 0;
        v22 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, v21, (ULONG)Unused);
      }
      if ( v22 < 0 )
      {
        ExtendedAttribute = 0;
        v15 = 0;
        if ( v22 != -2147483622 )
          ExtendedAttribute = v22;
        goto LABEL_119;
      }
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, SubKeyName.Length + 2LL);
      hMem[0] = Heap;
      v15 = (wchar_t *)Heap;
      if ( !Heap )
      {
        ExtendedAttribute = -1073741670;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          goto LABEL_116;
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          31,
          WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids,
          3221225626LL,
          -1073741670);
        *v54 = 0;
        *v55 = 8;
        goto LABEL_122;
      }
      v26 = Heap;
      v27 = SubKeyName.Length + 2LL;
      do
      {
        *v26++ = 0;
        --v27;
      }
      while ( v27 );
      memcpy_0(Heap, SubKeyName.Buffer, SubKeyName.Length);
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 32, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids, 0, 0);
      v53 = wcstoul(v15, 0, 16);
      v28 = v53;
      AccountContext2 = SampCreateAccountContext2(0, 4u, v53, 0, 0, 1, 1u, 0, 0, 1, 0, 0, 0, (__int64 *)&HandleId);
      ExtendedAttribute = AccountContext2;
      v30 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          123,
          WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
          AccountContext2,
          AccountContext2);
        v30 = WPP_GLOBAL_Control;
      }
      v8 = HandleId;
      if ( ExtendedAttribute < 0 )
        goto LABEL_119;
      v31 = *((_DWORD *)HandleId + 48) & 2;
      v74[0] = 27;
      v74[1] = 25;
      v32 = (*((_BYTE *)HandleId + 20) & 0x20) == 0;
      v33 = (char *)HandleId + 864;
      LODWORD(v34) = 3;
      v74[2] = 29;
      v57 = 3;
      v35 = (int *)((char *)HandleId + 16);
      v36 = (__int64 (__fastcall *)(_BYTE *, unsigned int *, _QWORD))*(&funcs_180001EF0 + 2 * v31);
      if ( v32 )
      {
        v37 = SampCheckExtendedAttributesForReadAccess((__int64)HandleId + 864, *v35, 0, (__int64)v74, &v57);
        v30 = WPP_GLOBAL_Control;
        ExtendedAttribute = v37;
        if ( v37 < 0 )
          goto LABEL_67;
        LODWORD(v34) = v57;
      }
      v38 = *v35;
      v39 = 0;
      while ( (unsigned int)v39 < (unsigned int)v34 )
      {
        v40 = &v74[v39];
        if ( (v33[24 * (*v40 - dword_1800BD00C[4 * v38])] & 1) != 0 )
        {
          v34 = (unsigned int)(v34 - 1);
          v39 = (unsigned int)v39;
          *v40 = v74[v34];
        }
        else
        {
          v41 = *(_DWORD *)(*((_QWORD *)&SampObjectExtendedAttributesProperties + 2 * *v35)
                          + 32LL * (v74[v39] - dword_1800BD00C[4 * v38])
                          + 4)
              & (((v8[192] & 2) != 0) + 1);
          if ( (*(_DWORD *)(&v30[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_d(v30[3].Buffer, 40, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v41 != 0);
            v30 = WPP_GLOBAL_Control;
          }
          if ( !v41 )
          {
            if ( (*(_DWORD *)(&v30[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              WPP_SF_Dd(v30[3].Buffer, 82, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221226147LL, -1073741149);
              v30 = WPP_GLOBAL_Control;
            }
            v8 = HandleId;
            ExtendedAttribute = -1073741149;
            goto LABEL_66;
          }
          v8 = HandleId;
          v39 = (unsigned int)(v39 + 1);
        }
      }
      if ( (*(_DWORD *)(&v30[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(v30[3].Buffer, 83, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 0, 0);
        v30 = WPP_GLOBAL_Control;
      }
      if ( (_DWORD)v34 )
      {
        v42 = v36(v8, v74, (unsigned int)v34);
        v30 = WPP_GLOBAL_Control;
        ExtendedAttribute = v42;
      }
      else
      {
        ExtendedAttribute = 0;
      }
LABEL_66:
      v28 = v53;
LABEL_67:
      if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 5u )
      {
        WPP_SF_Dd(v30[3].Buffer, 86, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3, ExtendedAttribute);
        v30 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v30[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(
          v30[3].Buffer,
          87,
          WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
          (unsigned int)ExtendedAttribute,
          ExtendedAttribute);
        v30 = WPP_GLOBAL_Control;
      }
      if ( ExtendedAttribute < 0 )
        goto LABEL_118;
      if ( v61 )
      {
        v43 = HandleId;
        v44 = 4LL * *v35;
        v45 = 0;
        v46 = (int *)(*(char **)((char *)&SampObjectExtendedAttributesProperties + v44 * 4)
                    + 32 * (unsigned int)(25 - dword_1800BD00C[v44]));
        v47 = (char *)HandleId + 24 * (unsigned int)(25 - dword_1800BD00C[v44]) + 864;
        if ( (*((_BYTE *)HandleId + 20) & 0x20) != 0 )
        {
          v45 = *v47 >> 2;
          *v47 |= 4u;
          v30 = WPP_GLOBAL_Control;
        }
        if ( (*v47 & 4) != 0 )
        {
          v48 = ((__int64 (__fastcall *)(_BYTE *, struct _UNICODE_STRING *))qword_1800BD430[2 * *v46])(
                  v47 + 8,
                  &DestinationString);
          ExtendedAttribute = v48;
          v30 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 66, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v48, v48);
            v30 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          if ( (*(_DWORD *)(&v30[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(v30[3].Buffer, 65, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221225506LL, -1073741790);
            v30 = WPP_GLOBAL_Control;
          }
          ExtendedAttribute = -1073741790;
        }
        if ( (v43[20] & 0x20) != 0 )
        {
          *v47 ^= (*v47 ^ (4 * v45)) & 4;
          v30 = WPP_GLOBAL_Control;
        }
        if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
        {
          WPP_SF_ZD(
            v30[3].Buffer,
            67,
            (unsigned int)WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
            (_DWORD)v46 + 8,
            ExtendedAttribute);
          v30 = WPP_GLOBAL_Control;
        }
        if ( (*(_DWORD *)(&v30[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            v30[3].Buffer,
            68,
            WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
            (unsigned int)ExtendedAttribute,
            ExtendedAttribute);
        if ( ExtendedAttribute < 0 )
        {
          v8 = HandleId;
LABEL_118:
          v15 = (wchar_t *)hMem[0];
          goto LABEL_119;
        }
        v49 = RtlEqualUnicodeString(&String1, &DestinationString, 1u);
        v8 = HandleId;
        if ( v49 )
        {
          ExtendedAttribute = SampGetExtendedAttribute((__int64)HandleId, 27, (__int64)&v73);
          if ( ExtendedAttribute < 0 )
            goto LABEL_118;
          if ( !memcmp_0(&Buf1, &Buf2, 0x10u) || !memcmp_0(&v73, &Buf2, 0x10u) )
          {
            v15 = (wchar_t *)hMem[0];
            --*v66;
            *v54 = v28;
            *v55 = 1;
            goto LABEL_122;
          }
        }
        SampFreeUnicodeString(&DestinationString);
        RtlInitUnicodeString(&DestinationString, 0);
      }
      if ( v62 )
      {
        ExtendedAttribute = SampGetExtendedAttribute((__int64)v8, 29, (__int64)Sid2);
        if ( ExtendedAttribute < 0 )
          goto LABEL_118;
        v50 = Sid2[1];
        if ( Sid2[1] )
        {
          if ( RtlEqualSid(v68[1], Sid2[1]) )
          {
            v8 = HandleId;
            v15 = (wchar_t *)hMem[0];
            --*v66;
            *v54 = v28;
            *v55 = 1;
            goto LABEL_122;
          }
          LocalFree(v50);
          *(_OWORD *)Sid2 = 0;
        }
        v8 = HandleId;
      }
      if ( v8 )
      {
        SampDeleteContext(v8);
        v8 = 0;
        HandleId = 0;
      }
      LocalFree(hMem[0]);
      v21 = v58 + 1;
    }
  }
  ExtendedAttribute = -1073741670;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      59,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      3221225626LL,
      -1073741670);
LABEL_116:
  *v54 = 0;
  *v55 = 8;
LABEL_122:
  if ( Sid2[1] )
    LocalFree(Sid2[1]);
  if ( v8 )
    SampDeleteContext(v8);
  if ( v15 )
    LocalFree(v15);
  if ( DestinationString.Buffer )
  {
    LocalFree(DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  if ( v64[1] )
  {
    LocalFree(v64[1]);
    v64[1] = 0;
  }
  if ( SubKeyName.Buffer )
  {
    LocalFree(SubKeyName.Buffer);
    SubKeyName.Buffer = 0;
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      120,
      &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
      (unsigned int)ExtendedAttribute,
      ExtendedAttribute);
  return (unsigned int)ExtendedAttribute;
}

```

## disassembly

```asm
0x180013ee0  push    rbp
0x180013ee2  push    rbx
0x180013ee3  push    rsi
0x180013ee4  push    rdi
0x180013ee5  push    r14
0x180013ee7  push    r15
0x180013ee9  lea     rbp, [rsp-108h]
0x180013ef1  sub     rsp, 208h
0x180013ef8  mov     rax, cs:__security_cookie
0x180013eff  xor     rax, rsp
0x180013f02  mov     [rbp+130h+var_40], rax
0x180013f09  mov     rax, [rbp+130h+arg_20]
0x180013f10  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x180013f14  xorps   xmm1, xmm1
0x180013f17  mov     [rbp+130h+var_198], rax
0x180013f1b  mov     rax, [rbp+130h+arg_28]
0x180013f22  xorps   xmm0, xmm0
0x180013f25  xor     r15d, r15d
0x180013f28  mov     [rbp+130h+var_130], rax
0x180013f2c  mov     rbx, r8
0x180013f2f  mov     [rbp+130h+var_1A0], r9
0x180013f33  mov     esi, edx
0x180013f35  mov     [rbp+130h+var_118], rbx
0x180013f39  xor     edx, edx; SourceString
0x180013f3b  mov     [rbp+130h+KeyHandle], r15
0x180013f3f  movups  xmmword ptr [rbp+130h+String1.Length], xmm0
0x180013f43  mov     qword ptr [rbp+130h+Unused], r15
0x180013f47  mov     edi, r15d
0x180013f4a  movups  xmmword ptr [rbp+130h+var_100.Length], xmm1
0x180013f4e  mov     [rsp+230h+HandleId], r15
0x180013f53  movups  xmmword ptr [rbp+130h+DestinationString.Length], xmm0
0x180013f57  movups  [rbp+130h+var_B0], xmm1
0x180013f5e  movups  [rbp+130h+Buf2], xmm0
0x180013f62  movups  xmmword ptr [rbp+130h+ObjectAttributes.Length], xmm1
0x180013f66  movups  xmmword ptr [rbp+130h+ObjectAttributes.ObjectName], xmm1
0x180013f6a  movups  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm1
0x180013f6e  movups  xmmword ptr [rbp+130h+Sid2], xmm0
0x180013f72  movups  xmmword ptr [rbp+130h+var_148], xmm1
0x180013f76  movups  xmmword ptr [rsp+230h+SubKeyName.Length], xmm0
0x180013f7b  call    cs:__imp_RtlInitUnicodeString
0x180013f81  xorps   xmm0, xmm0
0x180013f84  mov     rcx, rbx; struct _RPC_UNICODE_STRING *
0x180013f87  movups  [rbp+130h+Buf1], xmm0
0x180013f8b  call    ?SampValidateRpcUnicodeString@@YAEPEAU_RPC_UNICODE_STRING@@@Z; SampValidateRpcUnicodeString(_RPC_UNICODE_STRING *)
0x180013f90  test    al, al
0x180013f92  jnz     short loc_180013FAF
0x180013f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f9b  test    dword ptr [rcx+44h], 20000h
0x180013fa2  jz      loc_18001402B
0x180013fa8  mov     edx, 75h ; 'u'
0x180013fad  jmp     short loc_18001400D
0x180013faf  mov     r14d, esi
0x180013fb2  and     esi, 8000h
0x180013fb8  and     r14d, 4000h
0x180013fbf  mov     [rbp+130h+var_15C], esi
0x180013fc2  mov     [rbp+130h+var_160], r14d
0x180013fc6  test    r14d, r14d
0x180013fc9  jnz     short loc_180013FE6
0x180013fcb  test    esi, esi
0x180013fcd  jnz     short loc_180013FEA
0x180013fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fd6  test    dword ptr [rcx+44h], 20000h
0x180013fdd  jz      short loc_18001402B
0x180013fdf  mov     edx, 76h ; 'v'
0x180013fe4  jmp     short loc_18001400D
0x180013fe6  test    esi, esi
0x180013fe8  jz      short loc_180014035
0x180013fea  mov     rcx, [rbx+8]; Sid
0x180013fee  call    cs:__imp_RtlValidSid
0x180013ff4  test    al, al
0x180013ff6  jnz     short loc_180014035
0x180013ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fff  test    dword ptr [rcx+44h], 20000h
0x180014006  jz      short loc_18001402B
0x180014008  mov     edx, 77h ; 'w'
0x18001400d  mov     rcx, [rcx+38h]
0x180014011  lea     r8, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x180014018  mov     r9d, 0C000000Dh
0x18001401e  mov     dword ptr [rsp+230h+var_210], 0C000000Dh
0x180014026  call    WPP_SF_Dd
0x18001402b  mov     eax, 0C000000Dh
0x180014030  jmp     loc_180014A73
0x180014035  mov     rsi, r15
0x180014038  test    r14d, r14d
0x18001403b  jz      loc_180014122
0x180014041  lea     rdx, asc_1800CA5C4; "\\"
0x180014048  lea     rcx, [rbp+130h+var_100]; DestinationString
0x18001404c  call    cs:__imp_RtlInitUnicodeString
0x180014052  movups  xmm0, xmmword ptr [rbx]
0x180014055  movzx   r8d, word ptr [rbx]
0x180014059  xor     r14d, r14d
0x18001405c  mov     r9, [rbp+130h+var_100.Buffer]
0x180014060  mov     edx, r14d
0x180014063  movups  xmmword ptr [rbp+130h+hMem], xmm0
0x180014067  movups  xmmword ptr [rbp+130h+String1.Length], xmm0
0x18001406b  nop     dword ptr [rax+rax+00h]
0x180014070  cmp     edx, r8d
0x180014073  jnb     short loc_1800140CE
0x180014075  mov     rax, [rbx+8]
0x180014079  mov     ecx, edx
0x18001407b  shr     rcx, 1
0x18001407e  movzx   ecx, word ptr [rax+rcx*2]
0x180014082  cmp     [r9], cx
0x180014086  jz      short loc_18001408D
0x180014088  add     edx, 2
0x18001408b  jmp     short loc_180014070
0x18001408d  test    edx, edx
0x18001408f  js      short loc_1800140CE
0x180014091  movsxd  rax, edx
0x180014094  shr     rax, 1
0x180014097  inc     eax
0x180014099  mov     word ptr [rbp+130h+hMem], dx
0x18001409d  movsxd  rcx, eax
0x1800140a0  mov     rax, [rbp+130h+String1.Buffer]
0x1800140a4  mov     word ptr [rbp+130h+hMem+2], dx
0x1800140a8  lea     rcx, [rax+rcx*2]
0x1800140ac  mov     eax, 0FFFEh
0x1800140b1  mov     [rbp+130h+String1.Buffer], rcx
0x1800140b5  sub     ax, dx
0x1800140b8  movzx   ecx, [rbp+130h+String1.Length]
0x1800140bc  add     cx, ax
0x1800140bf  mov     [rbp+130h+String1.Length], cx
0x1800140c3  mov     [rbp+130h+String1.MaximumLength], cx
0x1800140c7  test    dx, dx
0x1800140ca  jz      short loc_1800140E1
0x1800140cc  jmp     short loc_1800140E5
0x1800140ce  movzx   eax, [rbp+130h+String1.Length]
0x1800140d2  movzx   edx, r14w
0x1800140d6  mov     [rbp+130h+String1.MaximumLength], ax
0x1800140da  movzx   ecx, ax
0x1800140dd  mov     dword ptr [rbp+130h+hMem], r14d
0x1800140e1  mov     [rbp+130h+hMem+8], r14
0x1800140e5  test    cx, cx
0x1800140e8  jnz     short loc_1800140EE
0x1800140ea  mov     [rbp+130h+String1.Buffer], r14
0x1800140ee  test    dx, dx
0x1800140f1  jz      short loc_180014125
0x1800140f3  lea     rdx, [rbp+130h+Buf2]; struct _GUID *
0x1800140f7  lea     rcx, [rbp+130h+hMem]; struct _UNICODE_STRING *
0x1800140fb  call    ?SampLookupInternetProviderGUIDByName@@YAJPEAU_UNICODE_STRING@@PEAU_GUID@@@Z; SampLookupInternetProviderGUIDByName(_UNICODE_STRING *,_GUID *)
0x180014100  cmp     eax, 0C0000225h
0x180014105  jnz     short loc_180014125
0x180014107  mov     rax, [rbp+130h+var_1A0]
0x18001410b  mov     ebx, 0C0000034h
0x180014110  mov     [rax], r14d
0x180014113  mov     rax, [rbp+130h+var_198]
0x180014117  mov     dword ptr [rax], 8
0x18001411d  jmp     loc_1800149D3
0x180014122  xor     r14d, r14d
0x180014125  mov     [rsp+230h+arg_0], r12
0x18001412d  lea     rdx, [rbp+130h+var_148]
0x180014131  xor     r8d, r8d
0x180014134  mov     [rsp+230h+var_30], r13
0x18001413c  mov     ecx, 4
0x180014141  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180014146  mov     ebx, eax
0x180014148  test    eax, eax
0x18001414a  js      loc_1800149A1
0x180014150  movzx   eax, cs:?SampNameDomainUsersNames@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampNameDomainUsersNames ...
0x180014157  lea     r8, [rbp+130h+ObjectAttributes]; ObjectAttributes
0x18001415b  add     ax, cs:?SampBackSlash@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampBackSlash ...
0x180014162  lea     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x180014166  sub     word ptr [rbp+130h+var_148], ax
0x18001416a  xorps   xmm0, xmm0
0x18001416d  mov     rax, cs:SampKey
0x180014174  xor     r9d, r9d; Unused
0x180014177  mov     [rbp+130h+ObjectAttributes.RootDirectory], rax
0x18001417b  mov     edx, 20019h; DesiredAccess
0x180014180  lea     rax, [rbp+130h+var_148]
0x180014184  mov     [rbp+130h+ObjectAttributes.Length], 30h ; '0'
0x18001418b  mov     [rbp+130h+ObjectAttributes.ObjectName], rax
0x18001418f  mov     [rbp+130h+ObjectAttributes.Attributes], 40h ; '@'
0x180014196  movdqu  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001419b  call    cs:__imp_RtlpNtOpenKey
0x1800141a1  mov     ebx, eax
0x1800141a3  test    eax, eax
0x1800141a5  js      loc_1800149A1
0x1800141ab  mov     r15d, 20h ; ' '
0x1800141b1  mov     dword ptr [rsp+230h+SubKeyName.Length], 200000h
0x1800141b9  mov     edx, r15d; uBytes
0x1800141bc  mov     ecx, 40h ; '@'; uFlags
0x1800141c1  call    cs:__imp_LocalAlloc
0x1800141c7  mov     [rbp+130h+SubKeyName.Buffer], rax
0x1800141cb  test    rax, rax
0x1800141ce  jz      loc_18001494E
0x1800141d4  mov     ebx, r14d
0x1800141d7  mov     [rax], r14w
0x1800141db  mov     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x1800141df  lea     r9, [rbp+130h+Unused]; Unused
0x1800141e3  mov     r8d, ebx; Index
0x1800141e6  mov     [rbp+130h+var_17C], ebx
0x1800141e9  lea     rdx, [rsp+230h+SubKeyName]; SubKeyName
0x1800141ee  call    cs:__imp_RtlpNtEnumerateSubKey
0x1800141f4  cmp     eax, 80000005h
0x1800141f9  jnz     short loc_180014252
0x1800141fb  mov     rcx, [rbp+130h+SubKeyName.Buffer]; hMem
0x1800141ff  test    rcx, rcx
0x180014202  jz      short loc_18001420E
0x180014204  call    cs:__imp_LocalFree
0x18001420a  mov     [rbp+130h+SubKeyName.Buffer], r14
0x18001420e  movzx   ecx, [rsp+230h+SubKeyName.Length]
0x180014213  mov     [rsp+230h+SubKeyName.MaximumLength], cx
0x180014218  mov     edx, ecx; uBytes
0x18001421a  mov     ecx, 40h ; '@'; uFlags
0x18001421f  mov     [rsp+230h+SubKeyName.Length], r14w
0x180014225  call    cs:__imp_LocalAlloc
0x18001422b  mov     [rbp+130h+SubKeyName.Buffer], rax
0x18001422f  test    rax, rax
0x180014232  jz      loc_18001486D
0x180014238  mov     [rax], r14w
0x18001423c  lea     r9, [rbp+130h+Unused]; Unused
0x180014240  mov     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x180014244  lea     rdx, [rsp+230h+SubKeyName]; SubKeyName
0x180014249  mov     r8d, ebx; Index
0x18001424c  call    cs:__imp_RtlpNtEnumerateSubKey
0x180014252  test    eax, eax
0x180014254  js      loc_18001493E
0x18001425a  mov     rcx, gs:60h
0x180014263  xor     edx, edx; Flags
0x180014265  movzx   r8d, [rsp+230h+SubKeyName.Length]
0x18001426b  add     r8, 2; Size
0x18001426f  mov     rcx, [rcx+30h]; HeapHandle
0x180014273  call    cs:__imp_RtlAllocateHeap
0x180014279  mov     [rbp+130h+hMem], rax
0x18001427d  mov     rsi, rax
0x180014280  test    rax, rax
0x180014283  jz      loc_1800148F4
0x180014289  movzx   edx, [rsp+230h+SubKeyName.Length]
0x18001428e  mov     rcx, rax
0x180014291  add     rdx, 2
0x180014295  nop     word ptr [rax+rax+00000000h]
0x1800142a0  mov     byte ptr [rcx], 0
0x1800142a3  lea     rcx, [rcx+1]
0x1800142a7  sub     rdx, 1
0x1800142ab  jnz     short loc_1800142A0
0x1800142ad  movzx   r8d, [rsp+230h+SubKeyName.Length]; Size
0x1800142b3  mov     rcx, rsi; void *
0x1800142b6  mov     rdx, [rbp+130h+SubKeyName.Buffer]; Src
0x1800142ba  call    memcpy_0
0x1800142bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142c6  test    dword ptr [rcx+44h], 20000h
0x1800142cd  jz      short loc_1800142EA
0x1800142cf  mov     rcx, [rcx+38h]
0x1800142d3  lea     r8, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids
0x1800142da  mov     edx, r15d
0x1800142dd  mov     dword ptr [rsp+230h+var_210], r14d
0x1800142e2  xor     r9d, r9d
0x1800142e5  call    WPP_SF_Dd
0x1800142ea  xor     edx, edx; EndPtr
0x1800142ec  mov     r8d, 10h; Radix
0x1800142f2  mov     rcx, rsi; String
0x1800142f5  call    cs:__imp_wcstoul
0x1800142fb  mov     [rbp+130h+var_1A8], eax
0x1800142fe  xor     r9d, r9d
0x180014301  mov     r12d, eax
0x180014304  mov     edx, 4
0x180014309  lea     rax, [rsp+230h+HandleId]
0x18001430e  mov     r8d, r12d
0x180014311  mov     [rsp+230h+var_1C8], rax
0x180014316  xor     ecx, ecx
0x180014318  mov     [rsp+230h+var_1D0], r14
0x18001431d  mov     [rsp+230h+var_1D8], 0
0x180014322  mov     [rsp+230h+var_1E0], 0
0x180014327  mov     [rsp+230h+var_1E8], 1
0x18001432c  mov     [rsp+230h+var_1F0], 0
0x180014331  mov     [rsp+230h+var_1F8], 0
0x180014336  mov     [rsp+230h+var_200], 1
0x18001433b  mov     [rsp+230h+var_208], 1
0x180014343  mov     [rsp+230h+var_210], r14
0x180014348  call    SampCreateAccountContext2
0x18001434d  mov     ebx, eax
0x18001434f  mov     r10, cs:WPP_GLOBAL_Control
0x180014356  test    dword ptr [r10+44h], 20000h
0x18001435e  jz      short loc_180014383
0x180014360  mov     rcx, [r10+38h]
0x180014364  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x18001436b  mov     edx, 7Bh ; '{'
0x180014370  mov     dword ptr [rsp+230h+var_210], eax
0x180014374  mov     r9d, eax
0x180014377  call    WPP_SF_Dd
0x18001437c  mov     r10, cs:WPP_GLOBAL_Control
0x180014383  mov     rdi, [rsp+230h+HandleId]
0x180014388  test    ebx, ebx
0x18001438a  js      loc_1800149A1
0x180014390  mov     eax, [rdi+0C0h]
0x180014396  lea     r9, __ImageBase
0x18001439d  and     eax, 2
0x1800143a0  mov     [rbp+130h+var_A0], 1Bh
0x1800143aa  add     rax, rax
0x1800143ad  mov     [rbp+130h+var_9C], 19h
0x1800143b7  test    byte ptr [rdi+14h], 20h
0x1800143bb  lea     r15, [rdi+360h]
0x1800143c2  mov     esi, 3
0x1800143c7  mov     [rbp+130h+var_98], 1Dh
0x1800143d1  mov     [rbp+130h+var_180], esi
0x1800143d4  lea     r14, [rdi+10h]
0x1800143d8  mov     r13, ds:(funcs_180001EF0 - 180000000h)[r9+rax*8]
0x1800143e0  jnz     short loc_18001441B
0x1800143e2  mov     edx, [r14]
0x1800143e5  lea     rax, [rbp+130h+var_180]
  ... truncated ...
```
