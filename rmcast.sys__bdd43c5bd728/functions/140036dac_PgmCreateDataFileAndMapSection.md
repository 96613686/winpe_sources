# PgmCreateDataFileAndMapSection

- ea: `0x140036dac`
- end: `0x140037442`
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
- `0x140036b98`
- `0x140036dac`
- `0x1400384e4`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140036e39`
- `ntoskrnl!KeStackAttachProcess` at `0x140036e39`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140036e9c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14003733a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400373f5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140036e9c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14003733a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400373f5`
- `ntoskrnl!ZwCreateFile` at `0x1400370b7`
- `ntoskrnl!ZwCreateFile` at `0x1400370b7`
- `ntoskrnl!ZwCreateSection` at `0x140037154`
- `ntoskrnl!ZwCreateSection` at `0x140037154`
- `ntoskrnl!ZwMapViewOfSection` at `0x140037262`
- `ntoskrnl!ZwMapViewOfSection` at `0x140037262`
- `ntoskrnl!ObfReferenceObject` at `0x1400373dc`
- `ntoskrnl!ObfReferenceObject` at `0x1400373dc`
- `ntoskrnl!ZwClose` at `0x1400372e2`
- `ntoskrnl!ZwClose` at `0x140037303`
- `ntoskrnl!ZwClose` at `0x1400372e2`
- `ntoskrnl!ZwClose` at `0x140037303`
- `ntoskrnl!ObfDereferenceObject` at `0x1400372c1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400372c1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400371b7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400371b7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140036e19`
- `ntoskrnl!PsGetCurrentProcess` at `0x140036e19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036fb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037321`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037350`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037406`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036fb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037321`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037350`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037406`

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
0x140036dac  mov     r11, rsp
0x140036daf  mov     [r11+18h], rbx
0x140036db3  mov     [r11+20h], rsi
0x140036db7  push    rdi
0x140036db8  push    r12
0x140036dba  push    r13
0x140036dbc  push    r14
0x140036dbe  push    r15
0x140036dc0  sub     rsp, 0F0h
0x140036dc7  mov     rax, cs:__security_cookie
0x140036dce  xor     rax, rsp
0x140036dd1  mov     [rsp+118h+var_30], rax
0x140036dd9  xorps   xmm0, xmm0
0x140036ddc  xor     r13d, r13d
0x140036ddf  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x140036de7  xor     eax, eax
0x140036de9  mov     qword ptr [rsp+118h+MaximumSize], r13
0x140036dee  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x140036df6  mov     rdi, rdx
0x140036df9  mov     [r11-78h], r13
0x140036dfd  mov     rsi, rcx
0x140036e00  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x140036e05  movups  xmmword ptr [r11-70h], xmm0
0x140036e0a  movups  xmmword ptr [r11-60h], xmm0
0x140036e0f  movups  xmmword ptr [r11-50h], xmm0
0x140036e14  movups  xmmword ptr [r11-40h], xmm0
0x140036e19  call    cs:__imp_PsGetCurrentProcess
0x140036e20  nop     dword ptr [rax+rax+00h]
0x140036e25  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140036e2c  cmp     rax, rcx
0x140036e2f  jz      short loc_140036E4A
0x140036e31  lea     rdx, [rsp+118h+ApcState]; ApcState
0x140036e39  call    cs:__imp_KeStackAttachProcess
0x140036e40  nop     dword ptr [rax+rax+00h]
0x140036e45  mov     r14b, 1
0x140036e48  jmp     short loc_140036E4D
0x140036e4a  mov     r14b, r13b
0x140036e4d  mov     rcx, rdi
0x140036e50  call    BuildPgmDataFileName
0x140036e55  mov     ebx, eax
0x140036e57  test    eax, eax
0x140036e59  jns     short loc_140036EAF
0x140036e5b  mov     r10, cs:WPP_GLOBAL_Control
0x140036e62  lea     rcx, WPP_GLOBAL_Control
0x140036e69  cmp     r10, rcx
0x140036e6c  jz      short loc_140036E8F
0x140036e6e  mov     ecx, [r10+2Ch]
0x140036e72  test    cl, 2
0x140036e75  jz      short loc_140036E8F
0x140036e77  mov     rcx, [r10+18h]
0x140036e7b  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036e82  mov     edx, 0Bh
0x140036e87  mov     r9d, eax
0x140036e8a  call    WPP_SF_d
0x140036e8f  test    r14b, r14b
0x140036e92  jz      short loc_140036EA8
0x140036e94  lea     rcx, [rsp+118h+ApcState]; ApcState
0x140036e9c  call    cs:__imp_KeUnstackDetachProcess
0x140036ea3  nop     dword ptr [rax+rax+00h]
0x140036ea8  mov     eax, ebx
0x140036eaa  jmp     loc_140037414
0x140036eaf  mov     rcx, [rdi+18h]
0x140036eb3  xor     edx, edx
0x140036eb5  mov     r10, [rcx+118h]
0x140036ebc  mov     r8d, [rcx+0F8h]
0x140036ec3  mov     rax, r10
0x140036ec6  div     r8
0x140036ec9  movzx   edx, byte ptr [rdi+0A0h]
0x140036ed0  lea     r9, [rax+rax]
0x140036ed4  cmp     dl, 1
0x140036ed7  jbe     short loc_140036EE2
0x140036ed9  lea     rax, [rdx-1]
0x140036edd  add     r9, rax
0x140036ee0  jmp     short loc_140036EE9
0x140036ee2  shr     rax, 2
0x140036ee6  sub     r9, rax
0x140036ee9  mov     eax, 7FFFFFFFh
0x140036eee  cmp     r9, rax
0x140036ef1  jbe     short loc_140036F28
0x140036ef3  mov     r9d, eax
0x140036ef6  imul    rax, r8, 3FFFFFFFh
0x140036efd  cmp     r10, rax
0x140036f00  jbe     short loc_140036F28
0x140036f02  mov     [rcx+118h], rax
0x140036f09  xor     edx, edx
0x140036f0b  mov     rcx, [rdi+18h]
0x140036f0f  mov     rax, [rcx+118h]
0x140036f16  shl     rax, 3
0x140036f1a  div     qword ptr [rcx+110h]
0x140036f21  mov     [rcx+120h], rax
0x140036f28  mov     r8, [rdi+28h]
0x140036f2c  xor     edx, edx
0x140036f2e  movzx   eax, byte ptr [rdi+0A0h]
0x140036f35  mov     ecx, [r8+6Ch]
0x140036f39  mov     r12d, ecx
0x140036f3c  imul    ecx, eax
0x140036f3f  imul    r12, r9
0x140036f43  mov     rax, r12
0x140036f46  div     rcx
0x140036f49  mov     rcx, rsi
0x140036f4c  sub     r12, rdx
0x140036f4f  xor     edx, edx
0x140036f51  mov     [r8+58h], r12
0x140036f55  mov     rax, r12
0x140036f58  mov     r9, [rdi+28h]
0x140036f5c  mov     r8d, [r9+6Ch]
0x140036f60  div     r8
0x140036f63  mov     rdx, rdi
0x140036f66  mov     [r9+60h], rax
0x140036f6a  mov     qword ptr [rsp+118h+MaximumSize], r12
0x140036f6f  call    InitRDataInfo
0x140036f74  mov     ebx, eax
0x140036f76  test    eax, eax
0x140036f78  jns     short loc_140036FD1
0x140036f7a  mov     r10, cs:WPP_GLOBAL_Control
0x140036f81  lea     rcx, WPP_GLOBAL_Control
0x140036f88  cmp     r10, rcx
0x140036f8b  jz      short loc_140036FAE
0x140036f8d  mov     edx, [r10+2Ch]
0x140036f91  test    dl, 2
0x140036f94  jz      short loc_140036FAE
0x140036f96  mov     rcx, [r10+18h]
0x140036f9a  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036fa1  mov     edx, 0Ch
0x140036fa6  mov     r9d, eax
0x140036fa9  call    WPP_SF_d
0x140036fae  mov     rcx, [rdi+28h]
0x140036fb2  xor     edx, edx; Tag
0x140036fb4  mov     rcx, [rcx+18h]; P
0x140036fb8  call    cs:__imp_ExFreePoolWithTag
0x140036fbf  nop     dword ptr [rax+rax+00h]
0x140036fc4  mov     rax, [rdi+28h]
0x140036fc8  mov     [rax+18h], r13
0x140036fcc  jmp     loc_140036E8F
0x140036fd1  lea     rcx, [rsp+118h+Object]
0x140036fd6  mov     [rsp+118h+Object], r13
0x140036fdb  call    PgmBuildAdminSecurityDescriptor
0x140036fe0  mov     r15, [rsp+118h+Object]
0x140036fe5  mov     esi, eax
0x140036fe7  test    eax, eax
0x140036fe9  jns     short loc_14003702B
0x140036feb  mov     rax, cs:WPP_GLOBAL_Control
0x140036ff2  lea     rcx, WPP_GLOBAL_Control
0x140036ff9  cmp     rax, rcx
0x140036ffc  jz      loc_1400372B4
0x140037002  mov     edx, [rax+2Ch]
0x140037005  test    dl, 2
0x140037008  jz      loc_1400372B4
0x14003700e  mov     rcx, [rax+18h]
0x140037012  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140037019  mov     edx, 0Dh
0x14003701e  mov     r9d, esi
0x140037021  call    WPP_SF_d
0x140037026  jmp     loc_1400372B4
0x14003702b  mov     rcx, [rdi+28h]
0x14003702f  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x140037037  mov     [rsp+118h+EaLength], r13d; EaLength
0x14003703c  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x140037041  mov     [rsp+118h+EaBuffer], r13; EaBuffer
0x140037046  xorps   xmm0, xmm0
0x140037049  mov     [rsp+118h+CreateOptions], 1040h; CreateOptions
0x140037051  mov     edx, 10003h; DesiredAccess
0x140037056  lea     rax, [rcx+10h]
0x14003705a  mov     [rsp+118h+CreateDisposition], 2; CreateDisposition
0x140037062  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x14003706a  add     rcx, 38h ; '8'; FileHandle
0x14003706e  lea     rax, [rsp+118h+MaximumSize]
0x140037073  mov     [rsp+118h+ShareAccess], r13d; ShareAccess
0x140037078  mov     [rsp+118h+FileAttributes], 100h; FileAttributes
0x140037080  mov     [rsp+118h+AllocationSize], rax; AllocationSize
0x140037085  mov     qword ptr [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x14003708e  mov     qword ptr [rsp+118h+ObjectAttributes.Attributes], 240h
0x14003709a  mov     [rsp+118h+ObjectAttributes.RootDirectory], r13
0x14003709f  mov     [rsp+118h+ObjectAttributes.SecurityDescriptor], r15
0x1400370a7  mov     [rsp+118h+ObjectAttributes.SecurityQualityOfService], r13
0x1400370af  movups  xmmword ptr [rsp+118h+IoStatusBlock], xmm0
0x1400370b7  call    cs:__imp_ZwCreateFile
0x1400370be  nop     dword ptr [rax+rax+00h]
0x1400370c3  mov     esi, eax
0x1400370c5  test    eax, eax
0x1400370c7  jns     short loc_1400370F6
0x1400370c9  mov     r10, cs:WPP_GLOBAL_Control
0x1400370d0  lea     rcx, WPP_GLOBAL_Control
0x1400370d7  cmp     r10, rcx
0x1400370da  jz      loc_1400372B4
0x1400370e0  mov     eax, [r10+2Ch]
0x1400370e4  test    al, 2
0x1400370e6  jz      loc_1400372B4
0x1400370ec  mov     edx, 0Eh
0x1400370f1  jmp     loc_140037298
0x1400370f6  mov     rax, [rdi+28h]
0x1400370fa  lea     r9, [rsp+118h+MaximumSize]; MaximumSize
0x1400370ff  xorps   xmm0, xmm0
0x140037102  mov     qword ptr [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x14003710b  mov     qword ptr [rsp+118h+ObjectAttributes.Attributes], 240h
0x140037117  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x14003711c  mov     [rsp+118h+ObjectAttributes.RootDirectory], r13
0x140037121  mov     edx, 0F0007h; DesiredAccess
0x140037126  lea     rcx, [rax+40h]; SectionHandle
0x14003712a  mov     [rsp+118h+ObjectAttributes.ObjectName], r13
0x140037132  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003713b  mov     rax, [rax+38h]
0x14003713f  mov     qword ptr [rsp+118h+ShareAccess], rax; FileHandle
0x140037144  mov     [rsp+118h+FileAttributes], 8000000h; AllocationAttributes
0x14003714c  mov     dword ptr [rsp+118h+AllocationSize], 4; SectionPageProtection
0x140037154  call    cs:__imp_ZwCreateSection
0x14003715b  nop     dword ptr [rax+rax+00h]
0x140037160  mov     esi, eax
0x140037162  test    eax, eax
0x140037164  jns     short loc_140037193
0x140037166  mov     r10, cs:WPP_GLOBAL_Control
0x14003716d  lea     rcx, WPP_GLOBAL_Control
0x140037174  cmp     r10, rcx
0x140037177  jz      loc_1400372B4
0x14003717d  mov     eax, [r10+2Ch]
0x140037181  test    al, 2
0x140037183  jz      loc_1400372B4
0x140037189  mov     edx, 0Fh
0x14003718e  jmp     loc_140037298
0x140037193  mov     rbx, [rdi+28h]
0x140037197  lea     rax, [rsp+118h+Object]
0x14003719c  mov     qword ptr [rsp+118h+FileAttributes], r13; HandleInformation
0x1400371a1  xor     r9d, r9d; AccessMode
0x1400371a4  xor     r8d, r8d; ObjectType
0x1400371a7  mov     [rsp+118h+Object], r13
0x1400371ac  xor     edx, edx; DesiredAccess
0x1400371ae  mov     [rsp+118h+AllocationSize], rax; Object
0x1400371b3  mov     rcx, [rbx+40h]; Handle
0x1400371b7  call    cs:__imp_ObReferenceObjectByHandle
0x1400371be  nop     dword ptr [rax+rax+00h]
0x1400371c3  mov     esi, eax
0x1400371c5  mov     rax, [rsp+118h+Object]
0x1400371ca  mov     [rbx+48h], rax
0x1400371ce  test    esi, esi
0x1400371d0  jns     short loc_14003721B
0x1400371d2  mov     r10, cs:WPP_GLOBAL_Control
0x1400371d9  lea     rcx, WPP_GLOBAL_Control
0x1400371e0  cmp     r10, rcx
0x1400371e3  jz      loc_1400372B4
0x1400371e9  mov     eax, [r10+2Ch]
0x1400371ed  test    al, 2
0x1400371ef  jz      loc_1400372B4
0x1400371f5  mov     r9, [rdi+28h]
0x1400371f9  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140037200  mov     rcx, [r10+18h]
0x140037204  mov     edx, 10h
0x140037209  mov     dword ptr [rsp+118h+AllocationSize], esi
0x14003720d  mov     r9, [r9+40h]
0x140037211  call    WPP_SF_qD
0x140037216  jmp     loc_1400372B4
0x14003721b  mov     rcx, [rdi+28h]
0x14003721f  lea     rax, [rsp+118h+ViewSize]
0x140037227  mov     dword ptr [rsp+118h+EaBuffer], 4; Win32Protect
0x14003722f  xor     r9d, r9d; ZeroBits
0x140037232  mov     [rsp+118h+CreateOptions], r13d; AllocationType
0x140037237  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003723b  mov     [rsp+118h+CreateDisposition], 2; InheritDisposition
0x140037243  mov     qword ptr [rsp+118h+ShareAccess], rax; ViewSize
0x140037248  lea     r8, [rcx+50h]; BaseAddress
0x14003724c  mov     [rsp+118h+ViewSize], r13
0x140037254  mov     rcx, [rcx+40h]; SectionHandle
0x140037258  mov     qword ptr [rsp+118h+FileAttributes], r13; SectionOffset
0x14003725d  mov     [rsp+118h+AllocationSize], r13; CommitSize
0x140037262  call    cs:__imp_ZwMapViewOfSection
0x140037269  nop     dword ptr [rax+rax+00h]
0x14003726e  mov     esi, eax
0x140037270  test    eax, eax
0x140037272  jns     loc_140037373
0x140037278  mov     r10, cs:WPP_GLOBAL_Control
0x14003727f  lea     rcx, WPP_GLOBAL_Control
0x140037286  cmp     r10, rcx
0x140037289  jz      short loc_1400372B4
0x14003728b  mov     eax, [r10+2Ch]
0x14003728f  test    al, 2
0x140037291  jz      short loc_1400372B4
0x140037293  mov     edx, 11h
0x140037298  mov     r9, [rdi+28h]
0x14003729c  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x1400372a3  mov     rcx, [r10+18h]
0x1400372a7  add     r9, 10h
0x1400372ab  mov     dword ptr [rsp+118h+AllocationSize], esi
0x1400372af  call    WPP_SF_ZD
0x1400372b4  mov     rax, [rdi+28h]
0x1400372b8  mov     rcx, [rax+48h]; Object
0x1400372bc  test    rcx, rcx
0x1400372bf  jz      short loc_1400372D5
0x1400372c1  call    cs:__imp_ObfDereferenceObject
0x1400372c8  nop     dword ptr [rax+rax+00h]
0x1400372cd  mov     rax, [rdi+28h]
0x1400372d1  mov     [rax+48h], r13
0x1400372d5  mov     rax, [rdi+28h]
0x1400372d9  mov     rcx, [rax+40h]; Handle
0x1400372dd  test    rcx, rcx
0x1400372e0  jz      short loc_1400372F6
0x1400372e2  call    cs:__imp_ZwClose
0x1400372e9  nop     dword ptr [rax+rax+00h]
0x1400372ee  mov     rax, [rdi+28h]
0x1400372f2  mov     [rax+40h], r13
0x1400372f6  mov     rax, [rdi+28h]
0x1400372fa  mov     rcx, [rax+38h]; Handle
  ... truncated ...
```
