# CreateSecurityDescriptor

- ea: `0x14000d570`
- end: `0x14000d9d1`
- name: `CreateSecurityDescriptor`
- size: `1121`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c4a0`
- `0x14000cb50`
- `0x14000f400`
- `0x14000f5d0`
- `0x14000f8ec`
- `0x14005a68c`
- `0x14005a808`

## callees

- `0x1400057f4`
- `0x14000d570`
- `0x14001a200`
- `0x140041c34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d5c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d646`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d6c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d73e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d5c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d646`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d6c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d73e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d98d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d9a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d98d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d9a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d6b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d72a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d97f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d999`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d6b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d72a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d97f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d999`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d9c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14009d27d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d9c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14009d27d`
- `ntdll!RtlAddAce` at `0x14000d711`
- `ntdll!RtlAddAce` at `0x14000d711`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14000d772`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14000d772`
- `ntdll!RtlCreateAcl` at `0x14000d6e5`
- `ntdll!RtlCreateAcl` at `0x14000d6e5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000d75d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000d75d`
- `ntdll!RtlCopySid` at `0x14000d687`
- `ntdll!RtlCopySid` at `0x14000d687`
- `ntdll!RtlLengthSid` at `0x14000d61f`
- `ntdll!RtlLengthSid` at `0x14000d61f`
- `ntdll!RtlNtStatusToDosError` at `0x14000d9c1`
- `ntdll!RtlNtStatusToDosError` at `0x14009d275`
- `ntdll!RtlNtStatusToDosError` at `0x14000d9c1`
- `ntdll!RtlNtStatusToDosError` at `0x14009d275`

## pseudocode

```c
void *__fastcall CreateSecurityDescriptor(__int64 a1, unsigned int a2)
{
  int v3; // r15d
  struct _ACL *v4; // r12
  void *v5; // r13
  HANDLE ProcessHeap; // rax
  __int64 v7; // r9
  _QWORD *v8; // r14
  int v9; // r15d
  __int64 i; // rsi
  HANDLE v11; // rax
  _WORD *v12; // rax
  __int64 v13; // r9
  _WORD *v14; // rdi
  ULONG v15; // r15d
  HANDLE v16; // rax
  struct _ACL *v17; // rax
  __int64 j; // rdi
  HANDLE v19; // rax
  void *v20; // rax
  CUser *v21; // rcx
  __int64 v22; // rdx
  CUser *v23; // rcx
  __int64 v24; // rdx
  __int64 k; // rdi
  void *v27; // rsi
  HANDLE v28; // rax
  HANDLE v29; // rax
  ULONG v30; // eax
  void *v31; // [rsp+38h] [rbp-70h] BYREF
  struct _ACL *v32; // [rsp+40h] [rbp-68h] BYREF
  int v33; // [rsp+48h] [rbp-60h]
  int v34; // [rsp+4Ch] [rbp-5Ch]
  _QWORD *v35; // [rsp+50h] [rbp-58h]
  ULONG v36; // [rsp+58h] [rbp-50h]
  PSID SourceSid; // [rsp+60h] [rbp-48h]
  char v39; // [rsp+C0h] [rbp+18h]
  ULONG DestinationSidLength; // [rsp+C8h] [rbp+20h]

  v3 = -1073741801;
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v31 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, 8LL * a2);
  v35 = v8;
  if ( v8 )
  {
    v9 = 0;
    v34 = 0;
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      v39 = *(_BYTE *)(a1 + 16LL * (unsigned int)i + 12);
      v33 = *(_DWORD *)(a1 + 16LL * (unsigned int)i + 8);
      SourceSid = *(PSID *)(a1 + 16LL * (unsigned int)i);
      DestinationSidLength = RtlLengthSid(SourceSid);
      v36 = DestinationSidLength + 8;
      v11 = GetProcessHeap();
      v12 = HeapAlloc(v11, 8u, DestinationSidLength + 8);
      v14 = v12;
      if ( v12 )
      {
        *(_BYTE *)v12 = 0;
        v12[1] = (unsigned __int8)(DestinationSidLength + 8);
        *((_BYTE *)v12 + 1) = v39;
        *((_DWORD *)v12 + 1) = v33;
        RtlCopySid(DestinationSidLength, v12 + 4, SourceSid);
      }
      else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids, v13);
      }
      v8[i] = v14;
      if ( !v14 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = 11;
          goto LABEL_40;
        }
        goto LABEL_25;
      }
      v9 += (unsigned __int16)v14[1];
      v34 = v9;
    }
    v15 = v9 + 8;
    v16 = GetProcessHeap();
    v17 = (struct _ACL *)HeapAlloc(v16, 8u, v15);
    v4 = v17;
    v32 = v17;
    if ( !v17 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = 12;
LABEL_40:
        WPP_SF_(*((_QWORD *)v21 + 2), v22, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids, v13);
      }
LABEL_25:
      v3 = -1073741801;
      goto LABEL_47;
    }
    RtlCreateAcl(v17, v15, 2u);
    for ( j = 0; (unsigned int)j < a2; j = (unsigned int)(j + 1) )
    {
      v3 = RtlAddAce(v4, 2u, 0, (PVOID)v8[j], *(unsigned __int16 *)(v8[j] + 2LL));
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids,
            (unsigned int)v3);
        }
        goto LABEL_47;
      }
    }
    v19 = GetProcessHeap();
    v20 = HeapAlloc(v19, 8u, 0x28u);
    v5 = v20;
    v31 = v20;
    if ( v20 )
    {
      RtlCreateSecurityDescriptor(v20, 1u);
      v3 = RtlSetDaclSecurityDescriptor(v5, 1u, v4, 0);
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids,
            (unsigned int)v3);
        }
        UHHeapFree(&v31);
        v5 = v31;
      }
    }
    else
    {
      v3 = -1073741801;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = 14;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = 10;
LABEL_35:
      WPP_SF_(*((_QWORD *)v23 + 2), v24, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids, v7);
    }
  }
LABEL_47:
  if ( v8 )
  {
    for ( k = 0; (unsigned int)k < a2; k = (unsigned int)(k + 1) )
    {
      v27 = (void *)v8[k];
      if ( v27 )
      {
        v28 = GetProcessHeap();
        HeapFree(v28, 0, v27);
      }
    }
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v8);
  }
  if ( !v5 )
  {
    if ( v4 )
      UHHeapFree((void **)&v32);
    v30 = RtlNtStatusToDosError(v3);
    SetLastError(v30);
  }
  return v5;
}

```

## disassembly

```asm
0x14000d570  mov     [rsp+arg_8], edx
0x14000d574  mov     [rsp+arg_0], rcx
0x14000d579  push    rbx
0x14000d57a  push    rsi
0x14000d57b  push    rdi
0x14000d57c  push    r12
0x14000d57e  push    r13
0x14000d580  push    r14
0x14000d582  push    r15
0x14000d584  sub     rsp, 70h
0x14000d588  mov     ebx, edx
0x14000d58a  mov     r15d, 0C0000017h
0x14000d590  mov     [rsp+0A8h+var_78], r15d
0x14000d595  mov     [rsp+0A8h+var_58], 0
0x14000d59e  xor     r12d, r12d
0x14000d5a1  mov     [rsp+0A8h+var_68], r12
0x14000d5a6  xor     r13d, r13d
0x14000d5a9  mov     [rsp+0A8h+var_70], r13
0x14000d5ae  mov     edi, ebx
0x14000d5b0  shl     rdi, 3
0x14000d5b4  call    cs:__imp_GetProcessHeap
0x14000d5ba  mov     rcx, rax; hHeap
0x14000d5bd  mov     r8, rdi; dwBytes
0x14000d5c0  mov     edx, 8; dwFlags
0x14000d5c5  call    cs:__imp_HeapAlloc
0x14000d5cb  mov     r14, rax
0x14000d5ce  mov     [rsp+0A8h+var_58], rax
0x14000d5d3  test    rax, rax
0x14000d5d6  jz      loc_14000D864
0x14000d5dc  xor     r15d, r15d
0x14000d5df  mov     [rsp+0A8h+var_5C], r15d
0x14000d5e4  xor     esi, esi
0x14000d5e6  mov     [rsp+0A8h+var_74], esi
0x14000d5ea  cmp     esi, ebx
0x14000d5ec  jnb     loc_14000D6AD
0x14000d5f2  mov     eax, esi
0x14000d5f4  add     rax, rax
0x14000d5f7  mov     rdx, [rsp+0A8h+arg_0]
0x14000d5ff  movzx   ecx, byte ptr [rdx+rax*8+0Ch]
0x14000d604  mov     [rsp+0A8h+arg_10], cl
0x14000d60b  mov     ecx, [rdx+rax*8+8]
0x14000d60f  mov     [rsp+0A8h+var_60], ecx
0x14000d613  mov     rax, [rdx+rax*8]
0x14000d617  mov     [rsp+0A8h+SourceSid], rax
0x14000d61c  mov     rcx, rax; Sid
0x14000d61f  call    cs:__imp_RtlLengthSid
0x14000d625  mov     [rsp+0A8h+DestinationSidLength], eax
0x14000d62c  add     eax, 8
0x14000d62f  mov     [rsp+0A8h+var_50], eax
0x14000d633  mov     edi, eax
0x14000d635  call    cs:__imp_GetProcessHeap
0x14000d63b  mov     rcx, rax; hHeap
0x14000d63e  mov     r8d, edi; dwBytes
0x14000d641  mov     edx, 8; dwFlags
0x14000d646  call    cs:__imp_HeapAlloc
0x14000d64c  mov     rdi, rax
0x14000d64f  test    rax, rax
0x14000d652  jz      loc_14000D8B0
0x14000d658  mov     byte ptr [rax], 0
0x14000d65b  mov     ecx, [rsp+0A8h+DestinationSidLength]; DestinationSidLength
0x14000d662  lea     eax, [rcx+8]
0x14000d665  movzx   eax, al
0x14000d668  mov     [rdi+2], ax
0x14000d66c  movzx   eax, [rsp+0A8h+arg_10]
0x14000d674  mov     [rdi+1], al
0x14000d677  mov     eax, [rsp+0A8h+var_60]
0x14000d67b  mov     [rdi+4], eax
0x14000d67e  lea     rdx, [rdi+8]; DestinationSid
0x14000d682  mov     r8, [rsp+0A8h+SourceSid]; SourceSid
0x14000d687  call    cs:__imp_RtlCopySid
0x14000d68d  mov     [r14+rsi*8], rdi
0x14000d691  test    rdi, rdi
0x14000d694  jz      loc_14000D83B
0x14000d69a  movzx   eax, word ptr [rdi+2]
0x14000d69e  add     r15d, eax
0x14000d6a1  mov     [rsp+0A8h+var_5C], r15d
0x14000d6a6  inc     esi
0x14000d6a8  jmp     loc_14000D5E6
0x14000d6ad  add     r15d, 8
0x14000d6b1  call    cs:__imp_GetProcessHeap
0x14000d6b7  mov     rcx, rax; hHeap
0x14000d6ba  mov     r8d, r15d; dwBytes
0x14000d6bd  mov     edx, 8; dwFlags
0x14000d6c2  call    cs:__imp_HeapAlloc
0x14000d6c8  mov     r12, rax
0x14000d6cb  mov     [rsp+0A8h+var_68], rax
0x14000d6d0  test    rax, rax
0x14000d6d3  jz      loc_14000D81A
0x14000d6d9  mov     r8d, 2; AclRevision
0x14000d6df  mov     edx, r15d; AclSize
0x14000d6e2  mov     rcx, rax; Acl
0x14000d6e5  call    cs:__imp_RtlCreateAcl
0x14000d6eb  mov     [rsp+0A8h+var_78], eax
0x14000d6ef  xor     edi, edi
0x14000d6f1  mov     [rsp+0A8h+var_74], edi
0x14000d6f5  cmp     edi, ebx
0x14000d6f7  jnb     short loc_14000D72A
0x14000d6f9  mov     r9, [r14+rdi*8]; AceList
0x14000d6fd  movzx   eax, word ptr [r9+2]
0x14000d702  mov     [rsp+0A8h+AceListLength], eax; AceListLength
0x14000d706  xor     r8d, r8d; StartingAceIndex
0x14000d709  mov     edx, 2; AceRevision
0x14000d70e  mov     rcx, r12; Acl
0x14000d711  call    cs:__imp_RtlAddAce
0x14000d717  mov     r15d, eax
0x14000d71a  mov     [rsp+0A8h+var_78], eax
0x14000d71e  test    eax, eax
0x14000d720  js      loc_14000D7D2
0x14000d726  inc     edi
0x14000d728  jmp     short loc_14000D6F1
0x14000d72a  call    cs:__imp_GetProcessHeap
0x14000d730  mov     rcx, rax; hHeap
0x14000d733  mov     edx, 8; dwFlags
0x14000d738  mov     r8d, 28h ; '('; dwBytes
0x14000d73e  call    cs:__imp_HeapAlloc
0x14000d744  mov     r13, rax
0x14000d747  mov     [rsp+0A8h+var_70], rax
0x14000d74c  test    rax, rax
0x14000d74f  jz      loc_14000D925
0x14000d755  mov     edx, 1; Revision
0x14000d75a  mov     rcx, rax; SecurityDescriptor
0x14000d75d  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000d763  mov     [rsp+0A8h+var_78], eax
0x14000d767  xor     r9d, r9d; DaclDefaulted
0x14000d76a  mov     r8, r12; Dacl
0x14000d76d  mov     dl, 1; DaclPresent
0x14000d76f  mov     rcx, r13; SecurityDescriptor
0x14000d772  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000d778  mov     r15d, eax
0x14000d77b  mov     [rsp+0A8h+var_78], eax
0x14000d77f  test    eax, eax
0x14000d781  jns     loc_14000D953
0x14000d787  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d78e  lea     rax, WPP_GLOBAL_Control
0x14000d795  cmp     rcx, rax
0x14000d798  jz      short loc_14000D7BE
0x14000d79a  test    byte ptr [rcx+1Ch], 2
0x14000d79e  jz      short loc_14000D7BE
0x14000d7a0  cmp     byte ptr [rcx+19h], 2
0x14000d7a4  jb      short loc_14000D7BE
0x14000d7a6  mov     edx, 0Fh
0x14000d7ab  mov     r9d, r15d
0x14000d7ae  lea     r8, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids
0x14000d7b5  mov     rcx, [rcx+10h]
0x14000d7b9  call    WPP_SF_d
0x14000d7be  lea     rcx, [rsp+0A8h+var_70]
0x14000d7c3  call    UHHeapFree
0x14000d7c8  mov     r13, [rsp+0A8h+var_70]
0x14000d7cd  jmp     loc_14000D953
0x14000d7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7d9  lea     rax, WPP_GLOBAL_Control
0x14000d7e0  cmp     rcx, rax
0x14000d7e3  jz      loc_14000D953
0x14000d7e9  test    byte ptr [rcx+1Ch], 2
0x14000d7ed  jz      loc_14000D953
0x14000d7f3  cmp     byte ptr [rcx+19h], 2
0x14000d7f7  jb      loc_14000D953
0x14000d7fd  mov     edx, 0Dh
0x14000d802  mov     r9d, r15d
0x14000d805  lea     r8, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids
0x14000d80c  mov     rcx, [rcx+10h]
0x14000d810  call    WPP_SF_d
0x14000d815  jmp     loc_14000D953
0x14000d81a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d821  lea     rax, WPP_GLOBAL_Control
0x14000d828  cmp     rcx, rax
0x14000d82b  jnz     loc_14000D90F
0x14000d831  mov     r15d, [rsp+0A8h+var_78]
0x14000d836  jmp     loc_14000D953
0x14000d83b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d842  lea     rax, WPP_GLOBAL_Control
0x14000d849  cmp     rcx, rax
0x14000d84c  jz      short loc_14000D831
0x14000d84e  test    byte ptr [rcx+1Ch], 2
0x14000d852  jz      short loc_14000D831
0x14000d854  cmp     byte ptr [rcx+19h], 2
0x14000d858  jb      short loc_14000D831
0x14000d85a  mov     edx, 0Bh
0x14000d85f  jmp     loc_14000D8FA
0x14000d864  lea     rax, WPP_GLOBAL_Control
0x14000d86b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d872  cmp     rcx, rax
0x14000d875  jz      loc_14000D953
0x14000d87b  test    byte ptr [rcx+1Ch], 2
0x14000d87f  jz      loc_14000D953
0x14000d885  cmp     byte ptr [rcx+19h], 2
0x14000d889  jb      loc_14000D953
0x14000d88f  mov     edx, 0Ah
0x14000d894  jmp     short loc_14000D89B
0x14000d896  mov     edx, 0Eh
0x14000d89b  lea     r8, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids
0x14000d8a2  mov     rcx, [rcx+10h]
0x14000d8a6  call    WPP_SF_
0x14000d8ab  jmp     loc_14000D953
0x14000d8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8b7  lea     rax, WPP_GLOBAL_Control
0x14000d8be  cmp     rcx, rax
0x14000d8c1  jz      loc_14000D68D
0x14000d8c7  test    byte ptr [rcx+1Ch], 2
0x14000d8cb  jz      loc_14000D68D
0x14000d8d1  cmp     byte ptr [rcx+19h], 2
0x14000d8d5  jb      loc_14000D68D
0x14000d8db  mov     edx, 11h
0x14000d8e0  lea     r8, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids
0x14000d8e7  mov     rcx, [rcx+10h]
0x14000d8eb  call    WPP_SF_
0x14000d8f0  jmp     loc_14000D68D
0x14000d8f5  mov     edx, 0Ch
0x14000d8fa  lea     r8, WPP_b346fd90c9c23c4ee3450cad4b06957a_Traceguids
0x14000d901  mov     rcx, [rcx+10h]
0x14000d905  call    WPP_SF_
0x14000d90a  jmp     loc_14000D831
0x14000d90f  test    byte ptr [rcx+1Ch], 2
0x14000d913  jz      loc_14000D831
0x14000d919  cmp     byte ptr [rcx+19h], 2
0x14000d91d  jb      loc_14000D831
0x14000d923  jmp     short loc_14000D8F5
0x14000d925  mov     r15d, 0C0000017h
0x14000d92b  mov     [rsp+0A8h+var_78], r15d
0x14000d930  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d937  lea     rax, WPP_GLOBAL_Control
0x14000d93e  cmp     rcx, rax
0x14000d941  jz      short loc_14000D953
0x14000d943  test    byte ptr [rcx+1Ch], 2
0x14000d947  jz      short loc_14000D953
0x14000d949  cmp     byte ptr [rcx+19h], 2
0x14000d94d  jnb     loc_14000D896
0x14000d953  test    r14, r14
0x14000d956  jnz     short loc_14000D970
0x14000d958  test    r13, r13
0x14000d95b  jz      short loc_14000D9AF
0x14000d95d  mov     rax, r13
0x14000d960  add     rsp, 70h
0x14000d964  pop     r15
0x14000d966  pop     r14
0x14000d968  pop     r13
0x14000d96a  pop     r12
0x14000d96c  pop     rdi
0x14000d96d  pop     rsi
0x14000d96e  pop     rbx
0x14000d96f  retn
0x14000d970  xor     edi, edi
0x14000d972  test    ebx, ebx
0x14000d974  jz      short loc_14000D999
0x14000d976  mov     rsi, [r14+rdi*8]
0x14000d97a  test    rsi, rsi
0x14000d97d  jz      short loc_14000D993
0x14000d97f  call    cs:__imp_GetProcessHeap
0x14000d985  mov     r8, rsi; lpMem
0x14000d988  xor     edx, edx; dwFlags
0x14000d98a  mov     rcx, rax; hHeap
0x14000d98d  call    cs:__imp_HeapFree
0x14000d993  inc     edi
0x14000d995  cmp     edi, ebx
0x14000d997  jb      short loc_14000D976
0x14000d999  call    cs:__imp_GetProcessHeap
0x14000d99f  mov     r8, r14; lpMem
0x14000d9a2  xor     edx, edx; dwFlags
0x14000d9a4  mov     rcx, rax; hHeap
0x14000d9a7  call    cs:__imp_HeapFree
0x14000d9ad  jmp     short loc_14000D958
0x14000d9af  test    r12, r12
0x14000d9b2  jz      short loc_14000D9BE
0x14000d9b4  lea     rcx, [rsp+0A8h+var_68]
0x14000d9b9  call    UHHeapFree
0x14000d9be  mov     ecx, r15d; Status
0x14000d9c1  call    cs:__imp_RtlNtStatusToDosError
0x14000d9c7  mov     ecx, eax; dwErrCode
0x14000d9c9  call    cs:__imp_SetLastError
0x14000d9cf  jmp     short loc_14000D95D
0x14009d200  push    rbx
0x14009d202  push    rbp
0x14009d203  push    rsi
0x14009d204  push    rdi
0x14009d205  sub     rsp, 38h
0x14009d209  mov     rbp, rdx
0x14009d20c  mov     rdi, [rbp+50h]
0x14009d210  test    rdi, rdi
0x14009d213  jz      short loc_14009D25A
0x14009d215  xor     ebx, ebx
0x14009d217  mov     [rbp+34h], ebx
0x14009d21a  mov     esi, [rbp+0B8h]
0x14009d220  test    esi, esi
0x14009d222  jz      short loc_14009D250
0x14009d224  mov     eax, ebx
0x14009d226  cmp     qword ptr [rdi+rbx*8], 0
0x14009d22b  jz      short loc_14009D247
0x14009d22d  mov     eax, ebx
0x14009d22f  mov     rcx, [rdi+rbx*8]
0x14009d233  mov     [rbp+0C0h], rcx
0x14009d23a  lea     rcx, [rbp+0C0h]
0x14009d241  call    UHHeapFree
0x14009d246  nop
0x14009d247  inc     ebx
0x14009d249  cmp     ebx, esi
0x14009d24b  jb      short loc_14009D224
0x14009d24d  mov     [rbp+34h], ebx
0x14009d250  lea     rcx, [rbp+50h]
0x14009d254  call    UHHeapFree
0x14009d259  nop
  ... truncated ...
```
