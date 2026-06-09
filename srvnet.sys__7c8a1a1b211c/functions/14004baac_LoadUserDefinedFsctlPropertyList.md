# LoadUserDefinedFsctlPropertyList

- ea: `0x14004baac`
- end: `0x14004c0f6`
- name: `LoadUserDefinedFsctlPropertyList`
- size: `1610`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x14004c210`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x14000bef0`
- `0x14001389c`
- `0x140015790`
- `0x140016cc8`
- `0x140022db0`
- `0x14002a3e0`
- `0x14004ba8c`
- `0x14004baac`
- `0x14004c0fc`
- `0x14004f4f0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14004bb21`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004bb21`
- `ntoskrnl!ZwOpenKey` at `0x14004bb5e`
- `ntoskrnl!ZwOpenKey` at `0x14004bb5e`
- `ntoskrnl!qsort` at `0x14004c055`
- `ntoskrnl!qsort` at `0x14004c055`
- `ntoskrnl!ZwQueryKey` at `0x14004bbd3`
- `ntoskrnl!ZwQueryKey` at `0x14004bbd3`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14004bc5d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14004bc5d`
- `ntoskrnl!ZwClose` at `0x14004c0c4`
- `ntoskrnl!ZwClose` at `0x14004c0c4`

## string_xrefs

- `0x14004bb06`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters\FsctlAllowList`

## pseudocode

```c
__int64 __fastcall LoadUserDefinedFsctlPropertyList(void **a1, unsigned int *a2)
{
  __int64 v2; // rbx
  _DWORD *v3; // rsi
  __int64 v4; // rdx
  NTSTATUS v5; // edi
  unsigned int v6; // eax
  __int64 v7; // rdi
  unsigned int v8; // r13d
  ULONG v9; // eax
  NTSTATUS v10; // eax
  int v11; // eax
  int v12; // edi
  int v13; // r8d
  __int64 v14; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdi
  int v18; // r9d
  unsigned int v19; // edx
  _WORD *v20; // rcx
  unsigned int v21; // r8d
  int v22; // r8d
  int v23; // r9d
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rax
  void **v26; // rcx
  unsigned int *v27; // r14
  unsigned int v28; // ebx
  void **v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-89h] BYREF
  ULONG v34; // [rsp+34h] [rbp-85h]
  ULONG i; // [rsp+38h] [rbp-81h]
  __int64 v36; // [rsp+40h] [rbp-79h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-71h] BYREF
  __int64 PoolWithTag; // [rsp+50h] [rbp-69h]
  void **v39; // [rsp+58h] [rbp-61h]
  ULONGLONG pullResult; // [rsp+60h] [rbp-59h] BYREF
  unsigned int *v41; // [rsp+68h] [rbp-51h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-19h] BYREF
  char KeyInformation[36]; // [rsp+B0h] [rbp-9h] BYREF
  int v45; // [rsp+D4h] [rbp+1Bh]
  int v46; // [rsp+D8h] [rbp+1Fh]

  v39 = a1;
  v41 = a2;
  KeyHandle = 0;
  PoolWithTag = 0;
  v2 = 0;
  ResultLength = 0;
  *a1 = 0;
  *a2 = 0;
  v3 = 0;
  v36 = 0;
  DestinationString = 0;
  pullResult = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters\\FsctlAllowList");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v5 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_1f61802886993e1448d511754803ac98_Traceguids,
        (unsigned int)v5);
    }
    goto LABEL_89;
  }
  v6 = ZwQueryKey(KeyHandle, KeyFullInformation, KeyInformation, 0x30u, &ResultLength);
  if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147483643 )
  {
    LODWORD(v7) = v46 + ((v45 + 27) & 0xFFFFFFF8);
    v34 = v7;
    PoolWithTag = SrvNetAllocatePoolWithTag(258, (unsigned int)v7, 1684095315);
    v3 = (_DWORD *)PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v16 = 11;
LABEL_86:
        WPP_SF_(AttachedDevice, v16, WPP_1f61802886993e1448d511754803ac98_Traceguids);
      }
      goto LABEL_87;
    }
  }
  else
  {
    LODWORD(v7) = 0;
    v34 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1f61802886993e1448d511754803ac98_Traceguids, v6);
    }
  }
  v8 = 0;
  v9 = 0;
LABEL_13:
  for ( i = v9; ; v9 = i )
  {
    v10 = ZwEnumerateValueKey(KeyHandle, v9, KeyValueFullInformation, v3, v7, &ResultLength);
    v5 = v10;
    if ( v10 >= 0 )
    {
      v11 = v3[1];
      if ( v11 == 4 )
      {
        if ( v3[3] < 4u )
          goto LABEL_48;
        v12 = *(_DWORD *)((char *)v3 + (unsigned int)v3[2]);
        if ( !(unsigned __int8)ContainsFsctlSingleListEntry(&v36) )
        {
          v14 = SrvNetAllocatePoolWithTag(258, 16, 1684095315);
          if ( !v14 )
          {
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
              || !BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              goto LABEL_87;
            }
            v16 = 13;
            goto LABEL_85;
          }
          *(_DWORD *)(v14 + 8) = v12;
          *(_BYTE *)(v14 + 12) = 3;
          *(_QWORD *)v14 = v2;
          v2 = v14;
          v36 = v14;
          goto LABEL_20;
        }
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000) != 0 )
          McTemplateK0qqzr1_EtwWriteTransfer(v3[4] >> 1, v4, v13, 0, v3[4] >> 1, (__int64)(v3 + 5));
LABEL_48:
        if ( i != -1 )
        {
          LODWORD(v7) = v34;
          v9 = i + 1;
          goto LABEL_13;
        }
LABEL_65:
        v5 = 0;
        if ( !v8 )
          goto LABEL_89;
        v5 = RtlULongLongMult(8u, v8, &pullResult);
        if ( v5 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_1f61802886993e1448d511754803ac98_Traceguids,
              KeyHandle,
              v5);
          }
          goto LABEL_89;
        }
        v25 = SrvNetAllocatePoolWithTag(258, pullResult, 1684095315);
        v26 = v39;
        v4 = 0;
        *v39 = (void *)v25;
        if ( v25 )
        {
          v27 = v41;
          v28 = 0;
          *v41 = v8;
          v29 = v26;
          do
          {
            v30 = PopFsctlSingleListEntry(&v36, v4);
            *((_DWORD *)*v29 + 2 * v28) = *(_DWORD *)(v30 + 8);
            *((_BYTE *)*v29 + 8 * v28 + 4) = *(_BYTE *)(v30 + 12);
            SrvNetWskNotifyCleanupProviderContext(v30);
            ++v28;
          }
          while ( v28 < v8 );
          v3 = (_DWORD *)PoolWithTag;
          qsort(*v39, *v27, 8u, (int (__cdecl *)(const void *, const void *))CompareFsctlPropertyListRecords);
          goto LABEL_89;
        }
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_87;
        }
        v16 = 17;
LABEL_85:
        AttachedDevice = v24->AttachedDevice;
        goto LABEL_86;
      }
      if ( v11 != 7 || !v3[3] )
        goto LABEL_48;
      v17 = SrvNetAllocatePoolWithTag(258, 16, 1684095315);
      if ( !v17 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_87;
        }
        v16 = 14;
        goto LABEL_85;
      }
      *(_BYTE *)(v17 + 12) = 0;
      v19 = 0;
      *(_DWORD *)(v17 + 8) = 0;
      v20 = (_WORD *)((char *)v3 + (unsigned int)v3[2]);
      v21 = v3[3] >> 1;
      if ( v21 )
      {
        do
        {
          if ( !*v20 && v19 < v21 - 2 )
            *v20 = 44;
          ++v20;
          ++v19;
        }
        while ( v19 < v21 );
      }
      if ( (int)RfsCskvParse((int)v3 + v3[2], v3[3], v21, v18, v17) < 0 )
      {
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000) != 0 )
        {
          v23 = 2;
          goto LABEL_46;
        }
      }
      else
      {
        LODWORD(v4) = *(_DWORD *)(v17 + 8);
        if ( (_DWORD)v4 )
        {
          if ( !(unsigned __int8)ContainsFsctlSingleListEntry(&v36) )
          {
            *(_BYTE *)(v17 + 12) |= 3u;
            *(_QWORD *)v17 = v2;
            v2 = v17;
            v36 = v17;
LABEL_20:
            ++v8;
            goto LABEL_48;
          }
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000) == 0 )
            goto LABEL_47;
          v23 = 0;
          goto LABEL_46;
        }
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000) != 0 )
        {
          v23 = 1;
LABEL_46:
          McTemplateK0qqzr1_EtwWriteTransfer(v3[4] >> 1, v4, v22, v23, v3[4] >> 1, (__int64)(v3 + 5));
        }
      }
LABEL_47:
      SrvNetWskNotifyCleanupProviderContext(v17);
      goto LABEL_48;
    }
    if ( v10 != -2147483643 && v10 != -1073741789 )
    {
      if ( v10 != -2147483622 )
        goto LABEL_89;
      goto LABEL_65;
    }
    v7 = ResultLength;
    v34 = ResultLength;
    if ( v3 )
      SrvNetWskNotifyCleanupProviderContext(v3);
    PoolWithTag = SrvNetAllocatePoolWithTag(258, v7, 1684095315);
    v3 = (_DWORD *)PoolWithTag;
    if ( !PoolWithTag )
      break;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v16 = 15;
    goto LABEL_85;
  }
LABEL_87:
  v5 = -1073741670;
LABEL_89:
  while ( 1 )
  {
    v31 = PopFsctlSingleListEntry(&v36, v4);
    if ( !v31 )
      break;
    SrvNetWskNotifyCleanupProviderContext(v31);
  }
  if ( v3 )
    SrvNetWskNotifyCleanupProviderContext(v3);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14004baac  mov     [rsp-8+arg_10], rbx
0x14004bab1  push    rbp
0x14004bab2  push    rsi
0x14004bab3  push    rdi
0x14004bab4  push    r13
0x14004bab6  push    r14
0x14004bab8  lea     rbp, [rsp-37h]
0x14004babd  sub     rsp, 0F0h
0x14004bac4  mov     rax, cs:__security_cookie
0x14004bacb  xor     rax, rsp
0x14004bace  mov     [rbp+57h+var_30], rax
0x14004bad2  xor     r14d, r14d
0x14004bad5  mov     [rbp+57h+var_B8], rcx
0x14004bad9  xorps   xmm0, xmm0
0x14004badc  mov     [rbp+57h+var_A8], rdx
0x14004bae0  mov     rax, rcx
0x14004bae3  mov     [rbp+57h+KeyHandle], r14
0x14004bae7  xor     ecx, ecx
0x14004bae9  mov     [rbp+57h+var_C0], r14
0x14004baed  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004baf1  mov     ebx, r14d
0x14004baf4  mov     [rsp+110h+var_E0], r14d
0x14004baf9  mov     [rax], r14
0x14004bafc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004bb00  mov     [rdx], r14d
0x14004bb03  mov     esi, r14d
0x14004bb06  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004bb0d  mov     [rbp+57h+var_D0], rbx
0x14004bb11  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004bb15  mov     [rbp+57h+pullResult], r14
0x14004bb19  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004bb1d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14004bb21  call    cs:__imp_RtlInitUnicodeString
0x14004bb28  nop     dword ptr [rax+rax+00h]
0x14004bb2d  lea     rax, [rbp+57h+DestinationString]
0x14004bb31  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004bb38  xorps   xmm0, xmm0
0x14004bb3b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004bb3f  lea     r13d, [r14+1]
0x14004bb43  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14004bb47  mov     edx, r13d; DesiredAccess
0x14004bb4a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004bb51  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004bb55  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004bb59  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004bb5e  call    cs:__imp_ZwOpenKey
0x14004bb65  nop     dword ptr [rax+rax+00h]
0x14004bb6a  mov     edi, eax
0x14004bb6c  test    eax, eax
0x14004bb6e  jns     short loc_14004BBB7
0x14004bb70  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004bb77  lea     r14, WPP_GLOBAL_Control
0x14004bb7e  cmp     rcx, r14
0x14004bb81  jz      loc_14004C0A0
0x14004bb87  mov     eax, [rcx+2Ch]
0x14004bb8a  test    al, 20h
0x14004bb8c  jz      loc_14004C0A0
0x14004bb92  cmp     [rcx+29h], r13b
0x14004bb96  jb      loc_14004C0A0
0x14004bb9c  mov     rcx, [rcx+18h]
0x14004bba0  lea     edx, [rbx+0Ah]
0x14004bba3  mov     r9d, edi
0x14004bba6  lea     r8, WPP_1f61802886993e1448d511754803ac98_Traceguids
0x14004bbad  call    WPP_SF_d
0x14004bbb2  jmp     loc_14004C0A0
0x14004bbb7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004bbbb  lea     rax, [rsp+110h+var_E0]
0x14004bbc0  mov     r9d, 30h ; '0'; Length
0x14004bbc6  mov     [rsp+110h+ResultLength], rax; ResultLength
0x14004bbcb  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x14004bbcf  lea     edx, [r9-2Eh]; KeyInformationClass
0x14004bbd3  call    cs:__imp_ZwQueryKey
0x14004bbda  nop     dword ptr [rax+rax+00h]
0x14004bbdf  mov     ecx, 80000000h
0x14004bbe4  lea     r14, WPP_GLOBAL_Control
0x14004bbeb  mov     r9d, eax
0x14004bbee  add     eax, ecx
0x14004bbf0  test    ecx, eax
0x14004bbf2  jnz     loc_14004BCDC
0x14004bbf8  cmp     r9d, 80000005h
0x14004bbff  jz      loc_14004BCDC
0x14004bc05  xor     edi, edi
0x14004bc07  mov     [rsp+110h+var_DC], edi
0x14004bc0b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004bc12  cmp     rcx, r14
0x14004bc15  jz      short loc_14004BC37
0x14004bc17  mov     eax, [rcx+2Ch]
0x14004bc1a  test    al, 20h
0x14004bc1c  jz      short loc_14004BC37
0x14004bc1e  cmp     [rcx+29h], r13b
0x14004bc22  jb      short loc_14004BC37
0x14004bc24  mov     rcx, [rcx+18h]
0x14004bc28  lea     edx, [rdi+0Ch]
0x14004bc2b  lea     r8, WPP_1f61802886993e1448d511754803ac98_Traceguids
0x14004bc32  call    WPP_SF_d
0x14004bc37  xor     r13d, r13d
0x14004bc3a  xor     eax, eax
0x14004bc3c  mov     [rsp+110h+var_D8], eax
0x14004bc40  lea     rcx, [rsp+110h+var_E0]
0x14004bc45  mov     r9, rsi; KeyValueInformation
0x14004bc48  mov     [rsp+110h+var_E8], rcx; ResultLength
0x14004bc4d  mov     r8d, 1; KeyValueInformationClass
0x14004bc53  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004bc57  mov     edx, eax; Index
0x14004bc59  mov     dword ptr [rsp+110h+ResultLength], edi; Length
0x14004bc5d  call    cs:__imp_ZwEnumerateValueKey
0x14004bc64  nop     dword ptr [rax+rax+00h]
0x14004bc69  xor     ecx, ecx
0x14004bc6b  mov     edi, eax
0x14004bc6d  test    eax, eax
0x14004bc6f  js      loc_14004BE83
0x14004bc75  mov     eax, [rsi+4]
0x14004bc78  cmp     eax, 4
0x14004bc7b  jnz     loc_14004BD73
0x14004bc81  cmp     [rsi+0Ch], eax
0x14004bc84  jb      loc_14004BE6B
0x14004bc8a  mov     eax, [rsi+8]
0x14004bc8d  lea     rcx, [rbp+57h+var_D0]
0x14004bc91  mov     edi, [rax+rsi]
0x14004bc94  mov     edx, edi
0x14004bc96  call    ContainsFsctlSingleListEntry
0x14004bc9b  xor     ecx, ecx
0x14004bc9d  test    al, al
0x14004bc9f  jnz     loc_14004BD47
0x14004bca5  lea     edx, [rcx+10h]
0x14004bca8  mov     r8d, 64614153h
0x14004bcae  mov     ecx, 102h
0x14004bcb3  call    SrvNetAllocatePoolWithTag
0x14004bcb8  xor     ecx, ecx
0x14004bcba  test    rax, rax
0x14004bcbd  jz      loc_14004BED6
0x14004bcc3  mov     [rax+8], edi
0x14004bcc6  mov     byte ptr [rax+0Ch], 3
0x14004bcca  mov     [rax], rbx
0x14004bccd  mov     rbx, rax
0x14004bcd0  mov     [rbp+57h+var_D0], rax
0x14004bcd4  inc     r13d
0x14004bcd7  jmp     loc_14004BE6B
0x14004bcdc  mov     edi, [rbp+57h+var_3C]
0x14004bcdf  mov     ecx, 102h
0x14004bce4  add     edi, 1Bh
0x14004bce7  mov     r8d, 64614153h
0x14004bced  and     edi, 0FFFFFFF8h
0x14004bcf0  add     edi, [rbp+57h+var_38]
0x14004bcf3  mov     edx, edi
0x14004bcf5  mov     [rsp+110h+var_DC], edi
0x14004bcf9  call    SrvNetAllocatePoolWithTag
0x14004bcfe  mov     [rbp+57h+var_C0], rax
0x14004bd02  mov     rsi, rax
0x14004bd05  test    rax, rax
0x14004bd08  jnz     loc_14004BC37
0x14004bd0e  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004bd15  lea     r14, WPP_GLOBAL_Control
0x14004bd1c  cmp     rax, r14
0x14004bd1f  jz      loc_14004C091
0x14004bd25  mov     ecx, [rax+2Ch]
0x14004bd28  test    cl, 20h
0x14004bd2b  jz      loc_14004C091
0x14004bd31  cmp     [rax+29h], r13b
0x14004bd35  jb      loc_14004C091
0x14004bd3b  mov     rcx, [rax+18h]
0x14004bd3f  lea     edx, [rsi+0Bh]
0x14004bd42  jmp     loc_14004C085
0x14004bd47  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 40h
0x14004bd4e  jz      loc_14004BE6B
0x14004bd54  mov     ecx, [rsi+10h]
0x14004bd57  lea     rax, [rsi+14h]
0x14004bd5b  shr     ecx, 1
0x14004bd5d  xor     r9d, r9d
0x14004bd60  mov     [rsp+110h+var_E8], rax
0x14004bd65  mov     dword ptr [rsp+110h+ResultLength], ecx
0x14004bd69  call    McTemplateK0qqzr1_EtwWriteTransfer
0x14004bd6e  jmp     loc_14004BE69
0x14004bd73  cmp     eax, 7
0x14004bd76  jnz     loc_14004BE6B
0x14004bd7c  cmp     [rsi+0Ch], ecx
0x14004bd7f  jbe     loc_14004BE6B
0x14004bd85  lea     edx, [rax+9]
0x14004bd88  mov     ecx, 102h
0x14004bd8d  mov     r8d, 64614153h
0x14004bd93  call    SrvNetAllocatePoolWithTag
0x14004bd98  mov     rdi, rax
0x14004bd9b  xor     eax, eax
0x14004bd9d  test    rdi, rdi
0x14004bda0  jz      loc_14004BF05
0x14004bda6  mov     [rdi+0Ch], al
0x14004bda9  mov     edx, eax
0x14004bdab  mov     [rdi+8], eax
0x14004bdae  mov     ecx, [rsi+8]
0x14004bdb1  mov     r8d, [rsi+0Ch]
0x14004bdb5  add     rcx, rsi
0x14004bdb8  shr     r8d, 1
0x14004bdbb  jz      short loc_14004BDDC
0x14004bdbd  cmp     [rcx], ax
0x14004bdc0  jnz     short loc_14004BDD1
0x14004bdc2  lea     eax, [r8-2]
0x14004bdc6  cmp     edx, eax
0x14004bdc8  jnb     short loc_14004BDCF
0x14004bdca  mov     word ptr [rcx], 2Ch ; ','
0x14004bdcf  xor     eax, eax
0x14004bdd1  add     rcx, 2
0x14004bdd5  inc     edx
0x14004bdd7  cmp     edx, r8d
0x14004bdda  jb      short loc_14004BDBD
0x14004bddc  mov     ecx, [rsi+8]
0x14004bddf  mov     edx, [rsi+0Ch]
0x14004bde2  add     rcx, rsi
0x14004bde5  mov     [rsp+110h+ResultLength], rdi
0x14004bdea  call    RfsCskvParse
0x14004bdef  test    eax, eax
0x14004bdf1  js      short loc_14004BE3B
0x14004bdf3  mov     edx, [rdi+8]
0x14004bdf6  test    edx, edx
0x14004bdf8  jz      short loc_14004BE2A
0x14004bdfa  lea     rcx, [rbp+57h+var_D0]
0x14004bdfe  call    ContainsFsctlSingleListEntry
0x14004be03  xor     ecx, ecx
0x14004be05  test    al, al
0x14004be07  jnz     short loc_14004BE1C
0x14004be09  or      byte ptr [rdi+0Ch], 3
0x14004be0d  mov     [rdi], rbx
0x14004be10  mov     rbx, rdi
0x14004be13  mov     [rbp+57h+var_D0], rbx
0x14004be17  jmp     loc_14004BCD4
0x14004be1c  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 40h
0x14004be23  jz      short loc_14004BE61
0x14004be25  xor     r9d, r9d
0x14004be28  jmp     short loc_14004BE4A
0x14004be2a  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 40h
0x14004be31  jz      short loc_14004BE61
0x14004be33  mov     r9d, 1
0x14004be39  jmp     short loc_14004BE4A
0x14004be3b  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 40h
0x14004be42  jz      short loc_14004BE61
0x14004be44  mov     r9d, 2
0x14004be4a  mov     ecx, [rsi+10h]
0x14004be4d  lea     rax, [rsi+14h]
0x14004be51  shr     ecx, 1
0x14004be53  mov     [rsp+110h+var_E8], rax
0x14004be58  mov     dword ptr [rsp+110h+ResultLength], ecx
0x14004be5c  call    McTemplateK0qqzr1_EtwWriteTransfer
0x14004be61  mov     rcx, rdi
0x14004be64  call    SrvNetWskNotifyCleanupProviderContext
0x14004be69  xor     ecx, ecx
0x14004be6b  mov     eax, [rsp+110h+var_D8]
0x14004be6f  cmp     eax, 0FFFFFFFFh
0x14004be72  jz      loc_14004BF3F
0x14004be78  mov     edi, [rsp+110h+var_DC]
0x14004be7c  inc     eax
0x14004be7e  jmp     loc_14004BC3C
0x14004be83  cmp     eax, 80000005h
0x14004be88  jz      short loc_14004BE95
0x14004be8a  cmp     eax, 0C0000023h
0x14004be8f  jnz     loc_14004BF34
0x14004be95  mov     edi, [rsp+110h+var_E0]
0x14004be99  mov     [rsp+110h+var_DC], edi
0x14004be9d  test    rsi, rsi
0x14004bea0  jz      short loc_14004BEAA
0x14004bea2  mov     rcx, rsi
0x14004bea5  call    SrvNetWskNotifyCleanupProviderContext
0x14004beaa  mov     rdx, rdi
0x14004bead  mov     ecx, 102h
0x14004beb2  mov     r8d, 64614153h
0x14004beb8  call    SrvNetAllocatePoolWithTag
0x14004bebd  mov     [rbp+57h+var_C0], rax
0x14004bec1  mov     rsi, rax
0x14004bec4  test    rax, rax
0x14004bec7  jz      loc_14004C063
0x14004becd  mov     eax, [rsp+110h+var_D8]
0x14004bed1  jmp     loc_14004BC40
0x14004bed6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004bedd  cmp     rcx, r14
0x14004bee0  jz      loc_14004C091
0x14004bee6  mov     eax, [rcx+2Ch]
0x14004bee9  test    al, 20h
0x14004beeb  jz      loc_14004C091
0x14004bef1  cmp     byte ptr [rcx+29h], 1
0x14004bef5  jb      loc_14004C091
0x14004befb  mov     edx, 0Dh
0x14004bf00  jmp     loc_14004C081
0x14004bf05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004bf0c  cmp     rcx, r14
0x14004bf0f  jz      loc_14004C091
0x14004bf15  mov     eax, [rcx+2Ch]
0x14004bf18  test    al, 20h
0x14004bf1a  jz      loc_14004C091
0x14004bf20  cmp     byte ptr [rcx+29h], 1
0x14004bf24  jb      loc_14004C091
0x14004bf2a  mov     edx, 0Eh
0x14004bf2f  jmp     loc_14004C081
0x14004bf34  cmp     eax, 8000001Ah
0x14004bf39  jnz     loc_14004C0A0
0x14004bf3f  mov     edi, ecx
0x14004bf41  test    r13d, r13d
0x14004bf44  jz      loc_14004C0A0
0x14004bf4a  mov     edx, r13d; ullMultiplier
0x14004bf4d  lea     r8, [rbp+57h+pullResult]; pullResult
0x14004bf51  mov     ecx, 8; ullMultiplicand
0x14004bf56  call    RtlULongLongMult
0x14004bf5b  mov     edi, eax
  ... truncated ...
```
