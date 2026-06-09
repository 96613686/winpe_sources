# RQueryUserServiceName

- ea: `0x140035aa0`
- end: `0x140035ebd`
- name: `RQueryUserServiceName`
- size: `1053`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, wchar_t *String2@<rdx>, LPCWSTR StringSid@<r8>, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140005824`
- `0x140006f20`
- `0x1400070d0`
- `0x140007130`
- `0x140008b90`
- `0x140011ba0`
- `0x140017160`
- `0x14001f99c`
- `0x140021ef4`
- `0x140030a5c`
- `0x140035aa0`
- `0x1400575b0`
- `0x14005b040`
- `0x140092060`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035dfb`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x140035b2b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x140035b2b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140035d92`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140035d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140035e18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140035e18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140035e42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140035e61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140035e42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140035e61`
- `ntdll!RtlFreeHeap` at `0x140035dac`
- `ntdll!RtlFreeHeap` at `0x140035de4`
- `ntdll!RtlFreeHeap` at `0x140035dac`
- `ntdll!RtlFreeHeap` at `0x140035de4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140035c47`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140035c47`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x140035ced`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x140035ced`

## pseudocode

```c
__int64 __fastcall RQueryUserServiceName(
        void *a1,
        wchar_t *String2,
        LPCWSTR StringSid,
        unsigned int a4,
        unsigned __int16 **a5)
{
  unsigned __int16 *v7; // r15
  PVOID v8; // rdi
  unsigned int v11; // eax
  DWORD NamedServiceRecord; // ebx
  struct CServiceRecord *v13; // rbx
  __int64 v14; // rcx
  DWORD UserServicesBySessionIdAndTemplate; // eax
  _QWORD *i; // rbx
  __int64 *v17; // r12
  __int64 v18; // rax
  int v19; // esi
  unsigned int TokenInformation; // eax
  PVOID v21; // rdi
  BOOL v22; // esi
  unsigned __int16 *v23; // rax
  unsigned __int16 v24; // ax
  PVOID P; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v28; // [rsp+40h] [rbp-C0h]
  struct CServiceRecord *v29; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v31; // [rsp+58h] [rbp-A8h]
  _QWORD v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD RpcCallAttributes[32]; // [rsp+80h] [rbp-80h] BYREF

  v31 = a5;
  Sid = 0;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  hObject = 0;
  P = 0;
  v28 = 0;
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v32);
  memset(&RpcCallAttributes[2], 0, 0x70u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 32;
  v11 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  NamedServiceRecord = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 105, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, v11);
    goto LABEL_49;
  }
  if ( RpcCallAttributes[15] != 1 )
  {
    NamedServiceRecord = 5;
    goto LABEL_49;
  }
  if ( !(unsigned int)ScIsValidScManagerHandle(a1) )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 106, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
    NamedServiceRecord = 6;
    goto LABEL_49;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 107, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
    NamedServiceRecord = 50;
    goto LABEL_49;
  }
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v29);
  NamedServiceRecord = ScGetNamedServiceRecord(String2, &v29);
  if ( NamedServiceRecord )
    goto LABEL_49;
  v13 = v29;
  if ( (*((_DWORD *)v29 + 13) & 0x100000) == 0 )
  {
    NamedServiceRecord = 87;
    goto LABEL_49;
  }
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    NamedServiceRecord = GetLastError();
    goto LABEL_49;
  }
  UserServicesBySessionIdAndTemplate = CServiceDatabase::GetUserServicesBySessionIdAndTemplate(v14, v32, a4, v13);
  NamedServiceRecord = UserServicesBySessionIdAndTemplate;
  if ( UserServicesBySessionIdAndTemplate )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_dS(
        WPP_GLOBAL_Control->StubInfo,
        108,
        (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
        UserServicesBySessionIdAndTemplate,
        (__int64)String2);
    goto LABEL_55;
  }
  for ( i = (_QWORD *)v32[0]; ; i = (_QWORD *)*i )
  {
    if ( i == v32 )
    {
      NamedServiceRecord = 1060;
      goto LABEL_49;
    }
    v17 = (__int64 *)i[2];
    v18 = (*(__int64 (__fastcall **)(__int64 *))(*v17 + 80))(v17);
    v19 = UMgrQueryUserToken(v18, &hObject);
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_dS(
          WPP_GLOBAL_Control->StubInfo,
          109,
          (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
          v19,
          v17[7]);
      v28 = v19;
      goto LABEL_39;
    }
    TokenInformation = ScGetTokenInformation(hObject, TokenUser, &P);
    if ( !TokenInformation )
      break;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        110,
        (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
        v17[7],
        TokenInformation);
    v8 = P;
LABEL_39:
    if ( v8 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
      v8 = 0;
      P = 0;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
  }
  v21 = P;
  v22 = EqualSid(*(PSID *)P, Sid);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
  v8 = 0;
  P = 0;
  CloseHandle(hObject);
  hObject = 0;
  if ( !v22 )
    goto LABEL_39;
  v23 = (unsigned __int16 *)LocalAlloc(0x40u, 0x200u);
  v7 = v23;
  if ( v23 )
  {
    v24 = StringCchCopyW(v23, 0x100u, (const unsigned __int16 *)v17[7]);
    NamedServiceRecord = v24;
    if ( !v24 )
      goto LABEL_49;
    LocalFree(v7);
    v7 = 0;
  }
  NamedServiceRecord = 14;
LABEL_49:
  if ( Sid )
    LocalFree(Sid);
  if ( NamedServiceRecord == 1060 && v28 )
    NamedServiceRecord = v28;
  *v31 = v7;
LABEL_55:
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear((__int64)v32);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v29);
  return NamedServiceRecord;
}

```

## disassembly

```asm
0x140035aa0  mov     [rsp-8+arg_0], rbx
0x140035aa5  push    rbp
0x140035aa6  push    rsi
0x140035aa7  push    rdi
0x140035aa8  push    r12
0x140035aaa  push    r13
0x140035aac  push    r14
0x140035aae  push    r15
0x140035ab0  lea     rbp, [rsp-10h]
0x140035ab5  sub     rsp, 110h
0x140035abc  mov     rax, cs:__security_cookie
0x140035ac3  xor     rax, rsp
0x140035ac6  mov     [rbp+40h+var_40], rax
0x140035aca  mov     rax, [rbp+40h+arg_20]
0x140035ace  mov     r14, rcx
0x140035ad1  mov     [rsp+140h+var_E8], rax
0x140035ad6  lea     rcx, [rsp+140h+var_E0]
0x140035adb  xor     eax, eax
0x140035add  mov     r13d, r9d
0x140035ae0  mov     [rsp+140h+Sid], rax
0x140035ae5  mov     r15d, eax
0x140035ae8  mov     [rsp+140h+var_F8], rax
0x140035aed  mov     edi, eax
0x140035aef  mov     [rsp+140h+hObject], rax
0x140035af4  mov     r12, r8
0x140035af7  mov     [rsp+140h+P], rax
0x140035afc  mov     rsi, rdx
0x140035aff  mov     [rsp+140h+var_100], eax
0x140035b03  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x140035b08  xor     edx, edx; Val
0x140035b0a  lea     r8d, [rdi+70h]; Size
0x140035b0e  lea     rcx, [rbp+40h+var_B8]; void *
0x140035b12  call    memset
0x140035b17  lea     rdx, [rbp+40h+RpcCallAttributes]; RpcCallAttributes
0x140035b1b  mov     [rbp+40h+RpcCallAttributes], 3
0x140035b22  xor     ecx, ecx; ClientBinding
0x140035b24  mov     [rbp+40h+var_BC], 20h ; ' '
0x140035b2b  call    cs:__imp_RpcServerInqCallAttributesW
0x140035b31  mov     ebx, eax
0x140035b33  test    eax, eax
0x140035b35  jz      short loc_140035B73
0x140035b37  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b3e  lea     r14, WPP_GLOBAL_Control
0x140035b45  cmp     rcx, r14
0x140035b48  jz      loc_140035E57
0x140035b4e  test    byte ptr [rcx+1Ch], 1
0x140035b52  jz      loc_140035E57
0x140035b58  mov     rcx, [rcx+10h]
0x140035b5c  lea     edx, [rdi+69h]
0x140035b5f  mov     r9d, eax
0x140035b62  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140035b69  call    WPP_SF_d
0x140035b6e  jmp     loc_140035E57
0x140035b73  cmp     [rbp+40h+var_84], 1
0x140035b77  jz      short loc_140035B83
0x140035b79  mov     ebx, 5
0x140035b7e  jmp     loc_140035E57
0x140035b83  mov     rcx, r14; void *
0x140035b86  call    ?ScIsValidScManagerHandle@@YAHPEAX@Z; ScIsValidScManagerHandle(void *)
0x140035b8b  test    eax, eax
0x140035b8d  jnz     short loc_140035BC5
0x140035b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b96  lea     r14, WPP_GLOBAL_Control
0x140035b9d  cmp     rcx, r14
0x140035ba0  jz      short loc_140035BBB
0x140035ba2  test    byte ptr [rcx+1Ch], 1
0x140035ba6  jz      short loc_140035BBB
0x140035ba8  mov     rcx, [rcx+10h]
0x140035bac  lea     edx, [rax+6Ah]
0x140035baf  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140035bb6  call    WPP_SF_
0x140035bbb  mov     ebx, 6
0x140035bc0  jmp     loc_140035E57
0x140035bc5  call    IsUMgrQueryUserContextPresent
0x140035bca  test    al, al
0x140035bcc  jnz     short loc_140035C06
0x140035bce  mov     rcx, cs:WPP_GLOBAL_Control
0x140035bd5  lea     r14, WPP_GLOBAL_Control
0x140035bdc  cmp     rcx, r14
0x140035bdf  jz      short loc_140035BFC
0x140035be1  test    byte ptr [rcx+1Ch], 1
0x140035be5  jz      short loc_140035BFC
0x140035be7  mov     rcx, [rcx+10h]
0x140035beb  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140035bf2  mov     edx, 6Bh ; 'k'
0x140035bf7  call    WPP_SF_
0x140035bfc  mov     ebx, 32h ; '2'
0x140035c01  jmp     loc_140035E57
0x140035c06  lea     rcx, [rsp+140h+var_F8]
0x140035c0b  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140035c10  lea     rdx, [rsp+140h+var_F8]; struct CServiceRecord **
0x140035c15  mov     rcx, rsi; String2
0x140035c18  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x140035c1d  mov     ebx, eax
0x140035c1f  test    eax, eax
0x140035c21  jnz     loc_140035E57
0x140035c27  mov     rbx, [rsp+140h+var_F8]
0x140035c2c  mov     eax, [rbx+34h]
0x140035c2f  bt      eax, 14h
0x140035c33  jb      short loc_140035C3F
0x140035c35  mov     ebx, 57h ; 'W'
0x140035c3a  jmp     loc_140035E57
0x140035c3f  lea     rdx, [rsp+140h+Sid]; Sid
0x140035c44  mov     rcx, r12; StringSid
0x140035c47  call    cs:__imp_ConvertStringSidToSidW
0x140035c4d  test    eax, eax
0x140035c4f  jnz     short loc_140035C5E
0x140035c51  call    cs:__imp_GetLastError
0x140035c57  mov     ebx, eax
0x140035c59  jmp     loc_140035E57
0x140035c5e  mov     r9, rbx
0x140035c61  lea     rdx, [rsp+140h+var_E0]
0x140035c66  mov     r8d, r13d
0x140035c69  call    ?GetUserServicesBySessionIdAndTemplate@CServiceDatabase@@QEAAKAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@KPEAVCServiceRecord@@@Z; CServiceDatabase::GetUserServicesBySessionIdAndTemplate(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &,ulong,CServiceRecord *)
0x140035c6e  mov     ebx, eax
0x140035c70  test    eax, eax
0x140035c72  jz      short loc_140035CB7
0x140035c74  mov     rcx, cs:WPP_GLOBAL_Control
0x140035c7b  lea     r14, WPP_GLOBAL_Control
0x140035c82  cmp     rcx, r14
0x140035c85  jz      loc_140035E80
0x140035c8b  test    byte ptr [rcx+1Ch], 1
0x140035c8f  jz      loc_140035E80
0x140035c95  mov     rcx, [rcx+10h]
0x140035c99  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140035ca0  mov     edx, 6Ch ; 'l'
0x140035ca5  mov     [rsp+140h+var_120], rsi
0x140035caa  mov     r9d, eax
0x140035cad  call    WPP_SF_dS
0x140035cb2  jmp     loc_140035E80
0x140035cb7  mov     rbx, [rsp+140h+var_E0]
0x140035cbc  lea     r14, WPP_GLOBAL_Control
0x140035cc3  lea     rax, [rsp+140h+var_E0]
0x140035cc8  cmp     rbx, rax
0x140035ccb  jz      loc_140035E52
0x140035cd1  mov     r12, [rbx+10h]
0x140035cd5  mov     rcx, r12
0x140035cd8  mov     rax, [r12]
0x140035cdc  mov     rax, [rax+50h]
0x140035ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035ce5  mov     rcx, rax
0x140035ce8  lea     rdx, [rsp+140h+hObject]
0x140035ced  call    cs:__imp_UMgrQueryUserToken
0x140035cf3  mov     esi, eax
0x140035cf5  test    eax, eax
0x140035cf7  jns     short loc_140035D36
0x140035cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140035d00  cmp     rcx, r14
0x140035d03  jz      short loc_140035D2D
0x140035d05  test    byte ptr [rcx+1Ch], 1
0x140035d09  jz      short loc_140035D2D
0x140035d0b  mov     rax, [r12+38h]
0x140035d10  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140035d17  mov     rcx, [rcx+10h]
0x140035d1b  mov     edx, 6Dh ; 'm'
0x140035d20  mov     r9d, esi
0x140035d23  mov     [rsp+140h+var_120], rax
0x140035d28  call    WPP_SF_dS
0x140035d2d  mov     [rsp+140h+var_100], esi
0x140035d31  jmp     loc_140035DCD
0x140035d36  mov     rcx, [rsp+140h+hObject]; TokenHandle
0x140035d3b  lea     r8, [rsp+140h+P]; void **
0x140035d40  mov     edx, 1; TokenInformationClass
0x140035d45  call    ?ScGetTokenInformation@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; ScGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x140035d4a  test    eax, eax
0x140035d4c  jz      short loc_140035D85
0x140035d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140035d55  cmp     rcx, r14
0x140035d58  jz      short loc_140035D7E
0x140035d5a  test    byte ptr [rcx+1Ch], 1
0x140035d5e  jz      short loc_140035D7E
0x140035d60  mov     r9, [r12+38h]
0x140035d65  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140035d6c  mov     rcx, [rcx+10h]
0x140035d70  mov     edx, 6Eh ; 'n'
0x140035d75  mov     dword ptr [rsp+140h+var_120], eax
0x140035d79  call    WPP_SF_Sd
0x140035d7e  mov     rdi, [rsp+140h+P]
0x140035d83  jmp     short loc_140035DCD
0x140035d85  mov     rdi, [rsp+140h+P]
0x140035d8a  mov     rdx, [rsp+140h+Sid]; pSid2
0x140035d8f  mov     rcx, [rdi]; pSid1
0x140035d92  call    cs:__imp_EqualSid
0x140035d98  mov     rcx, gs:60h
0x140035da1  mov     r8, rdi; P
0x140035da4  xor     edx, edx; Flags
0x140035da6  mov     esi, eax
0x140035da8  mov     rcx, [rcx+30h]; HeapHandle
0x140035dac  call    cs:__imp_RtlFreeHeap
0x140035db2  mov     rcx, [rsp+140h+hObject]; hObject
0x140035db7  xor     edi, edi
0x140035db9  mov     [rsp+140h+P], rdi
0x140035dbe  call    cs:__imp_CloseHandle
0x140035dc4  mov     [rsp+140h+hObject], rdi
0x140035dc9  test    esi, esi
0x140035dcb  jnz     short loc_140035E0E
0x140035dcd  test    rdi, rdi
0x140035dd0  jz      short loc_140035DF1
0x140035dd2  mov     rcx, gs:60h
0x140035ddb  mov     r8, rdi; P
0x140035dde  xor     edx, edx; Flags
0x140035de0  mov     rcx, [rcx+30h]; HeapHandle
0x140035de4  call    cs:__imp_RtlFreeHeap
0x140035dea  xor     edi, edi
0x140035dec  mov     [rsp+140h+P], rdi
0x140035df1  mov     rcx, [rsp+140h+hObject]; hObject
0x140035df6  test    rcx, rcx
0x140035df9  jz      short loc_140035E06
0x140035dfb  call    cs:__imp_CloseHandle
0x140035e01  mov     [rsp+140h+hObject], r15
0x140035e06  mov     rbx, [rbx]
0x140035e09  jmp     loc_140035CC3
0x140035e0e  mov     edx, 200h; uBytes
0x140035e13  mov     ecx, 40h ; '@'; uFlags
0x140035e18  call    cs:__imp_LocalAlloc
0x140035e1e  mov     r15, rax
0x140035e21  test    rax, rax
0x140035e24  jz      short loc_140035E4B
0x140035e26  mov     r8, [r12+38h]; unsigned __int16 *
0x140035e2b  mov     edx, 100h; unsigned __int64
0x140035e30  mov     rcx, rax; unsigned __int16 *
0x140035e33  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140035e38  movzx   ebx, ax
0x140035e3b  test    ebx, ebx
0x140035e3d  jz      short loc_140035E57
0x140035e3f  mov     rcx, r15; hMem
0x140035e42  call    cs:__imp_LocalFree
0x140035e48  xor     r15d, r15d
0x140035e4b  mov     ebx, 0Eh
0x140035e50  jmp     short loc_140035E57
0x140035e52  mov     ebx, 424h
0x140035e57  mov     rcx, [rsp+140h+Sid]; hMem
0x140035e5c  test    rcx, rcx
0x140035e5f  jz      short loc_140035E67
0x140035e61  call    cs:__imp_LocalFree
0x140035e67  cmp     ebx, 424h
0x140035e6d  jnz     short loc_140035E78
0x140035e6f  mov     eax, [rsp+140h+var_100]
0x140035e73  test    eax, eax
0x140035e75  cmovnz  ebx, eax
0x140035e78  mov     rax, [rsp+140h+var_E8]
0x140035e7d  mov     [rax], r15
0x140035e80  lea     rcx, [rsp+140h+var_E0]
0x140035e85  call    ?clear@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAAXXZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear(void)
0x140035e8a  lea     rcx, [rsp+140h+var_F8]
0x140035e8f  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140035e94  mov     eax, ebx
0x140035e96  mov     rcx, [rbp+40h+var_40]
0x140035e9a  xor     rcx, rsp; StackCookie
0x140035e9d  call    __security_check_cookie
0x140035ea2  mov     rbx, [rsp+140h+arg_0]
0x140035eaa  add     rsp, 110h
0x140035eb1  pop     r15
0x140035eb3  pop     r14
0x140035eb5  pop     r13
0x140035eb7  pop     r12
0x140035eb9  pop     rdi
0x140035eba  pop     rsi
0x140035ebb  pop     rbp
0x140035ebc  retn
```
