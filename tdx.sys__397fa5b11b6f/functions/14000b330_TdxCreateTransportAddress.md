# TdxCreateTransportAddress

- ea: `0x14000b330`
- end: `0x14000baa5`
- name: `TdxCreateTransportAddress`
- size: `1909`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009290`

## callees

- `0x1400036b0`
- `0x1400054ec`
- `0x14000b330`
- `0x14000bab0`
- `0x14000ca98`
- `0x140012b5c`
- `0x140012b8c`
- `0x140018600`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000b41e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000b441`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000b41e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000b441`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000b404`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000b500`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000b404`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000b500`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000b735`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000b9c8`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000b735`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000b9c8`
- `ntoskrnl!ExAllocatePool2` at `0x14000b3d3`
- `ntoskrnl!ExAllocatePool2` at `0x14000b3d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b894`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b894`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba94`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000b87f`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000b87f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000b858`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14000b858`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b81c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b81c`
- `ntoskrnl!SeAssignSecurity` at `0x14000b847`
- `ntoskrnl!SeAssignSecurity` at `0x14000b847`
- `ntoskrnl!SeLockSubjectContext` at `0x14000b80c`
- `ntoskrnl!SeLockSubjectContext` at `0x14000b80c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b518`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b542`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b678`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b518`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b542`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b678`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000b58b`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000b6cc`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000b58b`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000b6cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b616`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b6f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b616`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b6f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba19`

## pseudocode

```c
__int64 __fastcall TdxCreateTransportAddress(
        KSPIN_LOCK a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        KSPIN_LOCK **a7)
{
  __int16 v9; // ax
  __int64 v10; // r13
  KSPIN_LOCK *Pool2; // rax
  KSPIN_LOCK *v12; // rbx
  KSPIN_LOCK *v13; // r14
  PIRP TopLevelIrp; // rax
  int v15; // ecx
  PIRP v16; // rax
  int v17; // edx
  int v18; // ecx
  unsigned int v19; // edx
  _QWORD *v20; // rax
  int v21; // eax
  _WORD *v22; // rdx
  size_t v23; // r8
  KIRQL v24; // al
  int v25; // edx
  KIRQL v26; // al
  int v27; // ecx
  KIRQL v28; // di
  __int64 v29; // rdx
  KSPIN_LOCK v30; // rdx
  bool v31; // zf
  KSPIN_LOCK v32; // r15
  KSPIN_LOCK **v33; // rax
  KIRQL v34; // dl
  KSPIN_LOCK *v35; // rcx
  int v36; // esi
  KIRQL v37; // di
  int v38; // ecx
  KSPIN_LOCK *v39; // rdx
  __int16 v41; // ax
  __int64 v42; // r9
  unsigned int v43; // r10d
  SCOPE_LEVEL v44; // r11d
  struct _SECURITY_SUBJECT_CONTEXT *v45; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rdi
  PACCESS_TOKEN ClientToken; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v49; // ebx
  PVOID CallersAddress; // [rsp+40h] [rbp-48h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+48h] [rbp-40h] BYREF
  __int64 v53; // [rsp+A0h] [rbp+18h] BYREF
  KIRQL v54; // [rsp+A8h] [rbp+20h]

  v53 = 0;
  if ( !*(_DWORD *)a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids);
    }
    return 3221225991LL;
  }
  v9 = *(_WORD *)(a3 + 6);
  if ( v9 == 2 )
  {
    if ( (unsigned __int16)(*(_WORD *)(a3 + 4) - 14) <= 0x70u && a4 >= 0x12 )
      goto LABEL_5;
    goto LABEL_47;
  }
  if ( v9 != 23 )
    return 3221225793LL;
  if ( (unsigned __int16)(*(_WORD *)(a3 + 4) - 26) > 0x64u || a4 < 0x1E )
  {
LABEL_47:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids);
    }
    return 3221225793LL;
  }
LABEL_5:
  v10 = a5;
  if ( *(_WORD *)(a5 + 26) || *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a5 + 8) + 8LL) + 64LL) )
  {
    v45 = *(struct _SECURITY_SUBJECT_CONTEXT **)(*(_QWORD *)(a5 + 8) + 8LL);
    CallersAddress = 0;
    SubjectContext = v45 + 1;
    SeLockSubjectContext(v45 + 1);
    ClientToken = v45[2].ClientToken;
    GenericMapping = IoGetFileObjectGenericMapping();
    v49 = SeAssignSecurity(0, ClientToken, &CallersAddress, 0, SubjectContext, GenericMapping, PagedPool);
    SeUnlockSubjectContext(SubjectContext);
    if ( v49 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids);
      }
    }
    else
    {
      v49 = ObLogSecurityDescriptor(CallersAddress, &v53, 1);
      ExFreePoolWithTag(CallersAddress, 0);
      if ( v49 >= 0 )
        goto LABEL_8;
    }
    return (unsigned int)v49;
  }
  v53 = 0;
LABEL_8:
  Pool2 = (KSPIN_LOCK *)ExAllocatePool2(64, 824, 1098409044);
  v12 = Pool2;
  if ( Pool2 )
  {
    v13 = Pool2 + 3;
    Pool2[4] = (KSPIN_LOCK)(Pool2 + 3);
    Pool2[3] = (KSPIN_LOCK)(Pool2 + 3);
    KeInitializeSpinLock(Pool2 + 1);
    *((_DWORD *)v12 + 4) = 1;
    *((_DWORD *)v12 + 1) = 1;
    TopLevelIrp = IoGetTopLevelIrp();
    v15 = 0;
    if ( TopLevelIrp == (PIRP)5 )
      v15 = 32;
    *(_DWORD *)v12 = v15 | *(_DWORD *)v12 & 0xFFFFFFDF;
    v16 = IoGetTopLevelIrp();
    v17 = *(_DWORD *)v12;
    v18 = 0;
    v12[63] = 0;
    v12[64] = 0;
    if ( v16 == (PIRP)6 )
      v18 = 64;
    v19 = v18 | v17 & 0xFFFFFFBF;
    *(_DWORD *)v12 = v19;
    if ( (unsigned __int16)(*(_WORD *)(a1 + 36) - 2) > 1u )
    {
      *(_DWORD *)v12 = v19 & 0xFFFFFFFD;
      v12[48] = (KSPIN_LOCK)(v12 + 47);
      v12[47] = (KSPIN_LOCK)(v12 + 47);
      v12[46] = (KSPIN_LOCK)(v12 + 45);
      v12[45] = (KSPIN_LOCK)(v12 + 45);
      v20 = v12 + 43;
    }
    else
    {
      v20 = v12 + 42;
      *(_DWORD *)v12 = v19 | 2;
    }
    *v20 = v20;
    v20[1] = v20;
    v12[66] = (KSPIN_LOCK)(v12 + 65);
    v12[65] = (KSPIN_LOCK)(v12 + 65);
    memmove(v12 + 7, (const void *)a3, *(unsigned __int16 *)(a3 + 4) + 8LL);
    v21 = *(_DWORD *)v12;
    *((_DWORD *)v12 + 14) = 1;
    v22 = (_WORD *)(a3 + 6);
    if ( (v21 & 0x40) != 0 && *v22 == 2 )
    {
      v41 = *(_WORD *)(a3 + 8);
      *((_WORD *)v12 + 96) = 23;
      *((_WORD *)v12 + 97) = v41;
      *((_DWORD *)v12 + 49) = 0;
      *(IN6_ADDR *)(v12 + 25) = in6addr_v4mappedprefix;
      *((_BYTE *)v12 + 212) = *(_BYTE *)(a3 + 10);
      *((_BYTE *)v12 + 213) = *(_BYTE *)(a3 + 11);
      *((_BYTE *)v12 + 214) = *(_BYTE *)(a3 + 12);
      *((_BYTE *)v12 + 215) = *(_BYTE *)(a3 + 13);
      *((SCOPE_ID *)v12 + 54) = scopeid_unspecified;
      v44 = Ipv4AddressScope((const UCHAR *)(a3 + 10));
      if ( v44 == ScopeLevelGlobal || *(_BYTE *)(a3 + 10) == 127 )
      {
        *(_DWORD *)(v42 + 24) = 0;
        v43 = 0;
      }
      if ( v43 >> 28 == v44 )
        *(_DWORD *)(v42 + 24) = v43 & 0xFFFFFFF;
    }
    else
    {
      v23 = 16;
      if ( *v22 != 2 )
        v23 = 28;
      memmove(v12 + 24, v22, v23);
    }
    if ( (*(_BYTE *)(v10 + 26) & 3) != 0 )
      *(_DWORD *)v12 |= 8u;
    KeInitializeSpinLock(v12 + 69);
    SpinLock = (PKSPIN_LOCK)(a1 + 16);
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
    v25 = *(_DWORD *)(a1 + 168);
    v54 = v24;
    if ( (v25 & 1) != 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v24);
      DbgTdxDereferenceTransportAddress(v12, "minio\\netio\\session\\tdi\\address.c", 1019);
      v36 = -1073741811;
LABEL_28:
      if ( v53 )
        ObDereferenceSecurityDescriptor(v53, 1);
      return (unsigned int)v36;
    }
    v26 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 216));
    v27 = *(_DWORD *)(a1 + 24);
    v28 = v26;
    v29 = *(unsigned int *)(a1 + 1184) + 7LL;
    CallersAddress = 0;
    v30 = a1 + 32 * v29;
    *(_DWORD *)(v30 + 24) = v27 + 1;
    *(_QWORD *)v30 = "minio\\netio\\session\\tdi\\transport.c";
    *(_DWORD *)(v30 + 8) = 228;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v30 + 16));
    *(_DWORD *)(a1 + 1184) = (*(_DWORD *)(a1 + 1184) + 1) % 0x1Eu;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 216), v28);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
    _InterlockedIncrement((volatile signed __int32 *)v12 + 4);
    v31 = *((_DWORD *)v12 + 1) == 1;
    v12[5] = a1;
    if ( v31 )
    {
      v32 = a1 + 176;
      v33 = *(KSPIN_LOCK ***)(v32 + 8);
      if ( *v33 == (KSPIN_LOCK *)v32 )
        goto LABEL_24;
    }
    else
    {
      v32 = a1 + 192;
      v33 = *(KSPIN_LOCK ***)(v32 + 8);
      if ( *v33 == (KSPIN_LOCK *)v32 )
      {
LABEL_24:
        v34 = v54;
        v35 = SpinLock;
        *v13 = v32;
        v13[1] = (KSPIN_LOCK)v33;
        *v33 = v13;
        *(_QWORD *)(v32 + 8) = v13;
        KeReleaseSpinLock(v35, v34);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, v12);
        }
        v36 = TdxActivateTransportAddress((_DWORD)v12, a6, (unsigned int)*(_QWORD *)(v10 + 48) + 88, a3, v53);
        if ( v36 < 0 )
        {
          TdxDetachObjectFromTransport(v12[5], v12);
          DbgTdxDereferenceTransportAddress(v12, "minio\\netio\\session\\tdi\\address.c", 1037);
          ExFreePoolWithTag(v12, 0);
        }
        else
        {
          v37 = KeAcquireSpinLockRaiseToDpc(v12 + 69);
          v38 = *((_DWORD *)v12 + 4) + 1;
          v39 = &v12[4 * *((unsigned int *)v12 + 204)];
          SpinLock = 0;
          *((_DWORD *)v39 + 146) = v38;
          v39[70] = (KSPIN_LOCK)"minio\\netio\\session\\tdi\\address.c";
          *((_DWORD *)v39 + 142) = 1040;
          RtlGetCallersAddress((PVOID *)&SpinLock, (PVOID *)v39 + 72);
          *((_DWORD *)v12 + 204) = ((unsigned __int8)*((_DWORD *)v12 + 204) + 1) & 7;
          KeReleaseSpinLock(v12 + 69, v37);
          _InterlockedIncrement((volatile signed __int32 *)v12 + 4);
          *(_QWORD *)(a2 + 24) = v12;
          *(_QWORD *)(a2 + 32) = 1;
          *a7 = v12;
        }
        goto LABEL_28;
      }
    }
    __fastfail(3u);
  }
  if ( v53 )
    ObDereferenceSecurityDescriptor(v53, 1);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14000b330  mov     [rsp+arg_8], rdx
0x14000b335  push    rbp
0x14000b336  push    rsi
0x14000b337  push    r15
0x14000b339  sub     rsp, 70h
0x14000b33d  xor     esi, esi
0x14000b33f  mov     rbp, r8
0x14000b342  mov     r15, rcx
0x14000b345  mov     [rsp+88h+arg_10], rsi
0x14000b34d  cmp     [r8], esi
0x14000b350  jz      loc_14000B937
0x14000b356  movzx   eax, word ptr [r8+6]
0x14000b35b  cmp     ax, 2
0x14000b35f  jnz     loc_14000B8D7
0x14000b365  movzx   eax, word ptr [r8+4]
0x14000b36a  sub     ax, 0Eh
0x14000b36e  cmp     ax, 70h ; 'p'
0x14000b372  ja      loc_14000B8F6
0x14000b378  cmp     r9d, 12h
0x14000b37c  jb      loc_14000B8F6
0x14000b382  mov     [rsp+88h+arg_0], rbx
0x14000b38a  mov     [rsp+88h+var_20], rdi
0x14000b38f  mov     [rsp+88h+var_30], r13
0x14000b394  mov     r13, [rsp+88h+arg_20]
0x14000b39c  cmp     [r13+1Ah], si
0x14000b3a1  jnz     loc_14000B7F8
0x14000b3a7  mov     rax, [r13+8]
0x14000b3ab  mov     rcx, [rax+8]
0x14000b3af  cmp     [rcx+40h], rsi
0x14000b3b3  jnz     loc_14000B7F8
0x14000b3b9  mov     [rsp+88h+arg_10], rsi
0x14000b3c1  mov     edi, 40h ; '@'
0x14000b3c6  mov     edx, 338h
0x14000b3cb  mov     ecx, edi
0x14000b3cd  mov     r8d, 41786454h
0x14000b3d3  call    cs:__imp_ExAllocatePool2
0x14000b3da  nop     dword ptr [rax+rax+00h]
0x14000b3df  mov     rbx, rax
0x14000b3e2  test    rax, rax
0x14000b3e5  jz      loc_14000B9B6
0x14000b3eb  mov     [rsp+88h+var_28], r12
0x14000b3f0  lea     rcx, [rax+8]; SpinLock
0x14000b3f4  mov     [rsp+88h+var_38], r14
0x14000b3f9  lea     r14, [rax+18h]
0x14000b3fd  mov     [r14+8], r14
0x14000b401  mov     [r14], r14
0x14000b404  call    cs:__imp_KeInitializeSpinLock
0x14000b40b  nop     dword ptr [rax+rax+00h]
0x14000b410  mov     dword ptr [rbx+10h], 1
0x14000b417  mov     dword ptr [rbx+4], 1
0x14000b41e  call    cs:__imp_IoGetTopLevelIrp
0x14000b425  nop     dword ptr [rax+rax+00h]
0x14000b42a  mov     ecx, esi
0x14000b42c  mov     edx, 20h ; ' '
0x14000b431  cmp     rax, 5
0x14000b435  mov     eax, [rbx]
0x14000b437  cmovz   ecx, edx
0x14000b43a  and     eax, 0FFFFFFDFh
0x14000b43d  or      eax, ecx
0x14000b43f  mov     [rbx], eax
0x14000b441  call    cs:__imp_IoGetTopLevelIrp
0x14000b448  nop     dword ptr [rax+rax+00h]
0x14000b44d  mov     edx, [rbx]
0x14000b44f  mov     ecx, esi
0x14000b451  cmp     rax, 6
0x14000b455  mov     [rbx+1F8h], rsi
0x14000b45c  mov     [rbx+200h], rsi
0x14000b463  cmovz   ecx, edi
0x14000b466  and     edx, 0FFFFFFBFh
0x14000b469  or      edx, ecx
0x14000b46b  mov     [rbx], edx
0x14000b46d  movzx   eax, word ptr [r15+24h]
0x14000b472  sub     ax, 2
0x14000b476  cmp     ax, 1
0x14000b47a  ja      loc_14000B9DE
0x14000b480  or      edx, 2
0x14000b483  lea     rax, [rbx+150h]
0x14000b48a  mov     [rbx], edx
0x14000b48c  mov     [rax], rax
0x14000b48f  lea     rcx, [rbx+38h]; void *
0x14000b493  mov     [rax+8], rax
0x14000b497  mov     rdx, rbp; Src
0x14000b49a  lea     rax, [rbx+208h]
0x14000b4a1  mov     [rax+8], rax
0x14000b4a5  mov     [rax], rax
0x14000b4a8  movzx   r8d, word ptr [rbp+4]
0x14000b4ad  add     r8, 8; Size
0x14000b4b1  call    memmove
0x14000b4b6  mov     eax, [rbx]
0x14000b4b8  lea     r9, [rbx+0C0h]
0x14000b4bf  mov     dword ptr [rbx+38h], 1
0x14000b4c6  lea     rdx, [rbp+6]; Src
0x14000b4ca  test    dil, al
0x14000b4cd  jnz     loc_14000B769
0x14000b4d3  cmp     word ptr [rdx], 2
0x14000b4d7  mov     eax, 1Ch
0x14000b4dc  mov     r8d, 10h
0x14000b4e2  mov     rcx, r9; void *
0x14000b4e5  cmovnz  r8d, eax; Size
0x14000b4e9  call    memmove
0x14000b4ee  test    byte ptr [r13+1Ah], 3
0x14000b4f3  jnz     loc_14000BA0B
0x14000b4f9  lea     rcx, [rbx+228h]; SpinLock
0x14000b500  call    cs:__imp_KeInitializeSpinLock
0x14000b507  nop     dword ptr [rax+rax+00h]
0x14000b50c  lea     rdi, [r15+10h]
0x14000b510  mov     rcx, rdi; SpinLock
0x14000b513  mov     [rsp+88h+SpinLock], rdi
0x14000b518  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b51f  nop     dword ptr [rax+rax+00h]
0x14000b524  mov     edx, [r15+0A8h]
0x14000b52b  mov     [rsp+88h+arg_18], al
0x14000b532  test    dl, 1
0x14000b535  jnz     loc_14000BA13
0x14000b53b  lea     rcx, [r15+0D8h]; SpinLock
0x14000b542  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b549  nop     dword ptr [rax+rax+00h]
0x14000b54e  mov     ecx, [r15+18h]
0x14000b552  movzx   edi, al
0x14000b555  mov     edx, [r15+4A0h]
0x14000b55c  lea     rax, aMinioNetioSess_4; "minio\\netio\\session\\tdi\\transport.c"
0x14000b563  add     rdx, 7
0x14000b567  mov     [rsp+88h+CallersAddress], rsi
0x14000b56c  shl     rdx, 5
0x14000b570  add     rdx, r15
0x14000b573  inc     ecx
0x14000b575  mov     [rdx+18h], ecx
0x14000b578  lea     rcx, [rsp+88h+CallersAddress]; CallersAddress
0x14000b57d  mov     [rdx], rax
0x14000b580  mov     dword ptr [rdx+8], 0E4h
0x14000b587  add     rdx, 10h; CallersCaller
0x14000b58b  call    cs:__imp_RtlGetCallersAddress
0x14000b592  nop     dword ptr [rax+rax+00h]
0x14000b597  mov     r8d, [r15+4A0h]
0x14000b59e  lea     rcx, [r15+0D8h]; SpinLock
0x14000b5a5  inc     r8d
0x14000b5a8  mov     eax, 88888889h
0x14000b5ad  mul     r8d
0x14000b5b0  shr     edx, 4
0x14000b5b3  imul    eax, edx, 1Eh
0x14000b5b6  movzx   edx, dil; NewIrql
0x14000b5ba  sub     r8d, eax
0x14000b5bd  mov     [r15+4A0h], r8d
0x14000b5c4  call    cs:__imp_KeReleaseSpinLock
0x14000b5cb  nop     dword ptr [rax+rax+00h]
0x14000b5d0  lock inc dword ptr [r15+18h]
0x14000b5d5  lock inc dword ptr [rbx+10h]
0x14000b5d9  cmp     dword ptr [rbx+4], 1
0x14000b5dd  mov     [rbx+28h], r15
0x14000b5e1  jnz     loc_14000B8AD
0x14000b5e7  add     r15, 0B0h
0x14000b5ee  mov     rax, [r15+8]
0x14000b5f2  cmp     [rax], r15
0x14000b5f5  jnz     loc_14000B8C1
0x14000b5fb  movzx   edx, [rsp+88h+arg_18]; NewIrql
0x14000b603  mov     rcx, [rsp+88h+SpinLock]; SpinLock
0x14000b608  mov     [r14], r15
0x14000b60b  mov     [r14+8], rax
0x14000b60f  mov     [rax], r14
0x14000b612  mov     [r15+8], r14
0x14000b616  call    cs:__imp_KeReleaseSpinLock
0x14000b61d  nop     dword ptr [rax+rax+00h]
0x14000b622  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b629  lea     rax, WPP_GLOBAL_Control
0x14000b630  cmp     rcx, rax
0x14000b633  jz      short loc_14000B63F
0x14000b635  cmp     byte ptr [rcx+29h], 5
0x14000b639  jnb     loc_14000BA44
0x14000b63f  mov     r8, [r13+30h]
0x14000b643  mov     r9, rbp
0x14000b646  mov     rax, [rsp+88h+arg_10]
0x14000b64e  add     r8, 58h ; 'X'
0x14000b652  mov     rdx, [rsp+88h+arg_28]
0x14000b65a  mov     rcx, rbx
0x14000b65d  mov     [rsp+88h+SubjectContext], rax
0x14000b662  call    TdxActivateTransportAddress
0x14000b667  mov     esi, eax
0x14000b669  test    eax, eax
0x14000b66b  js      loc_14000BA6E
0x14000b671  lea     rcx, [rbx+228h]; SpinLock
0x14000b678  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b67f  nop     dword ptr [rax+rax+00h]
0x14000b684  mov     ecx, [rbx+10h]
0x14000b687  movzx   edi, al
0x14000b68a  mov     edx, [rbx+330h]
0x14000b690  lea     rax, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000b697  shl     rdx, 5
0x14000b69b  inc     ecx
0x14000b69d  add     rdx, rbx
0x14000b6a0  mov     [rsp+88h+SpinLock], 0
0x14000b6a9  mov     [rdx+248h], ecx
0x14000b6af  lea     rcx, [rsp+88h+SpinLock]; CallersAddress
0x14000b6b4  mov     [rdx+230h], rax
0x14000b6bb  mov     dword ptr [rdx+238h], 410h
0x14000b6c5  add     rdx, 240h; CallersCaller
0x14000b6cc  call    cs:__imp_RtlGetCallersAddress
0x14000b6d3  nop     dword ptr [rax+rax+00h]
0x14000b6d8  mov     eax, [rbx+330h]
0x14000b6de  lea     rcx, [rbx+228h]; SpinLock
0x14000b6e5  inc     eax
0x14000b6e7  movzx   edx, dil; NewIrql
0x14000b6eb  and     eax, 7
0x14000b6ee  mov     [rbx+330h], eax
0x14000b6f4  call    cs:__imp_KeReleaseSpinLock
0x14000b6fb  nop     dword ptr [rax+rax+00h]
0x14000b700  lock inc dword ptr [rbx+10h]
0x14000b704  mov     rax, [rsp+88h+arg_8]
0x14000b70c  mov     [rax+18h], rbx
0x14000b710  mov     qword ptr [rax+20h], 1
0x14000b718  mov     rax, [rsp+88h+arg_30]
0x14000b720  mov     [rax], rbx
0x14000b723  mov     rcx, [rsp+88h+arg_10]
0x14000b72b  test    rcx, rcx
0x14000b72e  jz      short loc_14000B741
0x14000b730  mov     edx, 1
0x14000b735  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000b73c  nop     dword ptr [rax+rax+00h]
0x14000b741  mov     r12, [rsp+88h+var_28]
0x14000b746  mov     eax, esi
0x14000b748  mov     r14, [rsp+88h+var_38]
0x14000b74d  mov     rdi, [rsp+88h+var_20]
0x14000b752  mov     rbx, [rsp+88h+arg_0]
0x14000b75a  mov     r13, [rsp+88h+var_30]
0x14000b75f  add     rsp, 70h
0x14000b763  pop     r15
0x14000b765  pop     rsi
0x14000b766  pop     rbp
0x14000b767  retn
0x14000b769  cmp     word ptr [rdx], 2
0x14000b76d  jnz     loc_14000B4D3
0x14000b773  movzx   eax, word ptr [rbp+8]
0x14000b777  lea     rcx, [rbp+0Ah]; Address
0x14000b77b  movups  xmm0, xmmword ptr cs:in6addr_v4mappedprefix.u
0x14000b782  mov     r10d, dword ptr cs:scopeid_unspecified
0x14000b789  mov     word ptr [r9], 17h
0x14000b78f  mov     [r9+2], ax
0x14000b794  mov     [r9+4], esi
0x14000b798  movups  xmmword ptr [r9+8], xmm0
0x14000b79d  movzx   eax, byte ptr [rbp+0Ah]
0x14000b7a1  mov     [r9+14h], al
0x14000b7a5  movzx   eax, byte ptr [rbp+0Bh]
0x14000b7a9  mov     [r9+15h], al
0x14000b7ad  movzx   eax, byte ptr [rbp+0Ch]
0x14000b7b1  mov     [r9+16h], al
0x14000b7b5  movzx   eax, byte ptr [rbp+0Dh]
0x14000b7b9  mov     [r9+17h], al
0x14000b7bd  mov     [r9+18h], r10d
0x14000b7c1  call    Ipv4AddressScope
0x14000b7c6  mov     r11d, eax
0x14000b7c9  cmp     eax, 0Eh
0x14000b7cc  jnz     loc_14000B8C8
0x14000b7d2  mov     [r9+18h], esi
0x14000b7d6  mov     r10d, esi
0x14000b7d9  mov     eax, r10d
0x14000b7dc  shr     eax, 1Ch
0x14000b7df  cmp     eax, r11d
0x14000b7e2  jnz     loc_14000B4EE
0x14000b7e8  and     r10d, 0FFFFFFFh
0x14000b7ef  mov     [r9+18h], r10d
0x14000b7f3  jmp     loc_14000B4EE
0x14000b7f8  mov     rax, [r13+8]
0x14000b7fc  mov     rbx, [rax+8]
0x14000b800  mov     [rsp+88h+CallersAddress], rsi
0x14000b805  lea     rdi, [rbx+20h]
0x14000b809  mov     rcx, rdi; SubjectContext
0x14000b80c  call    cs:__imp_SeLockSubjectContext
0x14000b813  nop     dword ptr [rax+rax+00h]
0x14000b818  mov     rbx, [rbx+40h]
0x14000b81c  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000b823  nop     dword ptr [rax+rax+00h]
0x14000b828  mov     [rsp+88h+PoolType], 1; PoolType
0x14000b830  lea     r8, [rsp+88h+CallersAddress]; NewDescriptor
0x14000b835  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x14000b83a  xor     r9d, r9d; IsDirectoryObject
0x14000b83d  mov     rdx, rbx; ExplicitDescriptor
0x14000b840  mov     [rsp+88h+SubjectContext], rdi; SubjectContext
0x14000b845  xor     ecx, ecx; ParentDescriptor
0x14000b847  call    cs:__imp_SeAssignSecurity
0x14000b84e  nop     dword ptr [rax+rax+00h]
0x14000b853  mov     rcx, rdi; SubjectContext
0x14000b856  mov     ebx, eax
0x14000b858  call    cs:__imp_SeUnlockSubjectContext
0x14000b85f  nop     dword ptr [rax+rax+00h]
0x14000b864  test    ebx, ebx
0x14000b866  js      loc_14000B978
0x14000b86c  mov     rcx, [rsp+88h+CallersAddress]
0x14000b871  lea     rdx, [rsp+88h+arg_10]
0x14000b879  mov     r8d, 1
0x14000b87f  call    cs:__imp_ObLogSecurityDescriptor
0x14000b886  nop     dword ptr [rax+rax+00h]
0x14000b88b  mov     rcx, [rsp+88h+CallersAddress]; P
0x14000b890  xor     edx, edx; Tag
0x14000b892  mov     ebx, eax
0x14000b894  call    cs:__imp_ExFreePoolWithTag
0x14000b89b  nop     dword ptr [rax+rax+00h]
0x14000b8a0  test    ebx, ebx
0x14000b8a2  jns     loc_14000B3C1
0x14000b8a8  jmp     loc_14000B9AF
0x14000b8ad  add     r15, 0C0h
0x14000b8b4  mov     rax, [r15+8]
  ... truncated ...
```
