# GetMonitorCapabilityFromInf

- ea: `0x1400acae0`
- end: `0x1400acef8`
- name: `GetMonitorCapabilityFromInf`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400aca10`

## callees

- `0x1400acae0`
- `0x1400acf00`
- `0x1400ad01c`
- `0x1400ad6c4`
- `0x1401c3a20`
- `0x1401c4068`
- `0x140238160`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400acbbb`
- `ntoskrnl!ZwOpenKey` at `0x1400acd93`
- `ntoskrnl!ZwOpenKey` at `0x1400acbbb`
- `ntoskrnl!ZwOpenKey` at `0x1400acd93`
- `ntoskrnl!ZwQueryValueKey` at `0x1400ace04`
- `ntoskrnl!ZwQueryValueKey` at `0x1400ace04`
- `ntoskrnl!ZwClose` at `0x1400acc29`
- `ntoskrnl!ZwClose` at `0x1400acc3a`
- `ntoskrnl!ZwClose` at `0x1400ace2b`
- `ntoskrnl!ZwClose` at `0x1400acc29`
- `ntoskrnl!ZwClose` at `0x1400acc3a`
- `ntoskrnl!ZwClose` at `0x1400ace2b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400acb45`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400acb45`
- `ntoskrnl!ZwEnumerateKey` at `0x1400acc14`
- `ntoskrnl!ZwEnumerateKey` at `0x1400acc14`
- `ntoskrnl!wcsncpy_s` at `0x1400accab`
- `ntoskrnl!wcsncpy_s` at `0x1400ace87`
- `ntoskrnl!wcsncpy_s` at `0x1400accab`
- `ntoskrnl!wcsncpy_s` at `0x1400ace87`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400acb7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400acdd5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400acb7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400acdd5`

## pseudocode

```c
__int64 __fastcall GetMonitorCapabilityFromInf(struct _DEVICE_OBJECT *a1, __int64 a2, char a3)
{
  unsigned int inserted; // r14d
  ULONG v6; // esi
  unsigned __int64 v8; // r9
  wchar_t *v9; // rdi
  __int64 v10; // rbx
  wchar_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // edi
  unsigned int v16; // ebx
  unsigned __int64 v17; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v21; // [rsp+50h] [rbp-B0h]
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  void *DeviceRegKey; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v25; // [rsp+78h] [rbp-88h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _DWORD KeyInformation[64]; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+1B0h] [rbp+B0h]
  __int64 v29; // [rsp+1B4h] [rbp+B4h]
  WCHAR SourceString[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t Dst[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  DeviceRegKey = 0;
  KeyHandle = 0;
  Handle = 0;
  if ( IoOpenDeviceRegistryKey(a1, 2u, 0x20019u, &DeviceRegKey) < 0 )
    return 0;
  inserted = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"MODES");
  ObjectAttributes.RootDirectory = DeviceRegKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    memset(KeyInformation, 0, sizeof(KeyInformation));
    v6 = 0;
    ResultLength = 0;
    v25 = 0;
    v24 = 0;
    while ( ZwEnumerateKey(KeyHandle, v6, KeyBasicInformation, KeyInformation, 0x100u, &ResultLength) >= 0 )
    {
      DestinationString.Buffer = (PWSTR)&KeyInformation[4];
      DestinationString.Length = KeyInformation[3];
      DestinationString.MaximumLength = KeyInformation[3];
      v8 = LOWORD(KeyInformation[3]);
      if ( LOWORD(KeyInformation[3]) >= 0x100u )
        v8 = 256;
      wcsncpy_s(Dst, 0x80u, (const wchar_t *)&KeyInformation[4], v8 >> 1);
      if ( DestinationString.Length < 0x100u )
      {
        v17 = DestinationString.Length & 0xFFFE;
        if ( v17 >= 0x100 )
          _report_rangecheckfailure();
        *(wchar_t *)((char *)Dst + v17) = 0;
      }
      v29 = 0xFFFFFFFFLL;
      ++v6;
      Dst[127] = 0;
      v21 = v6;
      v9 = Dst;
      v28 = 0;
      v10 = 0;
      do
      {
        if ( (unsigned int)v10 >= 4 )
          break;
        v11 = wcschr(v9, 0x2Cu);
        if ( v11 )
        {
          v12 = 0;
          *v11 = 0;
        }
        *(&v28 + v10) = xwtol(v9, v12, v13, v11);
        v9 = (wchar_t *)(v14 + 2);
        v10 = (unsigned int)(v10 + 1);
      }
      while ( v14 );
      if ( v28 )
      {
        if ( (_DWORD)v29 != -1 )
        {
          LODWORD(v24) = v28;
          ObjectAttributes.RootDirectory = KeyHandle;
          *(_QWORD *)((char *)&v24 + 4) = v29;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwOpenKey(&Handle, 0x2000000u, &ObjectAttributes) >= 0 )
          {
            v15 = 0;
            v16 = 0;
            wcscpy(SourceString, L"Mode1");
            do
            {
              RtlInitUnicodeString(&DestinationString, SourceString);
              if ( ZwQueryValueKey(
                     Handle,
                     &DestinationString,
                     KeyValueFullInformation,
                     KeyInformation,
                     0x100u,
                     &ResultLength) >= 0 )
              {
                wcsncpy_s(Dst, 0x80u, (const wchar_t *)((char *)KeyInformation + KeyInformation[2]), 0x7Fu);
                v25 = 0xFFFFFFFF00000000uLL;
                DWORD2(v24) = -1;
                HIDWORD(v24) = a3 == 0 ? 0x38 : 0;
                if ( (unsigned int)ParseModeCap(Dst) )
                  inserted = InsertModecapList(&v24, a2, inserted);
                v15 = 1;
              }
              else if ( v15 )
              {
                break;
              }
              ++SourceString[4];
              ++v16;
            }
            while ( v16 < 9 );
            ZwClose(Handle);
            v6 = v21;
          }
        }
      }
    }
    ZwClose(KeyHandle);
  }
  ZwClose(DeviceRegKey);
  return inserted;
}

```

## disassembly

```asm
0x1400acae0  mov     [rsp-8+arg_10], rbx
0x1400acae5  mov     [rsp-8+arg_18], rsi
0x1400acaea  push    rbp
0x1400acaeb  push    rdi
0x1400acaec  push    r12
0x1400acaee  push    r14
0x1400acaf0  push    r15
0x1400acaf2  lea     rbp, [rsp-1E0h]
0x1400acafa  sub     rsp, 2E0h
0x1400acb01  mov     rax, cs:__security_cookie
0x1400acb08  xor     rax, rsp
0x1400acb0b  mov     [rbp+200h+var_30], rax
0x1400acb12  mov     r12b, r8b
0x1400acb15  mov     [rsp+300h+DeviceRegKey], 0
0x1400acb1e  mov     r15, rdx
0x1400acb21  mov     [rsp+300h+KeyHandle], 0
0x1400acb2a  mov     ebx, 20019h
0x1400acb2f  mov     [rsp+300h+Handle], 0
0x1400acb38  mov     r8d, ebx; DesiredAccess
0x1400acb3b  lea     r9, [rsp+300h+DeviceRegKey]; DeviceRegKey
0x1400acb40  mov     edx, 2; DevInstKeyType
0x1400acb45  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400acb4c  nop     dword ptr [rax+rax+00h]
0x1400acb51  test    eax, eax
0x1400acb53  js      loc_1400ACE66
0x1400acb59  xorps   xmm0, xmm0
0x1400acb5c  lea     rdx, aModes; "MODES"
0x1400acb63  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x1400acb68  xor     r14d, r14d
0x1400acb6b  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x1400acb6f  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x1400acb73  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400acb77  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x1400acb7c  call    cs:__imp_RtlInitUnicodeString
0x1400acb83  nop     dword ptr [rax+rax+00h]
0x1400acb88  mov     rax, [rsp+300h+DeviceRegKey]
0x1400acb8d  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1400acb91  mov     [rbp+200h+ObjectAttributes.RootDirectory], rax
0x1400acb95  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400acb9a  lea     rax, [rsp+300h+DestinationString]
0x1400acb9f  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400acba6  xorps   xmm0, xmm0
0x1400acba9  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1400acbad  mov     edx, ebx; DesiredAccess
0x1400acbaf  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1400acbb6  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400acbbb  call    cs:__imp_ZwOpenKey
0x1400acbc2  nop     dword ptr [rax+rax+00h]
0x1400acbc7  test    eax, eax
0x1400acbc9  js      short loc_1400ACC35
0x1400acbcb  mov     ebx, 100h
0x1400acbd0  lea     rcx, [rbp+200h+KeyInformation]; void *
0x1400acbd4  mov     r8d, ebx; Size
0x1400acbd7  xor     edx, edx; Val
0x1400acbd9  call    memset
0x1400acbde  xor     esi, esi
0x1400acbe0  xorps   xmm0, xmm0
0x1400acbe3  xor     eax, eax
0x1400acbe5  mov     [rsp+300h+var_2D0], esi
0x1400acbe9  mov     [rsp+300h+var_288], rax
0x1400acbee  movups  [rsp+300h+var_298], xmm0
0x1400acbf3  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400acbf8  lea     rax, [rsp+300h+var_2D0]
0x1400acbfd  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1400acc02  lea     r9, [rbp+200h+KeyInformation]; KeyInformation
0x1400acc06  xor     r8d, r8d; KeyInformationClass
0x1400acc09  mov     [rsp+300h+Length], ebx; Length
0x1400acc0d  mov     edx, esi; Index
0x1400acc0f  mov     edi, 1
0x1400acc14  call    cs:__imp_ZwEnumerateKey
0x1400acc1b  nop     dword ptr [rax+rax+00h]
0x1400acc20  test    eax, eax
0x1400acc22  jns     short loc_1400ACC75
0x1400acc24  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x1400acc29  call    cs:__imp_ZwClose
0x1400acc30  nop     dword ptr [rax+rax+00h]
0x1400acc35  mov     rcx, [rsp+300h+DeviceRegKey]; Handle
0x1400acc3a  call    cs:__imp_ZwClose
0x1400acc41  nop     dword ptr [rax+rax+00h]
0x1400acc46  mov     eax, r14d
0x1400acc49  mov     rcx, [rbp+200h+var_30]
0x1400acc50  xor     rcx, rsp; StackCookie
0x1400acc53  call    __security_check_cookie
0x1400acc58  lea     r11, [rsp+300h+var_20]
0x1400acc60  mov     rbx, [r11+40h]
0x1400acc64  mov     rsi, [r11+48h]
0x1400acc68  mov     rsp, r11
0x1400acc6b  pop     r15
0x1400acc6d  pop     r14
0x1400acc6f  pop     r12
0x1400acc71  pop     rdi
0x1400acc72  pop     rbp
0x1400acc73  retn
0x1400acc75  lea     rax, [rbp+200h+Src]
0x1400acc79  mov     [rsp+300h+DestinationString.Buffer], rax
0x1400acc7e  mov     eax, [rbp+200h+var_244]
0x1400acc81  mov     [rsp+300h+DestinationString.Length], ax
0x1400acc86  mov     [rsp+300h+DestinationString.MaximumLength], ax
0x1400acc8b  movzx   r9d, ax
0x1400acc8f  cmp     ax, bx
0x1400acc92  jnb     loc_1400ACED5
0x1400acc98  shr     r9, 1; MaxCount
0x1400acc9b  lea     r8, [rbp+200h+Src]; Src
0x1400acc9f  mov     edx, 80h; SizeInWords
0x1400acca4  lea     rcx, [rbp+200h+Dst]; Dst
0x1400accab  call    cs:__imp_wcsncpy_s
0x1400accb2  nop     dword ptr [rax+rax+00h]
0x1400accb7  cmp     [rsp+300h+DestinationString.Length], bx
0x1400accbc  jb      loc_1400ACE45
0x1400accc2  xor     eax, eax
0x1400accc4  mov     dword ptr [rbp+200h+var_14C], 0FFFFFFFFh
0x1400accce  add     esi, edi
0x1400accd0  mov     [rbp+200h+var_32], ax
0x1400accd7  mov     [rsp+300h+var_2B0], esi
0x1400accdb  lea     rdi, [rbp+200h+Dst]
0x1400acce2  mov     [rbp+200h+var_150], eax
0x1400acce8  xor     ebx, ebx
0x1400accea  mov     dword ptr [rbp+200h+var_14C+4], eax
0x1400accf0  cmp     ebx, 4
0x1400accf3  jnb     short loc_1400ACD29
0x1400accf5  mov     edx, 2Ch ; ','; Ch
0x1400accfa  mov     rcx, rdi; Str
0x1400accfd  call    wcschr
0x1400acd02  mov     r9, rax
0x1400acd05  test    rax, rax
0x1400acd08  jz      short loc_1400ACD0F
0x1400acd0a  xor     edx, edx
0x1400acd0c  mov     [rax], dx
0x1400acd0f  mov     rcx, rdi
0x1400acd12  call    xwtol
0x1400acd17  mov     [rbp+rbx*4+200h+var_150], eax
0x1400acd1e  lea     rdi, [r9+2]
0x1400acd22  inc     ebx
0x1400acd24  test    r9, r9
0x1400acd27  jnz     short loc_1400ACCF0
0x1400acd29  mov     eax, [rbp+200h+var_150]
0x1400acd2f  mov     ebx, 100h
0x1400acd34  test    eax, eax
0x1400acd36  jz      loc_1400ACBF3
0x1400acd3c  mov     ecx, dword ptr [rbp+200h+var_14C]
0x1400acd42  cmp     ecx, 0FFFFFFFFh
0x1400acd45  jz      loc_1400ACBF3
0x1400acd4b  mov     dword ptr [rsp+300h+var_298], eax
0x1400acd4f  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1400acd53  mov     eax, dword ptr [rbp+200h+var_14C+4]
0x1400acd59  xorps   xmm0, xmm0
0x1400acd5c  mov     dword ptr [rsp+300h+var_298+8], eax
0x1400acd60  mov     edx, 2000000h; DesiredAccess
0x1400acd65  mov     rax, [rsp+300h+KeyHandle]
0x1400acd6a  mov     [rbp+200h+ObjectAttributes.RootDirectory], rax
0x1400acd6e  lea     rax, [rsp+300h+DestinationString]
0x1400acd73  mov     dword ptr [rsp+300h+var_298+4], ecx
0x1400acd77  lea     rcx, [rsp+300h+Handle]; KeyHandle
0x1400acd7c  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1400acd80  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400acd87  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1400acd8e  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400acd93  call    cs:__imp_ZwOpenKey
0x1400acd9a  nop     dword ptr [rax+rax+00h]
0x1400acd9f  test    eax, eax
0x1400acda1  js      loc_1400ACBF3
0x1400acda7  xor     edi, edi
0x1400acda9  mov     [rbp+200h+var_138], 31h ; '1'
0x1400acdb3  mov     rax, 650064006F004Dh
0x1400acdbd  xor     ebx, ebx
0x1400acdbf  mov     qword ptr [rbp+200h+SourceString], rax
0x1400acdc6  lea     esi, [rdi+1]
0x1400acdc9  lea     rdx, [rbp+200h+SourceString]; SourceString
0x1400acdd0  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x1400acdd5  call    cs:__imp_RtlInitUnicodeString
0x1400acddc  nop     dword ptr [rax+rax+00h]
0x1400acde1  mov     rcx, [rsp+300h+Handle]; KeyHandle
0x1400acde6  lea     rax, [rsp+300h+var_2D0]
0x1400acdeb  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1400acdf0  lea     r9, [rbp+200h+KeyInformation]; KeyValueInformation
0x1400acdf4  mov     r8d, esi; KeyValueInformationClass
0x1400acdf7  mov     [rsp+300h+Length], 100h; Length
0x1400acdff  lea     rdx, [rsp+300h+DestinationString]; ValueName
0x1400ace04  call    cs:__imp_ZwQueryValueKey
0x1400ace0b  nop     dword ptr [rax+rax+00h]
0x1400ace10  test    eax, eax
0x1400ace12  jns     short loc_1400ACE6D
0x1400ace14  test    edi, edi
0x1400ace16  jnz     short loc_1400ACE26
0x1400ace18  add     word ptr [rbp+200h+var_138], si
0x1400ace1f  add     ebx, esi
0x1400ace21  cmp     ebx, 9
0x1400ace24  jb      short loc_1400ACDC9
0x1400ace26  mov     rcx, [rsp+300h+Handle]; Handle
0x1400ace2b  call    cs:__imp_ZwClose
0x1400ace32  nop     dword ptr [rax+rax+00h]
0x1400ace37  mov     esi, [rsp+300h+var_2B0]
0x1400ace3b  mov     ebx, 100h
0x1400ace40  jmp     loc_1400ACBF3
0x1400ace45  movzx   ecx, [rsp+300h+DestinationString.Length]
0x1400ace4a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1400ace4e  cmp     rcx, rbx
0x1400ace51  jnb     loc_1400ACEF2
0x1400ace57  xor     eax, eax
0x1400ace59  mov     [rbp+rcx+200h+Dst], ax
0x1400ace61  jmp     loc_1400ACCC2
0x1400ace66  xor     eax, eax
0x1400ace68  jmp     loc_1400ACC49
0x1400ace6d  mov     eax, [rbp+200h+var_248]
0x1400ace70  lea     r8, [rbp+200h+KeyInformation]
0x1400ace74  mov     edx, 80h; SizeInWords
0x1400ace79  lea     rcx, [rbp+200h+Dst]; Dst
0x1400ace80  add     r8, rax; Src
0x1400ace83  lea     r9d, [rdx-1]; MaxCount
0x1400ace87  call    cs:__imp_wcsncpy_s
0x1400ace8e  nop     dword ptr [rax+rax+00h]
0x1400ace93  mov     al, r12b
0x1400ace96  mov     dword ptr [rsp+300h+var_288], 0
0x1400ace9e  neg     al
0x1400acea0  lea     rdx, [rsp+300h+var_298]
0x1400acea5  mov     r8d, esi
0x1400acea8  sbb     ecx, ecx
0x1400aceaa  or      eax, 0FFFFFFFFh
0x1400acead  not     ecx
0x1400aceaf  mov     dword ptr [rsp+300h+var_298+8], eax
0x1400aceb3  and     ecx, 38h
0x1400aceb6  mov     dword ptr [rsp+300h+var_288+4], eax
0x1400aceba  mov     dword ptr [rsp+300h+var_298+0Ch], ecx
0x1400acebe  lea     rcx, [rbp+200h+Dst]; Str
0x1400acec5  call    ParseModeCap
0x1400aceca  test    eax, eax
0x1400acecc  jnz     short loc_1400ACEDD
0x1400acece  mov     edi, esi
0x1400aced0  jmp     loc_1400ACE18
0x1400aced5  mov     r9, rbx
0x1400aced8  jmp     loc_1400ACC98
0x1400acedd  mov     r8d, r14d
0x1400acee0  lea     rcx, [rsp+300h+var_298]
0x1400acee5  mov     rdx, r15
0x1400acee8  call    InsertModecapList
0x1400aceed  mov     r14d, eax
0x1400acef0  jmp     short loc_1400ACECE
0x1400acef2  call    __report_rangecheckfailure
```
