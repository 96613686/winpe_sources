# SecurityManager::PrepareForKeys(void *)

- ea: `0x1402740a0`
- end: `0x1402746c0`
- name: `?PrepareForKeys@SecurityManager@@UEAAJPEAX@Z`
- size: `1568`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140029744`
- `0x14005e804`
- `0x1400b42d0`
- `0x1400d6a94`
- `0x14012eacc`
- `0x140132960`
- `0x140271c78`
- `0x140272148`
- `0x1402721b8`
- `0x140272418`
- `0x140272af0`
- `0x140272f30`
- `0x140273248`
- `0x14027388c`
- `0x1402740a0`
- `0x140274790`
- `0x140274a90`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140274157`
- `ntdll!NtQuerySystemInformation` at `0x140274157`
- `bcrypt!BCryptGenRandom` at `0x1402741ee`
- `bcrypt!BCryptGenRandom` at `0x1402741ee`
- `vid!VidSetMailboxKey` at `0x14027430e`
- `vid!VidSetMailboxKey` at `0x14027430e`
- `vid!VidGetRpcSession` at `0x14027437b`
- `vid!VidGetRpcSession` at `0x14027437b`

## string_xrefs

- `0x14027410d`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027418c`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402742c9`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274326`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274393`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402743e6`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274455`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402744db`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274541`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274593`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402745e5`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274637`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall SecurityManager::PrepareForKeys(SecurityManager *this, void *a2)
{
  SecurityManager *v3; // rsi
  __int64 v4; // rdx
  NTSTATUS v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // edx
  int v10; // edi
  __int64 v11; // rdx
  NTSTATUS v12; // eax
  struct _GUID *v13; // rdi
  const unsigned __int16 *v14; // rdx
  int SecurityProcess; // eax
  unsigned int v16; // edi
  const char *v17; // r9
  unsigned int LastError; // ebx
  const char *v19; // r9
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // edi
  int v23; // eax
  unsigned int v24; // edi
  int v25; // eax
  unsigned int v26; // edi
  int SecurityCookie; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // edi
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // [rsp+20h] [rbp-D8h]
  int v36; // [rsp+20h] [rbp-D8h]
  struct _TRUSTLET_MAILBOX_KEY *v37; // [rsp+28h] [rbp-D0h]
  ULONG ReturnLength[2]; // [rsp+30h] [rbp-C8h] BYREF
  __int128 v39; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B0h]
  __int128 v41; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-98h]
  __int128 v43; // [rsp+68h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-80h]
  __int128 SystemInformation; // [rsp+80h] [rbp-78h] BYREF
  __int128 *v46; // [rsp+90h] [rbp-68h]
  __int128 *v47; // [rsp+98h] [rbp-60h]
  __int64 v48; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-50h] BYREF
  UCHAR pbBuffer[16]; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v49 = 0;
  v48 = 0;
  v3 = (SecurityManager *)((char *)this - 24);
  if ( *((_DWORD *)this + 34) || *((_DWORD *)this + 28) || !*((_DWORD *)this + 30) && !*((_DWORD *)this + 31) )
    return 0;
  if ( !*((_QWORD *)this + 25) )
  {
    v4 = 2553;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)0x8007139FLL,
      v35);
    return 2147947423LL;
  }
  *((_QWORD *)this + 12) = a2;
  SystemInformation = 0;
  ReturnLength[0] = 0;
  v6 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, ReturnLength);
  if ( v6 >= 0 )
    v9 = SystemInformation & 1;
  else
    v9 = 0;
  v10 = v6 | 0x10000000;
  if ( v6 >= 0 )
    v10 = 0;
  if ( v10 < 0 )
  {
    v11 = 2560;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v10,
      v35);
    return (unsigned int)v10;
  }
  if ( !v9 )
  {
    VmEventWriteAndReport<std::wstring &,std::wstring &>(
      (_DWORD)this + 32,
      0,
      v7,
      v8,
      (__int64)this + 32,
      (__int64)this + 64);
    v4 = 2571;
    goto LABEL_7;
  }
  *(_OWORD *)pbBuffer = 0;
  v12 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  v10 = v12 | 0x10000000;
  if ( v12 >= 0 )
    v10 = 0;
  if ( v10 < 0 )
  {
    v11 = 2578;
    goto LABEL_15;
  }
  v43 = 0;
  v44 = 0;
  v41 = 0;
  v42 = 0;
  v39 = 0;
  v40 = 0;
  SecurityManager::UnwrapKeyProtector(v3, &v43, &v41, &v39);
  v13 = (struct _GUID *)((char *)this + 64);
  if ( *((_QWORD *)this + 11) <= 7u )
    v14 = (const unsigned __int16 *)((char *)this + 64);
  else
    v14 = *(const unsigned __int16 **)&v13->Data1;
  Vml::VmGuid::Assign((Vml::VmGuid *)&SystemInformation, v14);
  if ( *((_QWORD *)this + 11) > 7u )
    v13 = *(struct _GUID **)&v13->Data1;
  SecurityProcess = KeyManagement::CreateSecurityProcess(
                      (KeyManagement *)&SystemInformation,
                      v13,
                      *((const unsigned __int16 **)this + 25),
                      (const unsigned __int8 *)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)),
                      (struct _PS_TRUSTLET_TKSESSION_ID *)pbBuffer,
                      v37,
                      *(void ***)ReturnLength);
  v16 = SecurityProcess;
  if ( SecurityProcess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2A,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)SecurityProcess,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
    return v16;
  }
  if ( !(unsigned int)VidSetMailboxKey(*((_QWORD *)this + 12), pbBuffer) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA2F,
                  (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
                  v17);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
    return LastError;
  }
  if ( !(unsigned int)VidGetRpcSession(*((_QWORD *)this + 12), &v49, &v48, (char *)this + 360) )
  {
    v20 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xA34,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            v19);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
    return v20;
  }
  v21 = SecurityManager::InitializeRpcClient(v3);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA36,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v21,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
    return v22;
  }
  *(_QWORD *)&SystemInformation = v3;
  *((_QWORD *)&SystemInformation + 1) = &v48;
  v23 = lambda_2b6c794ed40287bf31308bbcd9759849_::operator()(&SystemInformation);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4C,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v23,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
    return v24;
  }
  *(_QWORD *)&SystemInformation = v3;
  *((_QWORD *)&SystemInformation + 1) = &v43;
  v46 = &v41;
  v47 = &v39;
  v25 = lambda_6c6ea953952cabd78dd0b7154551d92a_::operator()(&SystemInformation);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA72,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v25,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
    return v26;
  }
  if ( *((_DWORD *)this + 31) )
  {
    *(_QWORD *)ReturnLength = 0;
    SecurityCookie = SecurityManager::GetSecurityCookie(this, (unsigned __int64 *)ReturnLength);
    v28 = SecurityCookie;
    if ( SecurityCookie < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA77,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)SecurityCookie,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
      return v28;
    }
    v29 = SecurityManager::InitializeEncryptionKeys(this);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7C,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v29,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
      return v30;
    }
    v31 = SecurityManager::PersistKsdState(v3);
    v32 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7E,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v31,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
      return v32;
    }
    v33 = SecurityManager::ReleaseEncryptionKeys(this);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA80,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v33,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
      return v34;
    }
    SecurityManager::CloseKeyManagment(v3);
  }
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v39);
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v41);
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v43);
  return 0;
}

```

## disassembly

```asm
0x1402740a0  mov     r11, rsp
0x1402740a3  push    rbx
0x1402740a4  push    rsi
0x1402740a5  push    rdi
0x1402740a6  push    r14
0x1402740a8  sub     rsp, 0D8h
0x1402740af  mov     rax, cs:__security_cookie
0x1402740b6  xor     rax, rsp
0x1402740b9  mov     [rsp+0F8h+var_38], rax
0x1402740c1  mov     rbx, rcx
0x1402740c4  xor     r14d, r14d
0x1402740c7  mov     [r11-50h], r14
0x1402740cb  mov     [r11-58h], r14
0x1402740cf  lea     rsi, [rcx-18h]
0x1402740d3  cmp     [rsi+0A0h], r14d
0x1402740da  jnz     loc_1402746A0
0x1402740e0  cmp     [rcx+70h], r14d
0x1402740e4  jnz     loc_1402746A0
0x1402740ea  cmp     [rcx+78h], r14d
0x1402740ee  jnz     short loc_1402740FA
0x1402740f0  cmp     [rcx+7Ch], r14d
0x1402740f4  jz      loc_1402746A0
0x1402740fa  cmp     [rcx+0C8h], r14
0x140274101  jnz     short loc_14027412B
0x140274103  mov     edx, 9F9h; void *
0x140274108  mov     ebx, 8007139Fh
0x14027410d  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274114  mov     r9d, ebx; char *
0x140274117  mov     rcx, [rsp+0F8h]; this
0x14027411f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274124  mov     eax, ebx
0x140274126  jmp     loc_1402746A2
0x14027412b  mov     [rcx+60h], rdx
0x14027412f  xorps   xmm0, xmm0
0x140274132  movups  [rsp+0F8h+SystemInformation], xmm0
0x14027413a  mov     [rsp+0F8h+ReturnLength], r14d; void **
0x14027413f  lea     r9, [rsp+0F8h+ReturnLength]; ReturnLength
0x140274144  mov     r8d, 10h; SystemInformationLength
0x14027414a  lea     rdx, [rsp+0F8h+SystemInformation]; SystemInformation
0x140274152  mov     ecx, 0A5h; SystemInformationClass
0x140274157  call    cs:__imp_NtQuerySystemInformation
0x14027415e  nop     dword ptr [rax+rax+00h]
0x140274163  test    eax, eax
0x140274165  jns     short loc_14027416C
0x140274167  mov     edx, r14d
0x14027416a  jmp     short loc_140274177
0x14027416c  movzx   edx, byte ptr [rsp+0F8h+SystemInformation]
0x140274174  and     edx, 1
0x140274177  mov     edi, eax
0x140274179  bts     edi, 1Ch
0x14027417d  test    eax, eax
0x14027417f  cmovns  edi, r14d
0x140274183  test    edi, edi
0x140274185  jns     short loc_1402741AA
0x140274187  mov     edx, 0A00h; void *
0x14027418c  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274193  mov     r9d, edi; char *
0x140274196  mov     rcx, [rsp+0F8h]; this
0x14027419e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402741a3  mov     eax, edi
0x1402741a5  jmp     loc_1402746A2
0x1402741aa  test    edx, edx
0x1402741ac  jnz     short loc_1402741CF
0x1402741ae  lea     rax, [rbx+40h]
0x1402741b2  lea     rcx, [rbx+20h]
0x1402741b6  mov     [rsp+0F8h+var_D0], rax
0x1402741bb  mov     [rsp+0F8h+var_D8], rcx
0x1402741c0  call    ??$VmEventWriteAndReport@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@3@Z; VmEventWriteAndReport<std::wstring &,std::wstring &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,std::wstring &,std::wstring &)
0x1402741c5  mov     edx, 0A0Bh
0x1402741ca  jmp     loc_140274108
0x1402741cf  xorps   xmm0, xmm0
0x1402741d2  movups  xmmword ptr [rsp+0F8h+pbBuffer], xmm0
0x1402741da  mov     r9d, 2; dwFlags
0x1402741e0  lea     r8d, [r9+0Eh]; cbBuffer
0x1402741e4  lea     rdx, [rsp+0F8h+pbBuffer]; pbBuffer
0x1402741ec  xor     ecx, ecx; hAlgorithm
0x1402741ee  call    cs:__imp_BCryptGenRandom
0x1402741f5  nop     dword ptr [rax+rax+00h]
0x1402741fa  mov     edi, eax
0x1402741fc  bts     edi, 1Ch
0x140274200  test    eax, eax
0x140274202  cmovns  edi, r14d
0x140274206  test    edi, edi
0x140274208  jns     short loc_140274214
0x14027420a  mov     edx, 0A12h
0x14027420f  jmp     loc_14027418C
0x140274214  xorps   xmm1, xmm1
0x140274217  movdqu  [rsp+0F8h+var_90], xmm1
0x14027421d  mov     [rsp+0F8h+var_80], r14
0x140274222  movdqu  [rsp+0F8h+var_A8], xmm1
0x140274228  mov     [rsp+0F8h+var_98], r14
0x14027422d  movdqu  [rsp+0F8h+var_C0], xmm1
0x140274233  mov     [rsp+0F8h+var_B0], r14
0x140274238  lea     r9, [rsp+0F8h+var_C0]
0x14027423d  lea     r8, [rsp+0F8h+var_A8]
0x140274242  lea     rdx, [rsp+0F8h+var_90]
0x140274247  mov     rcx, rsi
0x14027424a  call    ?UnwrapKeyProtector@SecurityManager@@AEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@00@Z; SecurityManager::UnwrapKeyProtector(std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &)
0x14027424f  lea     rdi, [rbx+40h]
0x140274253  cmp     qword ptr [rdi+18h], 7
0x140274258  jbe     short loc_14027425F
0x14027425a  mov     rdx, [rdi]
0x14027425d  jmp     short loc_140274262
0x14027425f  mov     rdx, rdi; unsigned __int16 *
0x140274262  lea     rcx, [rsp+0F8h+SystemInformation]; this
0x14027426a  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x14027426f  mov     r8, [rbx+0C8h]; unsigned __int16 *
0x140274276  mov     r9, [rbx+0D0h]
0x14027427d  sub     r9, r8; unsigned __int8 *
0x140274280  cmp     qword ptr [rdi+18h], 7
0x140274285  jbe     short loc_14027428A
0x140274287  mov     rdi, [rdi]
0x14027428a  movaps  xmm0, [rsp+0F8h+SystemInformation]
0x140274292  movdqa  [rsp+0F8h+SystemInformation], xmm0
0x14027429b  lea     rax, [rsp+0F8h+pbBuffer]
0x1402742a3  mov     [rsp+0F8h+var_D8], rax; int
0x1402742a8  mov     rdx, rdi; struct _GUID *
0x1402742ab  lea     rcx, [rsp+0F8h+SystemInformation]; this
0x1402742b3  call    ?CreateSecurityProcess@KeyManagement@@YAJU_GUID@@PEBGPEBE_KPEAU_TRUSTLET_MAILBOX_KEY@@PEAPEAX@Z; KeyManagement::CreateSecurityProcess(_GUID,ushort const *,uchar const *,unsigned __int64,_TRUSTLET_MAILBOX_KEY *,void * *)
0x1402742b8  mov     edi, eax
0x1402742ba  test    eax, eax
0x1402742bc  jns     short loc_140274302
0x1402742be  mov     rcx, [rsp+0F8h]; this
0x1402742c6  mov     r9d, eax; char *
0x1402742c9  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402742d0  mov     edx, 0A2Ah; void *
0x1402742d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402742da  nop
0x1402742db  lea     rcx, [rsp+0F8h+var_C0]
0x1402742e0  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402742e5  nop
0x1402742e6  lea     rcx, [rsp+0F8h+var_A8]
0x1402742eb  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402742f0  nop
0x1402742f1  lea     rcx, [rsp+0F8h+var_90]
0x1402742f6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402742fb  mov     eax, edi
0x1402742fd  jmp     loc_1402746A2
0x140274302  lea     rdx, [rsp+0F8h+pbBuffer]
0x14027430a  mov     rcx, [rbx+60h]
0x14027430e  call    cs:__imp_VidSetMailboxKey
0x140274315  nop     dword ptr [rax+rax+00h]
0x14027431a  test    eax, eax
0x14027431c  jnz     short loc_140274360
0x14027431e  mov     rcx, [rsp+0F8h]; this
0x140274326  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027432d  mov     edx, 0A2Fh; void *
0x140274332  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140274337  mov     ebx, eax
0x140274339  lea     rcx, [rsp+0F8h+var_C0]
0x14027433e  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274343  nop
0x140274344  lea     rcx, [rsp+0F8h+var_A8]
0x140274349  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027434e  nop
0x14027434f  lea     rcx, [rsp+0F8h+var_90]
0x140274354  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274359  mov     eax, ebx
0x14027435b  jmp     loc_1402746A2
0x140274360  lea     r9, [rbx+168h]
0x140274367  lea     r8, [rsp+0F8h+var_58]
0x14027436f  lea     rdx, [rsp+0F8h+var_50]
0x140274377  mov     rcx, [rbx+60h]
0x14027437b  call    cs:__imp_VidGetRpcSession
0x140274382  nop     dword ptr [rax+rax+00h]
0x140274387  test    eax, eax
0x140274389  jnz     short loc_1402743CD
0x14027438b  mov     rcx, [rsp+0F8h]; this
0x140274393  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027439a  mov     edx, 0A34h; void *
0x14027439f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1402743a4  mov     ebx, eax
0x1402743a6  lea     rcx, [rsp+0F8h+var_C0]
0x1402743ab  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402743b0  nop
0x1402743b1  lea     rcx, [rsp+0F8h+var_A8]
0x1402743b6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402743bb  nop
0x1402743bc  lea     rcx, [rsp+0F8h+var_90]
0x1402743c1  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402743c6  mov     eax, ebx
0x1402743c8  jmp     loc_1402746A2
0x1402743cd  mov     rcx, rsi; this
0x1402743d0  call    ?InitializeRpcClient@SecurityManager@@AEAAJXZ; SecurityManager::InitializeRpcClient(void)
0x1402743d5  mov     edi, eax
0x1402743d7  test    eax, eax
0x1402743d9  jns     short loc_14027441F
0x1402743db  mov     rcx, [rsp+0F8h]; this
0x1402743e3  mov     r9d, eax; char *
0x1402743e6  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402743ed  mov     edx, 0A36h; void *
0x1402743f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402743f7  nop
0x1402743f8  lea     rcx, [rsp+0F8h+var_C0]
0x1402743fd  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274402  nop
0x140274403  lea     rcx, [rsp+0F8h+var_A8]
0x140274408  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027440d  nop
0x14027440e  lea     rcx, [rsp+0F8h+var_90]
0x140274413  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274418  mov     eax, edi
0x14027441a  jmp     loc_1402746A2
0x14027441f  mov     qword ptr [rsp+0F8h+SystemInformation], rsi
0x140274427  lea     rax, [rsp+0F8h+var_58]
0x14027442f  mov     qword ptr [rsp+0F8h+SystemInformation+8], rax
0x140274437  lea     rcx, [rsp+0F8h+SystemInformation]
0x14027443f  call    _lambda_2b6c794ed40287bf31308bbcd9759849___operator__
0x140274444  mov     edi, eax
0x140274446  test    eax, eax
0x140274448  jns     short loc_14027448E
0x14027444a  mov     rcx, [rsp+0F8h]; this
0x140274452  mov     r9d, eax; char *
0x140274455  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027445c  mov     edx, 0A4Ch; void *
0x140274461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274466  nop
0x140274467  lea     rcx, [rsp+0F8h+var_C0]
0x14027446c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274471  nop
0x140274472  lea     rcx, [rsp+0F8h+var_A8]
0x140274477  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027447c  nop
0x14027447d  lea     rcx, [rsp+0F8h+var_90]
0x140274482  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274487  mov     eax, edi
0x140274489  jmp     loc_1402746A2
0x14027448e  mov     qword ptr [rsp+0F8h+SystemInformation], rsi
0x140274496  lea     rax, [rsp+0F8h+var_90]
0x14027449b  mov     qword ptr [rsp+0F8h+SystemInformation+8], rax
0x1402744a3  lea     rax, [rsp+0F8h+var_A8]
0x1402744a8  mov     [rsp+0F8h+var_68], rax
0x1402744b0  lea     rax, [rsp+0F8h+var_C0]
0x1402744b5  mov     [rsp+0F8h+var_60], rax
0x1402744bd  lea     rcx, [rsp+0F8h+SystemInformation]
0x1402744c5  call    _lambda_6c6ea953952cabd78dd0b7154551d92a___operator__
0x1402744ca  mov     edi, eax
0x1402744cc  test    eax, eax
0x1402744ce  jns     short loc_140274514
0x1402744d0  mov     rcx, [rsp+0F8h]; this
0x1402744d8  mov     r9d, eax; char *
0x1402744db  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402744e2  mov     edx, 0A72h; void *
0x1402744e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402744ec  nop
0x1402744ed  lea     rcx, [rsp+0F8h+var_C0]
0x1402744f2  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402744f7  nop
0x1402744f8  lea     rcx, [rsp+0F8h+var_A8]
0x1402744fd  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274502  nop
0x140274503  lea     rcx, [rsp+0F8h+var_90]
0x140274508  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027450d  mov     eax, edi
0x14027450f  jmp     loc_1402746A2
0x140274514  cmp     [rbx+7Ch], r14d
0x140274518  jz      loc_140274676
0x14027451e  mov     qword ptr [rsp+0F8h+ReturnLength], r14
0x140274523  lea     rdx, [rsp+0F8h+ReturnLength]; unsigned __int64 *
0x140274528  mov     rcx, rbx; this
0x14027452b  call    ?GetSecurityCookie@SecurityManager@@UEAAJPEA_K@Z; SecurityManager::GetSecurityCookie(unsigned __int64 *)
0x140274530  mov     edi, eax
0x140274532  test    eax, eax
0x140274534  jns     short loc_14027457A
0x140274536  mov     rcx, [rsp+0F8h]; this
0x14027453e  mov     r9d, eax; char *
0x140274541  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274548  mov     edx, 0A77h; void *
0x14027454d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274552  nop
0x140274553  lea     rcx, [rsp+0F8h+var_C0]
0x140274558  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027455d  nop
0x14027455e  lea     rcx, [rsp+0F8h+var_A8]
0x140274563  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274568  nop
0x140274569  lea     rcx, [rsp+0F8h+var_90]
0x14027456e  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274573  mov     eax, edi
0x140274575  jmp     loc_1402746A2
0x14027457a  mov     rcx, rbx; this
0x14027457d  call    ?InitializeEncryptionKeys@SecurityManager@@UEAAJXZ; SecurityManager::InitializeEncryptionKeys(void)
0x140274582  mov     edi, eax
0x140274584  test    eax, eax
0x140274586  jns     short loc_1402745CC
0x140274588  mov     rcx, [rsp+0F8h]; this
0x140274590  mov     r9d, eax; char *
0x140274593  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027459a  mov     edx, 0A7Ch; void *
0x14027459f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402745a4  nop
0x1402745a5  lea     rcx, [rsp+0F8h+var_C0]
0x1402745aa  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402745af  nop
0x1402745b0  lea     rcx, [rsp+0F8h+var_A8]
0x1402745b5  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402745ba  nop
0x1402745bb  lea     rcx, [rsp+0F8h+var_90]
0x1402745c0  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402745c5  mov     eax, edi
  ... truncated ...
```
