# Smb2TrimDirectoryQueryResults

- ea: `0x1400773c8`
- end: `0x1400775de`
- name: `Smb2TrimDirectoryQueryResults`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140075db0`

## callees

- `0x140005070`
- `0x1400125d0`
- `0x1400152a0`
- `0x140038680`
- `0x1400773c8`
- `0x140077650`
- `0x140077678`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140097622`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140097622`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400976a2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400976a2`
- `ntoskrnl!IofCallDriver` at `0x140097785`
- `ntoskrnl!IofCallDriver` at `0x140097785`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400775cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400775cd`
- `ntoskrnl!IoReuseIrp` at `0x1400975f8`
- `ntoskrnl!IoReuseIrp` at `0x1400975f8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007746b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007746b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400774f8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400774f8`
- `srvnet!SrvNetFreeBuffer` at `0x140077510`
- `srvnet!SrvNetFreeBuffer` at `0x140077510`
- `srvnet!SrvNetAllocateBuffer` at `0x14007743d`
- `srvnet!SrvNetAllocateBuffer` at `0x14007743d`

## string_xrefs

- `0x140097769`: `Smb2TrimDirectoryQueryResults`

## pseudocode

```c
SECURITY_STATUS __fastcall Smb2TrimDirectoryQueryResults(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r13
  unsigned int *v3; // rbx
  SECURITY_STATUS result; // eax
  __int64 Buffer; // rax
  __int64 v6; // r14
  _DWORD *v7; // r12
  unsigned int *v8; // r15
  __int64 v9; // rcx
  __int16 v10; // ax
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // zf
  __int64 v14; // rcx
  unsigned int v15; // r15d
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  struct _FILE_OBJECT *v20; // rcx
  _QWORD *v21; // rcx
  int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rdx
  ULONG v25; // [rsp+20h] [rbp-60h]
  int v26[4]; // [rsp+40h] [rbp-40h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-30h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-20h] BYREF
  int v30; // [rsp+C8h] [rbp+48h]

  v1 = *(_QWORD *)(a1 + 560);
  v2 = *(unsigned int *)(v1 + 224);
  v3 = *(unsigned int **)(*(_QWORD *)(v1 + 160) + 24LL);
  *(_OWORD *)P = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( !(_DWORD)v2 )
    return -1073741811;
  v30 = *(_DWORD *)(v1 + 216);
  result = Smb2ImpersonateWorkItem(v1);
  if ( result >= 0 )
  {
    Buffer = SrvNetAllocateBuffer(*(unsigned int *)(*(_QWORD *)(v1 + 160) + 32LL), 0);
    v6 = Buffer;
    if ( Buffer )
    {
      v7 = 0;
      *(_DWORD *)(Buffer + 36) = 0;
      v8 = v3;
      P[0] = 0;
      LODWORD(P[1]) = 0;
      SeCaptureSubjectContext(&SubjectContext);
      v9 = (unsigned int)v2;
      do
      {
        *(_OWORD *)v26 = 0;
        if ( v30 == 12 )
          v10 = *((_WORD *)v8 + 4);
        else
          v10 = *((_WORD *)v3 + 30);
        v11 = *(_QWORD *)(v1 + 80);
        LOWORD(v26[0]) = v10;
        *(_QWORD *)&v26[2] = (char *)v3 + v9;
        if ( (unsigned int)Smb2IsAccessAllowedEx(
                             (struct _UNICODE_STRING *)v26,
                             v11,
                             (__int64 *)P,
                             0x120089u,
                             v25,
                             0,
                             (*(_DWORD *)(*(_QWORD *)(v1 + 56) + 80LL) & 0x4000) != 0) != -1073741790 )
        {
          v14 = *(unsigned int *)(v6 + 36);
          v15 = *v3;
          v7 = (_DWORD *)(v14 + *(_QWORD *)(v6 + 24));
          if ( !*v3 )
            v15 = v2 + LOWORD(v26[0]);
          memmove((void *)(v14 + *(_QWORD *)(v6 + 24)), v3, v15);
          *(_DWORD *)(v6 + 36) += v15;
        }
        v12 = *v3;
        if ( !(_DWORD)v12 )
          break;
        if ( (*(_BYTE *)(v1 + 212) & 2) != 0 )
          break;
        v13 = (unsigned int *)((char *)v3 + v12) == 0;
        v3 = (unsigned int *)((char *)v3 + v12);
        v9 = v2;
        v8 = v3;
      }
      while ( !v13 );
      if ( P[0] )
        ExFreePoolWithTag(P[0], 0);
      SeReleaseSubjectContext(&SubjectContext);
      Smb2Revert();
      SrvNetFreeBuffer(*(_QWORD *)(v1 + 160));
      *(_QWORD *)(v1 + 160) = v6;
      if ( v7 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = *(unsigned int *)(v6 + 36);
        *v7 = 0;
        *(_BYTE *)(*(_QWORD *)(v1 + 72) + 231LL) = 1;
        return 0;
      }
      else
      {
        IoReuseIrp(*(PIRP *)(a1 + 120), 0);
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 192LL) = *(_QWORD *)(*(_QWORD *)(v1 + 80) + 96LL);
        v16 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 152LL) = *(_QWORD *)(*(_QWORD *)(v16 + 8LL * KeGetCurrentNodeNumber() + 8)
                                                               + 224LL);
        *(_BYTE *)(*(_QWORD *)(a1 + 120) + 64LL) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
        v17 = *(_QWORD *)(a1 + 120);
        v18 = *(_QWORD *)(v17 + 184);
        *(_QWORD *)(a1 + 48) = Smb2ContinueQueryDirectory;
        v19 = *(_QWORD *)(v17 + 184);
        *(_QWORD *)(v19 - 16) = Srv2PostOnCompletionAndClearCancel;
        *(_QWORD *)(v19 - 8) = a1;
        *(_BYTE *)(v19 - 69) = -32;
        *(_WORD *)(v18 - 72) = 268;
        v20 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v1 + 80) + 96LL);
        *(_QWORD *)(v18 - 24) = v20;
        *(_QWORD *)(v18 - 32) = IoGetRelatedDeviceObject(v20);
        *(_QWORD *)(v18 - 56) = v1 + 192;
        *(_BYTE *)(v18 - 70) = 0;
        *(_DWORD *)(v18 - 40) = *(_DWORD *)(v1 + 208);
        *(_DWORD *)(v18 - 64) = *(_DWORD *)(v1 + 228);
        *(_DWORD *)(v18 - 48) = v30;
        *(_BYTE *)(v18 - 70) = *(_BYTE *)(v1 + 212) & 0xFE;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
        v21 = *(_QWORD **)(a1 + 120);
        v22 = *(_DWORD *)(*(_QWORD *)(v18 - 32) + 48LL);
        v23 = *(_QWORD *)(v1 + 160);
        if ( (v22 & 4) != 0 )
        {
          v21[3] = *(_QWORD *)(v23 + 24);
          *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) |= 0x10u;
        }
        else
        {
          if ( (v22 & 0x10) == 0 )
          {
            v21[14] = *(_QWORD *)(v23 + 24);
            v23 = *(_QWORD *)(v1 + 160);
            v21 = *(_QWORD **)(a1 + 120);
          }
          v21[1] = *(_QWORD *)(v23 + 56);
        }
        if ( (int)Srv2MarkWorkItemCancellable(a1, 0) >= 0 )
        {
          LOBYTE(v25) = 1;
          LOBYTE(v24) = 3;
          SRV2_PERF_ENTER_EX(a1 + 584, v24, 849, "Smb2TrimDirectoryQueryResults", v25);
          IofCallDriver(*(PDEVICE_OBJECT *)(v18 - 32), *(PIRP *)(a1 + 120));
          return 259;
        }
        else
        {
          return -1073741536;
        }
      }
    }
    else
    {
      Smb2Revert();
      return -1073741670;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400773c8  mov     [rsp-38h+arg_10], rbx
0x1400773cd  mov     [rsp-38h+arg_0], rcx
0x1400773d2  push    rbp
0x1400773d3  push    rsi
0x1400773d4  push    rdi
0x1400773d5  push    r12
0x1400773d7  push    r13
0x1400773d9  push    r14
0x1400773db  push    r15
0x1400773dd  mov     rbp, rsp
0x1400773e0  sub     rsp, 80h
0x1400773e7  mov     rdi, [rcx+230h]
0x1400773ee  xorps   xmm0, xmm0
0x1400773f1  mov     rax, [rdi+0A0h]
0x1400773f8  mov     r13d, [rdi+0E0h]
0x1400773ff  mov     rbx, [rax+18h]
0x140077403  movups  xmmword ptr [rbp+P], xmm0
0x140077407  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14007740b  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14007740f  test    r13d, r13d
0x140077412  jz      loc_140077585
0x140077418  mov     eax, [rdi+0D8h]
0x14007741e  mov     rcx, rdi
0x140077421  mov     [rbp+arg_8], eax
0x140077424  call    Smb2ImpersonateWorkItem
0x140077429  test    eax, eax
0x14007742b  js      loc_140077549
0x140077431  mov     rax, [rdi+0A0h]
0x140077438  xor     edx, edx
0x14007743a  mov     ecx, [rax+20h]
0x14007743d  call    cs:__imp_SrvNetAllocateBuffer
0x140077444  nop     dword ptr [rax+rax+00h]
0x140077449  mov     r14, rax
0x14007744c  test    rax, rax
0x14007744f  jz      loc_14007758C
0x140077455  xor     r12d, r12d
0x140077458  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14007745c  mov     [rax+24h], r12d
0x140077460  mov     r15, rbx
0x140077463  mov     [rbp+P], r12
0x140077467  mov     dword ptr [rbp+P+8], r12d
0x14007746b  call    cs:__imp_SeCaptureSubjectContext
0x140077472  nop     dword ptr [rax+rax+00h]
0x140077477  mov     esi, [rbp+arg_8]
0x14007747a  mov     ecx, r13d
0x14007747d  xorps   xmm0, xmm0
0x140077480  movups  xmmword ptr [rbp+var_40], xmm0
0x140077484  cmp     esi, 0Ch
0x140077487  jnz     loc_140077565
0x14007748d  movzx   eax, word ptr [r15+8]
0x140077492  mov     rdx, [rdi+50h]; int
0x140077496  lea     r8, [rbp+P]; int
0x14007749a  mov     word ptr [rbp+var_40], ax
0x14007749e  xor     r15d, r15d
0x1400774a1  lea     rax, [rcx+rbx]
0x1400774a5  mov     r9d, 120089h; int
0x1400774ab  mov     qword ptr [rbp+var_40+8], rax
0x1400774af  mov     rax, [rdi+38h]
0x1400774b3  mov     ecx, [rax+50h]
0x1400774b6  shr     ecx, 0Eh
0x1400774b9  and     cl, 1
0x1400774bc  mov     [rsp+80h+var_50], cl; char
0x1400774c0  lea     rcx, [rbp+var_40]; int
0x1400774c4  mov     [rsp+80h+var_58], r15; __int64
0x1400774c9  call    Smb2IsAccessAllowedEx
0x1400774ce  cmp     eax, 0C0000022h
0x1400774d3  jnz     loc_140077598
0x1400774d9  mov     ecx, [rbx]
0x1400774db  test    ecx, ecx
0x1400774dd  jnz     loc_1400775BC
0x1400774e3  mov     rcx, [rbp+P]; P
0x1400774e7  mov     rsi, [rbp+arg_0]
0x1400774eb  test    rcx, rcx
0x1400774ee  jnz     loc_1400775CB
0x1400774f4  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400774f8  call    cs:__imp_SeReleaseSubjectContext
0x1400774ff  nop     dword ptr [rax+rax+00h]
0x140077504  call    Smb2Revert
0x140077509  mov     rcx, [rdi+0A0h]
0x140077510  call    cs:__imp_SrvNetFreeBuffer
0x140077517  nop     dword ptr [rax+rax+00h]
0x14007751c  mov     [rdi+0A0h], r14
0x140077523  test    r12, r12
0x140077526  jz      loc_1400975F2
0x14007752c  mov     rax, [rsi+78h]
0x140077530  mov     ecx, [r14+24h]
0x140077534  mov     [rax+38h], rcx
0x140077538  mov     [r12], r15d
0x14007753c  mov     rax, [rdi+48h]
0x140077540  mov     byte ptr [rax+0E7h], 1
0x140077547  xor     eax, eax
0x140077549  mov     rbx, [rsp+80h+arg_10]
0x140077551  add     rsp, 80h
0x140077558  pop     r15
0x14007755a  pop     r14
0x14007755c  pop     r13
0x14007755e  pop     r12
0x140077560  pop     rdi
0x140077561  pop     rsi
0x140077562  pop     rbp
0x140077563  retn
0x140077565  movzx   eax, word ptr [rbx+3Ch]
0x140077569  jmp     loc_140077492
0x14007756e  add     rbx, rcx
0x140077571  mov     rcx, r13
0x140077574  mov     r15, rbx
0x140077577  jnz     loc_14007747D
0x14007757d  xor     r15d, r15d
0x140077580  jmp     loc_1400774E3
0x140077585  mov     eax, 0C000000Dh
0x14007758a  jmp     short loc_140077549
0x14007758c  call    Smb2Revert
0x140077591  mov     eax, 0C000009Ah
0x140077596  jmp     short loc_140077549
0x140077598  mov     ecx, [r14+24h]
0x14007759c  mov     r12, [r14+18h]
0x1400775a0  mov     r15d, [rbx]
0x1400775a3  add     r12, rcx
0x1400775a6  test    r15d, r15d
0x1400775a9  jnz     loc_1400975D8
0x1400775af  movzx   r15d, word ptr [rbp+var_40]
0x1400775b4  add     r15d, r13d
0x1400775b7  jmp     loc_1400975D8
0x1400775bc  test    byte ptr [rdi+0D4h], 2
0x1400775c3  jnz     loc_1400774E3
0x1400775c9  jmp     short loc_14007756E
0x1400775cb  xor     edx, edx; Tag
0x1400775cd  call    cs:__imp_ExFreePoolWithTag
0x1400775d4  nop     dword ptr [rax+rax+00h]
0x1400775d9  jmp     loc_1400774F4
0x1400975d8  mov     r8d, r15d; Size
0x1400975db  mov     rdx, rbx; Src
0x1400975de  mov     rcx, r12; void *
0x1400975e1  call    memmove
0x1400975e6  add     [r14+24h], r15d
0x1400975ea  xor     r15d, r15d
0x1400975ed  jmp     loc_1400774D9
0x1400975f2  mov     rcx, [rsi+78h]; Irp
0x1400975f6  xor     edx, edx; Iostatus
0x1400975f8  call    cs:__imp_IoReuseIrp
0x1400975ff  nop     dword ptr [rax+rax+00h]
0x140097604  mov     rax, [rdi+50h]
0x140097608  mov     rcx, [rsi+78h]
0x14009760c  mov     rax, [rax+60h]
0x140097610  mov     [rcx+0C0h], rax
0x140097617  mov     rax, [rsi+40h]
0x14009761b  mov     rbx, [rax+88h]
0x140097622  call    cs:__imp_KeGetCurrentNodeNumber
0x140097629  nop     dword ptr [rax+rax+00h]
0x14009762e  movzx   eax, ax
0x140097631  mov     rcx, [rbx+rax*8+8]
0x140097636  mov     rax, [rsi+78h]
0x14009763a  mov     rdx, [rcx+0E0h]
0x140097641  lea     rcx, Smb2ContinueQueryDirectory
0x140097648  mov     [rax+98h], rdx
0x14009764f  mov     rax, [rsi+78h]
0x140097653  mov     [rax+40h], r15b
0x140097657  mov     rax, [rsi+78h]
0x14009765b  mov     [rax+30h], r15d
0x14009765f  mov     rax, [rsi+78h]
0x140097663  mov     [rax+38h], r15
0x140097667  mov     rax, [rsi+78h]
0x14009766b  mov     rbx, [rax+0B8h]
0x140097672  mov     [rsi+30h], rcx
0x140097676  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14009767d  mov     rax, [rax+0B8h]
0x140097684  mov     [rax-10h], rcx
0x140097688  mov     [rax-8], rsi
0x14009768c  mov     byte ptr [rax-45h], 0E0h
0x140097690  mov     word ptr [rbx-48h], 10Ch
0x140097696  mov     rax, [rdi+50h]
0x14009769a  mov     rcx, [rax+60h]; FileObject
0x14009769e  mov     [rbx-18h], rcx
0x1400976a2  call    cs:__imp_IoGetRelatedDeviceObject
0x1400976a9  nop     dword ptr [rax+rax+00h]
0x1400976ae  mov     [rbx-20h], rax
0x1400976b2  lea     rax, [rdi+0C0h]
0x1400976b9  mov     [rbx-38h], rax
0x1400976bd  mov     [rbx-46h], r15b
0x1400976c1  mov     eax, [rdi+0D0h]
0x1400976c7  mov     [rbx-28h], eax
0x1400976ca  mov     eax, [rdi+0E4h]
0x1400976d0  mov     [rbx-40h], eax
0x1400976d3  mov     eax, [rbp+arg_8]
0x1400976d6  mov     [rbx-30h], eax
0x1400976d9  mov     al, [rdi+0D4h]
0x1400976df  and     al, 0FEh
0x1400976e1  mov     [rbx-46h], al
0x1400976e4  mov     rax, [rsi+78h]
0x1400976e8  mov     [rax+18h], r15
0x1400976ec  mov     rax, [rsi+78h]
0x1400976f0  mov     [rax+8], r15
0x1400976f4  mov     rax, [rsi+78h]
0x1400976f8  mov     [rax+70h], r15
0x1400976fc  mov     rax, [rbx-20h]
0x140097700  mov     rcx, [rsi+78h]
0x140097704  mov     edx, [rax+30h]
0x140097707  mov     rax, [rdi+0A0h]
0x14009770e  test    dl, 4
0x140097711  jz      short loc_140097725
0x140097713  mov     rax, [rax+18h]
0x140097717  mov     [rcx+18h], rax
0x14009771b  mov     rax, [rsi+78h]
0x14009771f  or      dword ptr [rax+10h], 10h
0x140097723  jmp     short loc_140097745
0x140097725  test    dl, 10h
0x140097728  jnz     short loc_14009773D
0x14009772a  mov     rax, [rax+18h]
0x14009772e  mov     [rcx+70h], rax
0x140097732  mov     rax, [rdi+0A0h]
0x140097739  mov     rcx, [rsi+78h]
0x14009773d  mov     rax, [rax+38h]
0x140097741  mov     [rcx+8], rax
0x140097745  xor     edx, edx
0x140097747  mov     rcx, rsi
0x14009774a  call    Srv2MarkWorkItemCancellable
0x14009774f  test    eax, eax
0x140097751  jns     short loc_14009775D
0x140097753  mov     eax, 0C0000120h
0x140097758  jmp     loc_140077549
0x14009775d  lea     rcx, [rsi+248h]
0x140097764  mov     [rsp+80h+var_60], 1
0x140097769  lea     r9, aSmb2trimdirect; "Smb2TrimDirectoryQueryResults"
0x140097770  mov     r8d, 351h
0x140097776  mov     dl, 3
0x140097778  call    SRV2_PERF_ENTER_EX
0x14009777d  mov     rdx, [rsi+78h]; Irp
0x140097781  mov     rcx, [rbx-20h]; DeviceObject
0x140097785  call    cs:__imp_IofCallDriver
0x14009778c  nop     dword ptr [rax+rax+00h]
0x140097791  mov     eax, 103h
0x140097796  jmp     loc_140077549
```
