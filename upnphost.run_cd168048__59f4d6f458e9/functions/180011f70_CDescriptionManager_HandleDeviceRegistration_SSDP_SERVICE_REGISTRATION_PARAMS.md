# CDescriptionManager::HandleDeviceRegistration(SSDP_SERVICE_REGISTRATION_PARAMS *)

- ea: `0x180011f70`
- end: `0x180012483`
- name: `?HandleDeviceRegistration@CDescriptionManager@@AEAAJPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z`
- size: `1299`
- prototype: `int(CDescriptionManager *__hidden this, struct SSDP_SERVICE_REGISTRATION_PARAMS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011ec0`

## callees

- `0x18000b0d0`
- `0x18000e298`
- `0x18000e478`
- `0x18000e4b0`
- `0x180010780`
- `0x180011f70`
- `0x18001248c`
- `0x18001252c`
- `0x180012598`
- `0x18003b1cc`
- `0x18004e0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800120e8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800120e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001204a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001204a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800121f2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012279`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800121f2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001236e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001236e`
- `SSDPAPI!DeregisterService` at `0x1800121d0`
- `SSDPAPI!DeregisterService` at `0x1800121d0`
- `SSDPAPI!RegisterServiceEx` at `0x180012149`
- `SSDPAPI!RegisterServiceEx` at `0x180012149`

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
  __int64 v8; // rdx
  const struct _GUID *v9; // rbp
  signed int v10; // esi
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
  v8 = *((_QWORD *)v4 + 4);
  v9 = (const struct _GUID *)((char *)v4 + 52);
  if ( v8 )
  {
    v10 = CDescriptionManager::HandleDeviceDeregistration(v3, v8, (char *)v4 + 52);
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
            if ( v17[2] != v24 || (v10 = CUArray<_TP_WORK *>::HrSetReserve(v17, (unsigned int)(v24 + 50)), v10 >= 0) )
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
0x180011f70  mov     [rsp+arg_8], rdx
0x180011f75  mov     [rsp+arg_0], rcx
0x180011f7a  push    rbx
0x180011f7b  push    rdi
0x180011f7c  push    r12
0x180011f7e  push    r15
0x180011f80  sub     rsp, 48h
0x180011f84  lea     rbx, [rcx+1E8h]
0x180011f8b  mov     r12, rcx
0x180011f8e  mov     rcx, rbx; lpCriticalSection
0x180011f91  mov     [rsp+68h+arg_10], rbx
0x180011f99  mov     r15, rdx
0x180011f9c  xor     edi, edi
0x180011f9e  call    cs:__imp_EnterCriticalSection
0x180011fa5  nop     dword ptr [rax+rax+00h]
0x180011faa  lea     r8, [r12+260h]
0x180011fb2  mov     rdx, [r8]
0x180011fb5  cmp     rdx, r8
0x180011fb8  jz      short loc_180011FCF
0x180011fba  test    edi, edi
0x180011fbc  jnz     short loc_180011FCF
0x180011fbe  cmp     rdx, r15
0x180011fc1  jz      loc_1800120A0
0x180011fc7  mov     rdx, [rdx]
0x180011fca  cmp     rdx, r8
0x180011fcd  jnz     short loc_180011FBA
0x180011fcf  mov     rcx, rbx; lpCriticalSection
0x180011fd2  mov     [rsp+68h+var_28], rsi
0x180011fd7  call    cs:__imp_LeaveCriticalSection
0x180011fde  nop     dword ptr [rax+rax+00h]
0x180011fe3  test    edi, edi
0x180011fe5  jz      loc_1800120B8
0x180011feb  mov     rdx, [r15+20h]
0x180011fef  mov     [rsp+68h+arg_18], rbp
0x180011ff7  lea     rbp, [r15+34h]
0x180011ffb  test    rdx, rdx
0x180011ffe  jz      loc_180012392
0x180012004  mov     r8, rbp
0x180012007  mov     rcx, r12
0x18001200a  call    ?HandleDeviceDeregistration@CDescriptionManager@@AEAAJPEAV?$CUArray@PEAX@@AEBU_GUID@@@Z; CDescriptionManager::HandleDeviceDeregistration(CUArray<void *> *,_GUID const &)
0x18001200f  mov     esi, eax
0x180012011  jmp     short loc_180012047
0x180012013  mov     r12, [rsp+68h+arg_0]
0x180012018  lea     rbp, [r15+34h]
0x18001201c  mov     r9, rdi
0x18001201f  mov     rdx, rbp
0x180012022  mov     rcx, r12
0x180012025  call    ?HrPublishCompletion@CDescriptionManager@@AEAAJAEBU_GUID@@JPEAV?$CUArray@PEAX@@@Z; CDescriptionManager::HrPublishCompletion(_GUID const &,long,CUArray<void *> *)
0x18001202a  mov     esi, eax
0x18001202c  test    eax, eax
0x18001202e  js      loc_1800121A5
0x180012034  test    r13d, r13d
0x180012037  jnz     loc_180012356
0x18001203d  mov     r13, [rsp+68h+var_30]
0x180012042  mov     r14, [rsp+68h+var_38]
0x180012047  mov     rcx, rbx; lpCriticalSection
0x18001204a  call    cs:__imp_EnterCriticalSection
0x180012051  nop     dword ptr [rax+rax+00h]
0x180012056  lea     rcx, [r12+140h]
0x18001205e  mov     rdx, rbp
0x180012061  call    ?HrErase@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAJAEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::HrErase(_GUID const &)
0x180012066  mov     rcx, rbx; lpCriticalSection
0x180012069  call    cs:__imp_LeaveCriticalSection
0x180012070  nop     dword ptr [rax+rax+00h]
0x180012075  mov     rdx, r15; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x180012078  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18001207d  mov     rbp, [rsp+68h+arg_18]
0x180012085  test    esi, esi
0x180012087  jnz     loc_180012445
0x18001208d  mov     eax, esi
0x18001208f  mov     rsi, [rsp+68h+var_28]
0x180012094  add     rsp, 48h
0x180012098  pop     r15
0x18001209a  pop     r12
0x18001209c  pop     rdi
0x18001209d  pop     rbx
0x18001209e  retn
0x1800120a0  mov     rax, [r15+8]
0x1800120a4  mov     edi, 1
0x1800120a9  mov     rcx, [r15]
0x1800120ac  mov     [rax], rcx
0x1800120af  mov     [rcx+8], rax
0x1800120b3  jmp     loc_180011FCA
0x1800120b8  mov     rsi, [rsp+68h+var_28]
0x1800120bd  mov     eax, 80004005h
0x1800120c2  add     rsp, 48h
0x1800120c6  pop     r15
0x1800120c8  pop     r12
0x1800120ca  pop     rdi
0x1800120cb  pop     rbx
0x1800120cc  retn
0x1800120ce  mov     rax, [r12+170h]
0x1800120d6  lea     rcx, [rax+rdx*4]; this
0x1800120da  test    rcx, rcx
0x1800120dd  jz      loc_180012351
0x1800120e3  mov     ecx, 10h; Size
0x1800120e8  call    cs:__imp_malloc
0x1800120ef  nop     dword ptr [rax+rax+00h]
0x1800120f4  mov     rdi, rax
0x1800120f7  test    rax, rax
0x1800120fa  jz      loc_18001243B
0x180012100  xor     esi, esi
0x180012102  xor     r13d, r13d
0x180012105  xor     ebp, ebp
0x180012107  mov     [rax], rsi
0x18001210a  mov     [rax+8], rsi
0x18001210e  cmp     [r15+28h], esi
0x180012112  jle     loc_180012018
0x180012118  test    esi, esi
0x18001211a  js      loc_18001230E
0x180012120  test    r13d, r13d
0x180012123  jnz     loc_180012013
0x180012129  mov     rax, [r15+10h]
0x18001212d  movsxd  rcx, ebp
0x180012130  mov     r14, [rax+rcx*8]
0x180012134  test    r14, r14
0x180012137  jz      loc_1800123AB
0x18001213d  mov     rdx, [r15+18h]
0x180012141  xor     esi, esi
0x180012143  mov     edx, [rdx+rcx*4]
0x180012146  mov     rcx, r14
0x180012149  call    cs:__imp_RegisterServiceEx
0x180012150  nop     dword ptr [rax+rax+00h]
0x180012155  mov     r12, rax
0x180012158  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001215c  jz      loc_1800123B5
0x180012162  test    esi, esi
0x180012164  js      short loc_180012182
0x180012166  mov     edx, [rdi+0Ch]
0x180012169  cmp     [rdi+8], edx
0x18001216c  jz      loc_1800122E9
0x180012172  movsxd  rcx, dword ptr [rdi+8]
0x180012176  mov     rax, [rdi]
0x180012179  mov     [rax+rcx*8], r12
0x18001217d  inc     dword ptr [rdi+8]
0x180012180  xor     esi, esi
0x180012182  mov     eax, [r15+28h]
0x180012186  dec     eax
0x180012188  cmp     ebp, eax
0x18001218a  jl      loc_180012268
0x180012190  inc     ebp
0x180012192  cmp     ebp, [r15+28h]
0x180012196  jl      short loc_180012118
0x180012198  mov     r12, [rsp+68h+arg_0]
0x18001219d  test    esi, esi
0x18001219f  jns     loc_180012018
0x1800121a5  mov     r14d, [rdi+8]
0x1800121a9  xor     ebp, ebp
0x1800121ab  test    r14d, r14d
0x1800121ae  jle     loc_18001224F
0x1800121b4  mov     rbx, [rsp+68h+arg_0]
0x1800121b9  lea     r12d, [r14-1]
0x1800121bd  lea     r15, WPP_GLOBAL_Control
0x1800121c4  mov     rcx, [rdi]
0x1800121c7  mov     edx, 1
0x1800121cc  mov     rcx, [rcx+rbp*8]
0x1800121d0  call    cs:__imp_DeregisterService
0x1800121d7  nop     dword ptr [rax+rax+00h]
0x1800121dc  cmp     ebp, r12d
0x1800121df  jge     short loc_180012236
0x1800121e1  test    r13d, r13d
0x1800121e4  jnz     short loc_180012236
0x1800121e6  mov     rcx, [rbx+1E0h]; hHandle
0x1800121ed  mov     edx, 4Bh ; 'K'; dwMilliseconds
0x1800121f2  call    cs:__imp_WaitForSingleObject
0x1800121f9  nop     dword ptr [rax+rax+00h]
0x1800121fe  test    eax, eax
0x180012200  jnz     loc_1800123F9
0x180012206  mov     r13d, 1
0x18001220c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012213  cmp     rcx, r15
0x180012216  jz      short loc_180012236
0x180012218  test    byte ptr [rcx+1Ch], 40h
0x18001221c  jz      short loc_180012236
0x18001221e  mov     rcx, [rcx+10h]
0x180012222  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180012229  mov     edx, 35h ; '5'
0x18001222e  xor     r9d, r9d
0x180012231  call    WPP_SF_d
0x180012236  inc     ebp
0x180012238  cmp     ebp, r14d
0x18001223b  jl      short loc_1800121C4
0x18001223d  mov     rbx, [rsp+68h+arg_10]
0x180012245  mov     r15, [rsp+68h+arg_8]
0x18001224a  mov     r12, [rsp+68h+arg_0]
0x18001224f  mov     rcx, rdi; void *
0x180012252  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x180012257  lea     rbp, [r15+34h]
0x18001225b  test    esi, esi
0x18001225d  js      loc_180012356
0x180012263  jmp     loc_180012034
0x180012268  mov     rax, [rsp+68h+arg_0]
0x18001226d  mov     edx, 4Bh ; 'K'; dwMilliseconds
0x180012272  mov     rcx, [rax+1E0h]; hHandle
0x180012279  call    cs:__imp_WaitForSingleObject
0x180012280  nop     dword ptr [rax+rax+00h]
0x180012285  test    eax, eax
0x180012287  jz      short loc_180012303
0x180012289  cmp     eax, 102h
0x18001228e  jz      loc_180012190
0x180012294  mov     rcx, cs:WPP_GLOBAL_Control
0x18001229b  lea     rdx, WPP_GLOBAL_Control
0x1800122a2  cmp     rcx, rdx
0x1800122a5  jz      short loc_1800122C5
0x1800122a7  test    byte ptr [rcx+1Ch], 40h
0x1800122ab  jz      short loc_1800122C5
0x1800122ad  mov     rcx, [rcx+10h]
0x1800122b1  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800122b8  mov     edx, 34h ; '4'
0x1800122bd  mov     r9d, eax
0x1800122c0  call    WPP_SF_d
0x1800122c5  call    cs:__imp_GetLastError
0x1800122cc  nop     dword ptr [rax+rax+00h]
0x1800122d1  mov     esi, eax
0x1800122d3  test    eax, eax
0x1800122d5  jle     loc_180012190
0x1800122db  movzx   esi, ax
0x1800122de  or      esi, 80070000h
0x1800122e4  jmp     loc_180012190
0x1800122e9  add     edx, 32h ; '2'
0x1800122ec  mov     rcx, rdi
0x1800122ef  call    ?HrSetReserve@?$CUArray@PEAU_TP_WORK@@@@QEAAJJ@Z; CUArray<_TP_WORK *>::HrSetReserve(long)
0x1800122f4  mov     esi, eax
0x1800122f6  test    eax, eax
0x1800122f8  js      loc_180012182
0x1800122fe  jmp     loc_180012172
0x180012303  mov     r13d, 1
0x180012309  jmp     loc_180012190
0x18001230e  mov     r12, [rsp+68h+arg_0]
0x180012313  jmp     loc_1800121A5
0x180012318  cmp     eax, r9d
0x18001231b  jge     short loc_180012351
0x18001231d  mov     rcx, [r15+34h]
0x180012321  lea     rbp, [r15+34h]
0x180012325  movsxd  rdx, eax
0x180012328  mov     r8, rdx
0x18001232b  shl     r8, 4
0x18001232f  add     r8, [r12+160h]
0x180012337  sub     rcx, [r8]
0x18001233a  jnz     short loc_180012344
0x18001233c  mov     rcx, [rbp+8]
0x180012340  sub     rcx, [r8+8]
0x180012344  test    rcx, rcx
0x180012347  jz      loc_1800120CE
0x18001234d  inc     eax
0x18001234f  jmp     short loc_180012318
0x180012351  mov     esi, 80004005h
0x180012356  mov     rdx, rbp; struct _GUID *
0x180012359  call    ?Hr_DoStopUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStopUrlListening(_GUID const &)
0x18001235e  mov     rdx, rbp; struct _GUID *
0x180012361  mov     rcx, r12; this
0x180012364  call    ?HrRD_RemoveFromEventing@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_RemoveFromEventing(_GUID const &)
0x180012369  jmp     loc_18001203D
0x18001236e  call    cs:__imp_GetLastError
0x180012375  nop     dword ptr [rax+rax+00h]
0x18001237a  mov     esi, eax
0x18001237c  test    eax, eax
0x18001237e  jle     loc_180012236
0x180012384  movzx   esi, ax
0x180012387  or      esi, 80070000h
0x18001238d  jmp     loc_180012236
0x180012392  mov     r9d, [r12+168h]
0x18001239a  xor     eax, eax
0x18001239c  mov     [rsp+68h+var_30], r13
0x1800123a1  mov     [rsp+68h+var_38], r14
0x1800123a6  jmp     loc_180012318
0x1800123ab  mov     esi, 80004003h
0x1800123b0  jmp     loc_180012182
0x1800123b5  mov     esi, 80070057h
0x1800123ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123c1  lea     rax, WPP_GLOBAL_Control
0x1800123c8  cmp     rcx, rax
0x1800123cb  jz      loc_180012162
0x1800123d1  test    byte ptr [rcx+1Ch], 1
0x1800123d5  jz      loc_180012162
0x1800123db  mov     rax, [r14+18h]
0x1800123df  mov     r9, [r14]
0x1800123e2  mov     rcx, [rcx+10h]
0x1800123e6  mov     [rsp+68h+var_40], esi
0x1800123ea  mov     [rsp+68h+var_48], rax
0x1800123ef  call    WPP_SF_ssd
0x1800123f4  jmp     loc_180012182
0x1800123f9  cmp     eax, 102h
0x1800123fe  jz      loc_180012236
0x180012404  mov     rcx, cs:WPP_GLOBAL_Control
0x18001240b  cmp     rcx, r15
0x18001240e  jz      loc_18001236E
0x180012414  test    byte ptr [rcx+1Ch], 40h
0x180012418  jz      loc_18001236E
0x18001241e  mov     rcx, [rcx+10h]
0x180012422  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180012429  mov     edx, 36h ; '6'
0x18001242e  mov     r9d, eax
0x180012431  call    WPP_SF_d
0x180012436  jmp     loc_18001236E
0x18001243b  mov     esi, 8007000Eh
0x180012440  jmp     loc_180012356
0x180012445  mov     rcx, cs:WPP_GLOBAL_Control
0x18001244c  lea     rax, WPP_GLOBAL_Control
0x180012453  cmp     rcx, rax
  ... truncated ...
```
