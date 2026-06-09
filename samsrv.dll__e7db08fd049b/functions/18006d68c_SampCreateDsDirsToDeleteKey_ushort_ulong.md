# SampCreateDsDirsToDeleteKey(ushort *,ulong)

- ea: `0x18006d68c`
- end: `0x18006d847`
- name: `?SampCreateDsDirsToDeleteKey@@YAJPEAGK@Z`
- size: `443`
- prototype: `__int64 __fastcall(PVOID Data, ULONG DataSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180071374`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x18006d68c`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x18006d74e`
- `ntdll!NtSetValueKey` at `0x18006d74e`
- `ntdll!NtOpenKey` at `0x18006d70c`
- `ntdll!NtOpenKey` at `0x18006d70c`
- `ntdll!NtFlushKey` at `0x18006d785`
- `ntdll!NtFlushKey` at `0x18006d785`
- `ntdll!NtClose` at `0x18006d7ba`
- `ntdll!NtClose` at `0x18006d7ba`
- `ntdll!RtlInitUnicodeString` at `0x18006d6d3`
- `ntdll!RtlInitUnicodeString` at `0x18006d72e`
- `ntdll!RtlInitUnicodeString` at `0x18006d6d3`
- `ntdll!RtlInitUnicodeString` at `0x18006d72e`

## string_xrefs

- `0x18006d6b4`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 __fastcall SampCreateDsDirsToDeleteKey(PVOID Data, ULONG DataSize)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  PUNICODE_STRING v8; // rcx
  __int64 v9; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
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
    v8 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v9 = 178;
      goto LABEL_17;
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"DsDirs");
    v6 = NtSetValueKey(KeyHandle, &ValueName, 0, 7u, Data, DataSize);
    v5 = v6;
    if ( v6 < 0 && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 175, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v6);
    v7 = NtFlushKey(KeyHandle);
    if ( v7 < 0 && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 176, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v7);
    v4 = NtClose(KeyHandle);
    if ( v4 >= 0 )
      goto LABEL_18;
    v8 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v9 = 177;
LABEL_17:
      WPP_SF_d(v8[3].Buffer, v9, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v4);
LABEL_18:
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_DWORD *)(&v8[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v8[3].Buffer, 179, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v5, v5);
  return v5;
}

```

## disassembly

```asm
0x18006d68c  mov     [rsp-18h+arg_0], rbx
0x18006d691  mov     [rsp-18h+arg_8], rsi
0x18006d696  push    rbp
0x18006d697  push    rdi
0x18006d698  push    r14
0x18006d69a  mov     rbp, rsp
0x18006d69d  sub     rsp, 80h
0x18006d6a4  xorps   xmm0, xmm0
0x18006d6a7  mov     [rbp+KeyHandle], 0
0x18006d6af  mov     edi, edx
0x18006d6b1  mov     rsi, rcx
0x18006d6b4  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006d6bb  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006d6bf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006d6c3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006d6c7  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d6cb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006d6cf  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18006d6d3  call    cs:__imp_RtlInitUnicodeString
0x18006d6d9  lea     rax, [rbp+DestinationString]
0x18006d6dd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006d6e4  xorps   xmm0, xmm0
0x18006d6e7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006d6eb  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006d6ef  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006d6f7  mov     edx, 10000000h; DesiredAccess
0x18006d6fc  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006d703  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18006d707  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d70c  call    cs:__imp_NtOpenKey
0x18006d712  lea     r14, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006d719  mov     ebx, eax
0x18006d71b  test    eax, eax
0x18006d71d  js      loc_18006D7DE
0x18006d723  lea     rdx, aDsdirs; "DsDirs"
0x18006d72a  lea     rcx, [rbp+ValueName]; DestinationString
0x18006d72e  call    cs:__imp_RtlInitUnicodeString
0x18006d734  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006d738  lea     rdx, [rbp+ValueName]; ValueName
0x18006d73c  mov     r9d, 7; Type
0x18006d742  mov     [rsp+80h+DataSize], edi; DataSize
0x18006d746  xor     r8d, r8d; TitleIndex
0x18006d749  mov     [rsp+80h+Data], rsi; Data
0x18006d74e  call    cs:__imp_NtSetValueKey
0x18006d754  mov     ebx, eax
0x18006d756  test    eax, eax
0x18006d758  jns     short loc_18006D781
0x18006d75a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d761  test    byte ptr [rcx+44h], 80h
0x18006d765  jz      short loc_18006D781
0x18006d767  cmp     byte ptr [rcx+41h], 2
0x18006d76b  jb      short loc_18006D781
0x18006d76d  mov     rcx, [rcx+38h]
0x18006d771  mov     edx, 0AFh
0x18006d776  mov     r9d, eax
0x18006d779  mov     r8, r14
0x18006d77c  call    WPP_SF_d
0x18006d781  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006d785  call    cs:__imp_NtFlushKey
0x18006d78b  test    eax, eax
0x18006d78d  jns     short loc_18006D7B6
0x18006d78f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d796  test    byte ptr [rcx+44h], 80h
0x18006d79a  jz      short loc_18006D7B6
0x18006d79c  cmp     byte ptr [rcx+41h], 2
0x18006d7a0  jb      short loc_18006D7B6
0x18006d7a2  mov     rcx, [rcx+38h]
0x18006d7a6  mov     edx, 0B0h
0x18006d7ab  mov     r9d, eax
0x18006d7ae  mov     r8, r14
0x18006d7b1  call    WPP_SF_d
0x18006d7b6  mov     rcx, [rbp+KeyHandle]; Handle
0x18006d7ba  call    cs:__imp_NtClose
0x18006d7c0  test    eax, eax
0x18006d7c2  jns     short loc_18006D805
0x18006d7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d7cb  test    byte ptr [rcx+44h], 80h
0x18006d7cf  jz      short loc_18006D80C
0x18006d7d1  cmp     byte ptr [rcx+41h], 2
0x18006d7d5  jb      short loc_18006D80C
0x18006d7d7  mov     edx, 0B1h
0x18006d7dc  jmp     short loc_18006D7F6
0x18006d7de  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d7e5  test    byte ptr [rcx+44h], 80h
0x18006d7e9  jz      short loc_18006D80C
0x18006d7eb  cmp     byte ptr [rcx+41h], 2
0x18006d7ef  jb      short loc_18006D80C
0x18006d7f1  mov     edx, 0B2h
0x18006d7f6  mov     rcx, [rcx+38h]
0x18006d7fa  mov     r9d, eax
0x18006d7fd  mov     r8, r14
0x18006d800  call    WPP_SF_d
0x18006d805  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d80c  test    dword ptr [rcx+44h], 20000h
0x18006d813  jz      short loc_18006D82D
0x18006d815  mov     rcx, [rcx+38h]
0x18006d819  mov     edx, 0B3h
0x18006d81e  mov     r9d, ebx
0x18006d821  mov     dword ptr [rsp+80h+Data], ebx
0x18006d825  mov     r8, r14
0x18006d828  call    WPP_SF_Dd
0x18006d82d  lea     r11, [rsp+80h+var_s0]
0x18006d835  mov     eax, ebx
0x18006d837  mov     rbx, [r11+20h]
0x18006d83b  mov     rsi, [r11+28h]
0x18006d83f  mov     rsp, r11
0x18006d842  pop     r14
0x18006d844  pop     rdi
0x18006d845  pop     rbp
0x18006d846  retn
```
