# GetMonitorCapabilityFromInf

- ea: `0x1400c73b0`
- end: `0x1400c77c8`
- name: `GetMonitorCapabilityFromInf`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400c72e0`

## callees

- `0x1400c73b0`
- `0x1400c77d0`
- `0x1400c78ec`
- `0x1400c7f94`
- `0x1401c3f80`
- `0x1401c45c8`
- `0x140238b10`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400c748b`
- `ntoskrnl!ZwOpenKey` at `0x1400c7663`
- `ntoskrnl!ZwOpenKey` at `0x1400c748b`
- `ntoskrnl!ZwOpenKey` at `0x1400c7663`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c76d4`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c76d4`
- `ntoskrnl!ZwClose` at `0x1400c74f9`
- `ntoskrnl!ZwClose` at `0x1400c750a`
- `ntoskrnl!ZwClose` at `0x1400c76fb`
- `ntoskrnl!ZwClose` at `0x1400c74f9`
- `ntoskrnl!ZwClose` at `0x1400c750a`
- `ntoskrnl!ZwClose` at `0x1400c76fb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400c7415`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400c7415`
- `ntoskrnl!ZwEnumerateKey` at `0x1400c74e4`
- `ntoskrnl!ZwEnumerateKey` at `0x1400c74e4`
- `ntoskrnl!wcsncpy_s` at `0x1400c757b`
- `ntoskrnl!wcsncpy_s` at `0x1400c7757`
- `ntoskrnl!wcsncpy_s` at `0x1400c757b`
- `ntoskrnl!wcsncpy_s` at `0x1400c7757`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c744c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c76a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c744c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c76a5`

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
0x1400c73b0  mov     [rsp-8+arg_10], rbx
0x1400c73b5  mov     [rsp-8+arg_18], rsi
0x1400c73ba  push    rbp
0x1400c73bb  push    rdi
0x1400c73bc  push    r12
0x1400c73be  push    r14
0x1400c73c0  push    r15
0x1400c73c2  lea     rbp, [rsp-1E0h]
0x1400c73ca  sub     rsp, 2E0h
0x1400c73d1  mov     rax, cs:__security_cookie
0x1400c73d8  xor     rax, rsp
0x1400c73db  mov     [rbp+200h+var_30], rax
0x1400c73e2  mov     r12b, r8b
0x1400c73e5  mov     [rsp+300h+DeviceRegKey], 0
0x1400c73ee  mov     r15, rdx
0x1400c73f1  mov     [rsp+300h+KeyHandle], 0
0x1400c73fa  mov     ebx, 20019h
0x1400c73ff  mov     [rsp+300h+Handle], 0
0x1400c7408  mov     r8d, ebx; DesiredAccess
0x1400c740b  lea     r9, [rsp+300h+DeviceRegKey]; DeviceRegKey
0x1400c7410  mov     edx, 2; DevInstKeyType
0x1400c7415  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400c741c  nop     dword ptr [rax+rax+00h]
0x1400c7421  test    eax, eax
0x1400c7423  js      loc_1400C7736
0x1400c7429  xorps   xmm0, xmm0
0x1400c742c  lea     rdx, aModes; "MODES"
0x1400c7433  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x1400c7438  xor     r14d, r14d
0x1400c743b  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x1400c743f  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x1400c7443  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c7447  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x1400c744c  call    cs:__imp_RtlInitUnicodeString
0x1400c7453  nop     dword ptr [rax+rax+00h]
0x1400c7458  mov     rax, [rsp+300h+DeviceRegKey]
0x1400c745d  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1400c7461  mov     [rbp+200h+ObjectAttributes.RootDirectory], rax
0x1400c7465  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400c746a  lea     rax, [rsp+300h+DestinationString]
0x1400c746f  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400c7476  xorps   xmm0, xmm0
0x1400c7479  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1400c747d  mov     edx, ebx; DesiredAccess
0x1400c747f  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1400c7486  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c748b  call    cs:__imp_ZwOpenKey
0x1400c7492  nop     dword ptr [rax+rax+00h]
0x1400c7497  test    eax, eax
0x1400c7499  js      short loc_1400C7505
0x1400c749b  mov     ebx, 100h
0x1400c74a0  lea     rcx, [rbp+200h+KeyInformation]; void *
0x1400c74a4  mov     r8d, ebx; Size
0x1400c74a7  xor     edx, edx; Val
0x1400c74a9  call    memset
0x1400c74ae  xor     esi, esi
0x1400c74b0  xorps   xmm0, xmm0
0x1400c74b3  xor     eax, eax
0x1400c74b5  mov     [rsp+300h+var_2D0], esi
0x1400c74b9  mov     [rsp+300h+var_288], rax
0x1400c74be  movups  [rsp+300h+var_298], xmm0
0x1400c74c3  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400c74c8  lea     rax, [rsp+300h+var_2D0]
0x1400c74cd  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1400c74d2  lea     r9, [rbp+200h+KeyInformation]; KeyInformation
0x1400c74d6  xor     r8d, r8d; KeyInformationClass
0x1400c74d9  mov     [rsp+300h+Length], ebx; Length
0x1400c74dd  mov     edx, esi; Index
0x1400c74df  mov     edi, 1
0x1400c74e4  call    cs:__imp_ZwEnumerateKey
0x1400c74eb  nop     dword ptr [rax+rax+00h]
0x1400c74f0  test    eax, eax
0x1400c74f2  jns     short loc_1400C7545
0x1400c74f4  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x1400c74f9  call    cs:__imp_ZwClose
0x1400c7500  nop     dword ptr [rax+rax+00h]
0x1400c7505  mov     rcx, [rsp+300h+DeviceRegKey]; Handle
0x1400c750a  call    cs:__imp_ZwClose
0x1400c7511  nop     dword ptr [rax+rax+00h]
0x1400c7516  mov     eax, r14d
0x1400c7519  mov     rcx, [rbp+200h+var_30]
0x1400c7520  xor     rcx, rsp; StackCookie
0x1400c7523  call    __security_check_cookie
0x1400c7528  lea     r11, [rsp+300h+var_20]
0x1400c7530  mov     rbx, [r11+40h]
0x1400c7534  mov     rsi, [r11+48h]
0x1400c7538  mov     rsp, r11
0x1400c753b  pop     r15
0x1400c753d  pop     r14
0x1400c753f  pop     r12
0x1400c7541  pop     rdi
0x1400c7542  pop     rbp
0x1400c7543  retn
0x1400c7545  lea     rax, [rbp+200h+Src]
0x1400c7549  mov     [rsp+300h+DestinationString.Buffer], rax
0x1400c754e  mov     eax, [rbp+200h+var_244]
0x1400c7551  mov     [rsp+300h+DestinationString.Length], ax
0x1400c7556  mov     [rsp+300h+DestinationString.MaximumLength], ax
0x1400c755b  movzx   r9d, ax
0x1400c755f  cmp     ax, bx
0x1400c7562  jnb     loc_1400C77A5
0x1400c7568  shr     r9, 1; MaxCount
0x1400c756b  lea     r8, [rbp+200h+Src]; Src
0x1400c756f  mov     edx, 80h; SizeInWords
0x1400c7574  lea     rcx, [rbp+200h+Dst]; Dst
0x1400c757b  call    cs:__imp_wcsncpy_s
0x1400c7582  nop     dword ptr [rax+rax+00h]
0x1400c7587  cmp     [rsp+300h+DestinationString.Length], bx
0x1400c758c  jb      loc_1400C7715
0x1400c7592  xor     eax, eax
0x1400c7594  mov     dword ptr [rbp+200h+var_14C], 0FFFFFFFFh
0x1400c759e  add     esi, edi
0x1400c75a0  mov     [rbp+200h+var_32], ax
0x1400c75a7  mov     [rsp+300h+var_2B0], esi
0x1400c75ab  lea     rdi, [rbp+200h+Dst]
0x1400c75b2  mov     [rbp+200h+var_150], eax
0x1400c75b8  xor     ebx, ebx
0x1400c75ba  mov     dword ptr [rbp+200h+var_14C+4], eax
0x1400c75c0  cmp     ebx, 4
0x1400c75c3  jnb     short loc_1400C75F9
0x1400c75c5  mov     edx, 2Ch ; ','; Ch
0x1400c75ca  mov     rcx, rdi; Str
0x1400c75cd  call    wcschr
0x1400c75d2  mov     r9, rax
0x1400c75d5  test    rax, rax
0x1400c75d8  jz      short loc_1400C75DF
0x1400c75da  xor     edx, edx
0x1400c75dc  mov     [rax], dx
0x1400c75df  mov     rcx, rdi
0x1400c75e2  call    xwtol
0x1400c75e7  mov     [rbp+rbx*4+200h+var_150], eax
0x1400c75ee  lea     rdi, [r9+2]
0x1400c75f2  inc     ebx
0x1400c75f4  test    r9, r9
0x1400c75f7  jnz     short loc_1400C75C0
0x1400c75f9  mov     eax, [rbp+200h+var_150]
0x1400c75ff  mov     ebx, 100h
0x1400c7604  test    eax, eax
0x1400c7606  jz      loc_1400C74C3
0x1400c760c  mov     ecx, dword ptr [rbp+200h+var_14C]
0x1400c7612  cmp     ecx, 0FFFFFFFFh
0x1400c7615  jz      loc_1400C74C3
0x1400c761b  mov     dword ptr [rsp+300h+var_298], eax
0x1400c761f  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1400c7623  mov     eax, dword ptr [rbp+200h+var_14C+4]
0x1400c7629  xorps   xmm0, xmm0
0x1400c762c  mov     dword ptr [rsp+300h+var_298+8], eax
0x1400c7630  mov     edx, 2000000h; DesiredAccess
0x1400c7635  mov     rax, [rsp+300h+KeyHandle]
0x1400c763a  mov     [rbp+200h+ObjectAttributes.RootDirectory], rax
0x1400c763e  lea     rax, [rsp+300h+DestinationString]
0x1400c7643  mov     dword ptr [rsp+300h+var_298+4], ecx
0x1400c7647  lea     rcx, [rsp+300h+Handle]; KeyHandle
0x1400c764c  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1400c7650  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400c7657  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1400c765e  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c7663  call    cs:__imp_ZwOpenKey
0x1400c766a  nop     dword ptr [rax+rax+00h]
0x1400c766f  test    eax, eax
0x1400c7671  js      loc_1400C74C3
0x1400c7677  xor     edi, edi
0x1400c7679  mov     [rbp+200h+var_138], 31h ; '1'
0x1400c7683  mov     rax, 650064006F004Dh
0x1400c768d  xor     ebx, ebx
0x1400c768f  mov     qword ptr [rbp+200h+SourceString], rax
0x1400c7696  lea     esi, [rdi+1]
0x1400c7699  lea     rdx, [rbp+200h+SourceString]; SourceString
0x1400c76a0  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x1400c76a5  call    cs:__imp_RtlInitUnicodeString
0x1400c76ac  nop     dword ptr [rax+rax+00h]
0x1400c76b1  mov     rcx, [rsp+300h+Handle]; KeyHandle
0x1400c76b6  lea     rax, [rsp+300h+var_2D0]
0x1400c76bb  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1400c76c0  lea     r9, [rbp+200h+KeyInformation]; KeyValueInformation
0x1400c76c4  mov     r8d, esi; KeyValueInformationClass
0x1400c76c7  mov     [rsp+300h+Length], 100h; Length
0x1400c76cf  lea     rdx, [rsp+300h+DestinationString]; ValueName
0x1400c76d4  call    cs:__imp_ZwQueryValueKey
0x1400c76db  nop     dword ptr [rax+rax+00h]
0x1400c76e0  test    eax, eax
0x1400c76e2  jns     short loc_1400C773D
0x1400c76e4  test    edi, edi
0x1400c76e6  jnz     short loc_1400C76F6
0x1400c76e8  add     word ptr [rbp+200h+var_138], si
0x1400c76ef  add     ebx, esi
0x1400c76f1  cmp     ebx, 9
0x1400c76f4  jb      short loc_1400C7699
0x1400c76f6  mov     rcx, [rsp+300h+Handle]; Handle
0x1400c76fb  call    cs:__imp_ZwClose
0x1400c7702  nop     dword ptr [rax+rax+00h]
0x1400c7707  mov     esi, [rsp+300h+var_2B0]
0x1400c770b  mov     ebx, 100h
0x1400c7710  jmp     loc_1400C74C3
0x1400c7715  movzx   ecx, [rsp+300h+DestinationString.Length]
0x1400c771a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1400c771e  cmp     rcx, rbx
0x1400c7721  jnb     loc_1400C77C2
0x1400c7727  xor     eax, eax
0x1400c7729  mov     [rbp+rcx+200h+Dst], ax
0x1400c7731  jmp     loc_1400C7592
0x1400c7736  xor     eax, eax
0x1400c7738  jmp     loc_1400C7519
0x1400c773d  mov     eax, [rbp+200h+var_248]
0x1400c7740  lea     r8, [rbp+200h+KeyInformation]
0x1400c7744  mov     edx, 80h; SizeInWords
0x1400c7749  lea     rcx, [rbp+200h+Dst]; Dst
0x1400c7750  add     r8, rax; Src
0x1400c7753  lea     r9d, [rdx-1]; MaxCount
0x1400c7757  call    cs:__imp_wcsncpy_s
0x1400c775e  nop     dword ptr [rax+rax+00h]
0x1400c7763  mov     al, r12b
0x1400c7766  mov     dword ptr [rsp+300h+var_288], 0
0x1400c776e  neg     al
0x1400c7770  lea     rdx, [rsp+300h+var_298]
0x1400c7775  mov     r8d, esi
0x1400c7778  sbb     ecx, ecx
0x1400c777a  or      eax, 0FFFFFFFFh
0x1400c777d  not     ecx
0x1400c777f  mov     dword ptr [rsp+300h+var_298+8], eax
0x1400c7783  and     ecx, 38h
0x1400c7786  mov     dword ptr [rsp+300h+var_288+4], eax
0x1400c778a  mov     dword ptr [rsp+300h+var_298+0Ch], ecx
0x1400c778e  lea     rcx, [rbp+200h+Dst]; Str
0x1400c7795  call    ParseModeCap
0x1400c779a  test    eax, eax
0x1400c779c  jnz     short loc_1400C77AD
0x1400c779e  mov     edi, esi
0x1400c77a0  jmp     loc_1400C76E8
0x1400c77a5  mov     r9, rbx
0x1400c77a8  jmp     loc_1400C7568
0x1400c77ad  mov     r8d, r14d
0x1400c77b0  lea     rcx, [rsp+300h+var_298]
0x1400c77b5  mov     rdx, r15
0x1400c77b8  call    InsertModecapList
0x1400c77bd  mov     r14d, eax
0x1400c77c0  jmp     short loc_1400C779E
0x1400c77c2  call    __report_rangecheckfailure
```
