# SampLookupNameBySid(_SAMP_OBJECT *,ulong,void *,_UNICODE_STRING *,_UNICODE_STRING *,void * *,_SID_NAME_USE *,ulong *)

- ea: `0x180053f9c`
- end: `0x18005463c`
- name: `?SampLookupNameBySid@@YAJPEAU_SAMP_OBJECT@@KPEAXPEAU_UNICODE_STRING@@2PEAPEAXPEAW4_SID_NAME_USE@@PEAK@Z`
- size: `1696`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, unsigned int, void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **, enum _SID_NAME_USE *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800559a0`

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
- `0x180023760`
- `0x180024fc0`
- `0x180027250`
- `0x180027e24`
- `0x18002cd80`
- `0x180053544`
- `0x180053f9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800541be`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800541be`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054148`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054189`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054148`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180054189`
- `ntdll!RtlEqualSid` at `0x18005427a`
- `ntdll!RtlEqualSid` at `0x1800542ba`
- `ntdll!RtlEqualSid` at `0x1800543b4`
- `ntdll!RtlEqualSid` at `0x18005427a`
- `ntdll!RtlEqualSid` at `0x1800542ba`
- `ntdll!RtlEqualSid` at `0x1800543b4`
- `ntdll!NtClose` at `0x180054594`
- `ntdll!NtClose` at `0x180054594`
- `ntdll!RtlpNtOpenKey` at `0x1800540e1`
- `ntdll!RtlpNtOpenKey` at `0x1800540e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054293`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800542e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800543d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800543fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054508`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005456c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054293`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800542e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800543d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800543fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054508`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005456c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545de`

## pseudocode

```c
__int64 __fastcall SampLookupNameBySid(
        struct _SAMP_OBJECT *a1,
        int a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        void **a6,
        enum _SID_NAME_USE *a7,
        unsigned int *a8)
{
  enum _SID_NAME_USE *v8; // r13
  PSID v9; // r14
  PSID v10; // r15
  char v11; // si
  PVOID v12; // rdi
  wchar_t *v13; // r12
  int inited; // ebx
  ULONG v15; // r13d
  NTSTATUS v16; // eax
  int NullTerminateString; // eax
  unsigned int v18; // r13d
  __int64 v19; // r8
  __int64 v20; // r9
  PSID v21; // rbx
  int v22; // r13d
  void **v23; // rcx
  struct _UNICODE_STRING v24; // xmm0
  struct _UNICODE_STRING v25; // xmm1
  struct _SAMP_OBJECT *v26; // r13
  struct _UNICODE_STRING v27; // xmm0
  void **v28; // rcx
  void *v29; // rsi
  struct _UNICODE_STRING v30; // xmm0
  __int64 v32; // [rsp+20h] [rbp-E0h]
  void *v34; // [rsp+40h] [rbp-C0h]
  int v35; // [rsp+48h] [rbp-B8h]
  PSID Sid2; // [rsp+50h] [rbp-B0h] BYREF
  PVOID HandleId; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING SubKeyName; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid1; // [rsp+80h] [rbp-80h]
  void *v42; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v43; // [rsp+90h] [rbp-70h] BYREF
  ULONG Unused[2]; // [rsp+98h] [rbp-68h] BYREF
  struct _SAMP_OBJECT *v45; // [rsp+A0h] [rbp-60h]
  unsigned int *v46; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING *v47; // [rsp+B0h] [rbp-50h]
  void **v48; // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING *v49; // [rsp+C0h] [rbp-40h]
  __int128 v50; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v51[4]; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL v52[2]; // [rsp+E8h] [rbp-18h]
  HLOCAL v53[2]; // [rsp+F8h] [rbp-8h] BYREF
  HLOCAL v54[2]; // [rsp+108h] [rbp+8h] BYREF
  HLOCAL v55[2]; // [rsp+118h] [rbp+18h] BYREF
  PSID hMem[2]; // [rsp+128h] [rbp+28h] BYREF
  PSID v57[2]; // [rsp+138h] [rbp+38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+48h] BYREF
  struct _GUID v59; // [rsp+178h] [rbp+78h] BYREF

  v8 = a7;
  v48 = a6;
  v45 = a1;
  v46 = a8;
  *a4 = 0;
  Sid1 = a3;
  v9 = 0;
  v49 = a5;
  *a5 = 0;
  v47 = a4;
  v10 = 0;
  v50 = 0;
  KeyHandle = 0;
  v11 = 0;
  v59 = 0;
  *(_QWORD *)Unused = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  HandleId = 0;
  v13 = 0;
  Sid2 = 0;
  v43 = 0;
  *(_OWORD *)hMem = 0;
  String = 0;
  *(_OWORD *)v57 = 0;
  v34 = 0;
  v42 = 0;
  SubKeyName = 0;
  *(_OWORD *)v54 = 0;
  *(_OWORD *)v55 = 0;
  *(_OWORD *)v52 = 0;
  *(_OWORD *)v53 = 0;
  inited = SampBuildAccountKeyName(4, &v50, 0);
  if ( inited < 0 )
    goto LABEL_50;
  LOWORD(v50) = v50 - (SampBackSlash.Length + SampNameDomainUsersNames.Length);
  ObjectAttributes.RootDirectory = SampKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v50;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  inited = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
  SampFreeUnicodeString(&v50);
  if ( inited < 0 )
    goto LABEL_50;
  v15 = 0;
  v35 = 0;
  inited = SampInitUnicodeString(&SubKeyName, 0x20u);
  if ( inited < 0 )
    goto LABEL_49;
  while ( 1 )
  {
    v51[0] = 27;
    v51[1] = 25;
    v51[2] = 29;
    v51[3] = 40;
    v16 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, v15, (ULONG)Unused);
    if ( v16 == -2147483643 )
    {
      SampFreeUnicodeString(&SubKeyName);
      inited = SampInitUnicodeString(&SubKeyName, SubKeyName.Length);
      if ( inited < 0 )
        goto LABEL_49;
      v16 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, v15, (ULONG)Unused);
    }
    if ( v16 < 0 )
    {
      inited = 0;
      if ( v16 != -2147483622 )
        inited = v16;
      goto LABEL_49;
    }
    NullTerminateString = SampMakeNullTerminateString(&SubKeyName, &String);
    v13 = String;
    inited = NullTerminateString;
    if ( NullTerminateString < 0 )
      goto LABEL_49;
    v18 = wcstoul(String, 0, 16);
    inited = SampCreateAccountContext(4, v18, v19, v20, v32, (__int64)&HandleId);
    if ( inited < 0 )
    {
      v12 = HandleId;
      goto LABEL_49;
    }
    v12 = HandleId;
    inited = SampReadExtendedAttributes((struct _SAMP_OBJECT *)HandleId, 0, v51, 4u);
    if ( inited < 0 )
      goto LABEL_49;
    inited = SampGetExtendedAttribute((__int64)v12, 29, (__int64)hMem);
    if ( inited < 0 )
      goto LABEL_49;
    v9 = hMem[1];
    if ( !hMem[1] )
    {
      v22 = a2;
      goto LABEL_30;
    }
    if ( (a2 & 0x80u) == 0 )
    {
      v21 = Sid1;
    }
    else
    {
      inited = SampCreateFullSid(*((PSID *)SampDefinedDomains + 170 * *((unsigned int *)v45 + 50) + 1), v18, &Sid2);
      if ( inited < 0 )
        goto LABEL_49;
      v21 = Sid1;
      if ( RtlEqualSid(Sid1, Sid2) )
        v11 = 1;
      LocalFree(Sid2);
      Sid2 = 0;
    }
    v22 = a2;
    if ( (a2 & 0x8000) != 0 && RtlEqualSid(v21, v9) )
    {
      v11 = 1;
    }
    else if ( !v11 )
    {
      goto LABEL_24;
    }
    inited = SampExtractInternetDomainSidFromSid(v9, &v43);
    if ( inited < 0 )
      goto LABEL_49;
LABEL_24:
    LocalFree(v9);
    v9 = 0;
    if ( v11 )
    {
      inited = SampGetExtendedAttribute((__int64)v12, 27, (__int64)&v59);
      if ( inited >= 0 )
      {
        inited = SampLookupInternetProviderNameByGUID(&v59, (struct _UNICODE_STRING *)v54);
        if ( inited >= 0 )
        {
          inited = SampGetExtendedAttribute((__int64)v12, 25, (__int64)v55);
          if ( inited >= 0 )
          {
            v23 = v48;
            v24 = *(struct _UNICODE_STRING *)v54;
            --*v46;
            v25 = *(struct _UNICODE_STRING *)v55;
            *a7 = SidTypeUser;
            *v23 = v43;
            *v49 = v24;
            *v47 = v25;
            goto LABEL_60;
          }
        }
      }
      goto LABEL_49;
    }
LABEL_30:
    inited = SampGetExtendedAttribute((__int64)v12, 40, (__int64)v57);
    if ( inited < 0 )
      goto LABEL_49;
    v10 = v57[1];
    if ( v57[1] )
    {
      if ( (v22 & 0x100000) != 0 && RtlEqualSid(Sid1, v57[1]) )
        v11 = 1;
      LocalFree(v10);
      v10 = 0;
      if ( v11 )
        break;
    }
    if ( v12 )
    {
      SampDeleteContext(v12);
      v12 = 0;
      HandleId = 0;
    }
    if ( v13 )
    {
      LocalFree(v13);
      v13 = 0;
      String = 0;
    }
    v15 = ++v35;
  }
  inited = SampGetUnicodeStringAttribute((struct _SAMP_OBJECT *)v12);
  if ( inited < 0 )
    goto LABEL_49;
  v26 = v45;
  inited = SampCopySid(&v42, *((void **)SampDefinedDomains + 170 * *((unsigned int *)v45 + 50) + 1));
  if ( inited >= 0 )
  {
    inited = SampDuplicateUnicodeString(
               (PUNICODE_STRING)v53,
               (PCUNICODE_STRING)SampDefinedDomains + 85 * *((unsigned int *)v26 + 50) + 1);
    if ( inited >= 0 )
    {
      v27 = *(struct _UNICODE_STRING *)v52;
      v28 = v48;
      *(_OWORD *)v52 = 0;
      --*v46;
      v29 = 0;
      *a7 = SidTypeUser;
      *v47 = v27;
      v30 = *(struct _UNICODE_STRING *)v53;
      *v28 = v42;
      *(_OWORD *)v53 = 0;
      *v49 = v30;
      goto LABEL_61;
    }
  }
  v34 = v42;
LABEL_49:
  v8 = a7;
LABEL_50:
  if ( v54[1] )
    LocalFree(v54[1]);
  if ( v55[1] )
    LocalFree(v55[1]);
  if ( v43 )
    LocalFree(v43);
  if ( !v11 )
  {
    *v8 = SidTypeUnknown;
    if ( (int)(inited + 0x80000000) < 0 || inited == -1073741724 )
      inited = -1073741772;
  }
LABEL_60:
  v29 = v34;
LABEL_61:
  if ( v12 )
    SampDeleteContext(v12);
  if ( v13 )
    LocalFree(v13);
  SampFreeUnicodeString(&SubKeyName);
  if ( v9 )
    LocalFree(v9);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Sid2 )
    LocalFree(Sid2);
  if ( v29 )
    LocalFree(v29);
  if ( v10 )
    LocalFree(v10);
  if ( v52[1] )
    LocalFree(v52[1]);
  if ( v53[1] )
    LocalFree(v53[1]);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      128,
      &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
      (unsigned int)inited,
      inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180053f9c  mov     [rsp-8+arg_8], rbx
0x180053fa1  push    rbp
0x180053fa2  push    rsi
0x180053fa3  push    rdi
0x180053fa4  push    r12
0x180053fa6  push    r13
0x180053fa8  push    r14
0x180053faa  push    r15
0x180053fac  lea     rbp, [rsp-90h]
0x180053fb4  sub     rsp, 190h
0x180053fbb  mov     rax, cs:__security_cookie
0x180053fc2  xor     rax, rsp
0x180053fc5  mov     [rbp+0C0h+var_38], rax
0x180053fcc  mov     rax, [rbp+0C0h+arg_28]
0x180053fd3  xorps   xmm0, xmm0
0x180053fd6  mov     r13, [rbp+0C0h+arg_30]
0x180053fdd  xorps   xmm1, xmm1
0x180053fe0  mov     [rbp+0C0h+var_108], rax
0x180053fe4  mov     rax, [rbp+0C0h+arg_38]
0x180053feb  mov     [rbp+0C0h+var_120], rcx
0x180053fef  mov     rcx, [rbp+0C0h+arg_20]
0x180053ff6  mov     [rbp+0C0h+var_118], rax
0x180053ffa  xor     eax, eax
0x180053ffc  movups  xmmword ptr [r9], xmm1
0x180054000  mov     [rbp+0C0h+Sid1], r8
0x180054004  mov     r14d, eax
0x180054007  mov     [rsp+1C0h+var_188], edx
0x18005400b  xor     r8d, r8d
0x18005400e  mov     [rbp+0C0h+var_100], rcx
0x180054012  lea     rdx, [rbp+0C0h+var_F8]
0x180054016  movups  xmmword ptr [rcx], xmm0
0x180054019  lea     ecx, [rax+4]
0x18005401c  mov     [rbp+0C0h+var_110], r9
0x180054020  mov     [rsp+1C0h+var_190], r13
0x180054025  mov     r15d, eax
0x180054028  movups  [rbp+0C0h+var_F8], xmm0
0x18005402c  mov     [rsp+1C0h+KeyHandle], rax
0x180054031  mov     sil, al
0x180054034  movups  xmmword ptr [rbp+0C0h+var_48.Data1], xmm1
0x180054038  mov     qword ptr [rbp+0C0h+Unused], rax
0x18005403c  mov     edi, eax
0x18005403e  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x180054042  mov     [rsp+1C0h+HandleId], rax
0x180054047  mov     r12d, eax
0x18005404a  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x18005404e  mov     [rsp+1C0h+Sid2], rax
0x180054053  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180054057  mov     [rbp+0C0h+var_130], rax
0x18005405b  movups  xmmword ptr [rbp+0C0h+hMem], xmm0
0x18005405f  mov     [rsp+1C0h+String], rax
0x180054064  movups  xmmword ptr [rbp+0C0h+var_88], xmm1
0x180054068  mov     [rsp+1C0h+var_180], rax
0x18005406d  mov     [rbp+0C0h+var_138], rax
0x180054071  movups  xmmword ptr [rsp+1C0h+SubKeyName.Length], xmm0
0x180054076  movups  xmmword ptr [rbp+0C0h+var_B8], xmm1
0x18005407a  movups  xmmword ptr [rbp+0C0h+var_A8], xmm0
0x18005407e  movups  xmmword ptr [rbp+0C0h+var_D8], xmm0
0x180054082  movups  xmmword ptr [rbp+0C0h+var_C8], xmm1
0x180054086  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x18005408b  mov     ebx, eax
0x18005408d  test    eax, eax
0x18005408f  js      loc_1800544FF
0x180054095  movzx   eax, cs:?SampNameDomainUsersNames@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampNameDomainUsersNames ...
0x18005409c  lea     r8, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x1800540a0  add     ax, cs:?SampBackSlash@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampBackSlash ...
0x1800540a7  lea     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x1800540ac  sub     word ptr [rbp+0C0h+var_F8], ax
0x1800540b0  xorps   xmm0, xmm0
0x1800540b3  mov     rax, cs:SampKey
0x1800540ba  xor     r9d, r9d; Unused
0x1800540bd  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], rax
0x1800540c1  mov     edx, 20019h; DesiredAccess
0x1800540c6  lea     rax, [rbp+0C0h+var_F8]
0x1800540ca  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x1800540d1  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rax
0x1800540d5  mov     [rbp+0C0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800540dc  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800540e1  call    cs:__imp_RtlpNtOpenKey
0x1800540e7  lea     rcx, [rbp+0C0h+var_F8]
0x1800540eb  mov     ebx, eax
0x1800540ed  call    SampFreeUnicodeString
0x1800540f2  test    ebx, ebx
0x1800540f4  js      loc_1800544FF
0x1800540fa  xor     r13d, r13d
0x1800540fd  lea     edx, [r12+20h]; unsigned __int16
0x180054102  lea     rcx, [rsp+1C0h+SubKeyName]; struct _UNICODE_STRING *
0x180054107  mov     [rsp+1C0h+var_178], r13d
0x18005410c  call    ?SampInitUnicodeString@@YAJPEAU_UNICODE_STRING@@G@Z; SampInitUnicodeString(_UNICODE_STRING *,ushort)
0x180054111  mov     ebx, eax
0x180054113  test    eax, eax
0x180054115  js      loc_1800544FA
0x18005411b  mov     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x180054120  lea     r9, [rbp+0C0h+Unused]; Unused
0x180054124  mov     r8d, r13d; Index
0x180054127  mov     [rbp+0C0h+var_E8], 1Bh
0x18005412e  lea     rdx, [rsp+1C0h+SubKeyName]; SubKeyName
0x180054133  mov     [rbp+0C0h+var_E4], 19h
0x18005413a  mov     [rbp+0C0h+var_E0], 1Dh
0x180054141  mov     [rbp+0C0h+var_DC], 28h ; '('
0x180054148  call    cs:__imp_RtlpNtEnumerateSubKey
0x18005414e  cmp     eax, 80000005h
0x180054153  jnz     short loc_18005418F
0x180054155  lea     rcx, [rsp+1C0h+SubKeyName]
0x18005415a  call    SampFreeUnicodeString
0x18005415f  movzx   edx, [rsp+1C0h+SubKeyName.Length]; unsigned __int16
0x180054164  lea     rcx, [rsp+1C0h+SubKeyName]; struct _UNICODE_STRING *
0x180054169  call    ?SampInitUnicodeString@@YAJPEAU_UNICODE_STRING@@G@Z; SampInitUnicodeString(_UNICODE_STRING *,ushort)
0x18005416e  mov     ebx, eax
0x180054170  test    eax, eax
0x180054172  js      loc_1800544FA
0x180054178  mov     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x18005417d  lea     r9, [rbp+0C0h+Unused]; Unused
0x180054181  mov     r8d, r13d; Index
0x180054184  lea     rdx, [rsp+1C0h+SubKeyName]; SubKeyName
0x180054189  call    cs:__imp_RtlpNtEnumerateSubKey
0x18005418f  test    eax, eax
0x180054191  js      loc_1800544E7
0x180054197  lea     rdx, [rsp+1C0h+String]
0x18005419c  lea     rcx, [rsp+1C0h+SubKeyName]
0x1800541a1  call    SampMakeNullTerminateString
0x1800541a6  mov     r12, [rsp+1C0h+String]
0x1800541ab  mov     ebx, eax
0x1800541ad  test    eax, eax
0x1800541af  js      loc_1800544FA
0x1800541b5  xor     edx, edx; EndPtr
0x1800541b7  mov     rcx, r12; String
0x1800541ba  lea     r8d, [rdx+10h]; Radix
0x1800541be  call    cs:__imp_wcstoul
0x1800541c4  mov     r13d, eax
0x1800541c7  mov     edi, 4
0x1800541cc  lea     rax, [rsp+1C0h+HandleId]
0x1800541d1  mov     edx, r13d
0x1800541d4  mov     ecx, edi
0x1800541d6  mov     [rsp+1C0h+var_198], rax
0x1800541db  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x1800541e0  mov     ebx, eax
0x1800541e2  test    eax, eax
0x1800541e4  js      loc_1800544E0
0x1800541ea  mov     r9d, edi
0x1800541ed  lea     r8, [rbp+0C0h+var_E8]
0x1800541f1  mov     rdi, [rsp+1C0h+HandleId]
0x1800541f6  xor     edx, edx
0x1800541f8  mov     rcx, rdi
0x1800541fb  call    SampReadExtendedAttributes
0x180054200  mov     ebx, eax
0x180054202  test    eax, eax
0x180054204  js      loc_1800544FA
0x18005420a  lea     r8, [rbp+0C0h+hMem]
0x18005420e  mov     edx, 1Dh
0x180054213  mov     rcx, rdi
0x180054216  call    SampGetExtendedAttribute
0x18005421b  mov     ebx, eax
0x18005421d  test    eax, eax
0x18005421f  js      loc_1800544FA
0x180054225  mov     r14, [rbp+0C0h+hMem+8]
0x180054229  test    r14, r14
0x18005422c  jz      loc_18005437D
0x180054232  mov     eax, [rsp+1C0h+var_188]
0x180054236  test    al, 80h
0x180054238  jz      short loc_1800542A4
0x18005423a  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180054241  lea     r8, [rsp+1C0h+Sid2]
0x180054246  mov     rax, [rbp+0C0h+var_120]
0x18005424a  mov     edx, r13d
0x18005424d  mov     eax, [rax+0C8h]
0x180054253  imul    r9, rax, 550h
0x18005425a  mov     rcx, [r9+rcx+8]; SourceSid
0x18005425f  call    SampCreateFullSid
0x180054264  mov     ebx, eax
0x180054266  test    eax, eax
0x180054268  js      loc_1800544FA
0x18005426e  mov     rbx, [rbp+0C0h+Sid1]
0x180054272  mov     rdx, [rsp+1C0h+Sid2]; Sid2
0x180054277  mov     rcx, rbx; Sid1
0x18005427a  call    cs:__imp_RtlEqualSid
0x180054280  mov     rcx, [rsp+1C0h+Sid2]; hMem
0x180054285  test    al, al
0x180054287  mov     eax, 1
0x18005428c  movzx   esi, sil
0x180054290  cmovnz  esi, eax
0x180054293  call    cs:__imp_LocalFree
0x180054299  mov     [rsp+1C0h+Sid2], 0
0x1800542a2  jmp     short loc_1800542A8
0x1800542a4  mov     rbx, [rbp+0C0h+Sid1]
0x1800542a8  mov     r13d, [rsp+1C0h+var_188]
0x1800542ad  bt      r13d, 0Fh
0x1800542b2  jnb     short loc_1800542C9
0x1800542b4  mov     rdx, r14; Sid2
0x1800542b7  mov     rcx, rbx; Sid1
0x1800542ba  call    cs:__imp_RtlEqualSid
0x1800542c0  test    al, al
0x1800542c2  jz      short loc_1800542C9
0x1800542c4  mov     sil, 1
0x1800542c7  jmp     short loc_1800542CE
0x1800542c9  test    sil, sil
0x1800542cc  jz      short loc_1800542E4
0x1800542ce  lea     rdx, [rbp+0C0h+var_130]; void **
0x1800542d2  mov     rcx, r14; Src
0x1800542d5  call    ?SampExtractInternetDomainSidFromSid@@YAJPEAXPEAPEAX@Z; SampExtractInternetDomainSidFromSid(void *,void * *)
0x1800542da  mov     ebx, eax
0x1800542dc  test    eax, eax
0x1800542de  js      loc_1800544FA
0x1800542e4  mov     rcx, r14; hMem
0x1800542e7  call    cs:__imp_LocalFree
0x1800542ed  xor     r14d, r14d
0x1800542f0  test    sil, sil
0x1800542f3  jz      loc_180054382
0x1800542f9  lea     r8, [rbp+0C0h+var_48]
0x1800542fd  mov     rcx, rdi
0x180054300  lea     edx, [r14+1Bh]
0x180054304  call    SampGetExtendedAttribute
0x180054309  mov     ebx, eax
0x18005430b  test    eax, eax
0x18005430d  js      loc_1800544FA
0x180054313  lea     rdx, [rbp+0C0h+var_B8]; struct _UNICODE_STRING *
0x180054317  lea     rcx, [rbp+0C0h+var_48]; struct _GUID *
0x18005431b  call    ?SampLookupInternetProviderNameByGUID@@YAJPEAU_GUID@@PEAU_UNICODE_STRING@@@Z; SampLookupInternetProviderNameByGUID(_GUID *,_UNICODE_STRING *)
0x180054320  mov     ebx, eax
0x180054322  test    eax, eax
0x180054324  js      loc_1800544FA
0x18005432a  lea     r8, [rbp+0C0h+var_A8]
0x18005432e  mov     rcx, rdi
0x180054331  lea     edx, [r14+19h]
0x180054335  call    SampGetExtendedAttribute
0x18005433a  mov     ebx, eax
0x18005433c  test    eax, eax
0x18005433e  js      loc_1800544FA
0x180054344  mov     rax, [rbp+0C0h+var_118]
0x180054348  mov     rcx, [rbp+0C0h+var_108]
0x18005434c  movups  xmm0, xmmword ptr [rbp+0C0h+var_B8]
0x180054350  dec     dword ptr [rax]
0x180054352  mov     rax, [rsp+1C0h+var_190]
0x180054357  movups  xmm1, xmmword ptr [rbp+0C0h+var_A8]
0x18005435b  mov     dword ptr [rax], 1
0x180054361  mov     rax, [rbp+0C0h+var_130]
0x180054365  mov     [rcx], rax
0x180054368  mov     rax, [rbp+0C0h+var_100]
0x18005436c  movdqu  xmmword ptr [rax], xmm0
0x180054370  mov     rax, [rbp+0C0h+var_110]
0x180054374  movdqu  xmmword ptr [rax], xmm1
0x180054378  jmp     loc_180054552
0x18005437d  mov     r13d, [rsp+1C0h+var_188]
0x180054382  lea     r8, [rbp+0C0h+var_88]
0x180054386  mov     edx, 28h ; '('
0x18005438b  mov     rcx, rdi
0x18005438e  call    SampGetExtendedAttribute
0x180054393  mov     ebx, eax
0x180054395  test    eax, eax
0x180054397  js      loc_1800544FA
0x18005439d  mov     r15, [rbp+0C0h+var_88+8]
0x1800543a1  test    r15, r15
0x1800543a4  jz      short loc_1800543E0
0x1800543a6  bt      r13d, 14h
0x1800543ab  jnb     short loc_1800543CA
0x1800543ad  mov     rcx, [rbp+0C0h+Sid1]; Sid1
0x1800543b1  mov     rdx, r15; Sid2
0x1800543b4  call    cs:__imp_RtlEqualSid
0x1800543ba  movzx   esi, sil
0x1800543be  mov     ebx, 1
0x1800543c3  test    al, al
0x1800543c5  cmovnz  esi, ebx
0x1800543c8  jmp     short loc_1800543CF
0x1800543ca  mov     ebx, 1
0x1800543cf  mov     rcx, r15; hMem
0x1800543d2  call    cs:__imp_LocalFree
0x1800543d8  xor     r15d, r15d
0x1800543db  test    sil, sil
0x1800543de  jnz     short loc_18005441C
0x1800543e0  test    rdi, rdi
0x1800543e3  jz      short loc_1800543F4
0x1800543e5  mov     rcx, rdi; HandleId
0x1800543e8  call    SampDeleteContext
0x1800543ed  xor     edi, edi
0x1800543ef  mov     [rsp+1C0h+HandleId], rdi
0x1800543f4  test    r12, r12
0x1800543f7  jz      short loc_18005440A
0x1800543f9  mov     rcx, r12; hMem
0x1800543fc  call    cs:__imp_LocalFree
0x180054402  xor     r12d, r12d
0x180054405  mov     [rsp+1C0h+String], r12
0x18005440a  mov     r13d, [rsp+1C0h+var_178]
0x18005440f  inc     r13d
0x180054412  mov     [rsp+1C0h+var_178], r13d
0x180054417  jmp     loc_18005411B
0x18005441c  lea     r9, [rbp+0C0h+var_D8]
0x180054420  mov     r8b, bl
0x180054423  mov     edx, ebx
0x180054425  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180054428  call    SampGetUnicodeStringAttribute
0x18005442d  mov     ebx, eax
0x18005442f  test    eax, eax
0x180054431  js      loc_1800544FA
0x180054437  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005443e  mov     r13, [rbp+0C0h+var_120]
0x180054442  mov     eax, [r13+0C8h]
0x180054449  imul    rcx, rax, 550h
0x180054450  mov     rdx, [rcx+rdx+8]; void *
0x180054455  lea     rcx, [rbp+0C0h+var_138]; void **
0x180054459  call    ?SampCopySid@@YAJPEAPEAXPEAX@Z; SampCopySid(void * *,void *)
0x18005445e  mov     ebx, eax
  ... truncated ...
```
