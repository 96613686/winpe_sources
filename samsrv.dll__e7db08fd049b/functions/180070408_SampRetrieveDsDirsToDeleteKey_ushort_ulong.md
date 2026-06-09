# SampRetrieveDsDirsToDeleteKey(ushort * *,ulong *)

- ea: `0x180070408`
- end: `0x180070679`
- name: `?SampRetrieveDsDirsToDeleteKey@@YAJPEAPEAGPEAK@Z`
- size: `625`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ec7c`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x180070408`
- `0x1800bb788`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180070490`
- `ntdll!NtOpenKey` at `0x180070490`
- `ntdll!NtQueryValueKey` at `0x1800704d8`
- `ntdll!NtQueryValueKey` at `0x180070523`
- `ntdll!NtQueryValueKey` at `0x1800704d8`
- `ntdll!NtQueryValueKey` at `0x180070523`
- `ntdll!NtClose` at `0x1800705ec`
- `ntdll!NtClose` at `0x1800705ec`
- `ntdll!RtlInitUnicodeString` at `0x180070456`
- `ntdll!RtlInitUnicodeString` at `0x1800704b2`
- `ntdll!RtlInitUnicodeString` at `0x180070456`
- `ntdll!RtlInitUnicodeString` at `0x1800704b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800704f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070537`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800704f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070537`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007058e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007058e`

## string_xrefs

- `0x180070437`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 __fastcall SampRetrieveDsDirsToDeleteKey(unsigned __int16 **a1, unsigned int *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int *v7; // rsi
  NTSTATUS v8; // eax
  unsigned __int16 *v9; // rax
  PUNICODE_STRING v10; // rcx
  __int64 v11; // rdx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+C0h] [rbp+40h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+48h] BYREF

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
  v4 = NtOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v5 = v4;
  if ( v4 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v11 = 166;
      goto LABEL_26;
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"DsDirs");
    v6 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    v5 = v6;
    if ( v6 == -1073741789 )
    {
      v7 = (unsigned int *)LocalAlloc(0x40u, ResultLength);
      if ( v7 )
      {
        v8 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v7, ResultLength, &ResultLength);
        v5 = v8;
        if ( v8 < 0 )
        {
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control[3].Buffer,
              162,
              WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
              (unsigned int)v8);
        }
        else
        {
          v9 = (unsigned __int16 *)LocalAlloc(0x40u, v7[2]);
          *a1 = v9;
          if ( v9 )
          {
            memcpy_0(v9, v7 + 3, v7[2]);
            *a2 = v7[2];
          }
          else
          {
            v5 = -1073741801;
          }
        }
        LocalFree(v7);
      }
      else
      {
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 163, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
        v5 = -1073741801;
      }
    }
    else if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 164, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v6);
    }
    v4 = NtClose(KeyHandle);
    if ( v4 >= 0 )
      goto LABEL_27;
    v10 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v11 = 165;
LABEL_26:
      WPP_SF_d(v10[3].Buffer, v11, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v4);
LABEL_27:
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_DWORD *)(&v10[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v10[3].Buffer, 167, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v5, v5);
  return v5;
}

```

## disassembly

```asm
0x180070408  mov     [rsp-28h+arg_0], rbx
0x18007040d  push    rbp
0x18007040e  push    rsi
0x18007040f  push    r12
0x180070411  push    r14
0x180070413  push    r15
0x180070415  mov     rbp, rsp
0x180070418  sub     rsp, 80h
0x18007041f  xorps   xmm0, xmm0
0x180070422  mov     [rbp+KeyHandle], 0
0x18007042a  mov     r15, rdx
0x18007042d  mov     [rbp+arg_10], 0
0x180070434  mov     r14, rcx
0x180070437  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x18007043e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180070442  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180070446  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007044a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007044e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180070452  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x180070456  call    cs:__imp_RtlInitUnicodeString
0x18007045c  lea     rax, [rbp+DestinationString]
0x180070460  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180070467  xorps   xmm0, xmm0
0x18007046a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007046e  mov     esi, 40h ; '@'
0x180070473  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007047b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007047f  mov     [rbp+ObjectAttributes.Attributes], esi
0x180070482  mov     edx, 10000000h; DesiredAccess
0x180070487  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18007048b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180070490  call    cs:__imp_NtOpenKey
0x180070496  lea     r12, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18007049d  mov     ebx, eax
0x18007049f  test    eax, eax
0x1800704a1  js      loc_180070610
0x1800704a7  lea     rdx, aDsdirs; "DsDirs"
0x1800704ae  lea     rcx, [rbp+ValueName]; DestinationString
0x1800704b2  call    cs:__imp_RtlInitUnicodeString
0x1800704b8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800704bc  lea     rax, [rbp+arg_10]
0x1800704c0  mov     [rsp+80h+ResultLength], rax; ResultLength
0x1800704c5  lea     r8d, [rsi-3Eh]; KeyValueInformationClass
0x1800704c9  xor     r9d, r9d; KeyValueInformation
0x1800704cc  mov     [rsp+80h+Length], 0; Length
0x1800704d4  lea     rdx, [rbp+ValueName]; ValueName
0x1800704d8  call    cs:__imp_NtQueryValueKey
0x1800704de  mov     ebx, eax
0x1800704e0  cmp     eax, 0C0000023h
0x1800704e5  jnz     loc_1800705C1
0x1800704eb  mov     edx, [rbp+arg_10]; uBytes
0x1800704ee  mov     ecx, esi; uFlags
0x1800704f0  call    cs:__imp_LocalAlloc
0x1800704f6  mov     rsi, rax
0x1800704f9  test    rax, rax
0x1800704fc  jz      loc_180070596
0x180070502  mov     edx, [rbp+arg_10]
0x180070505  lea     rax, [rbp+arg_10]
0x180070509  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18007050d  mov     r9, rsi; KeyValueInformation
0x180070510  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180070515  mov     r8d, 2; KeyValueInformationClass
0x18007051b  mov     [rsp+80h+Length], edx; Length
0x18007051f  lea     rdx, [rbp+ValueName]; ValueName
0x180070523  call    cs:__imp_NtQueryValueKey
0x180070529  mov     ebx, eax
0x18007052b  test    eax, eax
0x18007052d  js      short loc_180070564
0x18007052f  mov     edx, [rsi+8]; uBytes
0x180070532  mov     ecx, 40h ; '@'; uFlags
0x180070537  call    cs:__imp_LocalAlloc
0x18007053d  mov     [r14], rax
0x180070540  test    rax, rax
0x180070543  jz      short loc_18007055D
0x180070545  mov     r8d, [rsi+8]; Size
0x180070549  lea     rdx, [rsi+0Ch]; Src
0x18007054d  mov     rcx, rax; void *
0x180070550  call    memcpy_0
0x180070555  mov     eax, [rsi+8]
0x180070558  mov     [r15], eax
0x18007055b  jmp     short loc_18007058B
0x18007055d  mov     ebx, 0C0000017h
0x180070562  jmp     short loc_18007058B
0x180070564  mov     rcx, cs:WPP_GLOBAL_Control
0x18007056b  test    byte ptr [rcx+44h], 80h
0x18007056f  jz      short loc_18007058B
0x180070571  cmp     byte ptr [rcx+41h], 2
0x180070575  jb      short loc_18007058B
0x180070577  mov     rcx, [rcx+38h]
0x18007057b  mov     edx, 0A2h
0x180070580  mov     r9d, eax
0x180070583  mov     r8, r12
0x180070586  call    WPP_SF_d
0x18007058b  mov     rcx, rsi; hMem
0x18007058e  call    cs:__imp_LocalFree
0x180070594  jmp     short loc_1800705E8
0x180070596  mov     rcx, cs:WPP_GLOBAL_Control
0x18007059d  test    byte ptr [rcx+44h], 80h
0x1800705a1  jz      short loc_1800705BA
0x1800705a3  cmp     byte ptr [rcx+41h], 2
0x1800705a7  jb      short loc_1800705BA
0x1800705a9  mov     rcx, [rcx+38h]
0x1800705ad  mov     edx, 0A3h
0x1800705b2  mov     r8, r12
0x1800705b5  call    WPP_SF_
0x1800705ba  mov     ebx, 0C0000017h
0x1800705bf  jmp     short loc_1800705E8
0x1800705c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800705c8  test    byte ptr [rcx+44h], 80h
0x1800705cc  jz      short loc_1800705E8
0x1800705ce  cmp     byte ptr [rcx+41h], 2
0x1800705d2  jb      short loc_1800705E8
0x1800705d4  mov     rcx, [rcx+38h]
0x1800705d8  mov     edx, 0A4h
0x1800705dd  mov     r9d, eax
0x1800705e0  mov     r8, r12
0x1800705e3  call    WPP_SF_d
0x1800705e8  mov     rcx, [rbp+KeyHandle]; Handle
0x1800705ec  call    cs:__imp_NtClose
0x1800705f2  test    eax, eax
0x1800705f4  jns     short loc_180070637
0x1800705f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800705fd  test    byte ptr [rcx+44h], 80h
0x180070601  jz      short loc_18007063E
0x180070603  cmp     byte ptr [rcx+41h], 2
0x180070607  jb      short loc_18007063E
0x180070609  mov     edx, 0A5h
0x18007060e  jmp     short loc_180070628
0x180070610  mov     rcx, cs:WPP_GLOBAL_Control
0x180070617  test    byte ptr [rcx+44h], 80h
0x18007061b  jz      short loc_18007063E
0x18007061d  cmp     byte ptr [rcx+41h], 2
0x180070621  jb      short loc_18007063E
0x180070623  mov     edx, 0A6h
0x180070628  mov     rcx, [rcx+38h]
0x18007062c  mov     r9d, eax
0x18007062f  mov     r8, r12
0x180070632  call    WPP_SF_d
0x180070637  mov     rcx, cs:WPP_GLOBAL_Control
0x18007063e  test    dword ptr [rcx+44h], 20000h
0x180070645  jz      short loc_18007065F
0x180070647  mov     rcx, [rcx+38h]
0x18007064b  mov     edx, 0A7h
0x180070650  mov     r9d, ebx
0x180070653  mov     [rsp+80h+Length], ebx
0x180070657  mov     r8, r12
0x18007065a  call    WPP_SF_Dd
0x18007065f  mov     eax, ebx
0x180070661  mov     rbx, [rsp+80h+arg_0]
0x180070669  add     rsp, 80h
0x180070670  pop     r15
0x180070672  pop     r14
0x180070674  pop     r12
0x180070676  pop     rsi
0x180070677  pop     rbp
0x180070678  retn
```
