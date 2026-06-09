# CClassData::AdjustActivationToken(void *,ulong,unsigned __int64,_GUID const *,bool,bool,bool,bool,bool,bool,DESKTOP_APPX_LAUNCH_CONTEXT const *,void * *)

- ea: `0x18008fbec`
- end: `0x180090075`
- name: `?AdjustActivationToken@CClassData@@AEBAJPEAXK_KPEBU_GUID@@_N33333PEBUDESKTOP_APPX_LAUNCH_CONTEXT@@PEAPEAX@Z`
- size: `1161`
- prototype: `__int64 __usercall@<rax>(CClassData *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, const struct _GUID *, bool, bool, bool, bool, bool, bool, const struct DESKTOP_APPX_LAUNCH_CONTEXT *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e578`

## callees

- `0x18000b100`
- `0x180024590`
- `0x18004e554`
- `0x180051334`
- `0x180051378`
- `0x180051484`
- `0x1800516c0`
- `0x18008fbec`
- `0x180093f20`
- `0x180095c0c`
- `0x1800a3d1c`
- `0x1800a7b84`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800b969c`
- `0x180102e28`
- `0x18010547c`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18008fe49`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18008fe49`
- `ntdll!RtlInitUnicodeString` at `0x18008fe0f`
- `ntdll!RtlInitUnicodeString` at `0x18008fe0f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008fe94`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008fe94`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x18008ff68`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x180090057`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x18008ff68`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x180090057`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18008fdb8`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18008fdb8`

## string_xrefs

- `0x18008fe65`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18008ff84`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18008fdfe`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall CClassData::AdjustActivationToken(
        CClassData *this,
        void *a2,
        char a3,
        __int64 a4,
        const struct _GUID *a5,
        bool a6,
        bool a7,
        bool a8,
        bool a9,
        bool a10,
        bool a11,
        const struct DESKTOP_APPX_LAUNCH_CONTEXT *a12,
        void **a13)
{
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // ebx
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // esi
  const unsigned __int16 *v22; // rax
  unsigned int ApplicationCapabilities; // ebx
  int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // ebx
  int v27; // ebx
  const unsigned __int16 *v28; // rax
  int v29; // eax
  const unsigned __int16 *v30; // r8
  __int64 v31; // rdx
  unsigned int v33; // ebx
  const unsigned __int16 *v34; // rax
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v38; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  const struct _GUID *v41; // [rsp+90h] [rbp-70h]
  void *v42; // [rsp+98h] [rbp-68h]
  _BYTE pSid2[80]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[80]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v42 = a2;
  v40 = a4;
  *a13 = 0;
  v41 = a5;
  TokenHandle = a12;
  if ( !(unsigned int)CClassData::HasActivateAsPackage(this) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
  if ( !(unsigned __int8)IsPsmCreateBrokerTokenPresent() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16);
  if ( (a3 & 8) != 0 || (v17 = 1, a6) && !v40 )
    v17 = 3;
  if ( !(unsigned int)CClassData::GetRuntimeBehavior(this) && CClassData::GetAppTrustLevel(this) == PartialTrust )
    v17 |= 0x800u;
  if ( (unsigned int)CClassData::GetRuntimeBehavior(this) == 1 && CClassData::GetAppTrustLevel(this) == PartialTrust
    || (unsigned int)CClassData::GetRuntimeBehavior(this) == 3 && CClassData::GetAppTrustLevel(this) == BaseTrust )
  {
    if ( CClassData::GetAppTrustLevel(this) == PartialTrust )
    {
      v17 |= 4u;
    }
    else if ( (unsigned int)CClassData::GetRuntimeBehavior(this) == 3 )
    {
      v17 |= 0x40000u;
    }
    if ( !v40 )
      v17 |= 0x10000000u;
    v18 = v17 | 0x8000;
    if ( !a7 )
      v18 = v17;
    v17 = v18;
    if ( a8 )
      v17 = v18 | 0x20000;
  }
  v37 = 0;
  v19 = v17 | 0x2000;
  v38 = 0;
  LODWORD(DestinationString.Buffer) = 0;
  if ( !a9 )
    v19 = v17;
  BYTE4(DestinationString.Buffer) = 1;
  v20 = v19 | 0x80000;
  if ( !a10 )
    v20 = v19;
  *(_QWORD *)&DestinationString.Length = &v37;
  v21 = v20 | 0x40000000;
  if ( !a5 )
    v21 = v20;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v37);
  v22 = CClassData::ExecutionPackageName(this);
  v35 = 0;
  ApplicationCapabilities = QueryApplicationCapabilitiesEx(v22, 0, 0, 0);
  if ( BYTE4(DestinationString.Buffer) )
    *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 8LL) = LODWORD(DestinationString.Buffer);
  if ( (int)(ApplicationCapabilities + 0x80000000) < 0 || ApplicationCapabilities == -2147024444 )
  {
    if ( v38 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"Microsoft.appCategory.chatAgent_8wekyb3d8bbwe");
      memset_0(pSid2, 0, 0x44u);
      memset_0(v44, 0, 0x44u);
      v24 = RtlDeriveCapabilitySidsFromName(&DestinationString, v44, pSid2);
      if ( v24 < 0 )
      {
        v25 = 2345;
LABEL_39:
        ApplicationCapabilities = wil::details::in1diag3::Return_NtStatus(
                                    retaddr,
                                    (void *)v25,
                                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                                    (const char *)(unsigned int)v24,
                                    v35);
        goto LABEL_58;
      }
      v26 = 0;
      if ( v38 )
      {
        while ( !EqualSid(*(PSID *)(v37 + 8LL * v26), pSid2) )
        {
          if ( ++v26 >= v38 )
            goto LABEL_45;
        }
        v21 |= 0x1000u;
      }
    }
LABEL_45:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl)
      && a11
      && (unsigned int)CClassData::GetRuntimeBehavior(this) )
    {
      v21 |= 0x200000u;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::GetImpl'::`2'::impl) )
    {
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      v27 = (unsigned int)CClassData::AppUserModelID(this);
      v28 = CClassData::ExecutionPackageName(this);
      v29 = PsmAdjustActivationTokenEx2(v42, v21, *((unsigned int *)this + 33), v28);
      if ( v29 < 0 )
      {
        v31 = 2403;
LABEL_52:
        ApplicationCapabilities = wil::details::in1diag3::Return_NtStatus(
                                    retaddr,
                                    (void *)v31,
                                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                                    (const char *)(unsigned int)v29,
                                    v27);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        goto LABEL_58;
      }
      if ( a11 )
      {
        v29 = CiPolicyAdjustToken(TokenHandle, 0, v30);
        if ( v29 < 0 )
        {
          v31 = 2408;
          goto LABEL_52;
        }
      }
      *a13 = TokenHandle;
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    else
    {
      v33 = (unsigned int)CClassData::AppUserModelID(this);
      v34 = CClassData::ExecutionPackageName(this);
      v35 = v33;
      v24 = PsmAdjustActivationTokenEx2(v42, v21, *((unsigned int *)this + 33), v34);
      if ( v24 < 0 )
      {
        v25 = 2417;
        goto LABEL_39;
      }
    }
    ApplicationCapabilities = 0;
  }
LABEL_58:
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v37);
  return ApplicationCapabilities;
}

```

## disassembly

```asm
0x18008fbec  mov     [rsp-8+arg_10], rbx
0x18008fbf1  push    rbp
0x18008fbf2  push    rsi
0x18008fbf3  push    rdi
0x18008fbf4  push    r12
0x18008fbf6  push    r13
0x18008fbf8  push    r14
0x18008fbfa  push    r15
0x18008fbfc  lea     rbp, [rsp-50h]
0x18008fc01  sub     rsp, 150h
0x18008fc08  mov     rax, cs:__security_cookie
0x18008fc0f  xor     rax, rsp
0x18008fc12  mov     [rbp+80h+var_40], rax
0x18008fc16  mov     rax, [rbp+80h+arg_58]
0x18008fc1d  xor     r15d, r15d
0x18008fc20  mov     r13, [rbp+80h+arg_60]
0x18008fc27  mov     ebx, r8d
0x18008fc2a  mov     r14, [rbp+80h+arg_20]
0x18008fc31  mov     rdi, rcx
0x18008fc34  mov     [rbp+80h+var_E8], rdx
0x18008fc38  mov     [rbp+80h+var_F8], r9
0x18008fc3c  mov     [r13+0], r15
0x18008fc40  mov     [rbp+80h+var_F0], r14
0x18008fc44  mov     [rsp+180h+TokenHandle], rax
0x18008fc49  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18008fc4e  test    eax, eax
0x18008fc50  jnz     short loc_18008FC57
0x18008fc52  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008fc57  call    IsPsmCreateBrokerTokenPresent
0x18008fc5c  test    al, al
0x18008fc5e  jnz     short loc_18008FC65
0x18008fc60  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008fc65  mov     esi, 1
0x18008fc6a  test    bl, 8
0x18008fc6d  jnz     short loc_18008FC84
0x18008fc6f  lea     r12, [rbp+80h+var_F8]
0x18008fc73  mov     ebx, esi
0x18008fc75  cmp     [rbp+80h+arg_28], r15b
0x18008fc7c  jz      short loc_18008FC8C
0x18008fc7e  cmp     [rbp+80h+var_F8], r15
0x18008fc82  jnz     short loc_18008FC8C
0x18008fc84  mov     ebx, 3
0x18008fc89  mov     r12, r15
0x18008fc8c  mov     rcx, rdi
0x18008fc8f  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18008fc94  test    eax, eax
0x18008fc96  jnz     short loc_18008FCA8
0x18008fc98  mov     rcx, rdi; this
0x18008fc9b  call    ?GetAppTrustLevel@CClassData@@QEBA?AW4TrustLevel@AppModel@@XZ; CClassData::GetAppTrustLevel(void)
0x18008fca0  cmp     eax, esi
0x18008fca2  jnz     short loc_18008FCA8
0x18008fca4  bts     ebx, 0Bh
0x18008fca8  mov     rcx, rdi
0x18008fcab  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18008fcb0  cmp     eax, esi
0x18008fcb2  jnz     short loc_18008FCC0
0x18008fcb4  mov     rcx, rdi; this
0x18008fcb7  call    ?GetAppTrustLevel@CClassData@@QEBA?AW4TrustLevel@AppModel@@XZ; CClassData::GetAppTrustLevel(void)
0x18008fcbc  cmp     eax, esi
0x18008fcbe  jz      short loc_18008FCD9
0x18008fcc0  mov     rcx, rdi
0x18008fcc3  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18008fcc8  cmp     eax, 3
0x18008fccb  jnz     short loc_18008FD27
0x18008fccd  mov     rcx, rdi; this
0x18008fcd0  call    ?GetAppTrustLevel@CClassData@@QEBA?AW4TrustLevel@AppModel@@XZ; CClassData::GetAppTrustLevel(void)
0x18008fcd5  test    eax, eax
0x18008fcd7  jnz     short loc_18008FD27
0x18008fcd9  mov     rcx, rdi; this
0x18008fcdc  call    ?GetAppTrustLevel@CClassData@@QEBA?AW4TrustLevel@AppModel@@XZ; CClassData::GetAppTrustLevel(void)
0x18008fce1  cmp     eax, esi
0x18008fce3  jnz     short loc_18008FCEA
0x18008fce5  or      ebx, 4
0x18008fce8  jmp     short loc_18008FCFB
0x18008fcea  mov     rcx, rdi
0x18008fced  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18008fcf2  cmp     eax, 3
0x18008fcf5  jnz     short loc_18008FCFB
0x18008fcf7  bts     ebx, 12h
0x18008fcfb  cmp     [rbp+80h+var_F8], r15
0x18008fcff  jnz     short loc_18008FD08
0x18008fd01  mov     r12, r15
0x18008fd04  bts     ebx, 1Ch
0x18008fd08  mov     eax, ebx
0x18008fd0a  bts     eax, 0Fh
0x18008fd0e  cmp     [rbp+80h+arg_30], r15b
0x18008fd15  cmovz   eax, ebx
0x18008fd18  mov     ebx, eax
0x18008fd1a  cmp     [rbp+80h+arg_38], r15b
0x18008fd21  jz      short loc_18008FD27
0x18008fd23  bts     ebx, 11h
0x18008fd27  mov     eax, ebx
0x18008fd29  mov     [rsp+180h+var_118], r15
0x18008fd2e  bts     eax, 0Dh
0x18008fd32  mov     [rsp+180h+var_110], r15
0x18008fd37  cmp     [rbp+80h+arg_40], r15b
0x18008fd3e  mov     dword ptr [rbp+80h+DestinationString.Buffer], r15d
0x18008fd42  cmovz   eax, ebx
0x18008fd45  mov     byte ptr [rbp+80h+DestinationString.Buffer+4], 1
0x18008fd49  mov     ecx, eax
0x18008fd4b  bts     ecx, 13h
0x18008fd4f  cmp     [rbp+80h+arg_48], r15b
0x18008fd56  cmovz   ecx, eax
0x18008fd59  lea     rax, [rsp+180h+var_118]
0x18008fd5e  mov     esi, ecx
0x18008fd60  mov     qword ptr [rsp+180h+DestinationString.Length], rax
0x18008fd65  bts     esi, 1Eh
0x18008fd69  test    r14, r14
0x18008fd6c  cmovz   esi, ecx
0x18008fd6f  lea     rcx, [rsp+180h+var_118]
0x18008fd74  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18008fd79  mov     rcx, rdi; this
0x18008fd7c  call    ?ExecutionPackageName@CClassData@@QEBAPEBGXZ; CClassData::ExecutionPackageName(void)
0x18008fd81  mov     [rsp+180h+var_130], r15
0x18008fd86  lea     rcx, [rbp+80h+DestinationString.Buffer]
0x18008fd8a  mov     [rsp+180h+var_138], r15
0x18008fd8f  xor     r9d, r9d
0x18008fd92  mov     [rsp+180h+var_140], r15
0x18008fd97  xor     r8d, r8d
0x18008fd9a  mov     [rsp+180h+var_148], r15
0x18008fd9f  xor     edx, edx
0x18008fda1  mov     [rsp+180h+var_150], rcx
0x18008fda6  lea     rcx, [rsp+180h+var_118]
0x18008fdab  mov     [rsp+180h+var_158], rcx
0x18008fdb0  mov     rcx, rax
0x18008fdb3  mov     qword ptr [rsp+180h+var_160], r15; int
0x18008fdb8  call    cs:__imp_QueryApplicationCapabilitiesEx
0x18008fdbf  nop     dword ptr [rax+rax+00h]
0x18008fdc4  mov     ebx, eax
0x18008fdc6  cmp     byte ptr [rbp+80h+DestinationString.Buffer+4], r15b
0x18008fdca  jz      short loc_18008FDD8
0x18008fdcc  mov     rcx, qword ptr [rsp+180h+DestinationString.Length]
0x18008fdd1  mov     edx, dword ptr [rbp+80h+DestinationString.Buffer]
0x18008fdd4  mov     [rcx+8], rdx
0x18008fdd8  mov     eax, 80000000h
0x18008fddd  lea     ecx, [rbx+rax]
0x18008fde0  test    eax, ecx
0x18008fde2  jnz     short loc_18008FDF0
0x18008fde4  cmp     ebx, 800701C4h
0x18008fdea  jnz     loc_18008FFDB
0x18008fdf0  cmp     [rsp+180h+var_110], r15
0x18008fdf5  jbe     loc_18008FEB5
0x18008fdfb  xorps   xmm0, xmm0
0x18008fdfe  lea     rdx, aMicrosoftAppca; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x18008fe05  lea     rcx, [rsp+180h+DestinationString]; DestinationString
0x18008fe0a  movups  xmmword ptr [rsp+180h+DestinationString.Length], xmm0
0x18008fe0f  call    cs:__imp_RtlInitUnicodeString
0x18008fe16  nop     dword ptr [rax+rax+00h]
0x18008fe1b  mov     ebx, 44h ; 'D'
0x18008fe20  lea     rcx, [rbp+80h+pSid2]; void *
0x18008fe24  mov     r8d, ebx; Size
0x18008fe27  xor     edx, edx; Val
0x18008fe29  call    memset_0
0x18008fe2e  mov     r8d, ebx; Size
0x18008fe31  lea     rcx, [rbp+80h+var_90]; void *
0x18008fe35  xor     edx, edx; Val
0x18008fe37  call    memset_0
0x18008fe3c  lea     r8, [rbp+80h+pSid2]
0x18008fe40  lea     rdx, [rbp+80h+var_90]
0x18008fe44  lea     rcx, [rsp+180h+DestinationString]
0x18008fe49  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18008fe50  nop     dword ptr [rax+rax+00h]
0x18008fe55  test    eax, eax
0x18008fe57  jns     short loc_18008FE7B
0x18008fe59  mov     edx, 929h; void *
0x18008fe5e  mov     rcx, [rbp+88h]; this
0x18008fe65  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18008fe6c  mov     r9d, eax; char *
0x18008fe6f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008fe74  mov     ebx, eax
0x18008fe76  jmp     loc_18008FFDB
0x18008fe7b  mov     ebx, r15d
0x18008fe7e  cmp     [rsp+180h+var_110], r15
0x18008fe83  jbe     short loc_18008FEB5
0x18008fe85  mov     rcx, [rsp+180h+var_118]
0x18008fe8a  lea     rdx, [rbp+80h+pSid2]; pSid2
0x18008fe8e  mov     eax, ebx
0x18008fe90  mov     rcx, [rcx+rax*8]; pSid1
0x18008fe94  call    cs:__imp_EqualSid
0x18008fe9b  nop     dword ptr [rax+rax+00h]
0x18008fea0  test    eax, eax
0x18008fea2  jnz     short loc_18008FEB1
0x18008fea4  inc     ebx
0x18008fea6  mov     eax, ebx
0x18008fea8  cmp     rax, [rsp+180h+var_110]
0x18008fead  jb      short loc_18008FE85
0x18008feaf  jmp     short loc_18008FEB5
0x18008feb1  bts     esi, 0Ch
0x18008feb5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x18008febc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x18008fec1  mov     r15b, [rbp+80h+arg_50]
0x18008fec8  test    al, al
0x18008feca  jz      short loc_18008FEE1
0x18008fecc  test    r15b, r15b
0x18008fecf  jz      short loc_18008FEE1
0x18008fed1  mov     rcx, rdi
0x18008fed4  call    ?GetRuntimeBehavior@CClassData@@QEBA?AW4RuntimeBehavior@AppModel@@XZ; CClassData::GetRuntimeBehavior(void)
0x18008fed9  test    eax, eax
0x18008fedb  jz      short loc_18008FEE1
0x18008fedd  bts     esi, 15h
0x18008fee1  mov     rax, [rsp+180h+TokenHandle]
0x18008fee6  xor     r14d, r14d
0x18008fee9  test    rax, rax
0x18008feec  jz      short loc_18008FEF2
0x18008feee  mov     r14, [rax+38h]
0x18008fef2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchCiClaim@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchCiClaim@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchCiClaim> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::GetImpl(void)'::`2'::impl
0x18008fef9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchCiClaim@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::__private_IsEnabled(void)
0x18008fefe  test    al, al
0x18008ff00  jz      loc_18009000F
0x18008ff06  xor     edx, edx
0x18008ff08  mov     [rsp+180h+TokenHandle], 0
0x18008ff11  lea     rcx, [rsp+180h+TokenHandle]
0x18008ff16  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008ff1b  mov     rcx, rdi; this
0x18008ff1e  call    ?AppUserModelID@CClassData@@QEBAPEBGXZ; CClassData::AppUserModelID(void)
0x18008ff23  mov     rcx, rdi; this
0x18008ff26  mov     rbx, rax
0x18008ff29  call    ?ExecutionPackageName@CClassData@@QEBAPEBGXZ; CClassData::ExecutionPackageName(void)
0x18008ff2e  mov     rdx, [rbp+80h+var_F0]
0x18008ff32  lea     rcx, [rsp+180h+TokenHandle]
0x18008ff37  mov     r8d, [rdi+84h]
0x18008ff3e  mov     r9, rax
0x18008ff41  mov     [rsp+180h+var_138], rcx
0x18008ff46  mov     rcx, [rbp+80h+var_E8]
0x18008ff4a  mov     [rsp+180h+var_140], r14
0x18008ff4f  mov     [rsp+180h+var_148], r12
0x18008ff54  mov     [rsp+180h+var_150], rdx
0x18008ff59  mov     edx, esi
0x18008ff5b  mov     dword ptr [rsp+180h+var_158], 0
0x18008ff63  mov     qword ptr [rsp+180h+var_160], rbx; int
0x18008ff68  call    cs:__imp_PsmAdjustActivationTokenEx2
0x18008ff6f  nop     dword ptr [rax+rax+00h]
0x18008ff74  test    eax, eax
0x18008ff76  jns     short loc_18008FFA1
0x18008ff78  mov     edx, 963h; void *
0x18008ff7d  mov     rcx, [rbp+88h]; this
0x18008ff84  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18008ff8b  mov     r9d, eax; char *
0x18008ff8e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008ff93  lea     rcx, [rsp+180h+TokenHandle]
0x18008ff98  mov     ebx, eax
0x18008ff9a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008ff9f  jmp     short loc_18008FFDB
0x18008ffa1  test    r15b, r15b
0x18008ffa4  jz      short loc_18008FFBD
0x18008ffa6  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x18008ffab  xor     edx, edx; unsigned int
0x18008ffad  call    ?CiPolicyAdjustToken@@YAJPEAXKPEBG@Z; CiPolicyAdjustToken(void *,ulong,ushort const *)
0x18008ffb2  test    eax, eax
0x18008ffb4  jns     short loc_18008FFBD
0x18008ffb6  mov     edx, 968h
0x18008ffbb  jmp     short loc_18008FF7D
0x18008ffbd  mov     rax, [rsp+180h+TokenHandle]
0x18008ffc2  lea     rcx, [rsp+180h+TokenHandle]
0x18008ffc7  mov     [r13+0], rax
0x18008ffcb  mov     [rsp+180h+TokenHandle], 0
0x18008ffd4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008ffd9  xor     ebx, ebx
0x18008ffdb  lea     rcx, [rsp+180h+var_118]
0x18008ffe0  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18008ffe5  mov     eax, ebx
0x18008ffe7  mov     rcx, [rbp+80h+var_40]
0x18008ffeb  xor     rcx, rsp; StackCookie
0x18008ffee  call    __security_check_cookie
0x18008fff3  mov     rbx, [rsp+180h+arg_10]
0x18008fffb  add     rsp, 150h
0x180090002  pop     r15
0x180090004  pop     r14
0x180090006  pop     r13
0x180090008  pop     r12
0x18009000a  pop     rdi
0x18009000b  pop     rsi
0x18009000c  pop     rbp
0x18009000d  retn
0x18009000f  mov     rcx, rdi; this
0x180090012  call    ?AppUserModelID@CClassData@@QEBAPEBGXZ; CClassData::AppUserModelID(void)
0x180090017  mov     rcx, rdi; this
0x18009001a  mov     rbx, rax
0x18009001d  call    ?ExecutionPackageName@CClassData@@QEBAPEBGXZ; CClassData::ExecutionPackageName(void)
0x180090022  mov     rdx, [rbp+80h+var_F0]
0x180090026  mov     r9, rax
0x180090029  mov     r8d, [rdi+84h]
0x180090030  mov     rcx, [rbp+80h+var_E8]
0x180090034  mov     [rsp+180h+var_138], r13
0x180090039  mov     [rsp+180h+var_140], r14
0x18009003e  mov     [rsp+180h+var_148], r12
0x180090043  mov     [rsp+180h+var_150], rdx
0x180090048  mov     edx, esi
0x18009004a  mov     dword ptr [rsp+180h+var_158], 0
0x180090052  mov     qword ptr [rsp+180h+var_160], rbx
0x180090057  call    cs:__imp_PsmAdjustActivationTokenEx2
0x18009005e  nop     dword ptr [rax+rax+00h]
0x180090063  test    eax, eax
0x180090065  jns     loc_18008FFD9
0x18009006b  mov     edx, 971h
0x180090070  jmp     loc_18008FE5E
```
