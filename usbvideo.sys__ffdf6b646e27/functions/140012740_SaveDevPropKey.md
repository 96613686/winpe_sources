# SaveDevPropKey

- ea: `0x140012740`
- end: `0x140012b69`
- name: `SaveDevPropKey`
- size: `1065`
- prototype: `__int64 __usercall@<rax>(PCWCH String1@<rcx>, PDEVICE_OBJECT Pdo, PCWSTR SourceString)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140012740`
- `0x14001b118`
- `0x140023660`
- `0x1400236dc`
- `0x1400237b0`
- `0x140040a30`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x1400128d1`
- `ntoskrnl!RtlGUIDFromString` at `0x1400128d1`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400128ef`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400128ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001279a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400127ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400127c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012858`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400128bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001279a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400127ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400127c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012858`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400128bd`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400129b9`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400129b9`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1400129ea`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1400129ea`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1400127fb`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14001288d`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1400127fb`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14001288d`

## pseudocode

```c
__int64 __fastcall SaveDevPropKey(
        PCWCH String1,
        unsigned int a2,
        void *a3,
        ULONG a4,
        PDEVICE_OBJECT Pdo,
        PCWSTR SourceString)
{
  __int64 v10; // r8
  int v11; // r8d
  DEVPROPTYPE v12; // ebx
  unsigned int v13; // eax
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  PDEVICE_OBJECT v16; // rcx
  int v17; // edx
  UNICODE_STRING *p_GuidString; // r9
  BOOLEAN CaseInSensitive[8]; // [rsp+20h] [rbp-89h]
  PVOID Data; // [rsp+28h] [rbp-81h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  ULONG Type; // [rsp+50h] [rbp-59h] BYREF
  ULONG RequiredSize; // [rsp+54h] [rbp-55h] BYREF
  struct _UNICODE_STRING v25; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING v26; // [rsp+68h] [rbp-41h] BYREF
  UNICODE_STRING GuidString; // [rsp+78h] [rbp-31h] BYREF
  UNICODE_STRING String; // [rsp+88h] [rbp-21h] BYREF
  DEVPROPKEY Guid; // [rsp+98h] [rbp-11h] BYREF

  v25 = 0;
  DestinationString = 0;
  v26 = 0;
  if ( !Pdo )
    return 0;
  RtlInitUnicodeString(&DestinationString, String1);
  RtlInitUnicodeString(&v25, SourceString);
  RtlInitUnicodeString(&v26, L",");
  if ( !SourceString
    || DestinationString.Length < v25.Length
    || RtlCompareUnicodeStrings(
         String1,
         (unsigned __int64)v25.Length >> 1,
         v25.Buffer,
         (unsigned __int64)v25.Length >> 1,
         1u) )
  {
    return 0;
  }
  GuidString = 0;
  String = 0;
  memset(&Guid, 0, sizeof(Guid));
  if ( (unsigned __int64)(v25.Length + (unsigned int)v26.Length) + 76 >= DestinationString.Length )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v15 = 25;
    goto LABEL_45;
  }
  RtlInitUnicodeString(&GuidString, &DestinationString.Buffer[(unsigned __int64)v25.Length >> 1]);
  GuidString.Length = 76;
  if ( RtlCompareUnicodeStrings(
         &DestinationString.Buffer[((unsigned __int64)v25.Length >> 1) + 38],
         (unsigned __int64)v26.Length >> 1,
         v26.Buffer,
         (unsigned __int64)v26.Length >> 1,
         1u) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v15 = 24;
    goto LABEL_45;
  }
  RtlInitUnicodeString(
    &String,
    &DestinationString.Buffer[((unsigned __int64)(v25.Length + (unsigned int)v26.Length) >> 1) + 38]);
  if ( RtlGUIDFromString(&GuidString, &Guid.fmtid) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v17 = 23;
    p_GuidString = &GuidString;
LABEL_35:
    WPP_SF_ZZ(v16->AttachedDevice, v17, v11, (_DWORD)p_GuidString, (__int64)&DestinationString);
    return 0;
  }
  if ( RtlUnicodeStringToInteger(&String, 0, &Guid.pid) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v17 = 22;
    p_GuidString = &String;
    goto LABEL_35;
  }
  if ( Guid.pid >= 2 )
  {
    switch ( a2 )
    {
      case 1u:
        v12 = 18;
        break;
      case 3u:
        v12 = 4099;
        break;
      case 4u:
        v12 = 7;
        break;
      case 7u:
        v12 = 8210;
        break;
      default:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, a2);
        return 0;
    }
    Type = 0;
    RequiredSize = 0;
    if ( IoGetDevicePropertyData(Pdo, &Guid, 0, 0, 0, 0, &RequiredSize, &Type) == -1073741772 )
    {
      v13 = IoSetDevicePropertyData(Pdo, &Guid, 0, 1u, v12, a4, a3);
      if ( v13 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v13);
      return 0;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      return 0;
    v15 = 19;
LABEL_45:
    WPP_SF_Z(v14->AttachedDevice, v15, v10, &DestinationString, *(_QWORD *)CaseInSensitive, Data);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_Zd(WPP_GLOBAL_Control->AttachedDevice, Guid.pid, v11, (unsigned int)&DestinationString, Guid.pid);
  return 0;
}

```

## disassembly

```asm
0x140012740  push    rbp
0x140012742  push    rbx
0x140012743  push    rsi
0x140012744  push    rdi
0x140012745  push    r12
0x140012747  push    r14
0x140012749  push    r15
0x14001274b  lea     rbp, [rsp-17h]
0x140012750  sub     rsp, 0C0h
0x140012757  mov     rax, cs:__security_cookie
0x14001275e  xor     rax, rsp
0x140012761  mov     [rbp+47h+var_40], rax
0x140012765  mov     r14, [rbp+47h+Pdo]
0x140012769  xorps   xmm0, xmm0
0x14001276c  mov     rbx, [rbp+47h+SourceString]
0x140012770  xorps   xmm1, xmm1
0x140012773  mov     r12d, r9d
0x140012776  mov     r15, r8
0x140012779  mov     esi, edx
0x14001277b  mov     rdi, rcx
0x14001277e  movups  xmmword ptr [rbp+47h+var_98.Length], xmm0
0x140012782  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x140012786  movups  xmmword ptr [rbp+47h+var_88.Length], xmm0
0x14001278a  test    r14, r14
0x14001278d  jz      loc_140012B48
0x140012793  mov     rdx, rcx; SourceString
0x140012796  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14001279a  call    cs:__imp_RtlInitUnicodeString
0x1400127a1  nop     dword ptr [rax+rax+00h]
0x1400127a6  mov     rdx, rbx; SourceString
0x1400127a9  lea     rcx, [rbp+47h+var_98]; DestinationString
0x1400127ad  call    cs:__imp_RtlInitUnicodeString
0x1400127b4  nop     dword ptr [rax+rax+00h]
0x1400127b9  lea     rdx, asc_1400462F8; ","
0x1400127c0  lea     rcx, [rbp+47h+var_88]; DestinationString
0x1400127c4  call    cs:__imp_RtlInitUnicodeString
0x1400127cb  nop     dword ptr [rax+rax+00h]
0x1400127d0  test    rbx, rbx
0x1400127d3  jz      loc_140012B48
0x1400127d9  movzx   eax, [rbp+47h+var_98.Length]
0x1400127dd  cmp     [rbp+47h+DestinationString.Length], ax
0x1400127e1  jb      loc_140012B48
0x1400127e7  mov     r8, [rbp+47h+var_98.Buffer]; String2
0x1400127eb  mov     edx, eax
0x1400127ed  shr     rdx, 1; String1Length
0x1400127f0  mov     rcx, rdi; String1
0x1400127f3  mov     r9, rdx; String2Length
0x1400127f6  mov     [rsp+0F0h+CaseInSensitive], 1; CaseInSensitive
0x1400127fb  call    cs:__imp_RtlCompareUnicodeStrings
0x140012802  nop     dword ptr [rax+rax+00h]
0x140012807  test    eax, eax
0x140012809  jnz     loc_140012B48
0x14001280f  movzx   edx, [rbp+47h+var_88.Length]
0x140012813  xor     eax, eax
0x140012815  mov     [rbp+47h+Value], eax
0x140012818  xorps   xmm0, xmm0
0x14001281b  movzx   eax, [rbp+47h+var_98.Length]
0x14001281f  mov     ebx, 4Ch ; 'L'
0x140012824  add     edx, eax
0x140012826  xorps   xmm1, xmm1
0x140012829  movzx   eax, [rbp+47h+DestinationString.Length]
0x14001282d  add     rdx, rbx
0x140012830  movups  xmmword ptr [rbp+47h+GuidString.Length], xmm0
0x140012834  movups  xmmword ptr [rbp+47h+String.Length], xmm1
0x140012838  movups  xmmword ptr [rbp+47h+Guid.Data1], xmm0
0x14001283c  cmp     rdx, rax
0x14001283f  jnb     loc_140012B1D
0x140012845  movzx   ecx, [rbp+47h+var_98.Length]
0x140012849  mov     rax, [rbp+47h+DestinationString.Buffer]
0x14001284d  shr     rcx, 1
0x140012850  lea     rdx, [rax+rcx*2]; SourceString
0x140012854  lea     rcx, [rbp+47h+GuidString]; DestinationString
0x140012858  call    cs:__imp_RtlInitUnicodeString
0x14001285f  nop     dword ptr [rax+rax+00h]
0x140012864  movzx   ecx, [rbp+47h+var_98.Length]
0x140012868  mov     rax, [rbp+47h+DestinationString.Buffer]
0x14001286c  movzx   edx, [rbp+47h+var_88.Length]
0x140012870  add     rax, rbx
0x140012873  mov     r8, [rbp+47h+var_88.Buffer]; String2
0x140012877  shr     rcx, 1
0x14001287a  shr     rdx, 1; String1Length
0x14001287d  mov     r9, rdx; String2Length
0x140012880  mov     [rbp+47h+GuidString.Length], bx
0x140012884  mov     [rsp+0F0h+CaseInSensitive], 1; CaseInSensitive
0x140012889  lea     rcx, [rax+rcx*2]; String1
0x14001288d  call    cs:__imp_RtlCompareUnicodeStrings
0x140012894  nop     dword ptr [rax+rax+00h]
0x140012899  test    eax, eax
0x14001289b  jnz     loc_140012AFD
0x1400128a1  movzx   edx, [rbp+47h+var_88.Length]
0x1400128a5  lea     rcx, [rbp+47h+String]; DestinationString
0x1400128a9  movzx   eax, [rbp+47h+var_98.Length]
0x1400128ad  add     edx, eax
0x1400128af  mov     rax, [rbp+47h+DestinationString.Buffer]
0x1400128b3  add     rax, rbx
0x1400128b6  shr     rdx, 1
0x1400128b9  lea     rdx, [rax+rdx*2]; SourceString
0x1400128bd  call    cs:__imp_RtlInitUnicodeString
0x1400128c4  nop     dword ptr [rax+rax+00h]
0x1400128c9  lea     rdx, [rbp+47h+Guid]; Guid
0x1400128cd  lea     rcx, [rbp+47h+GuidString]; GuidString
0x1400128d1  call    cs:__imp_RtlGUIDFromString
0x1400128d8  nop     dword ptr [rax+rax+00h]
0x1400128dd  test    eax, eax
0x1400128df  jnz     loc_140012AD9
0x1400128e5  lea     r8, [rbp+47h+Value]; Value
0x1400128e9  xor     edx, edx; Base
0x1400128eb  lea     rcx, [rbp+47h+String]; String
0x1400128ef  call    cs:__imp_RtlUnicodeStringToInteger
0x1400128f6  nop     dword ptr [rax+rax+00h]
0x1400128fb  test    eax, eax
0x1400128fd  jnz     loc_140012A9B
0x140012903  mov     edx, [rbp+47h+Value]
0x140012906  cmp     edx, 2
0x140012909  jb      loc_140012A64
0x14001290f  mov     eax, esi
0x140012911  lea     edi, [rbx-3Ah]
0x140012914  sub     eax, 1
0x140012917  jz      short loc_140012979
0x140012919  sub     eax, 2
0x14001291c  jz      short loc_140012972
0x14001291e  sub     eax, 1
0x140012921  jz      short loc_14001296B
0x140012923  cmp     eax, 3
0x140012926  jz      short loc_140012964
0x140012928  mov     rcx, cs:WPP_GLOBAL_Control
0x14001292f  lea     rax, WPP_GLOBAL_Control
0x140012936  cmp     rcx, rax
0x140012939  jz      loc_140012B48
0x14001293f  cmp     byte ptr [rcx+29h], 2
0x140012943  jb      loc_140012B48
0x140012949  mov     rcx, [rcx+18h]
0x14001294d  lea     edx, [rbx-38h]
0x140012950  mov     r9d, esi
0x140012953  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x14001295a  call    WPP_SF_d
0x14001295f  jmp     loc_140012B48
0x140012964  mov     ebx, 2012h
0x140012969  jmp     short loc_14001297B
0x14001296b  mov     ebx, 7
0x140012970  jmp     short loc_14001297B
0x140012972  mov     ebx, 1003h
0x140012977  jmp     short loc_14001297B
0x140012979  mov     ebx, edi
0x14001297b  lea     rax, [rbp+47h+var_A0]
0x14001297f  mov     [rbp+47h+var_A0], 0
0x140012986  mov     [rsp+0F0h+Type], rax; Type
0x14001298b  lea     rdx, [rbp+47h+Guid]; PropertyKey
0x14001298f  lea     rax, [rbp+47h+var_9C]
0x140012993  mov     [rbp+47h+var_9C], 0
0x14001299a  mov     [rsp+0F0h+RequiredSize], rax; RequiredSize
0x14001299f  xor     r9d, r9d; Flags
0x1400129a2  mov     [rsp+0F0h+Data], 0; Data
0x1400129ab  xor     r8d, r8d; Lcid
0x1400129ae  mov     rcx, r14; Pdo
0x1400129b1  mov     dword ptr [rsp+0F0h+CaseInSensitive], 0; Size
0x1400129b9  call    cs:__imp_IoGetDevicePropertyData
0x1400129c0  nop     dword ptr [rax+rax+00h]
0x1400129c5  cmp     eax, 0C0000034h
0x1400129ca  jnz     short loc_140012A39
0x1400129cc  mov     [rsp+0F0h+RequiredSize], r15; Data
0x1400129d1  lea     rdx, [rbp+47h+Guid]; PropertyKey
0x1400129d5  mov     dword ptr [rsp+0F0h+Data], r12d; Size
0x1400129da  mov     r9d, 1; Flags
0x1400129e0  xor     r8d, r8d; Lcid
0x1400129e3  mov     dword ptr [rsp+0F0h+CaseInSensitive], ebx; Type
0x1400129e7  mov     rcx, r14; Pdo
0x1400129ea  call    cs:__imp_IoSetDevicePropertyData
0x1400129f1  nop     dword ptr [rax+rax+00h]
0x1400129f6  mov     r9d, eax
0x1400129f9  test    eax, eax
0x1400129fb  jz      loc_140012B48
0x140012a01  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a08  lea     rax, WPP_GLOBAL_Control
0x140012a0f  cmp     rcx, rax
0x140012a12  jz      loc_140012B48
0x140012a18  cmp     byte ptr [rcx+29h], 2
0x140012a1c  jb      loc_140012B48
0x140012a22  mov     rcx, [rcx+18h]
0x140012a26  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x140012a2d  mov     edx, edi
0x140012a2f  call    WPP_SF_d
0x140012a34  jmp     loc_140012B48
0x140012a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a40  lea     rax, WPP_GLOBAL_Control
0x140012a47  cmp     rcx, rax
0x140012a4a  jz      loc_140012B48
0x140012a50  cmp     byte ptr [rcx+29h], 5
0x140012a54  jb      loc_140012B48
0x140012a5a  mov     edx, 13h
0x140012a5f  jmp     loc_140012B3B
0x140012a64  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a6b  lea     rax, WPP_GLOBAL_Control
0x140012a72  cmp     rcx, rax
0x140012a75  jz      loc_140012B48
0x140012a7b  cmp     byte ptr [rcx+29h], 2
0x140012a7f  jb      loc_140012B48
0x140012a85  mov     rcx, [rcx+18h]
0x140012a89  lea     r9, [rbp+47h+DestinationString]
0x140012a8d  mov     dword ptr [rsp+0F0h+CaseInSensitive], edx
0x140012a91  call    WPP_SF_Zd
0x140012a96  jmp     loc_140012B48
0x140012a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012aa2  lea     rax, WPP_GLOBAL_Control
0x140012aa9  cmp     rcx, rax
0x140012aac  jz      loc_140012B48
0x140012ab2  cmp     byte ptr [rcx+29h], 2
0x140012ab6  jb      loc_140012B48
0x140012abc  mov     edx, 16h
0x140012ac1  lea     r9, [rbp+47h+String]
0x140012ac5  mov     rcx, [rcx+18h]
0x140012ac9  lea     rax, [rbp+47h+DestinationString]
0x140012acd  mov     qword ptr [rsp+0F0h+CaseInSensitive], rax
0x140012ad2  call    WPP_SF_ZZ
0x140012ad7  jmp     short loc_140012B48
0x140012ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ae0  lea     rax, WPP_GLOBAL_Control
0x140012ae7  cmp     rcx, rax
0x140012aea  jz      short loc_140012B48
0x140012aec  cmp     byte ptr [rcx+29h], 2
0x140012af0  jb      short loc_140012B48
0x140012af2  mov     edx, 17h
0x140012af7  lea     r9, [rbp+47h+GuidString]
0x140012afb  jmp     short loc_140012AC5
0x140012afd  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b04  lea     rax, WPP_GLOBAL_Control
0x140012b0b  cmp     rcx, rax
0x140012b0e  jz      short loc_140012B48
0x140012b10  cmp     byte ptr [rcx+29h], 2
0x140012b14  jb      short loc_140012B48
0x140012b16  mov     edx, 18h
0x140012b1b  jmp     short loc_140012B3B
0x140012b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b24  lea     rax, WPP_GLOBAL_Control
0x140012b2b  cmp     rcx, rax
0x140012b2e  jz      short loc_140012B48
0x140012b30  cmp     byte ptr [rcx+29h], 2
0x140012b34  jb      short loc_140012B48
0x140012b36  mov     edx, 19h
0x140012b3b  mov     rcx, [rcx+18h]
0x140012b3f  lea     r9, [rbp+47h+DestinationString]
0x140012b43  call    WPP_SF_Z
0x140012b48  xor     eax, eax
0x140012b4a  mov     rcx, [rbp+47h+var_40]
0x140012b4e  xor     rcx, rsp; StackCookie
0x140012b51  call    __security_check_cookie
0x140012b56  add     rsp, 0C0h
0x140012b5d  pop     r15
0x140012b5f  pop     r14
0x140012b61  pop     r12
0x140012b63  pop     rdi
0x140012b64  pop     rsi
0x140012b65  pop     rbx
0x140012b66  pop     rbp
0x140012b67  retn
```
