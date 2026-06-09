# SampRetrieveKeyForPostBootPromote(ulong *)

- ea: `0x180070680`
- end: `0x180070908`
- name: `?SampRetrieveKeyForPostBootPromote@@YAJPEAK@Z`
- size: `648`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006e734`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x180070680`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180070709`
- `ntdll!NtOpenKey` at `0x180070709`
- `ntdll!NtQueryValueKey` at `0x180070751`
- `ntdll!NtQueryValueKey` at `0x18007079d`
- `ntdll!NtQueryValueKey` at `0x180070751`
- `ntdll!NtQueryValueKey` at `0x18007079d`
- `ntdll!NtClose` at `0x180070877`
- `ntdll!NtClose` at `0x180070877`
- `ntdll!RtlInitUnicodeString` at `0x1800706cd`
- `ntdll!RtlInitUnicodeString` at `0x18007072b`
- `ntdll!RtlInitUnicodeString` at `0x1800706cd`
- `ntdll!RtlInitUnicodeString` at `0x18007072b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007076a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007076a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007080e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007080e`

## string_xrefs

- `0x1800706b2`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 __fastcall SampRetrieveKeyForPostBootPromote(unsigned int *a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  _DWORD *v5; // r14
  NTSTATUS v6; // eax
  PUNICODE_STRING v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A8h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SAMSS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v3 = v2;
  if ( v2 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v8 = 109;
      v9 = (unsigned int)v2;
      goto LABEL_31;
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"PostPromoteBoot");
    v4 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    v3 = v4;
    if ( v4 == -1073741789 )
    {
      v5 = LocalAlloc(0x40u, ResultLength);
      if ( v5 )
      {
        v6 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v5, ResultLength, &ResultLength);
        v3 = v6;
        if ( v6 < 0 )
        {
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control[3].Buffer,
              105,
              WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
              (unsigned int)v6);
        }
        else if ( v5[2] == 4 )
        {
          *a1 = v5[3];
        }
        else
        {
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 104, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
          v3 = -1073741823;
        }
        LocalFree(v5);
      }
      else
      {
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 106, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
        v3 = -1073741801;
      }
    }
    else if ( v4 != -1073741772
           && v4
           && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
           && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 107, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v4);
    }
    if ( NtClose(KeyHandle) >= 0 )
      goto LABEL_32;
    v7 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v8 = 108;
      v9 = v3;
LABEL_31:
      WPP_SF_d(v7[3].Buffer, v8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v9);
LABEL_32:
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_DWORD *)(&v7[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v7[3].Buffer, 110, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v3, v3);
  return v3;
}

```

## disassembly

```asm
0x180070680  mov     [rsp-18h+arg_0], rbx
0x180070685  mov     [rsp-18h+arg_18], r12
0x18007068a  push    rbp
0x18007068b  push    r14
0x18007068d  push    r15
0x18007068f  mov     rbp, rsp
0x180070692  sub     rsp, 80h
0x180070699  xorps   xmm0, xmm0
0x18007069c  mov     [rbp+KeyHandle], 0
0x1800706a4  mov     r15, rcx
0x1800706a7  mov     [rbp+arg_8], 0
0x1800706ae  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800706b2  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800706b9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800706bd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800706c1  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800706c5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800706c9  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x1800706cd  call    cs:__imp_RtlInitUnicodeString
0x1800706d3  lea     rax, [rbp+DestinationString]
0x1800706d7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800706de  xorps   xmm0, xmm0
0x1800706e1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800706e5  mov     r14d, 40h ; '@'
0x1800706eb  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800706f3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800706f7  mov     [rbp+ObjectAttributes.Attributes], r14d
0x1800706fb  mov     edx, 10000000h; DesiredAccess
0x180070700  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180070704  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180070709  call    cs:__imp_NtOpenKey
0x18007070f  lea     r12, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180070716  mov     ebx, eax
0x180070718  test    eax, eax
0x18007071a  js      loc_18007089E
0x180070720  lea     rdx, aPostpromoteboo; "PostPromoteBoot"
0x180070727  lea     rcx, [rbp+ValueName]; DestinationString
0x18007072b  call    cs:__imp_RtlInitUnicodeString
0x180070731  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180070735  lea     rax, [rbp+arg_8]
0x180070739  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18007073e  lea     r8d, [r14-3Eh]; KeyValueInformationClass
0x180070742  xor     r9d, r9d; KeyValueInformation
0x180070745  mov     [rsp+80h+Length], 0; Length
0x18007074d  lea     rdx, [rbp+ValueName]; ValueName
0x180070751  call    cs:__imp_NtQueryValueKey
0x180070757  mov     ebx, eax
0x180070759  cmp     eax, 0C0000023h
0x18007075e  jnz     loc_180070841
0x180070764  mov     edx, [rbp+arg_8]; uBytes
0x180070767  mov     ecx, r14d; uFlags
0x18007076a  call    cs:__imp_LocalAlloc
0x180070770  mov     r14, rax
0x180070773  test    rax, rax
0x180070776  jz      loc_180070816
0x18007077c  mov     ecx, [rbp+arg_8]
0x18007077f  lea     rax, [rbp+arg_8]
0x180070783  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180070788  lea     rdx, [rbp+ValueName]; ValueName
0x18007078c  mov     [rsp+80h+Length], ecx; Length
0x180070790  mov     r9, r14; KeyValueInformation
0x180070793  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180070797  mov     r8d, 2; KeyValueInformationClass
0x18007079d  call    cs:__imp_NtQueryValueKey
0x1800707a3  mov     ebx, eax
0x1800707a5  test    eax, eax
0x1800707a7  js      short loc_1800707E4
0x1800707a9  cmp     dword ptr [r14+8], 4
0x1800707ae  jnz     short loc_1800707B9
0x1800707b0  mov     eax, [r14+0Ch]
0x1800707b4  mov     [r15], eax
0x1800707b7  jmp     short loc_18007080B
0x1800707b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800707c0  test    byte ptr [rcx+44h], 80h
0x1800707c4  jz      short loc_1800707DD
0x1800707c6  cmp     byte ptr [rcx+41h], 2
0x1800707ca  jb      short loc_1800707DD
0x1800707cc  mov     rcx, [rcx+38h]
0x1800707d0  mov     edx, 68h ; 'h'
0x1800707d5  mov     r8, r12
0x1800707d8  call    WPP_SF_
0x1800707dd  mov     ebx, 0C0000001h
0x1800707e2  jmp     short loc_18007080B
0x1800707e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800707eb  test    byte ptr [rcx+44h], 80h
0x1800707ef  jz      short loc_18007080B
0x1800707f1  cmp     byte ptr [rcx+41h], 2
0x1800707f5  jb      short loc_18007080B
0x1800707f7  mov     rcx, [rcx+38h]
0x1800707fb  mov     edx, 69h ; 'i'
0x180070800  mov     r9d, eax
0x180070803  mov     r8, r12
0x180070806  call    WPP_SF_d
0x18007080b  mov     rcx, r14; hMem
0x18007080e  call    cs:__imp_LocalFree
0x180070814  jmp     short loc_180070873
0x180070816  mov     rcx, cs:WPP_GLOBAL_Control
0x18007081d  test    byte ptr [rcx+44h], 80h
0x180070821  jz      short loc_18007083A
0x180070823  cmp     byte ptr [rcx+41h], 2
0x180070827  jb      short loc_18007083A
0x180070829  mov     rcx, [rcx+38h]
0x18007082d  mov     edx, 6Ah ; 'j'
0x180070832  mov     r8, r12
0x180070835  call    WPP_SF_
0x18007083a  mov     ebx, 0C0000017h
0x18007083f  jmp     short loc_180070873
0x180070841  cmp     eax, 0C0000034h
0x180070846  jz      short loc_180070873
0x180070848  test    eax, eax
0x18007084a  jz      short loc_180070873
0x18007084c  mov     rcx, cs:WPP_GLOBAL_Control
0x180070853  test    byte ptr [rcx+44h], 80h
0x180070857  jz      short loc_180070873
0x180070859  cmp     byte ptr [rcx+41h], 2
0x18007085d  jb      short loc_180070873
0x18007085f  mov     rcx, [rcx+38h]
0x180070863  mov     edx, 6Bh ; 'k'
0x180070868  mov     r9d, eax
0x18007086b  mov     r8, r12
0x18007086e  call    WPP_SF_d
0x180070873  mov     rcx, [rbp+KeyHandle]; Handle
0x180070877  call    cs:__imp_NtClose
0x18007087d  test    eax, eax
0x18007087f  jns     short loc_1800708C5
0x180070881  mov     rcx, cs:WPP_GLOBAL_Control
0x180070888  test    byte ptr [rcx+44h], 80h
0x18007088c  jz      short loc_1800708CC
0x18007088e  cmp     byte ptr [rcx+41h], 2
0x180070892  jb      short loc_1800708CC
0x180070894  mov     edx, 6Ch ; 'l'
0x180070899  mov     r9d, ebx
0x18007089c  jmp     short loc_1800708B9
0x18007089e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800708a5  test    byte ptr [rcx+44h], 80h
0x1800708a9  jz      short loc_1800708CC
0x1800708ab  cmp     byte ptr [rcx+41h], 2
0x1800708af  jb      short loc_1800708CC
0x1800708b1  mov     edx, 6Dh ; 'm'
0x1800708b6  mov     r9d, eax
0x1800708b9  mov     rcx, [rcx+38h]
0x1800708bd  mov     r8, r12
0x1800708c0  call    WPP_SF_d
0x1800708c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800708cc  test    dword ptr [rcx+44h], 20000h
0x1800708d3  jz      short loc_1800708ED
0x1800708d5  mov     rcx, [rcx+38h]
0x1800708d9  mov     edx, 6Eh ; 'n'
0x1800708de  mov     r9d, ebx
0x1800708e1  mov     [rsp+80h+Length], ebx
0x1800708e5  mov     r8, r12
0x1800708e8  call    WPP_SF_Dd
0x1800708ed  lea     r11, [rsp+80h+var_s0]
0x1800708f5  mov     eax, ebx
0x1800708f7  mov     rbx, [r11+20h]
0x1800708fb  mov     r12, [r11+38h]
0x1800708ff  mov     rsp, r11
0x180070902  pop     r15
0x180070904  pop     r14
0x180070906  pop     rbp
0x180070907  retn
```
