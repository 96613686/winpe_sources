# SampRemoveAnonymousAccess(void * *,ulong *,ulong,_SAMP_OBJECT_TYPE)

- ea: `0x180019100`
- end: `0x18001953b`
- name: `?SampRemoveAnonymousAccess@@YAJPEAPEAXPEAKKW4_SAMP_OBJECT_TYPE@@@Z`
- size: `1083`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017a60`

## callees

- `0x180019100`
- `0x180027e24`
- `0x180037284`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlAddAce` at `0x1800192a7`
- `ntdll!RtlAddAce` at `0x1800192a7`
- `ntdll!RtlGetAcesBufferSize` at `0x18001927c`
- `ntdll!RtlGetAcesBufferSize` at `0x18001927c`
- `ntdll!RtlSetSecurityObject` at `0x180019336`
- `ntdll!RtlSetSecurityObject` at `0x180019336`
- `ntdll!RtlCopySecurityDescriptor` at `0x180019214`
- `ntdll!RtlCopySecurityDescriptor` at `0x180019214`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180019359`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180019359`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180019142`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180019142`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180019301`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180019301`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800192ca`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800192ca`
- `ntdll!RtlCreateAcl` at `0x180019263`
- `ntdll!RtlCreateAcl` at `0x180019263`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800192e4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800192e4`
- `ntdll!RtlFreeHeap` at `0x18001945d`
- `ntdll!RtlFreeHeap` at `0x18001945d`
- `ntdll!RtlLengthSid` at `0x180019234`
- `ntdll!RtlLengthSid` at `0x180019234`
- `ntdll!RtlEqualSid` at `0x1800193b3`
- `ntdll!RtlEqualSid` at `0x1800193c8`
- `ntdll!RtlEqualSid` at `0x1800193b3`
- `ntdll!RtlEqualSid` at `0x1800193c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019368`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019368`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001938d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800194ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001938d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800194ec`

## pseudocode

```c
__int64 __fastcall SampRemoveAnonymousAccess(HLOCAL *a1, ULONG *a2, int a3, int a4)
{
  HLOCAL v5; // rcx
  NTSTATUS DaclSecurityDescriptor; // eax
  unsigned int v7; // ebx
  PUNICODE_STRING v8; // rcx
  unsigned int AceCount; // esi
  PACL v11; // rbx
  ACCESS_MASK v12; // r13d
  unsigned int v13; // edi
  NTSTATUS Acl; // r15d
  HLOCAL v15; // rcx
  int AclSize; // edi
  ULONG v17; // edi
  struct _ACL *v18; // rax
  struct _ACL *v19; // rbx
  ULONG v20; // esi
  HLOCAL v21; // rax
  HLOCAL v22; // rdi
  __int64 v23; // rdx
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+31h] [rbp-18h] BYREF
  ULONG AceListLength; // [rsp+34h] [rbp-15h] BYREF
  PSECURITY_DESCRIPTOR pDestinationSecurityDescriptor; // [rsp+38h] [rbp-11h] BYREF
  PACL Dacl; // [rsp+40h] [rbp-9h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v30; // [rsp+68h] [rbp+1Fh]

  Dacl = 0;
  v5 = *a1;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v5, &DaclPresent, &Dacl, DaclDefaulted);
  v7 = DaclSecurityDescriptor;
  if ( DaclSecurityDescriptor >= 0 )
  {
    if ( DaclPresent && Dacl )
    {
      AceCount = Dacl->AceCount;
      if ( Dacl->AceCount )
      {
        v11 = Dacl + 1;
        v12 = 0;
        v13 = 0;
        do
        {
          if ( (v11->Sbz1 & 8) == 0
            && !v11->AclRevision
            && (RtlEqualSid(SampWorldSid, &v11[1]) || RtlEqualSid(SampAnonymousSid, &v11[1])) )
          {
            v12 |= a3 & *(_DWORD *)&v11->AceCount;
            *(_DWORD *)&v11->AceCount &= ~a3;
          }
          ++v13;
          v11 = (PACL)((char *)v11 + v11->AclSize);
        }
        while ( v13 < AceCount );
        Acl = 0;
        if ( v12 )
        {
          v15 = *a1;
          pDestinationSecurityDescriptor = 0;
          AceListLength = 0;
          memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
          v30 = 0;
          Acl = RtlCopySecurityDescriptor(v15, &pDestinationSecurityDescriptor);
          if ( Acl < 0 )
          {
            v19 = 0;
          }
          else
          {
            AclSize = Dacl->AclSize;
            v17 = RtlLengthSid(SampAuthenticatedUsersSid) + AclSize + 8;
            v18 = (struct _ACL *)LocalAlloc(0x40u, v17);
            v19 = v18;
            if ( v18 )
            {
              Acl = RtlCreateAcl(v18, v17, 2u);
              if ( Acl >= 0 )
              {
                Acl = RtlGetAcesBufferSize(Dacl, &AceListLength);
                if ( Acl >= 0 )
                {
                  Acl = RtlAddAce(v19, 2u, 0, &Dacl[1], AceListLength);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlAddAccessAllowedAce(v19, 2u, v12, SampAuthenticatedUsersSid);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                      if ( Acl >= 0 )
                      {
                        Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v19, 0);
                        if ( Acl >= 0 )
                        {
                          Acl = RtlSetSecurityObject(
                                  4u,
                                  SecurityDescriptor,
                                  &pDestinationSecurityDescriptor,
                                  (PGENERIC_MAPPING)(&SampObjectInformation + 11 * a4),
                                  0);
                          if ( Acl >= 0 )
                          {
                            if ( *((__int16 *)pDestinationSecurityDescriptor + 1) >= 0 )
                            {
                              Acl = -1073741811;
                              if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control[3].Buffer,
                                  26,
                                  WPP_5505de3e48bd33375e96ca021b170945_Traceguids);
                              }
                            }
                            else
                            {
                              v20 = RtlLengthSecurityDescriptor(pDestinationSecurityDescriptor);
                              v21 = LocalAlloc(0x40u, v20);
                              v22 = v21;
                              if ( v21 )
                              {
                                memcpy_0(v21, pDestinationSecurityDescriptor, v20);
                                LocalFree(*a1);
                                *a1 = v22;
                                *a2 = v20;
                              }
                              else
                              {
                                Acl = -1073741670;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            else
            {
              Acl = -1073741670;
            }
          }
          if ( pDestinationSecurityDescriptor )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pDestinationSecurityDescriptor);
          if ( v19 )
            LocalFree(v19);
        }
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            27,
            WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
            (unsigned int)Acl,
            Acl);
        return (unsigned int)Acl;
      }
      v8 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v23 = 25;
LABEL_46:
        WPP_SF_Dd(v8[3].Buffer, v23, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, 0, 0);
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v23 = 24;
        goto LABEL_46;
      }
    }
    return 0;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      23,
      WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
      (unsigned int)DaclSecurityDescriptor,
      DaclSecurityDescriptor);
  return v7;
}

```

## disassembly

```asm
0x180019100  mov     [rsp-8+arg_18], r9d
0x180019105  mov     [rsp-8+arg_10], r8d
0x18001910a  mov     [rsp-8+arg_8], rdx
0x18001910f  push    rbp
0x180019110  push    rbx
0x180019111  push    r12
0x180019113  push    r14
0x180019115  lea     rbp, [rsp-3Fh]
0x18001911a  sub     rsp, 88h
0x180019121  xor     r14d, r14d
0x180019124  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x180019128  mov     r12, rcx
0x18001912b  mov     [rbp+57h+Dacl], r14
0x18001912f  mov     rcx, [rcx]; SecurityDescriptor
0x180019132  lea     r8, [rbp+57h+Dacl]; Dacl
0x180019136  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x18001913a  mov     [rbp+57h+DaclPresent], r14b
0x18001913e  mov     [rbp+57h+DaclDefaulted], r14b
0x180019142  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180019148  mov     ebx, eax
0x18001914a  test    eax, eax
0x18001914c  js      loc_180019465
0x180019152  mov     [rsp+0A0h+arg_0], rsi
0x18001915a  cmp     [rbp+57h+DaclPresent], r14b
0x18001915e  jnz     short loc_18001918C
0x180019160  mov     rcx, cs:WPP_GLOBAL_Control
0x180019167  test    dword ptr [rcx+44h], 20000h
0x18001916e  jnz     loc_180019519
0x180019174  xor     eax, eax
0x180019176  mov     rsi, [rsp+0A0h+arg_0]
0x18001917e  add     rsp, 88h
0x180019185  pop     r14
0x180019187  pop     r12
0x180019189  pop     rbx
0x18001918a  pop     rbp
0x18001918b  retn
0x18001918c  mov     rbx, [rbp+57h+Dacl]
0x180019190  test    rbx, rbx
0x180019193  jz      short loc_180019160
0x180019195  movzx   esi, word ptr [rbx+4]
0x180019199  test    esi, esi
0x18001919b  jz      loc_18001942C
0x1800191a1  mov     [rsp+0A0h+var_20], rdi
0x1800191a9  add     rbx, 8
0x1800191ad  mov     [rsp+0A0h+var_28], r13
0x1800191b2  mov     r13d, r14d
0x1800191b5  mov     [rsp+0A0h+var_30], r15
0x1800191ba  mov     r15d, r14d
0x1800191bd  mov     edi, r14d
0x1800191c0  test    esi, esi
0x1800191c2  jz      loc_1800193FE
0x1800191c8  mov     r15d, [rbp+57h+arg_10]
0x1800191cc  nop     dword ptr [rax+00h]
0x1800191d0  test    byte ptr [rbx+1], 8
0x1800191d4  jz      loc_18001939F
0x1800191da  movzx   eax, word ptr [rbx+2]
0x1800191de  inc     edi
0x1800191e0  add     rbx, rax
0x1800191e3  cmp     edi, esi
0x1800191e5  jb      short loc_1800191D0
0x1800191e7  mov     r15d, r14d
0x1800191ea  test    r13d, r13d
0x1800191ed  jz      loc_1800193FE
0x1800191f3  mov     rcx, [r12]; pSourceSecurityDescriptor
0x1800191f7  lea     rdx, [rbp+57h+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x1800191fb  xorps   xmm0, xmm0
0x1800191fe  mov     [rbp+57h+pDestinationSecurityDescriptor], r14
0x180019202  xor     eax, eax
0x180019204  mov     [rbp+57h+var_6C], r14d
0x180019208  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18001920c  mov     [rbp+57h+var_38], rax
0x180019210  movups  [rbp+57h+var_48], xmm0
0x180019214  call    cs:__imp_RtlCopySecurityDescriptor
0x18001921a  mov     r15d, eax
0x18001921d  test    eax, eax
0x18001921f  js      loc_1800193EC
0x180019225  mov     rax, [rbp+57h+Dacl]
0x180019229  mov     rcx, cs:SampAuthenticatedUsersSid; Sid
0x180019230  movzx   edi, word ptr [rax+2]
0x180019234  call    cs:__imp_RtlLengthSid
0x18001923a  add     edi, 8
0x18001923d  mov     ecx, 40h ; '@'; uFlags
0x180019242  add     edi, eax
0x180019244  mov     edx, edi; uBytes
0x180019246  call    cs:__imp_LocalAlloc
0x18001924c  mov     rbx, rax
0x18001924f  test    rax, rax
0x180019252  jz      loc_180019498
0x180019258  mov     r8d, 2; AclRevision
0x18001925e  mov     edx, edi; AclSize
0x180019260  mov     rcx, rax; Acl
0x180019263  call    cs:__imp_RtlCreateAcl
0x180019269  mov     r15d, eax
0x18001926c  test    eax, eax
0x18001926e  js      loc_1800193EF
0x180019274  mov     rcx, [rbp+57h+Dacl]
0x180019278  lea     rdx, [rbp+57h+var_6C]
0x18001927c  call    cs:__imp_RtlGetAcesBufferSize
0x180019282  mov     r15d, eax
0x180019285  test    eax, eax
0x180019287  js      loc_1800193EF
0x18001928d  mov     r9, [rbp+57h+Dacl]
0x180019291  xor     r8d, r8d; StartingAceIndex
0x180019294  mov     eax, [rbp+57h+var_6C]
0x180019297  add     r9, 8; AceList
0x18001929b  mov     edx, 2; AceRevision
0x1800192a0  mov     [rsp+0A0h+AceListLength], eax; AceListLength
0x1800192a4  mov     rcx, rbx; Acl
0x1800192a7  call    cs:__imp_RtlAddAce
0x1800192ad  mov     r15d, eax
0x1800192b0  test    eax, eax
0x1800192b2  js      loc_1800193EF
0x1800192b8  mov     r9, cs:SampAuthenticatedUsersSid; Sid
0x1800192bf  mov     r8d, r13d; AccessMask
0x1800192c2  mov     edx, 2; Revision
0x1800192c7  mov     rcx, rbx; Acl
0x1800192ca  call    cs:__imp_RtlAddAccessAllowedAce
0x1800192d0  mov     r15d, eax
0x1800192d3  test    eax, eax
0x1800192d5  js      loc_1800193EF
0x1800192db  mov     edx, 1; Revision
0x1800192e0  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800192e4  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800192ea  mov     r15d, eax
0x1800192ed  test    eax, eax
0x1800192ef  js      loc_1800193EF
0x1800192f5  xor     r9d, r9d; DaclDefaulted
0x1800192f8  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800192fc  mov     r8, rbx; Dacl
0x1800192ff  mov     dl, 1; DaclPresent
0x180019301  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180019307  mov     r15d, eax
0x18001930a  test    eax, eax
0x18001930c  js      loc_1800193EF
0x180019312  movsxd  rax, [rbp+57h+arg_18]
0x180019316  lea     r8, [rbp+57h+pDestinationSecurityDescriptor]; ObjectsSecurityDescriptor
0x18001931a  imul    r9, rax, 58h ; 'X'
0x18001931e  lea     rax, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x180019325  mov     qword ptr [rsp+0A0h+AceListLength], r14; Token
0x18001932a  add     r9, rax; GenericMapping
0x18001932d  lea     rdx, [rbp+57h+SecurityDescriptor]; ModificationDescriptor
0x180019331  mov     ecx, 4; SecurityInformation
0x180019336  call    cs:__imp_RtlSetSecurityObject
0x18001933c  mov     r15d, eax
0x18001933f  test    eax, eax
0x180019341  js      loc_1800193EF
0x180019347  mov     rax, [rbp+57h+pDestinationSecurityDescriptor]
0x18001934b  cmp     [rax+2], r14w
0x180019350  jge     loc_1800194A3
0x180019356  mov     rcx, rax; SecurityDescriptor
0x180019359  call    cs:__imp_RtlLengthSecurityDescriptor
0x18001935f  mov     edx, eax; uBytes
0x180019361  mov     ecx, 40h ; '@'; uFlags
0x180019366  mov     esi, eax
0x180019368  call    cs:__imp_LocalAlloc
0x18001936e  mov     rdi, rax
0x180019371  test    rax, rax
0x180019374  jz      loc_1800194DE
0x18001937a  mov     rdx, [rbp+57h+pDestinationSecurityDescriptor]; Src
0x18001937e  mov     r8d, esi; Size
0x180019381  mov     rcx, rax; void *
0x180019384  call    memcpy_0
0x180019389  mov     rcx, [r12]; hMem
0x18001938d  call    cs:__imp_LocalFree
0x180019393  mov     rax, [rbp+57h+arg_8]
0x180019397  mov     [r12], rdi
0x18001939b  mov     [rax], esi
0x18001939d  jmp     short loc_1800193EF
0x18001939f  cmp     [rbx], r14b
0x1800193a2  jnz     loc_1800191DA
0x1800193a8  mov     rcx, cs:SampWorldSid; Sid1
0x1800193af  lea     rdx, [rbx+8]; Sid2
0x1800193b3  call    cs:__imp_RtlEqualSid
0x1800193b9  test    al, al
0x1800193bb  jnz     short loc_1800193D6
0x1800193bd  mov     rcx, cs:SampAnonymousSid; Sid1
0x1800193c4  lea     rdx, [rbx+8]; Sid2
0x1800193c8  call    cs:__imp_RtlEqualSid
0x1800193ce  test    al, al
0x1800193d0  jz      loc_1800191DA
0x1800193d6  mov     eax, [rbx+4]
0x1800193d9  and     eax, r15d
0x1800193dc  or      r13d, eax
0x1800193df  mov     eax, r15d
0x1800193e2  not     eax
0x1800193e4  and     [rbx+4], eax
0x1800193e7  jmp     loc_1800191DA
0x1800193ec  mov     rbx, r14
0x1800193ef  cmp     [rbp+57h+pDestinationSecurityDescriptor], r14
0x1800193f3  jnz     short loc_18001944A
0x1800193f5  test    rbx, rbx
0x1800193f8  jnz     loc_1800194E9
0x1800193fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180019405  mov     r13, [rsp+0A0h+var_28]
0x18001940a  mov     rdi, [rsp+0A0h+var_20]
0x180019412  test    dword ptr [rcx+44h], 20000h
0x180019419  jnz     loc_1800194F7
0x18001941f  mov     eax, r15d
0x180019422  mov     r15, [rsp+0A0h+var_30]
0x180019427  jmp     loc_180019176
0x18001942c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019433  test    dword ptr [rcx+44h], 20000h
0x18001943a  jz      loc_180019174
0x180019440  mov     edx, 19h
0x180019445  jmp     loc_18001951E
0x18001944a  mov     rcx, gs:60h
0x180019453  xor     edx, edx; Flags
0x180019455  mov     r8, [rbp+57h+pDestinationSecurityDescriptor]; P
0x180019459  mov     rcx, [rcx+30h]; HeapHandle
0x18001945d  call    cs:__imp_RtlFreeHeap
0x180019463  jmp     short loc_1800193F5
0x180019465  mov     rcx, cs:WPP_GLOBAL_Control
0x18001946c  test    dword ptr [rcx+44h], 20000h
0x180019473  jz      short loc_180019491
0x180019475  mov     rcx, [rcx+38h]
0x180019479  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x180019480  mov     edx, 17h
0x180019485  mov     [rsp+0A0h+AceListLength], ebx
0x180019489  mov     r9d, ebx
0x18001948c  call    WPP_SF_Dd
0x180019491  mov     eax, ebx
0x180019493  jmp     loc_18001917E
0x180019498  mov     r15d, 0C000009Ah
0x18001949e  jmp     loc_1800193EF
0x1800194a3  mov     r15d, 0C000000Dh
0x1800194a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194b0  test    byte ptr [rcx+44h], 20h
0x1800194b4  jz      loc_1800193EF
0x1800194ba  cmp     byte ptr [rcx+41h], 2
0x1800194be  jb      loc_1800193EF
0x1800194c4  mov     rcx, [rcx+38h]
0x1800194c8  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x1800194cf  mov     edx, 1Ah
0x1800194d4  call    WPP_SF_
0x1800194d9  jmp     loc_1800193EF
0x1800194de  mov     r15d, 0C000009Ah
0x1800194e4  jmp     loc_1800193EF
0x1800194e9  mov     rcx, rbx; hMem
0x1800194ec  call    cs:__imp_LocalFree
0x1800194f2  jmp     loc_1800193FE
0x1800194f7  mov     rcx, [rcx+38h]
0x1800194fb  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x180019502  mov     edx, 1Bh
0x180019507  mov     [rsp+0A0h+AceListLength], r15d
0x18001950c  mov     r9d, r15d
0x18001950f  call    WPP_SF_Dd
0x180019514  jmp     loc_18001941F
0x180019519  mov     edx, 18h
0x18001951e  mov     rcx, [rcx+38h]
0x180019522  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x180019529  xor     r9d, r9d
0x18001952c  mov     [rsp+0A0h+AceListLength], r14d
0x180019531  call    WPP_SF_Dd
0x180019536  jmp     loc_180019174
```
