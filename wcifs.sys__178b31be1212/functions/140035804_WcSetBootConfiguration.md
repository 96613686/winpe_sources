# WcSetBootConfiguration

- ea: `0x140035804`
- end: `0x140035ec8`
- name: `WcSetBootConfiguration`
- size: `1732`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400351b4`

## callees

- `0x140001c44`
- `0x1400020c4`
- `0x140004198`
- `0x140007c60`
- `0x140035804`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400358ef`
- `ntoskrnl!ZwOpenKey` at `0x140035ae4`
- `ntoskrnl!ZwOpenKey` at `0x140035cff`
- `ntoskrnl!ZwOpenKey` at `0x1400358ef`
- `ntoskrnl!ZwOpenKey` at `0x140035ae4`
- `ntoskrnl!ZwOpenKey` at `0x140035cff`
- `ntoskrnl!ZwClose` at `0x140035e44`
- `ntoskrnl!ZwClose` at `0x140035e5a`
- `ntoskrnl!ZwClose` at `0x140035e70`
- `ntoskrnl!ZwClose` at `0x140035e44`
- `ntoskrnl!ZwClose` at `0x140035e5a`
- `ntoskrnl!ZwClose` at `0x140035e70`
- `ntoskrnl!ZwQueryValueKey` at `0x140035993`
- `ntoskrnl!ZwQueryValueKey` at `0x140035b4e`
- `ntoskrnl!ZwQueryValueKey` at `0x140035c1f`
- `ntoskrnl!ZwQueryValueKey` at `0x140035d6c`
- `ntoskrnl!ZwQueryValueKey` at `0x140035993`
- `ntoskrnl!ZwQueryValueKey` at `0x140035b4e`
- `ntoskrnl!ZwQueryValueKey` at `0x140035c1f`
- `ntoskrnl!ZwQueryValueKey` at `0x140035d6c`
- `ntoskrnl!RtlGUIDFromString` at `0x140035a6c`
- `ntoskrnl!RtlGUIDFromString` at `0x140035a6c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140035bf1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140035bf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e92`

## string_xrefs

- `0x14003589f`: `ReparseTag`

## pseudocode

```c
__int64 __fastcall WcSetBootConfiguration(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  NTSTATUS v2; // ebx
  _BYTE *v3; // r14
  int v4; // r9d
  int v5; // edx
  NTSTATUS v6; // eax
  int v7; // r9d
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  char v14; // [rsp+30h] [rbp-D0h]
  char v15; // [rsp+30h] [rbp-D0h]
  NTSTATUS v16; // [rsp+38h] [rbp-C8h]
  char v17; // [rsp+38h] [rbp-C8h]
  __int64 ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING GuidString; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v22; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v25[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v26; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v27; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v28[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING v29; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+100h] [rbp+0h] BYREF
  int v31; // [rsp+104h] [rbp+4h]
  USHORT v32; // [rsp+108h] [rbp+8h]
  _DWORD v33[29]; // [rsp+10Ch] [rbp+Ch] BYREF

  ObjectAttributes.ObjectName = a1;
  v25[0] = 1835034;
  v25[1] = L"BootContainer";
  v28[0] = 655368;
  v28[1] = L"Hvsi";
  *(_QWORD *)&v29.Length = 2490404;
  v29.Buffer = L"WCIFSContainerMode";
  *(_QWORD *)&ValueName.Length = 2359330;
  ValueName.Buffer = L"BootContainerGuid";
  v26.Buffer = L"InstanceName";
  v27.Buffer = L"ReparseTag";
  KeyHandle = 0;
  Handle = 0;
  v22 = 0;
  LODWORD(ResultLength) = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&v26.Length = 1703960;
  *(_QWORD *)&v27.Length = 1441812;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  GuidString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v3 = KeyValueInformation;
    v6 = ZwQueryValueKey(
           KeyHandle,
           &ValueName,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x74u,
           (PULONG)&ResultLength);
    v2 = v6;
    if ( v6 < 0 )
    {
      if ( v6 == -1073741772 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v16 = v6;
      v4 = 72;
      v14 = -44;
      goto LABEL_10;
    }
    if ( v31 != 1 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v17 = v31;
      v7 = 73;
      v15 = -37;
      goto LABEL_14;
    }
    GuidString.Buffer = (PWSTR)v33;
    GuidString.MaximumLength = v32;
    GuidString.Length = v32 - 2;
    v2 = RtlGUIDFromString(&GuidString, &Guid);
    if ( v2 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v16 = v2;
      v4 = 74;
      v14 = -18;
      goto LABEL_10;
    }
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v25;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    v2 = v8;
    if ( v8 < 0 )
    {
      if ( v8 == -1073741772 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v16 = v8;
      v4 = 75;
      v14 = 3;
      goto LABEL_10;
    }
    v9 = ZwQueryValueKey(Handle, &v26, KeyValuePartialInformation, KeyValueInformation, 0x74u, (PULONG)&ResultLength);
    v2 = v9;
    if ( v9 < 0 )
    {
      if ( v9 == -1073741772 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v16 = v9;
      v4 = 76;
      v14 = 23;
      goto LABEL_10;
    }
    if ( v31 != 1 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v17 = v31;
      v7 = 77;
      v15 = 30;
      goto LABEL_14;
    }
    GuidString.Buffer = (PWSTR)v33;
    GuidString.MaximumLength = v32;
    GuidString.Length = v32 - 2;
    RtlCopyUnicodeString(&DestinationString, &GuidString);
    v10 = ZwQueryValueKey(Handle, &v27, KeyValuePartialInformation, KeyValueInformation, 0x74u, (PULONG)&ResultLength);
    v2 = v10;
    if ( v10 < 0 )
    {
      if ( v10 == -1073741772 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v16 = v10;
      v4 = 78;
      v14 = 54;
      goto LABEL_10;
    }
    if ( v31 == 4 )
    {
      dword_14000E6AC = v33[0];
      if ( v33[0] == -2147483624 )
      {
        dword_14000E6B0 = -1610612697;
      }
      else if ( v33[0] == -1879044072 )
      {
        dword_14000E6B0 = -1610608601;
      }
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v28;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v11 = ZwOpenKey(&v22, 0x20019u, &ObjectAttributes);
      v2 = v11;
      if ( v11 < 0 )
      {
        if ( v11 == -1073741772 )
        {
          v2 = 0;
          goto LABEL_56;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_56;
        v16 = v11;
        v4 = 80;
        v14 = 94;
        goto LABEL_10;
      }
      v12 = ZwQueryValueKey(v22, &v29, KeyValuePartialInformation, KeyValueInformation, 0x74u, (PULONG)&ResultLength);
      v2 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -1073741772 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_56;
        v16 = v12;
        v4 = 81;
        v14 = 116;
LABEL_10:
        LOBYTE(v5) = 2;
        goto LABEL_5;
      }
      if ( v31 == 4 )
      {
        if ( v33[0] == 1 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v5) = 4;
            WPP_RECORDER_SF_sD(
              wil_details_featureDescriptors_a->DeviceExtension,
              v5,
              1,
              83,
              (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
              128);
          }
          HIBYTE(qword_14000E6A2) = 1;
        }
        goto LABEL_56;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v17 = v31;
      v7 = 82;
      v15 = 123;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v17 = v31;
      v7 = 79;
      v15 = 61;
    }
LABEL_14:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_sDD(
      wil_details_featureDescriptors_a->DeviceExtension,
      v5,
      1,
      v7,
      (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
      v15,
      v17);
    goto LABEL_56;
  }
  v3 = 0;
  if ( v1 != -1073741772 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = v1;
    v4 = 71;
    v14 = -68;
    v5 = 2;
LABEL_5:
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v5,
      1,
      v4,
      (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
      v14,
      v16,
      ResultLength);
  }
LABEL_56:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v22 )
    ZwClose(v22);
  if ( v3 && v3 != KeyValueInformation )
    ExFreePoolWithTag(v3, 0x6E664357u);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140035804  mov     [rsp-8+arg_8], rbx
0x140035809  mov     [rsp-8+arg_10], rsi
0x14003580e  push    rbp
0x14003580f  push    rdi
0x140035810  push    r14
0x140035812  lea     rbp, [rsp-90h]
0x14003581a  sub     rsp, 190h
0x140035821  mov     rax, cs:__security_cookie
0x140035828  xor     rax, rsp
0x14003582b  mov     [rbp+0A0h+var_20], rax
0x140035832  xorps   xmm0, xmm0
0x140035835  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rcx
0x140035839  lea     rax, aBootcontainer; "BootContainer"
0x140035840  mov     [rbp+0A0h+var_F0], 1C001Ah
0x140035848  mov     [rbp+0A0h+var_E8], rax
0x14003584c  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x140035851  lea     rax, aHvsi; "Hvsi"
0x140035858  mov     [rbp+0A0h+var_C0], 0A0008h
0x140035860  mov     [rbp+0A0h+var_B8], rax
0x140035864  lea     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x140035869  lea     rax, aWcifscontainer; "WCIFSContainerMode"
0x140035870  mov     qword ptr [rbp+0A0h+var_B0.Length], 260024h
0x140035878  mov     [rbp+0A0h+var_B0.Buffer], rax
0x14003587c  mov     edx, 20019h; DesiredAccess
0x140035881  lea     rax, aBootcontainerg; "BootContainerGuid"
0x140035888  mov     qword ptr [rbp+0A0h+ValueName.Length], 240022h
0x140035890  mov     [rbp+0A0h+ValueName.Buffer], rax
0x140035894  lea     rax, aInstancename; "InstanceName"
0x14003589b  mov     [rbp+0A0h+var_E0.Buffer], rax
0x14003589f  lea     rax, aReparsetag; "ReparseTag"
0x1400358a6  mov     [rbp+0A0h+var_D0.Buffer], rax
0x1400358aa  xor     eax, eax
0x1400358ac  mov     [rsp+1A0h+KeyHandle], rax
0x1400358b1  mov     [rsp+1A0h+Handle], rax
0x1400358b6  mov     [rsp+1A0h+var_138], rax
0x1400358bb  mov     dword ptr [rsp+1A0h+var_160], eax
0x1400358bf  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rax
0x1400358c4  mov     qword ptr [rbp+0A0h+var_E0.Length], 1A0018h
0x1400358cc  mov     qword ptr [rbp+0A0h+var_D0.Length], 160014h
0x1400358d4  mov     qword ptr [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1400358dd  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x1400358e5  movups  xmmword ptr [rsp+1A0h+GuidString.Length], xmm0
0x1400358ea  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400358ef  call    cs:__imp_ZwOpenKey
0x1400358f6  nop     dword ptr [rax+rax+00h]
0x1400358fb  mov     ebx, eax
0x1400358fd  test    eax, eax
0x1400358ff  jns     short loc_140035968
0x140035901  xor     r14d, r14d
0x140035904  cmp     eax, 0C0000034h
0x140035909  jz      loc_140035E3A
0x14003590f  lea     rax, WPP_RECORDER_INITIALIZED
0x140035916  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003591d  jz      loc_140035E3A
0x140035923  mov     [rsp+1A0h+var_168], ebx
0x140035927  lea     r9d, [r14+47h]
0x14003592b  mov     dword ptr [rsp+1A0h+var_170], 0CBCh
0x140035933  lea     edx, [r14+2]
0x140035937  lea     r8d, [r14+1]
0x14003593b  mov     rcx, cs:wil_details_featureDescriptors_a
0x140035942  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140035949  mov     [rsp+1A0h+ResultLength], rax
0x14003594e  lea     rax, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140035955  mov     qword ptr [rsp+1A0h+Length], rax
0x14003595a  mov     rcx, [rcx+40h]
0x14003595e  call    WPP_RECORDER_SF_sDd
0x140035963  jmp     loc_140035E3A
0x140035968  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x14003596d  lea     rax, [rsp+1A0h+var_160]
0x140035972  mov     [rsp+1A0h+ResultLength], rax; ResultLength
0x140035977  lea     r9, [rbp+0A0h+KeyValueInformation]; KeyValueInformation
0x14003597b  mov     esi, 2
0x140035980  mov     [rsp+1A0h+Length], 74h ; 't'; Length
0x140035988  mov     r8d, esi; KeyValueInformationClass
0x14003598b  lea     rdx, [rbp+0A0h+ValueName]; ValueName
0x14003598f  lea     r14, [rbp+0A0h+KeyValueInformation]
0x140035993  call    cs:__imp_ZwQueryValueKey
0x14003599a  nop     dword ptr [rax+rax+00h]
0x14003599f  mov     ebx, eax
0x1400359a1  test    eax, eax
0x1400359a3  jns     short loc_1400359E0
0x1400359a5  cmp     eax, 0C0000034h
0x1400359aa  jz      loc_140035E3A
0x1400359b0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400359b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400359be  jz      loc_140035E3A
0x1400359c4  mov     [rsp+1A0h+var_168], ebx
0x1400359c8  lea     r9d, [rsi+46h]
0x1400359cc  mov     dword ptr [rsp+1A0h+var_170], 0CD4h
0x1400359d4  lea     r8d, [rsi-1]
0x1400359d8  mov     dl, sil
0x1400359db  jmp     loc_14003593B
0x1400359e0  mov     ecx, [rbp+0A0h+var_9C]
0x1400359e3  mov     edi, 1
0x1400359e8  cmp     ecx, edi
0x1400359ea  jz      short loc_140035A43
0x1400359ec  lea     rax, WPP_RECORDER_INITIALIZED
0x1400359f3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400359fa  jz      loc_140035E3A
0x140035a00  mov     [rsp+1A0h+var_168], ecx
0x140035a04  lea     r9d, [rdi+48h]
0x140035a08  mov     dword ptr [rsp+1A0h+var_170], 0CDBh
0x140035a10  mov     rcx, cs:wil_details_featureDescriptors_a
0x140035a17  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140035a1e  mov     [rsp+1A0h+ResultLength], rax
0x140035a23  mov     r8d, edi
0x140035a26  lea     rax, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140035a2d  mov     dl, sil
0x140035a30  mov     qword ptr [rsp+1A0h+Length], rax
0x140035a35  mov     rcx, [rcx+40h]
0x140035a39  call    WPP_RECORDER_SF_sDD
0x140035a3e  jmp     loc_140035E3A
0x140035a43  movzx   ecx, [rbp+0A0h+var_98]
0x140035a47  lea     rax, [rbp+0A0h+var_94]
0x140035a4b  mov     [rsp+1A0h+GuidString.Buffer], rax
0x140035a50  lea     rdx, Guid; Guid
0x140035a57  movzx   eax, cx
0x140035a5a  mov     [rsp+1A0h+GuidString.MaximumLength], cx
0x140035a5f  sub     ax, si
0x140035a62  lea     rcx, [rsp+1A0h+GuidString]; GuidString
0x140035a67  mov     [rsp+1A0h+GuidString.Length], ax
0x140035a6c  call    cs:__imp_RtlGUIDFromString
0x140035a73  nop     dword ptr [rax+rax+00h]
0x140035a78  mov     ebx, eax
0x140035a7a  test    eax, eax
0x140035a7c  jns     short loc_140035AAC
0x140035a7e  lea     rax, WPP_RECORDER_INITIALIZED
0x140035a85  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035a8c  jz      loc_140035E3A
0x140035a92  mov     [rsp+1A0h+var_168], ebx
0x140035a96  mov     r9d, 4Ah ; 'J'
0x140035a9c  mov     dword ptr [rsp+1A0h+var_170], 0CEEh
0x140035aa4  mov     r8d, edi
0x140035aa7  jmp     loc_1400359D8
0x140035aac  mov     rax, [rsp+1A0h+KeyHandle]
0x140035ab1  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x140035ab6  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rax
0x140035abb  lea     rcx, [rsp+1A0h+Handle]; KeyHandle
0x140035ac0  lea     rax, [rbp+0A0h+var_F0]
0x140035ac4  mov     [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x140035acc  xorps   xmm0, xmm0
0x140035acf  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x140035ad3  mov     edx, 20019h; DesiredAccess
0x140035ad8  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x140035adf  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140035ae4  call    cs:__imp_ZwOpenKey
0x140035aeb  nop     dword ptr [rax+rax+00h]
0x140035af0  mov     ebx, eax
0x140035af2  test    eax, eax
0x140035af4  jns     short loc_140035B2C
0x140035af6  cmp     eax, 0C0000034h
0x140035afb  jz      loc_140035E3A
0x140035b01  lea     rax, WPP_RECORDER_INITIALIZED
0x140035b08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035b0f  jz      loc_140035E3A
0x140035b15  mov     [rsp+1A0h+var_168], ebx
0x140035b19  mov     r9d, 4Bh ; 'K'
0x140035b1f  mov     dword ptr [rsp+1A0h+var_170], 0D03h
0x140035b27  jmp     loc_140035AA4
0x140035b2c  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x140035b31  lea     rax, [rsp+1A0h+var_160]
0x140035b36  mov     [rsp+1A0h+ResultLength], rax; ResultLength
0x140035b3b  lea     r9, [rbp+0A0h+KeyValueInformation]; KeyValueInformation
0x140035b3f  mov     r8d, esi; KeyValueInformationClass
0x140035b42  mov     [rsp+1A0h+Length], 74h ; 't'; Length
0x140035b4a  lea     rdx, [rbp+0A0h+var_E0]; ValueName
0x140035b4e  call    cs:__imp_ZwQueryValueKey
0x140035b55  nop     dword ptr [rax+rax+00h]
0x140035b5a  mov     ebx, eax
0x140035b5c  test    eax, eax
0x140035b5e  jns     short loc_140035B96
0x140035b60  cmp     eax, 0C0000034h
0x140035b65  jz      loc_140035E3A
0x140035b6b  lea     rax, WPP_RECORDER_INITIALIZED
0x140035b72  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035b79  jz      loc_140035E3A
0x140035b7f  mov     [rsp+1A0h+var_168], ebx
0x140035b83  mov     r9d, 4Ch ; 'L'
0x140035b89  mov     dword ptr [rsp+1A0h+var_170], 0D17h
0x140035b91  jmp     loc_140035AA4
0x140035b96  mov     ecx, [rbp+0A0h+var_9C]
0x140035b99  cmp     ecx, edi
0x140035b9b  jz      short loc_140035BC8
0x140035b9d  lea     rax, WPP_RECORDER_INITIALIZED
0x140035ba4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035bab  jz      loc_140035E3A
0x140035bb1  mov     [rsp+1A0h+var_168], ecx
0x140035bb5  mov     r9d, 4Dh ; 'M'
0x140035bbb  mov     dword ptr [rsp+1A0h+var_170], 0D1Eh
0x140035bc3  jmp     loc_140035A10
0x140035bc8  movzx   ecx, [rbp+0A0h+var_98]
0x140035bcc  lea     rax, [rbp+0A0h+var_94]
0x140035bd0  mov     [rsp+1A0h+GuidString.Buffer], rax
0x140035bd5  lea     rdx, [rsp+1A0h+GuidString]; SourceString
0x140035bda  movzx   eax, cx
0x140035bdd  mov     [rsp+1A0h+GuidString.MaximumLength], cx
0x140035be2  sub     ax, si
0x140035be5  lea     rcx, DestinationString; DestinationString
0x140035bec  mov     [rsp+1A0h+GuidString.Length], ax
0x140035bf1  call    cs:__imp_RtlCopyUnicodeString
0x140035bf8  nop     dword ptr [rax+rax+00h]
0x140035bfd  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x140035c02  lea     rax, [rsp+1A0h+var_160]
0x140035c07  mov     [rsp+1A0h+ResultLength], rax; ResultLength
0x140035c0c  lea     r9, [rbp+0A0h+KeyValueInformation]; KeyValueInformation
0x140035c10  mov     r8d, esi; KeyValueInformationClass
0x140035c13  mov     [rsp+1A0h+Length], 74h ; 't'; Length
0x140035c1b  lea     rdx, [rbp+0A0h+var_D0]; ValueName
0x140035c1f  call    cs:__imp_ZwQueryValueKey
0x140035c26  nop     dword ptr [rax+rax+00h]
0x140035c2b  mov     ebx, eax
0x140035c2d  test    eax, eax
0x140035c2f  jns     short loc_140035C67
0x140035c31  cmp     eax, 0C0000034h
0x140035c36  jz      loc_140035E3A
0x140035c3c  lea     rax, WPP_RECORDER_INITIALIZED
0x140035c43  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035c4a  jz      loc_140035E3A
0x140035c50  mov     [rsp+1A0h+var_168], ebx
0x140035c54  mov     r9d, 4Eh ; 'N'
0x140035c5a  mov     dword ptr [rsp+1A0h+var_170], 0D36h
0x140035c62  jmp     loc_140035AA4
0x140035c67  mov     ecx, [rbp+0A0h+var_9C]
0x140035c6a  cmp     ecx, 4
0x140035c6d  jz      short loc_140035C9A
0x140035c6f  lea     rax, WPP_RECORDER_INITIALIZED
0x140035c76  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035c7d  jz      loc_140035E3A
0x140035c83  mov     [rsp+1A0h+var_168], ecx
0x140035c87  mov     r9d, 4Fh ; 'O'
0x140035c8d  mov     dword ptr [rsp+1A0h+var_170], 0D3Dh
0x140035c95  jmp     loc_140035A10
0x140035c9a  mov     eax, [rbp+0A0h+var_94]
0x140035c9d  mov     cs:dword_14000E6AC, eax
0x140035ca3  cmp     eax, 80000018h
0x140035ca8  jnz     short loc_140035CB6
0x140035caa  mov     cs:dword_14000E6B0, 0A0000027h
0x140035cb4  jmp     short loc_140035CC7
0x140035cb6  cmp     eax, 90001018h
0x140035cbb  jnz     short loc_140035CC7
0x140035cbd  mov     cs:dword_14000E6B0, 0A0001027h
0x140035cc7  mov     rax, [rsp+1A0h+KeyHandle]
0x140035ccc  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x140035cd1  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rax
0x140035cd6  lea     rcx, [rsp+1A0h+var_138]; KeyHandle
0x140035cdb  lea     rax, [rbp+0A0h+var_C0]
0x140035cdf  mov     [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x140035ce7  xorps   xmm0, xmm0
0x140035cea  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x140035cee  mov     edx, 20019h; DesiredAccess
0x140035cf3  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x140035cfa  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140035cff  call    cs:__imp_ZwOpenKey
0x140035d06  nop     dword ptr [rax+rax+00h]
0x140035d0b  mov     ebx, eax
0x140035d0d  test    eax, eax
0x140035d0f  jns     short loc_140035D4A
0x140035d11  cmp     eax, 0C0000034h
0x140035d16  jz      short loc_140035D43
0x140035d18  lea     rax, WPP_RECORDER_INITIALIZED
0x140035d1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035d26  jz      loc_140035E3A
0x140035d2c  mov     [rsp+1A0h+var_168], ebx
0x140035d30  mov     r9d, 50h ; 'P'
0x140035d36  mov     dword ptr [rsp+1A0h+var_170], 0D5Eh
0x140035d3e  jmp     loc_140035AA4
0x140035d43  xor     ebx, ebx
0x140035d45  jmp     loc_140035E3A
0x140035d4a  mov     rcx, [rsp+1A0h+var_138]; KeyHandle
0x140035d4f  lea     rax, [rsp+1A0h+var_160]
0x140035d54  mov     [rsp+1A0h+ResultLength], rax; ResultLength
0x140035d59  lea     r9, [rbp+0A0h+KeyValueInformation]; KeyValueInformation
0x140035d5d  mov     r8d, esi; KeyValueInformationClass
0x140035d60  mov     [rsp+1A0h+Length], 74h ; 't'; Length
0x140035d68  lea     rdx, [rbp+0A0h+var_B0]; ValueName
0x140035d6c  call    cs:__imp_ZwQueryValueKey
0x140035d73  nop     dword ptr [rax+rax+00h]
0x140035d78  mov     ebx, eax
0x140035d7a  test    eax, eax
0x140035d7c  jns     short loc_140035DB4
0x140035d7e  cmp     eax, 0C0000034h
0x140035d83  jz      loc_140035E3A
0x140035d89  lea     rax, WPP_RECORDER_INITIALIZED
0x140035d90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035d97  jz      loc_140035E3A
0x140035d9d  mov     [rsp+1A0h+var_168], ebx
0x140035da1  mov     r9d, 51h ; 'Q'
0x140035da7  mov     dword ptr [rsp+1A0h+var_170], 0D74h
0x140035daf  jmp     loc_140035AA4
0x140035db4  mov     ecx, [rbp+0A0h+var_9C]
0x140035db7  cmp     ecx, 4
0x140035dba  jz      short loc_140035DE3
0x140035dbc  lea     rax, WPP_RECORDER_INITIALIZED
0x140035dc3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035dca  jz      short loc_140035E3A
0x140035dcc  mov     [rsp+1A0h+var_168], ecx
0x140035dd0  mov     r9d, 52h ; 'R'
0x140035dd6  mov     dword ptr [rsp+1A0h+var_170], 0D7Bh
0x140035dde  jmp     loc_140035A10
0x140035de3  cmp     [rbp+0A0h+var_94], edi
  ... truncated ...
```
