# ProfileManager::ReferencePcbListEx(int,void *,void *,_GUID const *,ulong,PM_PCB_LIST * *)

- ea: `0x18000bfa0`
- end: `0x18000c58f`
- name: `?ReferencePcbListEx@ProfileManager@@AEAAKHPEAX0PEBU_GUID@@KPEAPEAUPM_PCB_LIST@@@Z`
- size: `1519`
- prototype: `__int64 __fastcall(ProfileManager *this, void *, void *, void *, const struct _GUID *Buf2, unsigned int, struct PM_PCB_LIST **)`
- caller_count: `19`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017530`
- `0x1800186a8`
- `0x18003a9b8`
- `0x18003add8`
- `0x18003b91c`
- `0x18003e670`
- `0x18003efb0`
- `0x180057b30`
- `0x1800b76c4`
- `0x1800b938c`
- `0x1800c4c98`
- `0x1800c9a24`
- `0x1800f875c`
- `0x1800fa22c`
- `0x1800fb890`
- `0x1800fdd28`
- `0x180100be8`
- `0x1801fbfc0`
- `0x1801fd6a0`

## callees

- `0x18000a994`
- `0x18000aa0c`
- `0x18000bfa0`
- `0x18000c5a0`
- `0x18000c800`
- `0x18000cad0`
- `0x180011530`
- `0x1800288f0`
- `0x18003c4b0`
- `0x1800c6774`
- `0x1800cbfd8`
- `0x1800ee3d4`
- `0x180103e24`
- `0x18010730c`
- `0x1801fabbc`
- `0x1801faf34`
- `0x1801fb274`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c116`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c116`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c103`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c103`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c37a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c460`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c37a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c383`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c0de`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c0de`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c07f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c07f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c090`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c090`

## pseudocode

```c
__int64 __fastcall ProfileManager::ReferencePcbListEx(
        ProfileManager *this,
        void *a2,
        void *a3,
        void *a4,
        const struct _GUID *Buf2,
        unsigned int a6,
        struct PM_PCB_LIST **a7)
{
  std::_Ref_count_base *v9; // r10
  void *v10; // rbx
  DWORD TokenUserInfo; // esi
  void *v12; // rdi
  PSID v13; // rsi
  DWORD LengthSid; // r12d
  void *v15; // r14
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  void *v18; // rcx
  char *v19; // rdi
  char *v20; // rsi
  bool v21; // al
  char *v22; // rax
  __int64 v23; // rax
  std::_Ref_count_base *v24; // rcx
  volatile signed __int32 *v25; // rbx
  struct PM_PCB_LIST **v26; // rbx
  struct PM_PCB_LIST **v27; // r14
  struct PM_PCB_LIST *v28; // rdi
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdx
  unsigned int ready; // eax
  const char *v33; // r9
  std::_Ref_count_base *v34; // rbx
  __int64 result; // rax
  std::_Ref_count_base *v36; // rcx
  volatile signed __int32 *v37; // rbx
  const struct ProfileUser *IfNeeded; // rax
  __int64 v39; // rcx
  std::_Ref_count_base *v40; // rcx
  __int64 *v41; // rax
  _QWORD *v42; // rdx
  __int64 v43; // rcx
  unsigned int v44[2]; // [rsp+20h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-60h] BYREF
  int v46; // [rsp+30h] [rbp-58h] BYREF
  std::_Ref_count_base *v47[2]; // [rsp+38h] [rbp-50h]
  unsigned int *v48; // [rsp+48h] [rbp-40h]
  void *v49; // [rsp+50h] [rbp-38h]
  char v50; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v46 = ProfileUser::s_unspecifiedUser;
  *(_OWORD *)v47 = 0;
  v9 = qword_1802A06D8;
  if ( qword_1802A06D8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_1802A06D8 + 2);
    v9 = qword_1802A06D8;
  }
  try
  {
    v47[0] = (std::_Ref_count_base *)qword_1802A06D0;
    v47[1] = v9;
    if ( (_DWORD)a2 )
    {
      v46 = ProfileUser::s_wcmUser;
      v36 = qword_1802A06C0;
      if ( qword_1802A06C0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)qword_1802A06C0 + 2);
        v36 = qword_1802A06C0;
      }
      v47[0] = (std::_Ref_count_base *)qword_1802A06B8;
      v37 = (volatile signed __int32 *)v47[1];
      v47[1] = v36;
      if ( v37 && _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v37);
      }
    }
    else
    {
      if ( !a4 )
      {
        if ( !a3 )
        {
          v19 = (char *)&ProfileUser::s_unspecifiedUser;
LABEL_33:
          v46 = *(_DWORD *)v19;
          v23 = *((_QWORD *)v19 + 2);
          if ( v23 )
            _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
          v24 = (std::_Ref_count_base *)*((_QWORD *)v19 + 2);
          v47[0] = *((std::_Ref_count_base **)v19 + 1);
          v25 = (volatile signed __int32 *)v47[1];
          v47[1] = v24;
          if ( v25 && _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *, void *))v25)(v25, a2);
            std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v25);
          }
          goto LABEL_38;
        }
        *(_QWORD *)v44 = 0;
        v48 = v44;
        v50 = 1;
        lpMem = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids);
        }
        v10 = 0;
        v49 = 0;
        TokenUserInfo = GetTokenUserInfo(a3, (struct _TOKEN_USER **)&lpMem);
        v12 = lpMem;
        if ( !TokenUserInfo )
        {
          v13 = *(PSID *)lpMem;
          if ( *(_QWORD *)lpMem && IsValidSid(*(PSID *)lpMem) )
          {
            LengthSid = GetLengthSid(v13);
            if ( LengthSid )
            {
              v15 = 0;
              ProcessHeap = GetProcessHeap();
              if ( ProcessHeap && (v15 = HeapAlloc(ProcessHeap, 8u, LengthSid)) == 0 )
              {
                SetLastError(8u);
              }
              else if ( v15 && CopySid(LengthSid, v15, v13) )
              {
                TokenUserInfo = 0;
                v10 = v15;
                v49 = v15;
                goto LABEL_17;
              }
            }
            else
            {
              SetLastError(0x57u);
              v15 = 0;
            }
            TokenUserInfo = GetLastError();
            if ( TokenUserInfo && v15 )
              FreeWLMem(v15);
            goto LABEL_17;
          }
          TokenUserInfo = 87;
        }
LABEL_17:
        if ( v12 )
        {
          v17 = GetProcessHeap();
          if ( v17 )
            HeapFree(v17, 0, v12);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            23,
            WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids,
            TokenUserInfo);
        }
        if ( TokenUserInfo )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x5E6,
            (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
            (const char *)TokenUserInfo,
            v44[0]);
        v18 = *(void **)v44;
        *(_QWORD *)v44 = v10;
        if ( v18 )
        {
          FreeWLMem(v18);
          v10 = *(void **)v44;
        }
        a2 = v10;
        lpMem = v10;
        v19 = (char *)*((_QWORD *)this + 5);
        v20 = (char *)*((_QWORD *)this + 6);
        if ( v19 != v20 )
        {
          do
          {
            if ( !a2 || *(_DWORD *)v19 )
            {
              v21 = 0;
            }
            else
            {
              v21 = (unsigned int)wlansvc::profile::g_shim(*((_QWORD *)v19 + 1)) != 0;
              a2 = lpMem;
            }
            if ( v21 )
              break;
            v19 += 24;
          }
          while ( v19 != v20 );
          v10 = *(void **)v44;
        }
        v22 = (char *)*((_QWORD *)this + 6);
        if ( v19 == v22 )
        {
          if ( v22 == *((char **)this + 7) )
          {
            std::vector<ProfileUser>::_Emplace_reallocate<void * &>((char *)this + 40, *((_QWORD *)this + 6), &lpMem);
          }
          else
          {
            ProfileUser::ProfileUser(*((ProfileUser **)this + 6), a2);
            *((_QWORD *)this + 6) += 24LL;
          }
          v19 = (char *)(*((_QWORD *)this + 6) - 24LL);
          v10 = *(void **)v44;
        }
        if ( v10 )
          FreeWLMem(v10);
        goto LABEL_33;
      }
      IfNeeded = ProfileManager::FindUserAndCreateIfNeeded(this, a4);
      v46 = *(_DWORD *)IfNeeded;
      v39 = *((_QWORD *)IfNeeded + 2);
      if ( v39 )
        _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
      a2 = (void *)*((_QWORD *)IfNeeded + 2);
      v47[0] = *((std::_Ref_count_base **)IfNeeded + 1);
      v40 = v47[1];
      v47[1] = (std::_Ref_count_base *)a2;
      if ( v40 )
        std::_Ref_count_base::_Decref(v40);
    }
LABEL_38:
    v26 = (struct PM_PCB_LIST **)*((_QWORD *)this + 29);
    v27 = (struct PM_PCB_LIST **)*((_QWORD *)this + 30);
    while ( v26 != v27 )
    {
      v28 = *v26;
      if ( !memcmp_0((char *)*v26 + 96, Buf2, 0x10u) )
      {
        if ( v28 )
        {
          v31 = a6;
          goto LABEL_43;
        }
        break;
      }
      ++v26;
    }
    v41 = (__int64 *)std::make_unique<PM_PCB_LIST,,0>(&lpMem, a2);
    v42 = (_QWORD *)*((_QWORD *)this + 30);
    if ( v42 == *((_QWORD **)this + 31) )
    {
      std::vector<std::unique_ptr<PM_PCB_LIST>>::_Emplace_reallocate<std::unique_ptr<PM_PCB_LIST>>(
        (char *)this + 232,
        v42,
        v41);
    }
    else
    {
      v43 = *v41;
      *v41 = 0;
      *v42 = v43;
      *((_QWORD *)this + 30) += 8LL;
    }
    std::unique_ptr<PM_PCB_LIST>::~unique_ptr<PM_PCB_LIST>(&lpMem);
    *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 30) - 8LL) + 165LL) = 1;
    *(struct _GUID *)(*(_QWORD *)(*((_QWORD *)this + 30) - 8LL) + 96LL) = *Buf2;
    v29 = *(_QWORD *)(*((_QWORD *)this + 30) - 8LL);
    v31 = a6;
    *(_DWORD *)(v29 + 160) = a6;
    v28 = *(struct PM_PCB_LIST **)(*((_QWORD *)this + 30) - 8LL);
LABEL_43:
    if ( (_DWORD)v31 != *((_DWORD *)v28 + 40) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v29, v31, v30);
    ready = ProfileManager::ReadyUserPcbList(this, v28, (const struct ProfileUser *)&v46);
    if ( ready )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x740,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
        (const char *)ready,
        v44[0]);
    *a7 = v28;
    v34 = v47[1];
    if ( v47[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v47[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v34)(v34);
      std::_Ref_count_base::_Decwref(v34);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Win32_Return_CaughtException(
                           retaddr,
                           (void *)0x747,
                           (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                           v33);
  }
  return result;
}

```

## disassembly

```asm
0x18000bfa0  mov     [rsp+arg_0], rbx
0x18000bfa5  mov     [rsp+arg_10], rsi
0x18000bfaa  push    rdi
0x18000bfab  push    r12
0x18000bfad  push    r13
0x18000bfaf  push    r14
0x18000bfb1  push    r15
0x18000bfb3  sub     rsp, 60h
0x18000bfb7  mov     rdi, r8
0x18000bfba  mov     r15, rcx
0x18000bfbd  mov     eax, cs:?s_unspecifiedUser@ProfileUser@@2V1@B; ProfileUser const ProfileUser::s_unspecifiedUser
0x18000bfc3  mov     [rsp+88h+var_58], eax
0x18000bfc7  xorps   xmm0, xmm0
0x18000bfca  movdqu  xmmword ptr [rsp+88h+var_50], xmm0
0x18000bfd0  mov     r10, cs:qword_1802A06D8
0x18000bfd7  test    r10, r10
0x18000bfda  jz      short loc_18000BFE8
0x18000bfdc  lock inc dword ptr [r10+8]
0x18000bfe1  mov     r10, cs:qword_1802A06D8
0x18000bfe8  mov     rax, cs:qword_1802A06D0
0x18000bfef  mov     [rsp+88h+var_50], rax
0x18000bff4  mov     [rsp+88h+var_50+8], r10
0x18000bff9  test    edx, edx
0x18000bffb  jnz     loc_18000C305
0x18000c001  test    r9, r9
0x18000c004  jnz     loc_18000C3D3
0x18000c00a  xor     r13d, r13d
0x18000c00d  test    rdi, rdi
0x18000c010  jz      loc_18000C369
0x18000c016  mov     qword ptr [rsp+88h+var_68], r13; unsigned int
0x18000c01b  lea     rax, [rsp+88h+var_68]
0x18000c020  mov     [rsp+88h+var_40], rax
0x18000c025  mov     [rsp+88h+var_30], 1
0x18000c02a  mov     [rsp+88h+lpMem], r13
0x18000c02f  lea     r14, WPP_GLOBAL_Control
0x18000c036  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c03d  cmp     rcx, r14
0x18000c040  jz      short loc_18000C04C
0x18000c042  cmp     byte ptr [rcx+69h], 4
0x18000c046  jnb     loc_18000C437
0x18000c04c  mov     rbx, r13
0x18000c04f  mov     [rsp+88h+var_38], rbx
0x18000c054  lea     rdx, [rsp+88h+lpMem]; struct _TOKEN_USER **
0x18000c059  mov     rcx, rdi; TokenHandle
0x18000c05c  call    ?GetTokenUserInfo@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserInfo(void *,_TOKEN_USER * *)
0x18000c061  mov     esi, eax
0x18000c063  mov     rdi, [rsp+88h+lpMem]
0x18000c068  test    eax, eax
0x18000c06a  jnz     loc_18000C0FE
0x18000c070  mov     rsi, [rdi]
0x18000c073  test    rsi, rsi
0x18000c076  jz      loc_18000C46B
0x18000c07c  mov     rcx, rsi; pSid
0x18000c07f  call    cs:__imp_IsValidSid
0x18000c085  test    eax, eax
0x18000c087  jz      loc_18000C46B
0x18000c08d  mov     rcx, rsi; pSid
0x18000c090  call    cs:__imp_GetLengthSid
0x18000c096  mov     r12d, eax
0x18000c099  test    eax, eax
0x18000c09b  jz      loc_18000C375
0x18000c0a1  mov     r14, r13
0x18000c0a4  call    cs:__imp_GetProcessHeap
0x18000c0aa  test    rax, rax
0x18000c0ad  jz      short loc_18000C0CC
0x18000c0af  mov     r8d, r12d; dwBytes
0x18000c0b2  mov     edx, 8; dwFlags
0x18000c0b7  mov     rcx, rax; hHeap
0x18000c0ba  call    cs:__imp_HeapAlloc
0x18000c0c0  mov     r14, rax
0x18000c0c3  test    rax, rax
0x18000c0c6  jz      loc_18000C45B
0x18000c0cc  test    r14, r14
0x18000c0cf  jz      loc_18000C383
0x18000c0d5  mov     r8, rsi; pSourceSid
0x18000c0d8  mov     rdx, r14; pDestinationSid
0x18000c0db  mov     ecx, r12d; nDestinationSidLength
0x18000c0de  call    cs:__imp_CopySid
0x18000c0e4  test    eax, eax
0x18000c0e6  jz      loc_18000C383
0x18000c0ec  mov     esi, r13d
0x18000c0ef  mov     rbx, r14
0x18000c0f2  mov     [rsp+88h+var_38], rbx
0x18000c0f7  lea     r14, WPP_GLOBAL_Control
0x18000c0fe  test    rdi, rdi
0x18000c101  jz      short loc_18000C11C
0x18000c103  call    cs:__imp_GetProcessHeap
0x18000c109  test    rax, rax
0x18000c10c  jz      short loc_18000C11C
0x18000c10e  mov     r8, rdi; lpMem
0x18000c111  xor     edx, edx; dwFlags
0x18000c113  mov     rcx, rax; hHeap
0x18000c116  call    cs:__imp_HeapFree
0x18000c11c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c123  cmp     rcx, r14
0x18000c126  jnz     loc_18000C2C2
0x18000c12c  mov     rcx, [rsp+88h]; this
0x18000c134  test    esi, esi
0x18000c136  jnz     loc_18000C3BE
0x18000c13c  mov     rcx, qword ptr [rsp+88h+var_68]
0x18000c141  mov     qword ptr [rsp+88h+var_68], rbx; unsigned int
0x18000c146  test    rcx, rcx
0x18000c149  jz      short loc_18000C155
0x18000c14b  call    FreeWLMem
0x18000c150  mov     rbx, qword ptr [rsp+88h+var_68]
0x18000c155  mov     rdx, rbx
0x18000c158  mov     [rsp+88h+lpMem], rbx
0x18000c15d  mov     rdi, [r15+28h]
0x18000c161  mov     rsi, [r15+30h]
0x18000c165  cmp     rdi, rsi
0x18000c168  jz      short loc_18000C1A3
0x18000c16a  test    rdx, rdx
0x18000c16d  jz      loc_18000C362
0x18000c173  cmp     dword ptr [rdi], 0
0x18000c176  jnz     loc_18000C362
0x18000c17c  mov     rcx, [rdi+8]
0x18000c180  mov     rax, cs:?g_shim@profile@wlansvc@@3UWin32Shim@12@A; wlansvc::profile::Win32Shim wlansvc::profile::g_shim
0x18000c187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c18c  test    eax, eax
0x18000c18e  setnz   al
0x18000c191  mov     rdx, [rsp+88h+lpMem]; void *
0x18000c196  test    al, al
0x18000c198  jz      loc_18000C2F3
0x18000c19e  mov     rbx, qword ptr [rsp+88h+var_68]
0x18000c1a3  mov     rax, [r15+30h]
0x18000c1a7  cmp     rdi, rax
0x18000c1aa  jz      loc_18000C475
0x18000c1b0  test    rbx, rbx
0x18000c1b3  jz      short loc_18000C1BE
0x18000c1b5  mov     rcx, rbx
0x18000c1b8  call    FreeWLMem
0x18000c1bd  nop
0x18000c1be  mov     eax, [rdi]
0x18000c1c0  mov     [rsp+88h+var_58], eax
0x18000c1c4  mov     rax, [rdi+10h]
0x18000c1c8  test    rax, rax
0x18000c1cb  jz      short loc_18000C1D1
0x18000c1cd  lock inc dword ptr [rax+8]
0x18000c1d1  mov     rcx, [rdi+10h]
0x18000c1d5  mov     rax, [rdi+8]
0x18000c1d9  mov     [rsp+88h+var_50], rax
0x18000c1de  mov     rbx, [rsp+88h+var_50+8]
0x18000c1e3  mov     [rsp+88h+var_50+8], rcx
0x18000c1e8  test    rbx, rbx
0x18000c1eb  jz      loc_18000C412
0x18000c1f1  mov     esi, 0FFFFFFFFh
0x18000c1f6  mov     eax, esi
0x18000c1f8  lock xadd [rbx+8], eax
0x18000c1fd  cmp     eax, 1
0x18000c200  jz      loc_18000C4AD
0x18000c206  mov     rbx, [r15+0E8h]
0x18000c20d  mov     r14, [r15+0F0h]
0x18000c214  mov     r12, [rsp+88h+Buf2]
0x18000c21c  cmp     rbx, r14
0x18000c21f  jz      loc_18000C4C8
0x18000c225  mov     rdi, [rbx]
0x18000c228  lea     rcx, [rdi+60h]; Buf1
0x18000c22c  mov     r8d, 10h; Size
0x18000c232  mov     rdx, r12; Buf2
0x18000c235  call    memcmp_0
0x18000c23a  test    eax, eax
0x18000c23c  jnz     short loc_18000C2B9
0x18000c23e  test    rdi, rdi
0x18000c241  jz      loc_18000C4C8
0x18000c247  mov     edx, [rsp+88h+arg_28]
0x18000c24e  cmp     edx, [rdi+0A0h]
0x18000c254  jnz     loc_18000C55E
0x18000c25a  lea     r8, [rsp+88h+var_58]; struct ProfileUser *
0x18000c25f  mov     rdx, rdi; struct PM_PCB_LIST *
0x18000c262  mov     rcx, r15; this
0x18000c265  call    ?ReadyUserPcbList@ProfileManager@@AEAAKPEAUPM_PCB_LIST@@AEBVProfileUser@@@Z; ProfileManager::ReadyUserPcbList(PM_PCB_LIST *,ProfileUser const &)
0x18000c26a  mov     rcx, [rsp+88h]; this
0x18000c272  test    eax, eax
0x18000c274  jnz     loc_18000C3A9
0x18000c27a  mov     rax, [rsp+88h+arg_30]
0x18000c282  mov     [rax], rdi
0x18000c285  mov     rbx, [rsp+88h+var_50+8]
0x18000c28a  test    rbx, rbx
0x18000c28d  jz      short loc_18000C29D
0x18000c28f  lock xadd [rbx+8], esi
0x18000c294  cmp     esi, 1
0x18000c297  jz      loc_18000C568
0x18000c29d  xor     eax, eax
0x18000c29f  lea     r11, [rsp+88h+var_28]
0x18000c2a4  mov     rbx, [r11+30h]
0x18000c2a8  mov     rsi, [r11+40h]
0x18000c2ac  mov     rsp, r11
0x18000c2af  pop     r15
0x18000c2b1  pop     r14
0x18000c2b3  pop     r13
0x18000c2b5  pop     r12
0x18000c2b7  pop     rdi
0x18000c2b8  retn
0x18000c2b9  add     rbx, 8
0x18000c2bd  jmp     loc_18000C21C
0x18000c2c2  cmp     byte ptr [rcx+69h], 4
0x18000c2c6  jb      loc_18000C12C
0x18000c2cc  test    byte ptr [rcx+6Ch], 1
0x18000c2d0  jz      loc_18000C12C
0x18000c2d6  mov     edx, 17h
0x18000c2db  mov     r9d, esi
0x18000c2de  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c2e5  mov     rcx, [rcx+60h]
0x18000c2e9  call    WPP_SF_d
0x18000c2ee  jmp     loc_18000C12C
0x18000c2f3  add     rdi, 18h
0x18000c2f7  cmp     rdi, rsi
0x18000c2fa  jz      loc_18000C19E
0x18000c300  jmp     loc_18000C16A
0x18000c305  mov     eax, cs:?s_wcmUser@ProfileUser@@2V1@B; ProfileUser const ProfileUser::s_wcmUser
0x18000c30b  mov     [rsp+88h+var_58], eax
0x18000c30f  mov     rcx, cs:qword_1802A06C0
0x18000c316  test    rcx, rcx
0x18000c319  jz      short loc_18000C326
0x18000c31b  lock inc dword ptr [rcx+8]
0x18000c31f  mov     rcx, cs:qword_1802A06C0
0x18000c326  mov     rax, cs:qword_1802A06B8
0x18000c32d  mov     [rsp+88h+var_50], rax
0x18000c332  mov     rbx, [rsp+88h+var_50+8]
0x18000c337  mov     [rsp+88h+var_50+8], rcx
0x18000c33c  test    rbx, rbx
0x18000c33f  jz      loc_18000C40F
0x18000c345  mov     esi, 0FFFFFFFFh
0x18000c34a  mov     eax, esi
0x18000c34c  lock xadd [rbx+8], eax
0x18000c351  cmp     eax, 1
0x18000c354  jz      loc_18000C41C
0x18000c35a  xor     r13d, r13d
0x18000c35d  jmp     loc_18000C206
0x18000c362  xor     al, al
0x18000c364  jmp     loc_18000C196
0x18000c369  lea     rdi, ?s_unspecifiedUser@ProfileUser@@2V1@B; ProfileUser const ProfileUser::s_unspecifiedUser
0x18000c370  jmp     loc_18000C1BE
0x18000c375  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c37a  call    cs:__imp_SetLastError
0x18000c380  mov     r14, r13
0x18000c383  call    cs:__imp_GetLastError
0x18000c389  mov     esi, eax
0x18000c38b  test    eax, eax
0x18000c38d  jz      loc_18000C0F7
0x18000c393  test    r14, r14
0x18000c396  jz      loc_18000C0F7
0x18000c39c  mov     rcx, r14
0x18000c39f  call    FreeWLMem
0x18000c3a4  jmp     loc_18000C0F7
0x18000c3a9  mov     r9d, eax; char *
0x18000c3ac  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18000c3b3  mov     edx, 740h; void *
0x18000c3b8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000c3be  mov     r9d, esi; char *
0x18000c3c1  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18000c3c8  mov     edx, 5E6h; void *
0x18000c3cd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000c3d3  mov     rdx, r9; void *
0x18000c3d6  call    ?FindUserAndCreateIfNeeded@ProfileManager@@AEAAAEBVProfileUser@@PEAX@Z; ProfileManager::FindUserAndCreateIfNeeded(void *)
0x18000c3db  mov     ecx, [rax]
0x18000c3dd  mov     [rsp+88h+var_58], ecx
0x18000c3e1  mov     rcx, [rax+10h]
0x18000c3e5  test    rcx, rcx
0x18000c3e8  jz      short loc_18000C3EE
0x18000c3ea  lock inc dword ptr [rcx+8]
0x18000c3ee  mov     rdx, [rax+10h]
0x18000c3f2  mov     rax, [rax+8]
0x18000c3f6  mov     [rsp+88h+var_50], rax
0x18000c3fb  mov     rcx, [rsp+88h+var_50+8]; this
0x18000c400  mov     [rsp+88h+var_50+8], rdx
0x18000c405  test    rcx, rcx
0x18000c408  jz      short loc_18000C40F
0x18000c40a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c40f  xor     r13d, r13d
0x18000c412  mov     esi, 0FFFFFFFFh
0x18000c417  jmp     loc_18000C206
0x18000c41c  mov     rax, [rbx]
0x18000c41f  mov     rcx, rbx
0x18000c422  mov     rax, [rax]
0x18000c425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42a  mov     rcx, rbx; this
0x18000c42d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000c432  jmp     loc_18000C35A
0x18000c437  test    byte ptr [rcx+6Ch], 1
0x18000c43b  jz      loc_18000C04C
0x18000c441  mov     edx, 16h
0x18000c446  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c44d  mov     rcx, [rcx+60h]
0x18000c451  call    WPP_SF_
0x18000c456  jmp     loc_18000C04C
0x18000c45b  mov     ecx, 8; dwErrCode
0x18000c460  call    cs:__imp_SetLastError
0x18000c466  jmp     loc_18000C383
0x18000c46b  mov     esi, 57h ; 'W'
0x18000c470  jmp     loc_18000C0FE
0x18000c475  cmp     rax, [r15+38h]
0x18000c479  jz      short loc_18000C48A
0x18000c47b  mov     rcx, rax; this
0x18000c47e  call    ??0ProfileUser@@QEAA@PEAX@Z; ProfileUser::ProfileUser(void *)
0x18000c483  add     qword ptr [r15+30h], 18h
0x18000c488  jmp     short loc_18000C49B
0x18000c48a  lea     r8, [rsp+88h+lpMem]
0x18000c48f  mov     rdx, rax
0x18000c492  lea     rcx, [r15+28h]
  ... truncated ...
```
