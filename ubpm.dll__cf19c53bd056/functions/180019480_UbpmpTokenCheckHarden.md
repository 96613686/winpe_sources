# UbpmpTokenCheckHarden

- ea: `0x180019480`
- end: `0x180019a25`
- name: `UbpmpTokenCheckHarden`
- size: `1445`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, void *, int, unsigned __int64 *, char, HANDLE *, unsigned int *, void ***, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022054`

## callees

- `0x180001fb0`
- `0x18000f9a0`
- `0x180019480`
- `0x180019d90`
- `0x18001e9f4`
- `0x1800208bc`
- `0x180027a2c`
- `0x180027cf0`
- `0x180028cf8`
- `0x180028eec`
- `0x18003c120`
- `0x18003c6d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800195a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800196bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800195a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800196bf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800195d0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800196e7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800195d0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800196e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001997e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001997e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019518`

## pseudocode

```c
__int64 __fastcall UbpmpTokenCheckHarden(
        __int64 a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        unsigned __int64 *a5,
        char a6,
        HANDLE *a7,
        unsigned int *a8,
        void ***a9,
        _QWORD *a10)
{
  unsigned int *v10; // r12
  unsigned int NonInteractiveToken; // ebx
  void **v14; // r14
  unsigned __int64 *v15; // rsi
  char v16; // r13
  int v18; // ecx
  DWORD TokenGroups; // eax
  SID_AND_ATTRIBUTES *Groups; // r15
  DWORD LengthSid; // ebx
  void **v22; // rax
  unsigned int v23; // r12d
  unsigned int ConsumerSids; // eax
  __int64 v25; // rax
  DWORD v26; // ebx
  void *v27; // rax
  void *v28; // r12
  HANDLE *v29; // rbx
  int v30; // r8d
  __int64 v31; // rax
  unsigned __int64 v32; // r9
  unsigned __int64 v33; // rdx
  char v34; // r15
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // rax
  _QWORD *v37; // rcx
  int v38; // edx
  void *v39; // [rsp+30h] [rbp-20h]
  HANDLE hObject; // [rsp+38h] [rbp-18h] BYREF
  void **v41; // [rsp+40h] [rbp-10h]
  HLOCAL hMem; // [rsp+48h] [rbp-8h] BYREF
  struct _TOKEN_GROUPS *v44; // [rsp+A0h] [rbp+50h] BYREF
  int v45; // [rsp+A8h] [rbp+58h]

  v45 = a4;
  v10 = a8;
  v44 = 0;
  v41 = 0;
  hObject = 0;
  NonInteractiveToken = 0;
  *a8 = 0;
  v14 = 0;
  hMem = 0;
  v39 = 0;
  if ( !a3 || (v15 = a5) == 0 || (v16 = a6, !*a5) && !a6 )
  {
    *a9 = 0;
    *a10 = 0;
    goto LABEL_6;
  }
  if ( !UbpmUtilsSidSupportsHardening(a3) )
  {
    *a9 = 0;
    *a10 = 0;
    goto LABEL_6;
  }
  v18 = *(_DWORD *)a1;
  if ( v16 != 1 )
  {
    if ( v18 == 2 )
      UbpmpGetNoSidConsumerPrivMask(a3);
    v29 = a7;
    v28 = 0;
LABEL_30:
    v31 = *v15;
    if ( (*v15 & 0x8000000000000000uLL) == 0LL )
    {
      v35 = 0;
      v34 = 0;
      v32 = 0;
      v33 = *v15;
    }
    else
    {
      v32 = v31 & 0x7FFFFFFFFFFFFFFFLL;
      v33 = 0;
      v34 = 1;
      v35 = ~(_DWORD)v31 & 0x20000000;
    }
    TokenGroups = UbpmUtilsRemoveProcessPrivileges(*v29, v33, v35, v32, v15);
    NonInteractiveToken = TokenGroups;
    if ( !TokenGroups )
    {
      *a9 = v14;
      v14 = 0;
      v39 = 0;
      *a10 = v28;
      v36 = *v15 | 0x8000000000000000uLL;
      if ( !v34 )
        v36 = *v15;
      *v15 = v36;
      goto LABEL_6;
    }
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v38 = 223;
LABEL_42:
    WPP_SF_Sd(v37[2], v38, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)a2, TokenGroups);
    goto LABEL_6;
  }
  if ( ((v18 - 1) & 0xFFFFFFFC) != 0 || v18 == 2 )
  {
    ConsumerSids = UbpmpGetConsumerSids(a3, (__int64)v15);
    NonInteractiveToken = ConsumerSids;
    if ( ConsumerSids )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          (_DWORD)a2,
          ConsumerSids);
      v14 = v41;
      goto LABEL_6;
    }
    v14 = v41;
    TokenGroups = UbpmUtilsGetTokenGroups(
                    *(const unsigned __int16 **)(*(_QWORD *)(a1 + 32) + 64LL),
                    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 72LL),
                    *v10,
                    v41,
                    &v44);
    NonInteractiveToken = TokenGroups;
    if ( TokenGroups )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v38 = 217;
      goto LABEL_42;
    }
    v23 = *v10;
    Groups = (SID_AND_ATTRIBUTES *)v41;
  }
  else
  {
    TokenGroups = UbpmUtilsGetTokenGroups(
                    *(const unsigned __int16 **)(*(_QWORD *)(a1 + 32) + 64LL),
                    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 72LL),
                    0,
                    0,
                    &v44);
    NonInteractiveToken = TokenGroups;
    if ( TokenGroups )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v38 = 213;
      goto LABEL_42;
    }
    Groups = v44->Groups;
    LengthSid = GetLengthSid(v44->Groups[0].Sid);
    v22 = (void **)UbpmAlloc(LengthSid + 8);
    v14 = v22;
    if ( !v22 )
    {
      TokenGroups = GetLastError();
      NonInteractiveToken = TokenGroups;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v38 = 214;
      goto LABEL_42;
    }
    *v22 = v22 + 1;
    if ( !CopySid(LengthSid, v22 + 1, Groups->Sid) )
    {
      TokenGroups = GetLastError();
      NonInteractiveToken = TokenGroups;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v38 = 215;
      goto LABEL_42;
    }
    *v10 = 1;
    v23 = 1;
  }
  v25 = *(_QWORD *)(a1 + 32);
  if ( v25 && (unsigned int)(*(_DWORD *)(v25 + 32) - 4) <= 1 && v44 )
  {
    NonInteractiveToken = UbpmpTokenGetNonInteractiveToken(a1, 0, (__int64)v44, a2, &hObject, &hMem);
    if ( !NonInteractiveToken )
    {
      TokenGroups = UbpmUtilsAdjustTokenDefaultDacl(hObject, pSid, &Groups->Sid, v23);
      NonInteractiveToken = TokenGroups;
      if ( TokenGroups )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_6;
        v38 = 219;
        goto LABEL_42;
      }
      v26 = GetLengthSid(hMem);
      v27 = UbpmAlloc(v26);
      v39 = v27;
      v28 = v27;
      if ( !v27 )
      {
        TokenGroups = GetLastError();
        NonInteractiveToken = TokenGroups;
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_6;
        v38 = 220;
        goto LABEL_42;
      }
      if ( !CopySid(v26, v27, hMem) )
      {
        TokenGroups = GetLastError();
        NonInteractiveToken = TokenGroups;
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_6;
        v38 = 221;
        goto LABEL_42;
      }
      v29 = a7;
      CloseHandle(*a7);
      *v29 = hObject;
      hObject = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_Sid(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, v30, (_DWORD)a2, *v15, 1);
      goto LABEL_30;
    }
  }
  else
  {
    NonInteractiveToken = 87;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      218,
      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
      (_DWORD)a2,
      NonInteractiveToken);
LABEL_6:
  UBPM_MIDL_user_free(v44);
  UBPM_MIDL_user_free(v14);
  UBPM_MIDL_user_free(v39);
  LocalFree(hMem);
  if ( hObject )
    CloseHandle(hObject);
  return NonInteractiveToken;
}

```

## disassembly

```asm
0x180019480  mov     [rsp-38h+arg_8], rbx
0x180019485  mov     [rsp-38h+arg_18], r9d
0x18001948a  mov     [rsp-38h+arg_0], rcx
0x18001948f  push    rbp
0x180019490  push    rsi
0x180019491  push    rdi
0x180019492  push    r12
0x180019494  push    r13
0x180019496  push    r14
0x180019498  push    r15
0x18001949a  mov     rbp, rsp
0x18001949d  sub     rsp, 50h
0x1800194a1  mov     r12, [rbp+arg_38]
0x1800194a5  xor     ecx, ecx
0x1800194a7  mov     [rbp+arg_10], rcx
0x1800194ab  mov     r15, r8
0x1800194ae  mov     [rbp+var_10], rcx
0x1800194b2  mov     rdi, rdx
0x1800194b5  mov     [rbp+hObject], rcx
0x1800194b9  mov     ebx, ecx
0x1800194bb  mov     [r12], ecx
0x1800194bf  mov     r14d, ecx
0x1800194c2  mov     [rbp+hMem], rcx
0x1800194c6  mov     [rbp+var_20], rcx
0x1800194ca  test    r8, r8
0x1800194cd  jz      short loc_1800194E6
0x1800194cf  mov     rsi, [rbp+arg_20]
0x1800194d3  test    rsi, rsi
0x1800194d6  jz      short loc_1800194E6
0x1800194d8  mov     r13b, [rbp+arg_28]
0x1800194dc  cmp     [rsi], rcx
0x1800194df  jnz     short loc_180019545
0x1800194e1  test    r13b, r13b
0x1800194e4  jnz     short loc_180019545
0x1800194e6  mov     rax, [rbp+arg_40]
0x1800194ed  mov     [rax], rcx
0x1800194f0  mov     rax, [rbp+arg_48]
0x1800194f7  mov     [rax], rcx
0x1800194fa  mov     rcx, [rbp+arg_10]
0x1800194fe  call    UBPM_MIDL_user_free
0x180019503  mov     rcx, r14
0x180019506  call    UBPM_MIDL_user_free
0x18001950b  mov     rcx, [rbp+var_20]
0x18001950f  call    UBPM_MIDL_user_free
0x180019514  mov     rcx, [rbp+hMem]; hMem
0x180019518  call    cs:__imp_LocalFree
0x18001951e  mov     rcx, [rbp+hObject]; hObject
0x180019522  test    rcx, rcx
0x180019525  jnz     loc_180019A1A
0x18001952b  mov     eax, ebx
0x18001952d  mov     rbx, [rsp+50h+arg_8]
0x180019535  add     rsp, 50h
0x180019539  pop     r15
0x18001953b  pop     r14
0x18001953d  pop     r13
0x18001953f  pop     r12
0x180019541  pop     rdi
0x180019542  pop     rsi
0x180019543  pop     rbp
0x180019544  retn
0x180019545  mov     rcx, r15; pSid1
0x180019548  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x18001954d  test    al, al
0x18001954f  jz      loc_1800197F9
0x180019555  mov     rdx, [rbp+arg_0]
0x180019559  mov     ecx, [rdx]
0x18001955b  cmp     r13b, 1
0x18001955f  jnz     loc_1800197A7
0x180019565  lea     eax, [rcx-1]
0x180019568  test    eax, 0FFFFFFFCh
0x18001956d  jnz     short loc_1800195EE
0x18001956f  cmp     ecx, 2
0x180019572  jz      short loc_1800195EE
0x180019574  mov     rcx, [rdx+20h]
0x180019578  lea     rax, [rbp+arg_10]
0x18001957c  xor     r9d, r9d; void **
0x18001957f  mov     [rsp+50h+var_30], rax; struct _TOKEN_GROUPS **
0x180019584  xor     r8d, r8d; unsigned int
0x180019587  mov     edx, [rcx+48h]; unsigned int
0x18001958a  mov     rcx, [rcx+40h]; unsigned __int16 *
0x18001958e  call    ?UbpmUtilsGetTokenGroups@@YAKPEBGKKPEAPEAXPEAPEAU_TOKEN_GROUPS@@@Z; UbpmUtilsGetTokenGroups(ushort const *,ulong,ulong,void * *,_TOKEN_GROUPS * *)
0x180019593  mov     ebx, eax
0x180019595  test    eax, eax
0x180019597  jnz     loc_180019859
0x18001959d  mov     r15, [rbp+arg_10]
0x1800195a1  add     r15, 8
0x1800195a5  mov     rcx, [r15]; pSid
0x1800195a8  call    cs:__imp_GetLengthSid
0x1800195ae  mov     ebx, eax
0x1800195b0  lea     ecx, [rax+8]; Size
0x1800195b3  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800195b8  mov     r14, rax
0x1800195bb  test    rax, rax
0x1800195be  jz      loc_180019884
0x1800195c4  lea     rdx, [rax+8]; pDestinationSid
0x1800195c8  mov     ecx, ebx; nDestinationSidLength
0x1800195ca  mov     [rax], rdx
0x1800195cd  mov     r8, [r15]; pSourceSid
0x1800195d0  call    cs:__imp_CopySid
0x1800195d6  test    eax, eax
0x1800195d8  jz      loc_1800198B7
0x1800195de  mov     dword ptr [r12], 1
0x1800195e6  mov     r12d, 1
0x1800195ec  jmp     short loc_180019648
0x1800195ee  mov     edx, [rbp+arg_18]
0x1800195f1  lea     r9, [rbp+var_10]
0x1800195f5  mov     r8, r12
0x1800195f8  mov     [rsp+50h+var_30], rsi; __int64
0x1800195fd  mov     rcx, r15; pSid1
0x180019600  call    UbpmpGetConsumerSids
0x180019605  mov     ebx, eax
0x180019607  test    eax, eax
0x180019609  jnz     loc_1800198EA
0x18001960f  mov     rcx, [rbp+arg_0]
0x180019613  lea     rax, [rbp+arg_10]
0x180019617  mov     r14, [rbp+var_10]
0x18001961b  mov     r8d, [r12]; unsigned int
0x18001961f  mov     r9, r14; void **
0x180019622  mov     [rsp+50h+var_30], rax; struct _TOKEN_GROUPS **
0x180019627  mov     rcx, [rcx+20h]
0x18001962b  mov     edx, [rcx+48h]; unsigned int
0x18001962e  mov     rcx, [rcx+40h]; unsigned __int16 *
0x180019632  call    ?UbpmUtilsGetTokenGroups@@YAKPEBGKKPEAPEAXPEAPEAU_TOKEN_GROUPS@@@Z; UbpmUtilsGetTokenGroups(ushort const *,ulong,ulong,void * *,_TOKEN_GROUPS * *)
0x180019637  mov     ebx, eax
0x180019639  test    eax, eax
0x18001963b  jnz     loc_180019928
0x180019641  mov     r12d, [r12]
0x180019645  mov     r15, r14
0x180019648  mov     rcx, [rbp+arg_0]
0x18001964c  mov     rax, [rcx+20h]
0x180019650  test    rax, rax
0x180019653  jz      loc_180019812
0x180019659  mov     eax, [rax+20h]
0x18001965c  sub     eax, 4
0x18001965f  cmp     eax, 1
0x180019662  ja      loc_180019812
0x180019668  mov     r8, [rbp+arg_10]
0x18001966c  test    r8, r8
0x18001966f  jz      loc_180019812
0x180019675  lea     rax, [rbp+hMem]
0x180019679  mov     r9, rdi
0x18001967c  mov     [rsp+50h+var_28], rax
0x180019681  xor     edx, edx
0x180019683  lea     rax, [rbp+hObject]
0x180019687  mov     [rsp+50h+var_30], rax
0x18001968c  call    UbpmpTokenGetNonInteractiveToken
0x180019691  mov     ebx, eax
0x180019693  test    eax, eax
0x180019695  jnz     loc_180019817
0x18001969b  mov     rdx, cs:pSid; pSid
0x1800196a2  mov     r9d, r12d; unsigned int
0x1800196a5  mov     rcx, [rbp+hObject]; TokenHandle
0x1800196a9  mov     r8, r15; void **
0x1800196ac  call    ?UbpmUtilsAdjustTokenDefaultDacl@@YAKPEAX0PEAPEAXK@Z; UbpmUtilsAdjustTokenDefaultDacl(void *,void *,void * *,ulong)
0x1800196b1  mov     ebx, eax
0x1800196b3  test    eax, eax
0x1800196b5  jnz     loc_180019953
0x1800196bb  mov     rcx, [rbp+hMem]; pSid
0x1800196bf  call    cs:__imp_GetLengthSid
0x1800196c5  mov     ecx, eax; Size
0x1800196c7  mov     ebx, eax
0x1800196c9  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800196ce  mov     [rbp+var_20], rax
0x1800196d2  mov     r12, rax
0x1800196d5  test    rax, rax
0x1800196d8  jz      loc_18001997E
0x1800196de  mov     r8, [rbp+hMem]; pSourceSid
0x1800196e2  mov     rdx, rax; pDestinationSid
0x1800196e5  mov     ecx, ebx; nDestinationSidLength
0x1800196e7  call    cs:__imp_CopySid
0x1800196ed  test    eax, eax
0x1800196ef  jz      loc_1800199B1
0x1800196f5  mov     rbx, [rbp+arg_30]
0x1800196f9  mov     rcx, [rbx]; hObject
0x1800196fc  call    cs:__imp_CloseHandle
0x180019702  mov     rax, [rbp+hObject]
0x180019706  mov     [rbx], rax
0x180019709  mov     [rbp+hObject], 0
0x180019711  mov     rcx, cs:WPP_GLOBAL_Control
0x180019718  lea     r13, WPP_GLOBAL_Control
0x18001971f  cmp     rcx, r13
0x180019722  jz      short loc_18001972E
0x180019724  test    byte ptr [rcx+1Ch], 80h
0x180019728  jnz     loc_1800199E4
0x18001972e  mov     rax, [rsi]
0x180019731  test    rax, rax
0x180019734  jns     loc_1800197E8
0x18001973a  mov     r9, rax
0x18001973d  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180019747  not     rax
0x18001974a  and     r9, rcx; unsigned __int64
0x18001974d  xor     edx, edx; unsigned __int64
0x18001974f  mov     r15b, 1
0x180019752  and     eax, 20000000h
0x180019757  mov     r8d, eax; unsigned __int64
0x18001975a  mov     rcx, [rbx]; TokenHandle
0x18001975d  mov     [rsp+50h+var_30], rsi; unsigned __int64 *
0x180019762  call    ?UbpmUtilsRemoveProcessPrivileges@@YAKPEAX_K11PEA_K@Z; UbpmUtilsRemoveProcessPrivileges(void *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019767  mov     ebx, eax
0x180019769  test    eax, eax
0x18001976b  jnz     short loc_1800197C3
0x18001976d  mov     rax, [rbp+arg_40]
0x180019774  mov     rcx, 8000000000000000h
0x18001977e  mov     [rax], r14
0x180019781  xor     r14d, r14d
0x180019784  mov     rax, [rbp+arg_48]
0x18001978b  mov     [rbp+var_20], r14
0x18001978f  mov     [rax], r12
0x180019792  mov     rax, [rsi]
0x180019795  or      rax, rcx
0x180019798  test    r15b, r15b
0x18001979b  cmovz   rax, [rsi]
0x18001979f  mov     [rsi], rax
0x1800197a2  jmp     loc_1800194FA
0x1800197a7  cmp     ecx, 2
0x1800197aa  jz      loc_180019A0A
0x1800197b0  mov     rbx, [rbp+arg_30]
0x1800197b4  lea     r13, WPP_GLOBAL_Control
0x1800197bb  mov     r12, r14
0x1800197be  jmp     loc_18001972E
0x1800197c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197ca  cmp     rcx, r13
0x1800197cd  jz      loc_1800194FA
0x1800197d3  test    byte ptr [rcx+1Ch], 1
0x1800197d7  jz      loc_1800194FA
0x1800197dd  mov     edx, 0DFh
0x1800197e2  mov     dword ptr [rsp+50h+var_30], eax
0x1800197e6  jmp     short loc_180019841
0x1800197e8  xor     r8d, r8d
0x1800197eb  xor     r15b, r15b
0x1800197ee  xor     r9d, r9d
0x1800197f1  mov     rdx, rax
0x1800197f4  jmp     loc_18001975A
0x1800197f9  mov     rax, [rbp+arg_40]
0x180019800  mov     [rax], rbx
0x180019803  mov     rax, [rbp+arg_48]
0x18001980a  mov     [rax], rbx
0x18001980d  jmp     loc_1800194FA
0x180019812  mov     ebx, 57h ; 'W'
0x180019817  mov     rcx, cs:WPP_GLOBAL_Control
0x18001981e  lea     r13, WPP_GLOBAL_Control
0x180019825  cmp     rcx, r13
0x180019828  jz      loc_1800194FA
0x18001982e  test    byte ptr [rcx+1Ch], 1
0x180019832  jz      loc_1800194FA
0x180019838  mov     edx, 0DAh
0x18001983d  mov     dword ptr [rsp+50h+var_30], ebx
0x180019841  mov     rcx, [rcx+10h]
0x180019845  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001984c  mov     r9, rdi
0x18001984f  call    WPP_SF_Sd
0x180019854  jmp     loc_1800194FA
0x180019859  mov     rcx, cs:WPP_GLOBAL_Control
0x180019860  lea     r13, WPP_GLOBAL_Control
0x180019867  cmp     rcx, r13
0x18001986a  jz      loc_1800194FA
0x180019870  test    byte ptr [rcx+1Ch], 1
0x180019874  jz      loc_1800194FA
0x18001987a  mov     edx, 0D5h
0x18001987f  jmp     loc_1800197E2
0x180019884  call    cs:__imp_GetLastError
0x18001988a  mov     ebx, eax
0x18001988c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019893  lea     r13, WPP_GLOBAL_Control
0x18001989a  cmp     rcx, r13
0x18001989d  jz      loc_1800194FA
0x1800198a3  test    byte ptr [rcx+1Ch], 1
0x1800198a7  jz      loc_1800194FA
0x1800198ad  mov     edx, 0D6h
0x1800198b2  jmp     loc_1800197E2
0x1800198b7  call    cs:__imp_GetLastError
0x1800198bd  mov     ebx, eax
0x1800198bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198c6  lea     r13, WPP_GLOBAL_Control
0x1800198cd  cmp     rcx, r13
0x1800198d0  jz      loc_1800194FA
0x1800198d6  test    byte ptr [rcx+1Ch], 1
0x1800198da  jz      loc_1800194FA
0x1800198e0  mov     edx, 0D7h
0x1800198e5  jmp     loc_1800197E2
0x1800198ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198f1  lea     r13, WPP_GLOBAL_Control
0x1800198f8  cmp     rcx, r13
0x1800198fb  jz      short loc_18001991F
0x1800198fd  test    byte ptr [rcx+1Ch], 1
0x180019901  jz      short loc_18001991F
0x180019903  mov     rcx, [rcx+10h]
0x180019907  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001990e  mov     edx, 0D8h
0x180019913  mov     dword ptr [rsp+50h+var_30], eax
0x180019917  mov     r9, rdi
0x18001991a  call    WPP_SF_Sd
0x18001991f  mov     r14, [rbp+var_10]
0x180019923  jmp     loc_1800194FA
0x180019928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001992f  lea     r13, WPP_GLOBAL_Control
0x180019936  cmp     rcx, r13
0x180019939  jz      loc_1800194FA
0x18001993f  test    byte ptr [rcx+1Ch], 1
0x180019943  jz      loc_1800194FA
  ... truncated ...
```
