# Smb2CheckShareAccess

- ea: `0x14007c2b0`
- end: `0x14007c6a3`
- name: `Smb2CheckShareAccess`
- size: `1011`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140066dc4`
- `0x14007a89c`

## callees

- `0x140004dcc`
- `0x140015960`
- `0x1400281c8`
- `0x140038490`
- `0x140038980`
- `0x14007c2b0`
- `0x1400917ac`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007c3a1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007c3a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007c41f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007c41f`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140098255`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140098255`
- `ntoskrnl!RtlMapGenericMask` at `0x14007c35f`
- `ntoskrnl!RtlMapGenericMask` at `0x14007c35f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007c53c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007c53c`
- `ntoskrnl!SeFreePrivileges` at `0x14007c65e`
- `ntoskrnl!SeFreePrivileges` at `0x14007c65e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007c5bb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007c5bb`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c4b1`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c5d2`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009823a`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c4b1`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c5d2`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009823a`
- `srvnet!SrvLibAuditSuccessEnabled` at `0x14007c3f6`
- `srvnet!SrvLibAuditSuccessEnabled` at `0x14007c3f6`
- `srvnet!SrvLibAuditShareAccess` at `0x140098223`
- `srvnet!SrvLibAuditShareAccess` at `0x140098223`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x14007c635`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x14007c635`
- `srvnet!SrvLibSeAccessCheck` at `0x14007c593`
- `srvnet!SrvLibSeAccessCheck` at `0x14007c593`
- `ksecdd!FreeContextBuffer` at `0x140098338`
- `ksecdd!FreeContextBuffer` at `0x140098338`

## pseudocode

```c
__int64 __fastcall Smb2CheckShareAccess(__int64 a1, void *a2, DWORD a3, _DWORD *a4, int *a5)
{
  __int64 v6; // r15
  _QWORD *v8; // rsi
  __int64 v9; // rbx
  char v10; // r13
  __int64 v11; // rbx
  __int64 v12; // r14
  char v13; // r15
  PSECURITY_DESCRIPTOR *v14; // r14
  __int64 result; // rax
  int v16; // ecx
  int v17; // eax
  _DWORD *v18; // r9
  __int64 v19; // rdx
  int MaximalAccessRightsForUser; // r15d
  __int64 *v21; // rax
  __int64 v22; // r13
  __int64 v23; // rdi
  __int64 v24; // r11
  __int16 v25; // r14
  __int64 v26; // r15
  __int16 v27; // si
  UCHAR v28; // al
  __int64 v29; // r11
  int v30; // edx
  int v31; // [rsp+38h] [rbp-E8h]
  int v32; // [rsp+A0h] [rbp-80h] BYREF
  char v33; // [rsp+A4h] [rbp-7Ch]
  int v34; // [rsp+A8h] [rbp-78h] BYREF
  DWORD AccessMask; // [rsp+ACh] [rbp-74h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-70h]
  __int64 v37; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-60h]
  PPRIVILEGE_SET Privileges; // [rsp+C8h] [rbp-58h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+D0h] [rbp-50h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+E0h] [rbp-40h] BYREF
  _BYTE v42[128]; // [rsp+100h] [rbp-20h] BYREF

  pvContextBuffer[1] = a2;
  v36 = a1;
  v6 = a1;
  AccessMask = a3;
  v32 = 0;
  v34 = 0;
  Privileges = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(v42, 0, sizeof(v42));
  v8 = *(_QWORD **)(v6 + 560);
  pvContextBuffer[0] = 0;
  v37 = 0;
  v38 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a3 )
    return 3221225506LL;
  v9 = v8[7];
  v10 = 0;
  v33 = 0;
  v11 = *(_QWORD *)(v9 + 96);
  RtlMapGenericMask(&AccessMask, &Smb2FileAccessMapping);
  if ( (AccessMask & 0x1000000) != 0 )
  {
    v10 = 1;
    v33 = 1;
    AccessMask &= ~0x1000000u;
  }
  if ( (*(_DWORD *)(v11 + 288) & 0x100) != 0 && (a3 & 0x116) == 0 && (*a4 & 1) == 0 )
    *a4 |= 1u;
  if ( (*(_DWORD *)(v11 + 288) & 0x200) != 0 )
    *a4 |= 4u;
  ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)v11 + 96LL), 1u);
  v12 = v8[7];
  if ( *(_DWORD *)(v11 + 272) == *(_DWORD *)(v12 + 140) )
  {
LABEL_10:
    v13 = 0;
    if ( (a3 | *(_DWORD *)(v8[7] + 136LL)) != *(_DWORD *)(v8[7] + 136LL) )
      goto LABEL_32;
    v34 = *(_DWORD *)(v8[7] + 136LL);
    v14 = (PSECURITY_DESCRIPTOR *)(v11 + 264);
    while ( 1 )
    {
      if ( v32 >= 0 && !(unsigned __int8)SrvLibAuditSuccessEnabled(128) )
        goto LABEL_14;
      if ( v13 || !*v14 )
        break;
LABEL_32:
      v14 = (PSECURITY_DESCRIPTOR *)(v11 + 264);
      v32 = -1073741790;
      if ( *(_QWORD *)(v11 + 264) )
      {
        v32 = Smb2ImpersonateSecurityContext(v8[6]);
        if ( v32 < 0 )
          goto LABEL_14;
        SeCaptureSubjectContext(&SubjectContext);
        LOBYTE(v31) = 1;
        if ( (unsigned __int8)SrvLibSeAccessCheck(
                                *v14,
                                &SubjectContext,
                                0,
                                AccessMask,
                                0,
                                &Privileges,
                                &Smb2FileAccessMapping,
                                v31,
                                &v34,
                                v42,
                                &v32) )
          v32 = 0;
        if ( Privileges )
          SeFreePrivileges(Privileges);
        SeReleaseSubjectContext(&SubjectContext);
        PsAssignImpersonationToken(KeGetCurrentThread(), 0);
        v13 = 1;
      }
      else
      {
        v34 = 2032127;
        v32 = 0;
      }
    }
    if ( (int)Smb2ImpersonateSecurityContext(v8[6]) < 0 )
    {
LABEL_14:
      v6 = v36;
      goto LABEL_15;
    }
    v6 = v36;
    SrvLibAuditShareAccess(v11 + 104, *(_QWORD *)(v36 + 96) + 216LL, v11 + 120);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
LABEL_15:
    if ( v32 >= 0 )
      goto LABEL_16;
    goto LABEL_28;
  }
  v17 = Smb2ImpersonateSecurityContext(v8[6]);
  if ( v17 < 0 )
  {
    v32 = v17;
    v14 = (PSECURITY_DESCRIPTOR *)(v11 + 264);
  }
  else
  {
    v18 = (_DWORD *)(v12 + 136);
    v14 = (PSECURITY_DESCRIPTOR *)(v11 + 264);
    v19 = *(_QWORD *)(v11 + 264);
    if ( v19 )
    {
      MaximalAccessRightsForUser = SrvLibRetrieveMaximalAccessRightsForUser(0, v19, &Smb2FileAccessMapping, v18, 1);
    }
    else
    {
      *v18 = 18809343;
      MaximalAccessRightsForUser = 0;
    }
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    v32 = MaximalAccessRightsForUser;
    if ( MaximalAccessRightsForUser >= 0 )
    {
      *(_DWORD *)(v8[7] + 140LL) = *(_DWORD *)(v11 + 272);
      goto LABEL_10;
    }
    v6 = v36;
  }
LABEL_28:
  Smb2GetUserName(v8, pvContextBuffer, &v37);
  if ( Microsoft_Windows_SMBServerEnableBits < 0 )
  {
    v21 = (__int64 *)v8[4];
    if ( v21 )
      v22 = *v21;
    else
      LOBYTE(v22) = 0;
    v23 = (__int64)*v14;
    RtlLengthSecurityDescriptor(*v14);
    v24 = *(_QWORD *)(v6 + 96);
    v25 = (unsigned __int16)v37 >> 1;
    v26 = v24 + 216;
    v27 = *(_WORD *)(v24 + 360) >> 1;
    v28 = SOCKADDR_SIZE(*(_WORD *)(v24 + 216));
    McTemplateK0hzr0hzr2qbr4hzr6hzr8ddqbr12ddi_EtwWriteTransfer(
      *(_WORD *)(v11 + 120) >> 1,
      v30,
      v36 + 584,
      *(_WORD *)(v11 + 104) >> 1,
      *(_QWORD *)(v11 + 112),
      *(_WORD *)(v11 + 120) >> 1,
      *(_QWORD *)(v11 + 128),
      v28,
      v26,
      v25,
      v38,
      v27,
      *(_QWORD *)(v29 + 368),
      AccessMask,
      v34,
      v30,
      v23,
      v32,
      v32,
      v22);
    v10 = v33;
  }
  if ( pvContextBuffer[0] )
    FreeContextBuffer(pvContextBuffer[0]);
LABEL_16:
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v11 + 96LL));
  result = (unsigned int)v32;
  if ( v32 >= 0 && a5 )
  {
    v16 = v34;
    if ( v10 )
      v16 = v34 | 0x1000000;
    *a5 = v16;
  }
  return result;
}

```

## disassembly

```asm
0x14007c2b0  push    rbp
0x14007c2b2  push    rbx
0x14007c2b3  push    rsi
0x14007c2b4  push    rdi
0x14007c2b5  push    r12
0x14007c2b7  push    r14
0x14007c2b9  push    r15
0x14007c2bb  lea     rbp, [rsp-80h]
0x14007c2c0  sub     rsp, 1A0h
0x14007c2c7  mov     rax, cs:__security_cookie
0x14007c2ce  xor     rax, rsp
0x14007c2d1  mov     [rbp+0B0h+var_50], rax
0x14007c2d5  mov     r12, [rbp+0B0h+arg_20]
0x14007c2dc  xor     ebx, ebx
0x14007c2de  xorps   xmm0, xmm0
0x14007c2e1  mov     [rbp+0B0h+var_F8], rdx
0x14007c2e5  mov     edi, r8d
0x14007c2e8  mov     [rbp+0B0h+var_120], rcx
0x14007c2ec  mov     r15, rcx
0x14007c2ef  mov     [rbp+0B0h+AccessMask], r8d
0x14007c2f3  xor     edx, edx; Val
0x14007c2f5  mov     [rbp+0B0h+var_130], ebx
0x14007c2f8  mov     r8d, 80h; Size
0x14007c2fe  mov     [rbp+0B0h+var_128], ebx
0x14007c301  lea     rcx, [rbp+0B0h+var_D0]; void *
0x14007c305  mov     [rbp+0B0h+Privileges], rbx
0x14007c309  movups  xmmword ptr [rbp+0B0h+SubjectContext.ClientToken], xmm0
0x14007c30d  mov     r14, r9
0x14007c310  movups  xmmword ptr [rbp+0B0h+SubjectContext.PrimaryToken], xmm0
0x14007c314  call    memset
0x14007c319  mov     rsi, [r15+230h]
0x14007c320  mov     [rbp+0B0h+pvContextBuffer], rbx
0x14007c324  mov     [rbp+0B0h+var_118], rbx
0x14007c328  mov     [rbp+0B0h+var_110], rbx
0x14007c32c  test    r12, r12
0x14007c32f  jz      short loc_14007C335
0x14007c331  mov     [r12], ebx
0x14007c335  test    edi, edi
0x14007c337  jz      loc_14007C46E
0x14007c33d  mov     rbx, [rsi+38h]
0x14007c341  lea     rdx, Smb2FileAccessMapping; GenericMapping
0x14007c348  mov     [rsp+1D0h+var_38], r13
0x14007c350  lea     rcx, [rbp+0B0h+AccessMask]; AccessMask
0x14007c354  xor     r13b, r13b
0x14007c357  mov     [rbp+0B0h+var_12C], r13b
0x14007c35b  mov     rbx, [rbx+60h]
0x14007c35f  call    cs:__imp_RtlMapGenericMask
0x14007c366  nop     dword ptr [rax+rax+00h]
0x14007c36b  mov     eax, [rbp+0B0h+AccessMask]
0x14007c36e  bt      eax, 18h
0x14007c372  jb      loc_14007C5E6
0x14007c378  test    dword ptr [rbx+120h], 100h
0x14007c382  jnz     loc_14007C5F9
0x14007c388  test    dword ptr [rbx+120h], 200h
0x14007c392  jnz     loc_14007C61E
0x14007c398  mov     rcx, [rbx]
0x14007c39b  mov     dl, 1; Wait
0x14007c39d  add     rcx, 60h ; '`'; Resource
0x14007c3a1  call    cs:__imp_ExAcquireResourceSharedLite
0x14007c3a8  nop     dword ptr [rax+rax+00h]
0x14007c3ad  mov     r14, [rsi+38h]
0x14007c3b1  mov     eax, [r14+8Ch]
0x14007c3b8  cmp     [rbx+110h], eax
0x14007c3be  jnz     loc_14007C475
0x14007c3c4  mov     rax, [rsi+38h]
0x14007c3c8  xor     r15b, r15b
0x14007c3cb  mov     ecx, [rax+88h]
0x14007c3d1  mov     eax, ecx
0x14007c3d3  or      eax, edi
0x14007c3d5  cmp     eax, ecx
0x14007c3d7  jnz     loc_14007C50C
0x14007c3dd  mov     [rbp+0B0h+var_128], ecx
0x14007c3e0  lea     r14, [rbx+108h]
0x14007c3e7  cmp     [rbp+0B0h+var_130], 0
0x14007c3eb  jl      loc_14007C682
0x14007c3f1  mov     ecx, 80h
0x14007c3f6  call    cs:__imp_SrvLibAuditSuccessEnabled
0x14007c3fd  nop     dword ptr [rax+rax+00h]
0x14007c402  test    al, al
0x14007c404  jnz     loc_14007C682
0x14007c40a  mov     r15, [rbp+0B0h+var_120]
0x14007c40e  cmp     [rbp+0B0h+var_130], 0
0x14007c412  jl      loc_14007C4CE
0x14007c418  mov     rcx, [rbx]
0x14007c41b  add     rcx, 60h ; '`'; Resource
0x14007c41f  call    cs:__imp_ExReleaseResourceLite
0x14007c426  nop     dword ptr [rax+rax+00h]
0x14007c42b  mov     eax, [rbp+0B0h+var_130]
0x14007c42e  test    eax, eax
0x14007c430  js      short loc_14007C447
0x14007c432  test    r12, r12
0x14007c435  jz      short loc_14007C447
0x14007c437  mov     ecx, [rbp+0B0h+var_128]
0x14007c43a  test    r13b, r13b
0x14007c43d  jnz     loc_14007C69A
0x14007c443  mov     [r12], ecx
0x14007c447  mov     r13, [rsp+1D0h+var_38]
0x14007c44f  mov     rcx, [rbp+0B0h+var_50]
0x14007c453  xor     rcx, rsp; StackCookie
0x14007c456  call    __security_check_cookie
0x14007c45b  add     rsp, 1A0h
0x14007c462  pop     r15
0x14007c464  pop     r14
0x14007c466  pop     r12
0x14007c468  pop     rdi
0x14007c469  pop     rsi
0x14007c46a  pop     rbx
0x14007c46b  pop     rbp
0x14007c46c  retn
0x14007c46e  mov     eax, 0C0000022h
0x14007c473  jmp     short loc_14007C44F
0x14007c475  mov     rcx, [rsi+30h]
0x14007c479  call    Smb2ImpersonateSecurityContext
0x14007c47e  test    eax, eax
0x14007c480  js      short loc_14007C500
0x14007c482  lea     r9, [r14+88h]
0x14007c489  lea     r14, [rbx+108h]
0x14007c490  mov     rdx, [r14]
0x14007c493  test    rdx, rdx
0x14007c496  jnz     loc_14007C627
0x14007c49c  mov     dword ptr [r9], 11F01FFh
0x14007c4a3  xor     r15d, r15d
0x14007c4a6  mov     rcx, gs:188h; Thread
0x14007c4af  xor     edx, edx; Token
0x14007c4b1  call    cs:__imp_PsAssignImpersonationToken
0x14007c4b8  nop     dword ptr [rax+rax+00h]
0x14007c4bd  mov     [rbp+0B0h+var_130], r15d
0x14007c4c1  test    r15d, r15d
0x14007c4c4  jns     loc_14007C649
0x14007c4ca  mov     r15, [rbp+0B0h+var_120]
0x14007c4ce  lea     r8, [rbp+0B0h+var_118]
0x14007c4d2  mov     rcx, rsi
0x14007c4d5  lea     rdx, [rbp+0B0h+pvContextBuffer]
0x14007c4d9  call    Smb2GetUserName
0x14007c4de  cmp     cs:Microsoft_Windows_SMBServerEnableBits, 0
0x14007c4e5  jge     loc_14009832B
0x14007c4eb  mov     rax, [rsi+20h]
0x14007c4ef  test    rax, rax
0x14007c4f2  jz      loc_14009824C
0x14007c4f8  mov     r13, [rax]
0x14007c4fb  jmp     loc_14009824F
0x14007c500  mov     [rbp+0B0h+var_130], eax
0x14007c503  lea     r14, [rbx+108h]
0x14007c50a  jmp     short loc_14007C4CE
0x14007c50c  lea     r14, [rbx+108h]
0x14007c513  mov     [rbp+0B0h+var_130], 0C0000022h
0x14007c51a  cmp     qword ptr [r14], 0
0x14007c51e  jz      loc_14007C66F
0x14007c524  mov     rcx, [rsi+30h]
0x14007c528  call    Smb2ImpersonateSecurityContext
0x14007c52d  mov     [rbp+0B0h+var_130], eax
0x14007c530  test    eax, eax
0x14007c532  js      loc_14007C40A
0x14007c538  lea     rcx, [rbp+0B0h+SubjectContext]; SubjectContext
0x14007c53c  call    cs:__imp_SeCaptureSubjectContext
0x14007c543  nop     dword ptr [rax+rax+00h]
0x14007c548  mov     r9d, [rbp+0B0h+AccessMask]
0x14007c54c  lea     rax, [rbp+0B0h+var_130]
0x14007c550  mov     rcx, [r14]
0x14007c553  lea     rdx, [rbp+0B0h+SubjectContext]
0x14007c557  mov     [rsp+1D0h+var_180], rax
0x14007c55c  xor     r8d, r8d
0x14007c55f  lea     rax, [rbp+0B0h+var_D0]
0x14007c563  mov     [rsp+1D0h+var_188], rax
0x14007c568  lea     rax, [rbp+0B0h+var_128]
0x14007c56c  mov     [rsp+1D0h+var_190], rax
0x14007c571  lea     rax, Smb2FileAccessMapping
0x14007c578  mov     byte ptr [rsp+1D0h+var_198], 1
0x14007c57d  mov     [rsp+1D0h+var_1A0], rax
0x14007c582  lea     rax, [rbp+0B0h+Privileges]
0x14007c586  mov     [rsp+1D0h+var_1A8], rax
0x14007c58b  mov     dword ptr [rsp+1D0h+var_1B0], 0
0x14007c593  call    cs:__imp_SrvLibSeAccessCheck
0x14007c59a  nop     dword ptr [rax+rax+00h]
0x14007c59f  test    al, al
0x14007c5a1  jz      short loc_14007C5AA
0x14007c5a3  mov     [rbp+0B0h+var_130], 0
0x14007c5aa  mov     rcx, [rbp+0B0h+Privileges]; Privileges
0x14007c5ae  test    rcx, rcx
0x14007c5b1  jnz     loc_14007C65E
0x14007c5b7  lea     rcx, [rbp+0B0h+SubjectContext]; SubjectContext
0x14007c5bb  call    cs:__imp_SeReleaseSubjectContext
0x14007c5c2  nop     dword ptr [rax+rax+00h]
0x14007c5c7  mov     rcx, gs:188h; Thread
0x14007c5d0  xor     edx, edx; Token
0x14007c5d2  call    cs:__imp_PsAssignImpersonationToken
0x14007c5d9  nop     dword ptr [rax+rax+00h]
0x14007c5de  mov     r15b, 1
0x14007c5e1  jmp     loc_14007C3E7
0x14007c5e6  mov     r13b, 1
0x14007c5e9  btr     eax, 18h
0x14007c5ed  mov     [rbp+0B0h+var_12C], r13b
0x14007c5f1  mov     [rbp+0B0h+AccessMask], eax
0x14007c5f4  jmp     loc_14007C378
0x14007c5f9  mov     edx, [r14]
0x14007c5fc  test    edi, 116h
0x14007c602  setz    cl
0x14007c605  test    dl, 1
0x14007c608  setz    al
0x14007c60b  test    al, cl
0x14007c60d  jz      loc_14007C388
0x14007c613  or      edx, 1
0x14007c616  mov     [r14], edx
0x14007c619  jmp     loc_14007C388
0x14007c61e  or      dword ptr [r14], 4
0x14007c622  jmp     loc_14007C398
0x14007c627  lea     r8, Smb2FileAccessMapping
0x14007c62e  mov     byte ptr [rsp+1D0h+var_1B0], 1
0x14007c633  xor     ecx, ecx
0x14007c635  call    cs:__imp_SrvLibRetrieveMaximalAccessRightsForUser
0x14007c63c  nop     dword ptr [rax+rax+00h]
0x14007c641  mov     r15d, eax
0x14007c644  jmp     loc_14007C4A6
0x14007c649  mov     rcx, [rsi+38h]
0x14007c64d  mov     eax, [rbx+110h]
0x14007c653  mov     [rcx+8Ch], eax
0x14007c659  jmp     loc_14007C3C4
0x14007c65e  call    cs:__imp_SeFreePrivileges
0x14007c665  nop     dword ptr [rax+rax+00h]
0x14007c66a  jmp     loc_14007C5B7
0x14007c66f  mov     [rbp+0B0h+var_128], 1F01FFh
0x14007c676  mov     [rbp+0B0h+var_130], 0
0x14007c67d  jmp     loc_14007C3E7
0x14007c682  test    r15b, r15b
0x14007c685  jnz     loc_1400981BE
0x14007c68b  cmp     qword ptr [r14], 0
0x14007c68f  jnz     loc_14007C50C
0x14007c695  jmp     loc_1400981BE
0x14007c69a  bts     ecx, 18h
0x14007c69e  jmp     loc_14007C443
0x1400981be  mov     rcx, [rsi+30h]
0x1400981c2  call    Smb2ImpersonateSecurityContext
0x1400981c7  test    eax, eax
0x1400981c9  js      loc_14007C40A
0x1400981cf  mov     r9, [rbp+0B0h+var_F8]
0x1400981d3  test    r9, r9
0x1400981d6  jz      short loc_1400981DF
0x1400981d8  cmp     word ptr [r9], 0
0x1400981dd  jnz     short loc_1400981E6
0x1400981df  lea     r9, Smb2PathSeparatorString
0x1400981e6  mov     eax, [rbp+0B0h+var_130]
0x1400981e9  lea     r8, [rbx+78h]
0x1400981ed  mov     r15, [rbp+0B0h+var_120]
0x1400981f1  lea     rcx, [rbx+68h]
0x1400981f5  mov     dword ptr [rsp+1D0h+var_190], eax
0x1400981f9  lea     rax, [rbp+0B0h+var_D0]
0x1400981fd  mov     [rsp+1D0h+var_198], rax
0x140098202  mov     rax, [r14]
0x140098205  mov     rdx, [r15+60h]
0x140098209  mov     [rsp+1D0h+var_1A0], rax
0x14009820e  add     rdx, 0D8h
0x140098215  mov     eax, [rbp+0B0h+var_128]
0x140098218  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x14009821c  mov     eax, [rbp+0B0h+AccessMask]
0x14009821f  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140098223  call    cs:__imp_SrvLibAuditShareAccess
0x14009822a  nop     dword ptr [rax+rax+00h]
0x14009822f  mov     rcx, gs:188h; Thread
0x140098238  xor     edx, edx; Token
0x14009823a  call    cs:__imp_PsAssignImpersonationToken
0x140098241  nop     dword ptr [rax+rax+00h]
0x140098246  nop
0x140098247  jmp     loc_14007C40E
0x14009824c  xor     r13d, r13d
0x14009824f  mov     rdi, [r14]
0x140098252  mov     rcx, rdi; SecurityDescriptor
0x140098255  call    cs:__imp_RtlLengthSecurityDescriptor
0x14009825c  nop     dword ptr [rax+rax+00h]
0x140098261  mov     r11, [r15+60h]
0x140098265  mov     edx, eax
0x140098267  movzx   r14d, word ptr [rbp+0B0h+var_118]
0x14009826c  shr     r14w, 1
0x140098270  movzx   esi, word ptr [r11+168h]
0x140098278  lea     r15, [r11+0D8h]
0x14009827f  movzx   ecx, word ptr [r15]; af
0x140098283  shr     si, 1
0x140098286  call    SOCKADDR_SIZE
0x14009828b  movzx   ecx, word ptr [rbx+78h]
0x14009828f  movzx   r9d, word ptr [rbx+68h]
0x140098294  mov     r8, [rbp+0B0h+var_120]
0x140098298  mov     [rsp+1D0h+var_138], r13
0x1400982a0  add     r8, 248h
0x1400982a7  movzx   r10d, al
0x1400982ab  mov     eax, [rbp+0B0h+var_130]
0x1400982ae  mov     [rsp+1D0h+var_140], eax
0x1400982b5  mov     [rsp+1D0h+var_148], eax
0x1400982bc  mov     eax, [rbp+0B0h+var_128]
0x1400982bf  mov     [rsp+1D0h+var_150], rdi
0x1400982c7  mov     [rsp+1D0h+var_158], edx
0x1400982cb  mov     [rsp+1D0h+var_160], eax
0x1400982cf  mov     eax, [rbp+0B0h+AccessMask]
0x1400982d2  mov     [rsp+1D0h+var_168], eax
0x1400982d6  mov     rax, [r11+170h]
0x1400982dd  mov     [rsp+1D0h+var_170], rax
0x1400982e2  mov     rax, [rbp+0B0h+var_110]
0x1400982e6  mov     [rsp+1D0h+var_178], si
0x1400982eb  mov     [rsp+1D0h+var_180], rax
0x1400982f0  mov     rax, [rbx+80h]
0x1400982f7  mov     word ptr [rsp+1D0h+var_188], r14w
0x1400982fd  mov     [rsp+1D0h+var_190], r15
  ... truncated ...
```
