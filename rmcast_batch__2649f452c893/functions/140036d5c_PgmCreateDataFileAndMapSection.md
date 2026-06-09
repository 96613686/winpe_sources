# PgmCreateDataFileAndMapSection

- ea: `0x140036d5c`
- end: `0x1400373f2`
- name: `PgmCreateDataFileAndMapSection`
- size: `1686`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140005e3c`

## callees

- `0x140005068`
- `0x140005328`
- `0x140008450`
- `0x140008a04`
- `0x14000a050`
- `0x14000a0e0`
- `0x14001cdf0`
- `0x140036b48`
- `0x140036d5c`
- `0x140038494`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140036de9`
- `ntoskrnl!KeStackAttachProcess` at `0x140036de9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140036e4c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400372ea`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400373a5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140036e4c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400372ea`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400373a5`
- `ntoskrnl!ZwCreateFile` at `0x140037067`
- `ntoskrnl!ZwCreateFile` at `0x140037067`
- `ntoskrnl!ZwCreateSection` at `0x140037104`
- `ntoskrnl!ZwCreateSection` at `0x140037104`
- `ntoskrnl!ZwMapViewOfSection` at `0x140037212`
- `ntoskrnl!ZwMapViewOfSection` at `0x140037212`
- `ntoskrnl!ObfReferenceObject` at `0x14003738c`
- `ntoskrnl!ObfReferenceObject` at `0x14003738c`
- `ntoskrnl!ZwClose` at `0x140037292`
- `ntoskrnl!ZwClose` at `0x1400372b3`
- `ntoskrnl!ZwClose` at `0x140037292`
- `ntoskrnl!ZwClose` at `0x1400372b3`
- `ntoskrnl!ObfDereferenceObject` at `0x140037271`
- `ntoskrnl!ObfDereferenceObject` at `0x140037271`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037167`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037167`
- `ntoskrnl!PsGetCurrentProcess` at `0x140036dc9`
- `ntoskrnl!PsGetCurrentProcess` at `0x140036dc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036f68`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037300`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400373b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036f68`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037300`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400373b6`

## pseudocode

```c
__int64 __fastcall PgmCreateDataFileAndMapSection(__int64 a1, __int64 a2)
{
  char v4; // r14
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // r9
  __int64 v14; // r8
  unsigned __int64 v15; // r12
  int inited; // eax
  int v17; // eax
  PVOID v18; // r15
  NTSTATUS v19; // esi
  struct _UNICODE_STRING *v20; // rcx
  PDEVICE_OBJECT v21; // r10
  int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rcx
  int v26; // r8d
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  PVOID Object; // [rsp+60h] [rbp-B8h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+68h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-A8h] BYREF
  ULONG_PTR ViewSize; // [rsp+A0h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-70h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+B8h] [rbp-60h] BYREF

  MaximumSize.QuadPart = 0;
  ViewSize = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
  {
    v4 = 0;
  }
  else
  {
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
    v4 = 1;
  }
  v5 = BuildPgmDataFileName(a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids,
        (unsigned int)v5);
LABEL_8:
    if ( v4 )
      KeUnstackDetachProcess(&ApcState);
    return v6;
  }
  v8 = *(_QWORD *)(a2 + 24);
  v9 = *(unsigned int *)(v8 + 248);
  v10 = *(_QWORD *)(v8 + 280) / v9;
  v11 = *(unsigned __int8 *)(a2 + 160);
  v12 = 2 * v10;
  if ( (unsigned __int8)v11 <= 1u )
    v13 = v12 - (v10 >> 2);
  else
    v13 = v11 - 1 + v12;
  if ( v13 > 0x7FFFFFFF )
  {
    v13 = 0x7FFFFFFF;
    if ( *(_QWORD *)(v8 + 280) > 0x3FFFFFFF * v9 )
    {
      *(_QWORD *)(v8 + 280) = 0x3FFFFFFF * v9;
      *(_QWORD *)(*(_QWORD *)(a2 + 24) + 288LL) = (unsigned __int64)(8LL * *(_QWORD *)(*(_QWORD *)(a2 + 24) + 280LL))
                                                / *(_QWORD *)(*(_QWORD *)(a2 + 24) + 272LL);
    }
  }
  v14 = *(_QWORD *)(a2 + 40);
  v15 = v13 * *(unsigned int *)(v14 + 108)
      - v13 * *(unsigned int *)(v14 + 108) % ((unsigned int)*(unsigned __int8 *)(a2 + 160) * *(_DWORD *)(v14 + 108));
  *(_QWORD *)(v14 + 88) = v15;
  *(_QWORD *)(*(_QWORD *)(a2 + 40) + 96LL) = v15 / *(unsigned int *)(*(_QWORD *)(a2 + 40) + 108LL);
  MaximumSize.QuadPart = v15;
  inited = InitRDataInfo(a1, a2);
  v6 = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids,
        (unsigned int)inited);
    ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a2 + 40) + 24LL), 0);
    *(_QWORD *)(*(_QWORD *)(a2 + 40) + 24LL) = 0;
    goto LABEL_8;
  }
  Object = 0;
  v17 = PgmBuildAdminSecurityDescriptor(&Object);
  v18 = Object;
  v19 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids,
        (unsigned int)v17);
    goto LABEL_43;
  }
  v20 = *(struct _UNICODE_STRING **)(a2 + 40);
  ObjectAttributes.ObjectName = v20 + 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.SecurityDescriptor = Object;
  ObjectAttributes.SecurityQualityOfService = 0;
  IoStatusBlock = 0;
  v19 = ZwCreateFile(
          (PHANDLE)&v20[3].Buffer,
          0x10003u,
          &ObjectAttributes,
          &IoStatusBlock,
          &MaximumSize,
          0x100u,
          0,
          2u,
          0x1040u,
          0,
          0);
  if ( v19 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_43;
    v22 = 14;
LABEL_42:
    WPP_SF_ZD(
      v21->AttachedDevice,
      v22,
      (unsigned int)WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids,
      *(_QWORD *)(a2 + 40) + 16,
      v19);
LABEL_43:
    v27 = *(void **)(*(_QWORD *)(a2 + 40) + 72LL);
    if ( v27 )
    {
      ObfDereferenceObject(v27);
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 72LL) = 0;
    }
    v28 = *(void **)(*(_QWORD *)(a2 + 40) + 64LL);
    if ( v28 )
    {
      ZwClose(v28);
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 64LL) = 0;
    }
    v29 = *(void **)(*(_QWORD *)(a2 + 40) + 56LL);
    if ( v29 )
    {
      ZwClose(v29);
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 56LL) = 0;
    }
    if ( v18 )
      ExFreePoolWithTag(v18, 0);
    if ( v4 )
      KeUnstackDetachProcess(&ApcState);
    ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a2 + 40) + 24LL), 0);
    *(_QWORD *)(*(_QWORD *)(a2 + 40) + 24LL) = 0;
    DestroyRDataInfo(a2);
    return (unsigned int)v19;
  }
  v23 = *(_QWORD *)(a2 + 40);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v19 = ZwCreateSection(
          (PHANDLE)(v23 + 64),
          0xF0007u,
          &ObjectAttributes,
          &MaximumSize,
          4u,
          0x8000000u,
          *(HANDLE *)(v23 + 56));
  if ( v19 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_43;
    v22 = 15;
    goto LABEL_42;
  }
  v24 = *(_QWORD *)(a2 + 40);
  Object = 0;
  v19 = ObReferenceObjectByHandle(*(HANDLE *)(v24 + 64), 0, 0, 0, &Object, 0);
  *(_QWORD *)(v24 + 72) = Object;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 64LL),
        v19);
    goto LABEL_43;
  }
  v25 = *(_QWORD *)(a2 + 40);
  ViewSize = 0;
  v19 = ZwMapViewOfSection(
          *(HANDLE *)(v25 + 64),
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          (PVOID *)(v25 + 80),
          0,
          0,
          0,
          &ViewSize,
          ViewUnmap,
          0,
          4u);
  if ( v19 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_43;
    v22 = 17;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Zqi(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)WPP_GLOBAL_Control,
      v26,
      *(_QWORD *)(a2 + 40) + 16,
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 80LL),
      v15);
  *(_QWORD *)(*(_QWORD *)(a2 + 40) + 120LL) = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 88LL);
  *(_DWORD *)(*(_QWORD *)(a2 + 40) + 116LL) = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 96LL);
  *(_QWORD *)(*(_QWORD *)(a2 + 40) + 136LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a2 + 40) + 128LL) = 0;
  ObfReferenceObject(*(PVOID *)(a2 + 72));
  if ( v4 )
    KeUnstackDetachProcess(&ApcState);
  ExFreePoolWithTag(v18, 0);
  return 0;
}

```

## disassembly

```asm
0x140036d5c  mov     r11, rsp
0x140036d5f  mov     [r11+18h], rbx
0x140036d63  mov     [r11+20h], rsi
0x140036d67  push    rdi
0x140036d68  push    r12
0x140036d6a  push    r13
0x140036d6c  push    r14
0x140036d6e  push    r15
0x140036d70  sub     rsp, 0F0h
0x140036d77  mov     rax, cs:__security_cookie
0x140036d7e  xor     rax, rsp
0x140036d81  mov     [rsp+118h+var_30], rax
0x140036d89  xorps   xmm0, xmm0
0x140036d8c  xor     r13d, r13d
0x140036d8f  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x140036d97  xor     eax, eax
0x140036d99  mov     qword ptr [rsp+118h+MaximumSize], r13
0x140036d9e  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x140036da6  mov     rdi, rdx
0x140036da9  mov     [r11-78h], r13
0x140036dad  mov     rsi, rcx
0x140036db0  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x140036db5  movups  xmmword ptr [r11-70h], xmm0
0x140036dba  movups  xmmword ptr [r11-60h], xmm0
0x140036dbf  movups  xmmword ptr [r11-50h], xmm0
0x140036dc4  movups  xmmword ptr [r11-40h], xmm0
0x140036dc9  call    cs:__imp_PsGetCurrentProcess
0x140036dd0  nop     dword ptr [rax+rax+00h]
0x140036dd5  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140036ddc  cmp     rax, rcx
0x140036ddf  jz      short loc_140036DFA
0x140036de1  lea     rdx, [rsp+118h+ApcState]; ApcState
0x140036de9  call    cs:__imp_KeStackAttachProcess
0x140036df0  nop     dword ptr [rax+rax+00h]
0x140036df5  mov     r14b, 1
0x140036df8  jmp     short loc_140036DFD
0x140036dfa  mov     r14b, r13b
0x140036dfd  mov     rcx, rdi
0x140036e00  call    BuildPgmDataFileName
0x140036e05  mov     ebx, eax
0x140036e07  test    eax, eax
0x140036e09  jns     short loc_140036E5F
0x140036e0b  mov     r10, cs:WPP_GLOBAL_Control
0x140036e12  lea     rcx, WPP_GLOBAL_Control
0x140036e19  cmp     r10, rcx
0x140036e1c  jz      short loc_140036E3F
0x140036e1e  mov     ecx, [r10+2Ch]
0x140036e22  test    cl, 2
0x140036e25  jz      short loc_140036E3F
0x140036e27  mov     rcx, [r10+18h]
0x140036e2b  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036e32  mov     edx, 0Bh
0x140036e37  mov     r9d, eax
0x140036e3a  call    WPP_SF_d
0x140036e3f  test    r14b, r14b
0x140036e42  jz      short loc_140036E58
0x140036e44  lea     rcx, [rsp+118h+ApcState]; ApcState
0x140036e4c  call    cs:__imp_KeUnstackDetachProcess
0x140036e53  nop     dword ptr [rax+rax+00h]
0x140036e58  mov     eax, ebx
0x140036e5a  jmp     loc_1400373C4
0x140036e5f  mov     rcx, [rdi+18h]
0x140036e63  xor     edx, edx
0x140036e65  mov     r10, [rcx+118h]
0x140036e6c  mov     r8d, [rcx+0F8h]
0x140036e73  mov     rax, r10
0x140036e76  div     r8
0x140036e79  movzx   edx, byte ptr [rdi+0A0h]
0x140036e80  lea     r9, [rax+rax]
0x140036e84  cmp     dl, 1
0x140036e87  jbe     short loc_140036E92
0x140036e89  lea     rax, [rdx-1]
0x140036e8d  add     r9, rax
0x140036e90  jmp     short loc_140036E99
0x140036e92  shr     rax, 2
0x140036e96  sub     r9, rax
0x140036e99  mov     eax, 7FFFFFFFh
0x140036e9e  cmp     r9, rax
0x140036ea1  jbe     short loc_140036ED8
0x140036ea3  mov     r9d, eax
0x140036ea6  imul    rax, r8, 3FFFFFFFh
0x140036ead  cmp     r10, rax
0x140036eb0  jbe     short loc_140036ED8
0x140036eb2  mov     [rcx+118h], rax
0x140036eb9  xor     edx, edx
0x140036ebb  mov     rcx, [rdi+18h]
0x140036ebf  mov     rax, [rcx+118h]
0x140036ec6  shl     rax, 3
0x140036eca  div     qword ptr [rcx+110h]
0x140036ed1  mov     [rcx+120h], rax
0x140036ed8  mov     r8, [rdi+28h]
0x140036edc  xor     edx, edx
0x140036ede  movzx   eax, byte ptr [rdi+0A0h]
0x140036ee5  mov     ecx, [r8+6Ch]
0x140036ee9  mov     r12d, ecx
0x140036eec  imul    ecx, eax
0x140036eef  imul    r12, r9
0x140036ef3  mov     rax, r12
0x140036ef6  div     rcx
0x140036ef9  mov     rcx, rsi
0x140036efc  sub     r12, rdx
0x140036eff  xor     edx, edx
0x140036f01  mov     [r8+58h], r12
0x140036f05  mov     rax, r12
0x140036f08  mov     r9, [rdi+28h]
0x140036f0c  mov     r8d, [r9+6Ch]
0x140036f10  div     r8
0x140036f13  mov     rdx, rdi
0x140036f16  mov     [r9+60h], rax
0x140036f1a  mov     qword ptr [rsp+118h+MaximumSize], r12
0x140036f1f  call    InitRDataInfo
0x140036f24  mov     ebx, eax
0x140036f26  test    eax, eax
0x140036f28  jns     short loc_140036F81
0x140036f2a  mov     r10, cs:WPP_GLOBAL_Control
0x140036f31  lea     rcx, WPP_GLOBAL_Control
0x140036f38  cmp     r10, rcx
0x140036f3b  jz      short loc_140036F5E
0x140036f3d  mov     edx, [r10+2Ch]
0x140036f41  test    dl, 2
0x140036f44  jz      short loc_140036F5E
0x140036f46  mov     rcx, [r10+18h]
0x140036f4a  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036f51  mov     edx, 0Ch
0x140036f56  mov     r9d, eax
0x140036f59  call    WPP_SF_d
0x140036f5e  mov     rcx, [rdi+28h]
0x140036f62  xor     edx, edx; Tag
0x140036f64  mov     rcx, [rcx+18h]; P
0x140036f68  call    cs:__imp_ExFreePoolWithTag
0x140036f6f  nop     dword ptr [rax+rax+00h]
0x140036f74  mov     rax, [rdi+28h]
0x140036f78  mov     [rax+18h], r13
0x140036f7c  jmp     loc_140036E3F
0x140036f81  lea     rcx, [rsp+118h+Object]
0x140036f86  mov     [rsp+118h+Object], r13
0x140036f8b  call    PgmBuildAdminSecurityDescriptor
0x140036f90  mov     r15, [rsp+118h+Object]
0x140036f95  mov     esi, eax
0x140036f97  test    eax, eax
0x140036f99  jns     short loc_140036FDB
0x140036f9b  mov     rax, cs:WPP_GLOBAL_Control
0x140036fa2  lea     rcx, WPP_GLOBAL_Control
0x140036fa9  cmp     rax, rcx
0x140036fac  jz      loc_140037264
0x140036fb2  mov     edx, [rax+2Ch]
0x140036fb5  test    dl, 2
0x140036fb8  jz      loc_140037264
0x140036fbe  mov     rcx, [rax+18h]
0x140036fc2  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036fc9  mov     edx, 0Dh
0x140036fce  mov     r9d, esi
0x140036fd1  call    WPP_SF_d
0x140036fd6  jmp     loc_140037264
0x140036fdb  mov     rcx, [rdi+28h]
0x140036fdf  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x140036fe7  mov     [rsp+118h+EaLength], r13d; EaLength
0x140036fec  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x140036ff1  mov     [rsp+118h+EaBuffer], r13; EaBuffer
0x140036ff6  xorps   xmm0, xmm0
0x140036ff9  mov     [rsp+118h+CreateOptions], 1040h; CreateOptions
0x140037001  mov     edx, 10003h; DesiredAccess
0x140037006  lea     rax, [rcx+10h]
0x14003700a  mov     [rsp+118h+CreateDisposition], 2; CreateDisposition
0x140037012  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x14003701a  add     rcx, 38h ; '8'; FileHandle
0x14003701e  lea     rax, [rsp+118h+MaximumSize]
0x140037023  mov     [rsp+118h+ShareAccess], r13d; ShareAccess
0x140037028  mov     [rsp+118h+FileAttributes], 100h; FileAttributes
0x140037030  mov     [rsp+118h+AllocationSize], rax; AllocationSize
0x140037035  mov     qword ptr [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x14003703e  mov     qword ptr [rsp+118h+ObjectAttributes.Attributes], 240h
0x14003704a  mov     [rsp+118h+ObjectAttributes.RootDirectory], r13
0x14003704f  mov     [rsp+118h+ObjectAttributes.SecurityDescriptor], r15
0x140037057  mov     [rsp+118h+ObjectAttributes.SecurityQualityOfService], r13
0x14003705f  movups  xmmword ptr [rsp+118h+IoStatusBlock], xmm0
0x140037067  call    cs:__imp_ZwCreateFile
0x14003706e  nop     dword ptr [rax+rax+00h]
0x140037073  mov     esi, eax
0x140037075  test    eax, eax
0x140037077  jns     short loc_1400370A6
0x140037079  mov     r10, cs:WPP_GLOBAL_Control
0x140037080  lea     rcx, WPP_GLOBAL_Control
0x140037087  cmp     r10, rcx
0x14003708a  jz      loc_140037264
0x140037090  mov     eax, [r10+2Ch]
0x140037094  test    al, 2
0x140037096  jz      loc_140037264
0x14003709c  mov     edx, 0Eh
0x1400370a1  jmp     loc_140037248
0x1400370a6  mov     rax, [rdi+28h]
0x1400370aa  lea     r9, [rsp+118h+MaximumSize]; MaximumSize
0x1400370af  xorps   xmm0, xmm0
0x1400370b2  mov     qword ptr [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x1400370bb  mov     qword ptr [rsp+118h+ObjectAttributes.Attributes], 240h
0x1400370c7  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x1400370cc  mov     [rsp+118h+ObjectAttributes.RootDirectory], r13
0x1400370d1  mov     edx, 0F0007h; DesiredAccess
0x1400370d6  lea     rcx, [rax+40h]; SectionHandle
0x1400370da  mov     [rsp+118h+ObjectAttributes.ObjectName], r13
0x1400370e2  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400370eb  mov     rax, [rax+38h]
0x1400370ef  mov     qword ptr [rsp+118h+ShareAccess], rax; FileHandle
0x1400370f4  mov     [rsp+118h+FileAttributes], 8000000h; AllocationAttributes
0x1400370fc  mov     dword ptr [rsp+118h+AllocationSize], 4; SectionPageProtection
0x140037104  call    cs:__imp_ZwCreateSection
0x14003710b  nop     dword ptr [rax+rax+00h]
0x140037110  mov     esi, eax
0x140037112  test    eax, eax
0x140037114  jns     short loc_140037143
0x140037116  mov     r10, cs:WPP_GLOBAL_Control
0x14003711d  lea     rcx, WPP_GLOBAL_Control
0x140037124  cmp     r10, rcx
0x140037127  jz      loc_140037264
0x14003712d  mov     eax, [r10+2Ch]
0x140037131  test    al, 2
0x140037133  jz      loc_140037264
0x140037139  mov     edx, 0Fh
0x14003713e  jmp     loc_140037248
0x140037143  mov     rbx, [rdi+28h]
0x140037147  lea     rax, [rsp+118h+Object]
0x14003714c  mov     qword ptr [rsp+118h+FileAttributes], r13; HandleInformation
0x140037151  xor     r9d, r9d; AccessMode
0x140037154  xor     r8d, r8d; ObjectType
0x140037157  mov     [rsp+118h+Object], r13
0x14003715c  xor     edx, edx; DesiredAccess
0x14003715e  mov     [rsp+118h+AllocationSize], rax; Object
0x140037163  mov     rcx, [rbx+40h]; Handle
0x140037167  call    cs:__imp_ObReferenceObjectByHandle
0x14003716e  nop     dword ptr [rax+rax+00h]
0x140037173  mov     esi, eax
0x140037175  mov     rax, [rsp+118h+Object]
0x14003717a  mov     [rbx+48h], rax
0x14003717e  test    esi, esi
0x140037180  jns     short loc_1400371CB
0x140037182  mov     r10, cs:WPP_GLOBAL_Control
0x140037189  lea     rcx, WPP_GLOBAL_Control
0x140037190  cmp     r10, rcx
0x140037193  jz      loc_140037264
0x140037199  mov     eax, [r10+2Ch]
0x14003719d  test    al, 2
0x14003719f  jz      loc_140037264
0x1400371a5  mov     r9, [rdi+28h]
0x1400371a9  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x1400371b0  mov     rcx, [r10+18h]
0x1400371b4  mov     edx, 10h
0x1400371b9  mov     dword ptr [rsp+118h+AllocationSize], esi
0x1400371bd  mov     r9, [r9+40h]
0x1400371c1  call    WPP_SF_qD
0x1400371c6  jmp     loc_140037264
0x1400371cb  mov     rcx, [rdi+28h]
0x1400371cf  lea     rax, [rsp+118h+ViewSize]
0x1400371d7  mov     dword ptr [rsp+118h+EaBuffer], 4; Win32Protect
0x1400371df  xor     r9d, r9d; ZeroBits
0x1400371e2  mov     [rsp+118h+CreateOptions], r13d; AllocationType
0x1400371e7  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400371eb  mov     [rsp+118h+CreateDisposition], 2; InheritDisposition
0x1400371f3  mov     qword ptr [rsp+118h+ShareAccess], rax; ViewSize
0x1400371f8  lea     r8, [rcx+50h]; BaseAddress
0x1400371fc  mov     [rsp+118h+ViewSize], r13
0x140037204  mov     rcx, [rcx+40h]; SectionHandle
0x140037208  mov     qword ptr [rsp+118h+FileAttributes], r13; SectionOffset
0x14003720d  mov     [rsp+118h+AllocationSize], r13; CommitSize
0x140037212  call    cs:__imp_ZwMapViewOfSection
0x140037219  nop     dword ptr [rax+rax+00h]
0x14003721e  mov     esi, eax
0x140037220  test    eax, eax
0x140037222  jns     loc_140037323
0x140037228  mov     r10, cs:WPP_GLOBAL_Control
0x14003722f  lea     rcx, WPP_GLOBAL_Control
0x140037236  cmp     r10, rcx
0x140037239  jz      short loc_140037264
0x14003723b  mov     eax, [r10+2Ch]
0x14003723f  test    al, 2
0x140037241  jz      short loc_140037264
0x140037243  mov     edx, 11h
0x140037248  mov     r9, [rdi+28h]
0x14003724c  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140037253  mov     rcx, [r10+18h]
0x140037257  add     r9, 10h
0x14003725b  mov     dword ptr [rsp+118h+AllocationSize], esi
0x14003725f  call    WPP_SF_ZD
0x140037264  mov     rax, [rdi+28h]
0x140037268  mov     rcx, [rax+48h]; Object
0x14003726c  test    rcx, rcx
0x14003726f  jz      short loc_140037285
0x140037271  call    cs:__imp_ObfDereferenceObject
0x140037278  nop     dword ptr [rax+rax+00h]
0x14003727d  mov     rax, [rdi+28h]
0x140037281  mov     [rax+48h], r13
0x140037285  mov     rax, [rdi+28h]
0x140037289  mov     rcx, [rax+40h]; Handle
0x14003728d  test    rcx, rcx
0x140037290  jz      short loc_1400372A6
0x140037292  call    cs:__imp_ZwClose
0x140037299  nop     dword ptr [rax+rax+00h]
0x14003729e  mov     rax, [rdi+28h]
0x1400372a2  mov     [rax+40h], r13
0x1400372a6  mov     rax, [rdi+28h]
0x1400372aa  mov     rcx, [rax+38h]; Handle
  ... truncated ...
```
