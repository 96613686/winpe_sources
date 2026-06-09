# VmsPtNicAddConfiguredNicsToIoctlBuffer

- ea: `0x14003ae48`
- end: `0x14003b434`
- name: `VmsPtNicAddConfiguredNicsToIoctlBuffer`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005407c`

## callees

- `0x140027a64`
- `0x14003833c`
- `0x14003a450`
- `0x14003ae48`
- `0x14003b734`
- `0x14003b998`
- `0x14003ba40`
- `0x14003ca6c`
- `0x140054a20`
- `0x140054da0`
- `0x1400721d8`
- `0x14008497c`
- `0x14008d760`
- `0x1400a7994`
- `0x1400a7c8c`
- `0x1401bbc40`
- `0x1401bbea0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14003aee0`
- `ntoskrnl!ZwOpenKey` at `0x14003b027`
- `ntoskrnl!ZwOpenKey` at `0x14003aee0`
- `ntoskrnl!ZwOpenKey` at `0x14003b027`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003afa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b3c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003afa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b3c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003b0fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003b126`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003b0fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003b126`

## string_xrefs

- `0x14003b1b9`: `NT_SUCCESS(tempStatus)`
- `0x14003b2bd`: `VmsPtNicAddConfiguredNicsToIoctlBuffer`

## pseudocode

```c
__int64 __fastcall VmsPtNicAddConfiguredNicsToIoctlBuffer(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v4; // esi
  __int64 v5; // r15
  unsigned int v7; // r14d
  int v8; // r12d
  PCWSTR *v9; // r13
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // edi
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // edi
  int v19; // edx
  int v20; // r8d
  unsigned int i; // edi
  int v22; // eax
  int v23; // edx
  __int64 v24; // rdx
  int v25; // edx
  int v26; // edx
  __int64 v28; // [rsp+B0h] [rbp-80h] BYREF
  int v29; // [rsp+B8h] [rbp-78h] BYREF
  int v30; // [rsp+BCh] [rbp-74h]
  unsigned int v31; // [rsp+C0h] [rbp-70h]
  PVOID P; // [rsp+C8h] [rbp-68h]
  void *v33; // [rsp+D0h] [rbp-60h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-50h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v37; // [rsp+120h] [rbp-10h]
  __int64 v38; // [rsp+128h] [rbp-8h]
  struct _UNICODE_STRING v39; // [rsp+130h] [rbp+0h] BYREF
  struct _UNICODE_STRING v40; // [rsp+140h] [rbp+10h] BYREF
  char v41; // [rsp+150h] [rbp+20h] BYREF

  v4 = 0;
  ObjectAttributes.RootDirectory = ::KeyHandle;
  v5 = a2;
  v37 = a3;
  v38 = a2;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&VmsOmNicsConfigKeyStr;
  v31 = a4;
  KeyHandle = 0;
  P = 0;
  v7 = a4;
  v33 = 0;
  v8 = 0;
  v28 = 0;
  v9 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  v12 = v10;
  if ( v10 )
  {
    if ( v10 != -1073741772 )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_dqd(
        VmsIfrLog,
        v11,
        20,
        25,
        (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids,
        63,
        (char)&ObjectAttributes,
        v10);
      if ( v12 >= 0 )
        goto LABEL_6;
      if ( v12 != -1073741772 )
        WPP_RECORDER_SF_Zdd(
          VmsIfrLog,
          v13,
          v14,
          26,
          (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids,
          (__int64)&VmsOmNicsConfigKeyStr,
          63,
          v12);
    }
    return (unsigned int)v8;
  }
  while ( 1 )
  {
LABEL_6:
    v30 = v4;
    DestinationString.Buffer = (wchar_t *)&v41;
    v29 = 0;
    *(_QWORD *)&DestinationString.Length = 0x2000000;
    if ( v9 )
    {
      ExFreePoolWithTag(v9, 0);
      P = 0;
    }
    v15 = VmsCsKeyEnumerate(KeyHandle, (unsigned __int16)v4);
    v9 = (PCWSTR *)P;
    if ( v15 < 0 )
      break;
    RtlUnicodeStringPrintf(&DestinationString, L"%wZ\\%wZ", &VmsOmNicsConfigKeyStr, P);
    ObjectAttributes.RootDirectory = ::KeyHandle;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = ZwOpenKey(&v33, 0xF003Fu, &ObjectAttributes);
    v18 = v16;
    if ( !v16 )
      goto LABEL_21;
    if ( v16 == -1073741772 )
      goto LABEL_33;
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_dqd(
      VmsIfrLog,
      v17,
      20,
      25,
      (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids,
      63,
      (char)&ObjectAttributes,
      v16);
    if ( v18 < 0 )
    {
      if ( v18 != -1073741772 )
        WPP_RECORDER_SF_Zdd(
          VmsIfrLog,
          v19,
          v20,
          26,
          (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids,
          (__int64)&DestinationString,
          63,
          v18);
    }
    else
    {
LABEL_21:
      if ( (int)VmsCsAttrValueReadULong(v33, &VmsOmNicTypeStr, &v29) >= 0 && v29 == 2 )
      {
        v40 = 0;
        RtlInitUnicodeString(&v40, v9[1]);
        for ( i = 0; i < v7; ++i )
        {
          v39 = 0;
          RtlInitUnicodeString(&v39, (PCWSTR)(v37 + ((unsigned __int64)i << 8)));
          if ( v40.Length == v39.Length && !memcmp(v40.Buffer, v39.Buffer, v40.Length) )
            goto LABEL_32;
        }
        if ( (int)VmsPtNicGetInfoFromRegistry(v9, 0) >= 0 )
        {
          v22 = LibIoctlAddArrayRecordElement(v5, 0, &v28);
          v8 = v22;
          if ( v22 >= 0 )
          {
            v24 = v28;
          }
          else
          {
            if ( v22 != -2147483643 && v22 != -1073741789 )
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_d(VmsIfrLog, v23, 20, 70, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v22);
              goto LABEL_36;
            }
            v24 = 0;
            v28 = 0;
          }
          if ( v24 )
          {
            if ( (int)VmsPtNicGetInfoFromRegistry(v9, v24) >= 0 )
            {
              *(_BYTE *)(v28 + 780) = 1;
              *(_DWORD *)(v28 + 772) = 2;
              if ( (a1 & 1) != 0 )
              {
                WPP_RECORDER_SF_sddsSSdLLddSSdSS(
                  v28 + 1300,
                  v28 + 1038,
                  v28 + 782,
                  72,
                  (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
                  (__int64)"onecore\\vm\\dv\\net\\nvsp\\driver\\pt\\vmspt.c",
                  236,
                  (a1 >> 2) & 0x7F,
                  (__int64)"VmsPtNicAddConfiguredNicsToIoctlBuffer",
                  v28,
                  v28 + 256,
                  *(_WORD *)(v28 + 768),
                  *(_DWORD *)(v28 + 772),
                  *(_DWORD *)(v28 + 776),
                  *(_BYTE *)(v28 + 780),
                  *(_BYTE *)(v28 + 781),
                  v28 + 782,
                  v28 + 1038,
                  *(_DWORD *)(v28 + 1296),
                  v28 + 1300,
                  v28 + 1812);
                WPP_RECORDER_SF_sdds_MAC__MAC__MAC_DdS(
                  v28,
                  v28 + 2336,
                  v28 + 2330,
                  73,
                  (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
                  (__int64)"onecore\\vm\\dv\\net\\nvsp\\driver\\pt\\vmspt.c",
                  237,
                  (a1 >> 2) & 0x7F,
                  (__int64)"VmsPtNicAddConfiguredNicsToIoctlBuffer",
                  v28 + 2324,
                  v28 + 2330,
                  v28 + 2336,
                  *(_DWORD *)(v28 + 2344),
                  *(_DWORD *)(v28 + 2348),
                  v28 + 2352);
                v4 = v30;
                v7 = v31;
                v5 = v38;
              }
            }
            else
            {
              WPP_RECORDER_SF_s(
                VmsIfrLog,
                v25,
                19,
                71,
                (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
                (__int64)"NT_SUCCESS(tempStatus)");
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
            }
          }
        }
      }
LABEL_32:
      VmsCsKeyClose(v33);
    }
LABEL_33:
    LOWORD(v4) = v4 + 1;
  }
  VmsCsKeyClose(KeyHandle);
LABEL_36:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v8 < 0 )
  {
    LOBYTE(v26) = 2;
    WPP_RECORDER_SF_qqdd(
      VmsIfrLog,
      v26,
      20,
      74,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      v5,
      v37,
      v7,
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003ae48  mov     [rsp-8+arg_18], rbx
0x14003ae4d  push    rbp
0x14003ae4e  push    rsi
0x14003ae4f  push    rdi
0x14003ae50  push    r12
0x14003ae52  push    r13
0x14003ae54  push    r14
0x14003ae56  push    r15
0x14003ae58  lea     rbp, [rsp-230h]
0x14003ae60  sub     rsp, 360h
0x14003ae67  mov     rax, cs:__security_cookie
0x14003ae6e  xor     rax, rsp
0x14003ae71  mov     [rbp+260h+var_40], rax
0x14003ae78  mov     rax, cs:KeyHandle
0x14003ae7f  xor     esi, esi
0x14003ae81  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x14003ae85  mov     r15, rdx
0x14003ae88  lea     rax, VmsOmNicsConfigKeyStr
0x14003ae8f  mov     [rbp+260h+var_270], r8
0x14003ae93  mov     [rbp+260h+var_268], rdx
0x14003ae97  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x14003ae9b  mov     rbx, rcx
0x14003ae9e  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x14003aea2  xorps   xmm0, xmm0
0x14003aea5  mov     [rbp+260h+var_2D0], r9d
0x14003aea9  mov     edx, 0F003Fh; DesiredAccess
0x14003aeae  mov     [rbp+260h+KeyHandle], rsi
0x14003aeb2  lea     rcx, [rbp+260h+KeyHandle]; KeyHandle
0x14003aeb6  mov     [rbp+260h+P], rsi
0x14003aeba  mov     r14d, r9d
0x14003aebd  mov     [rbp+260h+var_2C0], rsi
0x14003aec1  mov     r12d, esi
0x14003aec4  mov     [rbp+260h+var_2E0], rsi
0x14003aec8  mov     r13d, esi
0x14003aecb  mov     qword ptr [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x14003aed3  mov     qword ptr [rbp+260h+ObjectAttributes.Attributes], 240h
0x14003aedb  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003aee0  call    cs:__imp_ZwOpenKey
0x14003aee7  nop     dword ptr [rax+rax+00h]
0x14003aeec  lea     rcx, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x14003aef3  mov     edi, eax
0x14003aef5  test    eax, eax
0x14003aef7  jz      loc_14003AF81
0x14003aefd  cmp     eax, 0C0000034h
0x14003af02  jz      loc_14003B406
0x14003af08  mov     [rsp+390h+var_358], eax
0x14003af0c  lea     r9d, [rsi+19h]
0x14003af10  lea     rax, [rbp+260h+ObjectAttributes]
0x14003af14  mov     dl, 2
0x14003af16  mov     [rsp+390h+var_360], rax
0x14003af1b  lea     r8d, [rsi+14h]
0x14003af1f  mov     dword ptr [rsp+390h+var_368], 0F003Fh
0x14003af27  mov     [rsp+390h+var_370], rcx
0x14003af2c  mov     rcx, cs:VmsIfrLog
0x14003af33  call    WPP_RECORDER_SF_dqd
0x14003af38  test    edi, edi
0x14003af3a  jns     short loc_14003AF81
0x14003af3c  lea     rcx, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x14003af43  cmp     edi, 0C0000034h
0x14003af49  jz      loc_14003B406
0x14003af4f  mov     [rsp+390h+var_358], edi
0x14003af53  lea     rax, VmsOmNicsConfigKeyStr
0x14003af5a  mov     dword ptr [rsp+390h+var_360], 0F003Fh
0x14003af62  lea     r9d, [rsi+1Ah]
0x14003af66  mov     [rsp+390h+var_368], rax
0x14003af6b  mov     [rsp+390h+var_370], rcx
0x14003af70  mov     rcx, cs:VmsIfrLog
0x14003af77  call    WPP_RECORDER_SF_Zdd
0x14003af7c  jmp     loc_14003B406
0x14003af81  mov     [rbp+260h+var_2D4], esi
0x14003af84  lea     rax, [rbp+260h+var_240]
0x14003af88  mov     [rbp+260h+DestinationString.Buffer], rax
0x14003af8c  mov     [rbp+260h+var_2D8], 0
0x14003af93  mov     qword ptr [rbp+260h+DestinationString.Length], 2000000h
0x14003af9b  test    r13, r13
0x14003af9e  jz      short loc_14003AFB9
0x14003afa0  xor     edx, edx; Tag
0x14003afa2  mov     rcx, r13; P
0x14003afa5  call    cs:__imp_ExFreePoolWithTag
0x14003afac  nop     dword ptr [rax+rax+00h]
0x14003afb1  mov     [rbp+260h+P], 0
0x14003afb9  mov     rcx, [rbp+260h+KeyHandle]; KeyHandle
0x14003afbd  lea     r8, [rbp+260h+P]
0x14003afc1  movzx   edx, si; Index
0x14003afc4  call    VmsCsKeyEnumerate
0x14003afc9  mov     r13, [rbp+260h+P]
0x14003afcd  test    eax, eax
0x14003afcf  js      loc_14003B3A6
0x14003afd5  mov     r9, r13
0x14003afd8  lea     r8, VmsOmNicsConfigKeyStr
0x14003afdf  lea     rdx, aWzWz; "%wZ\\%wZ"
0x14003afe6  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x14003afea  call    RtlUnicodeStringPrintf
0x14003afef  mov     rax, cs:KeyHandle
0x14003aff6  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x14003affa  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x14003affe  lea     rcx, [rbp+260h+var_2C0]; KeyHandle
0x14003b002  lea     rax, [rbp+260h+DestinationString]
0x14003b006  mov     qword ptr [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x14003b00e  xorps   xmm0, xmm0
0x14003b011  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x14003b015  mov     edx, 0F003Fh; DesiredAccess
0x14003b01a  mov     qword ptr [rbp+260h+ObjectAttributes.Attributes], 240h
0x14003b022  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003b027  call    cs:__imp_ZwOpenKey
0x14003b02e  nop     dword ptr [rax+rax+00h]
0x14003b033  mov     edi, eax
0x14003b035  test    eax, eax
0x14003b037  jz      loc_14003B0C9
0x14003b03d  cmp     eax, 0C0000034h
0x14003b042  jz      loc_14003B374
0x14003b048  mov     rcx, cs:VmsIfrLog
0x14003b04f  mov     r9d, 19h
0x14003b055  mov     [rsp+390h+var_358], eax
0x14003b059  mov     dl, 2
0x14003b05b  lea     rax, [rbp+260h+ObjectAttributes]
0x14003b05f  mov     [rsp+390h+var_360], rax
0x14003b064  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x14003b06b  lea     r8d, [r9-5]
0x14003b06f  mov     dword ptr [rsp+390h+var_368], 0F003Fh
0x14003b077  mov     [rsp+390h+var_370], rax
0x14003b07c  call    WPP_RECORDER_SF_dqd
0x14003b081  test    edi, edi
0x14003b083  jns     short loc_14003B0C9
0x14003b085  cmp     edi, 0C0000034h
0x14003b08b  jz      loc_14003B374
0x14003b091  mov     rcx, cs:VmsIfrLog
0x14003b098  lea     rax, [rbp+260h+DestinationString]
0x14003b09c  mov     [rsp+390h+var_358], edi
0x14003b0a0  mov     r9d, 1Ah
0x14003b0a6  mov     dword ptr [rsp+390h+var_360], 0F003Fh
0x14003b0ae  mov     [rsp+390h+var_368], rax
0x14003b0b3  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x14003b0ba  mov     [rsp+390h+var_370], rax
0x14003b0bf  call    WPP_RECORDER_SF_Zdd
0x14003b0c4  jmp     loc_14003B374
0x14003b0c9  mov     rcx, [rbp+260h+var_2C0]
0x14003b0cd  lea     r8, [rbp+260h+var_2D8]
0x14003b0d1  lea     rdx, VmsOmNicTypeStr
0x14003b0d8  call    VmsCsAttrValueReadULong
0x14003b0dd  test    eax, eax
0x14003b0df  js      loc_14003B36B
0x14003b0e5  cmp     [rbp+260h+var_2D8], 2
0x14003b0e9  jnz     loc_14003B36B
0x14003b0ef  xorps   xmm0, xmm0
0x14003b0f2  lea     rcx, [rbp+260h+var_250]; DestinationString
0x14003b0f6  movups  xmmword ptr [rbp+260h+var_250.Length], xmm0
0x14003b0fa  mov     rdx, [r13+8]; SourceString
0x14003b0fe  call    cs:__imp_RtlInitUnicodeString
0x14003b105  nop     dword ptr [rax+rax+00h]
0x14003b10a  xor     edi, edi
0x14003b10c  cmp     edi, r14d
0x14003b10f  jnb     short loc_14003B158
0x14003b111  xorps   xmm0, xmm0
0x14003b114  mov     edx, edi
0x14003b116  shl     rdx, 8
0x14003b11a  lea     rcx, [rbp+260h+var_260]; DestinationString
0x14003b11e  add     rdx, [rbp+260h+var_270]; SourceString
0x14003b122  movups  xmmword ptr [rbp+260h+var_260.Length], xmm0
0x14003b126  call    cs:__imp_RtlInitUnicodeString
0x14003b12d  nop     dword ptr [rax+rax+00h]
0x14003b132  movzx   eax, [rbp+260h+var_250.Length]
0x14003b136  cmp     ax, [rbp+260h+var_260.Length]
0x14003b13a  jnz     short loc_14003B154
0x14003b13c  mov     rdx, [rbp+260h+var_260.Buffer]; Buf2
0x14003b140  mov     r8d, eax; Size
0x14003b143  mov     rcx, [rbp+260h+var_250.Buffer]; Buf1
0x14003b147  call    memcmp
0x14003b14c  test    eax, eax
0x14003b14e  jz      loc_14003B36B
0x14003b154  inc     edi
0x14003b156  jmp     short loc_14003B10C
0x14003b158  xor     edx, edx
0x14003b15a  mov     rcx, r13
0x14003b15d  call    VmsPtNicGetInfoFromRegistry
0x14003b162  test    eax, eax
0x14003b164  js      loc_14003B36B
0x14003b16a  lea     r8, [rbp+260h+var_2E0]
0x14003b16e  xor     edx, edx
0x14003b170  mov     rcx, r15
0x14003b173  call    LibIoctlAddArrayRecordElement
0x14003b178  mov     r12d, eax
0x14003b17b  test    eax, eax
0x14003b17d  jns     short loc_14003B199
0x14003b17f  cmp     eax, 80000005h
0x14003b184  jz      short loc_14003B191
0x14003b186  cmp     eax, 0C0000023h
0x14003b18b  jnz     loc_14003B37C
0x14003b191  xor     edx, edx
0x14003b193  mov     [rbp+260h+var_2E0], rdx
0x14003b197  jmp     short loc_14003B19D
0x14003b199  mov     rdx, [rbp+260h+var_2E0]
0x14003b19d  test    rdx, rdx
0x14003b1a0  jz      loc_14003B36B
0x14003b1a6  mov     rcx, r13
0x14003b1a9  call    VmsPtNicGetInfoFromRegistry
0x14003b1ae  test    eax, eax
0x14003b1b0  jns     short loc_14003B1EA
0x14003b1b2  mov     rcx, cs:VmsIfrLog
0x14003b1b9  lea     rax, aNtSuccessTemps; "NT_SUCCESS(tempStatus)"
0x14003b1c0  mov     [rsp+390h+var_368], rax
0x14003b1c5  mov     r9d, 47h ; 'G'
0x14003b1cb  lea     rax, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14003b1d2  mov     [rsp+390h+var_370], rax
0x14003b1d7  lea     r8d, [r9-34h]
0x14003b1db  call    WPP_RECORDER_SF_s
0x14003b1e0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(((NTSTATUS)(tempStatus)) >= 0)")
0x14003b1e5  jmp     loc_14003B36B
0x14003b1ea  mov     rax, [rbp+260h+var_2E0]
0x14003b1ee  mov     ecx, 1
0x14003b1f3  mov     [rax+30Ch], cl
0x14003b1f9  mov     rax, [rbp+260h+var_2E0]
0x14003b1fd  mov     dword ptr [rax+304h], 2
0x14003b207  test    cl, bl
0x14003b209  jz      loc_14003B36B
0x14003b20f  mov     r14, [rbp+260h+var_2E0]
0x14003b213  mov     r15d, ebx
0x14003b216  shr     r15d, 2
0x14003b21a  mov     r9d, 48h ; 'H'
0x14003b220  and     r15d, 7Fh
0x14003b224  movzx   edi, word ptr [r14+300h]
0x14003b22c  lea     rax, [r14+714h]
0x14003b233  movzx   r10d, byte ptr [r14+30Dh]
0x14003b23b  lea     rcx, [r14+514h]
0x14003b242  movzx   r11d, byte ptr [r14+30Ch]
0x14003b24a  lea     rdx, [r14+40Eh]
0x14003b251  mov     [rsp+390h+var_2F0], rax
0x14003b259  lea     r8, [r14+30Eh]
0x14003b260  mov     eax, [r14+510h]
0x14003b267  lea     rsi, [r14+100h]
0x14003b26e  mov     [rsp+390h+var_2F8], rcx
0x14003b276  mov     [rsp+390h+var_300], eax
0x14003b27d  mov     eax, [r14+308h]
0x14003b284  mov     [rsp+390h+var_308], rdx
0x14003b28c  mov     [rsp+390h+var_310], r8
0x14003b294  mov     [rsp+390h+var_318], r10d
0x14003b299  mov     dword ptr [rsp+390h+var_320], r11d
0x14003b29e  mov     [rsp+390h+var_328], eax
0x14003b2a2  mov     eax, [r14+304h]
0x14003b2a9  mov     [rsp+390h+var_330], eax
0x14003b2ad  mov     dword ptr [rsp+390h+var_338], edi
0x14003b2b1  lea     rdi, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14003b2b8  mov     [rsp+390h+var_340], rsi
0x14003b2bd  lea     rsi, aVmsptnicaddcon; "VmsPtNicAddConfiguredNicsToIoctlBuffer"
0x14003b2c4  mov     [rsp+390h+var_348], r14
0x14003b2c9  lea     r14, aOnecoreVmDvNet_12; "onecore\\vm\\dv\\net\\nvsp\\driver\\pt"...
0x14003b2d0  mov     [rsp+390h+var_350], rsi
0x14003b2d5  mov     [rsp+390h+var_358], r15d
0x14003b2da  mov     dword ptr [rsp+390h+var_360], 11ECh
0x14003b2e2  mov     [rsp+390h+var_368], r14
0x14003b2e7  mov     [rsp+390h+var_370], rdi
0x14003b2ec  call    WPP_RECORDER_SF_sddsSSdLLddSSdSS
0x14003b2f1  mov     rcx, [rbp+260h+var_2E0]
0x14003b2f5  mov     r9d, 49h ; 'I'
0x14003b2fb  lea     rax, [rcx+930h]
0x14003b302  mov     [rsp+390h+var_320], rax
0x14003b307  lea     rdx, [rcx+920h]
0x14003b30e  mov     eax, [rcx+92Ch]
0x14003b314  lea     r8, [rcx+91Ah]
0x14003b31b  mov     [rsp+390h+var_328], eax
0x14003b31f  lea     r10, [rcx+914h]
0x14003b326  mov     eax, [rcx+928h]
0x14003b32c  mov     [rsp+390h+var_330], eax
0x14003b330  mov     [rsp+390h+var_338], rdx
0x14003b335  mov     [rsp+390h+var_340], r8
0x14003b33a  mov     [rsp+390h+var_348], r10
0x14003b33f  mov     [rsp+390h+var_350], rsi
0x14003b344  mov     [rsp+390h+var_358], r15d
0x14003b349  mov     dword ptr [rsp+390h+var_360], 11EDh
0x14003b351  mov     [rsp+390h+var_368], r14
0x14003b356  mov     [rsp+390h+var_370], rdi
0x14003b35b  call    WPP_RECORDER_SF_sdds_MAC__MAC__MAC_DdS
0x14003b360  mov     esi, [rbp+260h+var_2D4]
0x14003b363  mov     r14d, [rbp+260h+var_2D0]
0x14003b367  mov     r15, [rbp+260h+var_268]
0x14003b36b  mov     rcx, [rbp+260h+var_2C0]
0x14003b36f  call    VmsCsKeyClose
0x14003b374  inc     si
0x14003b377  jmp     loc_14003AF81
0x14003b37c  mov     rcx, cs:VmsIfrLog
0x14003b383  lea     rdi, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14003b38a  mov     r9d, 46h ; 'F'
0x14003b390  mov     dword ptr [rsp+390h+var_368], eax
0x14003b394  mov     dl, 2
0x14003b396  mov     [rsp+390h+var_370], rdi
0x14003b39b  lea     r8d, [r9-32h]
0x14003b39f  call    WPP_RECORDER_SF_d
0x14003b3a4  jmp     short loc_14003B3B6
0x14003b3a6  mov     rcx, [rbp+260h+KeyHandle]
0x14003b3aa  call    VmsCsKeyClose
0x14003b3af  lea     rdi, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14003b3b6  test    r13, r13
0x14003b3b9  jz      short loc_14003B3CC
0x14003b3bb  xor     edx, edx; Tag
0x14003b3bd  mov     rcx, r13; P
0x14003b3c0  call    cs:__imp_ExFreePoolWithTag
0x14003b3c7  nop     dword ptr [rax+rax+00h]
0x14003b3cc  test    r12d, r12d
0x14003b3cf  jns     short loc_14003B406
0x14003b3d1  mov     rax, [rbp+260h+var_270]
  ... truncated ...
```
