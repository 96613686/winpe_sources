# GenerateContainerId(ushort const *,NCoreLibrary::TString &)

- ea: `0x180013528`
- end: `0x180013745`
- name: `?GenerateContainerId@@YAJPEBGAEAVTString@NCoreLibrary@@@Z`
- size: `541`
- prototype: `int(const unsigned __int16 *, struct NCoreLibrary::TString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001285c`

## callees

- `0x180005680`
- `0x18000601c`
- `0x18000c4c0`
- `0x1800133bc`
- `0x180013528`
- `0x180013acc`
- `0x1800158e4`
- `0x180015970`
- `0x1800166d4`
- `0x180016704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001368f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001368f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800135fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800135fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800135ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800135e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800135ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800135e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013616`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136fb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180013666`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180013666`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001367f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001367f`

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
0x180013528  mov     [rsp-8+arg_10], rbx
0x18001352d  mov     [rsp-8+arg_18], rsi
0x180013532  push    rbp
0x180013533  push    rdi
0x180013534  push    r14
0x180013536  lea     rbp, [rsp-1F0h]
0x18001353e  sub     rsp, 2F0h
0x180013545  mov     rax, cs:__security_cookie
0x18001354c  xor     rax, rsp
0x18001354f  mov     [rbp+200h+var_20], rax
0x180013556  mov     rsi, rdx
0x180013559  mov     r14, rcx
0x18001355c  xor     edi, edi
0x18001355e  xorps   xmm0, xmm0
0x180013561  movups  [rsp+300h+var_290], xmm0
0x180013566  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18001356d  mov     [rsp+300h+lpAccountName], rbx
0x180013572  mov     [rsp+300h+var_2A8], rbx
0x180013577  mov     [rsp+300h+cbSid], 44h ; 'D'
0x18001357f  mov     [rsp+300h+var_2B8], 1
0x180013587  mov     [rsp+300h+StringSid], rdi
0x18001358c  xor     edx, edx; Val
0x18001358e  mov     r8d, 208h; Size
0x180013594  lea     rcx, [rbp+200h+var_230]; void *
0x180013598  call    memset_0
0x18001359d  mov     [rsp+300h+var_2B4], 104h
0x1800135a5  mov     [rsp+300h+TokenHandle], rdi
0x1800135aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800135b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800135b6  test    al, al
0x1800135b8  jz      short loc_1800135E0
0x1800135ba  call    cs:__imp_GetCurrentThread
0x1800135c1  nop     dword ptr [rax+rax+00h]
0x1800135c6  mov     rcx, rax; ThreadHandle
0x1800135c9  lea     r8, [rsp+300h+TokenHandle]; TokenHandle
0x1800135ce  lea     edx, [rdi+8]; DesiredAccess
0x1800135d1  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x1800135d6  test    eax, eax
0x1800135d8  jnz     loc_180013708
0x1800135de  jmp     short loc_180013611
0x1800135e0  call    cs:__imp_GetCurrentThread
0x1800135e7  nop     dword ptr [rax+rax+00h]
0x1800135ec  mov     rcx, rax; ThreadHandle
0x1800135ef  lea     r9, [rsp+300h+TokenHandle]; TokenHandle
0x1800135f4  mov     edx, 8; DesiredAccess
0x1800135f9  lea     r8d, [rdx-7]; OpenAsSelf
0x1800135fd  call    cs:__imp_OpenThreadToken
0x180013604  nop     dword ptr [rax+rax+00h]
0x180013609  test    eax, eax
0x18001360b  jz      loc_180013708
0x180013611  mov     rcx, [rsp+300h+TokenHandle]; hObject
0x180013616  call    cs:__imp_CloseHandle
0x18001361d  nop     dword ptr [rax+rax+00h]
0x180013622  lea     rcx, [rsp+300h+lpAccountName]; this
0x180013627  call    ?UserName@NUtilityLibrary@@YAJAEAVTString@NCoreLibrary@@@Z; NUtilityLibrary::UserName(NCoreLibrary::TString &)
0x18001362c  test    eax, eax
0x18001362e  mov     rbx, [rsp+300h+lpAccountName]
0x180013633  mov     edi, eax
0x180013635  js      loc_1800136F1
0x18001363b  lea     rax, [rsp+300h+var_2B8]
0x180013640  mov     [rsp+300h+peUse], rax; peUse
0x180013645  lea     rax, [rsp+300h+var_2B4]
0x18001364a  mov     [rsp+300h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001364f  lea     rax, [rbp+200h+var_230]
0x180013653  mov     [rsp+300h+ReferencedDomainName], rax; ReferencedDomainName
0x180013658  lea     r9, [rsp+300h+cbSid]; cbSid
0x18001365d  lea     r8, [rbp+200h+Sid]; Sid
0x180013661  mov     rdx, rbx; lpAccountName
0x180013664  xor     ecx, ecx; lpSystemName
0x180013666  call    cs:__imp_LookupAccountNameW
0x18001366d  nop     dword ptr [rax+rax+00h]
0x180013672  test    eax, eax
0x180013674  jz      short loc_18001368F
0x180013676  lea     rdx, [rsp+300h+StringSid]; StringSid
0x18001367b  lea     rcx, [rbp+200h+Sid]; Sid
0x18001367f  call    cs:__imp_ConvertSidToStringSidW
0x180013686  nop     dword ptr [rax+rax+00h]
0x18001368b  test    eax, eax
0x18001368d  jnz     short loc_1800136AE
0x18001368f  call    cs:__imp_GetLastError
0x180013696  nop     dword ptr [rax+rax+00h]
0x18001369b  mov     edi, eax
0x18001369d  test    eax, eax
0x18001369f  jle     short loc_1800136AA
0x1800136a1  movzx   edi, ax
0x1800136a4  or      edi, 80070000h
0x1800136aa  test    edi, edi
0x1800136ac  js      short loc_1800136F1
0x1800136ae  mov     r9, [rsp+300h+StringSid]
0x1800136b3  mov     r8, r14
0x1800136b6  lea     rdx, aSS; "%s\\%s"
0x1800136bd  lea     rcx, [rsp+300h+var_2A8]; this
0x1800136c2  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x1800136c7  test    eax, eax
0x1800136c9  mov     edi, eax
0x1800136cb  js      short loc_1800136F1
0x1800136cd  lea     r8, [rsp+300h+var_290]
0x1800136d2  mov     rdx, [rsp+300h+var_2A8]
0x1800136d7  call    DafClass5GuidFromString
0x1800136dc  test    eax, eax
0x1800136de  mov     edi, eax
0x1800136e0  js      short loc_1800136F1
0x1800136e2  mov     rdx, rsi; struct _GUID *
0x1800136e5  lea     rcx, [rsp+300h+var_290]; this
0x1800136ea  call    ?ClsidToString@NCoreLibrary@@YAJAEBU_GUID@@AEAVTString@1@@Z; NCoreLibrary::ClsidToString(_GUID const &,NCoreLibrary::TString &)
0x1800136ef  mov     edi, eax
0x1800136f1  mov     rcx, [rsp+300h+StringSid]; hMem
0x1800136f6  test    rcx, rcx
0x1800136f9  jz      short loc_180013708
0x1800136fb  call    cs:__imp_LocalFree
0x180013702  nop     dword ptr [rax+rax+00h]
0x180013707  nop
0x180013708  mov     rdx, [rsp+300h+var_2A8]; void *
0x18001370d  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180013712  nop
0x180013713  mov     rdx, rbx; void *
0x180013716  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18001371b  mov     eax, edi
0x18001371d  mov     rcx, [rbp+200h+var_20]
0x180013724  xor     rcx, rsp; StackCookie
0x180013727  call    __security_check_cookie
0x18001372c  lea     r11, [rsp+300h+var_10]
0x180013734  mov     rbx, [r11+30h]
0x180013738  mov     rsi, [r11+38h]
0x18001373c  mov     rsp, r11
0x18001373f  pop     r14
0x180013741  pop     rdi
0x180013742  pop     rbp
0x180013743  retn
```
