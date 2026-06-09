# Smb2AddShare

- ea: `0x140062f00`
- end: `0x140063701`
- name: `Smb2AddShare`
- size: `2049`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140059540`

## callees

- `0x14000c450`
- `0x1400280ac`
- `0x140028708`
- `0x140029014`
- `0x140038680`
- `0x140038980`
- `0x140062f00`
- `0x140065e80`
- `0x140076fd0`

## import_xrefs

- `ntoskrnl!PcwCreateInstance` at `0x1400635d8`
- `ntoskrnl!PcwCreateInstance` at `0x1400635d8`
- `ntoskrnl!ExAllocatePool2` at `0x140062fb1`
- `ntoskrnl!ExAllocatePool2` at `0x1400630c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400631ee`
- `ntoskrnl!ExAllocatePool2` at `0x14006325b`
- `ntoskrnl!ExAllocatePool2` at `0x140062fb1`
- `ntoskrnl!ExAllocatePool2` at `0x1400630c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400631ee`
- `ntoskrnl!ExAllocatePool2` at `0x14006325b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063034`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063047`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063034`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063047`
- `ntoskrnl!ExReleaseResourceLite` at `0x140063515`
- `ntoskrnl!ExReleaseResourceLite` at `0x140063515`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400634ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400634ad`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006311b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140063131`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006311b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140063131`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063012`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006306c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063012`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006306c`
- `ntoskrnl!EtwActivityIdControl` at `0x140063446`
- `ntoskrnl!EtwActivityIdControl` at `0x140063446`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400631af`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400631af`
- `ntoskrnl!RtlHashUnicodeString` at `0x140063424`
- `ntoskrnl!RtlHashUnicodeString` at `0x140063424`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140062f92`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140063242`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006327e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400633b2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140062f92`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140063242`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006327e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400633b2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400635f1`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400635f1`
- `srvnet!SrvLibGetBinary` at `0x140063583`
- `srvnet!SrvLibGetBinary` at `0x140063583`
- `ksecdd!BCryptGenRandom` at `0x140063463`
- `ksecdd!BCryptGenRandom` at `0x140063463`

## string_xrefs

- `0x14006357c`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 __fastcall Smb2AddShare(__int64 a1)
{
  NTSTATUS ShareQoSFlowID; // ebx
  int v3; // r14d
  _QWORD *Instance; // rbp
  __int16 *v5; // r15
  unsigned __int16 *v6; // r13
  _WORD *v7; // r12
  int v8; // ebx
  ULONG v9; // eax
  __int64 Pool2; // rax
  PVOID *v11; // rdi
  PVOID v12; // rcx
  PVOID v13; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rax
  struct _EX_RUNDOWN_REF *v17; // rcx
  bool v18; // zf
  void *v19; // rax
  __int16 v20; // ax
  void *v21; // rcx
  ULONG v22; // eax
  __int64 v23; // rax
  ULONG v24; // eax
  __int16 v25; // cx
  __int64 i; // rcx
  __int16 v27; // ax
  __int64 v28; // rax
  char *v29; // rbx
  char *v30; // rbx
  __int16 v31; // ax
  char *v32; // rbx
  __int16 v33; // ax
  void *v34; // rbx
  ULONG v35; // eax
  char v36; // si
  __int64 v37; // r8
  _QWORD *v38; // rdx
  const void *v39; // rax
  ULONG TimeIncrement; // eax
  int v41; // r8d
  struct _PCW_DATA Data; // [rsp+70h] [rbp-48h] BYREF
  ULONG HashValue; // [rsp+C0h] [rbp+8h] BYREF
  int v44; // [rsp+C8h] [rbp+10h] BYREF

  HashValue = 0;
  if ( (*(_DWORD *)(a1 + 128) & 0x21000) == 0x21000 )
    return (unsigned int)-1073741811;
  v3 = (unsigned __int8)*(_DWORD *)(a1 + 124);
  if ( v3 == 2 )
    return (unsigned int)-1073741637;
  Instance = (_QWORD *)Srv2GetInstance(*(unsigned int *)(a1 + 152));
  if ( !Instance )
    return (unsigned int)-1073741811;
  v5 = (__int16 *)(a1 + 24);
  v6 = (unsigned __int16 *)(a1 + 56);
  v7 = (_WORD *)(a1 + 8);
  v8 = *(unsigned __int16 *)(a1 + 8)
     + *(unsigned __int16 *)(a1 + 56)
     + *(unsigned __int16 *)(a1 + 72)
     + *(unsigned __int16 *)(a1 + 24);
  v9 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 184));
  Pool2 = ExAllocatePool2(256, v9 + v8 + 454, 1748128588);
  v11 = (PVOID *)Pool2;
  if ( !Pool2 )
    goto LABEL_7;
  *(_QWORD *)(Pool2 + 408) = Instance;
  v15 = (_QWORD *)(Pool2 + 336);
  v15[1] = v15;
  *v15 = v15;
  v11[27] = v11 + 26;
  v11[26] = v11 + 26;
  v16 = ExAllocatePool2(64, 656, 1748128588);
  *v11 = (PVOID)v16;
  if ( !v16 )
    goto LABEL_7;
  *(_QWORD *)v16 = 1;
  *(_WORD *)(v16 + 16) = 656;
  *(_DWORD *)(v16 + 8) = 12;
  *(_DWORD *)(v16 + 12) = 220;
  *(_QWORD *)(v16 + 48) = 0;
  *(_QWORD *)(v16 + 56) = v16;
  *(_QWORD *)(v16 + 64) = Instance;
  *(_DWORD *)(v16 + 72) = 0;
  *((_QWORD *)*v11 + 11) = v11;
  ExInitializeResourceLite((PERESOURCE)((char *)*v11 + 96));
  ExInitializeResourceLite((PERESOURCE)((char *)*v11 + 200));
  v17 = (struct _EX_RUNDOWN_REF *)((char *)*v11 + 304);
  *((_BYTE *)v11 + 278) = (*(_DWORD *)(a1 + 124) & 0x100000) != 0;
  *((_DWORD *)v11 + 89) = *(_DWORD *)a1;
  *((_DWORD *)v11 + 73) = *(_DWORD *)(a1 + 128) & 0x30;
  *((_DWORD *)v11 + 72) = *(_DWORD *)(a1 + 128) & 0xFFFFFFCF;
  *((_DWORD *)v11 + 92) = *(_DWORD *)(a1 + 148);
  *((_DWORD *)v11 + 74) = *(_DWORD *)(a1 + 140);
  *((_DWORD *)v11 + 75) = *(_DWORD *)(a1 + 144);
  *((_DWORD *)v11 + 76) = 1;
  *((_BYTE *)v11 + 281) = 0;
  ExInitializeRundownProtection(v17);
  v18 = ((_DWORD)v11[46] & 0xE000000) == 0;
  Smb2BypassCSVFileOpenRundownInitialized = 1;
  if ( !v18 )
    Smb2IsRkfInstalled = 1;
  if ( *(_WORD *)(a1 + 200) )
  {
    v19 = (void *)ExAllocatePool2(258, *(unsigned __int16 *)(a1 + 200), 1748128588);
    v11[24] = v19;
    if ( !v19 )
      goto LABEL_7;
    memmove(v19, *(const void **)(a1 + 208), *(unsigned __int16 *)(a1 + 200));
    v20 = *(_WORD *)(a1 + 200);
    *((_WORD *)v11 + 93) = v20;
    *((_WORD *)v11 + 92) = v20;
  }
  v21 = *(void **)(a1 + 192);
  if ( v21 )
  {
    v22 = RtlLengthSecurityDescriptor(v21);
    v23 = ExAllocatePool2(258, v22, 1748128588);
    v11[33] = (PVOID)v23;
    if ( v23 )
    {
      v24 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 192));
      memmove(v11[33], *(const void **)(a1 + 192), v24);
      goto LABEL_26;
    }
LABEL_7:
    ShareQoSFlowID = -1073741670;
    goto LABEL_8;
  }
LABEL_26:
  *((_DWORD *)v11 + 68) = 1;
  v11[14] = v11 + 55;
  v25 = *v7 + *v5 + 6;
  *((_WORD *)v11 + 53) = v25;
  *((_WORD *)v11 + 52) = v25;
  for ( i = 0; i != 2; ++i )
    *((_WORD *)v11[14] + i) = 92;
  v27 = *v5;
  *((_WORD *)v11 + 45) = *v5;
  *((_WORD *)v11 + 44) = v27;
  v11[12] = (char *)v11 + 444;
  memmove((char *)v11 + 444, *(const void **)(a1 + 32), (unsigned __int16)*v5);
  v28 = (unsigned __int16)*v5;
  *(_WORD *)((char *)v11 + v28 + 444) = 92;
  v29 = (char *)v11 + v28 + 446;
  LOWORD(v28) = *v7;
  *((_WORD *)v11 + 37) = *v7;
  *((_WORD *)v11 + 36) = v28;
  v11[10] = v29;
  memmove(v29, *(const void **)(a1 + 16), (unsigned __int16)*v7);
  v30 = &v29[(unsigned __int16)*v7];
  v31 = *v6;
  *((_WORD *)v11 + 61) = *v6;
  *((_WORD *)v11 + 60) = v31;
  v11[16] = v30;
  memmove(v30, *(const void **)(a1 + 64), *v6);
  v32 = &v30[*v6];
  v33 = *(_WORD *)(a1 + 72);
  *((_WORD *)v11 + 77) = v33;
  *((_WORD *)v11 + 76) = v33;
  v11[20] = v32;
  memmove(v32, *(const void **)(a1 + 80), *(unsigned __int16 *)(a1 + 72));
  v34 = (void *)((unsigned __int64)&v32[*(unsigned __int16 *)(a1 + 72) + 7] & 0xFFFFFFFFFFFFFFF8uLL);
  v11[32] = v34;
  v35 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 184));
  memmove(v34, *(const void **)(a1 + 184), v35);
  *((_DWORD *)v11 + 34) = 0;
  v11[18] = 0;
  if ( v3 == 3 )
  {
    *((_DWORD *)v11 + 71) = 1;
  }
  else
  {
    if ( v3 != 1 )
    {
      *((_DWORD *)v11 + 71) = 0;
      goto LABEL_34;
    }
    *((_DWORD *)v11 + 71) = 127;
  }
  *((_DWORD *)v11 + 73) = 48;
LABEL_34:
  RtlHashUnicodeString((PCUNICODE_STRING)(v11 + 9), 1u, 0, &HashValue);
  *((_DWORD *)v11 + 51) = HashValue;
  EtwActivityIdControl(3u, (LPGUID)(v11 + 1));
  BCryptGenRandom(0, (PUCHAR)v11 + 384, 8u, 2u);
  *((_DWORD *)v11 + 104) = *(_DWORD *)(a1 + 216);
  *(_OWORD *)(v11 + 5) = *(_OWORD *)(a1 + 220);
  ShareQoSFlowID = Smb2GenerateShareQoSFlowID(v11);
  if ( ShareQoSFlowID >= 0 )
  {
    v36 = 0;
    ExAcquireResourceExclusiveLite((PERESOURCE)(Instance[20] + 2064LL), 1u);
    if ( Smb2NoShare )
    {
      Smb2NoShare = 0;
      v36 = 1;
    }
    v37 = Instance[20] + 16 * ((HashValue & 0x7F) + 1LL);
    v38 = *(_QWORD **)(v37 + 8);
    if ( *v38 != v37 )
      __fastfail(3u);
    v11[28] = (PVOID)v37;
    v11[29] = v38;
    *v38 = v11 + 28;
    *(_QWORD *)(v37 + 8) = v11 + 28;
    ExReleaseResourceLite((PERESOURCE)(Instance[20] + 2064LL));
    Smb2DfsIsShareInDfs(v11, (char *)v11 + 276, (char *)v11 + 277);
    if ( *((_BYTE *)v11 + 276) )
      *((_DWORD *)v11 + 72) |= 1u;
    if ( *((_BYTE *)v11 + 277) )
      *((_DWORD *)v11 + 72) |= 2u;
    if ( v36 )
    {
      v44 = 16;
      SrvLibGetBinary(
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
        L"Guid",
        &Smb2Guid,
        &v44);
    }
    memset((char *)*v11 + 312, 0, 0x158u);
    v39 = (char *)*v11 + 312;
    Data.Size = 344;
    Data.Data = v39;
    ShareQoSFlowID = PcwCreateInstance(
                       (PPCW_INSTANCE *)v11 + 50,
                       Srv2ShareCounters,
                       (PCUNICODE_STRING)(v11 + 13),
                       1u,
                       &Data);
    v11[53] = 0;
    TimeIncrement = KeQueryTimeIncrement();
    v11[54] = (PVOID)(0x861C46800uLL / TimeIncrement);
    if ( ShareQoSFlowID >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          0x861C46800uLL % TimeIncrement,
          v41,
          (_DWORD)v11,
          (__int64)v5,
          (__int64)v7,
          (__int64)v6);
      }
      if ( (byte_14004C339 & 0x20) != 0 )
        McTemplateK0hzr0hzr2hzr4qqqqq_EtwWriteTransfer(
          *((_WORD *)v11 + 76) >> 1,
          (unsigned int)SMB2_EVENT_SHARE_ADD,
          v41,
          *((_WORD *)v11 + 36) >> 1,
          (__int64)v11[10],
          *((_WORD *)v11 + 44) >> 1,
          (__int64)v11[12],
          *((_WORD *)v11 + 76) >> 1,
          (__int64)v11[20],
          *((_DWORD *)v11 + 73),
          *((_DWORD *)v11 + 92),
          *((_DWORD *)v11 + 72),
          *((_DWORD *)v11 + 75),
          *((_DWORD *)v11 + 74));
      if ( ((_DWORD)v11[46] & 0x5000000) != 0 )
        _InterlockedIncrement(&Smb2ScaleOutSharesCount);
      return (unsigned int)ShareQoSFlowID;
    }
  }
LABEL_8:
  Srv2DereferenceInstance(Instance);
  if ( v11 )
  {
    v12 = v11[24];
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0);
      v11[24] = 0;
    }
    v13 = v11[33];
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0);
      v11[33] = 0;
    }
    if ( *v11 )
    {
      ExDeleteResourceLite((PERESOURCE)((char *)*v11 + 200));
      ExDeleteResourceLite((PERESOURCE)((char *)*v11 + 96));
      ExFreePoolWithTag(*v11, 0);
      *v11 = 0;
    }
    ExFreePoolWithTag(v11, 0);
  }
  return (unsigned int)ShareQoSFlowID;
}

```

## disassembly

```asm
0x140062f00  mov     rax, rsp
0x140062f03  mov     [rax+18h], rbx
0x140062f07  push    rbp
0x140062f08  push    rsi
0x140062f09  push    rdi
0x140062f0a  push    r12
0x140062f0c  push    r13
0x140062f0e  push    r14
0x140062f10  push    r15
0x140062f12  sub     rsp, 80h
0x140062f19  xor     ebx, ebx
0x140062f1b  mov     rsi, rcx
0x140062f1e  mov     [rax+8], ebx
0x140062f21  mov     eax, [rcx+80h]
0x140062f27  mov     ecx, 21000h
0x140062f2c  and     eax, ecx
0x140062f2e  cmp     eax, ecx
0x140062f30  jnz     short loc_140062F3C
0x140062f32  mov     ebx, 0C000000Dh
0x140062f37  jmp     loc_140063078
0x140062f3c  mov     r14d, [rsi+7Ch]
0x140062f40  movzx   r14d, r14b
0x140062f44  cmp     r14d, 2
0x140062f48  jnz     short loc_140062F54
0x140062f4a  mov     ebx, 0C00000BBh
0x140062f4f  jmp     loc_140063078
0x140062f54  mov     ecx, [rsi+98h]
0x140062f5a  call    Srv2GetInstance
0x140062f5f  mov     rbp, rax
0x140062f62  test    rax, rax
0x140062f65  jz      short loc_140062F32
0x140062f67  movzx   eax, word ptr [rsi+48h]
0x140062f6b  lea     r15, [rsi+18h]
0x140062f6f  movzx   ebx, word ptr [r15]
0x140062f73  lea     r13, [rsi+38h]
0x140062f77  mov     rcx, [rsi+0B8h]; SecurityDescriptor
0x140062f7e  lea     r12, [rsi+8]
0x140062f82  add     ebx, eax
0x140062f84  movzx   eax, word ptr [r13+0]
0x140062f89  add     ebx, eax
0x140062f8b  movzx   eax, word ptr [r12]
0x140062f90  add     ebx, eax
0x140062f92  call    cs:__imp_RtlLengthSecurityDescriptor
0x140062f99  nop     dword ptr [rax+rax+00h]
0x140062f9e  lea     edx, [rbx+1C6h]
0x140062fa4  mov     ecx, 100h
0x140062fa9  add     edx, eax
0x140062fab  mov     r8d, 6832534Ch
0x140062fb1  call    cs:__imp_ExAllocatePool2
0x140062fb8  nop     dword ptr [rax+rax+00h]
0x140062fbd  xor     ebx, ebx
0x140062fbf  mov     rdi, rax
0x140062fc2  test    rax, rax
0x140062fc5  jnz     loc_140063096
0x140062fcb  mov     ebx, 0C000009Ah
0x140062fd0  mov     rcx, rbp; Context
0x140062fd3  call    Srv2DereferenceInstance
0x140062fd8  xor     ebp, ebp
0x140062fda  test    rdi, rdi
0x140062fdd  jz      loc_140063078
0x140062fe3  mov     rcx, [rdi+0C0h]; P
0x140062fea  test    rcx, rcx
0x140062fed  jz      short loc_140063004
0x140062fef  xor     edx, edx; Tag
0x140062ff1  call    cs:__imp_ExFreePoolWithTag
0x140062ff8  nop     dword ptr [rax+rax+00h]
0x140062ffd  mov     [rdi+0C0h], rbp
0x140063004  mov     rcx, [rdi+108h]; P
0x14006300b  test    rcx, rcx
0x14006300e  jz      short loc_140063025
0x140063010  xor     edx, edx; Tag
0x140063012  call    cs:__imp_ExFreePoolWithTag
0x140063019  nop     dword ptr [rax+rax+00h]
0x14006301e  mov     [rdi+108h], rbp
0x140063025  mov     rcx, [rdi]
0x140063028  test    rcx, rcx
0x14006302b  jz      short loc_140063067
0x14006302d  add     rcx, 0C8h; Resource
0x140063034  call    cs:__imp_ExDeleteResourceLite
0x14006303b  nop     dword ptr [rax+rax+00h]
0x140063040  mov     rcx, [rdi]
0x140063043  add     rcx, 60h ; '`'; Resource
0x140063047  call    cs:__imp_ExDeleteResourceLite
0x14006304e  nop     dword ptr [rax+rax+00h]
0x140063053  mov     rcx, [rdi]; P
0x140063056  xor     edx, edx; Tag
0x140063058  call    cs:__imp_ExFreePoolWithTag
0x14006305f  nop     dword ptr [rax+rax+00h]
0x140063064  mov     [rdi], rbp
0x140063067  xor     edx, edx; Tag
0x140063069  mov     rcx, rdi; P
0x14006306c  call    cs:__imp_ExFreePoolWithTag
0x140063073  nop     dword ptr [rax+rax+00h]
0x140063078  mov     eax, ebx
0x14006307a  mov     rbx, [rsp+0B8h+arg_10]
0x140063082  add     rsp, 80h
0x140063089  pop     r15
0x14006308b  pop     r14
0x14006308d  pop     r13
0x14006308f  pop     r12
0x140063091  pop     rdi
0x140063092  pop     rsi
0x140063093  pop     rbp
0x140063094  retn
0x140063096  mov     [rax+198h], rbp
0x14006309d  mov     edx, 290h
0x1400630a2  add     rax, 150h
0x1400630a8  mov     ecx, 40h ; '@'
0x1400630ad  mov     r8d, 6832534Ch
0x1400630b3  mov     [rax+8], rax
0x1400630b7  mov     [rax], rax
0x1400630ba  lea     rax, [rdi+0D0h]
0x1400630c1  mov     [rax+8], rax
0x1400630c5  mov     [rax], rax
0x1400630c8  call    cs:__imp_ExAllocatePool2
0x1400630cf  nop     dword ptr [rax+rax+00h]
0x1400630d4  mov     [rdi], rax
0x1400630d7  test    rax, rax
0x1400630da  jz      loc_140062FCB
0x1400630e0  mov     qword ptr [rax], 1
0x1400630e7  mov     ecx, 290h
0x1400630ec  mov     [rax+10h], cx
0x1400630f0  mov     dword ptr [rax+8], 0Ch
0x1400630f7  mov     dword ptr [rax+0Ch], 0DCh
0x1400630fe  mov     [rax+30h], rbx
0x140063102  mov     [rax+38h], rax
0x140063106  mov     [rax+40h], rbp
0x14006310a  mov     [rax+48h], ebx
0x14006310d  mov     rax, [rdi]
0x140063110  mov     [rax+58h], rdi
0x140063114  mov     rcx, [rdi]
0x140063117  add     rcx, 60h ; '`'; Resource
0x14006311b  call    cs:__imp_ExInitializeResourceLite
0x140063122  nop     dword ptr [rax+rax+00h]
0x140063127  mov     rcx, [rdi]
0x14006312a  add     rcx, 0C8h; Resource
0x140063131  call    cs:__imp_ExInitializeResourceLite
0x140063138  nop     dword ptr [rax+rax+00h]
0x14006313d  mov     eax, [rsi+7Ch]
0x140063140  mov     rcx, [rdi]
0x140063143  shr     eax, 14h
0x140063146  add     rcx, 130h; RunRef
0x14006314d  and     al, 1
0x14006314f  mov     [rdi+116h], al
0x140063155  mov     eax, [rsi]
0x140063157  mov     [rdi+164h], eax
0x14006315d  mov     eax, [rsi+80h]
0x140063163  and     eax, 30h
0x140063166  mov     [rdi+124h], eax
0x14006316c  mov     eax, [rsi+80h]
0x140063172  and     eax, 0FFFFFFCFh
0x140063175  mov     [rdi+120h], eax
0x14006317b  mov     eax, [rsi+94h]
0x140063181  mov     [rdi+170h], eax
0x140063187  mov     eax, [rsi+8Ch]
0x14006318d  mov     [rdi+128h], eax
0x140063193  mov     eax, [rsi+90h]
0x140063199  mov     [rdi+12Ch], eax
0x14006319f  mov     dword ptr [rdi+130h], 1
0x1400631a9  mov     [rdi+119h], bl
0x1400631af  call    cs:__imp_ExInitializeRundownProtection
0x1400631b6  nop     dword ptr [rax+rax+00h]
0x1400631bb  test    dword ptr [rdi+170h], 0E000000h
0x1400631c5  mov     cs:Smb2BypassCSVFileOpenRundownInitialized, 1
0x1400631cc  jz      short loc_1400631D5
0x1400631ce  mov     cs:Smb2IsRkfInstalled, 1
0x1400631d5  movzx   eax, word ptr [rsi+0C8h]
0x1400631dc  test    ax, ax
0x1400631df  jz      short loc_140063236
0x1400631e1  mov     edx, eax
0x1400631e3  mov     ecx, 102h
0x1400631e8  mov     r8d, 6832534Ch
0x1400631ee  call    cs:__imp_ExAllocatePool2
0x1400631f5  nop     dword ptr [rax+rax+00h]
0x1400631fa  mov     [rdi+0C0h], rax
0x140063201  test    rax, rax
0x140063204  jz      loc_140062FCB
0x14006320a  movzx   r8d, word ptr [rsi+0C8h]; Size
0x140063212  mov     rcx, rax; void *
0x140063215  mov     rdx, [rsi+0D0h]; Src
0x14006321c  call    memmove
0x140063221  movzx   eax, word ptr [rsi+0C8h]
0x140063228  mov     [rdi+0BAh], ax
0x14006322f  mov     [rdi+0B8h], ax
0x140063236  mov     rcx, [rsi+0C0h]; SecurityDescriptor
0x14006323d  test    rcx, rcx
0x140063240  jz      short loc_1400632A0
0x140063242  call    cs:__imp_RtlLengthSecurityDescriptor
0x140063249  nop     dword ptr [rax+rax+00h]
0x14006324e  mov     edx, eax
0x140063250  mov     ecx, 102h
0x140063255  mov     r8d, 6832534Ch
0x14006325b  call    cs:__imp_ExAllocatePool2
0x140063262  nop     dword ptr [rax+rax+00h]
0x140063267  mov     [rdi+108h], rax
0x14006326e  test    rax, rax
0x140063271  jz      loc_140062FCB
0x140063277  mov     rcx, [rsi+0C0h]; SecurityDescriptor
0x14006327e  call    cs:__imp_RtlLengthSecurityDescriptor
0x140063285  nop     dword ptr [rax+rax+00h]
0x14006328a  mov     rdx, [rsi+0C0h]; Src
0x140063291  mov     rcx, [rdi+108h]; void *
0x140063298  mov     r8d, eax; Size
0x14006329b  call    memmove
0x1400632a0  mov     dword ptr [rdi+110h], 1
0x1400632aa  lea     rbx, [rdi+1B8h]
0x1400632b1  mov     [rdi+70h], rbx
0x1400632b5  movzx   ecx, word ptr [r15]
0x1400632b9  add     cx, 6
0x1400632bd  add     cx, [r12]
0x1400632c2  mov     [rdi+6Ah], cx
0x1400632c6  mov     [rdi+68h], cx
0x1400632ca  xor     ecx, ecx
0x1400632cc  mov     rax, [rdi+70h]
0x1400632d0  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400632d6  inc     rcx
0x1400632d9  cmp     rcx, 2
0x1400632dd  jnz     short loc_1400632CC
0x1400632df  movzx   eax, word ptr [r15]
0x1400632e3  add     rbx, 4
0x1400632e7  mov     [rdi+5Ah], ax
0x1400632eb  mov     rcx, rbx; void *
0x1400632ee  mov     [rdi+58h], ax
0x1400632f2  mov     [rdi+60h], rbx
0x1400632f6  movzx   r8d, word ptr [r15]; Size
0x1400632fa  mov     rdx, [rsi+20h]; Src
0x1400632fe  call    memmove
0x140063303  movzx   eax, word ptr [r15]
0x140063307  mov     word ptr [rax+rbx], 5Ch ; '\'
0x14006330d  add     rbx, 2
0x140063311  add     rbx, rax
0x140063314  movzx   eax, word ptr [r12]
0x140063319  mov     [rdi+4Ah], ax
0x14006331d  mov     rcx, rbx; void *
0x140063320  mov     [rdi+48h], ax
0x140063324  mov     [rdi+50h], rbx
0x140063328  movzx   r8d, word ptr [r12]; Size
0x14006332d  mov     rdx, [rsi+10h]; Src
0x140063331  call    memmove
0x140063336  movzx   eax, word ptr [r12]
0x14006333b  add     rbx, rax
0x14006333e  movzx   eax, word ptr [r13+0]
0x140063343  mov     [rdi+7Ah], ax
0x140063347  mov     rcx, rbx; void *
0x14006334a  mov     [rdi+78h], ax
0x14006334e  mov     [rdi+80h], rbx
0x140063355  movzx   r8d, word ptr [r13+0]; Size
0x14006335a  mov     rdx, [rsi+40h]; Src
0x14006335e  call    memmove
0x140063363  movzx   eax, word ptr [r13+0]
0x140063368  add     rbx, rax
0x14006336b  movzx   eax, word ptr [rsi+48h]
0x14006336f  mov     [rdi+9Ah], ax
0x140063376  mov     rcx, rbx; void *
0x140063379  mov     [rdi+98h], ax
0x140063380  mov     [rdi+0A0h], rbx
0x140063387  movzx   r8d, word ptr [rsi+48h]; Size
0x14006338c  mov     rdx, [rsi+50h]; Src
0x140063390  call    memmove
0x140063395  movzx   eax, word ptr [rsi+48h]
0x140063399  add     rax, 7
0x14006339d  add     rbx, rax
0x1400633a0  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400633a4  mov     [rdi+100h], rbx
0x1400633ab  mov     rcx, [rsi+0B8h]; SecurityDescriptor
0x1400633b2  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400633b9  nop     dword ptr [rax+rax+00h]
0x1400633be  mov     rdx, [rsi+0B8h]; Src
0x1400633c5  mov     rcx, rbx; void *
0x1400633c8  mov     r8d, eax; Size
0x1400633cb  call    memmove
0x1400633d0  xor     ecx, ecx
0x1400633d2  mov     [rdi+88h], ecx
0x1400633d8  mov     [rdi+90h], rcx
0x1400633df  cmp     r14d, 3
0x1400633e3  jnz     short loc_1400633F1
0x1400633e5  mov     dword ptr [rdi+11Ch], 1
0x1400633ef  jmp     short loc_140063401
0x1400633f1  cmp     r14d, 1
0x1400633f5  jnz     short loc_14006340D
0x1400633f7  mov     dword ptr [rdi+11Ch], 7Fh
0x140063401  mov     dword ptr [rdi+124h], 30h ; '0'
0x14006340b  jmp     short loc_140063413
0x14006340d  mov     [rdi+11Ch], ecx
0x140063413  lea     r9, [rsp+0B8h+HashValue]; HashValue
0x14006341b  xor     r8d, r8d; HashAlgorithm
0x14006341e  mov     dl, 1; CaseInSensitive
0x140063420  lea     rcx, [rdi+48h]; String
0x140063424  call    cs:__imp_RtlHashUnicodeString
0x14006342b  nop     dword ptr [rax+rax+00h]
0x140063430  mov     eax, [rsp+0B8h+HashValue]
0x140063437  lea     rdx, [rdi+8]; ActivityId
0x14006343b  mov     ecx, 3; ControlCode
0x140063440  mov     [rdi+0CCh], eax
0x140063446  call    cs:__imp_EtwActivityIdControl
0x14006344d  nop     dword ptr [rax+rax+00h]
0x140063452  xor     ecx, ecx; hAlgorithm
0x140063454  lea     rdx, [rdi+180h]; pbBuffer
0x14006345b  lea     r9d, [rcx+2]; dwFlags
0x14006345f  lea     r8d, [rcx+8]; cbBuffer
  ... truncated ...
```
