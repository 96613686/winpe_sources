# AccountManagerUtils::HideUserAccountFromLogonUI(ushort const *,uchar)

- ea: `0x1800dd888`
- end: `0x1800ddc09`
- name: `?HideUserAccountFromLogonUI@AccountManagerUtils@@YAJPEBGE@Z`
- size: `897`
- prototype: `__int64 __fastcall(PCWSTR SourceString, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d7da4`

## callees

- `0x1800088e8`
- `0x180014e7c`
- `0x180041fc0`
- `0x18004bf50`
- `0x180054670`
- `0x18006f1c9`
- `0x1800da9c4`
- `0x1800dc7c4`
- `0x1800dc824`
- `0x1800dd888`
- `0x1800de450`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800dda36`
- `ntdll!RtlInitUnicodeString` at `0x1800dda36`
- `SAMLIB!SamSetInformationUser` at `0x1800ddb6d`
- `SAMLIB!SamSetInformationUser` at `0x1800ddb6d`
- `SAMLIB!SamConnect` at `0x1800dd9a3`
- `SAMLIB!SamConnect` at `0x1800dd9a3`
- `SAMLIB!SamOpenUser` at `0x1800ddb0c`
- `SAMLIB!SamOpenUser` at `0x1800ddb0c`
- `SAMLIB!SamOpenDomain` at `0x1800dd9f4`
- `SAMLIB!SamOpenDomain` at `0x1800dd9f4`
- `SAMLIB!SamFreeMemory` at `0x1800ddacc`
- `SAMLIB!SamFreeMemory` at `0x1800ddae5`
- `SAMLIB!SamFreeMemory` at `0x1800ddb9a`
- `SAMLIB!SamFreeMemory` at `0x1800ddbaf`
- `SAMLIB!SamFreeMemory` at `0x1800ddacc`
- `SAMLIB!SamFreeMemory` at `0x1800ddae5`
- `SAMLIB!SamFreeMemory` at `0x1800ddb9a`
- `SAMLIB!SamFreeMemory` at `0x1800ddbaf`
- `SAMLIB!SamLookupNamesInDomain` at `0x1800dda83`
- `SAMLIB!SamLookupNamesInDomain` at `0x1800dda83`

## string_xrefs

- `0x1800dd915`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd94e`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd9ba`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dda0b`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800ddaac`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800ddb1e`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AccountManagerUtils::HideUserAccountFromLogonUI(PCWSTR SourceString, const unsigned __int16 *a2)
{
  PLSA_UNICODE_STRING v3; // rcx
  NTSTATUS v4; // eax
  POLICY_INFORMATION_CLASS v5; // edx
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // ebx
  bool v11; // zf
  unsigned int *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rcx
  unsigned int *v17; // rcx
  int v19; // [rsp+20h] [rbp-E0h]
  unsigned int *v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  unsigned int **v28; // [rsp+98h] [rbp-68h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h] BYREF
  char v30; // [rsp+A8h] [rbp-58h]
  __int64 *v31; // [rsp+B0h] [rbp-50h] BYREF
  int v32[2]; // [rsp+B8h] [rbp-48h] BYREF
  char v33; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v35[10]; // [rsp+E0h] [rbp-20h] BYREF
  char v36; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  PolicyHandle = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &PolicyHandle,
    0);
  v4 = LsaOpenPolicy(v3, &ObjectAttributes, 1u, &PolicyHandle);
  v6 = v4 | 0x10000000;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)v6,
      v19);
    goto LABEL_28;
  }
  Buffer = 0;
  v7 = LsaQueryInformationPolicy(PolicyHandle, v5, &Buffer);
  v6 = v7 | 0x10000000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)v6,
      v19);
LABEL_5:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Buffer);
    goto LABEL_28;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v24 = 0;
  v8 = SamConnect(0, &v24, 32, &ObjectAttributes);
  v6 = v8 | 0x10000000;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)v6,
      v19);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
    goto LABEL_5;
  }
  v23 = 0;
  v9 = SamOpenDomain(v24, 0x2000000, *((_QWORD *)Buffer + 2), &v23);
  v6 = v9 | 0x10000000;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)v6,
      v19);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
    goto LABEL_8;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v20 = 0;
  v21 = 0;
  v31 = &v21;
  *(_QWORD *)v32 = 0;
  v33 = 1;
  v28 = &v20;
  v29 = 0;
  v30 = 1;
  v10 = SamLookupNamesInDomain(v23, 1, &DestinationString, &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>(&v28);
  wil::details::out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>(&v31);
  v6 = v10 | 0x10000000;
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)v6,
      (int)v32);
LABEL_14:
    v11 = v21 == 0;
    v21 = 0;
    if ( !v11 )
      SamFreeMemory();
    v12 = v20;
    v20 = 0;
    if ( v12 )
      SamFreeMemory();
    goto LABEL_11;
  }
  v25 = 0;
  v13 = SamOpenUser(v23, 0x2000000, *v20, &v25);
  v6 = v13 | 0x10000000;
  if ( v13 < 0 )
  {
    v14 = 139;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
      (const char *)v6,
      (int)v32);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
    goto LABEL_14;
  }
  memset_0(v35, 0, 0xA8u);
  v35[0] = 0x4000;
  v36 = 1;
  v15 = SamSetInformationUser(v25, 28, v35);
  v6 = v15 | 0x10000000;
  if ( v15 < 0 )
  {
    v14 = 144;
    goto LABEL_20;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
  v16 = v21;
  v21 = 0;
  if ( v16 )
    SamFreeMemory();
  v17 = v20;
  v20 = 0;
  if ( v17 )
    SamFreeMemory();
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Buffer);
  v6 = 0;
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v6;
}

```

## disassembly

```asm
0x1800dd888  mov     [rsp-8+arg_8], rbx
0x1800dd88d  mov     [rsp-8+arg_10], rsi
0x1800dd892  push    rbp
0x1800dd893  push    rdi
0x1800dd894  push    r14
0x1800dd896  lea     rbp, [rsp-0A0h]
0x1800dd89e  sub     rsp, 1A0h
0x1800dd8a5  mov     rax, cs:__security_cookie
0x1800dd8ac  xor     rax, rsp
0x1800dd8af  mov     [rbp+0B0h+var_20], rax
0x1800dd8b6  mov     rdi, rcx
0x1800dd8b9  xor     esi, esi
0x1800dd8bb  mov     qword ptr [rsp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x1800dd8c4  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], rsi
0x1800dd8c8  mov     [rsp+1B0h+ObjectAttributes.RootDirectory], rsi
0x1800dd8cd  mov     [rsp+1B0h+ObjectAttributes.ObjectName], rsi
0x1800dd8d2  xorps   xmm0, xmm0
0x1800dd8d5  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800dd8da  mov     [rsp+1B0h+PolicyHandle], rsi
0x1800dd8df  xor     edx, edx
0x1800dd8e1  lea     rcx, [rsp+1B0h+PolicyHandle]
0x1800dd8e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800dd8eb  lea     r9, [rsp+1B0h+PolicyHandle]; PolicyHandle
0x1800dd8f0  lea     r8d, [rsi+1]; DesiredAccess
0x1800dd8f4  lea     rdx, [rsp+1B0h+ObjectAttributes]; ObjectAttributes
0x1800dd8f9  call    LsaOpenPolicy
0x1800dd8fe  mov     ebx, eax
0x1800dd900  mov     r14d, 10000000h
0x1800dd906  or      ebx, r14d
0x1800dd909  jge     short loc_1800DD929
0x1800dd90b  mov     rcx, [rbp+0B8h]; this
0x1800dd912  mov     r9d, ebx; char *
0x1800dd915  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd91c  lea     edx, [rsi+76h]; void *
0x1800dd91f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd924  jmp     loc_1800DDBD6
0x1800dd929  mov     [rsp+1B0h+Buffer], rsi
0x1800dd92e  lea     r8, [rsp+1B0h+Buffer]; Buffer
0x1800dd933  mov     rcx, [rsp+1B0h+PolicyHandle]; PolicyHandle
0x1800dd938  call    LsaQueryInformationPolicy
0x1800dd93d  mov     ebx, eax
0x1800dd93f  or      ebx, r14d
0x1800dd942  jge     short loc_1800DD96F
0x1800dd944  mov     rcx, [rbp+0B8h]; this
0x1800dd94b  mov     r9d, ebx; char *
0x1800dd94e  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd955  mov     edx, 79h ; 'y'; void *
0x1800dd95a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd95f  nop
0x1800dd960  lea     rcx, [rsp+1B0h+Buffer]
0x1800dd965  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800dd96a  jmp     loc_1800DDBD6
0x1800dd96f  mov     [rsp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x1800dd977  mov     [rsp+1B0h+ObjectAttributes.RootDirectory], rsi
0x1800dd97c  mov     [rbp+0B0h+ObjectAttributes.Attributes], esi
0x1800dd97f  mov     [rsp+1B0h+ObjectAttributes.ObjectName], rsi
0x1800dd984  xorps   xmm0, xmm0
0x1800dd987  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800dd98c  mov     [rsp+1B0h+var_160], rsi
0x1800dd991  lea     r9, [rsp+1B0h+ObjectAttributes]
0x1800dd996  mov     r8d, 20h ; ' '
0x1800dd99c  lea     rdx, [rsp+1B0h+var_160]
0x1800dd9a1  xor     ecx, ecx
0x1800dd9a3  call    cs:__imp_SamConnect
0x1800dd9a9  mov     ebx, eax
0x1800dd9ab  or      ebx, r14d
0x1800dd9ae  jge     short loc_1800DD9D7
0x1800dd9b0  mov     rcx, [rbp+0B8h]; this
0x1800dd9b7  mov     r9d, ebx; char *
0x1800dd9ba  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd9c1  mov     edx, 7Dh ; '}'; void *
0x1800dd9c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd9cb  lea     rcx, [rsp+1B0h+var_160]
0x1800dd9d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800dd9d5  jmp     short loc_1800DD960
0x1800dd9d7  mov     [rsp+1B0h+var_168], rsi
0x1800dd9dc  lea     r9, [rsp+1B0h+var_168]
0x1800dd9e1  mov     r8, [rsp+1B0h+Buffer]
0x1800dd9e6  mov     r8, [r8+10h]
0x1800dd9ea  mov     edx, 2000000h
0x1800dd9ef  mov     rcx, [rsp+1B0h+var_160]
0x1800dd9f4  call    cs:__imp_SamOpenDomain
0x1800dd9fa  mov     ebx, eax
0x1800dd9fc  or      ebx, r14d
0x1800dd9ff  jge     short loc_1800DDA28
0x1800dda01  mov     rcx, [rbp+0B8h]; this
0x1800dda08  mov     r9d, ebx; char *
0x1800dda0b  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dda12  mov     edx, 81h; void *
0x1800dda17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dda1c  lea     rcx, [rsp+1B0h+var_168]
0x1800dda21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800dda26  jmp     short loc_1800DD9CB
0x1800dda28  xorps   xmm0, xmm0
0x1800dda2b  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x1800dda2f  mov     rdx, rdi; SourceString
0x1800dda32  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x1800dda36  call    cs:__imp_RtlInitUnicodeString
0x1800dda3c  mov     [rsp+1B0h+var_180], rsi
0x1800dda41  mov     [rsp+1B0h+var_178], rsi
0x1800dda46  lea     rax, [rsp+1B0h+var_178]
0x1800dda4b  mov     [rbp+0B0h+var_100], rax
0x1800dda4f  mov     qword ptr [rbp+0B0h+var_F8], rsi
0x1800dda53  mov     [rbp+0B0h+var_F0], 1
0x1800dda57  lea     rax, [rsp+1B0h+var_180]
0x1800dda5c  mov     [rbp+0B0h+var_118], rax
0x1800dda60  mov     [rbp+0B0h+var_110], rsi
0x1800dda64  mov     [rbp+0B0h+var_108], 1
0x1800dda68  lea     rax, [rbp+0B0h+var_F8]
0x1800dda6c  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x1800dda71  lea     r9, [rbp+0B0h+var_110]
0x1800dda75  lea     r8, [rbp+0B0h+DestinationString]
0x1800dda79  mov     edx, 1
0x1800dda7e  mov     rcx, [rsp+1B0h+var_168]
0x1800dda83  call    cs:__imp_SamLookupNamesInDomain
0x1800dda89  mov     ebx, eax
0x1800dda8b  lea     rcx, [rbp+0B0h+var_118]
0x1800dda8f  call    ??1?$out_param_t@V?$unique_ptr@KU?$function_deleter@P6AJPEAX@Z$1?SamFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>(void)
0x1800dda94  lea     rcx, [rbp+0B0h+var_100]
0x1800dda98  call    ??1?$out_param_t@V?$unique_ptr@KU?$function_deleter@P6AJPEAX@Z$1?SamFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>(void)
0x1800dda9d  or      ebx, r14d
0x1800ddaa0  jns     short loc_1800DDAF0
0x1800ddaa2  mov     rcx, [rbp+0B8h]; this
0x1800ddaa9  mov     r9d, ebx; char *
0x1800ddaac  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800ddab3  mov     edx, 88h; void *
0x1800ddab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddabd  mov     rcx, [rsp+1B0h+var_178]
0x1800ddac2  test    rcx, rcx
0x1800ddac5  mov     [rsp+1B0h+var_178], rsi
0x1800ddaca  jz      short loc_1800DDAD2
0x1800ddacc  call    cs:__imp_SamFreeMemory
0x1800ddad2  mov     rcx, [rsp+1B0h+var_180]
0x1800ddad7  mov     [rsp+1B0h+var_180], rsi
0x1800ddadc  test    rcx, rcx
0x1800ddadf  jz      loc_1800DDA1C
0x1800ddae5  call    cs:__imp_SamFreeMemory
0x1800ddaeb  jmp     loc_1800DDA1C
0x1800ddaf0  mov     [rsp+1B0h+var_158], rsi
0x1800ddaf5  lea     r9, [rsp+1B0h+var_158]
0x1800ddafa  mov     r8, [rsp+1B0h+var_180]
0x1800ddaff  mov     r8d, [r8]
0x1800ddb02  mov     edx, 2000000h
0x1800ddb07  mov     rcx, [rsp+1B0h+var_168]
0x1800ddb0c  call    cs:__imp_SamOpenUser
0x1800ddb12  mov     ebx, eax
0x1800ddb14  or      ebx, r14d
0x1800ddb17  jge     short loc_1800DDB43
0x1800ddb19  mov     edx, 8Bh; void *
0x1800ddb1e  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800ddb25  mov     r9d, ebx; char *
0x1800ddb28  mov     rcx, [rbp+0B8h]; this
0x1800ddb2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddb34  lea     rcx, [rsp+1B0h+var_158]
0x1800ddb39  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ddb3e  jmp     loc_1800DDABD
0x1800ddb43  xor     edx, edx; Val
0x1800ddb45  mov     r8d, 0A8h; Size
0x1800ddb4b  lea     rcx, [rbp+0B0h+var_D0]; void *
0x1800ddb4f  call    memset_0
0x1800ddb54  mov     [rbp+0B0h+var_D0], 4000h
0x1800ddb5b  mov     [rbp+0B0h+var_A8], 1
0x1800ddb5f  lea     r8, [rbp+0B0h+var_D0]
0x1800ddb63  mov     edx, 1Ch
0x1800ddb68  mov     rcx, [rsp+1B0h+var_158]
0x1800ddb6d  call    cs:__imp_SamSetInformationUser
0x1800ddb73  mov     ebx, eax
0x1800ddb75  or      ebx, r14d
0x1800ddb78  jge     short loc_1800DDB81
0x1800ddb7a  mov     edx, 90h
0x1800ddb7f  jmp     short loc_1800DDB1E
0x1800ddb81  lea     rcx, [rsp+1B0h+var_158]
0x1800ddb86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ddb8b  mov     rcx, [rsp+1B0h+var_178]
0x1800ddb90  mov     [rsp+1B0h+var_178], rsi
0x1800ddb95  test    rcx, rcx
0x1800ddb98  jz      short loc_1800DDBA0
0x1800ddb9a  call    cs:__imp_SamFreeMemory
0x1800ddba0  mov     rcx, [rsp+1B0h+var_180]
0x1800ddba5  mov     [rsp+1B0h+var_180], rsi
0x1800ddbaa  test    rcx, rcx
0x1800ddbad  jz      short loc_1800DDBB5
0x1800ddbaf  call    cs:__imp_SamFreeMemory
0x1800ddbb5  lea     rcx, [rsp+1B0h+var_168]
0x1800ddbba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ddbbf  lea     rcx, [rsp+1B0h+var_160]
0x1800ddbc4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ddbc9  nop
0x1800ddbca  lea     rcx, [rsp+1B0h+Buffer]
0x1800ddbcf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ddbd4  mov     ebx, esi
0x1800ddbd6  lea     rcx, [rsp+1B0h+PolicyHandle]
0x1800ddbdb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ddbe0  mov     eax, ebx
0x1800ddbe2  mov     rcx, [rbp+0B0h+var_20]
0x1800ddbe9  xor     rcx, rsp; StackCookie
0x1800ddbec  call    __security_check_cookie
0x1800ddbf1  lea     r11, [rsp+1B0h+var_10]
0x1800ddbf9  mov     rbx, [r11+28h]
0x1800ddbfd  mov     rsi, [r11+30h]
0x1800ddc01  mov     rsp, r11
0x1800ddc04  pop     r14
0x1800ddc06  pop     rdi
0x1800ddc07  pop     rbp
0x1800ddc08  retn
```
