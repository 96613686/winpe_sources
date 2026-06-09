# CAccessInfo::IdentifyAccessWorker(SecurityDescriptorOwner,uint,void * *,ulong *)

- ea: `0x1800685d8`
- end: `0x180068af7`
- name: `?IdentifyAccessWorker@CAccessInfo@@AEAAPEAXW4SecurityDescriptorOwner@@IPEAPEAXPEAK@Z`
- size: `1311`
- prototype: `PSID __fastcall(PSID *, int, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052210`
- `0x1800684b4`

## callees

- `0x180034540`
- `0x1800685d8`
- `0x18007e3d4`
- `0x1800b27e0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180068745`
- `ntdll!RtlCopySid` at `0x180068745`
- `ntdll!RtlLengthSid` at `0x180068629`
- `ntdll!RtlLengthSid` at `0x180068629`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180068851`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800688fb`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800689a2`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180068851`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800688fb`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800689a2`
- `ntdll!RtlAddAce` at `0x18006876d`
- `ntdll!RtlAddAce` at `0x18006876d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006878b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006878b`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180068ab9`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180068ab9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180068a2b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180068a2b`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006889f`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180068949`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800689ea`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006889f`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180068949`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800689ea`
- `ntdll!RtlCreateAcl` at `0x18006867b`
- `ntdll!RtlCreateAcl` at `0x18006867b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068658`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800686db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068658`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800686db`

## string_xrefs

- `0x180068a74`: `onecore\com\combase\rpcss\olescm\access.cxx`
- `0x180068a68`: `CAccessInfo::IdentifyAccessWorker`

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
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
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
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
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
        if ( !dword_18014E4B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
        {
          return 0;
        }
        v34 = v28;
        v17 = 360;
      }
      else
      {
        if ( !dword_18014E4B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
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
        if ( !dword_18014E4B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
        {
          return 0;
        }
        v34 = v30;
        v17 = 386;
      }
      else
      {
        if ( !dword_18014E4B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
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
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      return 0;
    v34 = v25;
    v17 = 322;
    goto LABEL_70;
  }
  v26 = RtlSetGroupSecurityDescriptor(a1[4], psidLaunchServiceSid, 0);
  if ( v26 < 0 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      return 0;
    v34 = v26;
    v17 = 334;
    goto LABEL_70;
  }
LABEL_65:
  v31 = RtlSetDaclSecurityDescriptor(a1[4], 1u, v15, 0);
  if ( v31 < 0 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      return 0;
    v34 = v31;
    v17 = 401;
    goto LABEL_70;
  }
  v33 = RtlSetSaclSecurityDescriptor(a1[4], 0, 0, 0);
  if ( v33 < 0 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
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
0x1800685d8  mov     [rsp+arg_8], rbx
0x1800685dd  push    rbp
0x1800685de  push    rsi
0x1800685df  push    rdi
0x1800685e0  push    r12
0x1800685e2  push    r13
0x1800685e4  push    r14
0x1800685e6  push    r15
0x1800685e8  sub     rsp, 90h
0x1800685ef  mov     rax, cs:__security_cookie
0x1800685f6  xor     rax, rsp
0x1800685f9  mov     [rsp+0C8h+var_48], rax
0x180068601  mov     r13, r9
0x180068604  mov     esi, r8d
0x180068607  mov     r12d, edx
0x18006860a  mov     rdi, rcx
0x18006860d  cmp     r8d, 14h
0x180068611  ja      loc_180068A80
0x180068617  xor     r15d, r15d
0x18006861a  xor     ebp, ebp
0x18006861c  xor     r14d, r14d
0x18006861f  test    r8d, r8d
0x180068622  jz      short loc_180068644
0x180068624  mov     rcx, [r13+r14*8+0]; Sid
0x180068629  call    cs:__imp_RtlLengthSid
0x18006862f  add     r15d, eax
0x180068632  mov     [rsp+r14*4+0C8h+DestinationSidLength], eax
0x180068637  cmp     ebp, eax
0x180068639  cmovbe  ebp, eax
0x18006863c  inc     r14d
0x18006863f  cmp     r14d, esi
0x180068642  jb      short loc_180068624
0x180068644  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006864b  lea     eax, [rsi+rsi*2]
0x18006864e  lea     ebx, [r15+rax*4]
0x180068652  xor     edx, edx; dwFlags
0x180068654  lea     r8d, [rbx+30h]; dwBytes
0x180068658  call    cs:__imp_HeapAlloc
0x18006865e  mov     [rdi+20h], rax
0x180068662  test    rax, rax
0x180068665  jz      loc_180068A80
0x18006866b  lea     r14, [rax+28h]
0x18006866f  mov     r8d, 2; AclRevision
0x180068675  mov     rcx, r14; Acl
0x180068678  lea     edx, [rbx+8]; AclSize
0x18006867b  call    cs:__imp_RtlCreateAcl
0x180068681  mov     r8d, eax
0x180068684  test    eax, eax
0x180068686  jns     short loc_1800686BB
0x180068688  mov     ecx, cs:dword_18014E4B8
0x18006868e  test    ecx, ecx
0x180068690  jnz     short loc_1800686AB
0x180068692  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180068698  jz      loc_180068A80
0x18006869e  call    IsWppLevelEnabled
0x1800686a3  test    al, al
0x1800686a5  jz      loc_180068A80
0x1800686ab  mov     [rsp+0C8h+var_A0], r8d
0x1800686b0  mov     r8d, 0E5h
0x1800686b6  jmp     loc_180068A5E
0x1800686bb  add     ebp, 0Ch
0x1800686be  cmp     ebp, 70h ; 'p'
0x1800686c1  ja      short loc_1800686CF
0x1800686c3  lea     rax, [rdi+30h]
0x1800686c7  xor     ebp, ebp
0x1800686c9  mov     [rdi+28h], rax
0x1800686cd  jmp     short loc_1800686F0
0x1800686cf  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800686d6  xor     edx, edx; dwFlags
0x1800686d8  mov     r8d, ebp; dwBytes
0x1800686db  call    cs:__imp_HeapAlloc
0x1800686e1  xor     ebp, ebp
0x1800686e3  mov     [rdi+28h], rax
0x1800686e7  test    rax, rax
0x1800686ea  jz      loc_180068A80
0x1800686f0  mov     r15, [rsp+0C8h+arg_20]
0x1800686f8  mov     ebx, ebp
0x1800686fa  test    esi, esi
0x1800686fc  jz      loc_180068782
0x180068702  mov     rax, [rdi+28h]
0x180068706  mov     r8d, ebx
0x180068709  mov     [rax], bpl
0x18006870c  mov     rax, [rdi+28h]
0x180068710  movzx   ecx, word ptr [rsp+r8*4+0C8h+DestinationSidLength]
0x180068716  add     cx, 0Ch
0x18006871a  mov     [rax+2], cx
0x18006871e  mov     rax, [rdi+28h]
0x180068722  mov     [rax+1], bpl
0x180068726  mov     rcx, [rdi+28h]
0x18006872a  mov     eax, [r15+r8*4]
0x18006872e  mov     ebp, [rsp+r8*4+0C8h+DestinationSidLength]
0x180068733  mov     [rcx+4], eax
0x180068736  mov     ecx, ebp; DestinationSidLength
0x180068738  mov     rdx, [rdi+28h]
0x18006873c  mov     r8, [r13+r8*8+0]; SourceSid
0x180068741  add     rdx, 8; DestinationSid
0x180068745  call    cs:__imp_RtlCopySid
0x18006874b  mov     r8d, eax
0x18006874e  test    eax, eax
0x180068750  js      loc_180068804
0x180068756  mov     r9, [rdi+28h]; AceList
0x18006875a  lea     eax, [rbp+0Ch]
0x18006875d  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x180068761  mov     [rsp+0C8h+AceListLength], eax; AceListLength
0x180068765  mov     edx, 2; AceRevision
0x18006876a  mov     rcx, r14; Acl
0x18006876d  call    cs:__imp_RtlAddAce
0x180068773  xor     ebp, ebp
0x180068775  mov     r8d, eax
0x180068778  test    eax, eax
0x18006877a  js      short loc_1800687CF
0x18006877c  inc     ebx
0x18006877e  cmp     ebx, esi
0x180068780  jb      short loc_180068702
0x180068782  mov     rcx, [rdi+20h]; SecurityDescriptor
0x180068786  mov     edx, 1; Revision
0x18006878b  call    cs:__imp_RtlCreateSecurityDescriptor
0x180068791  mov     r8d, eax
0x180068794  test    eax, eax
0x180068796  jns     loc_180068839
0x18006879c  mov     ecx, cs:dword_18014E4B8
0x1800687a2  test    ecx, ecx
0x1800687a4  jnz     short loc_1800687BF
0x1800687a6  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x1800687ac  jz      loc_180068A80
0x1800687b2  call    IsWppLevelEnabled
0x1800687b7  test    al, al
0x1800687b9  jz      loc_180068A80
0x1800687bf  mov     [rsp+0C8h+var_A0], r8d
0x1800687c4  mov     r8d, 134h
0x1800687ca  jmp     loc_180068A5E
0x1800687cf  mov     eax, cs:dword_18014E4B8
0x1800687d5  test    eax, eax
0x1800687d7  jnz     short loc_1800687F4
0x1800687d9  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x1800687df  jz      loc_180068A80
0x1800687e5  xor     ecx, ecx
0x1800687e7  call    IsWppLevelEnabled
0x1800687ec  test    al, al
0x1800687ee  jz      loc_180068A80
0x1800687f4  mov     [rsp+0C8h+var_A0], r8d
0x1800687f9  mov     r8d, 11Eh
0x1800687ff  jmp     loc_180068A5E
0x180068804  mov     eax, cs:dword_18014E4B8
0x18006880a  test    eax, eax
0x18006880c  jnz     short loc_180068829
0x18006880e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180068814  jz      loc_180068A80
0x18006881a  xor     ecx, ecx
0x18006881c  call    IsWppLevelEnabled
0x180068821  test    al, al
0x180068823  jz      loc_180068A80
0x180068829  mov     [rsp+0C8h+var_A0], r8d
0x18006882e  mov     r8d, 110h
0x180068834  jmp     loc_180068A5E
0x180068839  cmp     r12d, 2
0x18006883d  jnz     loc_1800688E3
0x180068843  mov     rdx, cs:?psidLaunchServiceSid@@3PEAXEA; Owner
0x18006884a  xor     r8d, r8d; OwnerDefaulted
0x18006884d  mov     rcx, [rdi+20h]; SecurityDescriptor
0x180068851  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180068857  mov     r8d, eax
0x18006885a  test    eax, eax
0x18006885c  jns     short loc_180068891
0x18006885e  mov     ecx, cs:dword_18014E4B8
0x180068864  test    ecx, ecx
0x180068866  jnz     short loc_180068881
0x180068868  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006886e  jz      loc_180068A80
0x180068874  call    IsWppLevelEnabled
0x180068879  test    al, al
0x18006887b  jz      loc_180068A80
0x180068881  mov     [rsp+0C8h+var_A0], r8d
0x180068886  mov     r8d, 142h
0x18006888c  jmp     loc_180068A5E
0x180068891  mov     rdx, cs:?psidLaunchServiceSid@@3PEAXEA; Group
0x180068898  xor     r8d, r8d; GroupDefaulted
0x18006889b  mov     rcx, [rdi+20h]; SecurityDescriptor
0x18006889f  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800688a5  mov     r8d, eax
0x1800688a8  test    eax, eax
0x1800688aa  jns     loc_180068A1F
0x1800688b0  mov     ecx, cs:dword_18014E4B8
0x1800688b6  test    ecx, ecx
0x1800688b8  jnz     short loc_1800688D3
0x1800688ba  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x1800688c0  jz      loc_180068A80
0x1800688c6  call    IsWppLevelEnabled
0x1800688cb  test    al, al
0x1800688cd  jz      loc_180068A80
0x1800688d3  mov     [rsp+0C8h+var_A0], r8d
0x1800688d8  mov     r8d, 14Eh
0x1800688de  jmp     loc_180068A5E
0x1800688e3  cmp     r12d, 1
0x1800688e7  jnz     loc_18006898D
0x1800688ed  mov     rdx, cs:?psidStateServiceSid@@3PEAXEA; Owner
0x1800688f4  xor     r8d, r8d; OwnerDefaulted
0x1800688f7  mov     rcx, [rdi+20h]; SecurityDescriptor
0x1800688fb  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180068901  mov     r8d, eax
0x180068904  test    eax, eax
0x180068906  jns     short loc_18006893B
0x180068908  mov     ecx, cs:dword_18014E4B8
0x18006890e  test    ecx, ecx
0x180068910  jnz     short loc_18006892B
0x180068912  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x180068918  jz      loc_180068A80
0x18006891e  call    IsWppLevelEnabled
0x180068923  test    al, al
0x180068925  jz      loc_180068A80
0x18006892b  mov     [rsp+0C8h+var_A0], r8d
0x180068930  mov     r8d, 15Ch
0x180068936  jmp     loc_180068A5E
0x18006893b  mov     rdx, cs:?psidStateServiceSid@@3PEAXEA; Group
0x180068942  xor     r8d, r8d; GroupDefaulted
0x180068945  mov     rcx, [rdi+20h]; SecurityDescriptor
0x180068949  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006894f  mov     r8d, eax
0x180068952  test    eax, eax
0x180068954  jns     loc_180068A1F
0x18006895a  mov     ecx, cs:dword_18014E4B8
0x180068960  test    ecx, ecx
0x180068962  jnz     short loc_18006897D
0x180068964  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18006896a  jz      loc_180068A80
0x180068970  call    IsWppLevelEnabled
0x180068975  test    al, al
0x180068977  jz      loc_180068A80
0x18006897d  mov     [rsp+0C8h+var_A0], r8d
0x180068982  mov     r8d, 168h
0x180068988  jmp     loc_180068A5E
0x18006898d  cmp     r12d, 3
0x180068991  jnz     loc_180068A1F
0x180068997  mov     rdx, [rdi+8]; Owner
0x18006899b  xor     r8d, r8d; OwnerDefaulted
0x18006899e  mov     rcx, [rdi+20h]; SecurityDescriptor
0x1800689a2  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800689a8  mov     r8d, eax
0x1800689ab  test    eax, eax
0x1800689ad  jns     short loc_1800689DF
0x1800689af  mov     ecx, cs:dword_18014E4B8
0x1800689b5  test    ecx, ecx
0x1800689b7  jnz     short loc_1800689D2
0x1800689b9  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x1800689bf  jz      loc_180068A80
0x1800689c5  call    IsWppLevelEnabled
0x1800689ca  test    al, al
0x1800689cc  jz      loc_180068A80
0x1800689d2  mov     [rsp+0C8h+var_A0], r8d
0x1800689d7  mov     r8d, 176h
0x1800689dd  jmp     short loc_180068A5E
0x1800689df  mov     rdx, [rdi+8]; Group
0x1800689e3  xor     r8d, r8d; GroupDefaulted
0x1800689e6  mov     rcx, [rdi+20h]; SecurityDescriptor
0x1800689ea  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800689f0  mov     r8d, eax
0x1800689f3  test    eax, eax
0x1800689f5  jns     short loc_180068A1F
0x1800689f7  mov     ecx, cs:dword_18014E4B8
0x1800689fd  test    ecx, ecx
0x1800689ff  jnz     short loc_180068A12
0x180068a01  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x180068a07  jz      short loc_180068A80
0x180068a09  call    IsWppLevelEnabled
0x180068a0e  test    al, al
0x180068a10  jz      short loc_180068A80
0x180068a12  mov     [rsp+0C8h+var_A0], r8d
0x180068a17  mov     r8d, 182h
0x180068a1d  jmp     short loc_180068A5E
0x180068a1f  mov     rcx, [rdi+20h]; SecurityDescriptor
0x180068a23  xor     r9d, r9d; DaclDefaulted
0x180068a26  mov     r8, r14; Dacl
0x180068a29  mov     dl, 1; DaclPresent
0x180068a2b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180068a31  mov     r8d, eax
0x180068a34  test    eax, eax
0x180068a36  jns     short loc_180068AAD
0x180068a38  mov     ecx, cs:dword_18014E4B8
0x180068a3e  test    ecx, ecx
0x180068a40  jnz     short loc_180068A53
0x180068a42  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x180068a48  jz      short loc_180068A80
0x180068a4a  call    IsWppLevelEnabled
0x180068a4f  test    al, al
0x180068a51  jz      short loc_180068A80
0x180068a53  mov     [rsp+0C8h+var_A0], r8d
0x180068a58  mov     r8d, 191h
0x180068a5e  lea     rax, aStatus; "%!STATUS!"
0x180068a65  xor     r9d, r9d
0x180068a68  lea     rdx, aCaccessinfoIde; "CAccessInfo::IdentifyAccessWorker"
0x180068a6f  mov     qword ptr [rsp+0C8h+AceListLength], rax
0x180068a74  lea     rcx, aOnecoreComComb_10; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x180068a7b  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180068a80  xor     eax, eax
0x180068a82  mov     rcx, [rsp+0C8h+var_48]
0x180068a8a  xor     rcx, rsp; StackCookie
0x180068a8d  call    __security_check_cookie
0x180068a92  mov     rbx, [rsp+0C8h+arg_8]
0x180068a9a  add     rsp, 90h
0x180068aa1  pop     r15
  ... truncated ...
```
