# NtRegisterProtocolAddressInformationExt

- ea: `0x140018370`
- end: `0x14001865d`
- name: `NtRegisterProtocolAddressInformationExt`
- size: `749`
- prototype: `NTSTATUS __stdcall(HANDLE ResourceManager, PCRM_PROTOCOL_ID ProtocolId, ULONG ProtocolInformationSize, PVOID ProtocolInformation, ULONG CreateOptions)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400014d4`
- `0x1400024e0`
- `0x140018370`
- `0x140018664`
- `0x140018888`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001862c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001862c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a33`
- `ntoskrnl!ObfDereferenceObject` at `0x140018607`
- `ntoskrnl!ObfDereferenceObject` at `0x140018607`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400185d1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400185d1`
- `ntoskrnl!RtlCompareMemory` at `0x14001849a`
- `ntoskrnl!RtlCompareMemory` at `0x1400184b6`
- `ntoskrnl!RtlCompareMemory` at `0x14001849a`
- `ntoskrnl!RtlCompareMemory` at `0x1400184b6`
- `ntoskrnl!ProbeForRead` at `0x1400183fd`
- `ntoskrnl!ProbeForRead` at `0x1400183fd`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400184fb`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400184fb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001856b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001856b`
- `ntoskrnl!SeAccessCheck` at `0x140018555`
- `ntoskrnl!SeAccessCheck` at `0x140018555`

## pseudocode

```c
NTSTATUS __stdcall NtRegisterProtocolAddressInformationExt(
        HANDLE ResourceManager,
        PCRM_PROTOCOL_ID ProtocolId,
        ULONG ProtocolInformationSize,
        PVOID ProtocolInformation,
        ULONG CreateOptions)
{
  PCRM_PROTOCOL_ID p_Source1; // r15
  void *v8; // rsi
  KPROCESSOR_MODE v9; // r13
  NTSTATUS v10; // ebx
  SIZE_T v11; // rbx
  SIZE_T v12; // rax
  BOOLEAN v13; // bl
  int AccessStatus; // [rsp+58h] [rbp-B0h] BYREF
  DWORD GrantedAccess[2]; // [rsp+60h] [rbp-A8h] BYREF
  PVOID Object; // [rsp+68h] [rbp-A0h] BYREF
  PVOID P; // [rsp+70h] [rbp-98h]
  __int64 v19; // [rsp+78h] [rbp-90h]
  PCRM_PROTOCOL_ID v20; // [rsp+80h] [rbp-88h]
  PVOID v21; // [rsp+88h] [rbp-80h]
  HANDLE Handle; // [rsp+90h] [rbp-78h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+98h] [rbp-70h] BYREF
  __int128 Source1; // [rsp+B8h] [rbp-50h] BYREF

  GrantedAccess[1] = ProtocolInformationSize;
  p_Source1 = ProtocolId;
  Handle = ResourceManager;
  Source1 = 0;
  v8 = 0;
  P = 0;
  v9 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v9 )
  {
    v19 = 1;
    ProbeForRead(ProtocolId, 1u, 4u);
    if ( ProtocolInformationSize )
    {
      v8 = (void *)TmpProbeAndCaptureBuffer(ProtocolInformation, ProtocolInformationSize);
      P = v8;
    }
    v21 = v8;
    RtlCopyFromUser(&Source1, p_Source1, 0x10u);
    p_Source1 = (PCRM_PROTOCOL_ID)&Source1;
    v20 = (PCRM_PROTOCOL_ID)&Source1;
  }
  else
  {
    v20 = ProtocolId;
    v21 = ProtocolInformation;
  }
  if ( CreateOptions <= 3 )
  {
    v11 = RtlCompareMemory(p_Source1, &TmpPromotingProtocolId, 0x10u);
    v12 = RtlCompareMemory(p_Source1, TmpOleTxProtocolId, 0x10u);
    if ( (v11 == 16 || v12 == 16)
      && (GrantedAccess[0] = 0,
          AccessStatus = 0,
          memset(&SubjectContext, 0, sizeof(SubjectContext)),
          SeCaptureSubjectContext(&SubjectContext),
          v13 = SeAccessCheck(
                  TmpKtmRmDescriptor,
                  &SubjectContext,
                  0,
                  0x20u,
                  0,
                  0,
                  (PGENERIC_MAPPING)&TmpResourceManagerMapping,
                  1,
                  GrantedAccess,
                  &AccessStatus),
          SeReleaseSubjectContext(&SubjectContext),
          !v13) )
    {
      v10 = AccessStatus;
    }
    else if ( (CreateOptions & 1) != 0 || (CreateOptions & 2) != 0 )
    {
      v10 = -1073741637;
    }
    else
    {
      Object = 0;
      v10 = ObReferenceObjectByHandle(Handle, 0x20u, (POBJECT_TYPE)TmResourceManagerObjectType, v9, &Object, 0);
      if ( v10 >= 0 )
      {
        v10 = TmRegisterProtocolAddressInformation(Object);
        ObfDereferenceObject(Object);
      }
    }
  }
  else
  {
    v10 = -1073741811;
  }
  if ( v10 < 0 && v8 )
    ExFreePoolWithTag(v8, 0);
  return v10;
}

```

## disassembly

```asm
0x140018370  push    rbx
0x140018372  push    rsi
0x140018373  push    r12
0x140018375  push    r13
0x140018377  push    r14
0x140018379  push    r15
0x14001837b  sub     rsp, 0D8h
0x140018382  mov     rax, cs:__security_cookie
0x140018389  xor     rax, rsp
0x14001838c  mov     [rsp+108h+var_40], rax
0x140018394  mov     r12, r9
0x140018397  mov     ebx, r8d
0x14001839a  mov     [rsp+108h+var_A4], ebx
0x14001839e  mov     r15, rdx
0x1400183a1  mov     [rsp+108h+Handle], rcx
0x1400183a9  mov     [rsp+108h+var_B8], 0
0x1400183b1  xorps   xmm0, xmm0
0x1400183b4  movups  [rsp+108h+Source1], xmm0
0x1400183bc  xor     esi, esi
0x1400183be  mov     [rsp+108h+P], rsi
0x1400183c3  mov     rax, gs:188h
0x1400183cc  mov     r13b, [rax+232h]
0x1400183d3  mov     [rsp+108h+var_B4], r13b
0x1400183d8  test    r13b, r13b
0x1400183db  jz      loc_140018463
0x1400183e1  lea     r14d, [rsi+10h]
0x1400183e5  mov     [rsp+108h+var_90], r14
0x1400183ea  mov     [rsp+108h+var_90], 1
0x1400183f3  lea     edx, [rsi+1]; Length
0x1400183f6  lea     r8d, [rsi+4]; Alignment
0x1400183fa  mov     rcx, r15; Address
0x1400183fd  call    cs:__imp_ProbeForRead
0x140018404  nop     dword ptr [rax+rax+00h]
0x140018409  test    ebx, ebx
0x14001840b  jz      short loc_140018423
0x14001840d  lea     r8d, [rsi+1]
0x140018411  mov     edx, ebx; Size
0x140018413  mov     rcx, r12; Src
0x140018416  call    TmpProbeAndCaptureBuffer
0x14001841b  mov     rsi, rax
0x14001841e  mov     [rsp+108h+P], rax
0x140018423  mov     r12, rsi
0x140018426  mov     [rsp+108h+var_80], rsi
0x14001842e  mov     r8, r14; Size
0x140018431  mov     rdx, r15; Src
0x140018434  lea     rcx, [rsp+108h+Source1]; void *
0x14001843c  call    RtlCopyFromUser
0x140018441  lea     r15, [rsp+108h+Source1]
0x140018449  mov     [rsp+108h+var_88], r15
0x140018451  jmp     short loc_140018479
0x140018453  mov     ebx, eax
0x140018455  mov     [rsp+108h+var_B8], eax
0x140018459  mov     rsi, [rsp+108h+P]
0x14001845e  jmp     loc_14001861E
0x140018463  mov     [rsp+108h+var_88], r15
0x14001846b  mov     [rsp+108h+var_80], r12
0x140018473  mov     r14d, 10h
0x140018479  cmp     [rsp+108h+CreateOptions], 3
0x140018481  jbe     short loc_14001848D
0x140018483  mov     ebx, 0C000000Dh
0x140018488  jmp     loc_14001861A
0x14001848d  mov     r8, r14; Length
0x140018490  lea     rdx, TmpPromotingProtocolId; Source2
0x140018497  mov     rcx, r15; Source1
0x14001849a  call    cs:__imp_RtlCompareMemory
0x1400184a1  nop     dword ptr [rax+rax+00h]
0x1400184a6  mov     rbx, rax
0x1400184a9  mov     r8, r14; Length
0x1400184ac  lea     rdx, TmpOleTxProtocolId; Source2
0x1400184b3  mov     rcx, r15; Source1
0x1400184b6  call    cs:__imp_RtlCompareMemory
0x1400184bd  nop     dword ptr [rax+rax+00h]
0x1400184c2  cmp     rbx, r14
0x1400184c5  jz      short loc_1400184D0
0x1400184c7  cmp     rax, r14
0x1400184ca  jnz     loc_140018584
0x1400184d0  mov     [rsp+108h+var_A8], 0
0x1400184d8  mov     [rsp+108h+var_B0], 0
0x1400184e0  xorps   xmm0, xmm0
0x1400184e3  movups  xmmword ptr [rsp+108h+SubjectContext.ClientToken], xmm0
0x1400184eb  movups  xmmword ptr [rsp+108h+SubjectContext.PrimaryToken], xmm0
0x1400184f3  lea     rcx, [rsp+108h+SubjectContext]; SubjectContext
0x1400184fb  call    cs:__imp_SeCaptureSubjectContext
0x140018502  nop     dword ptr [rax+rax+00h]
0x140018507  lea     rax, [rsp+108h+var_B0]
0x14001850c  mov     [rsp+108h+AccessStatus], rax; AccessStatus
0x140018511  lea     rax, [rsp+108h+var_A8]
0x140018516  mov     [rsp+108h+GrantedAccess], rax; GrantedAccess
0x14001851b  mov     [rsp+108h+AccessMode], 1; AccessMode
0x140018520  lea     rax, TmpResourceManagerMapping
0x140018527  mov     [rsp+108h+GenericMapping], rax; GenericMapping
0x14001852c  mov     [rsp+108h+Privileges], 0; Privileges
0x140018535  mov     [rsp+108h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14001853d  mov     r9d, 20h ; ' '; DesiredAccess
0x140018543  xor     r8d, r8d; SubjectContextLocked
0x140018546  lea     rdx, [rsp+108h+SubjectContext]; SubjectSecurityContext
0x14001854e  mov     rcx, cs:TmpKtmRmDescriptor; SecurityDescriptor
0x140018555  call    cs:__imp_SeAccessCheck
0x14001855c  nop     dword ptr [rax+rax+00h]
0x140018561  mov     bl, al
0x140018563  lea     rcx, [rsp+108h+SubjectContext]; SubjectContext
0x14001856b  call    cs:__imp_SeReleaseSubjectContext
0x140018572  nop     dword ptr [rax+rax+00h]
0x140018577  test    bl, bl
0x140018579  jnz     short loc_140018584
0x14001857b  mov     ebx, [rsp+108h+var_B0]
0x14001857f  jmp     loc_14001861A
0x140018584  mov     eax, [rsp+108h+CreateOptions]
0x14001858b  test    al, 1
0x14001858d  jnz     loc_140018615
0x140018593  mov     eax, [rsp+108h+CreateOptions]
0x14001859a  test    al, 2
0x14001859c  jnz     short loc_140018615
0x14001859e  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x1400185a5  mov     [rsp+108h+Object], 0
0x1400185ae  mov     [rsp+108h+Privileges], 0; HandleInformation
0x1400185b7  lea     rax, [rsp+108h+Object]
0x1400185bc  mov     qword ptr [rsp+108h+PreviouslyGrantedAccess], rax; Object
0x1400185c1  mov     r9b, r13b; AccessMode
0x1400185c4  mov     edx, 20h ; ' '; DesiredAccess
0x1400185c9  mov     rcx, [rsp+108h+Handle]; Handle
0x1400185d1  call    cs:__imp_ObReferenceObjectByHandle
0x1400185d8  nop     dword ptr [rax+rax+00h]
0x1400185dd  mov     ebx, eax
0x1400185df  mov     [rsp+108h+var_B8], eax
0x1400185e3  test    eax, eax
0x1400185e5  js      short loc_14001861E
0x1400185e7  mov     r9, r12
0x1400185ea  mov     r8d, [rsp+108h+var_A4]
0x1400185ef  mov     rdx, r15
0x1400185f2  mov     rcx, [rsp+108h+Object]; Object
0x1400185f7  call    TmRegisterProtocolAddressInformation
0x1400185fc  mov     ebx, eax
0x1400185fe  mov     [rsp+108h+var_B8], eax
0x140018602  mov     rcx, [rsp+108h+Object]; Object
0x140018607  call    cs:__imp_ObfDereferenceObject
0x14001860e  nop     dword ptr [rax+rax+00h]
0x140018613  jmp     short loc_14001861E
0x140018615  mov     ebx, 0C00000BBh
0x14001861a  mov     [rsp+108h+var_B8], ebx
0x14001861e  test    ebx, ebx
0x140018620  jns     short loc_140018638
0x140018622  test    rsi, rsi
0x140018625  jz      short loc_140018638
0x140018627  xor     edx, edx; Tag
0x140018629  mov     rcx, rsi; P
0x14001862c  call    cs:__imp_ExFreePoolWithTag
0x140018633  nop     dword ptr [rax+rax+00h]
0x140018638  mov     eax, ebx
0x14001863a  mov     rcx, [rsp+108h+var_40]
0x140018642  xor     rcx, rsp; StackCookie
0x140018645  call    __security_check_cookie
0x14001864a  add     rsp, 0D8h
0x140018651  pop     r15
0x140018653  pop     r14
0x140018655  pop     r13
0x140018657  pop     r12
0x140018659  pop     rsi
0x14001865a  pop     rbx
0x14001865b  retn
0x1400229ff  push    rbp
0x140022a01  sub     rsp, 50h
0x140022a05  mov     rbp, rdx
0x140022a08  mov     dword ptr [rbp+5Ch], 1
0x140022a0f  mov     eax, [rbp+5Ch]
0x140022a12  add     rsp, 50h
0x140022a16  pop     rbp
0x140022a17  retn
0x140022a19  push    rbp
0x140022a1b  sub     rsp, 50h
0x140022a1f  mov     rbp, rdx
0x140022a22  cmp     dword ptr [rbp+50h], 0
0x140022a26  jge     short loc_140022A40
0x140022a28  mov     rcx, [rbp+70h]; P
0x140022a2c  test    rcx, rcx
0x140022a2f  jz      short loc_140022A40
0x140022a31  xor     edx, edx; Tag
0x140022a33  call    cs:__imp_ExFreePoolWithTag
0x140022a3a  nop     dword ptr [rax+rax+00h]
0x140022a3f  nop
0x140022a40  add     rsp, 50h
0x140022a44  pop     rbp
0x140022a45  retn
```
