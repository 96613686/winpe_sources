# Smb2TrimDirectoryQueryResults

- ea: `0x140077378`
- end: `0x14007758e`
- name: `Smb2TrimDirectoryQueryResults`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140075d60`

## callees

- `0x140005070`
- `0x1400125d0`
- `0x1400152a0`
- `0x140038680`
- `0x140077378`
- `0x140077600`
- `0x140077628`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400975d2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400975d2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140097652`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140097652`
- `ntoskrnl!IofCallDriver` at `0x140097735`
- `ntoskrnl!IofCallDriver` at `0x140097735`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007757d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007757d`
- `ntoskrnl!IoReuseIrp` at `0x1400975a8`
- `ntoskrnl!IoReuseIrp` at `0x1400975a8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007741b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007741b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400774a8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400774a8`
- `srvnet!SrvNetFreeBuffer` at `0x1400774c0`
- `srvnet!SrvNetFreeBuffer` at `0x1400774c0`
- `srvnet!SrvNetAllocateBuffer` at `0x1400773ed`
- `srvnet!SrvNetAllocateBuffer` at `0x1400773ed`

## string_xrefs

- `0x140097719`: `Smb2TrimDirectoryQueryResults`

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
0x140077378  mov     [rsp-38h+arg_10], rbx
0x14007737d  mov     [rsp-38h+arg_0], rcx
0x140077382  push    rbp
0x140077383  push    rsi
0x140077384  push    rdi
0x140077385  push    r12
0x140077387  push    r13
0x140077389  push    r14
0x14007738b  push    r15
0x14007738d  mov     rbp, rsp
0x140077390  sub     rsp, 80h
0x140077397  mov     rdi, [rcx+230h]
0x14007739e  xorps   xmm0, xmm0
0x1400773a1  mov     rax, [rdi+0A0h]
0x1400773a8  mov     r13d, [rdi+0E0h]
0x1400773af  mov     rbx, [rax+18h]
0x1400773b3  movups  xmmword ptr [rbp+P], xmm0
0x1400773b7  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x1400773bb  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x1400773bf  test    r13d, r13d
0x1400773c2  jz      loc_140077535
0x1400773c8  mov     eax, [rdi+0D8h]
0x1400773ce  mov     rcx, rdi
0x1400773d1  mov     [rbp+arg_8], eax
0x1400773d4  call    Smb2ImpersonateWorkItem
0x1400773d9  test    eax, eax
0x1400773db  js      loc_1400774F9
0x1400773e1  mov     rax, [rdi+0A0h]
0x1400773e8  xor     edx, edx
0x1400773ea  mov     ecx, [rax+20h]
0x1400773ed  call    cs:__imp_SrvNetAllocateBuffer
0x1400773f4  nop     dword ptr [rax+rax+00h]
0x1400773f9  mov     r14, rax
0x1400773fc  test    rax, rax
0x1400773ff  jz      loc_14007753C
0x140077405  xor     r12d, r12d
0x140077408  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14007740c  mov     [rax+24h], r12d
0x140077410  mov     r15, rbx
0x140077413  mov     [rbp+P], r12
0x140077417  mov     dword ptr [rbp+P+8], r12d
0x14007741b  call    cs:__imp_SeCaptureSubjectContext
0x140077422  nop     dword ptr [rax+rax+00h]
0x140077427  mov     esi, [rbp+arg_8]
0x14007742a  mov     ecx, r13d
0x14007742d  xorps   xmm0, xmm0
0x140077430  movups  xmmword ptr [rbp+var_40], xmm0
0x140077434  cmp     esi, 0Ch
0x140077437  jnz     loc_140077515
0x14007743d  movzx   eax, word ptr [r15+8]
0x140077442  mov     rdx, [rdi+50h]; int
0x140077446  lea     r8, [rbp+P]; int
0x14007744a  mov     word ptr [rbp+var_40], ax
0x14007744e  xor     r15d, r15d
0x140077451  lea     rax, [rcx+rbx]
0x140077455  mov     r9d, 120089h; int
0x14007745b  mov     qword ptr [rbp+var_40+8], rax
0x14007745f  mov     rax, [rdi+38h]
0x140077463  mov     ecx, [rax+50h]
0x140077466  shr     ecx, 0Eh
0x140077469  and     cl, 1
0x14007746c  mov     [rsp+80h+var_50], cl; char
0x140077470  lea     rcx, [rbp+var_40]; int
0x140077474  mov     [rsp+80h+var_58], r15; __int64
0x140077479  call    Smb2IsAccessAllowedEx
0x14007747e  cmp     eax, 0C0000022h
0x140077483  jnz     loc_140077548
0x140077489  mov     ecx, [rbx]
0x14007748b  test    ecx, ecx
0x14007748d  jnz     loc_14007756C
0x140077493  mov     rcx, [rbp+P]; P
0x140077497  mov     rsi, [rbp+arg_0]
0x14007749b  test    rcx, rcx
0x14007749e  jnz     loc_14007757B
0x1400774a4  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400774a8  call    cs:__imp_SeReleaseSubjectContext
0x1400774af  nop     dword ptr [rax+rax+00h]
0x1400774b4  call    Smb2Revert
0x1400774b9  mov     rcx, [rdi+0A0h]
0x1400774c0  call    cs:__imp_SrvNetFreeBuffer
0x1400774c7  nop     dword ptr [rax+rax+00h]
0x1400774cc  mov     [rdi+0A0h], r14
0x1400774d3  test    r12, r12
0x1400774d6  jz      loc_1400975A2
0x1400774dc  mov     rax, [rsi+78h]
0x1400774e0  mov     ecx, [r14+24h]
0x1400774e4  mov     [rax+38h], rcx
0x1400774e8  mov     [r12], r15d
0x1400774ec  mov     rax, [rdi+48h]
0x1400774f0  mov     byte ptr [rax+0E7h], 1
0x1400774f7  xor     eax, eax
0x1400774f9  mov     rbx, [rsp+80h+arg_10]
0x140077501  add     rsp, 80h
0x140077508  pop     r15
0x14007750a  pop     r14
0x14007750c  pop     r13
0x14007750e  pop     r12
0x140077510  pop     rdi
0x140077511  pop     rsi
0x140077512  pop     rbp
0x140077513  retn
0x140077515  movzx   eax, word ptr [rbx+3Ch]
0x140077519  jmp     loc_140077442
0x14007751e  add     rbx, rcx
0x140077521  mov     rcx, r13
0x140077524  mov     r15, rbx
0x140077527  jnz     loc_14007742D
0x14007752d  xor     r15d, r15d
0x140077530  jmp     loc_140077493
0x140077535  mov     eax, 0C000000Dh
0x14007753a  jmp     short loc_1400774F9
0x14007753c  call    Smb2Revert
0x140077541  mov     eax, 0C000009Ah
0x140077546  jmp     short loc_1400774F9
0x140077548  mov     ecx, [r14+24h]
0x14007754c  mov     r12, [r14+18h]
0x140077550  mov     r15d, [rbx]
0x140077553  add     r12, rcx
0x140077556  test    r15d, r15d
0x140077559  jnz     loc_140097588
0x14007755f  movzx   r15d, word ptr [rbp+var_40]
0x140077564  add     r15d, r13d
0x140077567  jmp     loc_140097588
0x14007756c  test    byte ptr [rdi+0D4h], 2
0x140077573  jnz     loc_140077493
0x140077579  jmp     short loc_14007751E
0x14007757b  xor     edx, edx; Tag
0x14007757d  call    cs:__imp_ExFreePoolWithTag
0x140077584  nop     dword ptr [rax+rax+00h]
0x140077589  jmp     loc_1400774A4
0x140097588  mov     r8d, r15d; Size
0x14009758b  mov     rdx, rbx; Src
0x14009758e  mov     rcx, r12; void *
0x140097591  call    memmove
0x140097596  add     [r14+24h], r15d
0x14009759a  xor     r15d, r15d
0x14009759d  jmp     loc_140077489
0x1400975a2  mov     rcx, [rsi+78h]; Irp
0x1400975a6  xor     edx, edx; Iostatus
0x1400975a8  call    cs:__imp_IoReuseIrp
0x1400975af  nop     dword ptr [rax+rax+00h]
0x1400975b4  mov     rax, [rdi+50h]
0x1400975b8  mov     rcx, [rsi+78h]
0x1400975bc  mov     rax, [rax+60h]
0x1400975c0  mov     [rcx+0C0h], rax
0x1400975c7  mov     rax, [rsi+40h]
0x1400975cb  mov     rbx, [rax+88h]
0x1400975d2  call    cs:__imp_KeGetCurrentNodeNumber
0x1400975d9  nop     dword ptr [rax+rax+00h]
0x1400975de  movzx   eax, ax
0x1400975e1  mov     rcx, [rbx+rax*8+8]
0x1400975e6  mov     rax, [rsi+78h]
0x1400975ea  mov     rdx, [rcx+0E0h]
0x1400975f1  lea     rcx, Smb2ContinueQueryDirectory
0x1400975f8  mov     [rax+98h], rdx
0x1400975ff  mov     rax, [rsi+78h]
0x140097603  mov     [rax+40h], r15b
0x140097607  mov     rax, [rsi+78h]
0x14009760b  mov     [rax+30h], r15d
0x14009760f  mov     rax, [rsi+78h]
0x140097613  mov     [rax+38h], r15
0x140097617  mov     rax, [rsi+78h]
0x14009761b  mov     rbx, [rax+0B8h]
0x140097622  mov     [rsi+30h], rcx
0x140097626  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14009762d  mov     rax, [rax+0B8h]
0x140097634  mov     [rax-10h], rcx
0x140097638  mov     [rax-8], rsi
0x14009763c  mov     byte ptr [rax-45h], 0E0h
0x140097640  mov     word ptr [rbx-48h], 10Ch
0x140097646  mov     rax, [rdi+50h]
0x14009764a  mov     rcx, [rax+60h]; FileObject
0x14009764e  mov     [rbx-18h], rcx
0x140097652  call    cs:__imp_IoGetRelatedDeviceObject
0x140097659  nop     dword ptr [rax+rax+00h]
0x14009765e  mov     [rbx-20h], rax
0x140097662  lea     rax, [rdi+0C0h]
0x140097669  mov     [rbx-38h], rax
0x14009766d  mov     [rbx-46h], r15b
0x140097671  mov     eax, [rdi+0D0h]
0x140097677  mov     [rbx-28h], eax
0x14009767a  mov     eax, [rdi+0E4h]
0x140097680  mov     [rbx-40h], eax
0x140097683  mov     eax, [rbp+arg_8]
0x140097686  mov     [rbx-30h], eax
0x140097689  mov     al, [rdi+0D4h]
0x14009768f  and     al, 0FEh
0x140097691  mov     [rbx-46h], al
0x140097694  mov     rax, [rsi+78h]
0x140097698  mov     [rax+18h], r15
0x14009769c  mov     rax, [rsi+78h]
0x1400976a0  mov     [rax+8], r15
0x1400976a4  mov     rax, [rsi+78h]
0x1400976a8  mov     [rax+70h], r15
0x1400976ac  mov     rax, [rbx-20h]
0x1400976b0  mov     rcx, [rsi+78h]
0x1400976b4  mov     edx, [rax+30h]
0x1400976b7  mov     rax, [rdi+0A0h]
0x1400976be  test    dl, 4
0x1400976c1  jz      short loc_1400976D5
0x1400976c3  mov     rax, [rax+18h]
0x1400976c7  mov     [rcx+18h], rax
0x1400976cb  mov     rax, [rsi+78h]
0x1400976cf  or      dword ptr [rax+10h], 10h
0x1400976d3  jmp     short loc_1400976F5
0x1400976d5  test    dl, 10h
0x1400976d8  jnz     short loc_1400976ED
0x1400976da  mov     rax, [rax+18h]
0x1400976de  mov     [rcx+70h], rax
0x1400976e2  mov     rax, [rdi+0A0h]
0x1400976e9  mov     rcx, [rsi+78h]
0x1400976ed  mov     rax, [rax+38h]
0x1400976f1  mov     [rcx+8], rax
0x1400976f5  xor     edx, edx
0x1400976f7  mov     rcx, rsi
0x1400976fa  call    Srv2MarkWorkItemCancellable
0x1400976ff  test    eax, eax
0x140097701  jns     short loc_14009770D
0x140097703  mov     eax, 0C0000120h
0x140097708  jmp     loc_1400774F9
0x14009770d  lea     rcx, [rsi+248h]
0x140097714  mov     [rsp+80h+var_60], 1
0x140097719  lea     r9, aSmb2trimdirect; "Smb2TrimDirectoryQueryResults"
0x140097720  mov     r8d, 351h
0x140097726  mov     dl, 3
0x140097728  call    SRV2_PERF_ENTER_EX
0x14009772d  mov     rdx, [rsi+78h]; Irp
0x140097731  mov     rcx, [rbx-20h]; DeviceObject
0x140097735  call    cs:__imp_IofCallDriver
0x14009773c  nop     dword ptr [rax+rax+00h]
0x140097741  mov     eax, 103h
0x140097746  jmp     loc_1400774F9
```
