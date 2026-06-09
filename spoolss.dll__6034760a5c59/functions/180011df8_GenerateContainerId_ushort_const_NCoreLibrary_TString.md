# GenerateContainerId(ushort const *,NCoreLibrary::TString &)

- ea: `0x180011df8`
- end: `0x180011fe4`
- name: `?GenerateContainerId@@YAJPEBGAEAVTString@NCoreLibrary@@@Z`
- size: `492`
- prototype: `int(const unsigned __int16 *, struct NCoreLibrary::TString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800111f0`

## callees

- `0x180005320`
- `0x180005cac`
- `0x18000bb44`
- `0x180011c98`
- `0x180011df8`
- `0x180012344`
- `0x180014008`
- `0x180014080`
- `0x180014ce0`
- `0x180014d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f3b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011ec1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011e8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011eaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011e8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011fa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011fa1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180011f1e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180011f1e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011f31`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011f31`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GenerateContainerId(const unsigned __int16 *a1, const struct _GUID *a2)
{
  signed int v4; // edi
  WCHAR *v5; // rbx
  HANDLE CurrentThread; // rax
  void **v7; // r9
  NCoreLibrary::TString *v8; // rcx
  HANDLE v9; // rax
  struct NCoreLibrary::TString *v10; // rdx
  int v11; // eax
  signed int LastError; // eax
  __int64 v13; // rcx
  struct NCoreLibrary::TString *v14; // r8
  NCoreLibrary::TString *v15; // rcx
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  void *v21; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpAccountName; // [rsp+68h] [rbp-98h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Sid[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = 0;
  v24 = 0;
  v5 = (WCHAR *)&NCoreLibrary::TString::gszNullState;
  lpAccountName = (LPCWSTR)&NCoreLibrary::TString::gszNullState;
  v21 = &NCoreLibrary::TString::gszNullState;
  cbSid = 68;
  peUse = SidTypeUser;
  StringSid = 0;
  memset_0(ReferencedDomainName, 0, 0x208u);
  cchReferencedDomainName = 260;
  TokenHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    if ( SecurityHelper::OpenThreadToken(CurrentThread, 8u, &TokenHandle, v7) )
      goto LABEL_16;
  }
  else
  {
    v9 = GetCurrentThread();
    if ( !OpenThreadToken(v9, 8u, 1, &TokenHandle) )
      goto LABEL_16;
  }
  CloseHandle(TokenHandle);
  v11 = NUtilityLibrary::UserName((NUtilityLibrary *)&lpAccountName, v10);
  v5 = (WCHAR *)lpAccountName;
  v4 = v11;
  if ( v11 >= 0 )
  {
    if ( LookupAccountNameW(0, lpAccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse)
      && ConvertSidToStringSidW(Sid, &StringSid) )
    {
      goto LABEL_11;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_11:
      v4 = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v21, L"%s\\%s", a1, StringSid);
      if ( v4 >= 0 )
      {
        v4 = DafClass5GuidFromString(v13, v21, &v24);
        if ( v4 >= 0 )
          v4 = NCoreLibrary::ClsidToString((NCoreLibrary *)&v24, a2, v14);
      }
    }
  }
  v8 = (NCoreLibrary::TString *)StringSid;
  if ( StringSid )
    LocalFree(StringSid);
LABEL_16:
  NCoreLibrary::TString::vFree(v8, v21);
  NCoreLibrary::TString::vFree(v15, v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011df8  mov     [rsp-8+arg_10], rbx
0x180011dfd  mov     [rsp-8+arg_18], rsi
0x180011e02  push    rbp
0x180011e03  push    rdi
0x180011e04  push    r14
0x180011e06  lea     rbp, [rsp-1F0h]
0x180011e0e  sub     rsp, 2F0h
0x180011e15  mov     rax, cs:__security_cookie
0x180011e1c  xor     rax, rsp
0x180011e1f  mov     [rbp+200h+var_20], rax
0x180011e26  mov     rsi, rdx
0x180011e29  mov     r14, rcx
0x180011e2c  xor     edi, edi
0x180011e2e  xorps   xmm0, xmm0
0x180011e31  movups  [rsp+300h+var_290], xmm0
0x180011e36  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180011e3d  mov     [rsp+300h+lpAccountName], rbx
0x180011e42  mov     [rsp+300h+var_2A8], rbx
0x180011e47  mov     [rsp+300h+cbSid], 44h ; 'D'
0x180011e4f  mov     [rsp+300h+var_2B8], 1
0x180011e57  mov     [rsp+300h+StringSid], rdi
0x180011e5c  xor     edx, edx; Val
0x180011e5e  mov     r8d, 208h; Size
0x180011e64  lea     rcx, [rbp+200h+var_230]; void *
0x180011e68  call    memset_0
0x180011e6d  mov     [rsp+300h+var_2B4], 104h
0x180011e75  mov     [rsp+300h+TokenHandle], rdi
0x180011e7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180011e81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180011e86  test    al, al
0x180011e88  jz      short loc_180011EAA
0x180011e8a  call    cs:__imp_GetCurrentThread
0x180011e90  mov     rcx, rax; ThreadHandle
0x180011e93  lea     r8, [rsp+300h+TokenHandle]; TokenHandle
0x180011e98  lea     edx, [rdi+8]; DesiredAccess
0x180011e9b  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x180011ea0  test    eax, eax
0x180011ea2  jnz     loc_180011FA8
0x180011ea8  jmp     short loc_180011ECF
0x180011eaa  call    cs:__imp_GetCurrentThread
0x180011eb0  mov     rcx, rax; ThreadHandle
0x180011eb3  lea     r9, [rsp+300h+TokenHandle]; TokenHandle
0x180011eb8  mov     edx, 8; DesiredAccess
0x180011ebd  lea     r8d, [rdx-7]; OpenAsSelf
0x180011ec1  call    cs:__imp_OpenThreadToken
0x180011ec7  test    eax, eax
0x180011ec9  jz      loc_180011FA8
0x180011ecf  mov     rcx, [rsp+300h+TokenHandle]; hObject
0x180011ed4  call    cs:__imp_CloseHandle
0x180011eda  lea     rcx, [rsp+300h+lpAccountName]; this
0x180011edf  call    ?UserName@NUtilityLibrary@@YAJAEAVTString@NCoreLibrary@@@Z; NUtilityLibrary::UserName(NCoreLibrary::TString &)
0x180011ee4  test    eax, eax
0x180011ee6  mov     rbx, [rsp+300h+lpAccountName]
0x180011eeb  mov     edi, eax
0x180011eed  js      loc_180011F97
0x180011ef3  lea     rax, [rsp+300h+var_2B8]
0x180011ef8  mov     [rsp+300h+peUse], rax; peUse
0x180011efd  lea     rax, [rsp+300h+var_2B4]
0x180011f02  mov     [rsp+300h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180011f07  lea     rax, [rbp+200h+var_230]
0x180011f0b  mov     [rsp+300h+ReferencedDomainName], rax; ReferencedDomainName
0x180011f10  lea     r9, [rsp+300h+cbSid]; cbSid
0x180011f15  lea     r8, [rbp+200h+Sid]; Sid
0x180011f19  mov     rdx, rbx; lpAccountName
0x180011f1c  xor     ecx, ecx; lpSystemName
0x180011f1e  call    cs:__imp_LookupAccountNameW
0x180011f24  test    eax, eax
0x180011f26  jz      short loc_180011F3B
0x180011f28  lea     rdx, [rsp+300h+StringSid]; StringSid
0x180011f2d  lea     rcx, [rbp+200h+Sid]; Sid
0x180011f31  call    cs:__imp_ConvertSidToStringSidW
0x180011f37  test    eax, eax
0x180011f39  jnz     short loc_180011F54
0x180011f3b  call    cs:__imp_GetLastError
0x180011f41  mov     edi, eax
0x180011f43  test    eax, eax
0x180011f45  jle     short loc_180011F50
0x180011f47  movzx   edi, ax
0x180011f4a  or      edi, 80070000h
0x180011f50  test    edi, edi
0x180011f52  js      short loc_180011F97
0x180011f54  mov     r9, [rsp+300h+StringSid]
0x180011f59  mov     r8, r14
0x180011f5c  lea     rdx, aSS; "%s\\%s"
0x180011f63  lea     rcx, [rsp+300h+var_2A8]; this
0x180011f68  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180011f6d  test    eax, eax
0x180011f6f  mov     edi, eax
0x180011f71  js      short loc_180011F97
0x180011f73  lea     r8, [rsp+300h+var_290]
0x180011f78  mov     rdx, [rsp+300h+var_2A8]
0x180011f7d  call    DafClass5GuidFromString
0x180011f82  test    eax, eax
0x180011f84  mov     edi, eax
0x180011f86  js      short loc_180011F97
0x180011f88  mov     rdx, rsi; struct _GUID *
0x180011f8b  lea     rcx, [rsp+300h+var_290]; this
0x180011f90  call    ?ClsidToString@NCoreLibrary@@YAJAEBU_GUID@@AEAVTString@1@@Z; NCoreLibrary::ClsidToString(_GUID const &,NCoreLibrary::TString &)
0x180011f95  mov     edi, eax
0x180011f97  mov     rcx, [rsp+300h+StringSid]; hMem
0x180011f9c  test    rcx, rcx
0x180011f9f  jz      short loc_180011FA8
0x180011fa1  call    cs:__imp_LocalFree
0x180011fa7  nop
0x180011fa8  mov     rdx, [rsp+300h+var_2A8]; void *
0x180011fad  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180011fb2  nop
0x180011fb3  mov     rdx, rbx; void *
0x180011fb6  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180011fbb  mov     eax, edi
0x180011fbd  mov     rcx, [rbp+200h+var_20]
0x180011fc4  xor     rcx, rsp; StackCookie
0x180011fc7  call    __security_check_cookie
0x180011fcc  lea     r11, [rsp+300h+var_10]
0x180011fd4  mov     rbx, [r11+30h]
0x180011fd8  mov     rsi, [r11+38h]
0x180011fdc  mov     rsp, r11
0x180011fdf  pop     r14
0x180011fe1  pop     rdi
0x180011fe2  pop     rbp
0x180011fe3  retn
```
