# CredentialManager::WriteCredential(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001bdac`
- end: `0x18001c1f1`
- name: `?WriteCredential@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBGAEAV23@@Z`
- size: `1093`
- prototype: `void __fastcall(__int64, __int64, __int64, BYTE *, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017510`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x1800062d4`
- `0x180006418`
- `0x18000669c`
- `0x1800083e0`
- `0x18001075c`
- `0x180012f20`
- `0x18001a8a0`
- `0x18001a99c`
- `0x18001b3b4`
- `0x18001b560`
- `0x18001b6fc`
- `0x18001bdac`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001be71`
- `msvcrt!_wcsicmp` at `0x18001be71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c04d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c04d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bdf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bdf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c1c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c1c4`
- `ADVAPI32!CredWriteW` at `0x18001c03f`
- `ADVAPI32!CredWriteW` at `0x18001c03f`
- `ADVAPI32!CredReadW` at `0x18001be9f`
- `ADVAPI32!CredReadW` at `0x18001be9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CredentialManager::WriteCredential(__int64 a1, __int64 a2, __int64 a3, BYTE *a4, __int64 a5)
{
  WCHAR *v8; // rdi
  _WORD *v9; // rcx
  __int64 v10; // rbx
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rcx
  const WCHAR *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  BYTE *v18; // rax
  __int64 v19; // r8
  int v20; // ecx
  int v21; // edx
  __int64 i; // rax
  __int64 v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rdx
  DWORD LastError; // ebx
  __int64 v30; // rdx
  __int64 v31; // rax
  PCREDENTIALW Credential; // [rsp+20h] [rbp-E0h] BYREF
  void **pExceptionObject; // [rsp+28h] [rbp-D8h] BYREF
  char v34; // [rsp+30h] [rbp-D0h]
  const char *v35; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h]
  int v38; // [rsp+50h] [rbp-B0h]
  int v39; // [rsp+54h] [rbp-ACh]
  int v40; // [rsp+58h] [rbp-A8h]
  _BYTE v41[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall *v42)(HANDLE); // [rsp+68h] [rbp-98h]
  __int64 CurrentThreadTokenAndRevertToSelf; // [rsp+70h] [rbp-90h]
  struct _CREDENTIALW v44; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v45; // [rsp+D0h] [rbp-30h]
  __int16 v46; // [rsp+D8h] [rbp-28h] BYREF
  __int64 (__fastcall *v47)(); // [rsp+E0h] [rbp-20h]
  PCREDENTIALW v48; // [rsp+E8h] [rbp-18h]
  __int64 v49; // [rsp+F0h] [rbp-10h]
  int v50; // [rsp+F8h] [rbp-8h]
  _WORD v51[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v52; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h]

  v8 = (WCHAR *)a5;
  v45 = &CriticalSection;
  EnterCriticalSection(&CriticalSection);
  if ( *(_QWORD *)(a5 + 24) < 8u )
    v9 = (_WORD *)a5;
  else
    v9 = *(_WORD **)a5;
  *(_QWORD *)(a5 + 16) = 0;
  *v9 = 0;
  v41[0] = 0;
  v42 = RestoreAndCloseThreadToken;
  CurrentThreadTokenAndRevertToSelf = GetCurrentThreadTokenAndRevertToSelf();
  CredentialManager::DeleteCredentialInt(RestoreAndCloseThreadToken, a2);
  Credential = 0;
  v10 = *(_QWORD *)xmmword_18002F7D0;
  while ( v10 != (_QWORD)xmmword_18002F7D0 )
  {
    if ( *(_QWORD *)(a3 + 24) < 8u )
      v11 = (const wchar_t *)a3;
    else
      v11 = *(const wchar_t **)a3;
    v12 = (const wchar_t *)(v10 + 64);
    if ( *(_QWORD *)(v10 + 88) >= 8u )
      v12 = *(const wchar_t **)v12;
    if ( !_wcsicmp(v12, v11) )
    {
      Credential = 0;
      v13 = *(_QWORD *)(v10 + 56) < 8u ? (const WCHAR *)(v10 + 32) : *(const WCHAR **)(v10 + 32);
      if ( CredReadW(v13, 1u, 0, &Credential) )
      {
        LOBYTE(v46) = 0;
        v47 = ReleaseCredentialBlob;
        v48 = Credential;
        if ( (unsigned __int8)IsValidCredentialBlob(Credential, v14, v15, v16, (_DWORD)Credential, pExceptionObject) )
        {
          v18 = a4;
          v19 = *(_QWORD *)(v17 + 40) - (_QWORD)a4;
          do
          {
            v20 = *(unsigned __int16 *)&v18[v19];
            v21 = *(unsigned __int16 *)v18 - v20;
            if ( v21 )
              break;
            v18 += 2;
          }
          while ( v20 );
          if ( !v21 )
          {
            std::wstring::operator=(a5, v10 + 32);
            wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(&v46);
            if ( v10 != (_QWORD)xmmword_18002F7D0 )
            {
              v31 = std::map<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
                      v23,
                      a2);
              std::wstring::operator=(v31, a5);
              ++*(_DWORD *)(v10 + 96);
              goto LABEL_51;
            }
            break;
          }
        }
        wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(&v46);
      }
    }
    if ( !*(_BYTE *)(v10 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v10 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v10 + 8); !*(_BYTE *)(i + 25) && v10 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v10 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min();
      }
      v10 = i;
    }
  }
  v53 = 7;
  v52 = 0;
  v51[0] = 0;
  CreateGuid(v51);
  std::wstring::assign(a5, L"EC::");
  v24 = -1;
  std::wstring::append(a5, v51, 0, -1);
  v26 = std::map<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
          v25,
          a2);
  std::wstring::operator=(v26, a5);
  v49 = 7;
  v48 = 0;
  v46 = 0;
  std::wstring::operator=(&v46, a3);
  v50 = 1;
  v27 = std::map<std::wstring,CredentialManager::EntryInformation,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,CredentialManager::EntryInformation>>>::operator[](
          &xmmword_18002F7D0,
          a5);
  std::wstring::operator=(v27, &v46);
  *(_DWORD *)(v27 + 32) = v50;
  v44.LastWritten = 0;
  *(&v44.CredentialBlobSize + 1) = 0;
  v44.Flags = 0;
  v44.Type = 1;
  if ( *(_QWORD *)(a5 + 24) >= 8u )
    v8 = *(WCHAR **)a5;
  v44.TargetName = v8;
  v44.Comment = 0;
  do
    ++v24;
  while ( *(_WORD *)&a4[2 * v24] );
  v44.CredentialBlobSize = 2 * v24 + 2;
  v44.CredentialBlob = a4;
  *(_QWORD *)&v44.Persist = 2;
  memset(&v44.Attributes, 0, 24);
  if ( !CredWriteW(&v44, 0) )
  {
    if ( GetLastError() == 8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, 15083);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
      v36 = 0;
      v37 = 0;
      v38 = 15083;
      v39 = -1;
      v40 = 314;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, LastError);
    }
    v34 = 0;
    v35 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
    v36 = 0;
    v37 = 0;
    v38 = LastError;
    v39 = -1;
    v40 = 315;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  LOBYTE(v28) = 1;
  std::wstring::_Tidy(&v46, v28, 0);
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v51, v30, 0);
LABEL_51:
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v41);
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18001bdac  mov     [rsp-8+arg_0], rbx
0x18001bdb1  push    rbp
0x18001bdb2  push    rsi
0x18001bdb3  push    rdi
0x18001bdb4  push    r12
0x18001bdb6  push    r13
0x18001bdb8  push    r14
0x18001bdba  push    r15
0x18001bdbc  lea     rbp, [rsp-30h]
0x18001bdc1  sub     rsp, 130h
0x18001bdc8  mov     rax, cs:__security_cookie
0x18001bdcf  xor     rax, rsp
0x18001bdd2  mov     [rbp+60h+var_40], rax
0x18001bdd6  mov     r15, r9
0x18001bdd9  mov     r14, r8
0x18001bddc  mov     r12, rdx
0x18001bddf  mov     rdi, [rbp+60h+arg_20]
0x18001bde6  lea     rsi, CriticalSection
0x18001bded  mov     [rbp+60h+var_90], rsi
0x18001bdf1  mov     rcx, rsi; lpCriticalSection
0x18001bdf4  call    cs:__imp_EnterCriticalSection
0x18001bdfa  nop
0x18001bdfb  cmp     qword ptr [rdi+18h], 8
0x18001be00  jb      short loc_18001BE07
0x18001be02  mov     rcx, [rdi]
0x18001be05  jmp     short loc_18001BE0A
0x18001be07  mov     rcx, rdi
0x18001be0a  xor     r13d, r13d
0x18001be0d  mov     [rdi+10h], r13
0x18001be11  mov     [rcx], r13w
0x18001be15  call    GetCurrentThreadTokenAndRevertToSelf
0x18001be1a  mov     [rsp+160h+var_100], r13b
0x18001be1f  lea     rcx, RestoreAndCloseThreadToken
0x18001be26  mov     [rsp+160h+var_F8], rcx
0x18001be2b  mov     [rsp+160h+var_F0], rax
0x18001be30  mov     rdx, r12
0x18001be33  call    ?DeleteCredentialInt@CredentialManager@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CredentialManager::DeleteCredentialInt(std::wstring const &)
0x18001be38  mov     [rsp+160h+Credential], r13
0x18001be3d  mov     rbx, qword ptr cs:xmmword_18002F7D0
0x18001be44  mov     rbx, [rbx]
0x18001be47  cmp     rbx, qword ptr cs:xmmword_18002F7D0
0x18001be4e  jz      loc_18001BF53
0x18001be54  cmp     qword ptr [r14+18h], 8
0x18001be59  jb      short loc_18001BE60
0x18001be5b  mov     rdx, [r14]
0x18001be5e  jmp     short loc_18001BE63
0x18001be60  mov     rdx, r14; String2
0x18001be63  lea     rcx, [rbx+40h]
0x18001be67  cmp     qword ptr [rbx+58h], 8
0x18001be6c  jb      short loc_18001BE71
0x18001be6e  mov     rcx, [rcx]; String1
0x18001be71  call    cs:__imp__wcsicmp
0x18001be77  test    eax, eax
0x18001be79  jnz     short loc_18001BEF5
0x18001be7b  mov     [rsp+160h+Credential], r13
0x18001be80  lea     rsi, [rbx+20h]
0x18001be84  cmp     qword ptr [rbx+38h], 8
0x18001be89  jb      short loc_18001BE90
0x18001be8b  mov     rcx, [rsi]
0x18001be8e  jmp     short loc_18001BE93
0x18001be90  mov     rcx, rsi; TargetName
0x18001be93  lea     r9, [rsp+160h+Credential]; Credential
0x18001be98  xor     r8d, r8d; Flags
0x18001be9b  lea     edx, [r8+1]; Type
0x18001be9f  call    cs:__imp_CredReadW
0x18001bea5  test    eax, eax
0x18001bea7  jz      short loc_18001BEF5
0x18001bea9  mov     rcx, [rsp+160h+Credential]
0x18001beae  mov     byte ptr [rbp+60h+var_88], r13b
0x18001beb2  lea     rax, ReleaseCredentialBlob
0x18001beb9  mov     [rbp+60h+var_80], rax
0x18001bebd  mov     [rbp+60h+var_78], rcx
0x18001bec1  call    IsValidCredentialBlob
0x18001bec6  test    al, al
0x18001bec8  jz      short loc_18001BEEC
0x18001beca  mov     rax, r15
0x18001becd  mov     r8, [rcx+28h]
0x18001bed1  sub     r8, r15
0x18001bed4  movzx   edx, word ptr [rax]
0x18001bed7  movzx   ecx, word ptr [rax+r8]
0x18001bedc  sub     edx, ecx
0x18001bede  jnz     short loc_18001BEE8
0x18001bee0  add     rax, 2
0x18001bee4  test    ecx, ecx
0x18001bee6  jnz     short loc_18001BED4
0x18001bee8  test    edx, edx
0x18001beea  jz      short loc_18001BF31
0x18001beec  lea     rcx, [rbp+60h+var_88]
0x18001bef0  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001bef5  cmp     [rbx+19h], r13b
0x18001bef9  jnz     loc_18001BE47
0x18001beff  mov     rcx, [rbx+10h]
0x18001bf03  cmp     [rcx+19h], r13b
0x18001bf07  jnz     short loc_18001BF10
0x18001bf09  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<Subscription>>,void *> *)
0x18001bf0e  jmp     short loc_18001BF29
0x18001bf10  mov     rax, [rbx+8]
0x18001bf14  jmp     short loc_18001BF23
0x18001bf16  cmp     rbx, [rax+10h]
0x18001bf1a  jnz     short loc_18001BF29
0x18001bf1c  mov     rbx, rax
0x18001bf1f  mov     rax, [rax+8]
0x18001bf23  cmp     [rax+19h], r13b
0x18001bf27  jz      short loc_18001BF16
0x18001bf29  mov     rbx, rax
0x18001bf2c  jmp     loc_18001BE47
0x18001bf31  mov     rdx, rsi
0x18001bf34  mov     rcx, rdi
0x18001bf37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001bf3c  nop
0x18001bf3d  lea     rcx, [rbp+60h+var_88]
0x18001bf41  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001bf46  cmp     rbx, qword ptr cs:xmmword_18002F7D0
0x18001bf4d  jnz     loc_18001C19C
0x18001bf53  mov     ebx, 7
0x18001bf58  mov     [rbp+60h+var_48], rbx
0x18001bf5c  mov     [rbp+60h+var_50], r13
0x18001bf60  mov     [rbp+60h+var_60], r13w
0x18001bf65  lea     rcx, [rbp+60h+var_60]
0x18001bf69  call    ?CreateGuid@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CreateGuid(std::wstring &)
0x18001bf6e  lea     rdx, aEc; "EC::"
0x18001bf75  mov     rcx, rdi
0x18001bf78  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001bf7d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001bf81  mov     r9, rsi
0x18001bf84  xor     r8d, r8d
0x18001bf87  lea     rdx, [rbp+60h+var_60]
0x18001bf8b  mov     rcx, rdi
0x18001bf8e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001bf93  mov     rdx, r12
0x18001bf96  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@Uwstring_iless@CredentialManager@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring const &)
0x18001bf9b  mov     rcx, rax
0x18001bf9e  mov     rdx, rdi
0x18001bfa1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001bfa6  mov     [rbp+60h+var_70], rbx
0x18001bfaa  mov     [rbp+60h+var_78], r13
0x18001bfae  mov     [rbp+60h+var_88], r13w
0x18001bfb3  mov     rdx, r14
0x18001bfb6  lea     rcx, [rbp+60h+var_88]
0x18001bfba  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001bfbf  lea     r14d, [rbx-6]
0x18001bfc3  mov     [rbp+60h+var_68], r14d
0x18001bfc7  mov     rdx, rdi
0x18001bfca  lea     rcx, xmmword_18002F7D0
0x18001bfd1  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@Uwstring_iless@4@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@2@@std@@QEAAAEAUEntryInformation@CredentialManager@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,CredentialManager::EntryInformation,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,CredentialManager::EntryInformation>>>::operator[](std::wstring const &)
0x18001bfd6  mov     rbx, rax
0x18001bfd9  lea     rdx, [rbp+60h+var_88]
0x18001bfdd  mov     rcx, rax
0x18001bfe0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001bfe5  mov     ecx, [rbp+60h+var_68]
0x18001bfe8  mov     [rbx+20h], ecx
0x18001bfeb  mov     qword ptr [rbp+60h+var_E0.LastWritten.dwLowDateTime], r13
0x18001bfef  mov     dword ptr [rbp+60h+var_E0+24h], r13d
0x18001bff3  mov     [rbp+60h+var_E0.Flags], r13d
0x18001bff7  mov     [rbp+60h+var_E0.Type], r14d
0x18001bffb  cmp     qword ptr [rdi+18h], 8
0x18001c000  jb      short loc_18001C005
0x18001c002  mov     rdi, [rdi]
0x18001c005  mov     [rbp+60h+var_E0.TargetName], rdi
0x18001c009  mov     [rbp+60h+var_E0.Comment], r13
0x18001c00d  inc     rsi
0x18001c010  cmp     [r15+rsi*2], r13w
0x18001c015  jnz     short loc_18001C00D
0x18001c017  lea     eax, ds:2[rsi*2]
0x18001c01e  mov     [rbp+60h+var_E0.CredentialBlobSize], eax
0x18001c021  mov     [rbp+60h+var_E0.CredentialBlob], r15
0x18001c025  mov     qword ptr [rbp+60h+var_E0.Persist], 2
0x18001c02d  mov     [rbp+60h+var_E0.Attributes], r13
0x18001c031  xorps   xmm0, xmm0
0x18001c034  movdqa  xmmword ptr [rbp+60h+var_E0.TargetAlias], xmm0
0x18001c039  xor     edx, edx; Flags
0x18001c03b  lea     rcx, [rbp+60h+var_E0]; Credential
0x18001c03f  call    cs:__imp_CredWriteW
0x18001c045  test    eax, eax
0x18001c047  jnz     loc_18001C17B
0x18001c04d  call    cs:__imp_GetLastError
0x18001c053  cmp     eax, 8
0x18001c056  jnz     loc_18001C0E5
0x18001c05c  lea     rax, WPP_GLOBAL_Control
0x18001c063  mov     ebx, 3AEBh
0x18001c068  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c06f  cmp     rcx, rax
0x18001c072  jz      short loc_18001C098
0x18001c074  test    byte ptr [rcx+1Ch], 40h
0x18001c078  jz      short loc_18001C098
0x18001c07a  cmp     byte ptr [rcx+19h], 2
0x18001c07e  jb      short loc_18001C098
0x18001c080  mov     edx, 14h
0x18001c085  mov     r9d, ebx
0x18001c088  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001c08f  mov     rcx, [rcx+10h]
0x18001c093  call    WPP_SF_D
0x18001c098  mov     [rsp+160h+var_130], r13b
0x18001c09d  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001c0a4  mov     [rsp+160h+var_128], rax
0x18001c0a9  mov     [rsp+160h+var_120], r13
0x18001c0ae  mov     [rsp+160h+var_118], r13
0x18001c0b3  mov     [rsp+160h+var_110], ebx
0x18001c0b7  mov     [rsp+160h+var_10C], 0FFFFFFFFh
0x18001c0bf  mov     [rsp+160h+var_108], 13Ah
0x18001c0c7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c0ce  mov     [rsp+160h+pExceptionObject], rax
0x18001c0d3  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001c0da  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18001c0df  call    _CxxThrowException_0
0x18001c0e5  call    cs:__imp_GetLastError
0x18001c0eb  mov     ebx, eax
0x18001c0ed  mov     eax, 507h
0x18001c0f2  test    ebx, ebx
0x18001c0f4  cmovz   ebx, eax
0x18001c0f7  lea     rax, WPP_GLOBAL_Control
0x18001c0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c105  cmp     rcx, rax
0x18001c108  jz      short loc_18001C12E
0x18001c10a  test    byte ptr [rcx+1Ch], 40h
0x18001c10e  jz      short loc_18001C12E
0x18001c110  cmp     byte ptr [rcx+19h], 2
0x18001c114  jb      short loc_18001C12E
0x18001c116  mov     edx, 15h
0x18001c11b  mov     r9d, ebx
0x18001c11e  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001c125  mov     rcx, [rcx+10h]
0x18001c129  call    WPP_SF_D
0x18001c12e  mov     [rsp+160h+var_130], r13b
0x18001c133  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001c13a  mov     [rsp+160h+var_128], rax
0x18001c13f  mov     [rsp+160h+var_120], r13
0x18001c144  mov     [rsp+160h+var_118], r13
0x18001c149  mov     [rsp+160h+var_110], ebx
0x18001c14d  mov     [rsp+160h+var_10C], 0FFFFFFFFh
0x18001c155  mov     [rsp+160h+var_108], 13Bh
0x18001c15d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c164  mov     [rsp+160h+pExceptionObject], rax
0x18001c169  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001c170  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18001c175  call    _CxxThrowException_0
0x18001c17b  xor     r8d, r8d
0x18001c17e  mov     dl, r14b
0x18001c181  lea     rcx, [rbp+60h+var_88]
0x18001c185  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c18a  nop
0x18001c18b  xor     r8d, r8d
0x18001c18e  mov     dl, r14b
0x18001c191  lea     rcx, [rbp+60h+var_60]
0x18001c195  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c19a  jmp     short loc_18001C1B2
0x18001c19c  mov     rdx, r12
0x18001c19f  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@Uwstring_iless@CredentialManager@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring const &)
0x18001c1a4  mov     rcx, rax
0x18001c1a7  mov     rdx, rdi
0x18001c1aa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c1af  inc     dword ptr [rbx+60h]
0x18001c1b2  lea     rcx, [rsp+160h+var_100]
0x18001c1b7  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001c1bc  nop
0x18001c1bd  lea     rcx, CriticalSection; lpCriticalSection
0x18001c1c4  call    cs:__imp_LeaveCriticalSection
0x18001c1ca  mov     rcx, [rbp+60h+var_40]
0x18001c1ce  xor     rcx, rsp; StackCookie
0x18001c1d1  call    __security_check_cookie
0x18001c1d6  mov     rbx, [rsp+160h+arg_0]
0x18001c1de  add     rsp, 130h
0x18001c1e5  pop     r15
0x18001c1e7  pop     r14
0x18001c1e9  pop     r13
0x18001c1eb  pop     r12
0x18001c1ed  pop     rdi
0x18001c1ee  pop     rsi
0x18001c1ef  pop     rbp
0x18001c1f0  retn
```
