# CAccessInfo::IdentifyAccessWorker(SecurityDescriptorOwner,uint,void * *,ulong *)

- ea: `0x18006d510`
- end: `0x18006da91`
- name: `?IdentifyAccessWorker@CAccessInfo@@AEAAPEAXW4SecurityDescriptorOwner@@IPEAPEAXPEAK@Z`
- size: `1409`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c1ac`
- `0x18006d3ec`

## callees

- `0x180034260`
- `0x18006d510`
- `0x18008172c`
- `0x1800b7ac0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18006d695`
- `ntdll!RtlCopySid` at `0x18006d695`
- `ntdll!RtlLengthSid` at `0x18006d561`
- `ntdll!RtlLengthSid` at `0x18006d561`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d7b7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d86d`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d920`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d7b7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d86d`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006d920`
- `ntdll!RtlAddAce` at `0x18006d6c3`
- `ntdll!RtlAddAce` at `0x18006d6c3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d6eb`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d6eb`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006da4d`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006da4d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d9b8`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d9b8`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d80b`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d8c1`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d971`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d80b`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d8c1`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006d971`
- `ntdll!RtlCreateAcl` at `0x18006d5bf`
- `ntdll!RtlCreateAcl` at `0x18006d5bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d596`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d625`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d596`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d625`

## string_xrefs

- `0x18006da07`: `onecore\com\combase\rpcss\olescm\access.cxx`
- `0x18006d9fb`: `CAccessInfo::IdentifyAccessWorker`

## pseudocode

```c
PSID __fastcall CAccessInfo::IdentifyAccessWorker(PSID *a1, int a2, unsigned int a3, __int64 a4, __int64 a5)
{
  int v9; // r15d
  ULONG v10; // ebp
  __int64 i; // r14
  ULONG v12; // eax
  int v13; // ebx
  struct _ACL *v14; // rax
  struct _ACL *v15; // r14
  NTSTATUS Acl; // r8d
  int v17; // r8d
  unsigned int v18; // ebp
  LPVOID v19; // rax
  unsigned int v20; // ebx
  ULONG v21; // ebp
  NTSTATUS v22; // r8d
  NTSTATUS v23; // r8d
  NTSTATUS SecurityDescriptor; // r8d
  NTSTATUS v25; // r8d
  NTSTATUS v26; // r8d
  NTSTATUS v27; // r8d
  NTSTATUS v28; // r8d
  NTSTATUS v29; // r8d
  NTSTATUS v30; // r8d
  NTSTATUS v31; // r8d
  NTSTATUS v33; // r8d
  NTSTATUS v34; // [rsp+28h] [rbp-A0h]
  ULONG DestinationSidLength[20]; // [rsp+30h] [rbp-98h]

  if ( a3 > 0x14 )
    return 0;
  v9 = 0;
  v10 = 0;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v12 = RtlLengthSid(*(PSID *)(a4 + 8 * i));
    v9 += v12;
    DestinationSidLength[i] = v12;
    if ( v10 <= v12 )
      v10 = v12;
  }
  v13 = v9 + 12 * a3;
  v14 = (struct _ACL *)HeapAlloc(g_hHeap, 0, (unsigned int)(v13 + 48));
  a1[4] = v14;
  if ( !v14 )
    return 0;
  v15 = v14 + 5;
  Acl = RtlCreateAcl(v14 + 5, v13 + 8, 2u);
  if ( Acl < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return 0;
    v34 = Acl;
    v17 = 229;
    goto LABEL_70;
  }
  v18 = v10 + 12;
  if ( v18 > 0x70 )
  {
    v19 = HeapAlloc(g_hHeap, 0, v18);
    a1[5] = v19;
    if ( !v19 )
      return 0;
  }
  else
  {
    a1[5] = a1 + 6;
  }
  v20 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      *(_BYTE *)a1[5] = 0;
      *((_WORD *)a1[5] + 1) = LOWORD(DestinationSidLength[v20]) + 12;
      *((_BYTE *)a1[5] + 1) = 0;
      v21 = DestinationSidLength[v20];
      *((_DWORD *)a1[5] + 1) = *(_DWORD *)(a5 + 4LL * v20);
      v22 = RtlCopySid(v21, (char *)a1[5] + 8, *(PSID *)(a4 + 8LL * v20));
      if ( v22 < 0 )
        break;
      v23 = RtlAddAce(v15, 2u, 0xFFFFFFFF, a1[5], v21 + 12);
      if ( v23 < 0 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v34 = v23;
          v17 = 286;
          goto LABEL_70;
        }
        return 0;
      }
      if ( ++v20 >= a3 )
        goto LABEL_19;
    }
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v34 = v22;
      v17 = 272;
      goto LABEL_70;
    }
    return 0;
  }
LABEL_19:
  SecurityDescriptor = RtlCreateSecurityDescriptor(a1[4], 1u);
  if ( SecurityDescriptor < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return 0;
    v34 = SecurityDescriptor;
    v17 = 308;
    goto LABEL_70;
  }
  if ( a2 != 2 )
  {
    if ( a2 == 1 )
    {
      v27 = RtlSetOwnerSecurityDescriptor(a1[4], psidStateServiceSid, 0);
      if ( v27 >= 0 )
      {
        v28 = RtlSetGroupSecurityDescriptor(a1[4], psidStateServiceSid, 0);
        if ( v28 >= 0 )
          goto LABEL_65;
        if ( !dword_1801574B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
        {
          return 0;
        }
        v34 = v28;
        v17 = 360;
      }
      else
      {
        if ( !dword_1801574B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
        {
          return 0;
        }
        v34 = v27;
        v17 = 348;
      }
    }
    else
    {
      if ( a2 != 3 )
        goto LABEL_65;
      v29 = RtlSetOwnerSecurityDescriptor(a1[4], a1[1], 0);
      if ( v29 >= 0 )
      {
        v30 = RtlSetGroupSecurityDescriptor(a1[4], a1[1], 0);
        if ( v30 >= 0 )
          goto LABEL_65;
        if ( !dword_1801574B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
        {
          return 0;
        }
        v34 = v30;
        v17 = 386;
      }
      else
      {
        if ( !dword_1801574B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
        {
          return 0;
        }
        v34 = v29;
        v17 = 374;
      }
    }
LABEL_70:
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\access.cxx",
      (unsigned int)"CAccessInfo::IdentifyAccessWorker",
      v17,
      0,
      (__int64)L"%!STATUS!",
      v34);
    return 0;
  }
  v25 = RtlSetOwnerSecurityDescriptor(a1[4], psidLaunchServiceSid, 0);
  if ( v25 < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return 0;
    v34 = v25;
    v17 = 322;
    goto LABEL_70;
  }
  v26 = RtlSetGroupSecurityDescriptor(a1[4], psidLaunchServiceSid, 0);
  if ( v26 < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return 0;
    v34 = v26;
    v17 = 334;
    goto LABEL_70;
  }
LABEL_65:
  v31 = RtlSetDaclSecurityDescriptor(a1[4], 1u, v15, 0);
  if ( v31 < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return 0;
    v34 = v31;
    v17 = 401;
    goto LABEL_70;
  }
  v33 = RtlSetSaclSecurityDescriptor(a1[4], 0, 0, 0);
  if ( v33 < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return 0;
    v34 = v33;
    v17 = 414;
    goto LABEL_70;
  }
  return a1[4];
}

```

## disassembly

```asm
0x18006d510  mov     [rsp+arg_8], rbx
0x18006d515  push    rbp
0x18006d516  push    rsi
0x18006d517  push    rdi
0x18006d518  push    r12
0x18006d51a  push    r13
0x18006d51c  push    r14
0x18006d51e  push    r15
0x18006d520  sub     rsp, 90h
0x18006d527  mov     rax, cs:__security_cookie
0x18006d52e  xor     rax, rsp
0x18006d531  mov     [rsp+0C8h+var_48], rax
0x18006d539  mov     r13, r9
0x18006d53c  mov     esi, r8d
0x18006d53f  mov     r12d, edx
0x18006d542  mov     rdi, rcx
0x18006d545  cmp     r8d, 14h
0x18006d549  ja      loc_18006DA13
0x18006d54f  xor     r15d, r15d
0x18006d552  xor     ebp, ebp
0x18006d554  xor     r14d, r14d
0x18006d557  test    r8d, r8d
0x18006d55a  jz      short loc_18006D582
0x18006d55c  mov     rcx, [r13+r14*8+0]; Sid
0x18006d561  call    cs:__imp_RtlLengthSid
0x18006d568  nop     dword ptr [rax+rax+00h]
0x18006d56d  add     r15d, eax
0x18006d570  mov     [rsp+r14*4+0C8h+DestinationSidLength], eax
0x18006d575  cmp     ebp, eax
0x18006d577  cmovbe  ebp, eax
0x18006d57a  inc     r14d
0x18006d57d  cmp     r14d, esi
0x18006d580  jb      short loc_18006D55C
0x18006d582  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006d589  lea     eax, [rsi+rsi*2]
0x18006d58c  lea     ebx, [r15+rax*4]
0x18006d590  xor     edx, edx; dwFlags
0x18006d592  lea     r8d, [rbx+30h]; dwBytes
0x18006d596  call    cs:__imp_HeapAlloc
0x18006d59d  nop     dword ptr [rax+rax+00h]
0x18006d5a2  mov     [rdi+20h], rax
0x18006d5a6  test    rax, rax
0x18006d5a9  jz      loc_18006DA13
0x18006d5af  lea     r14, [rax+28h]
0x18006d5b3  mov     r8d, 2; AclRevision
0x18006d5b9  mov     rcx, r14; Acl
0x18006d5bc  lea     edx, [rbx+8]; AclSize
0x18006d5bf  call    cs:__imp_RtlCreateAcl
0x18006d5c6  nop     dword ptr [rax+rax+00h]
0x18006d5cb  mov     r8d, eax
0x18006d5ce  test    eax, eax
0x18006d5d0  jns     short loc_18006D605
0x18006d5d2  mov     ecx, cs:dword_1801574B8
0x18006d5d8  test    ecx, ecx
0x18006d5da  jnz     short loc_18006D5F5
0x18006d5dc  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18006d5e2  jz      loc_18006DA13
0x18006d5e8  call    IsWppLevelEnabled
0x18006d5ed  test    al, al
0x18006d5ef  jz      loc_18006DA13
0x18006d5f5  mov     [rsp+0C8h+var_A0], r8d
0x18006d5fa  mov     r8d, 0E5h
0x18006d600  jmp     loc_18006D9F1
0x18006d605  add     ebp, 0Ch
0x18006d608  cmp     ebp, 70h ; 'p'
0x18006d60b  ja      short loc_18006D619
0x18006d60d  lea     rax, [rdi+30h]
0x18006d611  xor     ebp, ebp
0x18006d613  mov     [rdi+28h], rax
0x18006d617  jmp     short loc_18006D640
0x18006d619  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006d620  xor     edx, edx; dwFlags
0x18006d622  mov     r8d, ebp; dwBytes
0x18006d625  call    cs:__imp_HeapAlloc
0x18006d62c  nop     dword ptr [rax+rax+00h]
0x18006d631  xor     ebp, ebp
0x18006d633  mov     [rdi+28h], rax
0x18006d637  test    rax, rax
0x18006d63a  jz      loc_18006DA13
0x18006d640  mov     r15, [rsp+0C8h+arg_20]
0x18006d648  mov     ebx, ebp
0x18006d64a  test    esi, esi
0x18006d64c  jz      loc_18006D6E2
0x18006d652  mov     rax, [rdi+28h]
0x18006d656  mov     r8d, ebx
0x18006d659  mov     [rax], bpl
0x18006d65c  mov     rax, [rdi+28h]
0x18006d660  movzx   ecx, word ptr [rsp+r8*4+0C8h+DestinationSidLength]
0x18006d666  add     cx, 0Ch
0x18006d66a  mov     [rax+2], cx
0x18006d66e  mov     rax, [rdi+28h]
0x18006d672  mov     [rax+1], bpl
0x18006d676  mov     rcx, [rdi+28h]
0x18006d67a  mov     eax, [r15+r8*4]
0x18006d67e  mov     ebp, [rsp+r8*4+0C8h+DestinationSidLength]
0x18006d683  mov     [rcx+4], eax
0x18006d686  mov     ecx, ebp; DestinationSidLength
0x18006d688  mov     rdx, [rdi+28h]
0x18006d68c  mov     r8, [r13+r8*8+0]; SourceSid
0x18006d691  add     rdx, 8; DestinationSid
0x18006d695  call    cs:__imp_RtlCopySid
0x18006d69c  nop     dword ptr [rax+rax+00h]
0x18006d6a1  mov     r8d, eax
0x18006d6a4  test    eax, eax
0x18006d6a6  js      loc_18006D76A
0x18006d6ac  mov     r9, [rdi+28h]; AceList
0x18006d6b0  lea     eax, [rbp+0Ch]
0x18006d6b3  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18006d6b7  mov     [rsp+0C8h+AceListLength], eax; AceListLength
0x18006d6bb  mov     edx, 2; AceRevision
0x18006d6c0  mov     rcx, r14; Acl
0x18006d6c3  call    cs:__imp_RtlAddAce
0x18006d6ca  nop     dword ptr [rax+rax+00h]
0x18006d6cf  xor     ebp, ebp
0x18006d6d1  mov     r8d, eax
0x18006d6d4  test    eax, eax
0x18006d6d6  js      short loc_18006D735
0x18006d6d8  inc     ebx
0x18006d6da  cmp     ebx, esi
0x18006d6dc  jb      loc_18006D652
0x18006d6e2  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d6e6  mov     edx, 1; Revision
0x18006d6eb  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006d6f2  nop     dword ptr [rax+rax+00h]
0x18006d6f7  mov     r8d, eax
0x18006d6fa  test    eax, eax
0x18006d6fc  jns     loc_18006D79F
0x18006d702  mov     ecx, cs:dword_1801574B8
0x18006d708  test    ecx, ecx
0x18006d70a  jnz     short loc_18006D725
0x18006d70c  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d712  jz      loc_18006DA13
0x18006d718  call    IsWppLevelEnabled
0x18006d71d  test    al, al
0x18006d71f  jz      loc_18006DA13
0x18006d725  mov     [rsp+0C8h+var_A0], r8d
0x18006d72a  mov     r8d, 134h
0x18006d730  jmp     loc_18006D9F1
0x18006d735  mov     eax, cs:dword_1801574B8
0x18006d73b  test    eax, eax
0x18006d73d  jnz     short loc_18006D75A
0x18006d73f  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d745  jz      loc_18006DA13
0x18006d74b  xor     ecx, ecx
0x18006d74d  call    IsWppLevelEnabled
0x18006d752  test    al, al
0x18006d754  jz      loc_18006DA13
0x18006d75a  mov     [rsp+0C8h+var_A0], r8d
0x18006d75f  mov     r8d, 11Eh
0x18006d765  jmp     loc_18006D9F1
0x18006d76a  mov     eax, cs:dword_1801574B8
0x18006d770  test    eax, eax
0x18006d772  jnz     short loc_18006D78F
0x18006d774  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18006d77a  jz      loc_18006DA13
0x18006d780  xor     ecx, ecx
0x18006d782  call    IsWppLevelEnabled
0x18006d787  test    al, al
0x18006d789  jz      loc_18006DA13
0x18006d78f  mov     [rsp+0C8h+var_A0], r8d
0x18006d794  mov     r8d, 110h
0x18006d79a  jmp     loc_18006D9F1
0x18006d79f  cmp     r12d, 2
0x18006d7a3  jnz     loc_18006D855
0x18006d7a9  mov     rdx, cs:?psidLaunchServiceSid@@3PEAXEA; Owner
0x18006d7b0  xor     r8d, r8d; OwnerDefaulted
0x18006d7b3  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d7b7  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18006d7be  nop     dword ptr [rax+rax+00h]
0x18006d7c3  mov     r8d, eax
0x18006d7c6  test    eax, eax
0x18006d7c8  jns     short loc_18006D7FD
0x18006d7ca  mov     ecx, cs:dword_1801574B8
0x18006d7d0  test    ecx, ecx
0x18006d7d2  jnz     short loc_18006D7ED
0x18006d7d4  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d7da  jz      loc_18006DA13
0x18006d7e0  call    IsWppLevelEnabled
0x18006d7e5  test    al, al
0x18006d7e7  jz      loc_18006DA13
0x18006d7ed  mov     [rsp+0C8h+var_A0], r8d
0x18006d7f2  mov     r8d, 142h
0x18006d7f8  jmp     loc_18006D9F1
0x18006d7fd  mov     rdx, cs:?psidLaunchServiceSid@@3PEAXEA; Group
0x18006d804  xor     r8d, r8d; GroupDefaulted
0x18006d807  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d80b  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006d812  nop     dword ptr [rax+rax+00h]
0x18006d817  mov     r8d, eax
0x18006d81a  test    eax, eax
0x18006d81c  jns     loc_18006D9AC
0x18006d822  mov     ecx, cs:dword_1801574B8
0x18006d828  test    ecx, ecx
0x18006d82a  jnz     short loc_18006D845
0x18006d82c  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d832  jz      loc_18006DA13
0x18006d838  call    IsWppLevelEnabled
0x18006d83d  test    al, al
0x18006d83f  jz      loc_18006DA13
0x18006d845  mov     [rsp+0C8h+var_A0], r8d
0x18006d84a  mov     r8d, 14Eh
0x18006d850  jmp     loc_18006D9F1
0x18006d855  cmp     r12d, 1
0x18006d859  jnz     loc_18006D90B
0x18006d85f  mov     rdx, cs:?psidStateServiceSid@@3PEAXEA; Owner
0x18006d866  xor     r8d, r8d; OwnerDefaulted
0x18006d869  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d86d  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18006d874  nop     dword ptr [rax+rax+00h]
0x18006d879  mov     r8d, eax
0x18006d87c  test    eax, eax
0x18006d87e  jns     short loc_18006D8B3
0x18006d880  mov     ecx, cs:dword_1801574B8
0x18006d886  test    ecx, ecx
0x18006d888  jnz     short loc_18006D8A3
0x18006d88a  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d890  jz      loc_18006DA13
0x18006d896  call    IsWppLevelEnabled
0x18006d89b  test    al, al
0x18006d89d  jz      loc_18006DA13
0x18006d8a3  mov     [rsp+0C8h+var_A0], r8d
0x18006d8a8  mov     r8d, 15Ch
0x18006d8ae  jmp     loc_18006D9F1
0x18006d8b3  mov     rdx, cs:?psidStateServiceSid@@3PEAXEA; Group
0x18006d8ba  xor     r8d, r8d; GroupDefaulted
0x18006d8bd  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d8c1  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006d8c8  nop     dword ptr [rax+rax+00h]
0x18006d8cd  mov     r8d, eax
0x18006d8d0  test    eax, eax
0x18006d8d2  jns     loc_18006D9AC
0x18006d8d8  mov     ecx, cs:dword_1801574B8
0x18006d8de  test    ecx, ecx
0x18006d8e0  jnz     short loc_18006D8FB
0x18006d8e2  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d8e8  jz      loc_18006DA13
0x18006d8ee  call    IsWppLevelEnabled
0x18006d8f3  test    al, al
0x18006d8f5  jz      loc_18006DA13
0x18006d8fb  mov     [rsp+0C8h+var_A0], r8d
0x18006d900  mov     r8d, 168h
0x18006d906  jmp     loc_18006D9F1
0x18006d90b  cmp     r12d, 3
0x18006d90f  jnz     loc_18006D9AC
0x18006d915  mov     rdx, [rdi+8]; Owner
0x18006d919  xor     r8d, r8d; OwnerDefaulted
0x18006d91c  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d920  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18006d927  nop     dword ptr [rax+rax+00h]
0x18006d92c  mov     r8d, eax
0x18006d92f  test    eax, eax
0x18006d931  jns     short loc_18006D966
0x18006d933  mov     ecx, cs:dword_1801574B8
0x18006d939  test    ecx, ecx
0x18006d93b  jnz     short loc_18006D956
0x18006d93d  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d943  jz      loc_18006DA13
0x18006d949  call    IsWppLevelEnabled
0x18006d94e  test    al, al
0x18006d950  jz      loc_18006DA13
0x18006d956  mov     [rsp+0C8h+var_A0], r8d
0x18006d95b  mov     r8d, 176h
0x18006d961  jmp     loc_18006D9F1
0x18006d966  mov     rdx, [rdi+8]; Group
0x18006d96a  xor     r8d, r8d; GroupDefaulted
0x18006d96d  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d971  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006d978  nop     dword ptr [rax+rax+00h]
0x18006d97d  mov     r8d, eax
0x18006d980  test    eax, eax
0x18006d982  jns     short loc_18006D9AC
0x18006d984  mov     ecx, cs:dword_1801574B8
0x18006d98a  test    ecx, ecx
0x18006d98c  jnz     short loc_18006D99F
0x18006d98e  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d994  jz      short loc_18006DA13
0x18006d996  call    IsWppLevelEnabled
0x18006d99b  test    al, al
0x18006d99d  jz      short loc_18006DA13
0x18006d99f  mov     [rsp+0C8h+var_A0], r8d
0x18006d9a4  mov     r8d, 182h
0x18006d9aa  jmp     short loc_18006D9F1
0x18006d9ac  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006d9b0  xor     r9d, r9d; DaclDefaulted
0x18006d9b3  mov     r8, r14; Dacl
0x18006d9b6  mov     dl, 1; DaclPresent
0x18006d9b8  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006d9bf  nop     dword ptr [rax+rax+00h]
0x18006d9c4  mov     r8d, eax
0x18006d9c7  test    eax, eax
0x18006d9c9  jns     short loc_18006DA41
0x18006d9cb  mov     ecx, cs:dword_1801574B8
0x18006d9d1  test    ecx, ecx
0x18006d9d3  jnz     short loc_18006D9E6
0x18006d9d5  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006d9db  jz      short loc_18006DA13
0x18006d9dd  call    IsWppLevelEnabled
0x18006d9e2  test    al, al
0x18006d9e4  jz      short loc_18006DA13
0x18006d9e6  mov     [rsp+0C8h+var_A0], r8d
  ... truncated ...
```
