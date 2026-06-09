# SecurityManager::PrepareForKeys(void *)

- ea: `0x14027a0b0`
- end: `0x14027a6d0`
- name: `?PrepareForKeys@SecurityManager@@UEAAJPEAX@Z`
- size: `1568`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140036e3c`
- `0x1400691b4`
- `0x14006d540`
- `0x1400c5bf4`
- `0x14011b990`
- `0x14011ea40`
- `0x140277b28`
- `0x140278018`
- `0x140278088`
- `0x1402782e8`
- `0x140278b00`
- `0x140278f40`
- `0x140279258`
- `0x14027989c`
- `0x14027a0b0`
- `0x14027a7a0`
- `0x14027abb0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x14027a167`
- `ntdll!NtQuerySystemInformation` at `0x14027a167`
- `bcrypt!BCryptGenRandom` at `0x14027a1fe`
- `bcrypt!BCryptGenRandom` at `0x14027a1fe`
- `vid!VidSetMailboxKey` at `0x14027a31e`
- `vid!VidSetMailboxKey` at `0x14027a31e`
- `vid!VidGetRpcSession` at `0x14027a38b`
- `vid!VidGetRpcSession` at `0x14027a38b`

## string_xrefs

- `0x14027a11d`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a19c`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a2d9`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a336`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a3a3`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a3f6`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a465`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a4eb`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a551`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a5a3`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a5f5`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a647`: `onecore\vm\worker\security\securitymanager.cpp`

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
0x14027a0b0  mov     r11, rsp
0x14027a0b3  push    rbx
0x14027a0b4  push    rsi
0x14027a0b5  push    rdi
0x14027a0b6  push    r14
0x14027a0b8  sub     rsp, 0D8h
0x14027a0bf  mov     rax, cs:__security_cookie
0x14027a0c6  xor     rax, rsp
0x14027a0c9  mov     [rsp+0F8h+var_38], rax
0x14027a0d1  mov     rbx, rcx
0x14027a0d4  xor     r14d, r14d
0x14027a0d7  mov     [r11-50h], r14
0x14027a0db  mov     [r11-58h], r14
0x14027a0df  lea     rsi, [rcx-18h]
0x14027a0e3  cmp     [rsi+0A0h], r14d
0x14027a0ea  jnz     loc_14027A6B0
0x14027a0f0  cmp     [rcx+70h], r14d
0x14027a0f4  jnz     loc_14027A6B0
0x14027a0fa  cmp     [rcx+78h], r14d
0x14027a0fe  jnz     short loc_14027A10A
0x14027a100  cmp     [rcx+7Ch], r14d
0x14027a104  jz      loc_14027A6B0
0x14027a10a  cmp     [rcx+0C8h], r14
0x14027a111  jnz     short loc_14027A13B
0x14027a113  mov     edx, 9F9h; void *
0x14027a118  mov     ebx, 8007139Fh
0x14027a11d  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a124  mov     r9d, ebx; char *
0x14027a127  mov     rcx, [rsp+0F8h]; this
0x14027a12f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a134  mov     eax, ebx
0x14027a136  jmp     loc_14027A6B2
0x14027a13b  mov     [rcx+60h], rdx
0x14027a13f  xorps   xmm0, xmm0
0x14027a142  movups  [rsp+0F8h+SystemInformation], xmm0
0x14027a14a  mov     [rsp+0F8h+ReturnLength], r14d; void **
0x14027a14f  lea     r9, [rsp+0F8h+ReturnLength]; ReturnLength
0x14027a154  mov     r8d, 10h; SystemInformationLength
0x14027a15a  lea     rdx, [rsp+0F8h+SystemInformation]; SystemInformation
0x14027a162  mov     ecx, 0A5h; SystemInformationClass
0x14027a167  call    cs:__imp_NtQuerySystemInformation
0x14027a16e  nop     dword ptr [rax+rax+00h]
0x14027a173  test    eax, eax
0x14027a175  jns     short loc_14027A17C
0x14027a177  mov     edx, r14d
0x14027a17a  jmp     short loc_14027A187
0x14027a17c  movzx   edx, byte ptr [rsp+0F8h+SystemInformation]
0x14027a184  and     edx, 1
0x14027a187  mov     edi, eax
0x14027a189  bts     edi, 1Ch
0x14027a18d  test    eax, eax
0x14027a18f  cmovns  edi, r14d
0x14027a193  test    edi, edi
0x14027a195  jns     short loc_14027A1BA
0x14027a197  mov     edx, 0A00h; void *
0x14027a19c  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a1a3  mov     r9d, edi; char *
0x14027a1a6  mov     rcx, [rsp+0F8h]; this
0x14027a1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a1b3  mov     eax, edi
0x14027a1b5  jmp     loc_14027A6B2
0x14027a1ba  test    edx, edx
0x14027a1bc  jnz     short loc_14027A1DF
0x14027a1be  lea     rax, [rbx+40h]
0x14027a1c2  lea     rcx, [rbx+20h]
0x14027a1c6  mov     [rsp+0F8h+var_D0], rax
0x14027a1cb  mov     [rsp+0F8h+var_D8], rcx
0x14027a1d0  call    ??$VmEventWriteAndReport@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@3@Z; VmEventWriteAndReport<std::wstring &,std::wstring &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,std::wstring &,std::wstring &)
0x14027a1d5  mov     edx, 0A0Bh
0x14027a1da  jmp     loc_14027A118
0x14027a1df  xorps   xmm0, xmm0
0x14027a1e2  movups  xmmword ptr [rsp+0F8h+pbBuffer], xmm0
0x14027a1ea  mov     r9d, 2; dwFlags
0x14027a1f0  lea     r8d, [r9+0Eh]; cbBuffer
0x14027a1f4  lea     rdx, [rsp+0F8h+pbBuffer]; pbBuffer
0x14027a1fc  xor     ecx, ecx; hAlgorithm
0x14027a1fe  call    cs:__imp_BCryptGenRandom
0x14027a205  nop     dword ptr [rax+rax+00h]
0x14027a20a  mov     edi, eax
0x14027a20c  bts     edi, 1Ch
0x14027a210  test    eax, eax
0x14027a212  cmovns  edi, r14d
0x14027a216  test    edi, edi
0x14027a218  jns     short loc_14027A224
0x14027a21a  mov     edx, 0A12h
0x14027a21f  jmp     loc_14027A19C
0x14027a224  xorps   xmm1, xmm1
0x14027a227  movdqu  [rsp+0F8h+var_90], xmm1
0x14027a22d  mov     [rsp+0F8h+var_80], r14
0x14027a232  movdqu  [rsp+0F8h+var_A8], xmm1
0x14027a238  mov     [rsp+0F8h+var_98], r14
0x14027a23d  movdqu  [rsp+0F8h+var_C0], xmm1
0x14027a243  mov     [rsp+0F8h+var_B0], r14
0x14027a248  lea     r9, [rsp+0F8h+var_C0]
0x14027a24d  lea     r8, [rsp+0F8h+var_A8]
0x14027a252  lea     rdx, [rsp+0F8h+var_90]
0x14027a257  mov     rcx, rsi
0x14027a25a  call    ?UnwrapKeyProtector@SecurityManager@@AEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@00@Z; SecurityManager::UnwrapKeyProtector(std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &)
0x14027a25f  lea     rdi, [rbx+40h]
0x14027a263  cmp     qword ptr [rdi+18h], 7
0x14027a268  jbe     short loc_14027A26F
0x14027a26a  mov     rdx, [rdi]
0x14027a26d  jmp     short loc_14027A272
0x14027a26f  mov     rdx, rdi; unsigned __int16 *
0x14027a272  lea     rcx, [rsp+0F8h+SystemInformation]; this
0x14027a27a  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x14027a27f  mov     r8, [rbx+0C8h]; unsigned __int16 *
0x14027a286  mov     r9, [rbx+0D0h]
0x14027a28d  sub     r9, r8; unsigned __int8 *
0x14027a290  cmp     qword ptr [rdi+18h], 7
0x14027a295  jbe     short loc_14027A29A
0x14027a297  mov     rdi, [rdi]
0x14027a29a  movaps  xmm0, [rsp+0F8h+SystemInformation]
0x14027a2a2  movdqa  [rsp+0F8h+SystemInformation], xmm0
0x14027a2ab  lea     rax, [rsp+0F8h+pbBuffer]
0x14027a2b3  mov     [rsp+0F8h+var_D8], rax; int
0x14027a2b8  mov     rdx, rdi; struct _GUID *
0x14027a2bb  lea     rcx, [rsp+0F8h+SystemInformation]; this
0x14027a2c3  call    ?CreateSecurityProcess@KeyManagement@@YAJU_GUID@@PEBGPEBE_KPEAU_TRUSTLET_MAILBOX_KEY@@PEAPEAX@Z; KeyManagement::CreateSecurityProcess(_GUID,ushort const *,uchar const *,unsigned __int64,_TRUSTLET_MAILBOX_KEY *,void * *)
0x14027a2c8  mov     edi, eax
0x14027a2ca  test    eax, eax
0x14027a2cc  jns     short loc_14027A312
0x14027a2ce  mov     rcx, [rsp+0F8h]; this
0x14027a2d6  mov     r9d, eax; char *
0x14027a2d9  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a2e0  mov     edx, 0A2Ah; void *
0x14027a2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a2ea  nop
0x14027a2eb  lea     rcx, [rsp+0F8h+var_C0]
0x14027a2f0  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a2f5  nop
0x14027a2f6  lea     rcx, [rsp+0F8h+var_A8]
0x14027a2fb  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a300  nop
0x14027a301  lea     rcx, [rsp+0F8h+var_90]
0x14027a306  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a30b  mov     eax, edi
0x14027a30d  jmp     loc_14027A6B2
0x14027a312  lea     rdx, [rsp+0F8h+pbBuffer]
0x14027a31a  mov     rcx, [rbx+60h]
0x14027a31e  call    cs:__imp_VidSetMailboxKey
0x14027a325  nop     dword ptr [rax+rax+00h]
0x14027a32a  test    eax, eax
0x14027a32c  jnz     short loc_14027A370
0x14027a32e  mov     rcx, [rsp+0F8h]; this
0x14027a336  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a33d  mov     edx, 0A2Fh; void *
0x14027a342  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14027a347  mov     ebx, eax
0x14027a349  lea     rcx, [rsp+0F8h+var_C0]
0x14027a34e  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a353  nop
0x14027a354  lea     rcx, [rsp+0F8h+var_A8]
0x14027a359  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a35e  nop
0x14027a35f  lea     rcx, [rsp+0F8h+var_90]
0x14027a364  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a369  mov     eax, ebx
0x14027a36b  jmp     loc_14027A6B2
0x14027a370  lea     r9, [rbx+168h]
0x14027a377  lea     r8, [rsp+0F8h+var_58]
0x14027a37f  lea     rdx, [rsp+0F8h+var_50]
0x14027a387  mov     rcx, [rbx+60h]
0x14027a38b  call    cs:__imp_VidGetRpcSession
0x14027a392  nop     dword ptr [rax+rax+00h]
0x14027a397  test    eax, eax
0x14027a399  jnz     short loc_14027A3DD
0x14027a39b  mov     rcx, [rsp+0F8h]; this
0x14027a3a3  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a3aa  mov     edx, 0A34h; void *
0x14027a3af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14027a3b4  mov     ebx, eax
0x14027a3b6  lea     rcx, [rsp+0F8h+var_C0]
0x14027a3bb  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a3c0  nop
0x14027a3c1  lea     rcx, [rsp+0F8h+var_A8]
0x14027a3c6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a3cb  nop
0x14027a3cc  lea     rcx, [rsp+0F8h+var_90]
0x14027a3d1  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a3d6  mov     eax, ebx
0x14027a3d8  jmp     loc_14027A6B2
0x14027a3dd  mov     rcx, rsi; this
0x14027a3e0  call    ?InitializeRpcClient@SecurityManager@@AEAAJXZ; SecurityManager::InitializeRpcClient(void)
0x14027a3e5  mov     edi, eax
0x14027a3e7  test    eax, eax
0x14027a3e9  jns     short loc_14027A42F
0x14027a3eb  mov     rcx, [rsp+0F8h]; this
0x14027a3f3  mov     r9d, eax; char *
0x14027a3f6  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a3fd  mov     edx, 0A36h; void *
0x14027a402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a407  nop
0x14027a408  lea     rcx, [rsp+0F8h+var_C0]
0x14027a40d  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a412  nop
0x14027a413  lea     rcx, [rsp+0F8h+var_A8]
0x14027a418  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a41d  nop
0x14027a41e  lea     rcx, [rsp+0F8h+var_90]
0x14027a423  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a428  mov     eax, edi
0x14027a42a  jmp     loc_14027A6B2
0x14027a42f  mov     qword ptr [rsp+0F8h+SystemInformation], rsi
0x14027a437  lea     rax, [rsp+0F8h+var_58]
0x14027a43f  mov     qword ptr [rsp+0F8h+SystemInformation+8], rax
0x14027a447  lea     rcx, [rsp+0F8h+SystemInformation]
0x14027a44f  call    _lambda_2b6c794ed40287bf31308bbcd9759849___operator__
0x14027a454  mov     edi, eax
0x14027a456  test    eax, eax
0x14027a458  jns     short loc_14027A49E
0x14027a45a  mov     rcx, [rsp+0F8h]; this
0x14027a462  mov     r9d, eax; char *
0x14027a465  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a46c  mov     edx, 0A4Ch; void *
0x14027a471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a476  nop
0x14027a477  lea     rcx, [rsp+0F8h+var_C0]
0x14027a47c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a481  nop
0x14027a482  lea     rcx, [rsp+0F8h+var_A8]
0x14027a487  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a48c  nop
0x14027a48d  lea     rcx, [rsp+0F8h+var_90]
0x14027a492  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a497  mov     eax, edi
0x14027a499  jmp     loc_14027A6B2
0x14027a49e  mov     qword ptr [rsp+0F8h+SystemInformation], rsi
0x14027a4a6  lea     rax, [rsp+0F8h+var_90]
0x14027a4ab  mov     qword ptr [rsp+0F8h+SystemInformation+8], rax
0x14027a4b3  lea     rax, [rsp+0F8h+var_A8]
0x14027a4b8  mov     [rsp+0F8h+var_68], rax
0x14027a4c0  lea     rax, [rsp+0F8h+var_C0]
0x14027a4c5  mov     [rsp+0F8h+var_60], rax
0x14027a4cd  lea     rcx, [rsp+0F8h+SystemInformation]
0x14027a4d5  call    _lambda_6c6ea953952cabd78dd0b7154551d92a___operator__
0x14027a4da  mov     edi, eax
0x14027a4dc  test    eax, eax
0x14027a4de  jns     short loc_14027A524
0x14027a4e0  mov     rcx, [rsp+0F8h]; this
0x14027a4e8  mov     r9d, eax; char *
0x14027a4eb  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a4f2  mov     edx, 0A72h; void *
0x14027a4f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a4fc  nop
0x14027a4fd  lea     rcx, [rsp+0F8h+var_C0]
0x14027a502  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a507  nop
0x14027a508  lea     rcx, [rsp+0F8h+var_A8]
0x14027a50d  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a512  nop
0x14027a513  lea     rcx, [rsp+0F8h+var_90]
0x14027a518  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a51d  mov     eax, edi
0x14027a51f  jmp     loc_14027A6B2
0x14027a524  cmp     [rbx+7Ch], r14d
0x14027a528  jz      loc_14027A686
0x14027a52e  mov     qword ptr [rsp+0F8h+ReturnLength], r14
0x14027a533  lea     rdx, [rsp+0F8h+ReturnLength]; unsigned __int64 *
0x14027a538  mov     rcx, rbx; this
0x14027a53b  call    ?GetSecurityCookie@SecurityManager@@UEAAJPEA_K@Z; SecurityManager::GetSecurityCookie(unsigned __int64 *)
0x14027a540  mov     edi, eax
0x14027a542  test    eax, eax
0x14027a544  jns     short loc_14027A58A
0x14027a546  mov     rcx, [rsp+0F8h]; this
0x14027a54e  mov     r9d, eax; char *
0x14027a551  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a558  mov     edx, 0A77h; void *
0x14027a55d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a562  nop
0x14027a563  lea     rcx, [rsp+0F8h+var_C0]
0x14027a568  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a56d  nop
0x14027a56e  lea     rcx, [rsp+0F8h+var_A8]
0x14027a573  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a578  nop
0x14027a579  lea     rcx, [rsp+0F8h+var_90]
0x14027a57e  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a583  mov     eax, edi
0x14027a585  jmp     loc_14027A6B2
0x14027a58a  mov     rcx, rbx; this
0x14027a58d  call    ?InitializeEncryptionKeys@SecurityManager@@UEAAJXZ; SecurityManager::InitializeEncryptionKeys(void)
0x14027a592  mov     edi, eax
0x14027a594  test    eax, eax
0x14027a596  jns     short loc_14027A5DC
0x14027a598  mov     rcx, [rsp+0F8h]; this
0x14027a5a0  mov     r9d, eax; char *
0x14027a5a3  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a5aa  mov     edx, 0A7Ch; void *
0x14027a5af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a5b4  nop
0x14027a5b5  lea     rcx, [rsp+0F8h+var_C0]
0x14027a5ba  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a5bf  nop
0x14027a5c0  lea     rcx, [rsp+0F8h+var_A8]
0x14027a5c5  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a5ca  nop
0x14027a5cb  lea     rcx, [rsp+0F8h+var_90]
0x14027a5d0  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027a5d5  mov     eax, edi
  ... truncated ...
```
