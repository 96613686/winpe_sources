# CDescriptionManager::HandleDeviceRegistration(SSDP_SERVICE_REGISTRATION_PARAMS *)

- ea: `0x18001d4b0`
- end: `0x18001d985`
- name: `?HandleDeviceRegistration@CDescriptionManager@@AEAAJPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z`
- size: `1237`
- prototype: `int(CDescriptionManager *__hidden this, struct SSDP_SERVICE_REGISTRATION_PARAMS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d400`

## callees

- `0x180016d5c`
- `0x1800197b8`
- `0x180019970`
- `0x1800199a4`
- `0x18001b960`
- `0x18001d4b0`
- `0x18001d98c`
- `0x18001da24`
- `0x18001da80`
- `0x180038ce4`
- `0x18004ae64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d60e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d60e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d57e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d57e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d706`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d787`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d706`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d597`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d876`
- `SSDPAPI!DeregisterService` at `0x18001d6ea`
- `SSDPAPI!DeregisterService` at `0x18001d6ea`
- `SSDPAPI!RegisterServiceEx` at `0x18001d669`
- `SSDPAPI!RegisterServiceEx` at `0x18001d669`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HandleDeviceRegistration(
        HANDLE *this,
        struct SSDP_SERVICE_REGISTRATION_PARAMS *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  CDescriptionManager *v3; // r12
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v4; // r15
  int v5; // edi
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v6; // rdx
  CDescriptionManager *v7; // rcx
  _DWORD *v8; // rdx
  const struct _GUID *v9; // rbp
  int v10; // esi
  CDescriptionManager *v11; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // r8
  _DWORD *v17; // rdi
  int v18; // r13d
  int v19; // ebp
  __int64 v20; // rax
  _QWORD *v21; // r14
  int v22; // edx
  __int64 v23; // r12
  int v24; // edx
  int v25; // r14d
  __int64 v26; // rbp
  DWORD v27; // eax
  DWORD v28; // eax
  signed int LastError; // eax
  _QWORD *v30; // r8
  int i; // eax
  signed int v32; // eax
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+80h] [rbp+18h]

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 61);
  v3 = (CDescriptionManager *)this;
  v35 = (struct _RTL_CRITICAL_SECTION *)(this + 61);
  v4 = a2;
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 61));
  v6 = (struct SSDP_SERVICE_REGISTRATION_PARAMS *)*((_QWORD *)v3 + 76);
  while ( v6 != (CDescriptionManager *)((char *)v3 + 608) )
  {
    if ( v5 )
      break;
    if ( v6 == v4 )
    {
      v13 = (_QWORD *)*((_QWORD *)v4 + 1);
      v5 = 1;
      v14 = *(_QWORD *)v4;
      *v13 = *(_QWORD *)v4;
      *(_QWORD *)(v14 + 8) = v13;
    }
    else
    {
      v6 = *(struct SSDP_SERVICE_REGISTRATION_PARAMS **)v6;
    }
  }
  LeaveCriticalSection(v2);
  if ( !v5 )
    return 2147500037LL;
  v8 = (_DWORD *)*((_QWORD *)v4 + 4);
  v9 = (const struct _GUID *)((char *)v4 + 52);
  if ( v8 )
  {
    v10 = CDescriptionManager::HandleDeviceDeregistration((__int64)v3, v8, (__int64)v4 + 52);
    goto LABEL_12;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)v3 + 90) )
      goto LABEL_56;
    v9 = (const struct _GUID *)((char *)v4 + 52);
    v30 = (_QWORD *)(*((_QWORD *)v3 + 44) + 16LL * i);
    v7 = (CDescriptionManager *)(*(_QWORD *)((char *)v4 + 52) - *v30);
    if ( !v7 )
      v7 = (CDescriptionManager *)(*(_QWORD *)((char *)v4 + 60) - v30[1]);
    if ( !v7 )
      break;
  }
  v7 = (CDescriptionManager *)(*((_QWORD *)v3 + 46) + 4LL * i);
  if ( !v7 )
  {
LABEL_56:
    v10 = -2147467259;
    goto LABEL_57;
  }
  v15 = malloc(0x10u);
  v17 = v15;
  if ( v15 )
  {
    v10 = 0;
    v18 = 0;
    v19 = 0;
    *v15 = 0;
    v15[1] = 0;
    if ( *((int *)v4 + 10) <= 0 )
    {
LABEL_10:
      v9 = (const struct _GUID *)((char *)v4 + 52);
      v10 = CDescriptionManager::HrPublishCompletion(v3, (char *)v4 + 52, v16, v17);
      if ( v10 >= 0 )
        goto LABEL_11;
    }
    else
    {
      do
      {
        if ( v10 < 0 )
        {
          v3 = (CDescriptionManager *)this;
          goto LABEL_29;
        }
        if ( v18 )
        {
          v3 = (CDescriptionManager *)this;
          goto LABEL_10;
        }
        v20 = *((_QWORD *)v4 + 2);
        v21 = *(_QWORD **)(v20 + 8LL * v19);
        if ( v21 )
        {
          v10 = 0;
          v23 = RegisterServiceEx(*(_QWORD *)(v20 + 8LL * v19), *(unsigned int *)(*((_QWORD *)v4 + 3) + 4LL * v19));
          if ( v23 == -1
            && (v10 = -2147024809, WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control)
            && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v16, *v21, v21[3], 87);
          }
          else if ( v10 >= 0 )
          {
            v24 = v17[3];
            if ( v17[2] != v24 || (v10 = CUArray<void *>::HrSetReserve(v17, (unsigned int)(v24 + 50)), v10 >= 0) )
            {
              *(_QWORD *)(*(_QWORD *)v17 + 8LL * (int)v17[2]++) = v23;
              v10 = 0;
            }
          }
        }
        else
        {
          v10 = -2147467261;
        }
        if ( v19 < *((_DWORD *)v4 + 10) - 1 )
        {
          v28 = WaitForSingleObject(this[60], 0x4Bu);
          if ( v28 )
          {
            if ( v28 != 258 )
            {
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v28);
              LastError = GetLastError();
              v10 = LastError;
              if ( LastError > 0 )
                v10 = (unsigned __int16)LastError | 0x80070000;
            }
          }
          else
          {
            v18 = 1;
          }
        }
        ++v19;
      }
      while ( v19 < *((_DWORD *)v4 + 10) );
      v3 = (CDescriptionManager *)this;
      if ( v10 >= 0 )
        goto LABEL_10;
    }
LABEL_29:
    v25 = v17[2];
    v26 = 0;
    if ( v25 > 0 )
    {
      do
      {
        DeregisterService(*(_QWORD *)(*(_QWORD *)v17 + 8 * v26), 1);
        if ( (int)v26 < v25 - 1 && !v18 )
        {
          v27 = WaitForSingleObject(this[60], 0x4Bu);
          if ( v27 )
          {
            if ( v27 != 258 )
            {
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v27);
              v32 = GetLastError();
              v10 = v32;
              if ( v32 > 0 )
                v10 = (unsigned __int16)v32 | 0x80070000;
            }
          }
          else
          {
            v18 = 1;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, 0);
          }
        }
        v26 = (unsigned int)(v26 + 1);
      }
      while ( (int)v26 < v25 );
      v2 = v35;
      v4 = a2;
      v3 = (CDescriptionManager *)this;
    }
    CUArray<void *>::`scalar deleting destructor'(v17);
    v9 = (const struct _GUID *)((char *)v4 + 52);
    if ( v10 >= 0 )
    {
LABEL_11:
      if ( !v18 )
        goto LABEL_12;
    }
  }
  else
  {
    v10 = -2147024882;
  }
LABEL_57:
  CDescriptionManager::Hr_DoStopUrlListening(v7, v9);
  CDescriptionManager::HrRD_RemoveFromEventing(v3, v9);
LABEL_12:
  EnterCriticalSection(v2);
  CTable<_GUID,_TP_WORK *>::HrErase((char *)v3 + 320, v9);
  LeaveCriticalSection(v2);
  CDescriptionManager::PurgeRegistrationParams(v11, v4);
  if ( v10 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d4b0  mov     [rsp+arg_8], rdx
0x18001d4b5  mov     [rsp+arg_0], rcx
0x18001d4ba  push    rbx
0x18001d4bb  push    rdi
0x18001d4bc  push    r12
0x18001d4be  push    r15
0x18001d4c0  sub     rsp, 48h
0x18001d4c4  lea     rbx, [rcx+1E8h]
0x18001d4cb  mov     r12, rcx
0x18001d4ce  mov     rcx, rbx; lpCriticalSection
0x18001d4d1  mov     [rsp+68h+arg_10], rbx
0x18001d4d9  mov     r15, rdx
0x18001d4dc  xor     edi, edi
0x18001d4de  call    cs:__imp_EnterCriticalSection
0x18001d4e4  lea     r8, [r12+260h]
0x18001d4ec  mov     rdx, [r8]
0x18001d4ef  cmp     rdx, r8
0x18001d4f2  jz      short loc_18001D509
0x18001d4f4  test    edi, edi
0x18001d4f6  jnz     short loc_18001D509
0x18001d4f8  cmp     rdx, r15
0x18001d4fb  jz      loc_18001D5C7
0x18001d501  mov     rdx, [rdx]
0x18001d504  cmp     rdx, r8
0x18001d507  jnz     short loc_18001D4F4
0x18001d509  mov     rcx, rbx; lpCriticalSection
0x18001d50c  mov     [rsp+68h+var_28], rsi
0x18001d511  call    cs:__imp_LeaveCriticalSection
0x18001d517  test    edi, edi
0x18001d519  jz      loc_18001D5DF
0x18001d51f  mov     rdx, [r15+20h]
0x18001d523  mov     [rsp+68h+arg_18], rbp
0x18001d52b  lea     rbp, [r15+34h]
0x18001d52f  test    rdx, rdx
0x18001d532  jz      loc_18001D894
0x18001d538  mov     r8, rbp
0x18001d53b  mov     rcx, r12
0x18001d53e  call    ?HandleDeviceDeregistration@CDescriptionManager@@AEAAJPEAV?$CUArray@PEAX@@AEBU_GUID@@@Z; CDescriptionManager::HandleDeviceDeregistration(CUArray<void *> *,_GUID const &)
0x18001d543  mov     esi, eax
0x18001d545  jmp     short loc_18001D57B
0x18001d547  mov     r12, [rsp+68h+arg_0]
0x18001d54c  lea     rbp, [r15+34h]
0x18001d550  mov     r9, rdi
0x18001d553  mov     rdx, rbp
0x18001d556  mov     rcx, r12
0x18001d559  call    ?HrPublishCompletion@CDescriptionManager@@AEAAJAEBU_GUID@@JPEAV?$CUArray@PEAX@@@Z; CDescriptionManager::HrPublishCompletion(_GUID const &,long,CUArray<void *> *)
0x18001d55e  mov     esi, eax
0x18001d560  test    eax, eax
0x18001d562  js      loc_18001D6BF
0x18001d568  test    r13d, r13d
0x18001d56b  jnz     loc_18001D85E
0x18001d571  mov     r13, [rsp+68h+var_30]
0x18001d576  mov     r14, [rsp+68h+var_38]
0x18001d57b  mov     rcx, rbx; lpCriticalSection
0x18001d57e  call    cs:__imp_EnterCriticalSection
0x18001d584  lea     rcx, [r12+140h]
0x18001d58c  mov     rdx, rbp
0x18001d58f  call    ?HrErase@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAJAEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::HrErase(_GUID const &)
0x18001d594  mov     rcx, rbx; lpCriticalSection
0x18001d597  call    cs:__imp_LeaveCriticalSection
0x18001d59d  mov     rdx, r15; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18001d5a0  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18001d5a5  mov     rbp, [rsp+68h+arg_18]
0x18001d5ad  test    esi, esi
0x18001d5af  jnz     loc_18001D947
0x18001d5b5  mov     eax, esi
0x18001d5b7  mov     rsi, [rsp+68h+var_28]
0x18001d5bc  add     rsp, 48h
0x18001d5c0  pop     r15
0x18001d5c2  pop     r12
0x18001d5c4  pop     rdi
0x18001d5c5  pop     rbx
0x18001d5c6  retn
0x18001d5c7  mov     rax, [r15+8]
0x18001d5cb  mov     edi, 1
0x18001d5d0  mov     rcx, [r15]
0x18001d5d3  mov     [rax], rcx
0x18001d5d6  mov     [rcx+8], rax
0x18001d5da  jmp     loc_18001D504
0x18001d5df  mov     rsi, [rsp+68h+var_28]
0x18001d5e4  mov     eax, 80004005h
0x18001d5e9  add     rsp, 48h
0x18001d5ed  pop     r15
0x18001d5ef  pop     r12
0x18001d5f1  pop     rdi
0x18001d5f2  pop     rbx
0x18001d5f3  retn
0x18001d5f4  mov     rax, [r12+170h]
0x18001d5fc  lea     rcx, [rax+rdx*4]; this
0x18001d600  test    rcx, rcx
0x18001d603  jz      loc_18001D859
0x18001d609  mov     ecx, 10h; Size
0x18001d60e  call    cs:__imp_malloc
0x18001d614  mov     rdi, rax
0x18001d617  test    rax, rax
0x18001d61a  jz      loc_18001D93D
0x18001d620  xor     esi, esi
0x18001d622  xor     r13d, r13d
0x18001d625  xor     ebp, ebp
0x18001d627  mov     [rax], rsi
0x18001d62a  mov     [rax+8], rsi
0x18001d62e  cmp     [r15+28h], esi
0x18001d632  jle     loc_18001D54C
0x18001d638  test    esi, esi
0x18001d63a  js      loc_18001D810
0x18001d640  test    r13d, r13d
0x18001d643  jnz     loc_18001D547
0x18001d649  mov     rax, [r15+10h]
0x18001d64d  movsxd  rcx, ebp
0x18001d650  mov     r14, [rax+rcx*8]
0x18001d654  test    r14, r14
0x18001d657  jz      loc_18001D8AD
0x18001d65d  mov     rdx, [r15+18h]
0x18001d661  xor     esi, esi
0x18001d663  mov     edx, [rdx+rcx*4]
0x18001d666  mov     rcx, r14
0x18001d669  call    cs:__imp_RegisterServiceEx
0x18001d66f  mov     r12, rax
0x18001d672  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d676  jz      loc_18001D8B7
0x18001d67c  test    esi, esi
0x18001d67e  js      short loc_18001D69C
0x18001d680  mov     edx, [rdi+0Ch]
0x18001d683  cmp     [rdi+8], edx
0x18001d686  jz      loc_18001D7EB
0x18001d68c  movsxd  rcx, dword ptr [rdi+8]
0x18001d690  mov     rax, [rdi]
0x18001d693  mov     [rax+rcx*8], r12
0x18001d697  inc     dword ptr [rdi+8]
0x18001d69a  xor     esi, esi
0x18001d69c  mov     eax, [r15+28h]
0x18001d6a0  dec     eax
0x18001d6a2  cmp     ebp, eax
0x18001d6a4  jl      loc_18001D776
0x18001d6aa  inc     ebp
0x18001d6ac  cmp     ebp, [r15+28h]
0x18001d6b0  jl      short loc_18001D638
0x18001d6b2  mov     r12, [rsp+68h+arg_0]
0x18001d6b7  test    esi, esi
0x18001d6b9  jns     loc_18001D54C
0x18001d6bf  mov     r14d, [rdi+8]
0x18001d6c3  xor     ebp, ebp
0x18001d6c5  test    r14d, r14d
0x18001d6c8  jle     loc_18001D75D
0x18001d6ce  mov     rbx, [rsp+68h+arg_0]
0x18001d6d3  lea     r12d, [r14-1]
0x18001d6d7  lea     r15, WPP_GLOBAL_Control
0x18001d6de  mov     rcx, [rdi]
0x18001d6e1  mov     edx, 1
0x18001d6e6  mov     rcx, [rcx+rbp*8]
0x18001d6ea  call    cs:__imp_DeregisterService
0x18001d6f0  cmp     ebp, r12d
0x18001d6f3  jge     short loc_18001D744
0x18001d6f5  test    r13d, r13d
0x18001d6f8  jnz     short loc_18001D744
0x18001d6fa  mov     rcx, [rbx+1E0h]; hHandle
0x18001d701  mov     edx, 4Bh ; 'K'; dwMilliseconds
0x18001d706  call    cs:__imp_WaitForSingleObject
0x18001d70c  test    eax, eax
0x18001d70e  jnz     loc_18001D8FB
0x18001d714  mov     r13d, 1
0x18001d71a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d721  cmp     rcx, r15
0x18001d724  jz      short loc_18001D744
0x18001d726  test    byte ptr [rcx+1Ch], 40h
0x18001d72a  jz      short loc_18001D744
0x18001d72c  mov     rcx, [rcx+10h]
0x18001d730  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001d737  mov     edx, 35h ; '5'
0x18001d73c  xor     r9d, r9d
0x18001d73f  call    WPP_SF_d
0x18001d744  inc     ebp
0x18001d746  cmp     ebp, r14d
0x18001d749  jl      short loc_18001D6DE
0x18001d74b  mov     rbx, [rsp+68h+arg_10]
0x18001d753  mov     r15, [rsp+68h+arg_8]
0x18001d758  mov     r12, [rsp+68h+arg_0]
0x18001d75d  mov     rcx, rdi; void *
0x18001d760  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x18001d765  lea     rbp, [r15+34h]
0x18001d769  test    esi, esi
0x18001d76b  js      loc_18001D85E
0x18001d771  jmp     loc_18001D568
0x18001d776  mov     rax, [rsp+68h+arg_0]
0x18001d77b  mov     edx, 4Bh ; 'K'; dwMilliseconds
0x18001d780  mov     rcx, [rax+1E0h]; hHandle
0x18001d787  call    cs:__imp_WaitForSingleObject
0x18001d78d  test    eax, eax
0x18001d78f  jz      short loc_18001D805
0x18001d791  cmp     eax, 102h
0x18001d796  jz      loc_18001D6AA
0x18001d79c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7a3  lea     rdx, WPP_GLOBAL_Control
0x18001d7aa  cmp     rcx, rdx
0x18001d7ad  jz      short loc_18001D7CD
0x18001d7af  test    byte ptr [rcx+1Ch], 40h
0x18001d7b3  jz      short loc_18001D7CD
0x18001d7b5  mov     rcx, [rcx+10h]
0x18001d7b9  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001d7c0  mov     edx, 34h ; '4'
0x18001d7c5  mov     r9d, eax
0x18001d7c8  call    WPP_SF_d
0x18001d7cd  call    cs:__imp_GetLastError
0x18001d7d3  mov     esi, eax
0x18001d7d5  test    eax, eax
0x18001d7d7  jle     loc_18001D6AA
0x18001d7dd  movzx   esi, ax
0x18001d7e0  or      esi, 80070000h
0x18001d7e6  jmp     loc_18001D6AA
0x18001d7eb  add     edx, 32h ; '2'
0x18001d7ee  mov     rcx, rdi
0x18001d7f1  call    ?HrSetReserve@?$CUArray@PEAX@@QEAAJJ@Z; CUArray<void *>::HrSetReserve(long)
0x18001d7f6  mov     esi, eax
0x18001d7f8  test    eax, eax
0x18001d7fa  js      loc_18001D69C
0x18001d800  jmp     loc_18001D68C
0x18001d805  mov     r13d, 1
0x18001d80b  jmp     loc_18001D6AA
0x18001d810  mov     r12, [rsp+68h+arg_0]
0x18001d815  jmp     loc_18001D6BF
0x18001d820  cmp     eax, r9d
0x18001d823  jge     short loc_18001D859
0x18001d825  mov     rcx, [r15+34h]
0x18001d829  lea     rbp, [r15+34h]
0x18001d82d  movsxd  rdx, eax
0x18001d830  mov     r8, rdx
0x18001d833  shl     r8, 4
0x18001d837  add     r8, [r12+160h]
0x18001d83f  sub     rcx, [r8]
0x18001d842  jnz     short loc_18001D84C
0x18001d844  mov     rcx, [rbp+8]
0x18001d848  sub     rcx, [r8+8]
0x18001d84c  test    rcx, rcx
0x18001d84f  jz      loc_18001D5F4
0x18001d855  inc     eax
0x18001d857  jmp     short loc_18001D820
0x18001d859  mov     esi, 80004005h
0x18001d85e  mov     rdx, rbp; struct _GUID *
0x18001d861  call    ?Hr_DoStopUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStopUrlListening(_GUID const &)
0x18001d866  mov     rdx, rbp; struct _GUID *
0x18001d869  mov     rcx, r12; this
0x18001d86c  call    ?HrRD_RemoveFromEventing@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_RemoveFromEventing(_GUID const &)
0x18001d871  jmp     loc_18001D571
0x18001d876  call    cs:__imp_GetLastError
0x18001d87c  mov     esi, eax
0x18001d87e  test    eax, eax
0x18001d880  jle     loc_18001D744
0x18001d886  movzx   esi, ax
0x18001d889  or      esi, 80070000h
0x18001d88f  jmp     loc_18001D744
0x18001d894  mov     r9d, [r12+168h]
0x18001d89c  xor     eax, eax
0x18001d89e  mov     [rsp+68h+var_30], r13
0x18001d8a3  mov     [rsp+68h+var_38], r14
0x18001d8a8  jmp     loc_18001D820
0x18001d8ad  mov     esi, 80004003h
0x18001d8b2  jmp     loc_18001D69C
0x18001d8b7  mov     esi, 80070057h
0x18001d8bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8c3  lea     rax, WPP_GLOBAL_Control
0x18001d8ca  cmp     rcx, rax
0x18001d8cd  jz      loc_18001D67C
0x18001d8d3  test    byte ptr [rcx+1Ch], 1
0x18001d8d7  jz      loc_18001D67C
0x18001d8dd  mov     rax, [r14+18h]
0x18001d8e1  mov     r9, [r14]
0x18001d8e4  mov     rcx, [rcx+10h]
0x18001d8e8  mov     [rsp+68h+var_40], esi
0x18001d8ec  mov     [rsp+68h+var_48], rax
0x18001d8f1  call    WPP_SF_ssd
0x18001d8f6  jmp     loc_18001D69C
0x18001d8fb  cmp     eax, 102h
0x18001d900  jz      loc_18001D744
0x18001d906  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d90d  cmp     rcx, r15
0x18001d910  jz      loc_18001D876
0x18001d916  test    byte ptr [rcx+1Ch], 40h
0x18001d91a  jz      loc_18001D876
0x18001d920  mov     rcx, [rcx+10h]
0x18001d924  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001d92b  mov     edx, 36h ; '6'
0x18001d930  mov     r9d, eax
0x18001d933  call    WPP_SF_d
0x18001d938  jmp     loc_18001D876
0x18001d93d  mov     esi, 8007000Eh
0x18001d942  jmp     loc_18001D85E
0x18001d947  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d94e  lea     rax, WPP_GLOBAL_Control
0x18001d955  cmp     rcx, rax
0x18001d958  jz      loc_18001D5B5
0x18001d95e  test    byte ptr [rcx+1Ch], 1
0x18001d962  jz      loc_18001D5B5
0x18001d968  mov     rcx, [rcx+10h]
0x18001d96c  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001d973  mov     edx, 37h ; '7'
0x18001d978  mov     r9d, esi
0x18001d97b  call    WPP_SF_d
0x18001d980  jmp     loc_18001D5B5
```
