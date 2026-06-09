# kfapi::IsShareWithAppContainerEnabledForToken(void *,_GUID const *,bool *)

- ea: `0x18020d6c0`
- end: `0x18020dac3`
- name: `?IsShareWithAppContainerEnabledForToken@kfapi@@YAJPEAXPEBU_GUID@@PEA_N@Z`
- size: `1027`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, const struct _GUID *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180137340`

## callees

- `0x1800432f0`
- `0x180060a10`
- `0x18020d6c0`
- `0x18020dacc`
- `0x18020dd38`
- `0x18020e060`
- `0x18020e1f0`
- `0x18020e500`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `ntdll!RtlQueryPackageClaims` at `0x18020d737`
- `ntdll!RtlQueryPackageClaims` at `0x18020d737`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18020d781`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18020d781`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18020d790`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18020d790`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18020d773`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18020d773`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18020d82b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18020d82b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020d971`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020daaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020d971`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020daaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020d850`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020d89f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020d9ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020da20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020d850`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020d89f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020d9ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18020da20`

## string_xrefs

- `0x18020da40`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020da8e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020d861`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall kfapi::IsShareWithAppContainerEnabledForToken(
        HANDLE TokenHandle,
        _QWORD *a2,
        const struct _GUID *a3,
        bool *a4)
{
  const char *v7; // r9
  PUCHAR SidSubAuthorityCount; // rax
  unsigned int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  bool v13; // r14
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  bool v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  char v40; // [rsp+88h] [rbp-78h]
  __int128 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h]
  __int64 v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int128 v48; // [rsp+D0h] [rbp-30h]
  int v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  __int64 v51; // [rsp+F0h] [rbp-10h]
  PSID TokenInformation[12]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v53[128]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  LOBYTE(a3->Data1) = 0;
  if ( !a2
    || (ReturnLength = 0, v35 = 256, v36 = 0, (int)RtlQueryPackageClaims(TokenHandle, v53, &v35, 0) < 0)
    || v35 <= 1
    || (v36 & 4) == 0 )
  {
LABEL_3:
    memset_0(TokenInformation, 0, 0x54u);
    v34 = 84;
    if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x54u, &v34) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x5B5,
               (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\utils.cpp",
               v7);
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    if ( *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1) != 4096 )
      LOBYTE(a3->Data1) = (unsigned int)AppModelPolicy::GetWinInetStoragePartitioningPolicy(TokenHandle) == 1966081;
    return 0;
  }
  v32 = 0;
  v38 = &v32;
  v39 = 0;
  v40 = 1;
  v10 = SRCacheManager_Open(0, &v39);
  if ( v40 )
  {
    v11 = *v38;
    *v38 = v39;
    if ( v11 )
      SRCacheManager_Close(v11);
  }
  if ( (v10 & 0x80000000) == 0 )
  {
    v42 = 0;
    v41 = 0;
    v48 = 0;
    v43 = 0;
    v44 = 0;
    v13 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v31 = 0;
    v37 = 0;
    v10 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v32,
            v53,
            &v37);
    if ( (v10 & 0x80000000) != 0 )
    {
      v24 = 1165;
    }
    else
    {
      v14 = v37;
      if ( !v37 )
        goto LABEL_25;
      v33 = 0;
      v15 = StateRepository::Cache::Entity::Package_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v32,
              v37,
              (struct StateRepository::Cache::Context_NoThrow *)&v33,
              &v31);
      v10 = v15;
      if ( v15 < 0 )
      {
        v25 = 1110;
      }
      else
      {
        v13 = v31;
        if ( !v31
          || (v15 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v33, &v41, 536, v14),
              v10 = v15,
              v15 >= 0) )
        {
          v17 = v33;
          v33 = 0;
          if ( v17 )
            SRCacheContext_Close(v17, v16);
LABEL_25:
          if ( v13 )
          {
            v18 = *a2 - *(_QWORD *)&FOLDERID_Cookies.Data1;
            if ( *a2 == *(_QWORD *)&FOLDERID_Cookies.Data1 )
              v18 = a2[1] - *(_QWORD *)FOLDERID_Cookies.Data4;
            if ( v18 )
            {
              v19 = *a2 - *(_QWORD *)&FOLDERID_InternetCache.Data1;
              if ( *a2 == *(_QWORD *)&FOLDERID_InternetCache.Data1 )
                v19 = a2[1] - *(_QWORD *)FOLDERID_InternetCache.Data4;
              if ( v19 )
              {
                v20 = *a2 - *(_QWORD *)&FOLDERID_History.Data1;
                if ( *a2 == *(_QWORD *)&FOLDERID_History.Data1 )
                  v20 = a2[1] - *(_QWORD *)FOLDERID_History.Data4;
                if ( v20 )
                  goto LABEL_35;
                v22 = (unsigned int)v44 >> 19;
              }
              else
              {
                v22 = (unsigned int)v44 >> 17;
              }
            }
            else
            {
              v22 = (unsigned int)v44 >> 18;
            }
            LOBYTE(a3->Data1) = (v22 & 1) == 0;
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
            v23 = v32;
            v32 = 0;
            if ( v23 )
              SRCacheManager_Close(v23);
            return 0;
          }
LABEL_35:
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
          v21 = v32;
          v32 = 0;
          if ( v21 )
            SRCacheManager_Close(v21);
          goto LABEL_3;
        }
        v25 = 1115;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v15,
        0);
      v27 = v33;
      v33 = 0;
      if ( v27 )
        SRCacheContext_Close(v27, v26);
      v24 = 1168;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v10,
      ReturnLength);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x597,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\utils.cpp",
      (const char *)v10,
      ReturnLengthb);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
    (const char *)v10,
    0);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58D,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\utils.cpp",
    (const char *)v10,
    ReturnLengtha);
LABEL_15:
  v12 = v32;
  v32 = 0;
  if ( v12 )
    SRCacheManager_Close(v12);
  return v10;
}

```

## disassembly

```asm
0x18020d6c0  mov     [rsp-8+arg_8], rbx
0x18020d6c5  push    rbp
0x18020d6c6  push    rsi
0x18020d6c7  push    rdi
0x18020d6c8  push    r12
0x18020d6ca  push    r13
0x18020d6cc  push    r14
0x18020d6ce  push    r15
0x18020d6d0  lea     rbp, [rsp-170h]
0x18020d6d8  sub     rsp, 270h
0x18020d6df  mov     rax, cs:__security_cookie
0x18020d6e6  xor     rax, rsp
0x18020d6e9  mov     [rbp+1A0h+var_40], rax
0x18020d6f0  xor     r13d, r13d
0x18020d6f3  mov     r15, r8
0x18020d6f6  mov     [r8], r13b
0x18020d6f9  mov     rdi, rdx
0x18020d6fc  mov     r12, rcx
0x18020d6ff  test    rdx, rdx
0x18020d702  jz      short loc_18020D745
0x18020d704  mov     [rsp+2A0h+var_268], r13
0x18020d709  lea     rax, [rsp+2A0h+var_238]
0x18020d70e  mov     [rsp+2A0h+var_270], rax
0x18020d713  lea     r8, [rsp+2A0h+var_240]
0x18020d718  mov     [rsp+2A0h+var_278], r13
0x18020d71d  lea     rdx, [rbp+1A0h+var_140]
0x18020d721  xor     r9d, r9d
0x18020d724  mov     [rsp+2A0h+ReturnLength], r13; int
0x18020d729  mov     [rsp+2A0h+var_240], 100h
0x18020d732  mov     [rsp+2A0h+var_238], r13
0x18020d737  call    cs:__imp_RtlQueryPackageClaims
0x18020d73d  test    eax, eax
0x18020d73f  jns     loc_18020D7F7
0x18020d745  mov     ebx, 54h ; 'T'
0x18020d74a  lea     rcx, [rbp+1A0h+TokenInformation]; void *
0x18020d74e  mov     r8d, ebx; Size
0x18020d751  xor     edx, edx; Val
0x18020d753  call    memset_0
0x18020d758  lea     rax, [rsp+2A0h+var_248]
0x18020d75d  mov     [rsp+2A0h+var_248], ebx
0x18020d761  mov     r9d, ebx; TokenInformationLength
0x18020d764  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18020d769  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x18020d76d  mov     rcx, r12; TokenHandle
0x18020d770  lea     edx, [rbx-3Bh]; TokenInformationClass
0x18020d773  call    cs:__imp_GetTokenInformation
0x18020d779  test    eax, eax
0x18020d77b  jz      short loc_18020D7DD
0x18020d77d  mov     rcx, [rbp+1A0h+TokenInformation]; pSid
0x18020d781  call    cs:__imp_GetSidSubAuthorityCount
0x18020d787  mov     rcx, [rbp+1A0h+TokenInformation]; pSid
0x18020d78b  movzx   edx, byte ptr [rax]
0x18020d78e  dec     edx; nSubAuthority
0x18020d790  call    cs:__imp_GetSidSubAuthority
0x18020d796  cmp     dword ptr [rax], 1000h
0x18020d79c  jz      short loc_18020D7B1
0x18020d79e  mov     rcx, r12
0x18020d7a1  call    ?GetWinInetStoragePartitioningPolicy@AppModelPolicy@@YA?AW4WinInetStoragePartitioningPolicy@1@PEAX@Z; AppModelPolicy::GetWinInetStoragePartitioningPolicy(void *)
0x18020d7a6  cmp     eax, 1E0001h
0x18020d7ab  setz    al
0x18020d7ae  mov     [r15], al
0x18020d7b1  xor     eax, eax
0x18020d7b3  mov     rcx, [rbp+1A0h+var_40]
0x18020d7ba  xor     rcx, rsp; StackCookie
0x18020d7bd  call    __security_check_cookie
0x18020d7c2  mov     rbx, [rsp+2A0h+arg_8]
0x18020d7ca  add     rsp, 270h
0x18020d7d1  pop     r15
0x18020d7d3  pop     r14
0x18020d7d5  pop     r13
0x18020d7d7  pop     r12
0x18020d7d9  pop     rdi
0x18020d7da  pop     rsi
0x18020d7db  pop     rbp
0x18020d7dc  retn
0x18020d7dd  mov     rcx, [rbp+1A8h]; this
0x18020d7e4  lea     r8, aOnecoreuapShel_46; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18020d7eb  mov     edx, 5B5h; void *
0x18020d7f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18020d7f5  jmp     short loc_18020D7B3
0x18020d7f7  cmp     [rsp+2A0h+var_240], 1
0x18020d7fd  jbe     loc_18020D745
0x18020d803  test    byte ptr [rsp+2A0h+var_238], 4
0x18020d808  jz      loc_18020D745
0x18020d80e  lea     rax, [rsp+2A0h+var_258]
0x18020d813  mov     [rsp+2A0h+var_258], r13
0x18020d818  lea     rdx, [rbp+1A0h+var_220]
0x18020d81c  mov     [rsp+2A0h+var_228], rax
0x18020d821  xor     ecx, ecx
0x18020d823  mov     [rbp+1A0h+var_220], r13
0x18020d827  mov     [rbp+1A0h+var_218], 1
0x18020d82b  call    cs:__imp_SRCacheManager_Open
0x18020d831  mov     ebx, eax
0x18020d833  cmp     [rbp+1A0h+var_218], r13b
0x18020d837  jz      short loc_18020D856
0x18020d839  mov     rdx, [rsp+2A0h+var_228]
0x18020d83e  mov     rcx, [rbp+1A0h+var_220]
0x18020d842  mov     rax, [rdx]
0x18020d845  mov     [rdx], rcx
0x18020d848  test    rax, rax
0x18020d84b  jz      short loc_18020D856
0x18020d84d  mov     rcx, rax
0x18020d850  call    cs:__imp_SRCacheManager_Close
0x18020d856  test    ebx, ebx
0x18020d858  jns     short loc_18020D8AC
0x18020d85a  mov     rcx, [rbp+1A8h]; this
0x18020d861  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020d868  mov     r9d, ebx; char *
0x18020d86b  mov     edx, 0A5h; void *
0x18020d870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d875  mov     rcx, [rbp+1A8h]; this
0x18020d87c  lea     r8, aOnecoreuapShel_46; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18020d883  mov     r9d, ebx; char *
0x18020d886  mov     edx, 58Dh; void *
0x18020d88b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d890  mov     rcx, [rsp+2A0h+var_258]
0x18020d895  mov     [rsp+2A0h+var_258], r13
0x18020d89a  test    rcx, rcx
0x18020d89d  jz      short loc_18020D8A5
0x18020d89f  call    cs:__imp_SRCacheManager_Close
0x18020d8a5  mov     eax, ebx
0x18020d8a7  jmp     loc_18020D7B3
0x18020d8ac  xorps   xmm0, xmm0
0x18020d8af  mov     [rbp+1A0h+var_200], r13
0x18020d8b3  lea     r8, [rsp+2A0h+var_230]; __int64 *
0x18020d8b8  movdqa  [rbp+1A0h+var_210], xmm0
0x18020d8bd  lea     rdx, [rbp+1A0h+var_140]; unsigned __int16 *
0x18020d8c1  movdqa  [rbp+1A0h+var_1D0], xmm0
0x18020d8c6  lea     rcx, [rsp+2A0h+var_258]; struct StateRepository::Cache::Manager_NoThrow *
0x18020d8cb  mov     [rbp+1A0h+var_1F8], r13
0x18020d8cf  mov     [rbp+1A0h+var_1F0], r13
0x18020d8d3  mov     r14b, r13b
0x18020d8d6  mov     [rbp+1A0h+var_1E8], r13
0x18020d8da  mov     [rbp+1A0h+var_1E0], r13
0x18020d8de  mov     [rbp+1A0h+var_1D8], r13
0x18020d8e2  mov     [rbp+1A0h+var_1C0], r13d
0x18020d8e6  mov     [rbp+1A0h+var_1B8], r13
0x18020d8ea  mov     [rbp+1A0h+var_1B0], r13
0x18020d8ee  mov     [rsp+2A0h+var_260], r13b
0x18020d8f3  mov     [rsp+2A0h+var_230], r13
0x18020d8f8  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18020d8fd  mov     ebx, eax
0x18020d8ff  test    eax, eax
0x18020d901  js      loc_18020DA3B
0x18020d907  mov     rsi, [rsp+2A0h+var_230]
0x18020d90c  test    rsi, rsi
0x18020d90f  jz      short loc_18020D977
0x18020d911  lea     r9, [rsp+2A0h+var_260]; bool *
0x18020d916  mov     [rsp+2A0h+var_250], r13
0x18020d91b  lea     r8, [rsp+2A0h+var_250]; struct StateRepository::Cache::Context_NoThrow *
0x18020d920  mov     rdx, rsi; __int64
0x18020d923  lea     rcx, [rsp+2A0h+var_258]; struct StateRepository::Cache::Manager_NoThrow *
0x18020d928  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18020d92d  mov     ebx, eax
0x18020d92f  test    eax, eax
0x18020d931  js      loc_18020DA82
0x18020d937  mov     r14b, [rsp+2A0h+var_260]
0x18020d93c  test    r14b, r14b
0x18020d93f  jz      short loc_18020D962
0x18020d941  mov     r9, rsi
0x18020d944  lea     rdx, [rbp+1A0h+var_210]
0x18020d948  mov     r8d, 218h
0x18020d94e  lea     rcx, [rsp+2A0h+var_250]
0x18020d953  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x18020d958  mov     ebx, eax
0x18020d95a  test    eax, eax
0x18020d95c  js      loc_18020DABC
0x18020d962  mov     rcx, [rsp+2A0h+var_250]
0x18020d967  mov     [rsp+2A0h+var_250], r13
0x18020d96c  test    rcx, rcx
0x18020d96f  jz      short loc_18020D977
0x18020d971  call    cs:__imp_SRCacheContext_Close
0x18020d977  test    r14b, r14b
0x18020d97a  jz      short loc_18020D9D0
0x18020d97c  mov     rax, [rdi]
0x18020d97f  sub     rax, qword ptr cs:FOLDERID_Cookies.Data1
0x18020d986  jnz     short loc_18020D993
0x18020d988  mov     rax, [rdi+8]
0x18020d98c  sub     rax, qword ptr cs:FOLDERID_Cookies.Data4
0x18020d993  test    rax, rax
0x18020d996  jz      short loc_18020D9F7
0x18020d998  mov     rax, [rdi]
0x18020d99b  sub     rax, qword ptr cs:FOLDERID_InternetCache.Data1
0x18020d9a2  jnz     short loc_18020D9AF
0x18020d9a4  mov     rax, [rdi+8]
0x18020d9a8  sub     rax, qword ptr cs:FOLDERID_InternetCache.Data4
0x18020d9af  test    rax, rax
0x18020d9b2  jz      short loc_18020DA2B
0x18020d9b4  mov     rax, [rdi]
0x18020d9b7  sub     rax, qword ptr cs:FOLDERID_History.Data1
0x18020d9be  jnz     short loc_18020D9CB
0x18020d9c0  mov     rax, [rdi+8]
0x18020d9c4  sub     rax, qword ptr cs:FOLDERID_History.Data4
0x18020d9cb  test    rax, rax
0x18020d9ce  jz      short loc_18020DA33
0x18020d9d0  lea     rcx, [rbp+1A0h+var_210]; this
0x18020d9d4  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18020d9d9  mov     rcx, [rsp+2A0h+var_258]
0x18020d9de  mov     [rsp+2A0h+var_258], r13
0x18020d9e3  test    rcx, rcx
0x18020d9e6  jz      loc_18020D745
0x18020d9ec  call    cs:__imp_SRCacheManager_Close
0x18020d9f2  jmp     loc_18020D745
0x18020d9f7  mov     eax, dword ptr [rbp+1A0h+var_1F0]
0x18020d9fa  shr     eax, 12h
0x18020d9fd  not     al
0x18020d9ff  lea     rcx, [rbp+1A0h+var_210]; this
0x18020da03  and     al, 1
0x18020da05  mov     [r15], al
0x18020da08  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18020da0d  mov     rcx, [rsp+2A0h+var_258]
0x18020da12  mov     [rsp+2A0h+var_258], r13
0x18020da17  test    rcx, rcx
0x18020da1a  jz      loc_18020D7B1
0x18020da20  call    cs:__imp_SRCacheManager_Close
0x18020da26  jmp     loc_18020D7B1
0x18020da2b  mov     eax, dword ptr [rbp+1A0h+var_1F0]
0x18020da2e  shr     eax, 11h
0x18020da31  jmp     short loc_18020D9FD
0x18020da33  mov     eax, dword ptr [rbp+1A0h+var_1F0]
0x18020da36  shr     eax, 13h
0x18020da39  jmp     short loc_18020D9FD
0x18020da3b  mov     edx, 48Dh; void *
0x18020da40  lea     rdi, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020da47  mov     rcx, [rbp+1A8h]; this
0x18020da4e  mov     r9d, ebx; char *
0x18020da51  mov     r8, rdi; unsigned int
0x18020da54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020da59  mov     rcx, [rbp+1A8h]; this
0x18020da60  lea     r8, aOnecoreuapShel_46; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18020da67  mov     r9d, ebx; char *
0x18020da6a  mov     edx, 597h; void *
0x18020da6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020da74  lea     rcx, [rbp+1A0h+var_210]; this
0x18020da78  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18020da7d  jmp     loc_18020D890
0x18020da82  mov     edx, 456h; void *
0x18020da87  mov     rcx, [rbp+1A8h]; this
0x18020da8e  lea     rdi, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020da95  mov     r8, rdi; unsigned int
0x18020da98  mov     r9d, eax; char *
0x18020da9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020daa0  mov     rcx, [rsp+2A0h+var_250]
0x18020daa5  mov     [rsp+2A0h+var_250], r13
0x18020daaa  test    rcx, rcx
0x18020daad  jz      short loc_18020DAB5
0x18020daaf  call    cs:__imp_SRCacheContext_Close
0x18020dab5  mov     edx, 490h
0x18020daba  jmp     short loc_18020DA47
0x18020dabc  mov     edx, 45Bh
0x18020dac1  jmp     short loc_18020DA87
```
