# SampGetAdminPasswordFromRegistry(_USER_INTERNAL1_INFORMATION *)

- ea: `0x18006e15c`
- end: `0x18006e41e`
- name: `?SampGetAdminPasswordFromRegistry@@YAJPEAU_USER_INTERNAL1_INFORMATION@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(struct _USER_INTERNAL1_INFORMATION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070b54`
- `0x180073870`
- `0x1800799a8`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x18006e15c`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18006e1e2`
- `ntdll!NtOpenKey` at `0x18006e1e2`
- `ntdll!NtQueryValueKey` at `0x18006e22b`
- `ntdll!NtQueryValueKey` at `0x18006e271`
- `ntdll!NtQueryValueKey` at `0x18006e22b`
- `ntdll!NtQueryValueKey` at `0x18006e271`
- `ntdll!NtClose` at `0x18006e349`
- `ntdll!NtClose` at `0x18006e349`
- `ntdll!RtlInitUnicodeString` at `0x18006e1a9`
- `ntdll!RtlInitUnicodeString` at `0x18006e205`
- `ntdll!RtlInitUnicodeString` at `0x18006e1a9`
- `ntdll!RtlInitUnicodeString` at `0x18006e205`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e240`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e240`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e3a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e3a4`

## string_xrefs

- `0x18006e18e`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 __fastcall SampGetAdminPasswordFromRegistry(struct _USER_INTERNAL1_INFORMATION *a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  char *v4; // rdi
  ULONG v5; // r12d
  PUNICODE_STRING v6; // rcx
  PUNICODE_STRING v7; // rcx
  __int64 v8; // rax
  _BYTE *v9; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Length; // [rsp+A8h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
  Length = 0;
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
  if ( v2 >= 0 )
  {
    v4 = 0;
    Length = 0;
    v5 = 0;
    RtlInitUnicodeString(&ValueName, L"AdminInfo");
    v3 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, Length, &Length);
    if ( v3 == -1073741789 )
    {
      v4 = (char *)LocalAlloc(0x40u, Length);
      if ( !v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 141, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
          v6 = WPP_GLOBAL_Control;
        }
        v3 = -1073741801;
        goto LABEL_19;
      }
      v5 = Length;
      v3 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v4, Length, &Length);
    }
    if ( (v3 & 0x80000000) == 0 )
    {
      if ( *((_DWORD *)v4 + 2) == 35 )
      {
        if ( a1 )
        {
          *(_OWORD *)a1 = *(_OWORD *)(v4 + 12);
          *((_OWORD *)a1 + 1) = *(_OWORD *)(v4 + 28);
          *(_DWORD *)((char *)a1 + 31) = *(_DWORD *)(v4 + 43);
        }
      }
      else
      {
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 142, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
        v3 = -1073741823;
      }
      goto LABEL_22;
    }
    if ( v3 == -1073741772 )
      goto LABEL_22;
    v6 = WPP_GLOBAL_Control;
LABEL_19:
    if ( *((char *)&v6[4].MaximumLength + 2) < 0 && HIBYTE(v6[4].Length) >= 2u )
      WPP_SF_d(v6[3].Buffer, 143, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v3);
LABEL_22:
    if ( NtClose(KeyHandle) < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
        goto LABEL_27;
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 144, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v3);
    }
    v7 = WPP_GLOBAL_Control;
LABEL_27:
    if ( !v4 )
      goto LABEL_35;
    v8 = v5;
    v9 = v4;
    if ( v5 )
    {
      do
      {
        *v9++ = 0;
        --v8;
      }
      while ( v8 );
    }
    LocalFree(v4);
    goto LABEL_34;
  }
  v7 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 145, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v2);
LABEL_34:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_35:
  if ( (*(_DWORD *)(&v7[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v7[3].Buffer, 146, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v3, v3);
  return v3;
}

```

## disassembly

```asm
0x18006e15c  mov     [rsp-18h+arg_0], rbx
0x18006e161  mov     [rsp-18h+arg_18], rdi
0x18006e166  push    rbp
0x18006e167  push    r12
0x18006e169  push    r15
0x18006e16b  mov     rbp, rsp
0x18006e16e  sub     rsp, 80h
0x18006e175  xorps   xmm0, xmm0
0x18006e178  mov     [rbp+KeyHandle], 0
0x18006e180  mov     r15, rcx
0x18006e183  mov     [rbp+arg_8], 0
0x18006e18a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006e18e  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006e195  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006e199  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006e19d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006e1a1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006e1a5  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18006e1a9  call    cs:__imp_RtlInitUnicodeString
0x18006e1af  lea     rax, [rbp+DestinationString]
0x18006e1b3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006e1ba  xorps   xmm0, xmm0
0x18006e1bd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006e1c1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006e1c5  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006e1cd  mov     edx, 10000000h; DesiredAccess
0x18006e1d2  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006e1d9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18006e1dd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006e1e2  call    cs:__imp_NtOpenKey
0x18006e1e8  mov     ebx, eax
0x18006e1ea  test    eax, eax
0x18006e1ec  js      loc_18006E3AC
0x18006e1f2  xor     edi, edi
0x18006e1f4  lea     rdx, aAdmininfo; "AdminInfo"
0x18006e1fb  lea     rcx, [rbp+ValueName]; DestinationString
0x18006e1ff  mov     [rbp+arg_8], edi
0x18006e202  xor     r12d, r12d
0x18006e205  call    cs:__imp_RtlInitUnicodeString
0x18006e20b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006e20f  lea     rax, [rbp+arg_8]
0x18006e213  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18006e218  lea     r8d, [r12+2]; KeyValueInformationClass
0x18006e21d  mov     eax, [rbp+arg_8]
0x18006e220  lea     rdx, [rbp+ValueName]; ValueName
0x18006e224  xor     r9d, r9d; KeyValueInformation
0x18006e227  mov     [rsp+80h+Length], eax; Length
0x18006e22b  call    cs:__imp_NtQueryValueKey
0x18006e231  mov     ebx, eax
0x18006e233  cmp     eax, 0C0000023h
0x18006e238  jnz     short loc_18006E279
0x18006e23a  mov     edx, [rbp+arg_8]; uBytes
0x18006e23d  lea     ecx, [rdi+40h]; uFlags
0x18006e240  call    cs:__imp_LocalAlloc
0x18006e246  mov     rdi, rax
0x18006e249  test    rax, rax
0x18006e24c  jz      short loc_18006E2AD
0x18006e24e  mov     r12d, [rbp+arg_8]
0x18006e252  lea     rax, [rbp+arg_8]
0x18006e256  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006e25a  lea     rdx, [rbp+ValueName]; ValueName
0x18006e25e  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18006e263  mov     r9, rdi; KeyValueInformation
0x18006e266  mov     r8d, 2; KeyValueInformationClass
0x18006e26c  mov     [rsp+80h+Length], r12d; Length
0x18006e271  call    cs:__imp_NtQueryValueKey
0x18006e277  mov     ebx, eax
0x18006e279  test    ebx, ebx
0x18006e27b  js      loc_18006E312
0x18006e281  cmp     dword ptr [rdi+8], 23h ; '#'
0x18006e285  jnz     short loc_18006E2E3
0x18006e287  test    r15, r15
0x18006e28a  jz      loc_18006E345
0x18006e290  movups  xmm0, xmmword ptr [rdi+0Ch]
0x18006e294  movups  xmmword ptr [r15], xmm0
0x18006e298  movups  xmm1, xmmword ptr [rdi+1Ch]
0x18006e29c  movups  xmmword ptr [r15+10h], xmm1
0x18006e2a1  mov     eax, [rdi+2Bh]
0x18006e2a4  mov     [r15+1Fh], eax
0x18006e2a8  jmp     loc_18006E345
0x18006e2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2b4  test    byte ptr [rcx+44h], 80h
0x18006e2b8  jz      short loc_18006E2DC
0x18006e2ba  cmp     byte ptr [rcx+41h], 2
0x18006e2be  jb      short loc_18006E2DC
0x18006e2c0  mov     rcx, [rcx+38h]
0x18006e2c4  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006e2cb  mov     edx, 8Dh
0x18006e2d0  call    WPP_SF_
0x18006e2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2dc  mov     ebx, 0C0000017h
0x18006e2e1  jmp     short loc_18006E321
0x18006e2e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2ea  test    byte ptr [rcx+44h], 80h
0x18006e2ee  jz      short loc_18006E30B
0x18006e2f0  cmp     byte ptr [rcx+41h], 2
0x18006e2f4  jb      short loc_18006E30B
0x18006e2f6  mov     rcx, [rcx+38h]
0x18006e2fa  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006e301  mov     edx, 8Eh
0x18006e306  call    WPP_SF_
0x18006e30b  mov     ebx, 0C0000001h
0x18006e310  jmp     short loc_18006E345
0x18006e312  cmp     ebx, 0C0000034h
0x18006e318  jz      short loc_18006E345
0x18006e31a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e321  test    byte ptr [rcx+44h], 80h
0x18006e325  jz      short loc_18006E345
0x18006e327  cmp     byte ptr [rcx+41h], 2
0x18006e32b  jb      short loc_18006E345
0x18006e32d  mov     rcx, [rcx+38h]
0x18006e331  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006e338  mov     edx, 8Fh
0x18006e33d  mov     r9d, ebx
0x18006e340  call    WPP_SF_d
0x18006e345  mov     rcx, [rbp+KeyHandle]; Handle
0x18006e349  call    cs:__imp_NtClose
0x18006e34f  test    eax, eax
0x18006e351  jns     short loc_18006E37E
0x18006e353  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e35a  test    byte ptr [rcx+44h], 80h
0x18006e35e  jz      short loc_18006E385
0x18006e360  cmp     byte ptr [rcx+41h], 2
0x18006e364  jb      short loc_18006E385
0x18006e366  mov     rcx, [rcx+38h]
0x18006e36a  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006e371  mov     edx, 90h
0x18006e376  mov     r9d, ebx
0x18006e379  call    WPP_SF_d
0x18006e37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e385  test    rdi, rdi
0x18006e388  jz      short loc_18006E3DE
0x18006e38a  mov     eax, r12d
0x18006e38d  mov     rcx, rdi
0x18006e390  test    r12d, r12d
0x18006e393  jz      short loc_18006E3A1
0x18006e395  mov     byte ptr [rcx], 0
0x18006e398  inc     rcx
0x18006e39b  sub     rax, 1
0x18006e39f  jnz     short loc_18006E395
0x18006e3a1  mov     rcx, rdi; hMem
0x18006e3a4  call    cs:__imp_LocalFree
0x18006e3aa  jmp     short loc_18006E3D7
0x18006e3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e3b3  test    byte ptr [rcx+44h], 80h
0x18006e3b7  jz      short loc_18006E3DE
0x18006e3b9  cmp     byte ptr [rcx+41h], 2
0x18006e3bd  jb      short loc_18006E3DE
0x18006e3bf  mov     rcx, [rcx+38h]
0x18006e3c3  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006e3ca  mov     edx, 91h
0x18006e3cf  mov     r9d, eax
0x18006e3d2  call    WPP_SF_d
0x18006e3d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e3de  test    dword ptr [rcx+44h], 20000h
0x18006e3e5  jz      short loc_18006E403
0x18006e3e7  mov     rcx, [rcx+38h]
0x18006e3eb  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006e3f2  mov     edx, 92h
0x18006e3f7  mov     [rsp+80h+Length], ebx
0x18006e3fb  mov     r9d, ebx
0x18006e3fe  call    WPP_SF_Dd
0x18006e403  lea     r11, [rsp+80h+var_s0]
0x18006e40b  mov     eax, ebx
0x18006e40d  mov     rbx, [r11+20h]
0x18006e411  mov     rdi, [r11+38h]
0x18006e415  mov     rsp, r11
0x18006e418  pop     r15
0x18006e41a  pop     r12
0x18006e41c  pop     rbp
0x18006e41d  retn
```
