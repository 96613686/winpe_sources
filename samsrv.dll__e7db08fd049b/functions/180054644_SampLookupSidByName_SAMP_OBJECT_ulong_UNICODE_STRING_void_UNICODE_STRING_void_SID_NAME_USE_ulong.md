# SampLookupSidByName(_SAMP_OBJECT *,ulong,_UNICODE_STRING *,void * *,_UNICODE_STRING *,void * *,_SID_NAME_USE *,ulong *)

- ea: `0x180054644`
- end: `0x180054dd9`
- name: `?SampLookupSidByName@@YAJPEAU_SAMP_OBJECT@@KPEAU_UNICODE_STRING@@PEAPEAX12PEAW4_SID_NAME_USE@@PEAK@Z`
- size: `1941`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, unsigned int, struct _UNICODE_STRING *, void **, struct _UNICODE_STRING *, void **, enum _SID_NAME_USE *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180055cc0`

## callees

- `0x180002360`
- `0x180004fa0`
- `0x1800066f0`
- `0x1800198a0`
- `0x18001d960`
- `0x1800213d0`
- `0x180021ca0`
- `0x180022440`
- `0x180022530`
- `0x1800234e8`
- `0x180024cc8`
- `0x180024fc0`
- `0x180027250`
- `0x180027e24`
- `0x18002cd80`
- `0x180053544`
- `0x180054644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18005489b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18005489b`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054826`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054869`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054826`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054869`
- `ntdll!RtlEqualUnicodeString` at `0x180054942`
- `ntdll!RtlEqualUnicodeString` at `0x180054997`
- `ntdll!RtlEqualUnicodeString` at `0x1800549d7`
- `ntdll!RtlEqualUnicodeString` at `0x180054a14`
- `ntdll!RtlEqualUnicodeString` at `0x180054a81`
- `ntdll!RtlEqualUnicodeString` at `0x180054abe`
- `ntdll!RtlEqualUnicodeString` at `0x180054942`
- `ntdll!RtlEqualUnicodeString` at `0x180054997`
- `ntdll!RtlEqualUnicodeString` at `0x1800549d7`
- `ntdll!RtlEqualUnicodeString` at `0x180054a14`
- `ntdll!RtlEqualUnicodeString` at `0x180054a81`
- `ntdll!RtlEqualUnicodeString` at `0x180054abe`
- `ntdll!RtlCopySid` at `0x180054c3c`
- `ntdll!RtlCopySid` at `0x180054c3c`
- `ntdll!RtlLengthSid` at `0x180054bed`
- `ntdll!RtlLengthSid` at `0x180054bed`
- `ntdll!NtClose` at `0x180054d7b`
- `ntdll!NtClose` at `0x180054d7b`
- `ntdll!RtlpNtOpenKey` at `0x180054793`
- `ntdll!RtlpNtOpenKey` at `0x180054793`
- `ntdll!RtlInitUnicodeString` at `0x1800547d9`
- `ntdll!RtlInitUnicodeString` at `0x1800547d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054bfc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054bfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054cef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d61`

## pseudocode

```c
__int64 __fastcall SampLookupSidByName(
        struct _SAMP_OBJECT *a1,
        int a2,
        struct _UNICODE_STRING *a3,
        void **a4,
        struct _UNICODE_STRING *a5,
        void **a6,
        enum _SID_NAME_USE *a7,
        unsigned int *a8)
{
  char v8; // r12
  enum _SID_NAME_USE *v9; // r14
  wchar_t *v10; // r13
  char v11; // r15
  struct _SAMP_OBJECT *v12; // rsi
  wchar_t *v13; // rdi
  int inited; // ebx
  ULONG v15; // ebx
  HLOCAL v16; // r14
  unsigned int v17; // edx
  NTSTATUS v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  HLOCAL v22; // rax
  int FullSid; // eax
  ULONG v24; // ebx
  struct _UNICODE_STRING *v26; // [rsp+20h] [rbp-E0h]
  wchar_t *String; // [rsp+38h] [rbp-C8h] BYREF
  ULONG Index; // [rsp+40h] [rbp-C0h]
  struct _SAMP_OBJECT *v30; // [rsp+48h] [rbp-B8h]
  HLOCAL v31; // [rsp+50h] [rbp-B0h]
  enum _SID_NAME_USE *v32; // [rsp+58h] [rbp-A8h]
  PVOID HandleId; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING SubKeyName; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING *v36; // [rsp+80h] [rbp-80h]
  void *v37; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v38; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING v39; // [rsp+98h] [rbp-68h] BYREF
  ULONG Unused[2]; // [rsp+A8h] [rbp-58h] BYREF
  PUNICODE_STRING v41; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING v43; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v45[4]; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING String2; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING v47; // [rsp+108h] [rbp+8h] BYREF
  void **v48; // [rsp+118h] [rbp+18h]
  void **v49; // [rsp+120h] [rbp+20h]
  unsigned int *v50; // [rsp+128h] [rbp+28h]
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp+30h] BYREF
  HLOCAL Src[2]; // [rsp+140h] [rbp+40h] BYREF
  HLOCAL hMem[2]; // [rsp+150h] [rbp+50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+160h] [rbp+60h] BYREF
  struct _GUID v55; // [rsp+190h] [rbp+90h] BYREF

  v8 = 0;
  v9 = a7;
  v41 = a5;
  v10 = 0;
  v49 = a6;
  v11 = 0;
  v12 = 0;
  v50 = a8;
  v13 = 0;
  v36 = a3;
  v30 = a1;
  v31 = 0;
  v37 = 0;
  v48 = a4;
  v32 = a7;
  v42 = 0;
  v38 = 0;
  DestinationString = 0;
  KeyHandle = 0;
  v39 = 0;
  *(_QWORD *)Unused = 0;
  String2 = 0;
  HandleId = 0;
  v55 = 0;
  String = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_OWORD *)Src = 0;
  *(_OWORD *)hMem = 0;
  v43 = 0;
  String1 = 0;
  v47 = 0;
  SubKeyName = 0;
  inited = SampBuildAccountKeyName(4, &v42, 0);
  if ( inited < 0 )
    goto LABEL_77;
  LOWORD(v42) = v42 - (SampBackSlash.Length + SampNameDomainUsersNames.Length);
  ObjectAttributes.RootDirectory = SampKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v42;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  inited = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
  SampFreeUnicodeString(&v42);
  if ( inited < 0 )
    goto LABEL_77;
  inited = SampInitUnicodeString(&SubKeyName, 0x20u);
  if ( inited < 0 )
    goto LABEL_77;
  v15 = 0;
  Index = 0;
  v16 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\");
  SampRtlSplitNames(v36, v17, &DestinationString, &v39, &String2);
  while ( 1 )
  {
    v45[0] = 27;
    v45[1] = 25;
    v45[2] = 29;
    v45[3] = 40;
    v18 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, v15, (ULONG)Unused);
    if ( v18 == -2147483643 )
    {
      SampFreeUnicodeString(&SubKeyName);
      inited = SampInitUnicodeString(&SubKeyName, SubKeyName.Length);
      if ( inited < 0 )
        goto LABEL_64;
      v18 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, Index, (ULONG)Unused);
    }
    if ( v18 < 0 )
    {
      inited = 0;
      if ( v18 != -2147483622 )
        inited = v18;
      if ( inited >= 0 )
      {
LABEL_63:
        if ( v11 )
          goto LABEL_73;
      }
LABEL_64:
      if ( v16 )
        goto LABEL_65;
      goto LABEL_66;
    }
    inited = SampMakeNullTerminateString(&SubKeyName, &String);
    if ( inited < 0 )
      goto LABEL_64;
    LODWORD(v36) = wcstoul(String, 0, 16);
    inited = SampCreateAccountContext(4, (int)v36, v19, v20, (__int64)v26, (__int64)&HandleId);
    if ( inited < 0 )
    {
      v12 = (struct _SAMP_OBJECT *)HandleId;
      goto LABEL_64;
    }
    v12 = (struct _SAMP_OBJECT *)HandleId;
    inited = SampReadExtendedAttributes((struct _SAMP_OBJECT *)HandleId, 0, v45, 4u);
    if ( inited < 0 )
      goto LABEL_64;
    inited = SampGetExtendedAttribute((__int64)v12, 29, (__int64)Src);
    if ( inited < 0 )
      goto LABEL_64;
    v16 = Src[1];
    v21 = a2;
    if ( Src[1] )
      break;
LABEL_28:
    if ( (v21 & 0x100000) == 0 )
      goto LABEL_35;
    inited = SampGetExtendedAttribute((__int64)v12, 40, (__int64)hMem);
    if ( inited < 0 )
      goto LABEL_64;
    v13 = (wchar_t *)hMem[1];
    if ( hMem[1] )
    {
      inited = SampGetUnicodeStringAttribute(v12);
      if ( inited < 0 )
        goto LABEL_64;
      if ( !RtlEqualUnicodeString(&v47, &String2, 1u) )
      {
LABEL_36:
        LocalFree(v13);
        v13 = 0;
        goto LABEL_37;
      }
      if ( v39.Length
        && !RtlEqualUnicodeString(&v39, (PCUNICODE_STRING)SampDefinedDomains + 85 * *((unsigned int *)v30 + 50) + 1, 1u) )
      {
LABEL_35:
        if ( !v13 )
          goto LABEL_37;
        goto LABEL_36;
      }
      v10 = v13;
      v11 = 1;
      v13 = 0;
LABEL_53:
      v24 = RtlLengthSid(*((PSID *)SampDefinedDomains + 170 * *((unsigned int *)v30 + 50) + 1));
      v31 = LocalAlloc(0x40u, v24);
      if ( !v31 )
      {
        inited = -1073741670;
        goto LABEL_64;
      }
      inited = RtlCopySid(v24, v31, *((PSID *)SampDefinedDomains + 170 * *((unsigned int *)v30 + 50) + 1));
      if ( inited >= 0 )
      {
        inited = SampDuplicateUnicodeString(
                   v41,
                   (PCUNICODE_STRING)SampDefinedDomains + 85 * *((unsigned int *)v30 + 50) + 1);
        if ( inited >= 0 )
        {
          v22 = v31;
LABEL_58:
          *v48 = v10;
          *v49 = v22;
          --*v50;
          *v32 = SidTypeUser;
          goto LABEL_63;
        }
      }
      goto LABEL_64;
    }
LABEL_37:
    if ( String1.Buffer )
    {
      LocalFree(String1.Buffer);
      String1 = 0;
    }
    if ( v43.Buffer )
      LocalFree(v43.Buffer);
    if ( v16 )
    {
      LocalFree(v16);
      v16 = 0;
    }
    if ( String )
    {
      LocalFree(String);
      String = 0;
    }
    if ( v12 )
    {
      SampDeleteContext(v12);
      v12 = 0;
      HandleId = 0;
    }
    v15 = ++Index;
  }
  if ( (a2 & 0x4000) == 0 )
  {
LABEL_22:
    if ( (v21 & 0x200) != 0 )
    {
      inited = SampGetUnicodeStringAttribute(v12);
      if ( inited < 0 )
        goto LABEL_65;
      if ( RtlEqualUnicodeString(&v47, &String2, 1u)
        && (!v39.Length
         || RtlEqualUnicodeString(&v39, (PCUNICODE_STRING)SampDefinedDomains + 85 * *((unsigned int *)v30 + 50) + 1, 1u)) )
      {
        FullSid = SampCreateFullSid(
                    *((PSID *)SampDefinedDomains + 170 * *((unsigned int *)v30 + 50) + 1),
                    (ULONG)v36,
                    (PSID *)&v38);
        v10 = v38;
        v11 = 1;
        v8 = 1;
        inited = FullSid;
        if ( FullSid < 0 )
          goto LABEL_65;
        goto LABEL_53;
      }
      v21 = a2;
    }
    goto LABEL_28;
  }
  inited = SampGetExtendedAttribute((__int64)v12, 25, (__int64)&String1);
  if ( inited < 0 )
    goto LABEL_65;
  if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
    goto LABEL_21;
  inited = SampGetExtendedAttribute((__int64)v12, 27, (__int64)&v55);
  if ( inited < 0 )
    goto LABEL_65;
  inited = SampLookupInternetProviderNameByGUID(&v55, &v43);
  if ( inited < 0 )
    goto LABEL_65;
  if ( !v39.Length || !RtlEqualUnicodeString(&v43, &v39, 1u) )
  {
LABEL_21:
    v21 = a2;
    goto LABEL_22;
  }
  v10 = (wchar_t *)v16;
  inited = SampExtractInternetDomainSidFromSid(v16, &v37);
  v11 = 1;
  v22 = v37;
  v31 = v37;
  if ( inited >= 0 )
  {
    *v41 = v43;
    goto LABEL_58;
  }
LABEL_65:
  LocalFree(v16);
LABEL_66:
  if ( v10 )
    LocalFree(v10);
  if ( v31 )
    LocalFree(v31);
  if ( v13 )
    LocalFree(v13);
  if ( v11 )
  {
LABEL_73:
    if ( v8 && v43.Buffer )
      LocalFree(v43.Buffer);
  }
  v9 = v32;
  v13 = String;
LABEL_77:
  if ( String1.Buffer )
    LocalFree(String1.Buffer);
  if ( !v11 )
  {
    *v9 = SidTypeUnknown;
    if ( (int)(inited + 0x80000000) < 0 || inited == -1073741724 )
      inited = -1073741772;
  }
  if ( v12 )
    SampDeleteContext(v12);
  if ( v13 )
    LocalFree(v13);
  SampFreeUnicodeString(&SubKeyName);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      132,
      &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
      (unsigned int)inited,
      inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180054644  mov     [rsp-8+arg_8], rbx
0x180054649  push    rbp
0x18005464a  push    rsi
0x18005464b  push    rdi
0x18005464c  push    r12
0x18005464e  push    r13
0x180054650  push    r14
0x180054652  push    r15
0x180054654  lea     rbp, [rsp-0B0h]
0x18005465c  sub     rsp, 1B0h
0x180054663  mov     rax, cs:__security_cookie
0x18005466a  xor     rax, rsp
0x18005466d  mov     [rbp+0E0h+var_40], rax
0x180054674  mov     rax, [rbp+0E0h+arg_20]
0x18005467b  xor     r12d, r12d
0x18005467e  mov     r14, [rbp+0E0h+arg_30]
0x180054685  xorps   xmm0, xmm0
0x180054688  xorps   xmm1, xmm1
0x18005468b  mov     [rbp+0E0h+var_130], rax
0x18005468f  mov     rax, [rbp+0E0h+arg_28]
0x180054696  mov     r13d, r12d
0x180054699  mov     [rbp+0E0h+var_C0], rax
0x18005469d  mov     r15b, r12b
0x1800546a0  mov     rax, [rbp+0E0h+arg_38]
0x1800546a7  mov     esi, r12d
0x1800546aa  mov     [rbp+0E0h+var_B8], rax
0x1800546ae  mov     edi, r12d
0x1800546b1  mov     eax, r12d
0x1800546b4  mov     [rbp+0E0h+var_160], r8
0x1800546b8  mov     [rsp+1E0h+var_1B0], edx
0x1800546bc  xor     r8d, r8d
0x1800546bf  mov     [rsp+1E0h+var_198], rcx
0x1800546c4  lea     rdx, [rbp+0E0h+var_128]
0x1800546c8  lea     ecx, [r12+4]
0x1800546cd  mov     [rsp+1E0h+var_190], rax
0x1800546d2  mov     [rbp+0E0h+var_158], rax
0x1800546d6  mov     [rbp+0E0h+var_C8], r9
0x1800546da  mov     [rsp+1E0h+var_188], r14
0x1800546df  movups  [rbp+0E0h+var_128], xmm0
0x1800546e3  mov     [rbp+0E0h+var_150], r12
0x1800546e7  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm1
0x1800546eb  mov     [rsp+1E0h+KeyHandle], r12
0x1800546f0  movups  xmmword ptr [rbp+0E0h+var_148.Length], xmm0
0x1800546f4  mov     qword ptr [rbp+0E0h+Unused], r12
0x1800546f8  movups  xmmword ptr [rbp+0E0h+String2.Length], xmm1
0x1800546fc  mov     [rsp+1E0h+HandleId], r12
0x180054701  movups  xmmword ptr [rbp+0E0h+var_50.Data1], xmm0
0x180054708  mov     [rsp+1E0h+String], r12
0x18005470d  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x180054711  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x180054715  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005471c  movups  xmmword ptr [rbp+0E0h+Src], xmm0
0x180054720  movups  xmmword ptr [rbp+0E0h+hMem], xmm0
0x180054724  movups  xmmword ptr [rbp+0E0h+var_118.Length], xmm1
0x180054728  movups  xmmword ptr [rbp+0E0h+String1.Length], xmm0
0x18005472c  movups  xmmword ptr [rbp+0E0h+var_D8.Length], xmm1
0x180054730  movups  xmmword ptr [rsp+1E0h+SubKeyName.Length], xmm0
0x180054735  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x18005473a  mov     ebx, eax
0x18005473c  test    eax, eax
0x18005473e  js      loc_180054D18
0x180054744  movzx   eax, cs:?SampNameDomainUsersNames@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampNameDomainUsersNames ...
0x18005474b  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x18005474f  add     ax, cs:?SampBackSlash@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampBackSlash ...
0x180054756  lea     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18005475b  sub     word ptr [rbp+0E0h+var_128], ax
0x18005475f  xorps   xmm0, xmm0
0x180054762  mov     rax, cs:SampKey
0x180054769  xor     r9d, r9d; Unused
0x18005476c  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], rax
0x180054770  mov     edx, 20019h; DesiredAccess
0x180054775  lea     rax, [rbp+0E0h+var_128]
0x180054779  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x180054780  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x180054784  mov     [rbp+0E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005478b  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180054793  call    cs:__imp_RtlpNtOpenKey
0x180054799  lea     rcx, [rbp+0E0h+var_128]
0x18005479d  mov     ebx, eax
0x18005479f  call    SampFreeUnicodeString
0x1800547a4  test    ebx, ebx
0x1800547a6  js      loc_180054D18
0x1800547ac  lea     edx, [r12+20h]; unsigned __int16
0x1800547b1  lea     rcx, [rsp+1E0h+SubKeyName]; struct _UNICODE_STRING *
0x1800547b6  call    ?SampInitUnicodeString@@YAJPEAU_UNICODE_STRING@@G@Z; SampInitUnicodeString(_UNICODE_STRING *,ushort)
0x1800547bb  mov     ebx, eax
0x1800547bd  test    eax, eax
0x1800547bf  js      loc_180054D18
0x1800547c5  xor     ebx, ebx
0x1800547c7  lea     rdx, asc_1800CA5C4; "\\"
0x1800547ce  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x1800547d2  mov     [rsp+1E0h+Index], ebx
0x1800547d6  mov     r14d, r12d
0x1800547d9  call    cs:__imp_RtlInitUnicodeString
0x1800547df  mov     rcx, [rbp+0E0h+var_160]; struct _UNICODE_STRING *
0x1800547e3  lea     rax, [rbp+0E0h+String2]
0x1800547e7  lea     r9, [rbp+0E0h+var_148]; struct _UNICODE_STRING *
0x1800547eb  mov     [rsp+1E0h+var_1C0], rax; struct _UNICODE_STRING *
0x1800547f0  lea     r8, [rbp+0E0h+DestinationString]; struct _UNICODE_STRING *
0x1800547f4  call    ?SampRtlSplitNames@@YAXPEAU_UNICODE_STRING@@K000@Z; SampRtlSplitNames(_UNICODE_STRING *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1800547f9  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1800547fe  lea     r9, [rbp+0E0h+Unused]; Unused
0x180054802  mov     r8d, ebx; Index
0x180054805  mov     [rbp+0E0h+var_F8], 1Bh
0x18005480c  lea     rdx, [rsp+1E0h+SubKeyName]; SubKeyName
0x180054811  mov     [rbp+0E0h+var_F4], 19h
0x180054818  mov     [rbp+0E0h+var_F0], 1Dh
0x18005481f  mov     [rbp+0E0h+var_EC], 28h ; '('
0x180054826  call    cs:__imp_RtlpNtEnumerateSubKey
0x18005482c  cmp     eax, 80000005h
0x180054831  jnz     short loc_18005486F
0x180054833  lea     rcx, [rsp+1E0h+SubKeyName]
0x180054838  call    SampFreeUnicodeString
0x18005483d  movzx   edx, [rsp+1E0h+SubKeyName.Length]; unsigned __int16
0x180054842  lea     rcx, [rsp+1E0h+SubKeyName]; struct _UNICODE_STRING *
0x180054847  call    ?SampInitUnicodeString@@YAJPEAU_UNICODE_STRING@@G@Z; SampInitUnicodeString(_UNICODE_STRING *,ushort)
0x18005484c  mov     ebx, eax
0x18005484e  test    eax, eax
0x180054850  js      loc_180054CB8
0x180054856  mov     r8d, [rsp+1E0h+Index]; Index
0x18005485b  lea     r9, [rbp+0E0h+Unused]; Unused
0x18005485f  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x180054864  lea     rdx, [rsp+1E0h+SubKeyName]; SubKeyName
0x180054869  call    cs:__imp_RtlpNtEnumerateSubKey
0x18005486f  test    eax, eax
0x180054871  js      loc_180054CA4
0x180054877  lea     rdx, [rsp+1E0h+String]
0x18005487c  lea     rcx, [rsp+1E0h+SubKeyName]
0x180054881  call    SampMakeNullTerminateString
0x180054886  mov     ebx, eax
0x180054888  test    eax, eax
0x18005488a  js      loc_180054CB8
0x180054890  mov     rcx, [rsp+1E0h+String]; String
0x180054895  xor     edx, edx; EndPtr
0x180054897  lea     r8d, [rdx+10h]; Radix
0x18005489b  call    cs:__imp_wcstoul
0x1800548a1  lea     rcx, [rsp+1E0h+HandleId]
0x1800548a6  mov     esi, 4
0x1800548ab  mov     edx, eax
0x1800548ad  mov     dword ptr [rbp+0E0h+var_160], eax
0x1800548b0  mov     [rsp+1E0h+var_1B8], rcx
0x1800548b5  mov     ecx, esi
0x1800548b7  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x1800548bc  mov     ebx, eax
0x1800548be  test    eax, eax
0x1800548c0  js      loc_180054C9D
0x1800548c6  mov     r9d, esi
0x1800548c9  lea     r8, [rbp+0E0h+var_F8]
0x1800548cd  mov     rsi, [rsp+1E0h+HandleId]
0x1800548d2  xor     edx, edx
0x1800548d4  mov     rcx, rsi
0x1800548d7  call    SampReadExtendedAttributes
0x1800548dc  mov     ebx, eax
0x1800548de  test    eax, eax
0x1800548e0  js      loc_180054CB8
0x1800548e6  lea     r8, [rbp+0E0h+Src]
0x1800548ea  mov     edx, 1Dh
0x1800548ef  mov     rcx, rsi
0x1800548f2  call    SampGetExtendedAttribute
0x1800548f7  mov     ebx, eax
0x1800548f9  test    eax, eax
0x1800548fb  js      loc_180054CB8
0x180054901  mov     r14, [rbp+0E0h+Src+8]
0x180054905  xor     ebx, ebx
0x180054907  mov     eax, [rsp+1E0h+var_1B0]
0x18005490b  test    r14, r14
0x18005490e  jz      loc_180054A26
0x180054914  bt      eax, 0Eh
0x180054918  jnb     loc_1800549A9
0x18005491e  lea     r8, [rbp+0E0h+String1]
0x180054922  mov     rcx, rsi
0x180054925  lea     edx, [rbx+19h]
0x180054928  call    SampGetExtendedAttribute
0x18005492d  mov     ebx, eax
0x18005492f  test    eax, eax
0x180054931  js      loc_180054CBD
0x180054937  mov     r8b, 1; CaseInsensitive
0x18005493a  lea     rdx, [rbp+0E0h+String2]; String2
0x18005493e  lea     rcx, [rbp+0E0h+String1]; String1
0x180054942  call    cs:__imp_RtlEqualUnicodeString
0x180054948  xor     ebx, ebx
0x18005494a  test    al, al
0x18005494c  jz      short loc_1800549A5
0x18005494e  lea     r8, [rbp+0E0h+var_50]
0x180054955  mov     rcx, rsi
0x180054958  lea     edx, [rbx+1Bh]
0x18005495b  call    SampGetExtendedAttribute
0x180054960  mov     ebx, eax
0x180054962  test    eax, eax
0x180054964  js      loc_180054CBD
0x18005496a  lea     rdx, [rbp+0E0h+var_118]; struct _UNICODE_STRING *
0x18005496e  lea     rcx, [rbp+0E0h+var_50]; struct _GUID *
0x180054975  call    ?SampLookupInternetProviderNameByGUID@@YAJPEAU_GUID@@PEAU_UNICODE_STRING@@@Z; SampLookupInternetProviderNameByGUID(_GUID *,_UNICODE_STRING *)
0x18005497a  mov     ebx, eax
0x18005497c  test    eax, eax
0x18005497e  js      loc_180054CBD
0x180054984  xor     ebx, ebx
0x180054986  cmp     [rbp+0E0h+var_148.Length], bx
0x18005498a  jz      short loc_1800549A5
0x18005498c  mov     r8b, 1; CaseInsensitive
0x18005498f  lea     rdx, [rbp+0E0h+var_148]; String2
0x180054993  lea     rcx, [rbp+0E0h+var_118]; String1
0x180054997  call    cs:__imp_RtlEqualUnicodeString
0x18005499d  test    al, al
0x18005499f  jnz     loc_180054B4F
0x1800549a5  mov     eax, [rsp+1E0h+var_1B0]
0x1800549a9  bt      eax, 9
0x1800549ad  jnb     short loc_180054A26
0x1800549af  xor     r8d, r8d
0x1800549b2  lea     r9, [rbp+0E0h+var_D8]
0x1800549b6  mov     rcx, rsi; struct _SAMP_OBJECT *
0x1800549b9  lea     edx, [r8+1]
0x1800549bd  call    SampGetUnicodeStringAttribute
0x1800549c2  mov     ebx, eax
0x1800549c4  test    eax, eax
0x1800549c6  js      loc_180054CBD
0x1800549cc  mov     r8b, 1; CaseInsensitive
0x1800549cf  lea     rdx, [rbp+0E0h+String2]; String2
0x1800549d3  lea     rcx, [rbp+0E0h+var_D8]; String1
0x1800549d7  call    cs:__imp_RtlEqualUnicodeString
0x1800549dd  xor     ebx, ebx
0x1800549df  test    al, al
0x1800549e1  jz      short loc_180054A22
0x1800549e3  cmp     [rbp+0E0h+var_148.Length], bx
0x1800549e7  jz      loc_180054B87
0x1800549ed  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800549f4  mov     r8b, 1; CaseInsensitive
0x1800549f7  mov     rax, [rsp+1E0h+var_198]
0x1800549fc  add     rdx, 10h
0x180054a00  mov     eax, [rax+0C8h]
0x180054a06  imul    rcx, rax, 550h
0x180054a0d  add     rdx, rcx; String2
0x180054a10  lea     rcx, [rbp+0E0h+var_148]; String1
0x180054a14  call    cs:__imp_RtlEqualUnicodeString
0x180054a1a  test    al, al
0x180054a1c  jnz     loc_180054B87
0x180054a22  mov     eax, [rsp+1E0h+var_1B0]
0x180054a26  bt      eax, 14h
0x180054a2a  jnb     loc_180054ACC
0x180054a30  lea     r8, [rbp+0E0h+hMem]
0x180054a34  mov     edx, 28h ; '('
0x180054a39  mov     rcx, rsi
0x180054a3c  call    SampGetExtendedAttribute
0x180054a41  mov     ebx, eax
0x180054a43  test    eax, eax
0x180054a45  js      loc_180054CB8
0x180054a4b  mov     rdi, [rbp+0E0h+hMem+8]
0x180054a4f  xor     ebx, ebx
0x180054a51  test    rdi, rdi
0x180054a54  jz      loc_180054ADD
0x180054a5a  lea     r9, [rbp+0E0h+var_D8]
0x180054a5e  xor     r8d, r8d
0x180054a61  lea     edx, [rbx+1]
0x180054a64  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180054a67  call    SampGetUnicodeStringAttribute
0x180054a6c  mov     ebx, eax
0x180054a6e  test    eax, eax
0x180054a70  js      loc_180054CB8
0x180054a76  mov     r8b, 1; CaseInsensitive
0x180054a79  lea     rdx, [rbp+0E0h+String2]; String2
0x180054a7d  lea     rcx, [rbp+0E0h+var_D8]; String1
0x180054a81  call    cs:__imp_RtlEqualUnicodeString
0x180054a87  xor     ebx, ebx
0x180054a89  test    al, al
0x180054a8b  jz      short loc_180054AD1
0x180054a8d  cmp     [rbp+0E0h+var_148.Length], bx
0x180054a91  jz      loc_180054BC6
0x180054a97  mov     rax, [rsp+1E0h+var_198]
0x180054a9c  lea     rcx, [rbp+0E0h+var_148]; String1
0x180054aa0  mov     r8b, 1; CaseInsensitive
0x180054aa3  mov     eax, [rax+0C8h]
0x180054aa9  imul    rdx, rax, 550h
0x180054ab0  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180054ab7  add     rax, 10h
0x180054abb  add     rdx, rax; String2
0x180054abe  call    cs:__imp_RtlEqualUnicodeString
0x180054ac4  test    al, al
0x180054ac6  jnz     loc_180054BC6
0x180054acc  test    rdi, rdi
0x180054acf  jz      short loc_180054ADD
0x180054ad1  mov     rcx, rdi; hMem
0x180054ad4  call    cs:__imp_LocalFree
0x180054ada  mov     rdi, rbx
0x180054add  mov     rcx, [rbp+0E0h+String1.Buffer]; hMem
0x180054ae1  test    rcx, rcx
0x180054ae4  jz      short loc_180054AF3
0x180054ae6  call    cs:__imp_LocalFree
0x180054aec  xorps   xmm0, xmm0
0x180054aef  movups  xmmword ptr [rbp+0E0h+String1.Length], xmm0
0x180054af3  mov     rcx, [rbp+0E0h+var_118.Buffer]; hMem
0x180054af7  test    rcx, rcx
0x180054afa  jz      short loc_180054B02
0x180054afc  call    cs:__imp_LocalFree
0x180054b02  test    r14, r14
0x180054b05  jz      short loc_180054B13
0x180054b07  mov     rcx, r14; hMem
0x180054b0a  call    cs:__imp_LocalFree
0x180054b10  mov     r14, rbx
0x180054b13  mov     rax, [rsp+1E0h+String]
0x180054b18  test    rax, rax
  ... truncated ...
```
