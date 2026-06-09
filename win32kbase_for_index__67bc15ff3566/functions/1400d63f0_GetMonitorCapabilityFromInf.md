# GetMonitorCapabilityFromInf

- ea: `0x1400d63f0`
- end: `0x1400d6808`
- name: `GetMonitorCapabilityFromInf`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d6320`

## callees

- `0x1400d63f0`
- `0x1400d6810`
- `0x1400d692c`
- `0x14013490c`
- `0x1401c4b50`
- `0x1401c5198`
- `0x1402388e0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400d64cb`
- `ntoskrnl!ZwOpenKey` at `0x1400d66a3`
- `ntoskrnl!ZwOpenKey` at `0x1400d64cb`
- `ntoskrnl!ZwOpenKey` at `0x1400d66a3`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d6714`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d6714`
- `ntoskrnl!ZwClose` at `0x1400d6539`
- `ntoskrnl!ZwClose` at `0x1400d654a`
- `ntoskrnl!ZwClose` at `0x1400d673b`
- `ntoskrnl!ZwClose` at `0x1400d6539`
- `ntoskrnl!ZwClose` at `0x1400d654a`
- `ntoskrnl!ZwClose` at `0x1400d673b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400d6455`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400d6455`
- `ntoskrnl!ZwEnumerateKey` at `0x1400d6524`
- `ntoskrnl!ZwEnumerateKey` at `0x1400d6524`
- `ntoskrnl!wcsncpy_s` at `0x1400d65bb`
- `ntoskrnl!wcsncpy_s` at `0x1400d6797`
- `ntoskrnl!wcsncpy_s` at `0x1400d65bb`
- `ntoskrnl!wcsncpy_s` at `0x1400d6797`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d648c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d66e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d648c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d66e5`

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
0x1400d63f0  mov     [rsp-8+arg_10], rbx
0x1400d63f5  mov     [rsp-8+arg_18], rsi
0x1400d63fa  push    rbp
0x1400d63fb  push    rdi
0x1400d63fc  push    r12
0x1400d63fe  push    r14
0x1400d6400  push    r15
0x1400d6402  lea     rbp, [rsp-1E0h]
0x1400d640a  sub     rsp, 2E0h
0x1400d6411  mov     rax, cs:__security_cookie
0x1400d6418  xor     rax, rsp
0x1400d641b  mov     [rbp+200h+var_30], rax
0x1400d6422  mov     r12b, r8b
0x1400d6425  mov     [rsp+300h+DeviceRegKey], 0
0x1400d642e  mov     r15, rdx
0x1400d6431  mov     [rsp+300h+KeyHandle], 0
0x1400d643a  mov     ebx, 20019h
0x1400d643f  mov     [rsp+300h+Handle], 0
0x1400d6448  mov     r8d, ebx; DesiredAccess
0x1400d644b  lea     r9, [rsp+300h+DeviceRegKey]; DeviceRegKey
0x1400d6450  mov     edx, 2; DevInstKeyType
0x1400d6455  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400d645c  nop     dword ptr [rax+rax+00h]
0x1400d6461  test    eax, eax
0x1400d6463  js      loc_1400D6776
0x1400d6469  xorps   xmm0, xmm0
0x1400d646c  lea     rdx, aModes; "MODES"
0x1400d6473  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x1400d6478  xor     r14d, r14d
0x1400d647b  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x1400d647f  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x1400d6483  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d6487  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x1400d648c  call    cs:__imp_RtlInitUnicodeString
0x1400d6493  nop     dword ptr [rax+rax+00h]
0x1400d6498  mov     rax, [rsp+300h+DeviceRegKey]
0x1400d649d  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1400d64a1  mov     [rbp+200h+ObjectAttributes.RootDirectory], rax
0x1400d64a5  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400d64aa  lea     rax, [rsp+300h+DestinationString]
0x1400d64af  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400d64b6  xorps   xmm0, xmm0
0x1400d64b9  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1400d64bd  mov     edx, ebx; DesiredAccess
0x1400d64bf  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1400d64c6  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d64cb  call    cs:__imp_ZwOpenKey
0x1400d64d2  nop     dword ptr [rax+rax+00h]
0x1400d64d7  test    eax, eax
0x1400d64d9  js      short loc_1400D6545
0x1400d64db  mov     ebx, 100h
0x1400d64e0  lea     rcx, [rbp+200h+KeyInformation]; void *
0x1400d64e4  mov     r8d, ebx; Size
0x1400d64e7  xor     edx, edx; Val
0x1400d64e9  call    memset
0x1400d64ee  xor     esi, esi
0x1400d64f0  xorps   xmm0, xmm0
0x1400d64f3  xor     eax, eax
0x1400d64f5  mov     [rsp+300h+var_2D0], esi
0x1400d64f9  mov     [rsp+300h+var_288], rax
0x1400d64fe  movups  [rsp+300h+var_298], xmm0
0x1400d6503  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400d6508  lea     rax, [rsp+300h+var_2D0]
0x1400d650d  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1400d6512  lea     r9, [rbp+200h+KeyInformation]; KeyInformation
0x1400d6516  xor     r8d, r8d; KeyInformationClass
0x1400d6519  mov     [rsp+300h+Length], ebx; Length
0x1400d651d  mov     edx, esi; Index
0x1400d651f  mov     edi, 1
0x1400d6524  call    cs:__imp_ZwEnumerateKey
0x1400d652b  nop     dword ptr [rax+rax+00h]
0x1400d6530  test    eax, eax
0x1400d6532  jns     short loc_1400D6585
0x1400d6534  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x1400d6539  call    cs:__imp_ZwClose
0x1400d6540  nop     dword ptr [rax+rax+00h]
0x1400d6545  mov     rcx, [rsp+300h+DeviceRegKey]; Handle
0x1400d654a  call    cs:__imp_ZwClose
0x1400d6551  nop     dword ptr [rax+rax+00h]
0x1400d6556  mov     eax, r14d
0x1400d6559  mov     rcx, [rbp+200h+var_30]
0x1400d6560  xor     rcx, rsp; StackCookie
0x1400d6563  call    __security_check_cookie
0x1400d6568  lea     r11, [rsp+300h+var_20]
0x1400d6570  mov     rbx, [r11+40h]
0x1400d6574  mov     rsi, [r11+48h]
0x1400d6578  mov     rsp, r11
0x1400d657b  pop     r15
0x1400d657d  pop     r14
0x1400d657f  pop     r12
0x1400d6581  pop     rdi
0x1400d6582  pop     rbp
0x1400d6583  retn
0x1400d6585  lea     rax, [rbp+200h+Src]
0x1400d6589  mov     [rsp+300h+DestinationString.Buffer], rax
0x1400d658e  mov     eax, [rbp+200h+var_244]
0x1400d6591  mov     [rsp+300h+DestinationString.Length], ax
0x1400d6596  mov     [rsp+300h+DestinationString.MaximumLength], ax
0x1400d659b  movzx   r9d, ax
0x1400d659f  cmp     ax, bx
0x1400d65a2  jnb     loc_1400D67E5
0x1400d65a8  shr     r9, 1; MaxCount
0x1400d65ab  lea     r8, [rbp+200h+Src]; Src
0x1400d65af  mov     edx, 80h; SizeInWords
0x1400d65b4  lea     rcx, [rbp+200h+Dst]; Dst
0x1400d65bb  call    cs:__imp_wcsncpy_s
0x1400d65c2  nop     dword ptr [rax+rax+00h]
0x1400d65c7  cmp     [rsp+300h+DestinationString.Length], bx
0x1400d65cc  jb      loc_1400D6755
0x1400d65d2  xor     eax, eax
0x1400d65d4  mov     dword ptr [rbp+200h+var_14C], 0FFFFFFFFh
0x1400d65de  add     esi, edi
0x1400d65e0  mov     [rbp+200h+var_32], ax
0x1400d65e7  mov     [rsp+300h+var_2B0], esi
0x1400d65eb  lea     rdi, [rbp+200h+Dst]
0x1400d65f2  mov     [rbp+200h+var_150], eax
0x1400d65f8  xor     ebx, ebx
0x1400d65fa  mov     dword ptr [rbp+200h+var_14C+4], eax
0x1400d6600  cmp     ebx, 4
0x1400d6603  jnb     short loc_1400D6639
0x1400d6605  mov     edx, 2Ch ; ','; Ch
0x1400d660a  mov     rcx, rdi; Str
0x1400d660d  call    wcschr
0x1400d6612  mov     r9, rax
0x1400d6615  test    rax, rax
0x1400d6618  jz      short loc_1400D661F
0x1400d661a  xor     edx, edx
0x1400d661c  mov     [rax], dx
0x1400d661f  mov     rcx, rdi
0x1400d6622  call    xwtol
0x1400d6627  mov     [rbp+rbx*4+200h+var_150], eax
0x1400d662e  lea     rdi, [r9+2]
0x1400d6632  inc     ebx
0x1400d6634  test    r9, r9
0x1400d6637  jnz     short loc_1400D6600
0x1400d6639  mov     eax, [rbp+200h+var_150]
0x1400d663f  mov     ebx, 100h
0x1400d6644  test    eax, eax
0x1400d6646  jz      loc_1400D6503
0x1400d664c  mov     ecx, dword ptr [rbp+200h+var_14C]
0x1400d6652  cmp     ecx, 0FFFFFFFFh
0x1400d6655  jz      loc_1400D6503
0x1400d665b  mov     dword ptr [rsp+300h+var_298], eax
0x1400d665f  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1400d6663  mov     eax, dword ptr [rbp+200h+var_14C+4]
0x1400d6669  xorps   xmm0, xmm0
0x1400d666c  mov     dword ptr [rsp+300h+var_298+8], eax
0x1400d6670  mov     edx, 2000000h; DesiredAccess
0x1400d6675  mov     rax, [rsp+300h+KeyHandle]
0x1400d667a  mov     [rbp+200h+ObjectAttributes.RootDirectory], rax
0x1400d667e  lea     rax, [rsp+300h+DestinationString]
0x1400d6683  mov     dword ptr [rsp+300h+var_298+4], ecx
0x1400d6687  lea     rcx, [rsp+300h+Handle]; KeyHandle
0x1400d668c  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1400d6690  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400d6697  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1400d669e  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d66a3  call    cs:__imp_ZwOpenKey
0x1400d66aa  nop     dword ptr [rax+rax+00h]
0x1400d66af  test    eax, eax
0x1400d66b1  js      loc_1400D6503
0x1400d66b7  xor     edi, edi
0x1400d66b9  mov     [rbp+200h+var_138], 31h ; '1'
0x1400d66c3  mov     rax, 650064006F004Dh
0x1400d66cd  xor     ebx, ebx
0x1400d66cf  mov     qword ptr [rbp+200h+SourceString], rax
0x1400d66d6  lea     esi, [rdi+1]
0x1400d66d9  lea     rdx, [rbp+200h+SourceString]; SourceString
0x1400d66e0  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x1400d66e5  call    cs:__imp_RtlInitUnicodeString
0x1400d66ec  nop     dword ptr [rax+rax+00h]
0x1400d66f1  mov     rcx, [rsp+300h+Handle]; KeyHandle
0x1400d66f6  lea     rax, [rsp+300h+var_2D0]
0x1400d66fb  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1400d6700  lea     r9, [rbp+200h+KeyInformation]; KeyValueInformation
0x1400d6704  mov     r8d, esi; KeyValueInformationClass
0x1400d6707  mov     [rsp+300h+Length], 100h; Length
0x1400d670f  lea     rdx, [rsp+300h+DestinationString]; ValueName
0x1400d6714  call    cs:__imp_ZwQueryValueKey
0x1400d671b  nop     dword ptr [rax+rax+00h]
0x1400d6720  test    eax, eax
0x1400d6722  jns     short loc_1400D677D
0x1400d6724  test    edi, edi
0x1400d6726  jnz     short loc_1400D6736
0x1400d6728  add     word ptr [rbp+200h+var_138], si
0x1400d672f  add     ebx, esi
0x1400d6731  cmp     ebx, 9
0x1400d6734  jb      short loc_1400D66D9
0x1400d6736  mov     rcx, [rsp+300h+Handle]; Handle
0x1400d673b  call    cs:__imp_ZwClose
0x1400d6742  nop     dword ptr [rax+rax+00h]
0x1400d6747  mov     esi, [rsp+300h+var_2B0]
0x1400d674b  mov     ebx, 100h
0x1400d6750  jmp     loc_1400D6503
0x1400d6755  movzx   ecx, [rsp+300h+DestinationString.Length]
0x1400d675a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1400d675e  cmp     rcx, rbx
0x1400d6761  jnb     loc_1400D6802
0x1400d6767  xor     eax, eax
0x1400d6769  mov     [rbp+rcx+200h+Dst], ax
0x1400d6771  jmp     loc_1400D65D2
0x1400d6776  xor     eax, eax
0x1400d6778  jmp     loc_1400D6559
0x1400d677d  mov     eax, [rbp+200h+var_248]
0x1400d6780  lea     r8, [rbp+200h+KeyInformation]
0x1400d6784  mov     edx, 80h; SizeInWords
0x1400d6789  lea     rcx, [rbp+200h+Dst]; Dst
0x1400d6790  add     r8, rax; Src
0x1400d6793  lea     r9d, [rdx-1]; MaxCount
0x1400d6797  call    cs:__imp_wcsncpy_s
0x1400d679e  nop     dword ptr [rax+rax+00h]
0x1400d67a3  mov     al, r12b
0x1400d67a6  mov     dword ptr [rsp+300h+var_288], 0
0x1400d67ae  neg     al
0x1400d67b0  lea     rdx, [rsp+300h+var_298]
0x1400d67b5  mov     r8d, esi
0x1400d67b8  sbb     ecx, ecx
0x1400d67ba  or      eax, 0FFFFFFFFh
0x1400d67bd  not     ecx
0x1400d67bf  mov     dword ptr [rsp+300h+var_298+8], eax
0x1400d67c3  and     ecx, 38h
0x1400d67c6  mov     dword ptr [rsp+300h+var_288+4], eax
0x1400d67ca  mov     dword ptr [rsp+300h+var_298+0Ch], ecx
0x1400d67ce  lea     rcx, [rbp+200h+Dst]; Str
0x1400d67d5  call    ParseModeCap
0x1400d67da  test    eax, eax
0x1400d67dc  jnz     short loc_1400D67ED
0x1400d67de  mov     edi, esi
0x1400d67e0  jmp     loc_1400D6728
0x1400d67e5  mov     r9, rbx
0x1400d67e8  jmp     loc_1400D65A8
0x1400d67ed  mov     r8d, r14d
0x1400d67f0  lea     rcx, [rsp+300h+var_298]
0x1400d67f5  mov     rdx, r15
0x1400d67f8  call    InsertModecapList
0x1400d67fd  mov     r14d, eax
0x1400d6800  jmp     short loc_1400D67DE
0x1400d6802  call    __report_rangecheckfailure
```
