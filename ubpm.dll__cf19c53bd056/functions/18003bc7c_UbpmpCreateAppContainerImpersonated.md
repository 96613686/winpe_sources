# UbpmpCreateAppContainerImpersonated

- ea: `0x18003bc7c`
- end: `0x18003bfa6`
- name: `UbpmpCreateAppContainerImpersonated`
- size: `810`
- prototype: `__int64 __fastcall(unsigned __int16 *, PSID pSourceSid, PSID pSid1, int, __int64, struct _LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022054`

## callees

- `0x18000a6e0`
- `0x18000f9a0`
- `0x180016d80`
- `0x180019d90`
- `0x180032e38`
- `0x180034ec4`
- `0x18003bc7c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003bd52`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003bd52`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003bf72`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003bf72`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003bdfe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003bdfe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd0d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bece`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bd0d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bece`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bf86`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bf86`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003bcf8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003bcf8`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18003be80`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18003be80`
- `USERENV!DeleteAppContainerProfile` at `0x18003bf10`
- `USERENV!DeleteAppContainerProfile` at `0x18003bf10`
- `USERENV!CreateAppContainerProfile` at `0x18003be69`
- `USERENV!CreateAppContainerProfile` at `0x18003be69`

## pseudocode

```c
__int64 __fastcall UbpmpCreateAppContainerImpersonated(
        unsigned __int16 *a1,
        PSID pSourceSid,
        PSID pSid1,
        int a4,
        __int64 a5,
        struct _LIST_ENTRY **a6)
{
  int v7; // r12d
  PSID v8; // r13
  struct _LIST_ENTRY *Flink; // rdi
  __int64 v11; // rbp
  struct _LIST_ENTRY *v12; // r14
  struct _LIST_ENTRY *v13; // rbx
  __int64 v14; // rbp
  DWORD LengthSid; // edi
  unsigned __int16 *v16; // rax
  unsigned int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct _LIST_ENTRY *v20; // rdx
  int AppContainerProfile; // ebp
  struct _LIST_ENTRY *v22; // rax
  PSID pSid2[9]; // [rsp+30h] [rbp-48h] BYREF

  pSid2[0] = 0;
  v7 = a4;
  v8 = pSid1;
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_ContainerProfilesListLock);
  Flink = g_leContainerProfilesListHead.Flink;
  v11 = -1;
  if ( g_leContainerProfilesListHead.Flink != &g_leContainerProfilesListHead )
  {
    do
    {
      v12 = Flink->Flink;
      if ( CompareStringW(0x7Fu, 1u, a1, -1, (PCNZWCH)&Flink[2], -1) == 2 )
      {
        v13 = Flink;
        if ( EqualSid(pSourceSid, Flink[1].Blink) )
          break;
      }
      Flink = v12;
      v13 = 0;
    }
    while ( v12 != &g_leContainerProfilesListHead );
    v7 = a4;
    v8 = pSid1;
    if ( v13 )
      goto LABEL_35;
  }
  do
    ++v11;
  while ( a1[v11] );
  v14 = (unsigned int)(2 * v11 + 2);
  LengthSid = GetLengthSid(pSourceSid);
  v16 = (unsigned __int16 *)UbpmAlloc((unsigned int)v14 + LengthSid + 40);
  v13 = (struct _LIST_ENTRY *)v16;
  if ( v16 )
  {
    if ( (int)StringCbCopyW(v16 + 16, (unsigned int)v14, a1) < 0 )
    {
      v17 = 14;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v19 = 83;
LABEL_19:
      WPP_SF_d(v18[2], v19, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 14);
LABEL_31:
      UBPM_MIDL_user_free(v13);
      goto LABEL_36;
    }
    v20 = (struct _LIST_ENTRY *)((char *)v13 + v14 + 40);
    v13[1].Blink = v20;
    if ( !CopySid(LengthSid, v20, pSourceSid) )
    {
      v17 = 14;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v19 = 84;
      goto LABEL_19;
    }
    AppContainerProfile = CreateAppContainerProfile(a1, a1, a1, a5, v7, pSid2);
    if ( AppContainerProfile == -2147024713 )
      AppContainerProfile = DeriveAppContainerSidFromAppContainerName(a1, pSid2);
    if ( AppContainerProfile < 0 )
    {
      v17 = (unsigned __int16)AppContainerProfile;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          (_DWORD)a1,
          AppContainerProfile);
      goto LABEL_31;
    }
    if ( !EqualSid(v8, pSid2[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          (_DWORD)a1,
          AppContainerProfile);
      DeleteAppContainerProfile(a1);
      v17 = 5;
      goto LABEL_31;
    }
    v22 = off_18004C150[0];
    if ( off_18004C150[0]->Flink != &g_leContainerProfilesListHead )
      __fastfail(3u);
    v13->Flink = &g_leContainerProfilesListHead;
    v13->Blink = v22;
    v22->Flink = v13;
    off_18004C150[0] = v13;
LABEL_35:
    _InterlockedIncrement64((volatile signed __int64 *)&v13[1]);
    v17 = 0;
    *a6 = v13;
    goto LABEL_36;
  }
  v17 = 14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 14);
LABEL_36:
  if ( pSid2[0] )
    FreeSid(pSid2[0]);
  dword_18004CFA8 = 0;
  RtlReleaseSRWLockExclusive(&g_ContainerProfilesListLock);
  return v17;
}

```

## disassembly

```asm
0x18003bc7c  mov     rax, rsp
0x18003bc7f  mov     [rax+8], rbx
0x18003bc83  mov     [rax+20h], r9d
0x18003bc87  mov     [rax+18h], r8
0x18003bc8b  push    rbp
0x18003bc8c  push    rsi
0x18003bc8d  push    rdi
0x18003bc8e  push    r12
0x18003bc90  push    r13
0x18003bc92  push    r14
0x18003bc94  push    r15
0x18003bc96  sub     rsp, 40h
0x18003bc9a  mov     rsi, rcx
0x18003bc9d  xor     r14d, r14d
0x18003bca0  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18003bca7  mov     [rax-48h], r14
0x18003bcab  mov     r12d, r9d
0x18003bcae  mov     r13, r8
0x18003bcb1  mov     r15, rdx
0x18003bcb4  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18003bcb9  mov     rdi, cs:?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003bcc0  lea     rax, ?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003bcc7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18003bccb  cmp     rdi, rax
0x18003bcce  jz      short loc_18003BD3E
0x18003bcd0  xor     r12d, r12d
0x18003bcd3  lea     r13, ?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003bcda  mov     r14, [rdi]
0x18003bcdd  lea     rax, [rdi+20h]
0x18003bce1  mov     edx, 1; dwCmpFlags
0x18003bce6  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x18003bcea  mov     r9d, ebp; cchCount1
0x18003bced  mov     [rsp+78h+lpString2], rax; lpString2
0x18003bcf2  mov     r8, rsi; lpString1
0x18003bcf5  lea     ecx, [rdx+7Eh]; Locale
0x18003bcf8  call    cs:__imp_CompareStringW
0x18003bcfe  cmp     eax, 2
0x18003bd01  jnz     short loc_18003BD17
0x18003bd03  mov     rdx, [rdi+18h]; pSid2
0x18003bd07  mov     rcx, r15; pSid1
0x18003bd0a  mov     rbx, rdi
0x18003bd0d  call    cs:__imp_EqualSid
0x18003bd13  test    eax, eax
0x18003bd15  jnz     short loc_18003BD22
0x18003bd17  mov     rdi, r14
0x18003bd1a  mov     rbx, r12
0x18003bd1d  cmp     r14, r13
0x18003bd20  jnz     short loc_18003BCDA
0x18003bd22  mov     r12d, [rsp+78h+arg_18]
0x18003bd2a  mov     r13, [rsp+78h+arg_10]
0x18003bd32  test    rbx, rbx
0x18003bd35  jnz     loc_18003BF52
0x18003bd3b  xor     r14d, r14d
0x18003bd3e  inc     rbp
0x18003bd41  cmp     [rsi+rbp*2], r14w
0x18003bd46  jnz     short loc_18003BD3E
0x18003bd48  mov     rcx, r15; pSid
0x18003bd4b  lea     ebp, ds:2[rbp*2]
0x18003bd52  call    cs:__imp_GetLengthSid
0x18003bd58  mov     edi, eax
0x18003bd5a  lea     ecx, [rax+28h]
0x18003bd5d  add     ecx, ebp; Size
0x18003bd5f  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18003bd64  mov     rbx, rax
0x18003bd67  test    rax, rax
0x18003bd6a  jnz     short loc_18003BDAC
0x18003bd6c  lea     r9d, [rax+0Eh]
0x18003bd70  mov     edi, r9d
0x18003bd73  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd7a  lea     rax, WPP_GLOBAL_Control
0x18003bd81  cmp     rcx, rax
0x18003bd84  jz      loc_18003BF68
0x18003bd8a  test    byte ptr [rcx+1Ch], 1
0x18003bd8e  jz      loc_18003BF68
0x18003bd94  mov     rcx, [rcx+10h]
0x18003bd98  lea     edx, [rbx+52h]
0x18003bd9b  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003bda2  call    WPP_SF_d
0x18003bda7  jmp     loc_18003BF68
0x18003bdac  lea     rcx, [rax+20h]; unsigned __int16 *
0x18003bdb0  mov     edx, ebp; unsigned __int64
0x18003bdb2  mov     r8, rsi; unsigned __int16 *
0x18003bdb5  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bdba  test    eax, eax
0x18003bdbc  jns     short loc_18003BDEE
0x18003bdbe  mov     r9d, 0Eh
0x18003bdc4  mov     edi, r9d
0x18003bdc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bdce  lea     rax, WPP_GLOBAL_Control
0x18003bdd5  cmp     rcx, rax
0x18003bdd8  jz      loc_18003BF1B
0x18003bdde  test    byte ptr [rcx+1Ch], 1
0x18003bde2  jz      loc_18003BF1B
0x18003bde8  lea     edx, [r9+45h]
0x18003bdec  jmp     short loc_18003BE34
0x18003bdee  lea     rdx, [rbx+28h]
0x18003bdf2  mov     r8, r15; pSourceSid
0x18003bdf5  add     rdx, rbp; pDestinationSid
0x18003bdf8  mov     ecx, edi; nDestinationSidLength
0x18003bdfa  mov     [rbx+18h], rdx
0x18003bdfe  call    cs:__imp_CopySid
0x18003be04  test    eax, eax
0x18003be06  jnz     short loc_18003BE49
0x18003be08  lea     r9d, [rax+0Eh]
0x18003be0c  mov     edi, r9d
0x18003be0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be16  lea     rax, WPP_GLOBAL_Control
0x18003be1d  cmp     rcx, rax
0x18003be20  jz      loc_18003BF1B
0x18003be26  test    byte ptr [rcx+1Ch], 1
0x18003be2a  jz      loc_18003BF1B
0x18003be30  lea     edx, [r9+46h]
0x18003be34  mov     rcx, [rcx+10h]
0x18003be38  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003be3f  call    WPP_SF_d
0x18003be44  jmp     loc_18003BF1B
0x18003be49  mov     r9, [rsp+78h+arg_20]
0x18003be51  lea     rax, [rsp+78h+pSid2]
0x18003be56  mov     qword ptr [rsp+78h+cchCount2], rax
0x18003be5b  mov     r8, rsi
0x18003be5e  mov     rdx, rsi
0x18003be61  mov     dword ptr [rsp+78h+lpString2], r12d
0x18003be66  mov     rcx, rsi
0x18003be69  call    cs:__imp_CreateAppContainerProfile
0x18003be6f  mov     ebp, eax
0x18003be71  cmp     eax, 800700B7h
0x18003be76  jnz     short loc_18003BE88
0x18003be78  lea     rdx, [rsp+78h+pSid2]
0x18003be7d  mov     rcx, rsi
0x18003be80  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18003be86  mov     ebp, eax
0x18003be88  test    ebp, ebp
0x18003be8a  jns     short loc_18003BEC6
0x18003be8c  movzx   edi, bp
0x18003be8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be96  lea     rax, WPP_GLOBAL_Control
0x18003be9d  cmp     rcx, rax
0x18003bea0  jz      short loc_18003BF1B
0x18003bea2  test    byte ptr [rcx+1Ch], 1
0x18003bea6  jz      short loc_18003BF1B
0x18003bea8  mov     rcx, [rcx+10h]
0x18003beac  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003beb3  mov     edx, 55h ; 'U'
0x18003beb8  mov     dword ptr [rsp+78h+lpString2], ebp
0x18003bebc  mov     r9, rsi
0x18003bebf  call    WPP_SF_SL
0x18003bec4  jmp     short loc_18003BF1B
0x18003bec6  mov     rdx, [rsp+78h+pSid2]; pSid2
0x18003becb  mov     rcx, r13; pSid1
0x18003bece  call    cs:__imp_EqualSid
0x18003bed4  test    eax, eax
0x18003bed6  jnz     short loc_18003BF25
0x18003bed8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bedf  lea     rax, WPP_GLOBAL_Control
0x18003bee6  cmp     rcx, rax
0x18003bee9  jz      short loc_18003BF0D
0x18003beeb  test    byte ptr [rcx+1Ch], 1
0x18003beef  jz      short loc_18003BF0D
0x18003bef1  mov     rcx, [rcx+10h]
0x18003bef5  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003befc  mov     edx, 56h ; 'V'
0x18003bf01  mov     dword ptr [rsp+78h+lpString2], ebp
0x18003bf05  mov     r9, rsi
0x18003bf08  call    WPP_SF_SL
0x18003bf0d  mov     rcx, rsi
0x18003bf10  call    cs:__imp_DeleteAppContainerProfile
0x18003bf16  mov     edi, 5
0x18003bf1b  mov     rcx, rbx
0x18003bf1e  call    UBPM_MIDL_user_free
0x18003bf23  jmp     short loc_18003BF68
0x18003bf25  mov     rax, cs:off_18004C150
0x18003bf2c  lea     rcx, ?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003bf33  cmp     [rax], rcx
0x18003bf36  jz      short loc_18003BF3F
0x18003bf38  mov     ecx, 3
0x18003bf3d  int     29h; Win8: RtlFailFast(ecx)
0x18003bf3f  mov     [rbx], rcx
0x18003bf42  mov     [rbx+8], rax
0x18003bf46  mov     [rax], rbx
0x18003bf49  mov     cs:off_18004C150, rbx
0x18003bf50  jmp     short loc_18003BF55
0x18003bf52  xor     r14d, r14d
0x18003bf55  lock inc qword ptr [rbx+10h]
0x18003bf5a  mov     rax, [rsp+78h+arg_28]
0x18003bf62  mov     edi, r14d
0x18003bf65  mov     [rax], rbx
0x18003bf68  mov     rcx, [rsp+78h+pSid2]; pSid
0x18003bf6d  test    rcx, rcx
0x18003bf70  jz      short loc_18003BF78
0x18003bf72  call    cs:__imp_FreeSid
0x18003bf78  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_ContainerProfilesListLock
0x18003bf7f  mov     cs:dword_18004CFA8, r14d
0x18003bf86  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003bf8c  mov     rbx, [rsp+78h+arg_0]
0x18003bf94  mov     eax, edi
0x18003bf96  add     rsp, 40h
0x18003bf9a  pop     r15
0x18003bf9c  pop     r14
0x18003bf9e  pop     r13
0x18003bfa0  pop     r12
0x18003bfa2  pop     rdi
0x18003bfa3  pop     rsi
0x18003bfa4  pop     rbp
0x18003bfa5  retn
```
