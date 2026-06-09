# Smb2CheckShareAccess

- ea: `0x14007c260`
- end: `0x14007c653`
- name: `Smb2CheckShareAccess`
- size: `1011`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140066d74`
- `0x14007a84c`

## callees

- `0x140004dcc`
- `0x140015960`
- `0x1400281c8`
- `0x140038490`
- `0x140038980`
- `0x14007c260`
- `0x14009175c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007c351`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007c351`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007c3cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007c3cf`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140098205`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140098205`
- `ntoskrnl!RtlMapGenericMask` at `0x14007c30f`
- `ntoskrnl!RtlMapGenericMask` at `0x14007c30f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007c4ec`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007c4ec`
- `ntoskrnl!SeFreePrivileges` at `0x14007c60e`
- `ntoskrnl!SeFreePrivileges` at `0x14007c60e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007c56b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007c56b`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c461`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c582`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400981ea`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c461`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14007c582`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400981ea`
- `srvnet!SrvLibAuditSuccessEnabled` at `0x14007c3a6`
- `srvnet!SrvLibAuditSuccessEnabled` at `0x14007c3a6`
- `srvnet!SrvLibAuditShareAccess` at `0x1400981d3`
- `srvnet!SrvLibAuditShareAccess` at `0x1400981d3`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x14007c5e5`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x14007c5e5`
- `srvnet!SrvLibSeAccessCheck` at `0x14007c543`
- `srvnet!SrvLibSeAccessCheck` at `0x14007c543`
- `ksecdd!FreeContextBuffer` at `0x1400982e8`
- `ksecdd!FreeContextBuffer` at `0x1400982e8`

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
  struct _UNICODE_STRING v37; // [rsp+B8h] [rbp-68h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+C8h] [rbp-58h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+D0h] [rbp-50h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+E0h] [rbp-40h] BYREF
  _BYTE v41[128]; // [rsp+100h] [rbp-20h] BYREF

  pvContextBuffer[1] = a2;
  v36 = a1;
  v6 = a1;
  AccessMask = a3;
  v32 = 0;
  v34 = 0;
  Privileges = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(v41, 0, sizeof(v41));
  v8 = *(_QWORD **)(v6 + 560);
  pvContextBuffer[0] = 0;
  *(_QWORD *)&v37.Length = 0;
  v37.Buffer = 0;
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
                                v41,
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
  Smb2GetUserName((__int64)v8, (PCWSTR *)pvContextBuffer, &v37);
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
    v25 = v37.Length >> 1;
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
      (__int64)v37.Buffer,
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
0x14007c260  push    rbp
0x14007c262  push    rbx
0x14007c263  push    rsi
0x14007c264  push    rdi
0x14007c265  push    r12
0x14007c267  push    r14
0x14007c269  push    r15
0x14007c26b  lea     rbp, [rsp-80h]
0x14007c270  sub     rsp, 1A0h
0x14007c277  mov     rax, cs:__security_cookie
0x14007c27e  xor     rax, rsp
0x14007c281  mov     [rbp+0B0h+var_50], rax
0x14007c285  mov     r12, [rbp+0B0h+arg_20]
0x14007c28c  xor     ebx, ebx
0x14007c28e  xorps   xmm0, xmm0
0x14007c291  mov     [rbp+0B0h+var_F8], rdx
0x14007c295  mov     edi, r8d
0x14007c298  mov     [rbp+0B0h+var_120], rcx
0x14007c29c  mov     r15, rcx
0x14007c29f  mov     [rbp+0B0h+AccessMask], r8d
0x14007c2a3  xor     edx, edx; Val
0x14007c2a5  mov     [rbp+0B0h+var_130], ebx
0x14007c2a8  mov     r8d, 80h; Size
0x14007c2ae  mov     [rbp+0B0h+var_128], ebx
0x14007c2b1  lea     rcx, [rbp+0B0h+var_D0]; void *
0x14007c2b5  mov     [rbp+0B0h+Privileges], rbx
0x14007c2b9  movups  xmmword ptr [rbp+0B0h+SubjectContext.ClientToken], xmm0
0x14007c2bd  mov     r14, r9
0x14007c2c0  movups  xmmword ptr [rbp+0B0h+SubjectContext.PrimaryToken], xmm0
0x14007c2c4  call    memset
0x14007c2c9  mov     rsi, [r15+230h]
0x14007c2d0  mov     [rbp+0B0h+pvContextBuffer], rbx
0x14007c2d4  mov     [rbp+0B0h+var_118], rbx
0x14007c2d8  mov     [rbp+0B0h+var_110], rbx
0x14007c2dc  test    r12, r12
0x14007c2df  jz      short loc_14007C2E5
0x14007c2e1  mov     [r12], ebx
0x14007c2e5  test    edi, edi
0x14007c2e7  jz      loc_14007C41E
0x14007c2ed  mov     rbx, [rsi+38h]
0x14007c2f1  lea     rdx, Smb2FileAccessMapping; GenericMapping
0x14007c2f8  mov     [rsp+1D0h+var_38], r13
0x14007c300  lea     rcx, [rbp+0B0h+AccessMask]; AccessMask
0x14007c304  xor     r13b, r13b
0x14007c307  mov     [rbp+0B0h+var_12C], r13b
0x14007c30b  mov     rbx, [rbx+60h]
0x14007c30f  call    cs:__imp_RtlMapGenericMask
0x14007c316  nop     dword ptr [rax+rax+00h]
0x14007c31b  mov     eax, [rbp+0B0h+AccessMask]
0x14007c31e  bt      eax, 18h
0x14007c322  jb      loc_14007C596
0x14007c328  test    dword ptr [rbx+120h], 100h
0x14007c332  jnz     loc_14007C5A9
0x14007c338  test    dword ptr [rbx+120h], 200h
0x14007c342  jnz     loc_14007C5CE
0x14007c348  mov     rcx, [rbx]
0x14007c34b  mov     dl, 1; Wait
0x14007c34d  add     rcx, 60h ; '`'; Resource
0x14007c351  call    cs:__imp_ExAcquireResourceSharedLite
0x14007c358  nop     dword ptr [rax+rax+00h]
0x14007c35d  mov     r14, [rsi+38h]
0x14007c361  mov     eax, [r14+8Ch]
0x14007c368  cmp     [rbx+110h], eax
0x14007c36e  jnz     loc_14007C425
0x14007c374  mov     rax, [rsi+38h]
0x14007c378  xor     r15b, r15b
0x14007c37b  mov     ecx, [rax+88h]
0x14007c381  mov     eax, ecx
0x14007c383  or      eax, edi
0x14007c385  cmp     eax, ecx
0x14007c387  jnz     loc_14007C4BC
0x14007c38d  mov     [rbp+0B0h+var_128], ecx
0x14007c390  lea     r14, [rbx+108h]
0x14007c397  cmp     [rbp+0B0h+var_130], 0
0x14007c39b  jl      loc_14007C632
0x14007c3a1  mov     ecx, 80h
0x14007c3a6  call    cs:__imp_SrvLibAuditSuccessEnabled
0x14007c3ad  nop     dword ptr [rax+rax+00h]
0x14007c3b2  test    al, al
0x14007c3b4  jnz     loc_14007C632
0x14007c3ba  mov     r15, [rbp+0B0h+var_120]
0x14007c3be  cmp     [rbp+0B0h+var_130], 0
0x14007c3c2  jl      loc_14007C47E
0x14007c3c8  mov     rcx, [rbx]
0x14007c3cb  add     rcx, 60h ; '`'; Resource
0x14007c3cf  call    cs:__imp_ExReleaseResourceLite
0x14007c3d6  nop     dword ptr [rax+rax+00h]
0x14007c3db  mov     eax, [rbp+0B0h+var_130]
0x14007c3de  test    eax, eax
0x14007c3e0  js      short loc_14007C3F7
0x14007c3e2  test    r12, r12
0x14007c3e5  jz      short loc_14007C3F7
0x14007c3e7  mov     ecx, [rbp+0B0h+var_128]
0x14007c3ea  test    r13b, r13b
0x14007c3ed  jnz     loc_14007C64A
0x14007c3f3  mov     [r12], ecx
0x14007c3f7  mov     r13, [rsp+1D0h+var_38]
0x14007c3ff  mov     rcx, [rbp+0B0h+var_50]
0x14007c403  xor     rcx, rsp; StackCookie
0x14007c406  call    __security_check_cookie
0x14007c40b  add     rsp, 1A0h
0x14007c412  pop     r15
0x14007c414  pop     r14
0x14007c416  pop     r12
0x14007c418  pop     rdi
0x14007c419  pop     rsi
0x14007c41a  pop     rbx
0x14007c41b  pop     rbp
0x14007c41c  retn
0x14007c41e  mov     eax, 0C0000022h
0x14007c423  jmp     short loc_14007C3FF
0x14007c425  mov     rcx, [rsi+30h]
0x14007c429  call    Smb2ImpersonateSecurityContext
0x14007c42e  test    eax, eax
0x14007c430  js      short loc_14007C4B0
0x14007c432  lea     r9, [r14+88h]
0x14007c439  lea     r14, [rbx+108h]
0x14007c440  mov     rdx, [r14]
0x14007c443  test    rdx, rdx
0x14007c446  jnz     loc_14007C5D7
0x14007c44c  mov     dword ptr [r9], 11F01FFh
0x14007c453  xor     r15d, r15d
0x14007c456  mov     rcx, gs:188h; Thread
0x14007c45f  xor     edx, edx; Token
0x14007c461  call    cs:__imp_PsAssignImpersonationToken
0x14007c468  nop     dword ptr [rax+rax+00h]
0x14007c46d  mov     [rbp+0B0h+var_130], r15d
0x14007c471  test    r15d, r15d
0x14007c474  jns     loc_14007C5F9
0x14007c47a  mov     r15, [rbp+0B0h+var_120]
0x14007c47e  lea     r8, [rbp+0B0h+var_118]
0x14007c482  mov     rcx, rsi
0x14007c485  lea     rdx, [rbp+0B0h+pvContextBuffer]
0x14007c489  call    Smb2GetUserName
0x14007c48e  cmp     cs:Microsoft_Windows_SMBServerEnableBits, 0
0x14007c495  jge     loc_1400982DB
0x14007c49b  mov     rax, [rsi+20h]
0x14007c49f  test    rax, rax
0x14007c4a2  jz      loc_1400981FC
0x14007c4a8  mov     r13, [rax]
0x14007c4ab  jmp     loc_1400981FF
0x14007c4b0  mov     [rbp+0B0h+var_130], eax
0x14007c4b3  lea     r14, [rbx+108h]
0x14007c4ba  jmp     short loc_14007C47E
0x14007c4bc  lea     r14, [rbx+108h]
0x14007c4c3  mov     [rbp+0B0h+var_130], 0C0000022h
0x14007c4ca  cmp     qword ptr [r14], 0
0x14007c4ce  jz      loc_14007C61F
0x14007c4d4  mov     rcx, [rsi+30h]
0x14007c4d8  call    Smb2ImpersonateSecurityContext
0x14007c4dd  mov     [rbp+0B0h+var_130], eax
0x14007c4e0  test    eax, eax
0x14007c4e2  js      loc_14007C3BA
0x14007c4e8  lea     rcx, [rbp+0B0h+SubjectContext]; SubjectContext
0x14007c4ec  call    cs:__imp_SeCaptureSubjectContext
0x14007c4f3  nop     dword ptr [rax+rax+00h]
0x14007c4f8  mov     r9d, [rbp+0B0h+AccessMask]
0x14007c4fc  lea     rax, [rbp+0B0h+var_130]
0x14007c500  mov     rcx, [r14]
0x14007c503  lea     rdx, [rbp+0B0h+SubjectContext]
0x14007c507  mov     [rsp+1D0h+var_180], rax
0x14007c50c  xor     r8d, r8d
0x14007c50f  lea     rax, [rbp+0B0h+var_D0]
0x14007c513  mov     [rsp+1D0h+var_188], rax
0x14007c518  lea     rax, [rbp+0B0h+var_128]
0x14007c51c  mov     [rsp+1D0h+var_190], rax
0x14007c521  lea     rax, Smb2FileAccessMapping
0x14007c528  mov     byte ptr [rsp+1D0h+var_198], 1
0x14007c52d  mov     [rsp+1D0h+var_1A0], rax
0x14007c532  lea     rax, [rbp+0B0h+Privileges]
0x14007c536  mov     [rsp+1D0h+var_1A8], rax
0x14007c53b  mov     dword ptr [rsp+1D0h+var_1B0], 0
0x14007c543  call    cs:__imp_SrvLibSeAccessCheck
0x14007c54a  nop     dword ptr [rax+rax+00h]
0x14007c54f  test    al, al
0x14007c551  jz      short loc_14007C55A
0x14007c553  mov     [rbp+0B0h+var_130], 0
0x14007c55a  mov     rcx, [rbp+0B0h+Privileges]; Privileges
0x14007c55e  test    rcx, rcx
0x14007c561  jnz     loc_14007C60E
0x14007c567  lea     rcx, [rbp+0B0h+SubjectContext]; SubjectContext
0x14007c56b  call    cs:__imp_SeReleaseSubjectContext
0x14007c572  nop     dword ptr [rax+rax+00h]
0x14007c577  mov     rcx, gs:188h; Thread
0x14007c580  xor     edx, edx; Token
0x14007c582  call    cs:__imp_PsAssignImpersonationToken
0x14007c589  nop     dword ptr [rax+rax+00h]
0x14007c58e  mov     r15b, 1
0x14007c591  jmp     loc_14007C397
0x14007c596  mov     r13b, 1
0x14007c599  btr     eax, 18h
0x14007c59d  mov     [rbp+0B0h+var_12C], r13b
0x14007c5a1  mov     [rbp+0B0h+AccessMask], eax
0x14007c5a4  jmp     loc_14007C328
0x14007c5a9  mov     edx, [r14]
0x14007c5ac  test    edi, 116h
0x14007c5b2  setz    cl
0x14007c5b5  test    dl, 1
0x14007c5b8  setz    al
0x14007c5bb  test    al, cl
0x14007c5bd  jz      loc_14007C338
0x14007c5c3  or      edx, 1
0x14007c5c6  mov     [r14], edx
0x14007c5c9  jmp     loc_14007C338
0x14007c5ce  or      dword ptr [r14], 4
0x14007c5d2  jmp     loc_14007C348
0x14007c5d7  lea     r8, Smb2FileAccessMapping
0x14007c5de  mov     byte ptr [rsp+1D0h+var_1B0], 1
0x14007c5e3  xor     ecx, ecx
0x14007c5e5  call    cs:__imp_SrvLibRetrieveMaximalAccessRightsForUser
0x14007c5ec  nop     dword ptr [rax+rax+00h]
0x14007c5f1  mov     r15d, eax
0x14007c5f4  jmp     loc_14007C456
0x14007c5f9  mov     rcx, [rsi+38h]
0x14007c5fd  mov     eax, [rbx+110h]
0x14007c603  mov     [rcx+8Ch], eax
0x14007c609  jmp     loc_14007C374
0x14007c60e  call    cs:__imp_SeFreePrivileges
0x14007c615  nop     dword ptr [rax+rax+00h]
0x14007c61a  jmp     loc_14007C567
0x14007c61f  mov     [rbp+0B0h+var_128], 1F01FFh
0x14007c626  mov     [rbp+0B0h+var_130], 0
0x14007c62d  jmp     loc_14007C397
0x14007c632  test    r15b, r15b
0x14007c635  jnz     loc_14009816E
0x14007c63b  cmp     qword ptr [r14], 0
0x14007c63f  jnz     loc_14007C4BC
0x14007c645  jmp     loc_14009816E
0x14007c64a  bts     ecx, 18h
0x14007c64e  jmp     loc_14007C3F3
0x14009816e  mov     rcx, [rsi+30h]
0x140098172  call    Smb2ImpersonateSecurityContext
0x140098177  test    eax, eax
0x140098179  js      loc_14007C3BA
0x14009817f  mov     r9, [rbp+0B0h+var_F8]
0x140098183  test    r9, r9
0x140098186  jz      short loc_14009818F
0x140098188  cmp     word ptr [r9], 0
0x14009818d  jnz     short loc_140098196
0x14009818f  lea     r9, Smb2PathSeparatorString
0x140098196  mov     eax, [rbp+0B0h+var_130]
0x140098199  lea     r8, [rbx+78h]
0x14009819d  mov     r15, [rbp+0B0h+var_120]
0x1400981a1  lea     rcx, [rbx+68h]
0x1400981a5  mov     dword ptr [rsp+1D0h+var_190], eax
0x1400981a9  lea     rax, [rbp+0B0h+var_D0]
0x1400981ad  mov     [rsp+1D0h+var_198], rax
0x1400981b2  mov     rax, [r14]
0x1400981b5  mov     rdx, [r15+60h]
0x1400981b9  mov     [rsp+1D0h+var_1A0], rax
0x1400981be  add     rdx, 0D8h
0x1400981c5  mov     eax, [rbp+0B0h+var_128]
0x1400981c8  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x1400981cc  mov     eax, [rbp+0B0h+AccessMask]
0x1400981cf  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x1400981d3  call    cs:__imp_SrvLibAuditShareAccess
0x1400981da  nop     dword ptr [rax+rax+00h]
0x1400981df  mov     rcx, gs:188h; Thread
0x1400981e8  xor     edx, edx; Token
0x1400981ea  call    cs:__imp_PsAssignImpersonationToken
0x1400981f1  nop     dword ptr [rax+rax+00h]
0x1400981f6  nop
0x1400981f7  jmp     loc_14007C3BE
0x1400981fc  xor     r13d, r13d
0x1400981ff  mov     rdi, [r14]
0x140098202  mov     rcx, rdi; SecurityDescriptor
0x140098205  call    cs:__imp_RtlLengthSecurityDescriptor
0x14009820c  nop     dword ptr [rax+rax+00h]
0x140098211  mov     r11, [r15+60h]
0x140098215  mov     edx, eax
0x140098217  movzx   r14d, word ptr [rbp+0B0h+var_118]
0x14009821c  shr     r14w, 1
0x140098220  movzx   esi, word ptr [r11+168h]
0x140098228  lea     r15, [r11+0D8h]
0x14009822f  movzx   ecx, word ptr [r15]; af
0x140098233  shr     si, 1
0x140098236  call    SOCKADDR_SIZE
0x14009823b  movzx   ecx, word ptr [rbx+78h]
0x14009823f  movzx   r9d, word ptr [rbx+68h]
0x140098244  mov     r8, [rbp+0B0h+var_120]
0x140098248  mov     [rsp+1D0h+var_138], r13
0x140098250  add     r8, 248h
0x140098257  movzx   r10d, al
0x14009825b  mov     eax, [rbp+0B0h+var_130]
0x14009825e  mov     [rsp+1D0h+var_140], eax
0x140098265  mov     [rsp+1D0h+var_148], eax
0x14009826c  mov     eax, [rbp+0B0h+var_128]
0x14009826f  mov     [rsp+1D0h+var_150], rdi
0x140098277  mov     [rsp+1D0h+var_158], edx
0x14009827b  mov     [rsp+1D0h+var_160], eax
0x14009827f  mov     eax, [rbp+0B0h+AccessMask]
0x140098282  mov     [rsp+1D0h+var_168], eax
0x140098286  mov     rax, [r11+170h]
0x14009828d  mov     [rsp+1D0h+var_170], rax
0x140098292  mov     rax, [rbp+0B0h+var_110]
0x140098296  mov     [rsp+1D0h+var_178], si
0x14009829b  mov     [rsp+1D0h+var_180], rax
0x1400982a0  mov     rax, [rbx+80h]
0x1400982a7  mov     word ptr [rsp+1D0h+var_188], r14w
0x1400982ad  mov     [rsp+1D0h+var_190], r15
  ... truncated ...
```
