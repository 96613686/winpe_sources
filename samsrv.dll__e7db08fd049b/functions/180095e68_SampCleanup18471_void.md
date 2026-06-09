# SampCleanup18471(void)

- ea: `0x180095e68`
- end: `0x180096261`
- name: `?SampCleanup18471@@YAJXZ`
- size: `1017`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009642c`

## callees

- `0x1800022a0`
- `0x1800066f0`
- `0x180011810`
- `0x180024d6c`
- `0x1800270e0`
- `0x180027e24`
- `0x180027e70`
- `0x18002cd80`
- `0x18003cdc0`
- `0x180065b60`
- `0x180095968`
- `0x180095e68`
- `0x1800bb77c`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180095fb9`
- `ntdll!NtEnumerateKey` at `0x18009606e`
- `ntdll!NtEnumerateKey` at `0x180095fb9`
- `ntdll!NtEnumerateKey` at `0x18009606e`
- `ntdll!NtOpenKey` at `0x180095f01`
- `ntdll!NtOpenKey` at `0x18009603b`
- `ntdll!NtOpenKey` at `0x180095f01`
- `ntdll!NtOpenKey` at `0x18009603b`
- `ntdll!RtlAddActionToRXact` at `0x1800960c5`
- `ntdll!RtlAddActionToRXact` at `0x18009613a`
- `ntdll!RtlAddActionToRXact` at `0x18009618c`
- `ntdll!RtlAddActionToRXact` at `0x1800960c5`
- `ntdll!RtlAddActionToRXact` at `0x18009613a`
- `ntdll!RtlAddActionToRXact` at `0x18009618c`
- `ntdll!NtClose` at `0x1800960e2`
- `ntdll!NtClose` at `0x18009620e`
- `ntdll!NtClose` at `0x1800960e2`
- `ntdll!NtClose` at `0x18009620e`
- `ntdll!RtlInitUnicodeString` at `0x180095ec5`
- `ntdll!RtlInitUnicodeString` at `0x180096169`
- `ntdll!RtlInitUnicodeString` at `0x180095ec5`
- `ntdll!RtlInitUnicodeString` at `0x180096169`

## string_xrefs

- `0x180095e94`: `\Registry\Machine\Security\SAM\Fix18471`

## pseudocode

```c
__int64 SampCleanup18471(void)
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // ebx
  PUNICODE_STRING v3; // rcx
  __int64 v4; // rdx
  ULONG v5; // esi
  NTSTATUS v6; // edi
  USHORT v7; // bx
  ULONG v8; // ebx
  __int64 v9; // r8
  __int64 Context; // rax
  struct _SAMP_OBJECT *v11; // rdi
  __int64 v12; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyInformation[12]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int Buf1; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 Buf1_4[20]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[12]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v23; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v24[20]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v25[208]; // [rsp+100h] [rbp+0h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  Handle = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Security\\SAM\\Fix18471");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0x30019u, &ObjectAttributes);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v1 = SampAcquireWriteLock(*((_QWORD *)SampDefinedDomains + 170));
    if ( v1 < 0 )
      goto LABEL_31;
    SampSetTransactionDomain(0);
    SampSetTransactionWithinDomain(0);
    v5 = 0;
    while ( 1 )
    {
      v6 = NtEnumerateKey(KeyHandle, v5, KeyBasicInformation, KeyInformation, 0x36u, &ResultLength);
      if ( v6 >= 0 )
      {
        v7 = Buf1;
        if ( Buf1 != 10 || memcmp_0(Buf1_4, L"RXACT", 0xAu) )
        {
          DestinationString.Length = v7;
          DestinationString.Buffer = Buf1_4;
          ObjectAttributes.RootDirectory = KeyHandle;
          DestinationString.MaximumLength = v7;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v6 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v6 < 0 )
            goto LABEL_21;
          v8 = 0;
          do
          {
            v6 = NtEnumerateKey(Handle, v8, KeyBasicInformation, v22, 0x36u, &ResultLength);
            if ( v6 >= 0 )
            {
              DestinationString.Buffer = (PWSTR)v25;
              *(_DWORD *)&DestinationString.Length = 13107200;
              SampBuild18471CleanupKey(&DestinationString, Buf1_4, Buf1, v24, v23);
              v6 = RtlAddActionToRXact(SampRXactContext, 1u, &DestinationString, 0, 0, 0);
            }
            ++v8;
          }
          while ( v6 >= 0 );
          NtClose(Handle);
          Handle = 0;
          if ( v6 != -2147483622 )
          {
LABEL_21:
            v1 = 0;
            if ( v6 != -2147483622 )
              v1 = v6;
            if ( v1 >= 0 )
            {
              RtlInitUnicodeString(&DestinationString, L"Fix18471");
              v1 = RtlAddActionToRXact(SampRXactContext, 1u, &DestinationString, 0, 0, 0);
              if ( v1 >= 0 )
              {
                LOBYTE(v9) = 1;
                Context = SampCreateContext(0, 0, v9);
                v11 = (struct _SAMP_OBJECT *)Context;
                if ( Context )
                {
                  *(_QWORD *)(Context + 152) = SampKey;
                  v17 = 65540;
                  v1 = SampSetFixedAttributes(Context, &v17);
                  if ( v1 >= 0 )
                    v1 = SampStoreObjectAttributes(v11);
                  SampDeleteContext(v11);
                  if ( v1 >= 0 )
                  {
                    LOBYTE(v12) = 1;
                    v1 = SampReleaseWriteLock(v12);
                    goto LABEL_32;
                  }
                }
                else
                {
                  v1 = -1073741670;
                }
              }
            }
LABEL_31:
            SampReleaseWriteLock(0);
LABEL_32:
            if ( KeyHandle )
              NtClose(KeyHandle);
            v3 = WPP_GLOBAL_Control;
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              v4 = 18;
LABEL_36:
              WPP_SF_Dd(v3[3].Buffer, v4, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v1, v1);
            }
            return (unsigned int)v1;
          }
          DestinationString.Buffer = (PWSTR)v25;
          *(_DWORD *)&DestinationString.Length = 13107200;
          SampBuild18471CleanupKey(&DestinationString, Buf1_4, Buf1, 0, 0);
          v6 = RtlAddActionToRXact(SampRXactContext, 1u, &DestinationString, 0, 0, 0);
        }
      }
      ++v5;
      if ( v6 < 0 )
        goto LABEL_21;
    }
  }
  if ( v0 != -1073741772 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v4 = 17;
      goto LABEL_36;
    }
    return (unsigned int)v1;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180095e68  push    rbp
0x180095e6a  push    rbx
0x180095e6b  push    rsi
0x180095e6c  push    rdi
0x180095e6d  push    r12
0x180095e6f  push    r14
0x180095e71  lea     rbp, [rsp-0E8h]
0x180095e79  sub     rsp, 1E8h
0x180095e80  mov     rax, cs:__security_cookie
0x180095e87  xor     rax, rsp
0x180095e8a  mov     [rbp+110h+var_40], rax
0x180095e91  xorps   xmm0, xmm0
0x180095e94  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Security\\SAM\\Fix"...
0x180095e9b  xor     r14d, r14d
0x180095e9e  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x180095ea3  movups  xmmword ptr [rsp+210h+ObjectAttributes.Length], xmm0
0x180095ea8  mov     [rsp+210h+KeyHandle], r14
0x180095ead  movups  xmmword ptr [rsp+210h+ObjectAttributes.ObjectName], xmm0
0x180095eb2  mov     [rsp+210h+Handle], r14
0x180095eb7  movups  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x180095ebb  mov     [rsp+210h+var_1D0], r14d
0x180095ec0  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x180095ec5  call    cs:__imp_RtlInitUnicodeString
0x180095ecb  lea     rax, [rsp+210h+DestinationString]
0x180095ed0  mov     [rsp+210h+ObjectAttributes.Length], 30h ; '0'
0x180095ed8  xorps   xmm0, xmm0
0x180095edb  mov     [rsp+210h+ObjectAttributes.ObjectName], rax
0x180095ee0  lea     r8, [rsp+210h+ObjectAttributes]; ObjectAttributes
0x180095ee5  mov     [rsp+210h+ObjectAttributes.RootDirectory], r14
0x180095eea  mov     edx, 30019h; DesiredAccess
0x180095eef  mov     [rsp+210h+ObjectAttributes.Attributes], 40h ; '@'
0x180095ef7  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x180095efc  movdqu  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x180095f01  call    cs:__imp_NtOpenKey
0x180095f07  mov     ebx, eax
0x180095f09  test    eax, eax
0x180095f0b  jns     short loc_180095F65
0x180095f0d  cmp     eax, 0C0000034h
0x180095f12  jnz     short loc_180095F47
0x180095f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180095f1b  test    dword ptr [rcx+44h], 20000h
0x180095f22  jz      short loc_180095F40
0x180095f24  mov     rcx, [rcx+38h]
0x180095f28  lea     edx, [r14+10h]
0x180095f2c  xor     r9d, r9d
0x180095f2f  mov     [rsp+210h+Length], r14d
0x180095f34  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180095f3b  call    WPP_SF_Dd
0x180095f40  xor     eax, eax
0x180095f42  jmp     loc_180096242
0x180095f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180095f4e  test    dword ptr [rcx+44h], 20000h
0x180095f55  jz      loc_180096240
0x180095f5b  mov     edx, 11h
0x180095f60  jmp     loc_180096229
0x180095f65  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180095f6c  mov     rcx, [rcx+550h]
0x180095f73  call    SampAcquireWriteLock
0x180095f78  mov     ebx, eax
0x180095f7a  test    eax, eax
0x180095f7c  js      loc_1800961FD
0x180095f82  xor     ecx, ecx
0x180095f84  call    SampSetTransactionDomain
0x180095f89  xor     ecx, ecx
0x180095f8b  call    SampSetTransactionWithinDomain
0x180095f90  mov     esi, r14d
0x180095f93  mov     r12d, 8000001Ah
0x180095f99  mov     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x180095f9e  lea     rax, [rsp+210h+var_1D0]
0x180095fa3  mov     [rsp+210h+ResultLength], rax; ResultLength
0x180095fa8  lea     r9, [rbp+110h+KeyInformation]; KeyInformation
0x180095fac  xor     r8d, r8d; KeyInformationClass
0x180095faf  mov     [rsp+210h+Length], 36h ; '6'; Length
0x180095fb7  mov     edx, esi; Index
0x180095fb9  call    cs:__imp_NtEnumerateKey
0x180095fbf  mov     edi, eax
0x180095fc1  test    eax, eax
0x180095fc3  js      loc_180096142
0x180095fc9  mov     rbx, [rbp+110h+Buf1]
0x180095fcd  cmp     ebx, 0Ah
0x180095fd0  jnz     short loc_180095FED
0x180095fd2  mov     r8d, ebx; Size
0x180095fd5  lea     rdx, aRxact; "RXACT"
0x180095fdc  lea     rcx, [rbp+110h+Buf1+4]; Buf1
0x180095fe0  call    memcmp_0
0x180095fe5  test    eax, eax
0x180095fe7  jz      loc_180096142
0x180095fed  lea     rax, [rbp+110h+Buf1+4]
0x180095ff1  mov     [rsp+210h+DestinationString.Length], bx
0x180095ff6  mov     [rsp+210h+DestinationString.Buffer], rax
0x180095ffb  lea     r8, [rsp+210h+ObjectAttributes]; ObjectAttributes
0x180096000  mov     rax, [rsp+210h+KeyHandle]
0x180096005  lea     rcx, [rsp+210h+Handle]; KeyHandle
0x18009600a  mov     [rsp+210h+ObjectAttributes.RootDirectory], rax
0x18009600f  xorps   xmm0, xmm0
0x180096012  lea     rax, [rsp+210h+DestinationString]
0x180096017  mov     [rsp+210h+DestinationString.MaximumLength], bx
0x18009601c  mov     edx, 20019h; DesiredAccess
0x180096021  mov     [rsp+210h+ObjectAttributes.ObjectName], rax
0x180096026  mov     [rsp+210h+ObjectAttributes.Length], 30h ; '0'
0x18009602e  mov     [rsp+210h+ObjectAttributes.Attributes], 40h ; '@'
0x180096036  movdqu  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009603b  call    cs:__imp_NtOpenKey
0x180096041  mov     edi, eax
0x180096043  test    eax, eax
0x180096045  js      loc_18009614C
0x18009604b  mov     ebx, r14d
0x18009604e  mov     rcx, [rsp+210h+Handle]; KeyHandle
0x180096053  lea     rax, [rsp+210h+var_1D0]
0x180096058  mov     [rsp+210h+ResultLength], rax; ResultLength
0x18009605d  lea     r9, [rbp+110h+var_148]; KeyInformation
0x180096061  xor     r8d, r8d; KeyInformationClass
0x180096064  mov     [rsp+210h+Length], 36h ; '6'; Length
0x18009606c  mov     edx, ebx; Index
0x18009606e  call    cs:__imp_NtEnumerateKey
0x180096074  mov     edi, eax
0x180096076  test    eax, eax
0x180096078  js      short loc_1800960CD
0x18009607a  mov     r8d, dword ptr [rbp+110h+Buf1]; unsigned int
0x18009607e  lea     rax, [rbp+110h+var_110]
0x180096082  mov     [rsp+210h+DestinationString.Buffer], rax
0x180096087  lea     r9, [rbp+110h+var_138]; unsigned __int16 *
0x18009608b  mov     eax, [rbp+110h+var_13C]
0x18009608e  lea     rdx, [rbp+110h+Buf1+4]; unsigned __int16 *
0x180096092  lea     rcx, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x180096097  mov     [rsp+210h+Length], eax; unsigned int
0x18009609b  mov     dword ptr [rsp+210h+DestinationString.Length], 0C80000h
0x1800960a3  call    ?SampBuild18471CleanupKey@@YAXPEAU_UNICODE_STRING@@PEBGK1K@Z; SampBuild18471CleanupKey(_UNICODE_STRING *,ushort const *,ulong,ushort const *,ulong)
0x1800960a8  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x1800960af  lea     r8, [rsp+210h+DestinationString]; KeyName
0x1800960b4  xor     r9d, r9d; ValueType
0x1800960b7  mov     dword ptr [rsp+210h+ResultLength], r14d; ValueDataSize
0x1800960bc  mov     qword ptr [rsp+210h+Length], r14; ValueData
0x1800960c1  lea     edx, [r9+1]; ActionType
0x1800960c5  call    cs:__imp_RtlAddActionToRXact
0x1800960cb  mov     edi, eax
0x1800960cd  inc     ebx
0x1800960cf  test    edi, edi
0x1800960d1  jns     loc_18009604E
0x1800960d7  mov     rcx, [rsp+210h+Handle]; Handle
0x1800960dc  mov     r12d, 8000001Ah
0x1800960e2  call    cs:__imp_NtClose
0x1800960e8  mov     [rsp+210h+Handle], r14
0x1800960ed  cmp     edi, r12d
0x1800960f0  jnz     short loc_18009614C
0x1800960f2  mov     r8d, dword ptr [rbp+110h+Buf1]; unsigned int
0x1800960f6  lea     rax, [rbp+110h+var_110]
0x1800960fa  xor     r9d, r9d; unsigned __int16 *
0x1800960fd  mov     [rsp+210h+DestinationString.Buffer], rax
0x180096102  lea     rdx, [rbp+110h+Buf1+4]; unsigned __int16 *
0x180096106  mov     dword ptr [rsp+210h+DestinationString.Length], 0C80000h
0x18009610e  lea     rcx, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x180096113  mov     [rsp+210h+Length], r14d; unsigned int
0x180096118  call    ?SampBuild18471CleanupKey@@YAXPEAU_UNICODE_STRING@@PEBGK1K@Z; SampBuild18471CleanupKey(_UNICODE_STRING *,ushort const *,ulong,ushort const *,ulong)
0x18009611d  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x180096124  lea     r8, [rsp+210h+DestinationString]; KeyName
0x180096129  xor     r9d, r9d; ValueType
0x18009612c  mov     dword ptr [rsp+210h+ResultLength], r14d; ValueDataSize
0x180096131  mov     qword ptr [rsp+210h+Length], r14; ValueData
0x180096136  lea     edx, [r9+1]; ActionType
0x18009613a  call    cs:__imp_RtlAddActionToRXact
0x180096140  mov     edi, eax
0x180096142  inc     esi
0x180096144  test    edi, edi
0x180096146  jns     loc_180095F99
0x18009614c  cmp     edi, r12d
0x18009614f  mov     ebx, r14d
0x180096152  cmovnz  ebx, edi
0x180096155  test    ebx, ebx
0x180096157  js      loc_1800961FD
0x18009615d  lea     rdx, aFix18471; "Fix18471"
0x180096164  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x180096169  call    cs:__imp_RtlInitUnicodeString
0x18009616f  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x180096176  lea     r8, [rsp+210h+DestinationString]; KeyName
0x18009617b  xor     r9d, r9d; ValueType
0x18009617e  mov     dword ptr [rsp+210h+ResultLength], r14d; ValueDataSize
0x180096183  mov     qword ptr [rsp+210h+Length], r14; ValueData
0x180096188  lea     edx, [r9+1]; ActionType
0x18009618c  call    cs:__imp_RtlAddActionToRXact
0x180096192  mov     ebx, eax
0x180096194  test    eax, eax
0x180096196  js      short loc_1800961FD
0x180096198  mov     r8b, 1
0x18009619b  xor     edx, edx
0x18009619d  xor     ecx, ecx
0x18009619f  call    ?SampCreateContext@@YAPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@KE@Z; SampCreateContext(_SAMP_OBJECT_TYPE,ulong,uchar)
0x1800961a4  mov     rdi, rax
0x1800961a7  test    rax, rax
0x1800961aa  jz      short loc_1800961F8
0x1800961ac  mov     rcx, cs:SampKey
0x1800961b3  lea     rdx, [rsp+210h+var_1B8]
0x1800961b8  mov     [rax+98h], rcx
0x1800961bf  mov     rcx, rax
0x1800961c2  mov     [rsp+210h+var_1B8], 10004h
0x1800961ca  call    SampSetFixedAttributes
0x1800961cf  mov     ebx, eax
0x1800961d1  test    eax, eax
0x1800961d3  js      short loc_1800961E1
0x1800961d5  mov     dl, 1
0x1800961d7  mov     rcx, rdi; struct _SAMP_OBJECT *
0x1800961da  call    SampStoreObjectAttributes
0x1800961df  mov     ebx, eax
0x1800961e1  mov     rcx, rdi; HandleId
0x1800961e4  call    SampDeleteContext
0x1800961e9  test    ebx, ebx
0x1800961eb  js      short loc_1800961FD
0x1800961ed  mov     cl, 1
0x1800961ef  call    SampReleaseWriteLock
0x1800961f4  mov     ebx, eax
0x1800961f6  jmp     short loc_180096204
0x1800961f8  mov     ebx, 0C000009Ah
0x1800961fd  xor     ecx, ecx
0x1800961ff  call    SampReleaseWriteLock
0x180096204  mov     rcx, [rsp+210h+KeyHandle]; Handle
0x180096209  test    rcx, rcx
0x18009620c  jz      short loc_180096214
0x18009620e  call    cs:__imp_NtClose
0x180096214  mov     rcx, cs:WPP_GLOBAL_Control
0x18009621b  test    dword ptr [rcx+44h], 20000h
0x180096222  jz      short loc_180096240
0x180096224  mov     edx, 12h
0x180096229  mov     rcx, [rcx+38h]
0x18009622d  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180096234  mov     r9d, ebx
0x180096237  mov     [rsp+210h+Length], ebx
0x18009623b  call    WPP_SF_Dd
0x180096240  mov     eax, ebx
0x180096242  mov     rcx, [rbp+110h+var_40]
0x180096249  xor     rcx, rsp; StackCookie
0x18009624c  call    __security_check_cookie
0x180096251  add     rsp, 1E8h
0x180096258  pop     r14
0x18009625a  pop     r12
0x18009625c  pop     rdi
0x18009625d  pop     rsi
0x18009625e  pop     rbx
0x18009625f  pop     rbp
0x180096260  retn
```
